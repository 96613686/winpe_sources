# SvcWorker::GetCorSvcBindToUnregisteredWorker(void *,ICorSvcLogger *,ushort const *,ushort const *,ushort const *,ushort const *,void *,LogicalImage *)

- ea: `0x18002a784`
- end: `0x18002b986`
- name: `?GetCorSvcBindToUnregisteredWorker@SvcWorker@@KAPEAUICorSvcBindToWorker@@PEAXPEAUICorSvcLogger@@PEBG2220PEAVLogicalImage@@@Z`
- size: `4610`
- prototype: `struct ICorSvcBindToWorker *__fastcall(void *, struct ICorSvcLogger *, wchar_t *, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, void *, struct LogicalImage *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b988`

## callees

- `0x180001e8c`
- `0x180001f48`
- `0x180002320`
- `0x18000807c`
- `0x180013e2c`
- `0x18002a784`
- `0x18002f454`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030c50`
- `0x180030d84`
- `0x180032654`
- `0x180032948`
- `0x180032ef4`
- `0x180032f44`
- `0x18003303c`
- `0x180034fd4`
- `0x1800351c0`
- `0x1800351e8`
- `0x18003a040`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003e73c`
- `0x18003f280`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18002ae72`
- `ADVAPI32!FreeSid` at `0x18002b12c`
- `ADVAPI32!FreeSid` at `0x18002b1ba`
- `ADVAPI32!FreeSid` at `0x18002ae72`
- `ADVAPI32!FreeSid` at `0x18002b12c`
- `ADVAPI32!FreeSid` at `0x18002b1ba`
- `KERNEL32!TerminateProcess` at `0x18002b107`
- `KERNEL32!TerminateProcess` at `0x18002b107`
- `KERNEL32!LoadLibraryExW` at `0x18002adad`
- `KERNEL32!LoadLibraryExW` at `0x18002ae1d`
- `KERNEL32!LoadLibraryExW` at `0x18002adad`
- `KERNEL32!LoadLibraryExW` at `0x18002ae1d`
- `KERNEL32!GetExitCodeProcess` at `0x18002b508`
- `KERNEL32!GetExitCodeProcess` at `0x18002b508`
- `KERNEL32!GetCurrentProcessId` at `0x18002a9c4`
- `KERNEL32!GetCurrentProcessId` at `0x18002a9c4`
- `KERNEL32!ReadFile` at `0x18002b266`
- `KERNEL32!ReadFile` at `0x18002b2ab`
- `KERNEL32!ReadFile` at `0x18002b266`
- `KERNEL32!ReadFile` at `0x18002b2ab`
- `KERNEL32!GlobalAlloc` at `0x18002b284`
- `KERNEL32!GlobalAlloc` at `0x18002b284`
- `KERNEL32!CreatePipe` at `0x18002aaa5`
- `KERNEL32!CreatePipe` at `0x18002aaa5`
- `KERNEL32!OpenProcess` at `0x18002a9d4`
- `KERNEL32!OpenProcess` at `0x18002a9d4`
- `KERNEL32!GetModuleFileNameW` at `0x18002a847`
- `KERNEL32!GetModuleFileNameW` at `0x18002a847`
- `KERNEL32!GetModuleHandleW` at `0x18002a826`
- `KERNEL32!GetModuleHandleW` at `0x18002a826`
- `KERNEL32!WaitForMultipleObjects` at `0x18002b0eb`
- `KERNEL32!WaitForMultipleObjects` at `0x18002b0eb`
- `KERNEL32!IsDebuggerPresent` at `0x18002b0bb`
- `KERNEL32!IsDebuggerPresent` at `0x18002b0bb`
- `KERNEL32!CloseHandle` at `0x18002aa05`
- `KERNEL32!CloseHandle` at `0x18002aa1c`
- `KERNEL32!CloseHandle` at `0x18002aa32`
- `KERNEL32!CloseHandle` at `0x18002aa57`
- `KERNEL32!CloseHandle` at `0x18002aa81`
- `KERNEL32!CloseHandle` at `0x18002ab08`
- `KERNEL32!CloseHandle` at `0x18002b07f`
- `KERNEL32!CloseHandle` at `0x18002b09d`
- `KERNEL32!CloseHandle` at `0x18002b242`
- `KERNEL32!CloseHandle` at `0x18002b42e`
- `KERNEL32!CloseHandle` at `0x18002b440`
- `KERNEL32!CloseHandle` at `0x18002b457`
- `KERNEL32!CloseHandle` at `0x18002b46e`
- `KERNEL32!CloseHandle` at `0x18002b4ba`
- `KERNEL32!CloseHandle` at `0x18002aa05`
- `KERNEL32!CloseHandle` at `0x18002aa1c`
- `KERNEL32!CloseHandle` at `0x18002aa32`
- `KERNEL32!CloseHandle` at `0x18002aa57`
- `KERNEL32!CloseHandle` at `0x18002aa81`
- `KERNEL32!CloseHandle` at `0x18002ab08`
- `KERNEL32!CloseHandle` at `0x18002b07f`
- `KERNEL32!CloseHandle` at `0x18002b09d`
- `KERNEL32!CloseHandle` at `0x18002b242`
- `KERNEL32!CloseHandle` at `0x18002b42e`
- `KERNEL32!CloseHandle` at `0x18002b440`
- `KERNEL32!CloseHandle` at `0x18002b457`
- `KERNEL32!CloseHandle` at `0x18002b46e`
- `KERNEL32!CloseHandle` at `0x18002b4ba`
- `KERNEL32!CreateEventW` at `0x18002aaee`
- `KERNEL32!CreateEventW` at `0x18002aaee`
- `KERNEL32!GetLastError` at `0x18002aed6`
- `KERNEL32!GetLastError` at `0x18002b54b`
- `KERNEL32!GetLastError` at `0x18002b693`
- `KERNEL32!GetLastError` at `0x18002aed6`
- `KERNEL32!GetLastError` at `0x18002b54b`
- `KERNEL32!GetLastError` at `0x18002b693`
- `KERNEL32!GetProcAddress` at `0x18002adc0`
- `KERNEL32!GetProcAddress` at `0x18002add7`
- `KERNEL32!GetProcAddress` at `0x18002adf1`
- `KERNEL32!GetProcAddress` at `0x18002ae08`
- `KERNEL32!GetProcAddress` at `0x18002ae2d`
- `KERNEL32!GetProcAddress` at `0x18002adc0`
- `KERNEL32!GetProcAddress` at `0x18002add7`
- `KERNEL32!GetProcAddress` at `0x18002adf1`
- `KERNEL32!GetProcAddress` at `0x18002ae08`
- `KERNEL32!GetProcAddress` at `0x18002ae2d`
- `KERNEL32!HeapFree` at `0x18002b20f`
- `KERNEL32!HeapFree` at `0x18002b20f`
- `KERNEL32!GetProcessHeap` at `0x18002b1fa`
- `KERNEL32!GetProcessHeap` at `0x18002b1fa`
- `ucrtbase_clr0400!wcsncpy_s` at `0x18002ad70`
- `ucrtbase_clr0400!wcsncpy_s` at `0x18002ad70`
- `ole32!CreateStreamOnHGlobal` at `0x18002b2f5`
- `ole32!CreateStreamOnHGlobal` at `0x18002b2f5`
- `ole32!CoUnmarshalInterface` at `0x18002b345`
- `ole32!CoUnmarshalInterface` at `0x18002b345`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b5b3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b651`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b6fb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b79a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b84c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b91a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b5b3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b651`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b6fb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b79a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b84c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b91a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b88b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b959`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b88b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b959`

## string_xrefs

- `0x18002a81f`: `mscorsvc.dll`
- `0x18002ada6`: `kernel32.dll`
- `0x18002abde`: ` -Comment "NGen Worker Process"`
- `0x18002adb6`: `UpdateProcThreadAttribute`
- `0x18002adcd`: `InitializeProcThreadAttributeList`
- `0x18002ade7`: `DeleteProcThreadAttributeList`
- `0x18002b591`: `ERROR:  Reading data size from worker process failed with error %u\n`
- `0x18002b62f`: `ERROR:  Reading data size from worker process returned %u bytes instead of %u bytes\n`
- `0x18002b6d9`: `ERROR:  Reading data from worker process failed with error %u\n`
- `0x18002b778`: `ERROR:  Reading data from worker process returned %u bytes instead of %u bytes\n`
- `0x18002ae23`: `DeriveAppContainerSidFromAppContainerName`
- `0x18002ae16`: `userenv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=403
struct ICorSvcBindToWorker *__fastcall SvcWorker::GetCorSvcBindToUnregisteredWorker(
        void *a1,
        struct ICorSvcLogger *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        void *a7,
        struct LogicalImage *a8)
{
  unsigned __int16 *v8; // r12
  int v9; // edi
  unsigned int v10; // esi
  __int64 v11; // r14
  HMODULE ModuleHandleW; // rax
  DWORD ModuleFileNameW; // eax
  int v14; // r15d
  DWORD CurrentProcessId; // eax
  HANDLE v16; // r13
  int v17; // esi
  bool v18; // cl
  unsigned int v19; // esi
  int v20; // eax
  int v21; // eax
  HANDLE v22; // rbx
  char v23; // cl
  unsigned int v24; // ebx
  char v25; // dl
  unsigned int v26; // ebx
  unsigned int v27; // eax
  wchar_t *v28; // r14
  wchar_t *v29; // rbx
  char v30; // cl
  void *v31; // r13
  int v32; // r14d
  DWORD v33; // ebx
  void (__fastcall *v34)(_QWORD); // rax
  HMODULE Library; // rbx
  FARPROC v36; // r13
  FARPROC v37; // r12
  FARPROC v38; // rbx
  HMODULE v39; // rax
  unsigned int v40; // eax
  int v41; // esi
  int v42; // eax
  int v43; // eax
  char *v44; // rax
  char *v45; // r12
  void *v46; // r14
  struct _SECURITY_ATTRIBUTES *v47; // r8
  struct _SECURITY_ATTRIBUTES *v48; // r9
  int v49; // eax
  char *v50; // rax
  HANDLE v51; // rbx
  DWORD v52; // eax
  BOOL v53; // eax
  DWORD v54; // r14d
  wchar_t *v55; // r12
  HANDLE ProcessHeap; // rax
  HGLOBAL v57; // rax
  void *v58; // r14
  HRESULT StreamOnHGlobal; // eax
  int v60; // ecx
  HRESULT v61; // eax
  int v62; // ecx
  LPVOID v63; // r14
  int v64; // r14d
  int v65; // eax
  __int64 v66; // rsi
  __int64 LastError; // rbx
  const OLECHAR *Unicode; // rax
  BSTR v70; // r8
  const OLECHAR *v71; // rax
  BSTR v72; // r8
  __int64 v73; // rbx
  const OLECHAR *v74; // rax
  BSTR v75; // r8
  const OLECHAR *v76; // rax
  BSTR v77; // r8
  OLECHAR *v78; // rsi
  OLECHAR *v79; // rsi
  __int64 lpOverlapped; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+28h] [rbp-D8h]
  void *v82; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v83; // [rsp+38h] [rbp-C8h]
  struct _STARTUPINFOW *v84; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+64h] [rbp-9Ch] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  int v87; // [rsp+70h] [rbp-90h]
  DWORD ExitCode; // [rsp+78h] [rbp-88h] BYREF
  FARPROC Buffer; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hWritePipe; // [rsp+88h] [rbp-78h] BYREF
  int v91; // [rsp+90h] [rbp-70h]
  HANDLE hObject; // [rsp+98h] [rbp-68h] BYREF
  int v93; // [rsp+A0h] [rbp-60h]
  __int64 v94; // [rsp+A8h] [rbp-58h] BYREF
  int v95; // [rsp+B0h] [rbp-50h]
  HANDLE Handles; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE v97; // [rsp+C0h] [rbp-40h]
  struct ICorSvcLogger *v98; // [rsp+C8h] [rbp-38h]
  OLECHAR *v99; // [rsp+D0h] [rbp-30h]
  BOOL v100; // [rsp+D8h] [rbp-28h]
  LPVOID ppv; // [rsp+E0h] [rbp-20h] BYREF
  int v102; // [rsp+E8h] [rbp-18h]
  void (__fastcall *v103)(_QWORD); // [rsp+F0h] [rbp-10h]
  int v104; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v105; // [rsp+100h] [rbp+0h]
  BOOL v106; // [rsp+108h] [rbp+8h]
  PSID *p_pSid; // [rsp+110h] [rbp+10h]
  __int64 v108; // [rsp+118h] [rbp+18h]
  int v109; // [rsp+120h] [rbp+20h]
  HANDLE v110; // [rsp+128h] [rbp+28h]
  DWORD v111; // [rsp+130h] [rbp+30h]
  SIZE_T dwBytes; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *Src; // [rsp+140h] [rbp+40h]
  HANDLE v114; // [rsp+148h] [rbp+48h]
  HANDLE v115; // [rsp+150h] [rbp+50h]
  BOOL v116; // [rsp+158h] [rbp+58h]
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+160h] [rbp+60h] BYREF
  void *v118; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v119; // [rsp+180h] [rbp+80h]
  unsigned int (__fastcall *v120)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+188h] [rbp+88h]
  void *v121; // [rsp+190h] [rbp+90h]
  wchar_t *String1; // [rsp+198h] [rbp+98h]
  struct LogicalImage *v123; // [rsp+1A0h] [rbp+A0h]
  unsigned __int16 *v124; // [rsp+1A8h] [rbp+A8h]
  FARPROC ProcAddress; // [rsp+1B0h] [rbp+B0h]
  char *v126; // [rsp+1B8h] [rbp+B8h] BYREF
  void (__fastcall *v127)(_QWORD); // [rsp+1C0h] [rbp+C0h]
  struct _PROCESS_INFORMATION hProcess; // [rsp+1D0h] [rbp+D0h] BYREF
  HANDLE *p_hWritePipe; // [rsp+1E8h] [rbp+E8h]
  PSID v130; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v131; // [rsp+1F8h] [rbp+F8h]
  struct _STARTUPINFOW v132; // [rsp+210h] [rbp+110h] BYREF
  char *v133; // [rsp+278h] [rbp+178h]
  unsigned int v134; // [rsp+280h] [rbp+180h] BYREF
  int v135; // [rsp+288h] [rbp+188h]
  wchar_t *Source; // [rsp+290h] [rbp+190h]
  unsigned int v137; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v138; // [rsp+4A4h] [rbp+3A4h]
  wchar_t *Destination; // [rsp+4B0h] [rbp+3B0h]
  _WORD v140[260]; // [rsp+4B8h] [rbp+3B8h] BYREF
  unsigned int v141; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int64 v142; // [rsp+6C4h] [rbp+5C4h]
  void *lpMem; // [rsp+6D0h] [rbp+5D0h]
  __int16 v144; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v145[144]; // [rsp+8E0h] [rbp+7E0h] BYREF
  WCHAR Filename[264]; // [rsp+970h] [rbp+870h] BYREF

  v8 = a4;
  v105 = a4;
  String1 = a3;
  v98 = a2;
  v121 = a1;
  v119 = a5;
  v124 = a6;
  v118 = a7;
  v123 = a8;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v110 = (HANDLE)-1LL;
  ExitCode = 0;
  v111 = 0;
  v94 = 0;
  v95 = 0;
  ModuleHandleW = GetModuleHandleW(L"mscorsvc.dll");
  if ( !ModuleHandleW || (ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, Filename, 0x104u)) == 0 )
    ThrowLastError();
  if ( ModuleFileNameW == 260 )
    ThrowHR(-2147418113);
  v142 = 512;
  lpMem = &v144;
  v141 = 2;
  v144 = 0;
  SString::Set((SString *)&v141, Filename);
  if ( (~(HIDWORD(v142) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v141) )
    SString::ConvertToUnicode((SString *)&v141);
  if ( (v142 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v141, (unsigned int)v142, 1);
  if ( (v142 & 0x200000000LL) != 0
    && ((BYTE4(v142) & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)&v141) )
  {
    SString::ConvertToUnicode((SString *)&v141);
  }
  v126 = (char *)lpMem + (int)(((v141 >> ((v142 & 0x100000000LL) == 0)) - 1) << ((v142 & 0x100000000LL) == 0));
  LODWORD(v127) = (v142 & 0x100000000LL) == 0;
  SString::FindBack((SString *)&v141, (struct SString::CIterator *)&v126, L"\\");
  SString::Truncate((SString *)&v141, (const struct SString::Iterator *)&v126);
  SString::Append((SString *)&v141, L"\\mscorsvw.exe");
  hObject = (HANDLE)-1LL;
  v93 = 0;
  hWritePipe = (HANDLE)-1LL;
  v91 = 0;
  v108 = -1;
  v14 = 0;
  v109 = 0;
  *(_QWORD *)&PipeAttributes.nLength = 24;
  *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
  PipeAttributes.lpSecurityDescriptor = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = OpenProcess(0x100000u, 1, CurrentProcessId);
  v115 = v16;
  v106 = v16 != (HANDLE)-1LL;
  v116 = v106;
  NumberOfBytesRead = 0;
  while ( 1 )
  {
    if ( v93 )
    {
      if ( hObject )
        CloseHandle(hObject);
      v93 = 0;
    }
    if ( v91 )
    {
      if ( hWritePipe )
        CloseHandle(hWritePipe);
      v91 = 0;
    }
    if ( v14 )
    {
      if ( v11 )
        CloseHandle((HANDLE)v11);
      v14 = 0;
      v109 = 0;
    }
    p_hWritePipe = &hWritePipe;
    if ( v91 )
    {
      if ( hWritePipe )
        CloseHandle(hWritePipe);
      v91 = 0;
    }
    hWritePipe = (HANDLE)-1LL;
    v17 = v10 | 1;
    ppv = &hObject;
    if ( v93 )
    {
      if ( hObject )
        CloseHandle(hObject);
      v93 = 0;
    }
    hObject = (HANDLE)-1LL;
    v18 = !CreatePipe(&hObject, &hWritePipe, &PipeAttributes, 0);
    v19 = v17 & 0xFFFFFFFD;
    v20 = v93;
    if ( hObject != (HANDLE)-1LL )
      v20 = 1;
    v93 = v20;
    v10 = v19 & 0xFFFFFFFE;
    v21 = v91;
    if ( hWritePipe != (HANDLE)-1LL )
      v21 = 1;
    v91 = v21;
    if ( v18 )
      goto LABEL_177;
    v22 = CreateEventW(&PipeAttributes, 0, 0, 0);
    v114 = v22;
    v108 = (__int64)v22;
    if ( v22 != (HANDLE)-1LL )
      v14 = 1;
    v109 = v14;
    if ( !v22 )
LABEL_177:
      ThrowLastError();
    InlineSString<512>::InlineSString<512>(&v134, &v141);
    SString::AppendPrintf((SString *)&v134, L" -StartupEvent %x", v22);
    SString::AppendPrintf((SString *)&v134, L" -InterruptEvent %x", v118);
    SString::AppendPrintf((SString *)&v134, L" -NGENProcess %x", v16);
    SString::AppendPrintf((SString *)&v134, L" -Pipe %x", hWritePipe);
    if ( v119 )
      SString::AppendPrintf((SString *)&v134, L" -LocalAppData \"%s\"", v119);
    if ( v8 )
      SString::AppendPrintf((SString *)&v134, L" -Package \"%s\"", v8);
    SString::Append((SString *)&v134, L" -Comment \"NGen Worker Process\"");
    memset_0(&v132.cb + 1, 0, 0x6Cu);
    v132.cb = 104;
    v138 = 512;
    Destination = v140;
    v137 = 2;
    v140[0] = 0;
    v23 = v135;
    if ( (v135 & 2) != 0 && ((v135 & 7) != 7 || SString::s_IsANSIMultibyte) )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v134) )
        SString::ConvertToUnicode((SString *)&v134);
      v23 = v135;
    }
    v24 = v134 >> ((v23 & 1) == 0);
    SString::Resize(&v137, v24, 4);
    v25 = BYTE4(v138);
    v26 = (v24 + 1) << ((v138 & 0x100000000LL) == 0);
    v27 = v138;
    if ( v26 > (unsigned int)v138 )
    {
      SBuffer::ReallocateBuffer(&v137, v26, 1);
      v25 = BYTE4(v138);
      v27 = v138;
    }
    v137 = v26;
    if ( (v25 & 0x10) != 0 )
      SBuffer::ReallocateBuffer(&v137, v27, 1);
    v28 = Destination;
    Src = Destination;
    SString::ConvertToUnicode((SString *)&v134);
    v29 = Source;
    v30 = v135;
    if ( (v135 & 2) != 0 && ((v135 & 7) != 7 || SString::s_IsANSIMultibyte) )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v134) )
        SString::ConvertToUnicode((SString *)&v134);
      v30 = v135;
    }
    wcsncpy_s(v28, (unsigned __int64)v134 >> ((v30 & 1) == 0), v29, 0xFFFFFFFFFFFFFFFFuLL);
    v31 = 0;
    v99 = 0;
    v32 = 0;
    LODWORD(Buffer) = 0;
    v100 = 0;
    v33 = 0;
    v34 = 0;
    v103 = 0;
    pSid = 0;
    v87 = 0;
    if ( v8 )
    {
      Library = LoadLibraryExW(L"kernel32.dll", 0, 0);
      ProcAddress = GetProcAddress(Library, "UpdateProcThreadAttribute");
      v36 = GetProcAddress(Library, "InitializeProcThreadAttributeList");
      v120 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v36;
      v37 = GetProcAddress(Library, "DeleteProcThreadAttributeList");
      v103 = (void (__fastcall *)(_QWORD))v37;
      v38 = GetProcAddress(Library, "PackageFamilyNameFromFullName");
      v39 = LoadLibraryExW(L"userenv.dll", 0, 0);
      Buffer = GetProcAddress(v39, "DeriveAppContainerSidFromAppContainerName");
      v104 = 65;
      v40 = ((__int64 (__fastcall *)(unsigned __int16 *, int *, _BYTE *))v38)(v105, &v104, v145);
      if ( v40 )
        ThrowWin32(v40);
      p_pSid = &pSid;
      if ( v87 )
      {
        FreeSid(pSid);
        v87 = 0;
      }
      pSid = 0;
      v41 = v10 | 4;
      v42 = ((__int64 (__fastcall *)(_BYTE *, PSID *))Buffer)(v145, &pSid);
      if ( v42 < 0 )
        ThrowHR(v42);
      v10 = v41 & 0xFFFFFFFB;
      v43 = v87;
      if ( pSid )
        v43 = 1;
      v87 = v43;
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, SIZE_T *))v36)(0, 1, 0, &dwBytes);
      if ( GetLastError() != 122 )
        goto LABEL_180;
      v44 = (char *)operator new(dwBytes);
      v31 = v44;
      v99 = (OLECHAR *)v44;
      if ( v44 )
        v32 = 1;
      LODWORD(Buffer) = v32;
      v100 = v32;
      v133 = v44;
      if ( !v120(v44, 1, 0, &dwBytes) )
