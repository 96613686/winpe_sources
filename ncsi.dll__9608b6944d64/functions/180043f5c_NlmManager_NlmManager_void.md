# NlmManager::~NlmManager(void)

- ea: `0x180043f5c`
- end: `0x180043ffe`
- name: `??1NlmManager@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(NlmManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006de20`

## callees

- `0x18002b84c`
- `0x18002cea4`
- `0x180043f5c`
- `0x180044004`
- `0x18004404c`
- `0x180047f78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043fd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043fd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043ff7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043f69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043f69`

## pseudocode

```c
void __fastcall NlmManager::~NlmManager(NlmManager *this)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  void *v5; // rdx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v7[5]; // [rsp+28h] [rbp-50h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)this);
  lpCriticalSection = (LPCRITICAL_SECTION)this;
  memset_0(v7, 0, 0x40u);
  v2 = v7[1];
  *(_OWORD *)((char *)this + 40) = v7[0];
  v3 = v7[2];
  *(_OWORD *)((char *)this + 56) = v2;
  v4 = v7[3];
  *(_OWORD *)((char *)this + 72) = v3;
  *(_OWORD *)((char *)this + 88) = v4;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    &lpCriticalSection,
    0);
  WcmCommon::ThreadPoolWorkQueue::Cancel((NlmManager *)((char *)this + 104));
  if ( NlmManager::s_destructEvent )
    wil::details::SetEvent(NlmManager::s_destructEvent, v5);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((NlmManager *)((char *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180043f5c  mov     [rsp+arg_8], rbx
0x180043f61  push    rdi
0x180043f62  sub     rsp, 70h
0x180043f66  mov     rbx, rcx
0x180043f69  call    cs:__imp_EnterCriticalSection
0x180043f6f  xor     edx, edx; Val
0x180043f71  mov     [rsp+78h+lpCriticalSection], rbx
0x180043f76  lea     rcx, [rsp+78h+var_50]; void *
0x180043f7b  lea     r8d, [rdx+40h]; Size
0x180043f7f  call    memset_0
0x180043f84  movups  xmm0, [rsp+78h+var_50]
0x180043f89  xor     edx, edx
0x180043f8b  lea     rcx, [rsp+78h+lpCriticalSection]
0x180043f90  movups  xmm1, [rsp+78h+var_40]
0x180043f95  movups  xmmword ptr [rbx+28h], xmm0
0x180043f99  movups  xmm0, [rsp+78h+var_30]
0x180043f9e  movups  xmmword ptr [rbx+38h], xmm1
0x180043fa2  movups  xmm1, [rsp+78h+var_20]
0x180043fa7  movups  xmmword ptr [rbx+48h], xmm0
0x180043fab  movups  xmmword ptr [rbx+58h], xmm1
0x180043faf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180043fb4  lea     rcx, [rbx+68h]; this
0x180043fb8  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x180043fbd  mov     rcx, cs:?s_destructEvent@NlmManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; this
0x180043fc4  test    rcx, rcx
0x180043fc7  jz      short loc_180043FCE
0x180043fc9  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180043fce  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180043fd3  test    rcx, rcx
0x180043fd6  jz      short loc_180043FDE
0x180043fd8  call    cs:__imp_LeaveCriticalSection
0x180043fde  lea     rcx, [rbx+68h]; this
0x180043fe2  call    ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
0x180043fe7  mov     rcx, rbx
0x180043fea  mov     rbx, [rsp+78h+arg_8]
0x180043ff2  add     rsp, 70h
0x180043ff6  pop     rdi
0x180043ff7  jmp     cs:__imp_DeleteCriticalSection
```
