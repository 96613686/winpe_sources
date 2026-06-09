# GetFullPathNameTransactedA

- ea: `0x1800635e0`
- end: `0x180063682`
- name: `GetFullPathNameTransactedA`
- size: `162`
- prototype: `DWORD __stdcall(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800635e0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006360e`
- `ntdll!RtlGetCurrentTransaction` at `0x18006360e`
- `ntdll!RtlSetCurrentTransaction` at `0x180063629`
- `ntdll!RtlSetCurrentTransaction` at `0x180063652`
- `ntdll!RtlSetCurrentTransaction` at `0x180063629`
- `ntdll!RtlSetCurrentTransaction` at `0x180063652`
- `ntdll!RtlSetLastWin32Error` at `0x180063665`
- `ntdll!RtlSetLastWin32Error` at `0x180063665`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180063642`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180063642`

## pseudocode

```c
DWORD __stdcall GetFullPathNameTransactedA(
        LPCSTR lpFileName,
        DWORD nBufferLength,
        LPSTR lpBuffer,
        LPSTR *lpFilePart,
        HANDLE hTransaction)
{
  DWORD FullPathNameA; // ebx
  ULONG v10; // ecx

  FullPathNameA = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v10 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v10 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v10);
    return FullPathNameA;
  }
  RtlSetCurrentTransaction(hTransaction);
  FullPathNameA = GetFullPathNameA(lpFileName, nBufferLength, lpBuffer, lpFilePart);
  RtlSetCurrentTransaction(0);
  return FullPathNameA;
}

```

## disassembly

```asm
0x1800635e0  push    rbx
0x1800635e2  push    rsi
0x1800635e3  push    rdi
0x1800635e4  push    r12
0x1800635e6  push    r14
0x1800635e8  push    r15
0x1800635ea  sub     rsp, 28h
0x1800635ee  mov     rsi, r9
0x1800635f1  mov     r14, r8
0x1800635f4  mov     r15d, edx
0x1800635f7  mov     r12, rcx
0x1800635fa  xor     ebx, ebx
0x1800635fc  mov     rdi, [rsp+58h+hTransaction]
0x180063604  lea     rax, [rdi-1]
0x180063608  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006360c  ja      short loc_180063660
0x18006360e  call    cs:__imp_RtlGetCurrentTransaction
0x180063615  nop     dword ptr [rax+rax+00h]
0x18006361a  test    rax, rax
0x18006361d  jz      short loc_180063626
0x18006361f  mov     ecx, 1A45h
0x180063624  jmp     short loc_180063665
0x180063626  mov     rcx, rdi
0x180063629  call    cs:__imp_RtlSetCurrentTransaction
0x180063630  nop     dword ptr [rax+rax+00h]
0x180063635  nop
0x180063636  mov     r9, rsi; lpFilePart
0x180063639  mov     r8, r14; lpBuffer
0x18006363c  mov     edx, r15d; nBufferLength
0x18006363f  mov     rcx, r12; lpFileName
0x180063642  call    cs:__imp_GetFullPathNameA
0x180063649  nop     dword ptr [rax+rax+00h]
0x18006364e  mov     ebx, eax
0x180063650  xor     ecx, ecx
0x180063652  call    cs:__imp_RtlSetCurrentTransaction
0x180063659  nop     dword ptr [rax+rax+00h]
0x18006365e  jmp     short loc_180063671
0x180063660  mov     ecx, 1A2Ch; LastError
0x180063665  call    cs:__imp_RtlSetLastWin32Error
0x18006366c  nop     dword ptr [rax+rax+00h]
0x180063671  mov     eax, ebx
0x180063673  add     rsp, 28h
0x180063677  pop     r15
0x180063679  pop     r14
0x18006367b  pop     r12
0x18006367d  pop     rdi
0x18006367e  pop     rsi
0x18006367f  pop     rbx
0x180063680  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
