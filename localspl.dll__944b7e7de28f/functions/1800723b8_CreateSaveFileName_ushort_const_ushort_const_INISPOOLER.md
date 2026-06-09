# CreateSaveFileName(ushort const *,ushort const *,_INISPOOLER *)

- ea: `0x1800723b8`
- end: `0x180072555`
- name: `?CreateSaveFileName@@YAPEAGPEBG0PEAU_INISPOOLER@@@Z`
- size: `413`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006499c`

## callees

- `0x18000fb8c`
- `0x180011ed0`
- `0x180015e28`
- `0x18002fda0`
- `0x18002fdcc`
- `0x18003e984`
- `0x18003ea2c`
- `0x1800436b8`
- `0x1800436fc`
- `0x180054638`
- `0x1800723b8`
- `0x18007255c`
- `0x180072bd0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072489`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072489`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180072463`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180072463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800723e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007240e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800723e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007240e`
- `SPOOLSS!CheckLocalCall` at `0x1800723d1`
- `SPOOLSS!CheckLocalCall` at `0x1800723d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800724e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800724e4`

## string_xrefs

- `0x1800723ee`: `CreateSaveFileName`
- `0x18007241e`: `CreateSaveFileName`
- `0x180072517`: `CreateSaveFileName`
- `0x18007252f`: `CreateSaveFileName`
- `0x18007245c`: `shell32.dll`
- `0x180072510`: `Created file name %ws`
- `0x180072482`: `SHGetKnownFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall CreateSaveFileName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _INISPOOLER *a3)
{
  unsigned int v6; // eax
  int v7; // edx
  unsigned int v8; // ebx
  DWORD v10; // eax
  unsigned __int16 *v11; // rdi
  int LastErrorAsFailHRNoBreak; // ebx
  HMODULE Library; // rax
  NCoreLibrary *v14; // rcx
  __int64 v15; // rdx
  FARPROC ProcAddress; // rbx
  int *v17; // r8
  HMODULE hModule; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v21[4]; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+50h] BYREF

  v6 = CheckLocalCall(a1, a2);
  v8 = v6;
  if ( v6 == 1 )
  {
    SetLastError(0x32u);
    LocalSpoolerTelemetry::WriteDbgTraceError("CreateSaveFileName", L"Cannot autogenerate file names for remote users");
    return 0;
  }
  if ( v6 )
  {
    v10 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v6, v7);
    SetLastError(v10);
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "CreateSaveFileName",
      L"Failed to determine whether the call is local or remote.  Error hr: 0x%x.",
      v8);
    return 0;
  }
  v19 = 0;
  v11 = 0;
  v20 = 0;
  LastErrorAsFailHRNoBreak = MapDocumentNameToFileName(a1, &v19);
  if ( LastErrorAsFailHRNoBreak < 0 )
    goto LABEL_15;
  hModule = 0;
  Library = LoadLibraryExW(L"shell32.dll", 0, 0x800u);
  NCoreLibrary::TAutoHandleHMODULE::operator=(&hModule, Library);
  v14 = (NCoreLibrary *)hModule;
  if ( hModule && (pv = 0, (ProcAddress = GetProcAddress(hModule, "SHGetKnownFolderPath")) != 0) )
  {
    NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)v21, v15, v17);
    LastErrorAsFailHRNoBreak = ((__int64 (__fastcall *)(const GUID *, __int64, _QWORD, LPVOID *))ProcAddress)(
                                 &FOLDERID_Documents,
                                 0x8000,
                                 0,
                                 &pv);
    if ( LastErrorAsFailHRNoBreak >= 0 )
    {
      LastErrorAsFailHRNoBreak = CreateUniqueFileName((const unsigned __int16 *)pv, v19, a2, a3, &v20);
      CoTaskMemFree(pv);
      v11 = v20;
    }
    NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(v21);
  }
  else
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v14);
  }
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&hModule);
  if ( LastErrorAsFailHRNoBreak < 0 )
LABEL_15:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateSaveFileName",
      L"Failed with error hr: 0x%x",
      (unsigned int)LastErrorAsFailHRNoBreak);
  else
    LocalSpoolerTelemetry::WriteDbgTraceInfo("CreateSaveFileName", L"Created file name %ws", v11);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
  return v11;
}

```

## disassembly

