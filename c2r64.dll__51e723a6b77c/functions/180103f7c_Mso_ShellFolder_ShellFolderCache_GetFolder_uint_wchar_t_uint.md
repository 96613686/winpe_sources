# Mso::ShellFolder::ShellFolderCache::GetFolder(uint,wchar_t *,uint)

- ea: `0x180103f7c`
- end: `0x1801040b4`
- name: `?GetFolder@ShellFolderCache@ShellFolder@Mso@@QEAA?AW4CopyStatus@123@IPEA_WI@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801040b4`

## callees

- `0x180011340`
- `0x180011b70`
- `0x180030a94`
- `0x180035fa0`
- `0x180035ff4`
- `0x18009d454`
- `0x18009f990`
- `0x180103f7c`
- `0x1801041e0`
- `0x180104250`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x180103fc2`
- `KERNEL32!CreateEventExW` at `0x180103fc2`
- `KERNEL32!WaitForSingleObject` at `0x18010400b`
- `KERNEL32!WaitForSingleObject` at `0x18010400b`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180104085`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180104085`

## pseudocode

```c
__int64 __fastcall Mso::ShellFolder::ShellFolderCache::GetFolder(HANDLE *a1, int a2, wchar_t *a3)
{
  unsigned int v5; // edi
  HANDLE *v6; // r14
  HANDLE Event; // rbx
  __int64 v8; // rcx
  HKEY *v9; // rax
  bool v10; // r9
  __int64 v12; // rax
  char *v13; // r8
  const wchar_t *v14; // r8
  _BYTE v15[16]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16[5]; // [rsp+30h] [rbp-28h] BYREF
  int v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = a2;
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(
    v15,
    a1 + 13);
  v5 = 0;
  *a3 = 0;
  v6 = a1 + 12;
  if ( !a1[12] )
  {
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(a1 + 12);
    *v6 = Event;
    if ( Event )
    {
      v9 = (HKEY *)Mso::Registry::Key::operator&(a1 + 8);
      if ( !(unsigned int)MsoRegOpenKeyEx2((const struct _msoreg *)&vmsoridCUExplorer, 0, v9, v10) )
        Mso::ShellFolder::ShellFolderCache::RegisterForChangeNotification((Mso::ShellFolder::ShellFolderCache *)a1);
    }
    if ( !*v6 )
      goto LABEL_8;
  }
  if ( !WaitForSingleObject(*v6, 0) )
  {
    std::_Hash<std::_Umap_traits<unsigned int,std::wstring,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::clear(a1);
    Mso::ShellFolder::ShellFolderCache::RegisterForChangeNotification((Mso::ShellFolder::ShellFolderCache *)a1);
    Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v15);
    return 1;
  }
  else
  {
LABEL_8:
    v12 = std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>::operator()<long>(v8, (__int64)&v17);
    v13 = (char *)std::_Hash<std::_Umap_traits<enum Mso::Http::RequestSettings,Mso::TCntPtr<Mso::IRefCounted>,std::_Uhash_compare<enum Mso::Http::RequestSettings,std::hash<enum Mso::Http::RequestSettings>,std::equal_to<enum Mso::Http::RequestSettings>>,std::allocator<std::pair<enum Mso::Http::RequestSettings const,Mso::TCntPtr<Mso::IRefCounted>>>,0>>::_Find_last<enum Mso::Http::RequestSettings>(
                    a1,
                    v16,
                    &v17,
                    v12)[1];
    if ( !v13 )
      v13 = (char *)a1[1];
    if ( v13 == a1[1] )
    {
      v5 = 1;
    }
    else
    {
      v14 = (const wchar_t *)(v13 + 24);
      if ( *((_QWORD *)v14 + 3) > 7u )
        v14 = *(const wchar_t **)v14;
      if ( wcscpy_s(a3, 0x824u, v14) )
        v5 = 2;
    }
    Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v15);
    return v5;
  }
}