LABEL_180:
        ThrowLastError();
      v131 = 0;
      v130 = pSid;
      v82 = 0;
      v81 = 0;
      lpOverlapped = 24;
      if ( !((unsigned int (__fastcall *)(char *, _QWORD, __int64, PSID *))ProcAddress)(v133, 0, 131081, &v130) )
        ((void (__fastcall *)(char *))v37)(v133);
      v33 = 0x80000;
      v132.cb = 112;
      v34 = v103;
    }
    v45 = v133;
    v126 = v133;
    v127 = v34;
    if ( SvcWorker::UseProtectedProcess(String1, v105, v124, v123) )
      v33 |= 0x40000u;
    v46 = v121;
    SString::ConvertToUnicode((SString *)&v141);
    if ( v46 == (void *)-1LL )
      v49 = WszCreateProcess((LPCWSTR)lpMem, Src, v47, v48, lpOverlapped, v33, v82, v83, &v132, &hProcess);
    else
      v49 = CLRCreateProcessAsUser(
              v46,
              (const unsigned __int16 *)lpMem,
              Src,
              v48,
              (struct _SECURITY_ATTRIBUTES *)lpOverlapped,
              v81,
              v33,
              v83,
              (const unsigned __int16 *)v84,
              &v132,
              &hProcess);
    if ( !v49 )
      ThrowLastError();
    v50 = (char *)Destination + v137;
    if ( (v138 & 0x100000000LL) != 0 )
      *(v50 - 1) = 0;
    else
      *((_WORD *)v50 - 1) = 0;
    CloseHandle(hProcess.hThread);
    v51 = hProcess.hProcess;
    v52 = ExitCode;
    if ( ExitCode )
    {
      if ( v110 )
        CloseHandle(v110);
      v52 = 0;
      v111 = 0;
    }
    v110 = v51;
    if ( v51 != (HANDLE)-1LL )
      v52 = 1;
    ExitCode = v52;
    v111 = v52;
    v53 = IsDebuggerPresent();
    Handles = v114;
    v97 = v51;
    v54 = WaitForMultipleObjects(2u, &Handles, 0, v53 ? -1 : 30000);
    if ( v54 != 258 )
      break;
    TerminateProcess(v51, 1u);
    if ( v45 )
      v103(v45);
    if ( v87 )
    {
      FreeSid(pSid);
      v87 = 0;
    }
    if ( (_DWORD)Buffer )
    {
      operator delete(v31, 1u);
      v100 = 0;
    }
    if ( (v138 & 0x800000000LL) != 0 )
      operator delete(Destination);
    if ( (v135 & 8) != 0 )
      operator delete(Source);
    if ( (int)++NumberOfBytesRead >= 3 )
      goto LABEL_201;
    v11 = v108;
    v8 = v105;
    v16 = v115;
  }
  if ( v45 )
    v103(v45);
  if ( v87 )
  {
    FreeSid(pSid);
    v87 = 0;
  }
  if ( (_DWORD)Buffer )
  {
    operator delete(v31, 1u);
    v100 = 0;
  }
  if ( (v138 & 0x800000000LL) != 0 )
  {
    v55 = Destination;
    if ( Destination )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v55);
    }
  }
  if ( (v135 & 8) != 0 )
    operator delete(Source);
  if ( v54 )
  {
    if ( v54 == 1 )
    {
      ExitCode = 305419896;
      if ( !GetExitCodeProcess(v51, &ExitCode) )
        ThrowLastError();
      v138 = 512;
      Destination = v140;
      v137 = 2;
      v140[0] = 0;
      SString::Printf(
        (SString *)&v137,
        L"ERROR:  GetCorSvcBindToUnregisteredWorker failed because the worker process died with errorcode %i\n",
        ExitCode);
      SString::ConvertToUnicode((SString *)&v137);
      v78 = SysAllocString(Destination);
      v99 = v78;
      v100 = v78 != 0;
      (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, OLECHAR *))(*(_QWORD *)v98 + 24LL))(v98, 0, v78);
      v64 = -2146230524;
      if ( v78 )
      {
        SysFreeString(v78);
        v100 = 0;
      }
    }
    else
    {
LABEL_201:
      v138 = 512;
      Destination = v140;
      v137 = 2;
      v140[0] = 0;
      if ( v54 == 258 )
        SString::Set((SString *)&v137, L"ERROR:  Failed to synchronize with worker process because of timeout\n");
      else
        SString::Printf(
          (SString *)&v137,
          L"ERROR:  Failed to synchronize with worker process because WaitForMultipleObjects returned error %u\n",
          v54);
      SString::ConvertToUnicode((SString *)&v137);
      v79 = SysAllocString(Destination);
      v99 = v79;
      v100 = v79 != 0;
      (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, OLECHAR *))(*(_QWORD *)v98 + 24LL))(v98, 0, v79);
      v64 = -2146230523;
      if ( v79 )
      {
        SysFreeString(v79);
        v100 = 0;
      }
    }
    if ( (v138 & 0x800000000LL) != 0 )
      operator delete(Destination);
