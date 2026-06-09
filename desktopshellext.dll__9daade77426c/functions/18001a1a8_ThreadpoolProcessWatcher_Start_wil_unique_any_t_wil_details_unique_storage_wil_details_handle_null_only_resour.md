# ThreadpoolProcessWatcher::Start(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::function<void (void)> &&,_FILETIME *)

- ea: `0x18001a1a8`
- end: `0x18001a2ba`
- name: `?Start@ThreadpoolProcessWatcher@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180013a30`

## callees

- `0x180008390`
- `0x180011da0`
- `0x18001a18c`
- `0x18001a1a8`
- `0x18001a33c`
- `0x18001a510`
- `0x18002d848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a1d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a299`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a299`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001a287`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001a287`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001a24e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001a24e`

## string_xrefs

- `0x18001a1e9`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`
- `0x18001a26e`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ThreadpoolProcessWatcher::Start(RTL_SRWLOCK *a1, HANDLE *a2, __int64 a3)
{
  RTL_SRWLOCK *v6; // rbp
  const char *v7; // r9
  _DWORD *Ptr; // rax
  volatile signed __int32 *v9; // rax
  PVOID v10; // rcx
  std::_Ref_count_base *v11; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v13; // r9
  struct _TP_WAIT *v14; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  if ( LOBYTE(a1[11].Ptr) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x54,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v7);
  Ptr = a1[13].Ptr;
  if ( !Ptr || !Ptr[2] )
  {
    v9 = (volatile signed __int32 *)a1[1].Ptr;
    if ( v9 )
    {
      v10 = a1->Ptr;
      _InterlockedIncrement(v9 + 3);
    }
    else
    {
      v10 = 0;
    }
    a1[12].Ptr = v10;
    v11 = (std::_Ref_count_base *)a1[13].Ptr;
    a1[13].Ptr = (PVOID)v9;
    if ( v11 )
      std::_Ref_count_base::_Decwref(v11);
  }
  std::function<void (void)>::operator=(&a1[3], a3);
  ThreadpoolWait = CreateThreadpoolWait(
                     _lambda_8b0b9dbd4459d626ffc8152be8328efc_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long>,
                     &a1[12],
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    &a1[14],
    ThreadpoolWait);
  v14 = (struct _TP_WAIT *)a1[14].Ptr;
  if ( !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x77,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v13);
  SetThreadpoolWait(v14, *a2, 0);
  LOBYTE(a1[11].Ptr) = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  fc::details::registry_store_lock::~registry_store_lock((fc::details::registry_store_lock *)a2);
}

```

## disassembly

```asm
0x18001a1a8  mov     rax, rsp
0x18001a1ab  mov     [rax+8], rbx
0x18001a1af  mov     [rax+18h], rbp
0x18001a1b3  mov     [rax+20h], r9
0x18001a1b7  mov     [rax+10h], rdx
0x18001a1bb  push    rsi
0x18001a1bc  push    rdi
0x18001a1bd  push    r14
0x18001a1bf  sub     rsp, 20h
0x18001a1c3  mov     rbx, r8
0x18001a1c6  mov     r14, rdx
0x18001a1c9  mov     rdi, rcx
0x18001a1cc  lea     rbp, [rcx+10h]
0x18001a1d0  mov     rcx, rbp; SRWLock
0x18001a1d3  call    cs:__imp_AcquireSRWLockExclusive
0x18001a1d9  mov     [rsp+38h+arg_18], rbp
0x18001a1de  mov     rcx, [rsp+38h]; this
0x18001a1e3  cmp     byte ptr [rdi+58h], 0
0x18001a1e7  jz      short loc_18001A1FB
0x18001a1e9  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x18001a1f0  mov     edx, 54h ; 'T'; void *
0x18001a1f5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001a1fb  mov     rax, [rdi+68h]
0x18001a1ff  test    rax, rax
0x18001a202  jz      short loc_18001A20A
0x18001a204  cmp     dword ptr [rax+8], 0
0x18001a208  jnz     short loc_18001A234
0x18001a20a  mov     rax, [rdi+8]
0x18001a20e  test    rax, rax
0x18001a211  jz      short loc_18001A21C
0x18001a213  mov     rcx, [rdi]
0x18001a216  lock inc dword ptr [rax+0Ch]
0x18001a21a  jmp     short loc_18001A21E
0x18001a21c  xor     ecx, ecx
0x18001a21e  mov     [rdi+60h], rcx
0x18001a222  mov     rcx, [rdi+68h]; this
0x18001a226  mov     [rdi+68h], rax
0x18001a22a  test    rcx, rcx
0x18001a22d  jz      short loc_18001A234
0x18001a22f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001a234  lea     rcx, [rdi+18h]
0x18001a238  mov     rdx, rbx
0x18001a23b  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18001a240  xor     r8d, r8d; pcbe
0x18001a243  lea     rdx, [rdi+60h]; pv
0x18001a247  lea     rcx, ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001a24e  call    cs:__imp_CreateThreadpoolWait
0x18001a254  mov     rdx, rax
0x18001a257  lea     rcx, [rdi+70h]
0x18001a25b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18001a260  mov     rcx, [rdi+70h]; pwa
0x18001a264  mov     rax, [rsp+38h]
0x18001a269  test    rcx, rcx
0x18001a26c  jnz     short loc_18001A281
0x18001a26e  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x18001a275  lea     edx, [rcx+77h]; void *
0x18001a278  mov     rcx, rax; this
0x18001a27b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001a281  xor     r8d, r8d; pftTimeout
0x18001a284  mov     rdx, [r14]; h
0x18001a287  call    cs:__imp_SetThreadpoolWait
0x18001a28d  mov     byte ptr [rdi+58h], 1
0x18001a291  test    rbp, rbp
0x18001a294  jz      short loc_18001A2A0
0x18001a296  mov     rcx, rbp; SRWLock
0x18001a299  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a29f  nop
0x18001a2a0  mov     rcx, r14; this
0x18001a2a3  mov     rbx, [rsp+38h+arg_0]
0x18001a2a8  mov     rbp, [rsp+38h+arg_10]
0x18001a2ad  add     rsp, 20h
0x18001a2b1  pop     r14
0x18001a2b3  pop     rdi
0x18001a2b4  pop     rsi
0x18001a2b5  jmp     ??1registry_store_lock@details@fc@@QEAA@XZ; fc::details::registry_store_lock::~registry_store_lock(void)
```
