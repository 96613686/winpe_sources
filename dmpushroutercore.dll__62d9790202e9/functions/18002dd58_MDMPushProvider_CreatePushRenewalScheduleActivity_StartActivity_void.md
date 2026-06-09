# MDMPushProvider::CreatePushRenewalScheduleActivity::StartActivity(void)

- ea: `0x18002dd58`
- end: `0x18002de94`
- name: `?StartActivity@CreatePushRenewalScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::CreatePushRenewalScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180029994`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002dd58`
- `0x18002dfe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ddde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ddde`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ddc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ddc5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002dda7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002dda7`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushRenewalScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushRenewalScheduleActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  const GUID *v5; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MDMPushProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = MDMPushProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = (const GUID *)(v4 + 24), !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_SRWLock = &SRWLock;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v3,
      (unsigned __int8 *)&unk_1800471C0,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MDMPushProvider::CreatePushRenewalScheduleActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002dd58  mov     [rsp-8+arg_8], rbx
0x18002dd5d  mov     [rsp-8+arg_10], rdi
0x18002dd62  push    rbp
0x18002dd63  lea     rbp, [rsp-57h]
0x18002dd68  sub     rsp, 90h
0x18002dd6f  mov     rax, cs:__security_cookie
0x18002dd76  xor     rax, rsp
0x18002dd79  mov     [rbp+57h+var_10], rax
0x18002dd7d  mov     rbx, rcx
0x18002dd80  lea     rdx, [rbp+57h+SRWLock]
0x18002dd84  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002dd89  mov     rdi, [rbx+110h]
0x18002dd90  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002dd95  mov     r8d, [rax]
0x18002dd98  cmp     r8d, 5
0x18002dd9c  jbe     short loc_18002DDAF
0x18002dd9e  lea     rdx, [rdi+8]; ActivityId
0x18002dda2  mov     ecx, 3; ControlCode
0x18002dda7  call    cs:__imp_EventActivityIdControl
0x18002ddad  jmp     short loc_18002DDB6
0x18002ddaf  xorps   xmm0, xmm0
0x18002ddb2  movups  xmmword ptr [rdi+8], xmm0
0x18002ddb6  mov     dword ptr [rdi], 1
0x18002ddbc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002ddc0  test    rcx, rcx
0x18002ddc3  jz      short loc_18002DDCB
0x18002ddc5  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ddcb  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002ddd0  mov     rdi, rax
0x18002ddd3  mov     ecx, [rax]
0x18002ddd5  cmp     ecx, 5
0x18002ddd8  jbe     loc_18002DE60
0x18002ddde  call    cs:__imp_GetCurrentThreadId
0x18002dde4  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002dde7  mov     [rbp+57h+var_58], 0
0x18002ddef  mov     r8, [rbx+110h]
0x18002ddf6  cmp     byte ptr [r8+4], 0
0x18002ddfb  jz      short loc_18002DE1C
0x18002ddfd  lea     r9, [r8+18h]
0x18002de01  cmp     dword ptr [r9], 0
0x18002de05  jnz     short loc_18002DE1F
0x18002de07  cmp     dword ptr [r9+4], 0
0x18002de0c  jnz     short loc_18002DE1F
0x18002de0e  cmp     dword ptr [r9+8], 0
0x18002de13  jnz     short loc_18002DE1F
0x18002de15  cmp     dword ptr [r9+0Ch], 0
0x18002de1a  jnz     short loc_18002DE1F
0x18002de1c  xor     r9d, r9d
0x18002de1f  lea     rax, [rbp+57h+SRWLock]
0x18002de23  mov     [rbp+57h+var_20], rax
0x18002de27  mov     ecx, 4
0x18002de2c  mov     [rbp+57h+var_18], rcx
0x18002de30  lea     rax, [rbp+57h+var_58]
0x18002de34  mov     [rbp+57h+var_30], rax
0x18002de38  mov     [rbp+57h+var_28], 8
0x18002de40  add     r8, 8
0x18002de44  lea     rax, [rbp+57h+var_50]
0x18002de48  mov     [rsp+90h+var_68], rax
0x18002de4d  mov     [rsp+90h+var_70], ecx
0x18002de51  lea     rdx, unk_1800471C0
0x18002de58  mov     rcx, rdi
0x18002de5b  call    _tlgWriteTransfer_EventWriteTransfer
0x18002de60  lea     rcx, [rbx+120h]; this
0x18002de67  cmp     dword ptr [rcx+18h], 0
0x18002de6b  jnz     short loc_18002DE73
0x18002de6d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002de72  nop
0x18002de73  mov     rcx, [rbp+57h+var_10]
0x18002de77  xor     rcx, rsp; StackCookie
0x18002de7a  call    __security_check_cookie
0x18002de7f  lea     r11, [rsp+90h+var_s0]
0x18002de87  mov     rbx, [r11+18h]
0x18002de8b  mov     rdi, [r11+20h]
0x18002de8f  mov     rsp, r11
0x18002de92  pop     rbp
0x18002de93  retn
```
