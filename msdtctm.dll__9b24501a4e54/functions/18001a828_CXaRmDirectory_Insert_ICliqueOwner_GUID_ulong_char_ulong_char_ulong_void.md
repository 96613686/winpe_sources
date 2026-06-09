# CXaRmDirectory::Insert(ICliqueOwner *,_GUID *,ulong,char *,ulong,char *,ulong *,void * *)

- ea: `0x18001a828`
- end: `0x18001ac62`
- name: `?Insert@CXaRmDirectory@@QEAAKPEAUICliqueOwner@@PEAU_GUID@@KPEADK2PEAKPEAPEAX@Z`
- size: `1082`
- prototype: `__int64 __fastcall(CXaRmDirectory *this, struct ICliqueOwner *, struct _GUID *, unsigned int, char *, unsigned int, char *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009b9a0`

## callees

- `0x18001a828`
- `0x18001b4f0`
- `0x18001bb84`
- `0x18001bda4`
- `0x180021688`
- `0x180025770`
- `0x18009abb8`
- `0x18009d074`
- `0x18009d834`
- `0x18009dba4`
- `0x18009ddc8`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001abff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001abff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa26`
- `RPCRT4!UuidHash` at `0x18001ab20`
- `RPCRT4!UuidHash` at `0x18001ab20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a995`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001a921`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001a921`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a9d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a9d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a98a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a98a`

## string_xrefs

- `0x18001a949`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001a9bf`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001aa6e`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001aaf4`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001aafb`: `CXaOpenState`

## pseudocode

```c
__int64 __fastcall CXaRmDirectory::Insert(
        CXaRmDirectory *this,
        struct ICliqueOwner *a2,
        struct _GUID *a3,
        unsigned int a4,
        char *a5,
        unsigned int a6,
        char *a7,
        unsigned int *a8,
        void **a9)
{
  int v11; // ebx
  HMODULE Library; // rax
  HMODULE v14; // rbx
  signed int LastError; // eax
  unsigned int v16; // ecx
  FARPROC ProcAddress; // rax
  signed int v18; // eax
  int v19; // r8d
  unsigned int v20; // ecx
  CXaSynch *v21; // rax
  CXaSynch *v22; // rdi
  unsigned int v23; // ebx
  CXaRmDirectoryBucket *v24; // r14
  int v25; // [rsp+20h] [rbp-EE8h]
  CHAR *v26; // [rsp+20h] [rbp-EE8h]
  int v27; // [rsp+28h] [rbp-EE0h]
  CXaSynch *i; // [rsp+50h] [rbp-EB8h] BYREF
  RPC_STATUS Status; // [rsp+58h] [rbp-EB0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-EA8h] BYREF
  void **v31; // [rsp+68h] [rbp-EA0h] BYREF
  int v32; // [rsp+70h] [rbp-E98h]
  __int128 v33; // [rsp+78h] [rbp-E90h]
  void **v34; // [rsp+88h] [rbp-E80h] BYREF
  int v35; // [rsp+90h] [rbp-E78h]
  __int128 v36; // [rsp+98h] [rbp-E70h]
  CHAR ValueName[256]; // [rsp+B0h] [rbp-E58h] BYREF
  CHAR LibFileName[272]; // [rsp+1B0h] [rbp-D58h] BYREF
  char v39[3072]; // [rsp+2C0h] [rbp-C48h] BYREF

  v30 = 0;
  if ( a4 >= 0xC00 || a6 >= 0x100 )
    return 2147942487LL;
  TracedStringCbCopyNA(v39, 0xC00u, a5, a4);
  TracedStringCbCopyNA(ValueName, 0x100u, a7, a6);
  *a9 = 0;
  memset_0(LibFileName, 0, 0x105u);
  v11 = LookUpXaDllPath(ValueName, LibFileName);
  if ( v11 < 0 )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    return (unsigned int)v11;
  }
  Library = LoadLibraryExA(LibFileName, 0, 0);
  v14 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    XA_TRACE_WARNING(v16, LastError, ValueName, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 567);
    goto LABEL_9;
  }
  ProcAddress = GetProcAddress(Library, "GetXaSwitch");
  if ( !ProcAddress )
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v26 = ValueName;
    v19 = 582;
    v20 = -2147430310;
    goto LABEL_15;
  }
  try
  {
    v18 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(1, &v30);
  }
  catch ( ... )
  {
    XA_TRACE_WARNING(0x8000D057, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 602, ValueName, v25);
    DtcXaException("GetXaSwitch");
  }
  if ( v18 )
  {
    v26 = LibFileName;
    v19 = 610;
    v20 = -2147430321;
LABEL_15:
    XA_TRACE_WARNING(v20, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", v19, v18, v26, v27);
    FreeLibrary(v14);
LABEL_9:
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    return 0x80000000LL;
  }
  *a8 = _InterlockedIncrement((volatile signed __int32 *)&CXaRmDirectory::m_cRmId);
  v21 = (CXaSynch *)HeapAlloc(g_CXaSynch_MemAlloc, 0, 0x668u);
  i = v21;
  if ( v21 )
    v22 = CXaSynch::CXaSynch(v21);
  else
    v22 = 0;
  if ( !v22 )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    COMMON_TRACE("CXaSynch", "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 641, 0xC000110B);
    return 0x80000000LL;
  }
  v31 = &UTStaticList2<CXaOpenState *>::`vftable';
  v32 = 0;
  v33 = 0;
  v34 = &UTStaticList2<CXaOpenState *>::`vftable';
  v35 = 0;
  v36 = 0;
  if ( !(unsigned int)CTaskManager::AllocateXaOpenStateElements(*a8, &v31, &v34) )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    COMMON_TRACE("CXaOpenState", "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 652, 0xC000110B);
    return 0x80000000LL;
  }
  Status = 0;
  v23 = g_XaDirectory;
  v24 = (CXaRmDirectoryBucket *)(qword_18015DB38 + 80LL * (UuidHash(a3, &Status) % v23));
  (*(void (__fastcall **)(struct ICliqueOwner *))(*(_QWORD *)a2 + 8LL))(a2);
  (*(void (__fastcall **)(CXaSynch *, struct ICliqueOwner *, char *, CHAR *, __int64, int, struct _GUID *, unsigned int *, void **))(*(_QWORD *)v22 + 24LL))(
    v22,
    a2,
    v39,
    ValueName,
    v30,
    1,
    a3,
    a8,
    a9);
  EnterCriticalSection(&stru_180153898);
  for ( i = 0;
        (unsigned int)UTStaticList2<CSuperiorConnLink *>::RemoveLast(&v31, &i);
        (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v22 + 57) + 24LL))((__int64)v22 + 456, *((_QWORD *)i + 1)) )
  {
    ;
  }
  CTaskManager::DistributeXaOpenStateObjectsToThreads(&v34);
  LeaveCriticalSection(&stru_180153898);
  (**((void (__fastcall ***)(__int64))v24 + 3))((__int64)v24 + 24);
  CXaRmDirectoryBucket::InsertXaResource(v24, (CXaSynch *)((char *)v22 + 416));
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v24 + 3) + 8LL))((__int64)v24 + 24);
  return 1;
}

```

