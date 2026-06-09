# VerifyFileHasExtensionW(ushort const *)

- ea: `0x14000bb30`
- end: `0x14000bc62`
- name: `?VerifyFileHasExtensionW@@YAJPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140004e20`
- `0x140005188`
- `0x140005630`
- `0x140005b10`
- `0x14000747c`

## callees

- `0x14000bb30`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x14000bb6f`
- `KERNEL32!GetFullPathNameW` at `0x14000bba7`
- `KERNEL32!GetFullPathNameW` at `0x14000bb6f`
- `KERNEL32!GetFullPathNameW` at `0x14000bba7`
- `KERNEL32!GetLastError` at `0x14000bbeb`
- `KERNEL32!GetLastError` at `0x14000bbfd`
- `KERNEL32!GetLastError` at `0x14000bc12`
- `KERNEL32!GetLastError` at `0x14000bbeb`
- `KERNEL32!GetLastError` at `0x14000bbfd`
- `KERNEL32!GetLastError` at `0x14000bc12`
- `msvcrt!wcschr` at `0x14000bbca`
- `msvcrt!wcschr` at `0x14000bbca`
- `ole32!CoTaskMemAlloc` at `0x14000bb86`
- `ole32!CoTaskMemAlloc` at `0x14000bb86`
- `ole32!CoTaskMemFree` at `0x14000bc31`
- `ole32!CoTaskMemFree` at `0x14000bc40`
- `ole32!CoTaskMemFree` at `0x14000bc31`
- `ole32!CoTaskMemFree` at `0x14000bc40`

## pseudocode

```c
__int64 __fastcall VerifyFileHasExtensionW(LPCWSTR lpFileName)
{
  WCHAR *v1; // rsi
  WCHAR *v2; // rdi
  unsigned int v4; // ebx
  DWORD FullPathNameW; // eax
  DWORD v6; // ebp
  WCHAR *v7; // rax
  DWORD v8; // eax
  DWORD LastError; // eax
  WCHAR v11; // [rsp+48h] [rbp+10h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  v4 = -2147024809;
  if ( !lpFileName )
    goto LABEL_18;
  v11 = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 1u, &v11, 0);
  v6 = FullPathNameW;
  if ( !FullPathNameW )
    goto LABEL_10;
  v7 = (WCHAR *)CoTaskMemAlloc(2LL * FullPathNameW);
  v1 = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
LABEL_17:
    v2 = 0;
    goto LABEL_18;
  }
  v8 = GetFullPathNameW(lpFileName, v6, v7, &FilePart);
  if ( !v8 )
  {
LABEL_10:
    if ( (GetLastError() & 0x80000000) == 0 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LOWORD(LastError) = 1;
      v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = GetLastError();
      if ( !v4 )
        v4 = 1;
    }
    goto LABEL_17;
  }
  v2 = 0;
  if ( v8 < v6 && FilePart && wcschr(FilePart, 0x2Eu) )
  {
    v2 = v1;
    v1 = 0;
    v4 = 0;
  }
LABEL_18:
  CoTaskMemFree(v1);
  CoTaskMemFree(v2);
  return v4;
}