```asm
0x1800723b8  push    rbp
0x1800723ba  push    rbx
0x1800723bb  push    rsi
0x1800723bc  push    rdi
0x1800723bd  push    r14
0x1800723bf  push    r15
0x1800723c1  mov     rbp, rsp
0x1800723c4  sub     rsp, 68h
0x1800723c8  mov     r14, r8
0x1800723cb  mov     r15, rdx
0x1800723ce  mov     rsi, rcx
0x1800723d1  call    cs:__imp_CheckLocalCall
0x1800723d7  mov     ebx, eax
0x1800723d9  cmp     eax, 1
0x1800723dc  jnz     short loc_180072401
0x1800723de  lea     ecx, [rax+31h]; dwErrCode
0x1800723e1  call    cs:__imp_SetLastError
0x1800723e7  lea     rdx, aCannotAutogene; "Cannot autogenerate file names for remo"...
0x1800723ee  lea     rcx, aCreatesavefile; "CreateSaveFileName"
0x1800723f5  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800723fa  xor     eax, eax
0x1800723fc  jmp     loc_180072548
0x180072401  test    ebx, ebx
0x180072403  jz      short loc_18007242C
0x180072405  mov     ecx, ebx; this
0x180072407  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18007240c  mov     ecx, eax; dwErrCode
0x18007240e  call    cs:__imp_SetLastError
0x180072414  mov     r8d, ebx
0x180072417  lea     rdx, aFailedToDeterm; "Failed to determine whether the call is"...
0x18007241e  lea     rcx, aCreatesavefile; "CreateSaveFileName"
0x180072425  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007242a  jmp     short loc_1800723FA
0x18007242c  mov     [rbp+var_30], 0
0x180072434  xor     edi, edi
0x180072436  mov     [rbp+var_28], rdi
0x18007243a  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18007243e  mov     rcx, rsi; unsigned __int16 *
0x180072441  call    ?MapDocumentNameToFileName@@YAJPEBGPEAPEAG@Z; MapDocumentNameToFileName(ushort const *,ushort * *)
0x180072446  mov     ebx, eax
0x180072448  test    eax, eax
0x18007244a  js      loc_180072525
0x180072450  mov     [rbp+hModule], rdi
0x180072454  xor     edx, edx; hFile
0x180072456  mov     r8d, 800h; dwFlags
0x18007245c  lea     rcx, aShell32Dll; "shell32.dll"
0x180072463  call    cs:__imp_LoadLibraryExW
0x180072469  mov     rdx, rax
0x18007246c  lea     rcx, [rbp+hModule]
0x180072470  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x180072475  mov     rcx, [rbp+hModule]; this
0x180072479  test    rcx, rcx
0x18007247c  jz      short loc_1800724F9
0x18007247e  mov     [rbp+pv], rdi
0x180072482  lea     rdx, aShgetknownfold; "SHGetKnownFolderPath"
0x180072489  call    cs:__imp_GetProcAddress
0x18007248f  mov     rbx, rax
0x180072492  test    rax, rax
0x180072495  jz      short loc_1800724F9
0x180072497  lea     rcx, [rbp+var_20]; this
0x18007249b  call    ??0Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(void)
0x1800724a0  nop
0x1800724a1  lea     r9, [rbp+pv]
0x1800724a5  xor     r8d, r8d
0x1800724a8  mov     edx, 8000h
0x1800724ad  lea     rcx, FOLDERID_Documents
0x1800724b4  mov     rax, rbx
0x1800724b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724bc  mov     ebx, eax
0x1800724be  test    eax, eax
0x1800724c0  js      short loc_1800724EE
0x1800724c2  lea     rax, [rbp+var_28]
0x1800724c6  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x1800724cb  mov     r9, r14; struct _INISPOOLER *
0x1800724ce  mov     r8, r15; unsigned __int16 *
0x1800724d1  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800724d5  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800724d9  call    ?CreateUniqueFileName@@YAJPEBG00PEAU_INISPOOLER@@PEAPEAG@Z; CreateUniqueFileName(ushort const *,ushort const *,ushort const *,_INISPOOLER *,ushort * *)
0x1800724de  mov     ebx, eax
0x1800724e0  mov     rcx, [rbp+pv]; pv
0x1800724e4  call    cs:__imp_CoTaskMemFree
0x1800724ea  mov     rdi, [rbp+var_28]
0x1800724ee  lea     rcx, [rbp+var_20]; this
0x1800724f2  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x1800724f7  jmp     short loc_180072500
0x1800724f9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800724fe  mov     ebx, eax
0x180072500  lea     rcx, [rbp+hModule]
0x180072504  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x180072509  test    ebx, ebx
0x18007250b  js      short loc_180072525
0x18007250d  mov     r8, rdi
0x180072510  lea     rdx, aCreatedFileNam; "Created file name %ws"
0x180072517  lea     rcx, aCreatesavefile; "CreateSaveFileName"
0x18007251e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180072523  jmp     short loc_18007253C
0x180072525  mov     r8d, ebx
0x180072528  lea     rdx, aFailedWithErro_2; "Failed with error hr: 0x%x"
0x18007252f  lea     rcx, aCreatesavefile; "CreateSaveFileName"
0x180072536  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18007253b  nop
0x18007253c  lea     rcx, [rbp+var_30]
0x180072540  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x180072545  mov     rax, rdi
0x180072548  add     rsp, 68h
0x18007254c  pop     r15
0x18007254e  pop     r14
0x180072550  pop     rdi
0x180072551  pop     rsi
0x180072552  pop     rbx
0x180072553  pop     rbp
0x180072554  retn
```
