# CXaRmDirectory::Insert(ICliqueOwner *,ulong,char *,ulong,char *,int,_GUID *,ulong *,void * *)

- ea: `0x18001ae88`
- end: `0x18001b4e9`
- name: `?Insert@CXaRmDirectory@@QEAAKPEAUICliqueOwner@@KPEADK1HPEAU_GUID@@PEAKPEAPEAX@Z`
- size: `1633`
- prototype: `__int64 __fastcall(CXaRmDirectory *this, struct ICliqueOwner *, unsigned int, char *, unsigned int, char *, int, struct _GUID *, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009b9a0`
- `0x1800a71e0`

## callees

- `0x18001ac68`
- `0x18001ae88`
- `0x18001b4f0`
- `0x18001b584`
- `0x18001b5e4`
- `0x18001b71c`
- `0x18001b804`
- `0x18001bb84`
- `0x18001bcc4`
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

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b44b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b44b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b1a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b1a4`
- `RPCRT4!UuidCreate` at `0x18001b22b`
- `RPCRT4!UuidCreate` at `0x18001b22b`
- `RPCRT4!UuidHash` at `0x18001b24c`
- `RPCRT4!UuidHash` at `0x18001b24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b133`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b0bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b0bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b150`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b150`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b128`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b128`

## string_xrefs

- `0x18001b0e7`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001b182`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001b1e7`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001b373`: `com\complus\dtc\dtc\xatm\src\xarmdir.cpp`
- `0x18001b37a`: `CXaOpenState`

## pseudocode

