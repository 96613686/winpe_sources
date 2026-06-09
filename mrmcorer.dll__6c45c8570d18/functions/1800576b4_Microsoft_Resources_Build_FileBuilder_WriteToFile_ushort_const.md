# Microsoft::Resources::Build::FileBuilder::WriteToFile(ushort const *)

- ea: `0x1800576b4`
- end: `0x1800578a7`
- name: `?WriteToFile@FileBuilder@Build@Resources@Microsoft@@QEAAJPEBG@Z`
- size: `499`
- prototype: `int(Microsoft::Resources::Build::FileBuilder *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057324`
- `0x18009bc10`
- `0x1800aac98`

## callees

- `0x180019570`
- `0x18002c8d0`
- `0x1800576b4`
- `0x180057ca8`
- `0x180072238`
- `0x180083aa8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005789c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005789c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057784`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057784`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057751`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057751`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800577ea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c37be`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800577ea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c37be`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18005779e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18005779e`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::FileBuilder::WriteToFile(
        Microsoft::Resources::Build::FileBuilder *this,
        const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  HANDLE FileW; // rax
  const char *v8; // r9
  DWORD v9; // r8d
  const void *v10; // rdx
  const char *v11; // r9
  const char *v12; // r9
  unsigned int LastError; // ebx
  __int64 v14; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+30h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned __int8)DefString_IsEmpty(a2) )
  {
    LastError = -2147024809;
    v14 = 433;
    goto LABEL_17;
  }
  if ( !*((_QWORD *)this + 6) )
  {
    v4 = (*(__int64 (__fastcall **)(Microsoft::Resources::Build::FileBuilder *))(*(_QWORD *)this + 64LL))(this);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
        (const char *)(unsigned int)v4,
        dwCreationDisposition);
      return v5;
    }
    if ( !*((_QWORD *)this + 6) )
      goto LABEL_16;
  }
  if ( !*((_DWORD *)this + 14) )
  {
LABEL_16:
    LastError = -554696303;
    v14 = 442;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
      (const char *)LastError,
      dwCreationDisposition);
    return LastError;
  }
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0, 0);
  hFile = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1BF,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
                  v8);
LABEL_24:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hFile);
    return LastError;
  }
  v9 = *((_DWORD *)this + 14);
  v10 = (const void *)*((_QWORD *)this + 6);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(FileW, v10, v9, &NumberOfBytesWritten, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C8,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
                  v11);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      0);
    DeleteFileW(a2);
    if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hFile);
    return LastError;
  }
  if ( NumberOfBytesWritten != *((_DWORD *)this + 14) )
  {
    LastError = -554696426;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
      (const char *)0xDEF00116LL,
      dwCreationDispositiona);
LABEL_23:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      0);
    DeleteFileW(a2);
    goto LABEL_24;
  }
  if ( !FlushFileBuffers(hFile) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1CA,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\filebuilder.cpp",
                  v12);
    goto LABEL_23;
  }
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hFile);
  return 0;
}

