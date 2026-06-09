# CDRMStore::CreateFileForReadWrite(ushort *,int,void * *)

- ea: `0x180034e44`
- end: `0x180034f62`
- name: `?CreateFileForReadWrite@CDRMStore@@AEAAJPEAGHPEAPEAX@Z`
- size: `286`
- prototype: `int(CDRMStore *__hidden this, unsigned __int16 *, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180034c24`
- `0x18003650c`

## callees

- `0x180034e44`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034f22`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034f22`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180034eeb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180034eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f2e`

## pseudocode

```c
__int64 __fastcall CDRMStore::CreateFileForReadWrite(CDRMStore *this, unsigned __int16 *a2, int a3, void **a4)
{
  DWORD dwCreationDisposition; // edi
  struct _SECURITY_ATTRIBUTES *v7; // r9
  unsigned __int64 v8; // rbp
  int v9; // r15d
  DWORD v10; // r12d
  HANDLE FileW; // rax
  DWORD LastError; // ebx

  if ( !a2 || !a4 )
    return (DWORD)-2147024809;
  dwCreationDisposition = 3 - (a3 != 0);
  if ( g_fGlobalOptionUseServerProc )
    v7 = (struct _SECURITY_ATTRIBUTES *)((char *)this + 24);
  else
    v7 = 0;
  v8 = (unsigned __int64)this + 24;
  v9 = a3 != 0;
  v10 = (-v9 & 0xC0000000) + 0x80000000;
  FileW = CreateFileW(a2, v10, v9 + 5, v7, 3 - v9, 0x81u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_13;
  LastError = GetLastError();
  if ( LastError != 5 )
    goto LABEL_11;
  if ( !SetFileAttributesW(a2, 0x80u) )
    return (unsigned __int16)LastError | 0x80070000;
  FileW = CreateFileW(
            a2,
            v10,
            v9 + 5,
            (LPSECURITY_ATTRIBUTES)(v8 & -(__int64)(g_fGlobalOptionUseServerProc != 0)),
            dwCreationDisposition,
            0x81u,
            0);
  if ( FileW != (HANDLE)-1LL )
  {
LABEL_13:
    LastError = 0;
    *a4 = FileW;
    return LastError;
  }
  LastError = GetLastError();
LABEL_11:
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180034e44  push    rbx
0x180034e46  push    rbp
0x180034e47  push    rsi
0x180034e48  push    rdi
0x180034e49  push    r12
0x180034e4b  push    r14
0x180034e4d  push    r15
0x180034e4f  sub     rsp, 40h
0x180034e53  mov     r14, r9
0x180034e56  mov     rsi, rdx
0x180034e59  test    rdx, rdx
0x180034e5c  jz      loc_180034F4C
0x180034e62  test    r9, r9
0x180034e65  jz      loc_180034F4C
0x180034e6b  mov     eax, r8d
0x180034e6e  neg     eax
0x180034e70  sbb     edi, edi
0x180034e72  add     edi, 3
0x180034e75  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, 0; int g_fGlobalOptionUseServerProc
0x180034e7c  jz      short loc_180034E87
0x180034e7e  lea     r9, [rcx+18h]
0x180034e82  mov     rbp, r9
0x180034e85  jmp     short loc_180034E8E
0x180034e87  xor     r9d, r9d; lpSecurityAttributes
0x180034e8a  lea     rbp, [rcx+18h]
0x180034e8e  mov     eax, r8d
0x180034e91  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180034e9a  neg     eax
0x180034e9c  mov     [rsp+78h+dwFlagsAndAttributes], 81h; dwFlagsAndAttributes
0x180034ea4  mov     rcx, rsi; lpFileName
0x180034ea7  mov     [rsp+78h+dwCreationDisposition], edi; dwCreationDisposition
0x180034eab  sbb     r15d, r15d
0x180034eae  neg     r15d
0x180034eb1  neg     r8d
0x180034eb4  sbb     r12d, r12d
0x180034eb7  and     r12d, 0C0000000h
0x180034ebe  lea     r8d, [r15+5]; dwShareMode
0x180034ec2  add     r12d, 80000000h
0x180034ec9  mov     edx, r12d; dwDesiredAccess
0x180034ecc  call    cs:__imp_CreateFileW
0x180034ed2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034ed6  jnz     short loc_180034F45
0x180034ed8  call    cs:__imp_GetLastError
0x180034ede  mov     ebx, eax
0x180034ee0  cmp     eax, 5
0x180034ee3  jnz     short loc_180034F36
0x180034ee5  lea     edx, [rax+7Bh]; dwFileAttributes
0x180034ee8  mov     rcx, rsi; lpFileName
0x180034eeb  call    cs:__imp_SetFileAttributesW
0x180034ef1  test    eax, eax
0x180034ef3  jz      short loc_180034F3A
0x180034ef5  mov     eax, cs:?g_fGlobalOptionUseServerProc@@3HA; int g_fGlobalOptionUseServerProc
0x180034efb  lea     r8d, [r15+5]; dwShareMode
0x180034eff  neg     eax
0x180034f01  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180034f0a  mov     [rsp+78h+dwFlagsAndAttributes], 81h; dwFlagsAndAttributes
0x180034f12  mov     edx, r12d; dwDesiredAccess
0x180034f15  sbb     r9, r9
0x180034f18  mov     [rsp+78h+dwCreationDisposition], edi; dwCreationDisposition
0x180034f1c  and     r9, rbp; lpSecurityAttributes
0x180034f1f  mov     rcx, rsi; lpFileName
0x180034f22  call    cs:__imp_CreateFileW
0x180034f28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034f2c  jnz     short loc_180034F45
0x180034f2e  call    cs:__imp_GetLastError
0x180034f34  mov     ebx, eax
0x180034f36  test    ebx, ebx
0x180034f38  jle     short loc_180034F51
0x180034f3a  movzx   ebx, bx
0x180034f3d  or      ebx, 80070000h
0x180034f43  jmp     short loc_180034F51
0x180034f45  xor     ebx, ebx
0x180034f47  mov     [r14], rax
0x180034f4a  jmp     short loc_180034F51
0x180034f4c  mov     ebx, 80070057h
0x180034f51  mov     eax, ebx
0x180034f53  add     rsp, 40h
0x180034f57  pop     r15
0x180034f59  pop     r14
0x180034f5b  pop     r12
0x180034f5d  pop     rdi
0x180034f5e  pop     rsi
0x180034f5f  pop     rbp
0x180034f60  pop     rbx
0x180034f61  retn
```