LABEL_208:
    ThrowHR(v64);
  }
  if ( v91 )
  {
    if ( hWritePipe )
      CloseHandle(hWritePipe);
    v91 = 0;
  }
  if ( !ReadFile(hObject, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v138 = 512;
    Destination = v140;
    v137 = 2;
    v140[0] = 0;
    SString::Printf(
      (SString *)&v137,
      L"ERROR:  Reading data size from worker process failed with error %u\n",
      LastError);
    Unicode = SString::GetUnicode((SString *)&v137);
    v70 = SysAllocString(Unicode);
    Handles = v70;
    LODWORD(v97) = 0;
    if ( v70 )
      v9 = 1;
    LODWORD(v97) = v9;
    (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, BSTR))(*(_QWORD *)v98 + 24LL))(v98, 0, v70);
    ThrowWin32(LastError);
  }
  if ( NumberOfBytesRead != 4 )
  {
    v138 = 512;
    Destination = v140;
    v137 = 2;
    v140[0] = 0;
    SString::Printf(
      (SString *)&v137,
      L"ERROR:  Reading data size from worker process returned %u bytes instead of %u bytes\n",
      NumberOfBytesRead,
      4);
    v71 = SString::GetUnicode((SString *)&v137);
    v72 = SysAllocString(v71);
    Handles = v72;
    LODWORD(v97) = 0;
    if ( v72 )
      v9 = 1;
    LODWORD(v97) = v9;
    (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, BSTR))(*(_QWORD *)v98 + 24LL))(v98, 0, v72);
    ThrowHR(-2147467259);
  }
  v57 = GlobalAlloc(0, (unsigned int)Buffer);
  v58 = v57;
  if ( !v57 )
    ThrowLastError();
  if ( !ReadFile(hObject, v57, (DWORD)Buffer, &NumberOfBytesRead, 0) )
  {
    v73 = GetLastError();
    v138 = 512;
    Destination = v140;
    v137 = 2;
    v140[0] = 0;
    SString::Printf((SString *)&v137, L"ERROR:  Reading data from worker process failed with error %u\n", v73);
    v74 = SString::GetUnicode((SString *)&v137);
    v75 = SysAllocString(v74);
    Handles = v75;
    LODWORD(v97) = 0;
    if ( v75 )
      v9 = 1;
    LODWORD(v97) = v9;
    (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, BSTR))(*(_QWORD *)v98 + 24LL))(v98, 0, v75);
    ThrowWin32(v73);
  }
  if ( NumberOfBytesRead != (_DWORD)Buffer )
  {
    v138 = 512;
    Destination = v140;
    v137 = 2;
    v140[0] = 0;
    SString::Printf(
      (SString *)&v137,
      L"ERROR:  Reading data from worker process returned %u bytes instead of %u bytes\n",
      NumberOfBytesRead,
      (unsigned int)Buffer);
    v76 = SString::GetUnicode((SString *)&v137);
    v77 = SysAllocString(v76);
    Handles = v77;
    LODWORD(v97) = 0;
    if ( v77 )
      v9 = 1;
    LODWORD(v97) = v9;
    (*(void (__fastcall **)(struct ICorSvcLogger *, _QWORD, BSTR))(*(_QWORD *)v98 + 24LL))(v98, 0, v77);
    ThrowHR(-2147467259);
  }
  v87 = 0;
  p_pSid = &pSid;
  pSid = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(v58, 1, (LPSTREAM *)&pSid);
  v60 = v87;
  if ( pSid )
    v60 = 1;
  v87 = v60;
  if ( StreamOnHGlobal < 0 )
    ThrowHR(StreamOnHGlobal);
  v102 = 0;
  p_pSid = &ppv;
  ppv = 0;
  v61 = CoUnmarshalInterface((LPSTREAM)pSid, &IID_IClassFactory, &ppv);
  v62 = v102;
  v63 = ppv;
  if ( ppv )
    v62 = 1;
  v102 = v62;
  if ( v61 < 0 )
    ThrowHR(v61);
  p_pSid = (PSID *)&v94;
  if ( v95 )
  {
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    v95 = 0;
  }
  v94 = 0;
  v64 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v63 + 24LL))(
          v63,
          0,
          &IID_ICorSvcBindToWorker,
          &v94);
  v65 = v95;
  if ( v94 )
    v65 = 1;
  v95 = v65;
  if ( v102 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v102 = 0;
  }
  if ( v87 )
  {
    if ( pSid )
      (*(void (__fastcall **)(PSID))(*(_QWORD *)pSid + 16LL))(pSid);
    v87 = 0;
  }
  if ( v64 < 0 )
    goto LABEL_208;
  v95 = 0;
  v66 = v94;
  if ( v106 )
  {
    if ( v115 )
      CloseHandle(v115);
    v116 = 0;
  }
  if ( v14 )
  {
    CloseHandle(v114);
    v109 = 0;
  }
  if ( v91 )
  {
    if ( hWritePipe )
      CloseHandle(hWritePipe);
    v91 = 0;
  }
  if ( v93 )
  {
    if ( hObject )
      CloseHandle(hObject);
    v93 = 0;
  }
  if ( (v142 & 0x800000000LL) != 0 )
    operator delete(lpMem);
  if ( v95 )
  {
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    v95 = 0;
  }
  if ( ExitCode )
  {
    if ( v51 )
      CloseHandle(v51);
    v111 = 0;
  }
  return (struct ICorSvcBindToWorker *)v66;
}

