# OpenFontFile(ushort const *,bool &,uint &)

- ea: `0x1800f1948`
- end: `0x1800f1b02`
- name: `?OpenFontFile@@YAPEAXPEBGAEA_NAEAI@Z`
- size: `442`
- prototype: `void *__fastcall(const unsigned __int16 *, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800f1458`
- `0x18014abd8`

## callees

- `0x18000c4bc`
- `0x1800f1948`
- `0x180265240`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800f1a30`
- `KERNEL32!CloseHandle` at `0x1800f1af1`
- `KERNEL32!CloseHandle` at `0x1800f1a30`
- `KERNEL32!CloseHandle` at `0x1800f1af1`
- `KERNEL32!SetLastError` at `0x1800f1a43`
- `KERNEL32!SetLastError` at `0x1800f1a43`
- `KERNEL32!CreateFileW` at `0x1800f19ae`
- `KERNEL32!CreateFileW` at `0x1800f19ae`
- `KERNEL32!GetFileType` at `0x1800f19ca`
- `KERNEL32!GetFileType` at `0x1800f19ca`
- `KERNEL32!ReadFile` at `0x1800f1a9a`
- `KERNEL32!ReadFile` at `0x1800f1a9a`

## string_xrefs

- `0x1800f19f9`: `Error: This is not a valid file, hence failing to create: %s`

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
0x1800f1948  mov     [rsp+arg_18], rbx
0x1800f194d  push    rsi
0x1800f194e  push    r14
0x1800f1950  push    r15
0x1800f1952  sub     rsp, 80h
0x1800f1959  mov     rax, cs:__security_cookie
0x1800f1960  xor     rax, rsp
0x1800f1963  mov     [rsp+98h+var_20], rax
0x1800f1968  mov     byte ptr [rdx], 0
0x1800f196b  mov     r15, r8
0x1800f196e  mov     dword ptr [r8], 1
0x1800f1975  mov     r14, rdx
0x1800f1978  mov     rsi, rcx
0x1800f197b  test    rcx, rcx
0x1800f197e  jnz     short loc_1800F1989
0x1800f1980  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f1984  jmp     loc_1800F1A52
0x1800f1989  xor     r9d, r9d; lpSecurityAttributes
0x1800f198c  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x1800f1995  mov     [rsp+98h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800f199d  mov     edx, 80000000h; dwDesiredAccess
0x1800f19a2  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x1800f19aa  lea     r8d, [r9+1]; dwShareMode
0x1800f19ae  call    cs:__imp_CreateFileW
0x1800f19b5  nop     dword ptr [rax+rax+00h]
0x1800f19ba  mov     rbx, rax
0x1800f19bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f19c1  jz      loc_1800F1A4F
0x1800f19c7  mov     rcx, rax; hFile
0x1800f19ca  call    cs:__imp_GetFileType
0x1800f19d1  nop     dword ptr [rax+rax+00h]
0x1800f19d6  add     eax, 0FFFFFFFEh
0x1800f19d9  cmp     eax, 1
0x1800f19dc  ja      loc_1800F1A75
0x1800f19e2  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800f19e9  jz      short loc_1800F1A2D
0x1800f19eb  lea     rax, aNull; "(NULL)"
0x1800f19f2  xor     edx, edx; unsigned __int16
0x1800f19f4  mov     [rsp+98h+var_40], rdx; void *
0x1800f19f9  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1800f1a00  mov     [rsp+98h+var_48], edx; unsigned int
0x1800f1a04  xor     r8d, r8d; int
0x1800f1a07  mov     [rsp+98h+var_50], rax; unsigned __int16 *
0x1800f1a0c  mov     [rsp+98h+var_58], rax; unsigned __int16 *
0x1800f1a11  lea     ecx, [rdx+9]; int
0x1800f1a14  mov     [rsp+98h+var_60], rax; unsigned __int16 *
0x1800f1a19  mov     [rsp+98h+hTemplateFile], rax; unsigned __int16 *
0x1800f1a1e  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800f1a23  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi; unsigned __int16 *
0x1800f1a28  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f1a2d  mov     rcx, rbx; hObject
0x1800f1a30  call    cs:__imp_CloseHandle
0x1800f1a37  nop     dword ptr [rax+rax+00h]
0x1800f1a3c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f1a40  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800f1a43  call    cs:__imp_SetLastError
0x1800f1a4a  nop     dword ptr [rax+rax+00h]
0x1800f1a4f  mov     rax, rbx
0x1800f1a52  mov     rcx, [rsp+98h+var_20]
0x1800f1a57  xor     rcx, rsp; StackCookie
0x1800f1a5a  call    __security_check_cookie
0x1800f1a5f  mov     rbx, [rsp+98h+arg_18]
0x1800f1a67  add     rsp, 80h
0x1800f1a6e  pop     r15
0x1800f1a70  pop     r14
0x1800f1a72  pop     rsi
0x1800f1a73  retn
0x1800f1a75  xor     eax, eax
0x1800f1a77  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f1a7c  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x1800f1a81  mov     [rsp+98h+Buffer], rax
0x1800f1a86  mov     rcx, rbx; hFile
0x1800f1a89  mov     [rsp+98h+var_28], eax
0x1800f1a8d  mov     [rsp+98h+NumberOfBytesRead], eax
0x1800f1a91  lea     r8d, [rax+0Ch]; nNumberOfBytesToRead
0x1800f1a95  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpOverlapped
0x1800f1a9a  call    cs:__imp_ReadFile
0x1800f1aa1  nop     dword ptr [rax+rax+00h]
0x1800f1aa6  test    eax, eax
0x1800f1aa8  jz      short loc_1800F1AEE
0x1800f1aaa  cmp     [rsp+98h+NumberOfBytesRead], 0Ch
0x1800f1aaf  jnz     short loc_1800F1AEE
0x1800f1ab1  cmp     dword ptr [rsp+98h+Buffer], 66637474h
0x1800f1ab9  jnz     short loc_1800F1A4F
0x1800f1abb  mov     ecx, [rsp+98h+var_28]
0x1800f1abf  mov     edx, ecx
0x1800f1ac1  and     edx, 0FF0000h
0x1800f1ac7  mov     byte ptr [r14], 1
0x1800f1acb  mov     eax, ecx
0x1800f1acd  shr     eax, 10h
0x1800f1ad0  or      edx, eax
0x1800f1ad2  mov     eax, ecx
0x1800f1ad4  and     eax, 0FF00h
0x1800f1ad9  shl     ecx, 10h
0x1800f1adc  or      eax, ecx
0x1800f1ade  shr     edx, 8
0x1800f1ae1  shl     eax, 8
0x1800f1ae4  or      edx, eax
0x1800f1ae6  mov     [r15], edx
0x1800f1ae9  jmp     loc_1800F1A4F
0x1800f1aee  mov     rcx, rbx; hObject
0x1800f1af1  call    cs:__imp_CloseHandle
0x1800f1af8  nop     dword ptr [rax+rax+00h]
0x1800f1afd  jmp     loc_1800F1980
```