## disassembly

```asm
0x18001a828  push    rbx
0x18001a82a  push    rsi
0x18001a82b  push    rdi
0x18001a82c  push    r12
0x18001a82e  push    r13
0x18001a830  push    r14
0x18001a832  push    r15
0x18001a834  sub     rsp, 0ED0h
0x18001a83b  mov     rax, cs:__security_cookie
0x18001a842  xor     rax, rsp
0x18001a845  mov     [rsp+0F08h+var_48], rax
0x18001a84d  mov     r13, r8
0x18001a850  mov     r12, rdx
0x18001a853  mov     r8, [rsp+0F08h+arg_20]; char *
0x18001a85b  mov     rbx, [rsp+0F08h+arg_30]
0x18001a863  mov     rsi, [rsp+0F08h+arg_38]
0x18001a86b  mov     r15, [rsp+0F08h+arg_40]
0x18001a873  xor     r14d, r14d
0x18001a876  mov     [rsp+0F08h+var_EA8], r14
0x18001a87b  mov     edx, 0C00h; unsigned __int64
0x18001a880  cmp     r9d, edx
0x18001a883  jnb     loc_18001AC3A
0x18001a889  mov     edi, 100h
0x18001a88e  cmp     [rsp+0F08h+arg_28], edi
0x18001a895  jnb     loc_18001AC3A
0x18001a89b  mov     r9d, r9d; unsigned __int64
0x18001a89e  lea     rcx, [rsp+0F08h+var_C48]; char *
0x18001a8a6  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001a8ab  mov     r9d, [rsp+0F08h+arg_28]; unsigned __int64
0x18001a8b3  mov     r8, rbx; char *
0x18001a8b6  mov     edx, edi; unsigned __int64
0x18001a8b8  lea     rcx, [rsp+0F08h+ValueName]; char *
0x18001a8c0  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001a8c5  mov     [r15], r14
0x18001a8c8  xor     edx, edx; Val
0x18001a8ca  lea     r8d, [rdi+5]; Size
0x18001a8ce  lea     rcx, [rsp+0F08h+LibFileName]; void *
0x18001a8d6  call    memset_0
0x18001a8db  lea     rdx, [rsp+0F08h+LibFileName]; char *
0x18001a8e3  lea     rcx, [rsp+0F08h+ValueName]; lpValueName
0x18001a8eb  call    ?LookUpXaDllPath@@YAJPEAD0K@Z; LookUpXaDllPath(char *,char *,ulong)
0x18001a8f0  mov     ebx, eax
0x18001a8f2  test    eax, eax
0x18001a8f4  jns     short loc_18001A914
0x18001a8f6  mov     rcx, cs:qword_18015DB40
0x18001a8fd  mov     rax, [rcx+8]
0x18001a901  lea     rcx, qword_18015DB40
0x18001a908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a90d  mov     eax, ebx
0x18001a90f  jmp     loc_18001AC3F
0x18001a914  xor     r8d, r8d; dwFlags
0x18001a917  xor     edx, edx; hFile
0x18001a919  lea     rcx, [rsp+0F08h+LibFileName]; lpLibFileName
0x18001a921  call    cs:__imp_LoadLibraryExA
0x18001a927  mov     rbx, rax
0x18001a92a  test    rax, rax
0x18001a92d  jnz     short loc_18001A980
0x18001a92f  call    cs:__imp_GetLastError
0x18001a935  test    eax, eax
0x18001a937  jle     short loc_18001A941
0x18001a939  movzx   eax, ax
0x18001a93c  or      eax, 80070000h
0x18001a941  mov     dword ptr [rsp+0F08h+var_EE8], 237h; int
0x18001a949  lea     r9, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001a950  lea     r8, [rsp+0F08h+ValueName]; char *
0x18001a958  mov     edx, eax; unsigned int
0x18001a95a  call    ?XA_TRACE_WARNING@@YAXKKPEAD0H@Z; XA_TRACE_WARNING(ulong,ulong,char *,char *,int)
0x18001a95f  mov     rax, cs:qword_18015DB40
0x18001a966  lea     rcx, qword_18015DB40
0x18001a96d  mov     rax, [rax+8]
0x18001a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a976  mov     eax, 80000000h
0x18001a97b  jmp     loc_18001AC3F
0x18001a980  lea     rdx, aGetxaswitch; "GetXaSwitch"
0x18001a987  mov     rcx, rbx; hModule
0x18001a98a  call    cs:__imp_GetProcAddress
0x18001a990  test    rax, rax
0x18001a993  jnz     short loc_18001A9D9
0x18001a995  call    cs:__imp_GetLastError
0x18001a99b  test    eax, eax
0x18001a99d  jle     short loc_18001A9A7
0x18001a99f  movzx   eax, ax
0x18001a9a2  or      eax, 80070000h
0x18001a9a7  lea     rcx, [rsp+0F08h+ValueName]
0x18001a9af  mov     [rsp+0F08h+var_EE8], rcx; char *
0x18001a9b4  mov     r8d, 246h; int
0x18001a9ba  mov     ecx, 8000D05Ah; unsigned int
0x18001a9bf  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001a9c6  mov     r9d, eax; unsigned int
0x18001a9c9  call    ?XA_TRACE_WARNING@@YAXKPEADHK0H@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,char *,int)
0x18001a9ce  mov     rcx, rbx; hLibModule
0x18001a9d1  call    cs:__imp_FreeLibrary
0x18001a9d7  jmp     short loc_18001A95F
0x18001a9d9  lea     rdx, [rsp+0F08h+var_EA8]
0x18001a9de  mov     edi, 1
0x18001a9e3  mov     ecx, edi
0x18001a9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ea  nop
0x18001a9eb  test    eax, eax
0x18001a9ed  jz      short loc_18001AA09
0x18001a9ef  lea     rcx, [rsp+0F08h+LibFileName]
0x18001a9f7  mov     [rsp+0F08h+var_EE8], rcx
0x18001a9fc  mov     r8d, 262h
0x18001aa02  mov     ecx, 8000D04Fh
0x18001aa07  jmp     short loc_18001A9BF
0x18001aa09  mov     eax, edi
0x18001aa0b  lock xadd cs:?m_cRmId@CXaRmDirectory@@0KA, eax; ulong CXaRmDirectory::m_cRmId
0x18001aa13  add     eax, edi
0x18001aa15  mov     [rsi], eax
0x18001aa17  xor     edx, edx; dwFlags
0x18001aa19  mov     r8d, 668h; dwBytes
0x18001aa1f  mov     rcx, cs:?g_CXaSynch_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x18001aa26  call    cs:__imp_HeapAlloc
0x18001aa2c  mov     [rsp+0F08h+var_EB8], rax
0x18001aa31  test    rax, rax
0x18001aa34  jz      short loc_18001AA43
0x18001aa36  mov     rcx, rax; this
0x18001aa39  call    ??0CXaSynch@@QEAA@XZ; CXaSynch::CXaSynch(void)
0x18001aa3e  mov     rdi, rax
0x18001aa41  jmp     short loc_18001AA46
0x18001aa43  mov     rdi, r14
0x18001aa46  test    rdi, rdi
0x18001aa49  jnz     short loc_18001AA86
0x18001aa4b  mov     rax, cs:qword_18015DB40
0x18001aa52  lea     rcx, qword_18015DB40
0x18001aa59  mov     rax, [rax+8]
0x18001aa5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa62  mov     r9d, 0C000110Bh; unsigned int
0x18001aa68  mov     r8d, 281h; int
0x18001aa6e  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001aa75  lea     rcx, aCxasynch; "CXaSynch"
0x18001aa7c  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x18001aa81  jmp     loc_18001A976
0x18001aa86  lea     rax, ??_7?$UTStaticList2@PEAVCXaOpenState@@@@6B@; const UTStaticList2<CXaOpenState *>::`vftable'
0x18001aa8d  mov     [rsp+0F08h+var_EA0], rax
0x18001aa92  mov     [rsp+0F08h+var_E98], r14d
0x18001aa97  xorps   xmm0, xmm0
0x18001aa9a  movdqu  [rsp+0F08h+var_E90], xmm0
0x18001aaa0  mov     [rsp+0F08h+var_E80], rax
0x18001aaa8  mov     [rsp+0F08h+var_E78], r14d
0x18001aab0  movdqu  [rsp+0F08h+var_E70], xmm0
0x18001aab9  lea     r8, [rsp+0F08h+var_E80]
0x18001aac1  lea     rdx, [rsp+0F08h+var_EA0]
0x18001aac6  mov     ecx, [rsi]
0x18001aac8  call    ?AllocateXaOpenStateElements@CTaskManager@@SAHIPEAV?$UTStaticList2@PEAVCXaOpenState@@@@0@Z; CTaskManager::AllocateXaOpenStateElements(uint,UTStaticList2<CXaOpenState *> *,UTStaticList2<CXaOpenState *> *)
0x18001aacd  test    eax, eax
0x18001aacf  jnz     short loc_18001AB0D
0x18001aad1  mov     rax, cs:qword_18015DB40
0x18001aad8  lea     rcx, qword_18015DB40
0x18001aadf  mov     rax, [rax+8]
0x18001aae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aae8  mov     r9d, 0C000110Bh; unsigned int
0x18001aaee  mov     r8d, 28Ch; int
0x18001aaf4  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001aafb  lea     rcx, aCxaopenstate; "CXaOpenState"
0x18001ab02  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x18001ab07  nop
0x18001ab08  jmp     loc_18001A976
0x18001ab0d  mov     [rsp+0F08h+Status], r14d
0x18001ab12  mov     ebx, cs:?g_XaDirectory@@3VCXaRmDirectory@@A; CXaRmDirectory g_XaDirectory
0x18001ab18  lea     rdx, [rsp+0F08h+Status]; Status
0x18001ab1d  mov     rcx, r13; Uuid
0x18001ab20  call    cs:__imp_UuidHash
0x18001ab26  movzx   eax, ax
0x18001ab29  xor     edx, edx
0x18001ab2b  div     ebx
0x18001ab2d  lea     r14, [rdx+rdx*4]
0x18001ab31  shl     r14, 4
0x18001ab35  add     r14, cs:qword_18015DB38
0x18001ab3c  mov     rax, [r12]
0x18001ab40  mov     rcx, r12
0x18001ab43  mov     rax, [rax+8]
0x18001ab47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab4c  mov     rax, [rdi]
0x18001ab4f  mov     [rsp+0F08h+var_EC8], r15
0x18001ab54  mov     [rsp+0F08h+var_ED0], rsi
0x18001ab59  mov     [rsp+0F08h+var_ED8], r13
0x18001ab5e  mov     esi, 1
0x18001ab63  mov     [rsp+0F08h+var_EE0], esi
0x18001ab67  mov     rcx, [rsp+0F08h+var_EA8]
0x18001ab6c  mov     [rsp+0F08h+var_EE8], rcx
0x18001ab71  lea     r9, [rsp+0F08h+ValueName]
0x18001ab79  lea     r8, [rsp+0F08h+var_C48]
0x18001ab81  mov     rdx, r12
0x18001ab84  mov     rcx, rdi
0x18001ab87  mov     rax, [rax+18h]
0x18001ab8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab90  lea     rcx, stru_180153898; lpCriticalSection
0x18001ab97  call    cs:__imp_EnterCriticalSection
0x18001ab9d  mov     [rsp+0F08h+var_EB8], 0
0x18001aba6  lea     rdx, [rsp+0F08h+var_EB8]
0x18001abab  lea     rcx, [rsp+0F08h+var_EA0]
0x18001abb0  call    ?RemoveLast@?$UTStaticList2@PEAVCSuperiorConnLink@@@@UEAAHPEAPEAV?$UTStaticLink2@PEAVCSuperiorConnLink@@@@@Z; UTStaticList2<CSuperiorConnLink *>::RemoveLast(UTStaticLink2<CSuperiorConnLink *> * *)
0x18001abb5  test    eax, eax
0x18001abb7  jz      short loc_18001ABEB
0x18001abb9  lea     rbx, [rdi+1C8h]
0x18001abc0  mov     rax, [rbx]
0x18001abc3  mov     rdx, [rsp+0F08h+var_EB8]
0x18001abc8  mov     rdx, [rdx+8]
0x18001abcc  mov     rcx, rbx
0x18001abcf  mov     rax, [rax+18h]
0x18001abd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abd8  lea     rdx, [rsp+0F08h+var_EB8]
0x18001abdd  lea     rcx, [rsp+0F08h+var_EA0]
0x18001abe2  call    ?RemoveLast@?$UTStaticList2@PEAVCSuperiorConnLink@@@@UEAAHPEAPEAV?$UTStaticLink2@PEAVCSuperiorConnLink@@@@@Z; UTStaticList2<CSuperiorConnLink *>::RemoveLast(UTStaticLink2<CSuperiorConnLink *> * *)
0x18001abe7  test    eax, eax
0x18001abe9  jnz     short loc_18001ABC0
0x18001abeb  lea     rcx, [rsp+0F08h+var_E80]
0x18001abf3  call    ?DistributeXaOpenStateObjectsToThreads@CTaskManager@@SAXPEAV?$UTStaticList2@PEAVCXaOpenState@@@@@Z; CTaskManager::DistributeXaOpenStateObjectsToThreads(UTStaticList2<CXaOpenState *> *)
0x18001abf8  lea     rcx, stru_180153898; lpCriticalSection
0x18001abff  call    cs:__imp_LeaveCriticalSection
0x18001ac05  lea     rbx, [r14+18h]
0x18001ac09  mov     rax, [rbx]
0x18001ac0c  mov     rcx, rbx
0x18001ac0f  mov     rax, [rax]
0x18001ac12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac17  lea     rdx, [rdi+1A0h]; struct CXaGeneric *
0x18001ac1e  mov     rcx, r14; this
0x18001ac21  call    ?InsertXaResource@CXaRmDirectoryBucket@@QEAAHPEAVCXaGeneric@@@Z; CXaRmDirectoryBucket::InsertXaResource(CXaGeneric *)
0x18001ac26  mov     rdx, [rbx]
0x18001ac29  mov     rcx, rbx
0x18001ac2c  mov     rax, [rdx+8]
0x18001ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac35  nop
0x18001ac36  mov     eax, esi
0x18001ac38  jmp     short loc_18001AC3F
0x18001ac3a  mov     eax, 80070057h
0x18001ac3f  mov     rcx, [rsp+0F08h+var_48]
0x18001ac47  xor     rcx, rsp; StackCookie
0x18001ac4a  call    __security_check_cookie
0x18001ac4f  add     rsp, 0ED0h
0x18001ac56  pop     r15
0x18001ac58  pop     r14
0x18001ac5a  pop     r13
0x18001ac5c  pop     r12
0x18001ac5e  pop     rdi
0x18001ac5f  pop     rsi
0x18001ac60  pop     rbx
0x18001ac61  retn
```