```

## disassembly

```asm
0x18002a784  push    rbp
0x18002a786  push    rbx
0x18002a787  push    rsi
0x18002a788  push    rdi
0x18002a789  push    r12
0x18002a78b  push    r13
0x18002a78d  push    r14
0x18002a78f  push    r15
0x18002a791  lea     rbp, [rsp-0A98h]
0x18002a799  sub     rsp, 0B98h
0x18002a7a0  mov     rax, cs:__security_cookie
0x18002a7a7  xor     rax, rsp
0x18002a7aa  mov     [rbp+0AD0h+var_50], rax
0x18002a7b1  mov     r12, r9
0x18002a7b4  mov     [rbp+0AD0h+var_AD0], r9
0x18002a7b8  mov     [rbp+0AD0h+String1], r8
0x18002a7bf  mov     [rbp+0AD0h+var_B08], rdx
0x18002a7c3  mov     [rbp+0AD0h+var_A40], rcx
0x18002a7ca  mov     rax, [rbp+0AD0h+arg_20]
0x18002a7d1  mov     [rbp+0AD0h+var_A50], rax
0x18002a7d8  mov     rax, [rbp+0AD0h+arg_28]
0x18002a7df  mov     [rbp+0AD0h+var_A28], rax
0x18002a7e6  mov     rax, [rbp+0AD0h+arg_30]
0x18002a7ed  mov     [rbp+0AD0h+var_A58], rax
0x18002a7f1  mov     rax, [rbp+0AD0h+arg_38]
0x18002a7f8  mov     [rbp+0AD0h+var_A30], rax
0x18002a7ff  xor     edi, edi
0x18002a801  mov     esi, edi
0x18002a803  mov     [rsp+0BD0h+var_B70], edi
0x18002a807  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002a80b  mov     [rbp+0AD0h+var_AA8], r14
0x18002a80f  mov     eax, edi
0x18002a811  mov     [rsp+0BD0h+ExitCode], eax
0x18002a815  mov     [rbp+0AD0h+var_AA0], eax
0x18002a818  mov     [rbp+0AD0h+var_B28], rdi
0x18002a81c  mov     [rbp+0AD0h+var_B20], edi
0x18002a81f  lea     rcx, ModuleName; "mscorsvc.dll"
0x18002a826  call    cs:__imp_GetModuleHandleW
0x18002a82c  test    rax, rax
0x18002a82f  jz      loc_18002B524
0x18002a835  mov     ebx, 104h
0x18002a83a  mov     r8d, ebx; nSize
0x18002a83d  lea     rdx, [rbp+0AD0h+Filename]; lpFilename
0x18002a844  mov     rcx, rax; hModule
0x18002a847  call    cs:__imp_GetModuleFileNameW
0x18002a84d  test    eax, eax
0x18002a84f  jz      loc_18002B524
0x18002a855  cmp     eax, ebx
0x18002a857  jz      loc_18002B52A
0x18002a85d  mov     [rbp+0AD0h+var_510], rdi
0x18002a864  mov     [rbp+0AD0h+var_510+4], 200h
0x18002a86f  mov     [rbp+0AD0h+lpMem], rdi
0x18002a876  lea     rax, [rbp+0AD0h+var_4F8]
0x18002a87d  mov     [rbp+0AD0h+lpMem], rax
0x18002a884  mov     dword ptr [rbp+0AD0h+var_510], 2
0x18002a88e  mov     rax, [rbp+0AD0h+lpMem]
0x18002a895  mov     [rax], di
0x18002a898  lea     rdx, [rbp+0AD0h+Filename]; unsigned __int16 *
0x18002a89f  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a8a6  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18002a8ab  nop
0x18002a8ac  mov     eax, [rbp+0AD0h+var_508]
0x18002a8b2  shr     eax, 1
0x18002a8b4  not     eax
0x18002a8b6  lea     ebx, [rdi+1]
0x18002a8b9  test    bl, al
0x18002a8bb  jnz     short loc_18002A8D9
0x18002a8bd  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a8c4  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18002a8c9  test    eax, eax
0x18002a8cb  jnz     short loc_18002A8D9
0x18002a8cd  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a8d4  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002a8d9  test    byte ptr [rbp+0AD0h+var_508], 10h
0x18002a8e0  jz      short loc_18002A8F7
0x18002a8e2  mov     r8d, ebx
0x18002a8e5  mov     edx, dword ptr [rbp+0AD0h+var_510+4]
0x18002a8eb  lea     rcx, [rbp+0AD0h+var_510]
0x18002a8f2  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18002a8f7  mov     eax, [rbp+0AD0h+var_508]
0x18002a8fd  test    al, 2
0x18002a8ff  jz      short loc_18002A92C
0x18002a901  and     eax, 7
0x18002a904  cmp     al, 7
0x18002a906  jnz     short loc_18002A910
0x18002a908  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18002a90e  jz      short loc_18002A92C
0x18002a910  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a917  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18002a91c  test    eax, eax
0x18002a91e  jnz     short loc_18002A92C
0x18002a920  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a927  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002a92c  mov     ecx, [rbp+0AD0h+var_508]
0x18002a932  not     ecx
0x18002a934  and     ecx, ebx
0x18002a936  mov     eax, dword ptr [rbp+0AD0h+var_510]
0x18002a93c  shr     eax, cl
0x18002a93e  sub     eax, ebx
0x18002a940  shl     eax, cl
0x18002a942  cdqe
0x18002a944  add     rax, [rbp+0AD0h+lpMem]
0x18002a94b  mov     [rbp+0AD0h+var_A18], rax
0x18002a952  mov     dword ptr [rbp+0AD0h+var_A10], ecx
0x18002a958  lea     r8, asc_180049544; "\\"
0x18002a95f  lea     rdx, [rbp+0AD0h+var_A18]; struct SString::CIterator *
0x18002a966  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a96d  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@PEBG@Z; SString::FindBack(SString::CIterator &,ushort const *)
0x18002a972  lea     rdx, [rbp+0AD0h+var_A18]; struct SString::Iterator *
0x18002a979  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a980  call    ?Truncate@SString@@QEAAXAEBVIterator@1@@Z; SString::Truncate(SString::Iterator const &)
0x18002a985  lea     rdx, aMscorsvwExe; "\\mscorsvw.exe"
0x18002a98c  lea     rcx, [rbp+0AD0h+var_510]; this
0x18002a993  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002a998  mov     [rbp+0AD0h+hObject], r14
0x18002a99c  mov     [rbp+0AD0h+var_B30], edi
0x18002a99f  mov     [rbp+0AD0h+hWritePipe], r14
0x18002a9a3  mov     [rbp+0AD0h+var_B40], edi
0x18002a9a6  mov     [rbp+0AD0h+var_AB8], r14
0x18002a9aa  mov     r15d, edi
0x18002a9ad  mov     [rbp+0AD0h+var_AB0], edi
0x18002a9b0  mov     qword ptr [rbp+0AD0h+PipeAttributes.nLength], 18h
0x18002a9b8  mov     qword ptr [rbp+0AD0h+PipeAttributes.bInheritHandle], 1
0x18002a9c0  mov     [rbp+0AD0h+PipeAttributes.lpSecurityDescriptor], rdi
0x18002a9c4  call    cs:__imp_GetCurrentProcessId
0x18002a9ca  mov     r8d, eax; dwProcessId
0x18002a9cd  mov     edx, ebx; bInheritHandle
0x18002a9cf  mov     ecx, 100000h; dwDesiredAccess
0x18002a9d4  call    cs:__imp_OpenProcess
0x18002a9da  mov     r13, rax
0x18002a9dd  mov     [rbp+0AD0h+var_A80], rax
0x18002a9e1  mov     [rbp+0AD0h+var_A78], edi
0x18002a9e4  mov     eax, edi
0x18002a9e6  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18002a9ea  cmovnz  eax, ebx
0x18002a9ed  mov     [rbp+0AD0h+var_AC8], eax
0x18002a9f0  mov     [rbp+0AD0h+var_A78], eax
0x18002a9f3  mov     [rsp+0BD0h+NumberOfBytesRead], edi
0x18002a9f7  cmp     [rbp+0AD0h+var_B30], edi
0x18002a9fa  jz      short loc_18002AA0E
0x18002a9fc  mov     rcx, [rbp+0AD0h+hObject]; hObject
0x18002aa00  test    rcx, rcx
0x18002aa03  jz      short loc_18002AA0B
0x18002aa05  call    cs:__imp_CloseHandle
0x18002aa0b  mov     [rbp+0AD0h+var_B30], edi
0x18002aa0e  cmp     [rbp+0AD0h+var_B40], edi
0x18002aa11  jz      short loc_18002AA25
0x18002aa13  mov     rcx, [rbp+0AD0h+hWritePipe]; hObject
0x18002aa17  test    rcx, rcx
0x18002aa1a  jz      short loc_18002AA22
0x18002aa1c  call    cs:__imp_CloseHandle
0x18002aa22  mov     [rbp+0AD0h+var_B40], edi
0x18002aa25  test    r15d, r15d
0x18002aa28  jz      short loc_18002AA3E
0x18002aa2a  test    r14, r14
0x18002aa2d  jz      short loc_18002AA38
0x18002aa2f  mov     rcx, r14; hObject
0x18002aa32  call    cs:__imp_CloseHandle
0x18002aa38  mov     r15d, edi
0x18002aa3b  mov     [rbp+0AD0h+var_AB0], edi
0x18002aa3e  lea     rax, [rbp+0AD0h+hWritePipe]
0x18002aa42  mov     [rbp+0AD0h+var_9E8], rax
0x18002aa49  cmp     [rbp+0AD0h+var_B40], edi
0x18002aa4c  jz      short loc_18002AA60
0x18002aa4e  mov     rcx, [rbp+0AD0h+hWritePipe]; hObject
0x18002aa52  test    rcx, rcx
0x18002aa55  jz      short loc_18002AA5D
0x18002aa57  call    cs:__imp_CloseHandle
0x18002aa5d  mov     [rbp+0AD0h+var_B40], edi
0x18002aa60  or      [rbp+0AD0h+hWritePipe], 0FFFFFFFFFFFFFFFFh
0x18002aa65  or      esi, ebx
0x18002aa67  mov     [rsp+0BD0h+var_B70], esi
0x18002aa6b  lea     rax, [rbp+0AD0h+hObject]
0x18002aa6f  mov     [rbp+0AD0h+ppv], rax
0x18002aa73  cmp     [rbp+0AD0h+var_B30], edi
0x18002aa76  jz      short loc_18002AA8A
0x18002aa78  mov     rcx, [rbp+0AD0h+hObject]; hObject
0x18002aa7c  test    rcx, rcx
0x18002aa7f  jz      short loc_18002AA87
0x18002aa81  call    cs:__imp_CloseHandle
0x18002aa87  mov     [rbp+0AD0h+var_B30], edi
0x18002aa8a  or      [rbp+0AD0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002aa8f  or      esi, 2
0x18002aa92  mov     [rsp+0BD0h+var_B70], esi
0x18002aa96  xor     r9d, r9d; nSize
0x18002aa99  lea     r8, [rbp+0AD0h+PipeAttributes]; lpPipeAttributes
0x18002aa9d  lea     rdx, [rbp+0AD0h+hWritePipe]; hWritePipe
0x18002aaa1  lea     rcx, [rbp+0AD0h+hObject]; hReadPipe
0x18002aaa5  call    cs:__imp_CreatePipe
0x18002aaab  test    eax, eax
0x18002aaad  setz    cl
0x18002aab0  and     esi, 0FFFFFFFDh
0x18002aab3  mov     [rsp+0BD0h+var_B70], esi
0x18002aab7  mov     eax, [rbp+0AD0h+var_B30]
0x18002aaba  cmp     [rbp+0AD0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002aabf  cmovnz  eax, ebx
0x18002aac2  mov     [rbp+0AD0h+var_B30], eax
0x18002aac5  and     esi, 0FFFFFFFEh
0x18002aac8  mov     [rsp+0BD0h+var_B70], esi
0x18002aacc  mov     eax, [rbp+0AD0h+var_B40]
0x18002aacf  cmp     [rbp+0AD0h+hWritePipe], 0FFFFFFFFFFFFFFFFh
0x18002aad4  cmovnz  eax, ebx
0x18002aad7  mov     [rbp+0AD0h+var_B40], eax
0x18002aada  test    cl, cl
0x18002aadc  jnz     loc_18002B518
0x18002aae2  xor     r9d, r9d; lpName
0x18002aae5  xor     r8d, r8d; bInitialState
0x18002aae8  xor     edx, edx; bManualReset
0x18002aaea  lea     rcx, [rbp+0AD0h+PipeAttributes]; lpEventAttributes
0x18002aaee  call    cs:__imp_CreateEventW
0x18002aaf4  mov     rbx, rax
0x18002aaf7  mov     [rbp+0AD0h+var_A88], rax
0x18002aafb  test    r15d, r15d
0x18002aafe  jz      short loc_18002AB14
0x18002ab00  test    r14, r14
0x18002ab03  jz      short loc_18002AB0E
0x18002ab05  mov     rcx, r14; hObject
0x18002ab08  call    cs:__imp_CloseHandle
0x18002ab0e  mov     r15d, edi
0x18002ab11  mov     [rbp+0AD0h+var_AB0], edi
0x18002ab14  mov     [rbp+0AD0h+var_AB8], rbx
0x18002ab18  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ab1c  mov     r14d, 1
0x18002ab22  cmovnz  r15d, r14d
0x18002ab26  mov     [rbp+0AD0h+var_AB0], r15d
0x18002ab2a  test    rbx, rbx
0x18002ab2d  jz      loc_18002B518
0x18002ab33  lea     rdx, [rbp+0AD0h+var_510]
0x18002ab3a  lea     rcx, [rbp+0AD0h+var_950]
0x18002ab41  call    ??0?$InlineSString@$0CAA@@@QEAA@AEBV0@@Z; InlineSString<512>::InlineSString<512>(InlineSString<512> const &)
0x18002ab46  nop
0x18002ab47  mov     r8, rbx
0x18002ab4a  lea     rdx, aStartupeventX; " -StartupEvent %x"
0x18002ab51  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ab58  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002ab5d  mov     r8, [rbp+0AD0h+var_A58]
0x18002ab61  lea     rdx, aInterruptevent; " -InterruptEvent %x"
0x18002ab68  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ab6f  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002ab74  mov     r8, r13
0x18002ab77  lea     rdx, aNgenprocessX; " -NGENProcess %x"
0x18002ab7e  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ab85  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002ab8a  mov     r8, [rbp+0AD0h+hWritePipe]
0x18002ab8e  lea     rdx, aPipeX; " -Pipe %x"
0x18002ab95  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ab9c  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002aba1  mov     rax, [rbp+0AD0h+var_A50]
0x18002aba8  test    rax, rax
0x18002abab  jz      short loc_18002ABC3
0x18002abad  mov     r8, rax
0x18002abb0  lea     rdx, aLocalappdataS; " -LocalAppData \"%s\""
0x18002abb7  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002abbe  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002abc3  test    r12, r12
0x18002abc6  jz      short loc_18002ABDE
0x18002abc8  mov     r8, r12
0x18002abcb  lea     rdx, aPackageS; " -Package \"%s\""
0x18002abd2  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002abd9  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18002abde  lea     rdx, aCommentNgenWor; " -Comment \"NGen Worker Process\""
0x18002abe5  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002abec  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002abf1  xor     edx, edx; Val
0x18002abf3  lea     r8d, [rdx+6Ch]; Size
0x18002abf7  lea     rcx, [rbp+0AD0h+var_9C0+4]; void *
0x18002abfe  call    memset_0
0x18002ac03  mov     [rbp+0AD0h+var_9C0.cb], 68h ; 'h'
0x18002ac0d  mov     [rbp+0AD0h+var_730], rdi
0x18002ac14  mov     [rbp+0AD0h+var_730+4], 200h
0x18002ac1f  mov     [rbp+0AD0h+Destination], rdi
0x18002ac26  lea     rax, [rbp+0AD0h+var_718]
0x18002ac2d  mov     [rbp+0AD0h+Destination], rax
0x18002ac34  mov     dword ptr [rbp+0AD0h+var_730], 2
0x18002ac3e  mov     rax, [rbp+0AD0h+Destination]
0x18002ac45  mov     [rax], di
0x18002ac48  mov     ecx, [rbp+0AD0h+var_948]
0x18002ac4e  test    cl, 2
0x18002ac51  jz      short loc_18002AC86
0x18002ac53  mov     eax, ecx
0x18002ac55  and     eax, 7
0x18002ac58  cmp     al, 7
0x18002ac5a  jnz     short loc_18002AC64
0x18002ac5c  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18002ac62  jz      short loc_18002AC86
0x18002ac64  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ac6b  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18002ac70  test    eax, eax
0x18002ac72  jnz     short loc_18002AC80
0x18002ac74  lea     rcx, [rbp+0AD0h+var_950]; this
0x18002ac7b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002ac80  mov     ecx, [rbp+0AD0h+var_948]
0x18002ac86  not     ecx
0x18002ac88  and     ecx, r14d
0x18002ac8b  mov     ebx, [rbp+0AD0h+var_950]
0x18002ac91  shr     ebx, cl
0x18002ac93  xor     r9d, r9d
0x18002ac96  lea     r8d, [r9+4]
0x18002ac9a  mov     edx, ebx
0x18002ac9c  lea     rcx, [rbp+0AD0h+var_730]
  ... truncated ...
```
