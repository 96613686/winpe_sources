# GetCompressedFileSizeTransactedW

- ea: `0x18006be90`
- end: `0x18006befb`
- name: `GetCompressedFileSizeTransactedW`
- size: `107`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006be30`

## callees

- `0x18006be90`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006beb0`
- `ntdll!RtlGetCurrentTransaction` at `0x18006beb0`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bec5`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bedc`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bec5`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bedc`
- `ntdll!RtlSetLastWin32Error` at `0x18006bee9`
- `ntdll!RtlSetLastWin32Error` at `0x18006bee9`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x18006bed2`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x18006bed2`

## pseudocode

```c
DWORD __stdcall GetCompressedFileSizeTransactedW(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh, HANDLE hTransaction)
{
  DWORD CompressedFileSizeW; // ebx
  ULONG v7; // ecx

  CompressedFileSizeW = -1;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v7 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v7 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v7);
    return CompressedFileSizeW;
  }
  RtlSetCurrentTransaction(hTransaction);
  CompressedFileSizeW = GetCompressedFileSizeW(lpFileName, lpFileSizeHigh);
  RtlSetCurrentTransaction(0);
  return CompressedFileSizeW;
}

```

## disassembly

```asm
0x18006be90  push    rbx
0x18006be92  push    rsi
0x18006be93  push    rdi
0x18006be94  push    r14
0x18006be96  sub     rsp, 28h
0x18006be9a  mov     rdi, r8
0x18006be9d  mov     rsi, rdx
0x18006bea0  mov     r14, rcx
0x18006bea3  or      ebx, 0FFFFFFFFh
0x18006bea6  lea     rax, [r8-1]
0x18006beaa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006beae  ja      short loc_18006BEE4
0x18006beb0  call    cs:__imp_RtlGetCurrentTransaction
0x18006beb6  test    rax, rax
0x18006beb9  jz      short loc_18006BEC2
0x18006bebb  mov     ecx, 1A45h
0x18006bec0  jmp     short loc_18006BEE9
0x18006bec2  mov     rcx, rdi
0x18006bec5  call    cs:__imp_RtlSetCurrentTransaction
0x18006becb  nop
0x18006becc  mov     rdx, rsi; lpFileSizeHigh
0x18006becf  mov     rcx, r14; lpFileName
0x18006bed2  call    cs:__imp_GetCompressedFileSizeW
0x18006bed8  mov     ebx, eax
0x18006beda  xor     ecx, ecx
0x18006bedc  call    cs:__imp_RtlSetCurrentTransaction
0x18006bee2  jmp     short loc_18006BEEF
0x18006bee4  mov     ecx, 1A2Ch; LastError
0x18006bee9  call    cs:__imp_RtlSetLastWin32Error
0x18006beef  mov     eax, ebx
0x18006bef1  add     rsp, 28h
0x18006bef5  pop     r14
0x18006bef7  pop     rdi
0x18006bef8  pop     rsi
0x18006bef9  pop     rbx
0x18006befa  retn
0x18007b737  push    rbp
0x18007b739  sub     rsp, 20h
0x18007b73d  mov     rbp, rdx
0x18007b740  xor     ecx, ecx
0x18007b742  add     rsp, 20h
0x18007b746  pop     rbp
0x18007b747  jmp     cs:__imp_RtlSetCurrentTransaction
```