```

## disassembly

```asm
0x1800576b4  mov     [rsp-18h+arg_0], rbx
0x1800576b9  push    rbp
0x1800576ba  push    rsi
0x1800576bb  push    rdi
0x1800576bc  mov     rbp, rsp
0x1800576bf  sub     rsp, 40h
0x1800576c3  mov     rbx, rcx
0x1800576c6  mov     rdi, rdx
0x1800576c9  mov     rcx, rdx
0x1800576cc  call    DefString_IsEmpty
0x1800576d1  test    al, al
0x1800576d3  jnz     loc_180057835
0x1800576d9  cmp     qword ptr [rbx+30h], 0
0x1800576de  jnz     short loc_180057720
0x1800576e0  mov     rax, [rbx]
0x1800576e3  mov     rcx, rbx
0x1800576e6  mov     rax, [rax+40h]
0x1800576ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576ef  mov     esi, eax
0x1800576f1  test    eax, eax
0x1800576f3  jns     loc_180057806
0x1800576f9  mov     rcx, [rbp+18h]; this
0x1800576fd  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x180057704  mov     r9d, eax; char *
0x180057707  mov     edx, 1B7h; void *
0x18005770c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057711  mov     eax, esi
0x180057713  mov     rbx, [rsp+40h+arg_0]
0x180057718  add     rsp, 40h
0x18005771c  pop     rdi
0x18005771d  pop     rsi
0x18005771e  pop     rbp
0x18005771f  retn
0x180057720  cmp     dword ptr [rbx+38h], 0
0x180057724  jz      loc_180057811
0x18005772a  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180057733  xor     r9d, r9d; lpSecurityAttributes
0x180057736  mov     [rsp+40h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18005773e  xor     r8d, r8d; dwShareMode
0x180057741  mov     edx, 40000000h; dwDesiredAccess
0x180057746  mov     [rsp+40h+dwCreationDisposition], 2; dwCreationDisposition
0x18005774e  mov     rcx, rdi; lpFileName
0x180057751  call    cs:__imp_CreateFileW
0x180057757  mov     [rbp+hFile], rax
0x18005775b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005775f  jz      loc_180057841
0x180057765  mov     r8d, [rbx+38h]; nNumberOfBytesToWrite
0x180057769  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005776d  mov     rdx, [rbx+30h]; lpBuffer
0x180057771  mov     rcx, rax; hFile
0x180057774  mov     [rbp+NumberOfBytesWritten], 0
0x18005777b  mov     qword ptr [rsp+40h+dwCreationDisposition], 0; int
0x180057784  call    cs:__imp_WriteFile
0x18005778a  test    eax, eax
0x18005778c  jz      short loc_1800577C5
0x18005778e  mov     eax, [rbx+38h]
0x180057791  cmp     [rbp+NumberOfBytesWritten], eax
0x180057794  jnz     loc_18005785D
0x18005779a  mov     rcx, [rbp+hFile]; hFile
0x18005779e  call    cs:__imp_FlushFileBuffers
0x1800577a4  test    eax, eax
0x1800577a6  jz      loc_180057880
0x1800577ac  mov     rcx, [rbp+hFile]; hObject
0x1800577b0  lea     rax, [rcx-1]
0x1800577b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800577b8  jbe     loc_18005789C
0x1800577be  xor     eax, eax
0x1800577c0  jmp     loc_180057713
0x1800577c5  mov     rcx, [rbp+18h]; this
0x1800577c9  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x1800577d0  mov     edx, 1C8h; void *
0x1800577d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800577da  xor     edx, edx
0x1800577dc  lea     rcx, [rbp+hFile]
0x1800577e0  mov     ebx, eax
0x1800577e2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800577e7  mov     rcx, rdi; lpFileName
0x1800577ea  call    cs:__imp_DeleteFileW
0x1800577f0  mov     rcx, [rbp+hFile]; hObject
0x1800577f4  lea     rdx, [rcx-1]
0x1800577f8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800577fc  ja      short loc_18005782E
0x1800577fe  call    cs:__imp_CloseHandle
0x180057804  jmp     short loc_18005782E
0x180057806  cmp     qword ptr [rbx+30h], 0
0x18005780b  jnz     loc_180057720
0x180057811  mov     ebx, 0DEF00191h
0x180057816  mov     edx, 1BAh; void *
0x18005781b  mov     rcx, [rbp+18h]; this
0x18005781f  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x180057826  mov     r9d, ebx; char *
0x180057829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005782e  mov     eax, ebx
0x180057830  jmp     loc_180057713
0x180057835  mov     ebx, 80070057h
0x18005783a  mov     edx, 1B1h
0x18005783f  jmp     short loc_18005781B
0x180057841  mov     rcx, [rbp+18h]; this
0x180057845  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x18005784c  mov     edx, 1BFh; void *
0x180057851  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180057856  mov     ebx, eax
0x180057858  jmp     loc_1800C37C4
0x18005785d  mov     rcx, [rbp+18h]; this
0x180057861  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x180057868  mov     ebx, 0DEF00116h
0x18005786d  mov     edx, 1C9h; void *
0x180057872  mov     r9d, ebx; char *
0x180057875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005787a  nop
0x18005787b  jmp     loc_1800C37B0
0x180057880  mov     rcx, [rbp+18h]; this
0x180057884  lea     r8, aMinkernelMrtMr_26; "minkernel\\mrt\\mrm\\mrmex\\filebuilder"...
0x18005788b  mov     edx, 1CAh; void *
0x180057890  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180057895  mov     ebx, eax
0x180057897  jmp     loc_1800C37B0
0x18005789c  call    cs:__imp_CloseHandle
0x1800578a2  jmp     loc_1800577BE
0x1800c37b0  xor     edx, edx
0x1800c37b2  lea     rcx, [rbp+hFile]
0x1800c37b6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c37bb  mov     rcx, rdi; lpFileName
0x1800c37be  call    cs:__imp_DeleteFileW
0x1800c37c4  lea     rcx, [rbp+hFile]
0x1800c37c8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?_DefCloseHandle@@YAX0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>(void)
0x1800c37cd  nop
0x1800c37ce  jmp     loc_18005782E
```
