# GetCanonicalPathInfoW

- ea: `0x180001ce0`
- end: `0x180001d7b`
- name: `GetCanonicalPathInfoW`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800042d0`

## callees

- `0x1800018c0`
- `0x180001ce0`
- `0x180001d90`
- `0x180001de0`
- `0x180001e30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001d0e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001d0e`

## pseudocode

```c
__int64 __fastcall GetCanonicalPathInfoW(
        const WCHAR *a1,
        WCHAR *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int DrivePathInfo; // eax
  unsigned int v9; // ebx
  LPWSTR FilePart; // [rsp+20h] [rbp-18h] BYREF

  FilePart = 0;
  if ( GetFullPathNameW(a1, 0x104u, a2, &FilePart) - 1 > 0x101 )
    return 0;
  if ( (unsigned int)IsDrivePath(a2) )
    DrivePathInfo = GetDrivePathInfo(a2, a3, a4, a5);
  else
    DrivePathInfo = GetRemotePathInfo(a2, a3, a4, a5);
  v9 = DrivePathInfo;
  if ( DrivePathInfo )
    CanonicalizeTrailingSlash(*a5);
  return v9;
}

```

## disassembly

```asm
0x180001ce0  mov     [rsp+arg_8], rbx
0x180001ce5  mov     [rsp+arg_10], rbp
0x180001cea  push    rsi
0x180001ceb  sub     rsp, 30h
0x180001cef  mov     rbp, r8
0x180001cf2  mov     [rsp+38h+FilePart], 0
0x180001cfb  mov     r8, rdx; lpBuffer
0x180001cfe  mov     rsi, r9
0x180001d01  mov     rbx, rdx
0x180001d04  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x180001d09  mov     edx, 104h; nBufferLength
0x180001d0e  call    cs:__imp_GetFullPathNameW
0x180001d15  nop     dword ptr [rax+rax+00h]
0x180001d1a  dec     eax
0x180001d1c  cmp     eax, 101h
0x180001d21  ja      short loc_180001D77
0x180001d23  mov     rcx, rbx; unsigned __int16 *
0x180001d26  mov     [rsp+38h+arg_0], rdi
0x180001d2b  call    ?IsDrivePath@@YAHPEBG@Z; IsDrivePath(ushort const *)
0x180001d30  mov     rdi, [rsp+38h+arg_20]
0x180001d35  mov     r8, rsi; unsigned __int16 *
0x180001d38  mov     r9, rdi; unsigned __int16 **
0x180001d3b  mov     rdx, rbp; unsigned int *
0x180001d3e  mov     rcx, rbx; unsigned __int16 *
0x180001d41  test    eax, eax
0x180001d43  jz      short loc_180001D70
0x180001d45  call    ?GetDrivePathInfo@@YAHPEAGPEAK0PEAPEAG@Z; GetDrivePathInfo(ushort *,ulong *,ushort *,ushort * *)
0x180001d4a  mov     ebx, eax
0x180001d4c  test    eax, eax
0x180001d4e  jz      short loc_180001D58
0x180001d50  mov     rcx, [rdi]; lpszStart
0x180001d53  call    ?CanonicalizeTrailingSlash@@YAXPEAG@Z; CanonicalizeTrailingSlash(ushort *)
0x180001d58  mov     rdi, [rsp+38h+arg_0]
0x180001d5d  mov     eax, ebx
0x180001d5f  mov     rbx, [rsp+38h+arg_8]
0x180001d64  mov     rbp, [rsp+38h+arg_10]
0x180001d69  add     rsp, 30h
0x180001d6d  pop     rsi
0x180001d6e  retn
0x180001d70  call    ?GetRemotePathInfo@@YAHPEAGPEAK0PEAPEAG@Z; GetRemotePathInfo(ushort *,ulong *,ushort *,ushort * *)
0x180001d75  jmp     short loc_180001D4A
0x180001d77  xor     eax, eax
0x180001d79  jmp     short loc_180001D5F
```