```

## disassembly

```asm
0x14000bb30  mov     r11, rsp
0x14000bb33  mov     [r11+8], rbx
0x14000bb37  mov     [r11+20h], rbp
0x14000bb3b  push    rsi
0x14000bb3c  push    rdi
0x14000bb3d  push    r14
0x14000bb3f  sub     rsp, 20h
0x14000bb43  xor     esi, esi
0x14000bb45  xor     edi, edi
0x14000bb47  mov     r14, rcx
0x14000bb4a  mov     ebx, 80070057h
0x14000bb4f  test    rcx, rcx
0x14000bb52  jz      loc_14000BC2E
0x14000bb58  xor     eax, eax
0x14000bb5a  lea     edi, [rsi+1]
0x14000bb5d  mov     edx, edi; nBufferLength
0x14000bb5f  mov     [rsp+38h+arg_8], ax
0x14000bb64  xor     r9d, r9d; lpFilePart
0x14000bb67  mov     [r11+18h], rax
0x14000bb6b  lea     r8, [r11+10h]; lpBuffer
0x14000bb6f  call    cs:__imp_GetFullPathNameW
0x14000bb76  nop     dword ptr [rax+rax+00h]
0x14000bb7b  mov     ebp, eax
0x14000bb7d  test    eax, eax
0x14000bb7f  jz      short loc_14000BBEB
0x14000bb81  mov     ecx, ebp
0x14000bb83  add     rcx, rcx; cb
0x14000bb86  call    cs:__imp_CoTaskMemAlloc
0x14000bb8d  nop     dword ptr [rax+rax+00h]
0x14000bb92  mov     rsi, rax
0x14000bb95  test    rax, rax
0x14000bb98  jz      short loc_14000BBE4
0x14000bb9a  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x14000bb9f  mov     r8, rax; lpBuffer
0x14000bba2  mov     edx, ebp; nBufferLength
0x14000bba4  mov     rcx, r14; lpFileName
0x14000bba7  call    cs:__imp_GetFullPathNameW
0x14000bbae  nop     dword ptr [rax+rax+00h]
0x14000bbb3  test    eax, eax
0x14000bbb5  jz      short loc_14000BBEB
0x14000bbb7  xor     edi, edi
0x14000bbb9  cmp     eax, ebp
0x14000bbbb  jnb     short loc_14000BC2E
0x14000bbbd  mov     rcx, [rsp+38h+FilePart]; Str
0x14000bbc2  test    rcx, rcx
0x14000bbc5  jz      short loc_14000BC2E
0x14000bbc7  lea     edx, [rdi+2Eh]; Ch
0x14000bbca  call    cs:__imp_wcschr
0x14000bbd1  nop     dword ptr [rax+rax+00h]
0x14000bbd6  test    rax, rax
0x14000bbd9  jz      short loc_14000BC2E
0x14000bbdb  mov     rdi, rsi
0x14000bbde  xor     esi, esi
0x14000bbe0  xor     ebx, ebx
0x14000bbe2  jmp     short loc_14000BC2E
0x14000bbe4  mov     ebx, 8007000Eh
0x14000bbe9  jmp     short loc_14000BC2C
0x14000bbeb  call    cs:__imp_GetLastError
0x14000bbf2  nop     dword ptr [rax+rax+00h]
0x14000bbf7  test    eax, eax
0x14000bbf9  jz      short loc_14000BC12
0x14000bbfb  jg      short loc_14000BC12
0x14000bbfd  call    cs:__imp_GetLastError
0x14000bc04  nop     dword ptr [rax+rax+00h]
0x14000bc09  test    eax, eax
0x14000bc0b  mov     ebx, eax
0x14000bc0d  cmovz   ebx, edi
0x14000bc10  jmp     short loc_14000BC2C
0x14000bc12  call    cs:__imp_GetLastError
0x14000bc19  nop     dword ptr [rax+rax+00h]
0x14000bc1e  test    eax, eax
0x14000bc20  cmovz   eax, edi
0x14000bc23  movzx   ebx, ax
0x14000bc26  or      ebx, 80070000h
0x14000bc2c  xor     edi, edi
0x14000bc2e  mov     rcx, rsi; pv
0x14000bc31  call    cs:__imp_CoTaskMemFree
0x14000bc38  nop     dword ptr [rax+rax+00h]
0x14000bc3d  mov     rcx, rdi; pv
0x14000bc40  call    cs:__imp_CoTaskMemFree
0x14000bc47  nop     dword ptr [rax+rax+00h]
0x14000bc4c  mov     rbp, [rsp+38h+arg_18]
0x14000bc51  mov     eax, ebx
0x14000bc53  mov     rbx, [rsp+38h+arg_0]
0x14000bc58  add     rsp, 20h
0x14000bc5c  pop     r14
0x14000bc5e  pop     rdi
0x14000bc5f  pop     rsi
0x14000bc60  retn
```