```

## disassembly

```asm
0x180103f7c  mov     rax, rsp
0x180103f7f  mov     [rax+8], rbx
0x180103f83  mov     [rax+18h], rsi
0x180103f87  mov     [rax+10h], edx
0x180103f8a  push    rdi
0x180103f8b  push    r14
0x180103f8d  push    r15
0x180103f8f  sub     rsp, 40h
0x180103f93  mov     r15, r8
0x180103f96  mov     rsi, rcx
0x180103f99  lea     rdx, [rcx+68h]
0x180103f9d  lea     rcx, [rax-38h]
0x180103fa1  call    ??0?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@AEAV?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> &)
0x180103fa6  xor     edi, edi
0x180103fa8  mov     [r15], di
0x180103fac  lea     r14, [rsi+60h]
0x180103fb0  cmp     [r14], rdi
0x180103fb3  jnz     short loc_180104006
0x180103fb5  mov     r9d, 1F0003h; dwDesiredAccess
0x180103fbb  xor     r8d, r8d; dwFlags
0x180103fbe  xor     edx, edx; lpName
0x180103fc0  xor     ecx, ecx; lpEventAttributes
0x180103fc2  call    cs:__imp_CreateEventExW
0x180103fc8  mov     rbx, rax
0x180103fcb  mov     rcx, r14
0x180103fce  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x180103fd3  mov     [r14], rbx
0x180103fd6  test    rbx, rbx
0x180103fd9  jz      short loc_180104001
0x180103fdb  lea     rcx, [rsi+40h]
0x180103fdf  call    ??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ; Mso::Registry::Key::operator&(void)
0x180103fe4  mov     r8, rax; HKEY *
0x180103fe7  xor     edx, edx; unsigned int
0x180103fe9  lea     rcx, ?vmsoridCUExplorer@@3U_msoreg@@B; struct _msoreg *
0x180103ff0  call    ?MsoRegOpenKeyEx2@@YAJPEBU_msoreg@@KPEAPEAUHKEY__@@_N@Z; MsoRegOpenKeyEx2(_msoreg const *,ulong,HKEY__ * *,bool)
0x180103ff5  test    eax, eax
0x180103ff7  jnz     short loc_180104001
0x180103ff9  mov     rcx, rsi; this
0x180103ffc  call    ?RegisterForChangeNotification@ShellFolderCache@ShellFolder@Mso@@AEAAXXZ; Mso::ShellFolder::ShellFolderCache::RegisterForChangeNotification(void)
0x180104001  cmp     [r14], rdi
0x180104004  jz      short loc_180104036
0x180104006  xor     edx, edx; dwMilliseconds
0x180104008  mov     rcx, [r14]; hHandle
0x18010400b  call    cs:__imp_WaitForSingleObject
0x180104011  test    eax, eax
0x180104013  jnz     short loc_180104036
0x180104015  mov     rcx, rsi
0x180104018  call    ?clear@?$_Hash@V?$_Umap_traits@IV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,std::wstring,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::wstring>>,0>>::clear(void)
0x18010401d  mov     rcx, rsi; this
0x180104020  call    ?RegisterForChangeNotification@ShellFolderCache@ShellFolder@Mso@@AEAAXXZ; Mso::ShellFolder::ShellFolderCache::RegisterForChangeNotification(void)
0x180104025  lea     rcx, [rsp+58h+var_38]
0x18010402a  call    ??1?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x18010402f  mov     eax, 1
0x180104034  jmp     short loc_1801040A0
0x180104036  lea     rdx, [rsp+58h+arg_8]
0x18010403b  call    ??$?RJ@?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@QEBA_KAEBJ@Z; std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>::operator()<long>(long const &)
0x180104040  mov     r9, rax
0x180104043  lea     r8, [rsp+58h+arg_8]
0x180104048  lea     rdx, [rsp+58h+var_28]
0x18010404d  mov     rcx, rsi
0x180104050  call    ??$_Find_last@W4RequestSettings@Http@Mso@@@?$_Hash@V?$_Umap_traits@W4RequestSettings@Http@Mso@@V?$TCntPtr@UIRefCounted@Mso@@@3@V?$_Uhash_compare@W4RequestSettings@Http@Mso@@U?$hash@W4RequestSettings@Http@Mso@@@std@@U?$equal_to@W4RequestSettings@Http@Mso@@@5@@std@@V?$allocator@U?$pair@$$CBW4RequestSettings@Http@Mso@@V?$TCntPtr@UIRefCounted@Mso@@@3@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBW4RequestSettings@Http@Mso@@V?$TCntPtr@UIRefCounted@Mso@@@3@@std@@PEAX@std@@@1@AEBW4RequestSettings@Http@Mso@@_K@Z; std::_Hash<std::_Umap_traits<Mso::Http::RequestSettings,Mso::TCntPtr<Mso::IRefCounted>,std::_Uhash_compare<Mso::Http::RequestSettings,std::hash<Mso::Http::RequestSettings>,std::equal_to<Mso::Http::RequestSettings>>,std::allocator<std::pair<Mso::Http::RequestSettings const,Mso::TCntPtr<Mso::IRefCounted>>>,0>>::_Find_last<Mso::Http::RequestSettings>(Mso::Http::RequestSettings const &,unsigned __int64)
0x180104055  mov     r8, [rax+8]
0x180104059  test    r8, r8
0x18010405c  jnz     short loc_180104062
0x18010405e  mov     r8, [rsi+8]
0x180104062  cmp     r8, [rsi+8]
0x180104066  jnz     short loc_18010406F
0x180104068  mov     edi, 1
0x18010406d  jmp     short loc_180104094
0x18010406f  add     r8, 18h
0x180104073  cmp     qword ptr [r8+18h], 7
0x180104078  jbe     short loc_18010407D
0x18010407a  mov     r8, [r8]; Source
0x18010407d  mov     edx, 824h; SizeInWords
0x180104082  mov     rcx, r15; Destination
0x180104085  call    cs:__imp_wcscpy_s
0x18010408b  test    eax, eax
0x18010408d  jz      short loc_180104094
0x18010408f  mov     edi, 2
0x180104094  lea     rcx, [rsp+58h+var_38]
0x180104099  call    ??1?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x18010409e  mov     eax, edi
0x1801040a0  mov     rbx, [rsp+58h+arg_0]
0x1801040a5  mov     rsi, [rsp+58h+arg_10]
0x1801040aa  add     rsp, 40h
0x1801040ae  pop     r15
0x1801040b0  pop     r14
0x1801040b2  pop     rdi
0x1801040b3  retn
```
