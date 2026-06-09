# FATNotificationSource::StartChangeMonitor(wchar_t const *,TagCrawlTypes)

- ea: `0x18021d550`
- end: `0x18021d705`
- name: `?StartChangeMonitor@FATNotificationSource@@UEAAJPEB_WW4TagCrawlTypes@@@Z`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18000bf8c`
- `0x180022710`
- `0x18002751c`
- `0x18002bf00`
- `0x1800e2374`
- `0x1801160a4`
- `0x1801161b0`
- `0x18021d550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18021d5e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18021d5e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021d57b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021d5b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021d57b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021d5b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18021d680`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18021d680`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021d63f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021d63f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FATNotificationSource::StartChangeMonitor(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v7; // edi
  HANDLE EventW; // rax
  unsigned int Error; // eax
  HANDLE FileW; // rax
  unsigned int v11; // eax
  PTP_IO ThreadpoolIo; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-48h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-48h]
  _QWORD v18[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  v20 = a1 + 66112;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 66112));
  if ( *(_BYTE *)(a1 + 66160) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v20);
    return 2147943515LL;
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v20);
    v18[0] = a1 + 66064;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 66064));
    v7 = 0;
    try
    {
      CLMString::operator=(a1 + 65592, a2);
      ETWLog::Log(L"CFatNotify - Starting change monitor: %s", *(_QWORD *)(a1 + 65600));
      EventW = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)(a1 + 66040) = EventW;
      if ( !EventW )
      {
        Error = ResultFromLastError();
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx",
          (const char *)Error,
          dwCreationDisposition);
      }
      FileW = CreateFileW(a2, 1u, 7u, 0, 3u, 0x42000000u, 0);
      *(_QWORD *)(a1 + 66008) = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v11 = ResultFromLastError();
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx",
          (const char *)v11,
          dwCreationDispositiona);
      }
      ThreadpoolIo = CreateThreadpoolIo(FileW, TPReadDirectoryChangesWCallback, (PVOID)a1, 0);
      *(_QWORD *)(a1 + 66048) = ThreadpoolIo;
      if ( !ThreadpoolIo )
      {
        v13 = ResultFromLastError();
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx",
          (const char *)v13,
          dwCreationDispositiona);
      }
      *(_BYTE *)(a1 + 66056) = 1;
      FATNotificationSource::ReadDirectoryChanges((FATNotificationSource *)a1);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        276,
        "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx");
    }
    if ( a3 )
    {
      LOBYTE(v14) = 1;
      v15 = FATNotificationSource::InitiateCrawl(a1, v14, a3);
      v7 = v15;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v18);
    return v7;
  }
}

