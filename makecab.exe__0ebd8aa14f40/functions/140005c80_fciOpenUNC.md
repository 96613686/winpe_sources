# fciOpenUNC

- ea: `0x140005c80`
- end: `0x140005f8c`
- name: `fciOpenUNC`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140005b10`

## callees

- `0x140005c80`
- `0x140008a78`
- `0x14000e412`
- `0x14000e450`
- `0x14000e4e0`

## import_xrefs

- `msvcrt!_open_osfhandle` at `0x140005ef9`
- `msvcrt!_open_osfhandle` at `0x140005ef9`
- `msvcrt!ctime` at `0x140005e59`
- `msvcrt!ctime` at `0x140005f63`
- `msvcrt!ctime` at `0x140005e59`
- `msvcrt!ctime` at `0x140005f63`
- `msvcrt!time` at `0x140005d85`
- `msvcrt!time` at `0x140005ecb`
- `msvcrt!time` at `0x140005d85`
- `msvcrt!time` at `0x140005ecb`
- `msvcrt!_errno` at `0x140005f06`
- `msvcrt!_errno` at `0x140005f06`
- `msvcrt!printf` at `0x140005e6f`
- `msvcrt!printf` at `0x140005f21`
- `msvcrt!printf` at `0x140005f79`
- `msvcrt!printf` at `0x140005e6f`
- `msvcrt!printf` at `0x140005f21`
- `msvcrt!printf` at `0x140005f79`
- `KERNEL32!CloseHandle` at `0x140005f2a`
- `KERNEL32!CloseHandle` at `0x140005f2a`
- `KERNEL32!CreateFileA` at `0x140005d67`
- `KERNEL32!CreateFileA` at `0x140005d67`
- `KERNEL32!GetLastError` at `0x140005d70`
- `KERNEL32!GetLastError` at `0x140005e2e`
- `KERNEL32!GetLastError` at `0x140005ec0`
- `KERNEL32!GetLastError` at `0x140005d70`
- `KERNEL32!GetLastError` at `0x140005e2e`
- `KERNEL32!GetLastError` at `0x140005ec0`
- `KERNEL32!Sleep` at `0x140005e7b`
- `KERNEL32!Sleep` at `0x140005e7b`
- `KERNEL32!CreateFileW` at `0x140005e25`
- `KERNEL32!CreateFileW` at `0x140005eb7`
- `KERNEL32!CreateFileW` at `0x140005e25`
- `KERNEL32!CreateFileW` at `0x140005eb7`

## string_xrefs

- `0x140005e62`: `[%.19s] File open error (Win32Error=0x%X), retrying %s\n`
- `0x140005f0f`: `_open_osfhandle(%s) failed errno=%d\n`
- `0x140005f6c`: `[%.19s] File open error (Win32Error=0x%X), %s\n`

## pseudocode

```c
__int64 __fastcall fciOpenUNC(const CHAR *a1, int a2, __int64 a3, _DWORD *a4)
{
  int v4; // ebx
  DWORD v6; // r13d
  DWORD v7; // r14d
  int v8; // edx
  DWORD dwCreationDisposition; // edi
  int v10; // ecx
  DWORD dwFlagsAndAttributes; // r12d
  HANDLE FileA; // rsi
  DWORD LastError; // r15d
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  time_t v16; // rax
  time_t v17; // rbx
  char *v18; // rax
  int v19; // ecx
  int v20; // ebx
  int *v21; // rax
  int v22; // r8d
  char *v24; // rax
  DWORD dwMilliseconds; // [rsp+40h] [rbp-22A8h]
  time_t Time; // [rsp+48h] [rbp-22A0h] BYREF
  int v27; // [rsp+50h] [rbp-2298h]
  _DWORD *v28; // [rsp+58h] [rbp-2290h]
  time_t v29; // [rsp+60h] [rbp-2288h]
  _BYTE v30[560]; // [rsp+70h] [rbp-2278h] BYREF
  WCHAR FileName[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  v28 = a4;
  v4 = a2;
  v27 = a2;
  v6 = 4;
  if ( (a2 & 2) != 0 )
  {
    v7 = -1073741824;
  }
  else if ( (a2 & 1) != 0 )
  {
    v7 = 0x40000000;
  }
  else
  {
    v7 = 0x80000000;
    v6 = 5;
  }
  if ( (a2 & 0x10) != 0 )
  {
    v8 = 268435584;
  }
  else
  {
    v8 = 128;
    if ( (v4 & 0x20) != 0 )
      v8 = 134217856;
  }
  if ( (v4 & 0x100) != 0 )
    dwCreationDisposition = 2 - ((v4 & 0x400) != 0);
  else
    dwCreationDisposition = (v4 & 0x200) != 0 ? 5 : 3;
  v10 = v8 | 0x4000000;
  if ( (v4 & 0x40) == 0 )
    v10 = v8;
  dwFlagsAndAttributes = v10 | 0x100;
  if ( (v4 & 0x1000) == 0 )
    dwFlagsAndAttributes = v10;
  FileA = CreateFileA(a1, v7, v6, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  LastError = GetLastError();
  if ( FileA != (HANDLE)-1LL )
    goto LABEL_29;
  Time = time(0);
  memset_0(FileName, 0, sizeof(FileName));
  memset_0(v30, 0, sizeof(v30));
  v15 = -1;
  do
    ++v15;
  while ( a1[v15] );
  if ( v15 >= 0x1000 || !(unsigned int)GetFullPathUNCW(a1, FileName, v14, v30) )
  {
    v24 = ctime(&Time);
    printf("[%.19s] File open error (Win32Error=0x%X), %s\n", v24, LastError, a1);
LABEL_33:
    v20 = -1;
    *v28 = LastError;
    return v20;
  }
  v29 = Time + 70;
  dwMilliseconds = 25;
  FileA = CreateFileW(FileName, v7, v6, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  LastError = GetLastError();
  if ( FileA == (HANDLE)-1LL )
  {
    v16 = Time;
    v17 = v29;
    do
    {
      if ( v16 >= v17 )
        break;
      v18 = ctime(&Time);
      printf("[%.19s] File open error (Win32Error=0x%X), retrying %s\n", v18, LastError, a1);
      Sleep(dwMilliseconds);
      v19 = 5000;
      if ( 2 * dwMilliseconds < 0x1388 )
        v19 = 2 * dwMilliseconds;
      dwMilliseconds = v19;
      FileA = CreateFileW(FileName, v7, v6, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
      LastError = GetLastError();
      v16 = time(0);
      Time = v16;
    }
    while ( FileA == (HANDLE)-1LL );
    v4 = v27;
    if ( FileA == (HANDLE)-1LL )
      goto LABEL_33;
  }
LABEL_29:
  v20 = _open_osfhandle((intptr_t)FileA, v4 | 0x8080);
  if ( v20 == -1 )
  {
    v21 = _errno();
    v22 = *v21;
    *v28 = *v21;
    printf("_open_osfhandle(%s) failed errno=%d\n", a1, v22);
    CloseHandle(FileA);
  }
  return v20;
}

```

## disassembly

```asm
0x140005c80  mov     [rsp+arg_10], rbx
0x140005c85  push    rbp
0x140005c86  push    rsi
0x140005c87  push    rdi
0x140005c88  push    r12
0x140005c8a  push    r13
0x140005c8c  push    r14
0x140005c8e  push    r15
0x140005c90  mov     eax, 22B0h
0x140005c95  call    _alloca_probe
0x140005c9a  sub     rsp, rax
0x140005c9d  mov     rax, cs:__security_cookie
0x140005ca4  xor     rax, rsp
0x140005ca7  mov     [rsp+22E8h+var_48], rax
0x140005caf  mov     [rsp+22E8h+var_2290], r9
0x140005cb4  mov     ebx, edx
0x140005cb6  mov     [rsp+22E8h+var_2298], edx
0x140005cba  mov     rbp, rcx
0x140005cbd  mov     r13d, 4
0x140005cc3  test    dl, 2
0x140005cc6  jz      short loc_140005CD0
0x140005cc8  mov     r14d, 0C0000000h
0x140005cce  jmp     short loc_140005CE9
0x140005cd0  test    bl, 1
0x140005cd3  jz      short loc_140005CDD
0x140005cd5  mov     r14d, 40000000h
0x140005cdb  jmp     short loc_140005CE9
0x140005cdd  mov     r14d, 80000000h
0x140005ce3  mov     r13d, 5
0x140005ce9  test    bl, 10h
0x140005cec  jz      short loc_140005CF5
0x140005cee  mov     edx, 10000080h
0x140005cf3  jmp     short loc_140005D05
0x140005cf5  test    bl, 20h
0x140005cf8  mov     edx, 80h
0x140005cfd  mov     eax, 8000080h
0x140005d02  cmovnz  edx, eax
0x140005d05  mov     r8d, 100h
0x140005d0b  mov     eax, ebx
0x140005d0d  test    r8d, ebx
0x140005d10  jz      short loc_140005D20
0x140005d12  and     eax, 400h
0x140005d17  neg     eax
0x140005d19  sbb     edi, edi
0x140005d1b  add     edi, 2
0x140005d1e  jmp     short loc_140005D2F
0x140005d20  and     eax, 200h
0x140005d25  neg     eax
0x140005d27  sbb     edi, edi
0x140005d29  and     edi, 2
0x140005d2c  add     edi, 3
0x140005d2f  mov     ecx, edx
0x140005d31  mov     [rsp+22E8h+hTemplateFile], 0; hTemplateFile
0x140005d3a  bts     ecx, 1Ah
0x140005d3e  test    bl, 40h
0x140005d41  cmovz   ecx, edx
0x140005d44  mov     edx, r14d; dwDesiredAccess
0x140005d47  mov     r12d, ecx
0x140005d4a  or      r12d, r8d
0x140005d4d  mov     r8d, r13d; dwShareMode
0x140005d50  bt      ebx, 0Ch
0x140005d54  cmovnb  r12d, ecx
0x140005d58  xor     r9d, r9d; lpSecurityAttributes
0x140005d5b  mov     [rsp+22E8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140005d60  mov     rcx, rbp; lpFileName
0x140005d63  mov     [rsp+22E8h+dwCreationDisposition], edi; dwCreationDisposition
0x140005d67  call    cs:__imp_CreateFileA
0x140005d6d  mov     rsi, rax
0x140005d70  call    cs:__imp_GetLastError
0x140005d76  mov     r15d, eax
0x140005d79  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140005d7d  jnz     loc_140005EEE
0x140005d83  xor     ecx, ecx; Time
0x140005d85  call    cs:__imp_time
0x140005d8b  xor     edx, edx; Val
0x140005d8d  lea     rcx, [rsp+22E8h+FileName]; void *
0x140005d95  mov     r8d, 2000h; Size
0x140005d9b  mov     [rsp+22E8h+Time], rax
0x140005da0  mov     rsi, rax
0x140005da3  call    memset_0
0x140005da8  xor     edx, edx; Val
0x140005daa  lea     rcx, [rsp+22E8h+var_2278]; void *
0x140005daf  mov     r8d, 230h; Size
0x140005db5  call    memset_0
0x140005dba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140005dbe  inc     rcx
0x140005dc1  cmp     byte ptr [rcx+rbp], 0
0x140005dc5  jnz     short loc_140005DBE
0x140005dc7  cmp     rcx, 1000h
0x140005dce  jnb     loc_140005F5E
0x140005dd4  lea     r9, [rsp+22E8h+var_2278]
0x140005dd9  mov     rcx, rbp
0x140005ddc  lea     rdx, [rsp+22E8h+FileName]
0x140005de4  call    GetFullPathUNCW
0x140005de9  test    eax, eax
0x140005deb  jz      loc_140005F5E
0x140005df1  lea     rax, [rsi+46h]
0x140005df5  mov     [rsp+22E8h+hTemplateFile], 0; hTemplateFile
0x140005dfe  mov     [rsp+22E8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140005e03  lea     rcx, [rsp+22E8h+FileName]; lpFileName
0x140005e0b  xor     r9d, r9d; lpSecurityAttributes
0x140005e0e  mov     [rsp+22E8h+var_2288], rax
0x140005e13  mov     r8d, r13d; dwShareMode
0x140005e16  mov     [rsp+22E8h+dwCreationDisposition], edi; dwCreationDisposition
0x140005e1a  mov     edx, r14d; dwDesiredAccess
0x140005e1d  mov     [rsp+22E8h+dwMilliseconds], 19h
0x140005e25  call    cs:__imp_CreateFileW
0x140005e2b  mov     rsi, rax
0x140005e2e  call    cs:__imp_GetLastError
0x140005e34  mov     r15d, eax
0x140005e37  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140005e3b  jnz     loc_140005EEE
0x140005e41  mov     rax, [rsp+22E8h+Time]
0x140005e46  mov     rbx, [rsp+22E8h+var_2288]
0x140005e4b  cmp     rax, rbx
0x140005e4e  jge     loc_140005EE0
0x140005e54  lea     rcx, [rsp+22E8h+Time]; Time
0x140005e59  call    cs:__imp_ctime
0x140005e5f  mov     r9, rbp
0x140005e62  lea     rcx, a19sFileOpenErr; "[%.19s] File open error (Win32Error=0x%"...
0x140005e69  mov     rdx, rax
0x140005e6c  mov     r8d, r15d
0x140005e6f  call    cs:__imp_printf
0x140005e75  mov     esi, [rsp+22E8h+dwMilliseconds]
0x140005e79  mov     ecx, esi; dwMilliseconds
0x140005e7b  call    cs:__imp_Sleep
0x140005e81  mov     edx, 1388h
0x140005e86  mov     [rsp+22E8h+hTemplateFile], 0; hTemplateFile
0x140005e8f  mov     ecx, edx
0x140005e91  mov     [rsp+22E8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140005e96  lea     eax, [rsi+rsi]
0x140005e99  mov     [rsp+22E8h+dwCreationDisposition], edi; dwCreationDisposition
0x140005e9d  cmp     eax, edx
0x140005e9f  mov     r8d, r13d; dwShareMode
0x140005ea2  mov     edx, r14d; dwDesiredAccess
0x140005ea5  cmovb   ecx, eax
0x140005ea8  xor     r9d, r9d; lpSecurityAttributes
0x140005eab  mov     [rsp+22E8h+dwMilliseconds], ecx
0x140005eaf  lea     rcx, [rsp+22E8h+FileName]; lpFileName
0x140005eb7  call    cs:__imp_CreateFileW
0x140005ebd  mov     rsi, rax
0x140005ec0  call    cs:__imp_GetLastError
0x140005ec6  xor     ecx, ecx; Time
0x140005ec8  mov     r15d, eax
0x140005ecb  call    cs:__imp_time
0x140005ed1  mov     [rsp+22E8h+Time], rax
0x140005ed6  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140005eda  jz      loc_140005E4B
0x140005ee0  mov     ebx, [rsp+22E8h+var_2298]
0x140005ee4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140005ee8  jz      loc_140005F7F
0x140005eee  or      ebx, 8080h
0x140005ef4  mov     rcx, rsi; OSFileHandle
0x140005ef7  mov     edx, ebx; Flags
0x140005ef9  call    cs:__imp__open_osfhandle
0x140005eff  mov     ebx, eax
0x140005f01  cmp     eax, 0FFFFFFFFh
0x140005f04  jnz     short loc_140005F30
0x140005f06  call    cs:__imp__errno
0x140005f0c  mov     rdx, rbp
0x140005f0f  lea     rcx, aOpenOsfhandleS; "_open_osfhandle(%s) failed errno=%d\n"
0x140005f16  mov     r8d, [rax]
0x140005f19  mov     rax, [rsp+22E8h+var_2290]
0x140005f1e  mov     [rax], r8d
0x140005f21  call    cs:__imp_printf
0x140005f27  mov     rcx, rsi; hObject
0x140005f2a  call    cs:__imp_CloseHandle
0x140005f30  movsxd  rax, ebx
0x140005f33  mov     rcx, [rsp+22E8h+var_48]
0x140005f3b  xor     rcx, rsp; StackCookie
0x140005f3e  call    __security_check_cookie
0x140005f43  mov     rbx, [rsp+22E8h+arg_10]
0x140005f4b  add     rsp, 22B0h
0x140005f52  pop     r15
0x140005f54  pop     r14
0x140005f56  pop     r13
0x140005f58  pop     r12
0x140005f5a  pop     rdi
0x140005f5b  pop     rsi
0x140005f5c  pop     rbp
0x140005f5d  retn
0x140005f5e  lea     rcx, [rsp+22E8h+Time]; Time
0x140005f63  call    cs:__imp_ctime
0x140005f69  mov     r9, rbp
0x140005f6c  lea     rcx, a19sFileOpenErr_0; "[%.19s] File open error (Win32Error=0x%"...
0x140005f73  mov     rdx, rax
0x140005f76  mov     r8d, r15d
0x140005f79  call    cs:__imp_printf
0x140005f7f  mov     rax, [rsp+22E8h+var_2290]
0x140005f84  or      ebx, 0FFFFFFFFh
0x140005f87  mov     [rax], r15d
0x140005f8a  jmp     short loc_140005F30
```
