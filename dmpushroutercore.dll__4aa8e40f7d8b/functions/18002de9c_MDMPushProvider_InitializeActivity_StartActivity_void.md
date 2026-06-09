# MDMPushProvider::InitializeActivity::StartActivity(void)

- ea: `0x18002de9c`
- end: `0x18002dfd8`
- name: `?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ccec`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002de9c`
- `0x18002dfe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002df22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002df22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002df09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002df09`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002deeb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002deeb`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StartActivity(MDMPushProvider::InitializeActivity *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // r8
  const GUID *v6; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+27h]
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v13; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MDMPushProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = MDMPushProvider::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = (const GUID *)(v5 + 24), !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    p_SRWLock = &SRWLock;
    v13 = 4;
    v10 = &v8;
    v11 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v4,
      (unsigned __int8 *)byte_18004734F,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::InitializeActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x18002de9c  mov     [rsp-8+arg_8], rbx
0x18002dea1  mov     [rsp-8+arg_10], rdi
0x18002dea6  push    rbp
0x18002dea7  lea     rbp, [rsp-57h]
0x18002deac  sub     rsp, 90h
0x18002deb3  mov     rax, cs:__security_cookie
0x18002deba  xor     rax, rsp
0x18002debd  mov     [rbp+57h+var_10], rax
0x18002dec1  mov     rbx, rcx
0x18002dec4  lea     rdx, [rbp+57h+SRWLock]
0x18002dec8  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002decd  mov     rdi, [rbx+110h]
0x18002ded4  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002ded9  mov     r8d, [rax]
0x18002dedc  cmp     r8d, 5
0x18002dee0  jbe     short loc_18002DEF3
0x18002dee2  lea     rdx, [rdi+8]; ActivityId
0x18002dee6  mov     ecx, 3; ControlCode
0x18002deeb  call    cs:__imp_EventActivityIdControl
0x18002def1  jmp     short loc_18002DEFA
0x18002def3  xorps   xmm0, xmm0
0x18002def6  movups  xmmword ptr [rdi+8], xmm0
0x18002defa  mov     dword ptr [rdi], 1
0x18002df00  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002df04  test    rcx, rcx
0x18002df07  jz      short loc_18002DF0F
0x18002df09  call    cs:__imp_ReleaseSRWLockExclusive
0x18002df0f  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002df14  mov     rdi, rax
0x18002df17  mov     ecx, [rax]
0x18002df19  cmp     ecx, 5
0x18002df1c  jbe     loc_18002DFA4
0x18002df22  call    cs:__imp_GetCurrentThreadId
0x18002df28  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002df2b  mov     [rbp+57h+var_58], 0
0x18002df33  mov     r8, [rbx+110h]
0x18002df3a  cmp     byte ptr [r8+4], 0
0x18002df3f  jz      short loc_18002DF60
0x18002df41  lea     r9, [r8+18h]
0x18002df45  cmp     dword ptr [r9], 0
0x18002df49  jnz     short loc_18002DF63
0x18002df4b  cmp     dword ptr [r9+4], 0
0x18002df50  jnz     short loc_18002DF63
0x18002df52  cmp     dword ptr [r9+8], 0
0x18002df57  jnz     short loc_18002DF63
0x18002df59  cmp     dword ptr [r9+0Ch], 0
0x18002df5e  jnz     short loc_18002DF63
0x18002df60  xor     r9d, r9d
0x18002df63  lea     rax, [rbp+57h+SRWLock]
0x18002df67  mov     [rbp+57h+var_20], rax
0x18002df6b  mov     ecx, 4
0x18002df70  mov     [rbp+57h+var_18], rcx
0x18002df74  lea     rax, [rbp+57h+var_58]
0x18002df78  mov     [rbp+57h+var_30], rax
0x18002df7c  mov     [rbp+57h+var_28], 8
0x18002df84  add     r8, 8
0x18002df88  lea     rax, [rbp+57h+var_50]
0x18002df8c  mov     [rsp+90h+var_68], rax
0x18002df91  mov     [rsp+90h+var_70], ecx
0x18002df95  lea     rdx, byte_18004734F
0x18002df9c  mov     rcx, rdi
0x18002df9f  call    _tlgWriteTransfer_EventWriteTransfer
0x18002dfa4  lea     rcx, [rbx+120h]; this
0x18002dfab  cmp     dword ptr [rcx+18h], 0
0x18002dfaf  jnz     short loc_18002DFB7
0x18002dfb1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002dfb6  nop
0x18002dfb7  mov     rcx, [rbp+57h+var_10]
0x18002dfbb  xor     rcx, rsp; StackCookie
0x18002dfbe  call    __security_check_cookie
0x18002dfc3  lea     r11, [rsp+90h+var_s0]
0x18002dfcb  mov     rbx, [r11+18h]
0x18002dfcf  mov     rdi, [r11+20h]
0x18002dfd3  mov     rsp, r11
0x18002dfd6  pop     rbp
0x18002dfd7  retn
```
