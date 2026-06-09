# GetMachineName(ushort * *)

- ea: `0x18001dc64`
- end: `0x18001dd03`
- name: `?GetMachineName@@YAKPEAPEAG@Z`
- size: `159`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001dbfc`
- `0x18001dd0c`

## callees

- `0x18001dc64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dceb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dceb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dcb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dcb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcc5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001dc82`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001dcd7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001dc82`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001dcd7`

## pseudocode

```c
__int64 __fastcall GetMachineName(unsigned __int16 **a1)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  WCHAR *v4; // rdi
  SIZE_T v5; // rdx
  WCHAR *v6; // rax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  nSize = 0;
  if ( !GetComputerNameW(0, &nSize) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 111 )
    {
      v2 = 0;
    }
    else
    {
      v4 = 0;
      if ( LastError )
      {
LABEL_10:
        LocalFree(v4);
        return v2;
      }
    }
  }
  v5 = 2LL * ++nSize;
  v6 = (WCHAR *)LocalAlloc(0x40u, v5);
  v4 = v6;
  if ( v6 && GetComputerNameW(v6, &nSize) )
    *a1 = v4;
  else
    v2 = GetLastError();
  if ( v2 )
    goto LABEL_10;
  return v2;
}

```

## disassembly

```asm
0x18001dc64  mov     rax, rsp
0x18001dc67  mov     [rax+8], rbx
0x18001dc6b  mov     [rax+18h], rsi
0x18001dc6f  push    rdi
0x18001dc70  sub     rsp, 20h
0x18001dc74  mov     rsi, rcx
0x18001dc77  lea     rdx, [rax+10h]; nSize
0x18001dc7b  xor     ebx, ebx
0x18001dc7d  xor     ecx, ecx; lpBuffer
0x18001dc7f  mov     [rax+10h], ebx
0x18001dc82  call    cs:__imp_GetComputerNameW
0x18001dc88  test    eax, eax
0x18001dc8a  jnz     short loc_18001DCA3
0x18001dc8c  call    cs:__imp_GetLastError
0x18001dc92  mov     ebx, eax
0x18001dc94  cmp     eax, 6Fh ; 'o'
0x18001dc97  jnz     short loc_18001DC9D
0x18001dc99  xor     ebx, ebx
0x18001dc9b  jmp     short loc_18001DCA3
0x18001dc9d  xor     edi, edi
0x18001dc9f  test    eax, eax
0x18001dca1  jnz     short loc_18001DCE8
0x18001dca3  mov     eax, [rsp+28h+nSize]
0x18001dca7  mov     ecx, 40h ; '@'; uFlags
0x18001dcac  inc     eax
0x18001dcae  mov     edx, eax
0x18001dcb0  add     rdx, rdx; uBytes
0x18001dcb3  mov     [rsp+28h+nSize], eax
0x18001dcb7  call    cs:__imp_LocalAlloc
0x18001dcbd  mov     rdi, rax
0x18001dcc0  test    rax, rax
0x18001dcc3  jnz     short loc_18001DCCF
0x18001dcc5  call    cs:__imp_GetLastError
0x18001dccb  mov     ebx, eax
0x18001dccd  jmp     short loc_18001DCE4
0x18001dccf  lea     rdx, [rsp+28h+nSize]; nSize
0x18001dcd4  mov     rcx, rdi; lpBuffer
0x18001dcd7  call    cs:__imp_GetComputerNameW
0x18001dcdd  test    eax, eax
0x18001dcdf  jz      short loc_18001DCC5
0x18001dce1  mov     [rsi], rdi
0x18001dce4  test    ebx, ebx
0x18001dce6  jz      short loc_18001DCF1
0x18001dce8  mov     rcx, rdi; hMem
0x18001dceb  call    cs:__imp_LocalFree
0x18001dcf1  mov     rsi, [rsp+28h+arg_10]
0x18001dcf6  mov     eax, ebx
0x18001dcf8  mov     rbx, [rsp+28h+arg_0]
0x18001dcfd  add     rsp, 20h
0x18001dd01  pop     rdi
0x18001dd02  retn
```
