# OpenFontFile(ushort const *,bool &,uint &)

- ea: `0x1800e9154`
- end: `0x1800e92e5`
- name: `?OpenFontFile@@YAPEAXPEBGAEA_NAEAI@Z`
- size: `401`
- prototype: `void *__fastcall(const unsigned __int16 *, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800e8cac`
- `0x1801462ac`

## callees

- `0x180025a18`
- `0x1800e9154`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800e922c`
- `KERNEL32!CloseHandle` at `0x1800e92da`
- `KERNEL32!CloseHandle` at `0x1800e922c`
- `KERNEL32!CloseHandle` at `0x1800e92da`
- `KERNEL32!SetLastError` at `0x1800e9239`
- `KERNEL32!SetLastError` at `0x1800e9239`
- `KERNEL32!CreateFileW` at `0x1800e91ba`
- `KERNEL32!CreateFileW` at `0x1800e91ba`
- `KERNEL32!GetFileType` at `0x1800e91cc`
- `KERNEL32!GetFileType` at `0x1800e91cc`
- `KERNEL32!ReadFile` at `0x1800e9289`
- `KERNEL32!ReadFile` at `0x1800e9289`

## string_xrefs

- `0x1800e91f5`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
__int64 __fastcall OpenFontFile(const unsigned __int16 *a1, bool *a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  __int64 v8; // rbx
  unsigned int v9; // ecx
  int v10; // edx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-38h] BYREF
  __int64 Buffer; // [rsp+68h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+70h] [rbp-28h]

  *a2 = 0;
  *a3 = 1;
  if ( !a1 )
    return -1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
  v8 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileType(FileW) - 2 > 1 )
    {
      Buffer = 0;
      v13 = 0;
      NumberOfBytesRead = 0;
      if ( !ReadFile((HANDLE)v8, &Buffer, 0xCu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 12 )
      {
        CloseHandle((HANDLE)v8);
        return -1;
      }
      if ( (_DWORD)Buffer == 1717793908 )
      {
        v9 = v13;
        v10 = v13 & 0xFF0000;
        *a2 = 1;
        *a3 = (((v9 << 16) | v9 & 0xFF00) << 8) | ((unsigned int)(HIWORD(v9) | v10) >> 8);
      }
    }
    else
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: This is not a valid file, hence failing to create: %s",
          a1,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CloseHandle((HANDLE)v8);
      v8 = -1;
      SetLastError(0x6Eu);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800e9154  mov     [rsp+arg_18], rbx
0x1800e9159  push    rsi
0x1800e915a  push    r14
0x1800e915c  push    r15
0x1800e915e  sub     rsp, 80h
0x1800e9165  mov     rax, cs:__security_cookie
0x1800e916c  xor     rax, rsp
0x1800e916f  mov     [rsp+98h+var_20], rax
0x1800e9174  mov     byte ptr [rdx], 0
0x1800e9177  mov     r15, r8
0x1800e917a  mov     dword ptr [r8], 1
0x1800e9181  mov     r14, rdx
0x1800e9184  mov     rsi, rcx
0x1800e9187  test    rcx, rcx
0x1800e918a  jnz     short loc_1800E9195
0x1800e918c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e9190  jmp     loc_1800E9242
0x1800e9195  xor     r9d, r9d; lpSecurityAttributes
0x1800e9198  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1800e91a1  mov     [rsp+98h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800e91a9  mov     edx, 80000000h; dwDesiredAccess
0x1800e91ae  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e91b6  lea     r8d, [r9+1]; dwShareMode
0x1800e91ba  call    cs:__imp_CreateFileW
0x1800e91c0  mov     rbx, rax
0x1800e91c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e91c7  jz      short loc_1800E923F
0x1800e91c9  mov     rcx, rax; hFile
0x1800e91cc  call    cs:__imp_GetFileType
0x1800e91d2  add     eax, 0FFFFFFFEh
0x1800e91d5  cmp     eax, 1
0x1800e91d8  ja      loc_1800E9264
0x1800e91de  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800e91e5  jz      short loc_1800E9229
0x1800e91e7  lea     rax, aNull; "(NULL)"
0x1800e91ee  xor     edx, edx; unsigned __int16
0x1800e91f0  mov     [rsp+98h+var_40], rdx; void *
0x1800e91f5  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1800e91fc  mov     [rsp+98h+var_48], edx; unsigned int
0x1800e9200  xor     r8d, r8d; int
0x1800e9203  mov     [rsp+98h+var_50], rax; unsigned __int16 *
0x1800e9208  mov     [rsp+98h+var_58], rax; unsigned __int16 *
0x1800e920d  lea     ecx, [rdx+9]; int
0x1800e9210  mov     [rsp+98h+var_60], rax; unsigned __int16 *
0x1800e9215  mov     [rsp+98h+hTemplateFile], rax; unsigned __int16 *
0x1800e921a  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800e921f  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi; unsigned __int16 *
0x1800e9224  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800e9229  mov     rcx, rbx; hObject
0x1800e922c  call    cs:__imp_CloseHandle
0x1800e9232  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e9236  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800e9239  call    cs:__imp_SetLastError
0x1800e923f  mov     rax, rbx
0x1800e9242  mov     rcx, [rsp+98h+var_20]
0x1800e9247  xor     rcx, rsp; StackCookie
0x1800e924a  call    __security_check_cookie
0x1800e924f  mov     rbx, [rsp+98h+arg_18]
0x1800e9257  add     rsp, 80h
0x1800e925e  pop     r15
0x1800e9260  pop     r14
0x1800e9262  pop     rsi
0x1800e9263  retn
0x1800e9264  xor     eax, eax
0x1800e9266  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e926b  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x1800e9270  mov     [rsp+98h+Buffer], rax
0x1800e9275  mov     rcx, rbx; hFile
0x1800e9278  mov     [rsp+98h+var_28], eax
0x1800e927c  mov     [rsp+98h+NumberOfBytesRead], eax
0x1800e9280  lea     r8d, [rax+0Ch]; nNumberOfBytesToRead
0x1800e9284  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpOverlapped
0x1800e9289  call    cs:__imp_ReadFile
0x1800e928f  test    eax, eax
0x1800e9291  jz      short loc_1800E92D7
0x1800e9293  cmp     [rsp+98h+NumberOfBytesRead], 0Ch
0x1800e9298  jnz     short loc_1800E92D7
0x1800e929a  cmp     dword ptr [rsp+98h+Buffer], 66637474h
0x1800e92a2  jnz     short loc_1800E923F
0x1800e92a4  mov     ecx, [rsp+98h+var_28]
0x1800e92a8  mov     edx, ecx
0x1800e92aa  and     edx, 0FF0000h
0x1800e92b0  mov     byte ptr [r14], 1
0x1800e92b4  mov     eax, ecx
0x1800e92b6  shr     eax, 10h
0x1800e92b9  or      edx, eax
0x1800e92bb  mov     eax, ecx
0x1800e92bd  and     eax, 0FF00h
0x1800e92c2  shl     ecx, 10h
0x1800e92c5  or      eax, ecx
0x1800e92c7  shr     edx, 8
0x1800e92ca  shl     eax, 8
0x1800e92cd  or      edx, eax
0x1800e92cf  mov     [r15], edx
0x1800e92d2  jmp     loc_1800E923F
0x1800e92d7  mov     rcx, rbx; hObject
0x1800e92da  call    cs:__imp_CloseHandle
0x1800e92e0  jmp     loc_1800E918C
```