```

## disassembly

```asm
0x18021d550  mov     rax, rsp
0x18021d553  mov     [rax+10h], rbx
0x18021d557  mov     [rax+18h], r8d
0x18021d55b  mov     [rax+8], rcx
0x18021d55f  push    rsi
0x18021d560  push    rdi
0x18021d561  push    r14
0x18021d563  sub     rsp, 50h
0x18021d567  mov     esi, r8d
0x18021d56a  mov     r14, rdx
0x18021d56d  mov     rbx, rcx
0x18021d570  add     rcx, 10240h; lpCriticalSection
0x18021d577  mov     [rax+20h], rcx
0x18021d57b  call    cs:__imp_EnterCriticalSection
0x18021d581  lea     rcx, [rsp+68h+arg_18]
0x18021d589  cmp     byte ptr [rbx+10270h], 0
0x18021d590  jz      short loc_18021D5A1
0x18021d592  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18021d597  mov     eax, 8007045Bh
0x18021d59c  jmp     loc_18021D6F7
0x18021d5a1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18021d5a6  lea     rcx, [rbx+10210h]; lpCriticalSection
0x18021d5ad  mov     [rsp+68h+var_28], rcx
0x18021d5b2  call    cs:__imp_EnterCriticalSection
0x18021d5b8  nop
0x18021d5b9  xor     edi, edi
0x18021d5bb  lea     rcx, [rbx+10038h]
0x18021d5c2  mov     rdx, r14
0x18021d5c5  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18021d5ca  mov     rdx, [rbx+10040h]
0x18021d5d1  lea     rcx, aCfatnotifyStar; "CFatNotify - Starting change monitor: %"...
0x18021d5d8  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18021d5dd  xor     r9d, r9d; lpName
0x18021d5e0  xor     r8d, r8d; bInitialState
0x18021d5e3  lea     edx, [rdi+1]; bManualReset
0x18021d5e6  xor     ecx, ecx; lpEventAttributes
0x18021d5e8  call    cs:__imp_CreateEventW
0x18021d5ee  mov     [rbx+101F8h], rax
0x18021d5f5  test    rax, rax
0x18021d5f8  jnz     short loc_18021D618
0x18021d5fa  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18021d5ff  mov     rcx, [rsp+68h]; this
0x18021d604  mov     r9d, eax; char *
0x18021d607  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18021d60e  mov     edx, 0F6h; void *
0x18021d613  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18021d618  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18021d621  mov     [rsp+68h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x18021d629  mov     [rsp+68h+dwCreationDisposition], 3; int
0x18021d631  xor     r9d, r9d; lpSecurityAttributes
0x18021d634  lea     edx, [r9+1]; dwDesiredAccess
0x18021d638  lea     r8d, [r9+7]; dwShareMode
0x18021d63c  mov     rcx, r14; lpFileName
0x18021d63f  call    cs:__imp_CreateFileW
0x18021d645  mov     [rbx+101D8h], rax
0x18021d64c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18021d650  jnz     short loc_18021D670
0x18021d652  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18021d657  mov     rcx, [rsp+68h]; this
0x18021d65c  mov     r9d, eax; char *
0x18021d65f  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18021d666  mov     edx, 104h; void *
0x18021d66b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18021d670  xor     r9d, r9d; pcbe
0x18021d673  mov     r8, rbx; pv
0x18021d676  lea     rdx, ?TPReadDirectoryChangesWCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18021d67d  mov     rcx, rax; fl
0x18021d680  call    cs:__imp_CreateThreadpoolIo
0x18021d686  mov     [rbx+10200h], rax
0x18021d68d  test    rax, rax
0x18021d690  jnz     short loc_18021D6B0
0x18021d692  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18021d697  mov     rcx, [rsp+68h]; this
0x18021d69c  mov     r9d, eax; char *
0x18021d69f  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18021d6a6  mov     edx, 10Bh; void *
0x18021d6ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18021d6b0  mov     byte ptr [rbx+10208h], 1
0x18021d6b7  mov     rcx, rbx; this
0x18021d6ba  call    ?ReadDirectoryChanges@FATNotificationSource@@AEAAXXZ; FATNotificationSource::ReadDirectoryChanges(void)
0x18021d6bf  nop
0x18021d6c0  jmp     short loc_18021D6D5
0x18021d6c2  mov     rbx, [rsp+68h+arg_0]
0x18021d6c7  mov     esi, [rsp+68h+arg_10]
0x18021d6ce  mov     edi, dword ptr [rsp+68h+arg_18]
0x18021d6d5  test    esi, esi
0x18021d6d7  jz      short loc_18021D6EB
0x18021d6d9  mov     r8d, esi
0x18021d6dc  mov     dl, 1
0x18021d6de  mov     rcx, rbx
0x18021d6e1  call    ?InitiateCrawl@FATNotificationSource@@AEAAJ_NW4TagCrawlTypes@@@Z; FATNotificationSource::InitiateCrawl(bool,TagCrawlTypes)
0x18021d6e6  test    edi, edi
0x18021d6e8  cmovns  edi, eax
0x18021d6eb  lea     rcx, [rsp+68h+var_28]
0x18021d6f0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18021d6f5  mov     eax, edi
0x18021d6f7  mov     rbx, [rsp+68h+arg_8]
0x18021d6fc  add     rsp, 50h
0x18021d700  pop     r14
0x18021d702  pop     rdi
0x18021d703  pop     rsi
0x18021d704  retn
```