```c
__int64 __fastcall CXaRmDirectory::Insert(
        CXaRmDirectory *this,
        struct ICliqueOwner *a2,
        unsigned int a3,
        char *a4,
        unsigned int a5,
        char *a6,
        int a7,
        struct _GUID *a8,
        unsigned int *a9,
        void **a10)
{
  CXaSynch *v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rdx
  int v13; // r12d
  int v14; // ebx
  const struct _GUID *v16; // r9
  HMODULE Library; // rax
  HMODULE v18; // rbx
  signed int LastError; // eax
  unsigned int v20; // ecx
  FARPROC ProcAddress; // rax
  signed int v22; // eax
  char *v23; // rdx
  unsigned int v24; // ecx
  int v25; // r8d
  unsigned int v26; // eax
  CXaSynch *v27; // rax
  int v28; // esi
  unsigned int v29; // ebx
  UUID v30; // xmm6
  UUID v31; // xmm7
  UUID *v32; // rax
  __int64 v33; // rdx
  struct ICliqueOwner *v34; // rbx
  int v35; // [rsp+20h] [rbp-F48h]
  int v36; // [rsp+20h] [rbp-F48h]
  int v37; // [rsp+28h] [rbp-F40h]
  RPC_STATUS Status[2]; // [rsp+50h] [rbp-F18h] BYREF
  __int64 v39; // [rsp+58h] [rbp-F10h] BYREF
  char *v40; // [rsp+60h] [rbp-F08h]
  struct ICliqueOwner *v41; // [rsp+68h] [rbp-F00h]
  void **v42; // [rsp+70h] [rbp-EF8h] BYREF
  int v43; // [rsp+78h] [rbp-EF0h]
  __int128 v44; // [rsp+80h] [rbp-EE8h]
  void **v45; // [rsp+90h] [rbp-ED8h] BYREF
  int v46; // [rsp+98h] [rbp-ED0h]
  __int128 v47; // [rsp+A0h] [rbp-EC8h]
  UUID Uuid; // [rsp+B0h] [rbp-EB8h] BYREF
  CXaRmDirectoryBucket *v49[2]; // [rsp+C0h] [rbp-EA8h]
  CHAR v50[32]; // [rsp+D0h] [rbp-E98h] BYREF
  CHAR LibFileName[272]; // [rsp+F0h] [rbp-E78h] BYREF
  CHAR ValueName[256]; // [rsp+200h] [rbp-D68h] BYREF
  char v53[3072]; // [rsp+300h] [rbp-C68h] BYREF

  v40 = a4;
  v41 = a2;
  v10 = 0;
  v39 = 0;
  Uuid = 0;
  *(_OWORD *)v49 = 0;
  if ( a3 >= 0xC00 || a5 >= 0x100 )
    return 2147942487LL;
  TracedStringCbCopyNA(v53, 0xC00u, a4, a3);
  TracedStringCbCopyNA(ValueName, 0x100u, a6, a5);
  *a10 = 0;
  (*(void (__fastcall **)(__int64 *))qword_18015DB40)(&qword_18015DB40);
  std::string::string(v50, v53);
  v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::string,_MAP_ELEMENT,std::less<std::string>,throwing_allocator<std::pair<std::string,_MAP_ELEMENT>>,0>>::find(
                     &qword_18015DB78,
                     Status,
                     v50);
  LOBYTE(v12) = 1;
  std::string::_Tidy(v50, v12, 0);
  if ( v11 == qword_18015DB78 )
  {
    v13 = 0;
  }
  else
  {
    v13 = 1;
    Uuid = *(UUID *)(v11 + 64);
    *(_OWORD *)v49 = *(_OWORD *)(v11 + 80);
    if ( _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)v49, 8)) == 1 )
    {
      (**((void (__fastcall ***)(char *))v49[0] + 3))((char *)v49[0] + 24);
      (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
      CXaRmDirectoryBucket::GetXaResource(v49[0], &Uuid, a9, v16, a10);
      (*(void (__fastcall **)(char *))(*((_QWORD *)v49[0] + 3) + 8LL))((char *)v49[0] + 24);
      if ( *a10 )
      {
        *a8 = Uuid;
        return 2;
      }
      return 0x80000000LL;
    }
  }
  memset_0(LibFileName, 0, 0x105u);
  v14 = LookUpXaDllPath(ValueName, LibFileName);
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    return (unsigned int)v14;
  }
  Library = LoadLibraryExA(LibFileName, 0, 0);
  v18 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    XA_TRACE_WARNING(v20, LastError, ValueName, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 321);
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(Library, "GetXaSwitch");
  if ( !ProcAddress )
  {
    v22 = GetLastError();
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    XA_TRACE_WARNING(v24, v23, v25, v22, v36);
    goto LABEL_20;
  }
  try
  {
    v26 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(1, &v39);
  }
  catch ( ... )
  {
    XA_TRACE_WARNING(0x8000D057, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 356, LibFileName, v35);
    DtcXaException("GetXaSwitch");
  }
  if ( v26 )
  {
    XA_TRACE_WARNING(0x8000D04F, "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 364, v26, LibFileName, v37);
LABEL_20:
    FreeLibrary(v18);
LABEL_14:
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    return 0x80000000LL;
  }
  v27 = (CXaSynch *)HeapAlloc(g_CXaSynch_MemAlloc, 0, 0x668u);
  *(_QWORD *)Status = v27;
  if ( v27 )
    v10 = CXaSynch::CXaSynch(v27);
  if ( !v10 )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    COMMON_TRACE("CXaSynch", "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 393, 0xC000110B);
    return 0x80000000LL;
  }
  if ( v13 )
  {
    *(_DWORD *)(v11 + 88) = 1;
    v28 = a7;
  }
  else
  {
    v28 = a7;
    if ( a7 == 1 )
      Uuid = *a8;
    else
      UuidCreate(&Uuid);
    Status[0] = 0;
    v29 = g_XaDirectory;
    v49[0] = (CXaRmDirectoryBucket *)(qword_18015DB38 + 80LL * (UuidHash(&Uuid, Status) % v29));
    LODWORD(v49[1]) = 1;
    v30 = Uuid;
    v31 = *(UUID *)v49;
    std::string::string(v50, v40);
    v32 = (UUID *)std::map<std::string,_MAP_ELEMENT,std::less<std::string>,throwing_allocator<std::pair<std::string,_MAP_ELEMENT>>>::operator[](
                    &qword_18015DB78,
                    v50);
    *v32 = v30;
    v32[1] = v31;
    LOBYTE(v33) = 1;
    std::string::_Tidy(v50, v33, 0);
  }
  *a9 = _InterlockedIncrement((volatile signed __int32 *)&CXaRmDirectory::m_cRmId);
  if ( !v28 )
    *a8 = Uuid;
  v42 = &UTStaticList2<CXaOpenState *>::`vftable';
  v43 = 0;
  v44 = 0;
  v45 = &UTStaticList2<CXaOpenState *>::`vftable';
  v46 = 0;
  v47 = 0;
  if ( !(unsigned int)CTaskManager::AllocateXaOpenStateElements(*a9, &v42, &v45) )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
    COMMON_TRACE("CXaOpenState", "com\\complus\\dtc\\dtc\\xatm\\src\\xarmdir.cpp", 441, 0xC000110B);
    return 0x80000000LL;
  }
  v34 = v41;
  (*(void (__fastcall **)(struct ICliqueOwner *))(*(_QWORD *)v41 + 8LL))(v41);
  (*(void (__fastcall **)(CXaSynch *, struct ICliqueOwner *, char *, CHAR *, __int64, _DWORD, struct _GUID *, unsigned int *, void **))(*(_QWORD *)v10 + 24LL))(
    v10,
    v34,
    v53,
    ValueName,
    v39,
    0,
    a8,
    a9,
    a10);
  EnterCriticalSection(&stru_180153898);
  *(_QWORD *)Status = 0;
  while ( (unsigned int)UTStaticList2<CSuperiorConnLink *>::RemoveLast(&v42, Status) )
    (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v10 + 57) + 24LL))(
      (__int64)v10 + 456,
      *(_QWORD *)(*(_QWORD *)Status + 8LL));
  CTaskManager::DistributeXaOpenStateObjectsToThreads(&v45);
  LeaveCriticalSection(&stru_180153898);
  (**((void (__fastcall ***)(char *))v49[0] + 3))((char *)v49[0] + 24);
  CXaRmDirectoryBucket::InsertXaResource(v49[0], (CXaSynch *)((char *)v10 + 416));
  (*(void (__fastcall **)(__int64 *))(qword_18015DB40 + 8))(&qword_18015DB40);
  (*(void (__fastcall **)(char *))(*((_QWORD *)v49[0] + 3) + 8LL))((char *)v49[0] + 24);
  return 1;
}

```

