# DesktopShellHostExtensionsTelemetry::TerminateShell::StartActivity(void)

- ea: `0x1800394e0`
- end: `0x1800395ff`
- name: `?StartActivity@TerminateShell@DesktopShellHostExtensionsTelemetry@@QEAAXXZ`
- size: `287`
- prototype: `void __fastcall(DesktopShellHostExtensionsTelemetry::TerminateShell *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180017f00`

## callees

- `0x180001008`
- `0x18000b8f0`
- `0x18000cad8`
- `0x180012bf0`
- `0x1800250b4`
- `0x1800394e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039548`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039548`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039577`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039529`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039529`

## pseudocode

```c
void __fastcall DesktopShellHostExtensionsTelemetry::TerminateShell::StartActivity(
        DesktopShellHostExtensionsTelemetry::TerminateShell *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  int v5; // ebx
  __int64 v6; // r8
  int v7; // r9d
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = DesktopShellHostExtensionsLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = DesktopShellHostExtensionsLogging::Provider();
  v5 = (int)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_180099BE1,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&SRWLock);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((DesktopShellHostExtensionsTelemetry::TerminateShell *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800394e0  mov     [rsp+arg_10], rbx
0x1800394e5  push    rdi
0x1800394e6  sub     rsp, 30h
0x1800394ea  mov     rdi, rcx
0x1800394ed  lea     rdx, [rsp+38h+SRWLock]
0x1800394f2  call    ?LockExclusive@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800394f7  mov     rbx, [rdi+110h]
0x1800394fe  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x180039503  mov     edx, [rax]
0x180039505  cmp     edx, 5
0x180039508  jbe     short loc_180039531
0x18003950a  mov     rdx, 200000000000h
0x180039514  mov     rcx, rax
0x180039517  call    _tlgKeywordOn
0x18003951c  test    al, al
0x18003951e  jz      short loc_180039531
0x180039520  lea     rdx, [rbx+8]; ActivityId
0x180039524  mov     ecx, 3; ControlCode
0x180039529  call    cs:__imp_EventActivityIdControl
0x18003952f  jmp     short loc_180039538
0x180039531  xorps   xmm0, xmm0
0x180039534  movups  xmmword ptr [rbx+8], xmm0
0x180039538  mov     dword ptr [rbx], 1
0x18003953e  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180039543  test    rcx, rcx
0x180039546  jz      short loc_18003954E
0x180039548  call    cs:__imp_ReleaseSRWLockExclusive
0x18003954e  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x180039553  mov     rbx, rax
0x180039556  mov     ecx, [rax]
0x180039558  cmp     ecx, 5
0x18003955b  jbe     loc_1800395E1
0x180039561  mov     rdx, 200000000000h
0x18003956b  mov     rcx, rax
0x18003956e  call    _tlgKeywordOn
0x180039573  test    al, al
0x180039575  jz      short loc_1800395E1
0x180039577  call    cs:__imp_GetCurrentThreadId
0x18003957d  mov     dword ptr [rsp+38h+SRWLock], eax
0x180039581  mov     [rsp+38h+arg_8], 0
0x18003958a  mov     r8, [rdi+110h]
0x180039591  cmp     byte ptr [r8+4], 0
0x180039596  jz      short loc_1800395B7
0x180039598  lea     r9, [r8+18h]
0x18003959c  cmp     dword ptr [r9], 0
0x1800395a0  jnz     short loc_1800395BA
0x1800395a2  cmp     dword ptr [r9+4], 0
0x1800395a7  jnz     short loc_1800395BA
0x1800395a9  cmp     dword ptr [r9+8], 0
0x1800395ae  jnz     short loc_1800395BA
0x1800395b0  cmp     dword ptr [r9+0Ch], 0
0x1800395b5  jnz     short loc_1800395BA
0x1800395b7  xor     r9d, r9d
0x1800395ba  add     r8, 8
0x1800395be  lea     rax, [rsp+38h+SRWLock]
0x1800395c3  mov     [rsp+38h+var_10], rax
0x1800395c8  lea     rax, [rsp+38h+arg_8]
0x1800395cd  mov     [rsp+38h+var_18], rax
0x1800395d2  lea     rdx, byte_180099BE1
0x1800395d9  mov     rcx, rbx
0x1800395dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800395e1  lea     rcx, [rdi+120h]; this
0x1800395e8  cmp     dword ptr [rcx+18h], 0
0x1800395ec  jnz     short loc_1800395F4
0x1800395ee  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800395f3  nop
0x1800395f4  mov     rbx, [rsp+38h+arg_10]
0x1800395f9  add     rsp, 30h
0x1800395fd  pop     rdi
0x1800395fe  retn
```
