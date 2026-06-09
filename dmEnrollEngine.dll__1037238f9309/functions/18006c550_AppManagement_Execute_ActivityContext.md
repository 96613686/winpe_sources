# AppManagement::Execute(ActivityContext *)

- ea: `0x18006c550`
- end: `0x18006c5be`
- name: `?Execute@AppManagement@@UEAAJPEAVActivityContext@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(AppManagement *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001aec8`
- `0x18006c550`
- `0x180073ff0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c5a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c5a6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006c569`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006c569`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMLegacy_UnActivateLOB` at `0x18006c579`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMLegacy_UnActivateLOB` at `0x18006c579`

## string_xrefs

- `0x18006c55f`: `sppc.dll`

## pseudocode

```c
__int64 __fastcall AppManagement::Execute(AppManagement *this, struct ActivityContext *a2)
{
  int v3; // ebx
  HMODULE LibraryW; // rdi
  CEnrollmentLogger *Logger; // rax
  struct _GUID v7; // [rsp+20h] [rbp-18h] BYREF

  v3 = 0;
  LibraryW = LoadLibraryW(L"sppc.dll");
  if ( LibraryW )
  {
    v3 = DMLegacy_UnActivateLOB();
    if ( v3 < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      v7 = *(struct _GUID *)((char *)a2 + 8);
      CEnrollmentLogger::LogUnenrollUnActivateLOBAppManagementFail(Logger, v3, &v7);
    }
    FreeLibrary(LibraryW);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006c550  mov     [rsp+arg_0], rbx
0x18006c555  mov     [rsp+arg_8], rsi
0x18006c55a  push    rdi
0x18006c55b  sub     rsp, 30h
0x18006c55f  lea     rcx, aSppcDll; "sppc.dll"
0x18006c566  mov     rsi, rdx
0x18006c569  call    cs:__imp_LoadLibraryW
0x18006c56f  xor     ebx, ebx
0x18006c571  mov     rdi, rax
0x18006c574  test    rax, rax
0x18006c577  jz      short loc_18006C5AC
0x18006c579  call    cs:__imp_DMLegacy_UnActivateLOB
0x18006c57f  mov     ebx, eax
0x18006c581  test    eax, eax
0x18006c583  jns     short loc_18006C5A3
0x18006c585  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006c58a  movups  xmm0, xmmword ptr [rsi+8]
0x18006c58e  lea     r8, [rsp+38h+var_18]; struct _GUID
0x18006c593  mov     edx, ebx; int
0x18006c595  mov     rcx, rax; this
0x18006c598  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18006c59e  call    ?LogUnenrollUnActivateLOBAppManagementFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollUnActivateLOBAppManagementFail(long,_GUID)
0x18006c5a3  mov     rcx, rdi; hLibModule
0x18006c5a6  call    cs:__imp_FreeLibrary
0x18006c5ac  mov     rsi, [rsp+38h+arg_8]
0x18006c5b1  mov     eax, ebx
0x18006c5b3  mov     rbx, [rsp+38h+arg_0]
0x18006c5b8  add     rsp, 30h
0x18006c5bc  pop     rdi
0x18006c5bd  retn
```