## disassembly

```asm
0x18001ae88  mov     rax, rsp
0x18001ae8b  push    rbx
0x18001ae8c  push    rsi
0x18001ae8d  push    rdi
0x18001ae8e  push    r12
0x18001ae90  push    r13
0x18001ae92  push    r14
0x18001ae94  push    r15
0x18001ae96  sub     rsp, 0F30h
0x18001ae9d  movaps  xmmword ptr [rax-48h], xmm6
0x18001aea1  movaps  xmmword ptr [rax-58h], xmm7
0x18001aea5  mov     rax, cs:__security_cookie
0x18001aeac  xor     rax, rsp
0x18001aeaf  mov     [rsp+0F68h+var_68], rax
0x18001aeb7  mov     rax, r9
0x18001aeba  mov     [rsp+0F68h+var_F08], rax
0x18001aebf  mov     [rsp+0F68h+var_F00], rdx
0x18001aec4  mov     rbx, [rsp+0F68h+arg_28]
0x18001aecc  mov     r14, [rsp+0F68h+arg_38]
0x18001aed4  mov     r15, [rsp+0F68h+arg_40]
0x18001aedc  mov     r13, [rsp+0F68h+arg_48]
0x18001aee4  xor     edi, edi
0x18001aee6  mov     [rsp+0F68h+var_F10], rdi
0x18001aeeb  xorps   xmm0, xmm0
0x18001aeee  movups  xmmword ptr [rsp+0F68h+Uuid.Data1], xmm0
0x18001aef6  movups  xmmword ptr [rsp+0F68h+var_EA8], xmm0
0x18001aefe  mov     edx, 0C00h; unsigned __int64
0x18001af03  cmp     r8d, edx
0x18001af06  jnb     loc_18001B4B3
0x18001af0c  mov     esi, 100h
0x18001af11  cmp     [rsp+0F68h+arg_20], esi
0x18001af18  jnb     loc_18001B4B3
0x18001af1e  mov     r9d, r8d; unsigned __int64
0x18001af21  mov     r8, rax; char *
0x18001af24  lea     rcx, [rsp+0F68h+var_C68]; char *
0x18001af2c  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001af31  mov     r9d, [rsp+0F68h+arg_20]; unsigned __int64
0x18001af39  mov     r8, rbx; char *
0x18001af3c  mov     edx, esi; unsigned __int64
0x18001af3e  lea     rcx, [rsp+0F68h+ValueName]; char *
0x18001af46  call    ?TracedStringCbCopyNA@@YAXPEAD_KPEBD1@Z; TracedStringCbCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001af4b  mov     [r13+0], rdi
0x18001af4f  mov     rax, cs:qword_18015DB40
0x18001af56  lea     rcx, qword_18015DB40
0x18001af5d  mov     rax, [rax]
0x18001af60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af65  lea     rdx, [rsp+0F68h+var_C68]
0x18001af6d  lea     rcx, [rsp+0F68h+var_E98]
0x18001af75  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18001af7a  lea     r8, [rsp+0F68h+var_E98]
0x18001af82  lea     rdx, [rsp+0F68h+Status]
0x18001af87  lea     rcx, qword_18015DB78
0x18001af8e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U_MAP_ELEMENT@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$throwing_allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U_MAP_ELEMENT@@@std@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U_MAP_ELEMENT@@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,_MAP_ELEMENT,std::less<std::string>,throwing_allocator<std::pair<std::string,_MAP_ELEMENT>>,0>>::find(std::string const &)
0x18001af93  mov     rsi, [rax]
0x18001af96  xor     r8d, r8d
0x18001af99  mov     dl, 1
0x18001af9b  lea     rcx, [rsp+0F68h+var_E98]
0x18001afa3  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18001afa8  cmp     rsi, cs:qword_18015DB78
0x18001afaf  jnz     short loc_18001B006
0x18001afb1  mov     r12d, edi
0x18001afb4  xor     edx, edx; Val
0x18001afb6  mov     r8d, 105h; Size
0x18001afbc  lea     rcx, [rsp+0F68h+LibFileName]; void *
0x18001afc4  call    memset_0
0x18001afc9  lea     rdx, [rsp+0F68h+LibFileName]; char *
0x18001afd1  lea     rcx, [rsp+0F68h+ValueName]; lpValueName
0x18001afd9  call    ?LookUpXaDllPath@@YAJPEAD0K@Z; LookUpXaDllPath(char *,char *,ulong)
0x18001afde  mov     ebx, eax
0x18001afe0  test    eax, eax
0x18001afe2  jns     loc_18001B0B2
0x18001afe8  mov     rcx, cs:qword_18015DB40
0x18001afef  mov     rax, [rcx+8]
0x18001aff3  lea     rcx, qword_18015DB40
0x18001affa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afff  mov     eax, ebx
0x18001b001  jmp     loc_18001B4B8
0x18001b006  mov     r12d, 1
0x18001b00c  movups  xmm0, xmmword ptr [rsi+40h]
0x18001b010  movups  xmmword ptr [rsp+0F68h+Uuid.Data1], xmm0
0x18001b018  movups  xmm1, xmmword ptr [rsi+50h]
0x18001b01c  movups  xmmword ptr [rsp+0F68h+var_EA8], xmm1
0x18001b024  psrldq  xmm1, 8
0x18001b029  movd    eax, xmm1
0x18001b02d  cmp     eax, r12d
0x18001b030  jnz     short loc_18001AFB4
0x18001b032  mov     rcx, [rsp+0F68h+var_EA8]
0x18001b03a  add     rcx, 18h
0x18001b03e  mov     rax, [rcx]
0x18001b041  mov     rax, [rax]
0x18001b044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b049  mov     rax, cs:qword_18015DB40
0x18001b050  lea     rcx, qword_18015DB40
0x18001b057  mov     rax, [rax+8]
0x18001b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b060  mov     [rsp+0F68h+var_F48], r13; void **
0x18001b065  mov     r8, r15; unsigned int *
0x18001b068  lea     rdx, [rsp+0F68h+Uuid]; struct _GUID *
0x18001b070  mov     rcx, [rsp+0F68h+var_EA8]; this
0x18001b078  call    ?GetXaResource@CXaRmDirectoryBucket@@QEAAHPEAU_GUID@@PEAKAEBU2@PEAPEAX@Z; CXaRmDirectoryBucket::GetXaResource(_GUID *,ulong *,_GUID const &,void * *)
0x18001b07d  mov     rcx, [rsp+0F68h+var_EA8]
0x18001b085  add     rcx, 18h
0x18001b089  mov     rax, [rcx]
0x18001b08c  mov     rax, [rax+8]
0x18001b090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b095  cmp     [r13+0], rdi
0x18001b099  jz      short loc_18001B114
0x18001b09b  movups  xmm0, xmmword ptr [rsp+0F68h+Uuid.Data1]
0x18001b0a3  movdqu  xmmword ptr [r14], xmm0
0x18001b0a8  lea     eax, [r12+1]
0x18001b0ad  jmp     loc_18001B4B8
0x18001b0b2  xor     r8d, r8d; dwFlags
0x18001b0b5  xor     edx, edx; hFile
0x18001b0b7  lea     rcx, [rsp+0F68h+LibFileName]; lpLibFileName
0x18001b0bf  call    cs:__imp_LoadLibraryExA
0x18001b0c5  mov     rbx, rax
0x18001b0c8  test    rax, rax
0x18001b0cb  jnz     short loc_18001B11E
0x18001b0cd  call    cs:__imp_GetLastError
0x18001b0d3  test    eax, eax
0x18001b0d5  jle     short loc_18001B0DF
0x18001b0d7  movzx   eax, ax
0x18001b0da  or      eax, 80070000h
0x18001b0df  mov     dword ptr [rsp+0F68h+var_F48], 141h; int
0x18001b0e7  lea     r9, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b0ee  lea     r8, [rsp+0F68h+ValueName]; char *
0x18001b0f6  mov     edx, eax; unsigned int
0x18001b0f8  call    ?XA_TRACE_WARNING@@YAXKKPEAD0H@Z; XA_TRACE_WARNING(ulong,ulong,char *,char *,int)
0x18001b0fd  mov     rax, cs:qword_18015DB40
0x18001b104  lea     rcx, qword_18015DB40
0x18001b10b  mov     rax, [rax+8]
0x18001b10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b114  mov     eax, 80000000h
0x18001b119  jmp     loc_18001B4B8
0x18001b11e  lea     rdx, aGetxaswitch; "GetXaSwitch"
0x18001b125  mov     rcx, rbx; hModule
0x18001b128  call    cs:__imp_GetProcAddress
0x18001b12e  test    rax, rax
0x18001b131  jnz     short loc_18001B158
0x18001b133  call    cs:__imp_GetLastError
0x18001b139  test    eax, eax
0x18001b13b  jle     short loc_18001B145
0x18001b13d  movzx   eax, ax
0x18001b140  or      eax, 80070000h
0x18001b145  mov     r9d, eax; unsigned int
0x18001b148  call    ?XA_TRACE_WARNING@@YAXKPEADHKH@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,int)
0x18001b14d  mov     rcx, rbx; hLibModule
0x18001b150  call    cs:__imp_FreeLibrary
0x18001b156  jmp     short loc_18001B0FD
0x18001b158  lea     rdx, [rsp+0F68h+var_F10]
0x18001b15d  mov     ecx, 1
0x18001b162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b167  nop
0x18001b168  test    eax, eax
0x18001b16a  jz      short loc_18001B195
0x18001b16c  lea     rcx, [rsp+0F68h+LibFileName]
0x18001b174  mov     [rsp+0F68h+var_F48], rcx; char *
0x18001b179  mov     r9d, eax; unsigned int
0x18001b17c  mov     r8d, 16Ch; int
0x18001b182  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b189  mov     ecx, 8000D04Fh; unsigned int
0x18001b18e  call    ?XA_TRACE_WARNING@@YAXKPEADHK0H@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,char *,int)
0x18001b193  jmp     short loc_18001B14D
0x18001b195  xor     edx, edx; dwFlags
0x18001b197  mov     r8d, 668h; dwBytes
0x18001b19d  mov     rcx, cs:?g_CXaSynch_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x18001b1a4  call    cs:__imp_HeapAlloc
0x18001b1aa  mov     qword ptr [rsp+0F68h+Status], rax
0x18001b1af  test    rax, rax
0x18001b1b2  jz      short loc_18001B1BF
0x18001b1b4  mov     rcx, rax; this
0x18001b1b7  call    ??0CXaSynch@@QEAA@XZ; CXaSynch::CXaSynch(void)
0x18001b1bc  mov     rdi, rax
0x18001b1bf  test    rdi, rdi
0x18001b1c2  jnz     short loc_18001B1FF
0x18001b1c4  mov     rax, cs:qword_18015DB40
0x18001b1cb  lea     rcx, qword_18015DB40
0x18001b1d2  mov     rax, [rax+8]
0x18001b1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1db  mov     r9d, 0C000110Bh; unsigned int
0x18001b1e1  mov     r8d, 189h; int
0x18001b1e7  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b1ee  lea     rcx, aCxasynch; "CXaSynch"
0x18001b1f5  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x18001b1fa  jmp     loc_18001B114
0x18001b1ff  test    r12d, r12d
0x18001b202  jnz     loc_18001B2CD
0x18001b208  mov     esi, [rsp+0F68h+arg_30]
0x18001b20f  cmp     esi, 1
0x18001b212  jnz     short loc_18001B223
0x18001b214  movups  xmm0, xmmword ptr [r14]
0x18001b218  movdqu  xmmword ptr [rsp+0F68h+Uuid.Data1], xmm0
0x18001b221  jmp     short loc_18001B231
0x18001b223  lea     rcx, [rsp+0F68h+Uuid]; Uuid
0x18001b22b  call    cs:__imp_UuidCreate
0x18001b231  xor     r12d, r12d
0x18001b234  mov     [rsp+0F68h+Status], r12d
0x18001b239  mov     ebx, cs:?g_XaDirectory@@3VCXaRmDirectory@@A; CXaRmDirectory g_XaDirectory
0x18001b23f  lea     rdx, [rsp+0F68h+Status]; Status
0x18001b244  lea     rcx, [rsp+0F68h+Uuid]; Uuid
0x18001b24c  call    cs:__imp_UuidHash
0x18001b252  movzx   eax, ax
0x18001b255  xor     edx, edx
0x18001b257  div     ebx
0x18001b259  lea     rax, [rdx+rdx*4]
0x18001b25d  shl     rax, 4
0x18001b261  add     rax, cs:qword_18015DB38
0x18001b268  mov     [rsp+0F68h+var_EA8], rax
0x18001b270  mov     dword ptr [rsp+0F68h+var_EA8+8], 1
0x18001b27b  movups  xmm6, xmmword ptr [rsp+0F68h+Uuid.Data1]
0x18001b283  movups  xmm7, xmmword ptr [rsp+0F68h+var_EA8]
0x18001b28b  mov     rdx, [rsp+0F68h+var_F08]
0x18001b290  lea     rcx, [rsp+0F68h+var_E98]
0x18001b298  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18001b29d  nop
0x18001b29e  lea     rdx, [rsp+0F68h+var_E98]
0x18001b2a6  lea     rcx, qword_18015DB78
0x18001b2ad  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U_MAP_ELEMENT@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$throwing_allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U_MAP_ELEMENT@@@std@@@@@std@@QEAAAEAU_MAP_ELEMENT@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,_MAP_ELEMENT,std::less<std::string>,throwing_allocator<std::pair<std::string,_MAP_ELEMENT>>>::operator[](std::string &&)
0x18001b2b2  movups  xmmword ptr [rax], xmm6
0x18001b2b5  movups  xmmword ptr [rax+10h], xmm7
0x18001b2b9  xor     r8d, r8d
0x18001b2bc  mov     dl, 1
0x18001b2be  lea     rcx, [rsp+0F68h+var_E98]
0x18001b2c6  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18001b2cb  jmp     short loc_18001B2DE
0x18001b2cd  mov     dword ptr [rsi+58h], 1
0x18001b2d4  mov     esi, [rsp+0F68h+arg_30]
0x18001b2db  xor     r12d, r12d
0x18001b2de  mov     eax, 1
0x18001b2e3  lock xadd cs:?m_cRmId@CXaRmDirectory@@0KA, eax; ulong CXaRmDirectory::m_cRmId
0x18001b2eb  inc     eax
0x18001b2ed  mov     [r15], eax
0x18001b2f0  test    esi, esi
0x18001b2f2  jnz     short loc_18001B301
0x18001b2f4  movups  xmm0, xmmword ptr [rsp+0F68h+Uuid.Data1]
0x18001b2fc  movdqu  xmmword ptr [r14], xmm0
0x18001b301  lea     rax, ??_7?$UTStaticList2@PEAVCXaOpenState@@@@6B@; const UTStaticList2<CXaOpenState *>::`vftable'
0x18001b308  mov     [rsp+0F68h+var_EF8], rax
0x18001b30d  mov     [rsp+0F68h+var_EF0], r12d
0x18001b312  xorps   xmm0, xmm0
0x18001b315  movdqu  [rsp+0F68h+var_EE8], xmm0
0x18001b31e  mov     [rsp+0F68h+var_ED8], rax
0x18001b326  mov     [rsp+0F68h+var_ED0], r12d
0x18001b32e  movdqu  [rsp+0F68h+var_EC8], xmm0
0x18001b337  lea     r8, [rsp+0F68h+var_ED8]
0x18001b33f  lea     rdx, [rsp+0F68h+var_EF8]
0x18001b344  mov     ecx, [r15]
0x18001b347  call    ?AllocateXaOpenStateElements@CTaskManager@@SAHIPEAV?$UTStaticList2@PEAVCXaOpenState@@@@0@Z; CTaskManager::AllocateXaOpenStateElements(uint,UTStaticList2<CXaOpenState *> *,UTStaticList2<CXaOpenState *> *)
0x18001b34c  test    eax, eax
0x18001b34e  jnz     short loc_18001B38C
0x18001b350  mov     rax, cs:qword_18015DB40
0x18001b357  lea     rcx, qword_18015DB40
0x18001b35e  mov     rax, [rax+8]
0x18001b362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b367  mov     r9d, 0C000110Bh; unsigned int
0x18001b36d  mov     r8d, 1B9h; int
0x18001b373  lea     rdx, aComComplusDtcD_92; "com\\complus\\dtc\\dtc\\xatm\\src\\xarm"...
0x18001b37a  lea     rcx, aCxaopenstate; "CXaOpenState"
0x18001b381  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x18001b386  nop
0x18001b387  jmp     loc_18001B114
0x18001b38c  mov     rbx, [rsp+0F68h+var_F00]
0x18001b391  mov     rax, [rbx]
0x18001b394  mov     rcx, rbx
0x18001b397  mov     rax, [rax+8]
0x18001b39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3a0  mov     rax, [rdi]
0x18001b3a3  mov     [rsp+0F68h+var_F28], r13
0x18001b3a8  mov     [rsp+0F68h+var_F30], r15
0x18001b3ad  mov     [rsp+0F68h+var_F38], r14
0x18001b3b2  mov     [rsp+0F68h+var_F40], r12d
0x18001b3b7  mov     rcx, [rsp+0F68h+var_F10]
0x18001b3bc  mov     [rsp+0F68h+var_F48], rcx
0x18001b3c1  lea     r9, [rsp+0F68h+ValueName]
0x18001b3c9  lea     r8, [rsp+0F68h+var_C68]
0x18001b3d1  mov     rdx, rbx
0x18001b3d4  mov     rcx, rdi
0x18001b3d7  mov     rax, [rax+18h]
0x18001b3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3e0  lea     rcx, stru_180153898; lpCriticalSection
0x18001b3e7  call    cs:__imp_EnterCriticalSection
0x18001b3ed  mov     qword ptr [rsp+0F68h+Status], r12
0x18001b3f2  lea     rdx, [rsp+0F68h+Status]
0x18001b3f7  lea     rcx, [rsp+0F68h+var_EF8]
0x18001b3fc  call    ?RemoveLast@?$UTStaticList2@PEAVCSuperiorConnLink@@@@UEAAHPEAPEAV?$UTStaticLink2@PEAVCSuperiorConnLink@@@@@Z; UTStaticList2<CSuperiorConnLink *>::RemoveLast(UTStaticLink2<CSuperiorConnLink *> * *)
0x18001b401  test    eax, eax
0x18001b403  jz      short loc_18001B437
0x18001b405  lea     rbx, [rdi+1C8h]
0x18001b40c  mov     rax, [rbx]
0x18001b40f  mov     rdx, qword ptr [rsp+0F68h+Status]
0x18001b414  mov     rdx, [rdx+8]
0x18001b418  mov     rcx, rbx
0x18001b41b  mov     rax, [rax+18h]
0x18001b41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b424  lea     rdx, [rsp+0F68h+Status]
0x18001b429  lea     rcx, [rsp+0F68h+var_EF8]
0x18001b42e  call    ?RemoveLast@?$UTStaticList2@PEAVCSuperiorConnLink@@@@UEAAHPEAPEAV?$UTStaticLink2@PEAVCSuperiorConnLink@@@@@Z; UTStaticList2<CSuperiorConnLink *>::RemoveLast(UTStaticLink2<CSuperiorConnLink *> * *)
0x18001b433  test    eax, eax
0x18001b435  jnz     short loc_18001B40C
0x18001b437  lea     rcx, [rsp+0F68h+var_ED8]
  ... truncated ...
```
