# MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(void)

- ea: `0x18002dc14`
- end: `0x18002dd50`
- name: `?StartActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180027394`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002dc14`
- `0x18002dfe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dc9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dc9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dc81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dc81`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002dc63`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002dc63`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
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

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
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
      (unsigned __int8 *)byte_180047AF3,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MDMPushProvider::CreatePushLaunchScheduleActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002dc14  mov     [rsp-8+arg_8], rbx
0x18002dc19  mov     [rsp-8+arg_10], rdi
0x18002dc1e  push    rbp
0x18002dc1f  lea     rbp, [rsp-57h]
0x18002dc24  sub     rsp, 90h
0x18002dc2b  mov     rax, cs:__security_cookie
0x18002dc32  xor     rax, rsp
0x18002dc35  mov     [rbp+57h+var_10], rax
0x18002dc39  mov     rbx, rcx
0x18002dc3c  lea     rdx, [rbp+57h+SRWLock]
0x18002dc40  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002dc45  mov     rdi, [rbx+110h]
0x18002dc4c  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002dc51  mov     r8d, [rax]
0x18002dc54  cmp     r8d, 5
0x18002dc58  jbe     short loc_18002DC6B
0x18002dc5a  lea     rdx, [rdi+8]; ActivityId
0x18002dc5e  mov     ecx, 3; ControlCode
0x18002dc63  call    cs:__imp_EventActivityIdControl
0x18002dc69  jmp     short loc_18002DC72
0x18002dc6b  xorps   xmm0, xmm0
0x18002dc6e  movups  xmmword ptr [rdi+8], xmm0
0x18002dc72  mov     dword ptr [rdi], 1
0x18002dc78  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002dc7c  test    rcx, rcx
0x18002dc7f  jz      short loc_18002DC87
0x18002dc81  call    cs:__imp_ReleaseSRWLockExclusive
0x18002dc87  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002dc8c  mov     rdi, rax
0x18002dc8f  mov     ecx, [rax]
0x18002dc91  cmp     ecx, 5
0x18002dc94  jbe     loc_18002DD1C
0x18002dc9a  call    cs:__imp_GetCurrentThreadId
0x18002dca0  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002dca3  mov     [rbp+57h+var_58], 0
0x18002dcab  mov     r8, [rbx+110h]
0x18002dcb2  cmp     byte ptr [r8+4], 0
0x18002dcb7  jz      short loc_18002DCD8
0x18002dcb9  lea     r9, [r8+18h]
0x18002dcbd  cmp     dword ptr [r9], 0
0x18002dcc1  jnz     short loc_18002DCDB
0x18002dcc3  cmp     dword ptr [r9+4], 0
0x18002dcc8  jnz     short loc_18002DCDB
0x18002dcca  cmp     dword ptr [r9+8], 0
0x18002dccf  jnz     short loc_18002DCDB
0x18002dcd1  cmp     dword ptr [r9+0Ch], 0
0x18002dcd6  jnz     short loc_18002DCDB
0x18002dcd8  xor     r9d, r9d
0x18002dcdb  lea     rax, [rbp+57h+SRWLock]
0x18002dcdf  mov     [rbp+57h+var_20], rax
0x18002dce3  mov     ecx, 4
0x18002dce8  mov     [rbp+57h+var_18], rcx
0x18002dcec  lea     rax, [rbp+57h+var_58]
0x18002dcf0  mov     [rbp+57h+var_30], rax
0x18002dcf4  mov     [rbp+57h+var_28], 8
0x18002dcfc  add     r8, 8
0x18002dd00  lea     rax, [rbp+57h+var_50]
0x18002dd04  mov     [rsp+90h+var_68], rax
0x18002dd09  mov     [rsp+90h+var_70], ecx
0x18002dd0d  lea     rdx, byte_180047AF3
0x18002dd14  mov     rcx, rdi
0x18002dd17  call    _tlgWriteTransfer_EventWriteTransfer
0x18002dd1c  lea     rcx, [rbx+120h]; this
0x18002dd23  cmp     dword ptr [rcx+18h], 0
0x18002dd27  jnz     short loc_18002DD2F
0x18002dd29  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002dd2e  nop
0x18002dd2f  mov     rcx, [rbp+57h+var_10]
0x18002dd33  xor     rcx, rsp; StackCookie
0x18002dd36  call    __security_check_cookie
0x18002dd3b  lea     r11, [rsp+90h+var_s0]
0x18002dd43  mov     rbx, [r11+18h]
0x18002dd47  mov     rdi, [r11+20h]
0x18002dd4b  mov     rsp, r11
0x18002dd4e  pop     rbp
0x18002dd4f  retn
```
