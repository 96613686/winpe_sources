# ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StartActivity(_GUID const &,ulong,unsigned __int64)

- ea: `0x18004b3dc`
- end: `0x18004b5c5`
- name: `?StartActivity@ClientLib_InvokeOrQueueEvent@TraceProvider@Diagnostics@ComputeLib@@QEAAXAEBU_GUID@@K_K@Z`
- size: `489`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *__hidden this, const struct _GUID *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004a4e0`

## callees

- `0x1800016ec`
- `0x1800067c0`
- `0x180014a2c`
- `0x180014de4`
- `0x1800150dc`
- `0x18004b3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b4ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b4ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b4ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b4ef`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004b490`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004b490`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StartActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *this,
        const struct _GUID *a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int128 v9; // xmm0
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rbx
  const struct _tlgProvider_t *v12; // rax
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rax
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  const GUID *v20; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  int v22; // [rsp+38h] [rbp-51h] BYREF
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-19h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+88h] [rbp-1h]
  int *v30; // [rsp+90h] [rbp+7h]
  __int64 v31; // [rsp+98h] [rbp+Fh]
  __int64 *v32; // [rsp+A0h] [rbp+17h]
  __int64 v33; // [rsp+A8h] [rbp+1Fh]

  SRWLock = 0;
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v8 = *((_QWORD *)this + 34);
  v9 = (__int128)*a2;
  v10 = SRWLock;
  *(_BYTE *)(v8 + 4) = 1;
  *(_OWORD *)(v8 + 24) = v9;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  SRWLock = 0;
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v11 = *((_QWORD *)this + 34);
  v12 = ComputeLib::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v12 > 5u
    && (*((_QWORD *)v12 + 2) & 0x10000LL) != 0
    && (*((_QWORD *)v12 + 3) & 0x10000LL) == *((_QWORD *)v12 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v11 + 8));
  }
  else
  {
    *(_OWORD *)(v11 + 8) = 0;
  }
  v13 = SRWLock;
  *(_DWORD *)v11 = 1;
  if ( v13 )
    ReleaseSRWLockExclusive(v13);
  v14 = ComputeLib::Diagnostics::TraceProvider::Provider();
  v16 = (__int64)v14;
  if ( *(_DWORD *)v14 > 5u )
  {
    v17 = *((_QWORD *)v14 + 3);
    if ( (*(_QWORD *)(v16 + 16) & 0x10000LL) != 0 && (v17 & 0x10000) == v17 )
    {
      v23 = a4;
      v22 = a3;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v24 = 0;
      if ( !*(_BYTE *)(v19 + 4)
        || (v20 = (const GUID *)(v19 + 24), !*(_DWORD *)(v19 + 24))
        && !*(_DWORD *)(v19 + 28)
        && !*(_DWORD *)(v19 + 32)
        && !*(_DWORD *)(v19 + 36) )
      {
        v20 = 0;
      }
      v33 = 8;
      v32 = &v23;
      v31 = 4;
      v30 = &v22;
      v29 = 4;
      p_SRWLock = &SRWLock;
      v27 = 8;
      v26 = &v24;
      tlgWriteTransfer_EventWriteTransfer(
        v16,
        (unsigned __int8 *)&byte_1800C84DB,
        (const GUID *)(v19 + 8),
        v20,
        6u,
        &v25);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *)((char *)this + 288),
      v15);
}

```

## disassembly

```asm
0x18004b3dc  mov     [rsp-8+arg_8], rbx
0x18004b3e1  mov     [rsp-8+arg_10], rsi
0x18004b3e6  push    rbp
0x18004b3e7  push    rdi
0x18004b3e8  push    r12
0x18004b3ea  push    r14
0x18004b3ec  push    r15
0x18004b3ee  lea     rbp, [rsp-37h]
0x18004b3f3  sub     rsp, 0C0h
0x18004b3fa  mov     rax, cs:__security_cookie
0x18004b401  xor     rax, rsp
0x18004b404  mov     [rbp+57h+var_30], rax
0x18004b408  mov     rbx, rdx
0x18004b40b  xor     r15d, r15d
0x18004b40e  lea     rdx, [rbp+57h+SRWLock]
0x18004b412  mov     [rbp+57h+SRWLock], r15
0x18004b416  mov     rsi, r9
0x18004b419  mov     r14d, r8d
0x18004b41c  mov     rdi, rcx
0x18004b41f  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b424  mov     rax, [rdi+110h]
0x18004b42b  movups  xmm0, xmmword ptr [rbx]
0x18004b42e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004b432  mov     byte ptr [rax+4], 1
0x18004b436  movdqu  xmmword ptr [rax+18h], xmm0
0x18004b43b  test    rcx, rcx
0x18004b43e  jz      short loc_18004B446
0x18004b440  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b446  lea     rdx, [rbp+57h+SRWLock]
0x18004b44a  mov     [rbp+57h+SRWLock], r15
0x18004b44e  mov     rcx, rdi
0x18004b451  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b456  mov     rbx, [rdi+110h]
0x18004b45d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b462  mov     r12d, 10000h
0x18004b468  mov     ecx, [rax]
0x18004b46a  cmp     ecx, 5
0x18004b46d  jbe     short loc_18004B498
0x18004b46f  mov     rcx, [rax+18h]
0x18004b473  mov     rax, [rax+10h]
0x18004b477  test    r12, rax
0x18004b47a  jz      short loc_18004B498
0x18004b47c  mov     rax, rcx
0x18004b47f  and     rax, r12
0x18004b482  cmp     rax, rcx
0x18004b485  jnz     short loc_18004B498
0x18004b487  lea     rdx, [rbx+8]; ActivityId
0x18004b48b  mov     ecx, 3; ControlCode
0x18004b490  call    cs:__imp_EventActivityIdControl
0x18004b496  jmp     short loc_18004B49F
0x18004b498  xorps   xmm0, xmm0
0x18004b49b  movups  xmmword ptr [rbx+8], xmm0
0x18004b49f  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004b4a3  mov     dword ptr [rbx], 1
0x18004b4a9  test    rcx, rcx
0x18004b4ac  jz      short loc_18004B4B4
0x18004b4ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b4b4  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b4b9  mov     rbx, rax
0x18004b4bc  mov     ecx, [rax]
0x18004b4be  cmp     ecx, 5
0x18004b4c1  jbe     loc_18004B58B
0x18004b4c7  mov     rax, [rax+18h]
0x18004b4cb  mov     rcx, [rbx+10h]
0x18004b4cf  test    r12, rcx
0x18004b4d2  jz      loc_18004B58B
0x18004b4d8  mov     rcx, rax
0x18004b4db  and     rcx, r12
0x18004b4de  cmp     rcx, rax
0x18004b4e1  jnz     loc_18004B58B
0x18004b4e7  mov     [rbp+57h+var_A0], rsi
0x18004b4eb  mov     [rbp+57h+var_A8], r14d
0x18004b4ef  call    cs:__imp_GetCurrentThreadId
0x18004b4f5  mov     r8, [rdi+110h]
0x18004b4fc  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004b4ff  mov     [rbp+57h+var_98], r15
0x18004b503  cmp     [r8+4], r15b
0x18004b507  jz      short loc_18004B524
0x18004b509  lea     r9, [r8+18h]
0x18004b50d  cmp     [r9], r15d
0x18004b510  jnz     short loc_18004B527
0x18004b512  cmp     [r9+4], r15d
0x18004b516  jnz     short loc_18004B527
0x18004b518  cmp     [r9+8], r15d
0x18004b51c  jnz     short loc_18004B527
0x18004b51e  cmp     [r9+0Ch], r15d
0x18004b522  jnz     short loc_18004B527
0x18004b524  mov     r9, r15; int
0x18004b527  lea     rax, [rbp+57h+var_A0]
0x18004b52b  mov     [rbp+57h+var_38], 8
0x18004b533  mov     [rbp+57h+var_40], rax
0x18004b537  lea     rdx, byte_1800C84DB; int
0x18004b53e  lea     rax, [rbp+57h+var_A8]
0x18004b542  mov     [rbp+57h+var_48], 4
0x18004b54a  mov     [rbp+57h+var_50], rax
0x18004b54e  add     r8, 8; int
0x18004b552  lea     rax, [rbp+57h+SRWLock]
0x18004b556  mov     [rbp+57h+var_58], 4
0x18004b55e  mov     [rbp+57h+var_60], rax
0x18004b562  mov     rcx, rbx; int
0x18004b565  lea     rax, [rbp+57h+var_98]
0x18004b569  mov     [rbp+57h+var_68], 8
0x18004b571  mov     [rbp+57h+var_70], rax
0x18004b575  lea     rax, [rbp+57h+var_90]
0x18004b579  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x18004b57e  mov     [rsp+0E0h+var_C0], 6; ULONG
0x18004b586  call    _tlgWriteTransfer_EventWriteTransfer
0x18004b58b  lea     rcx, [rdi+120h]; this
0x18004b592  cmp     [rcx+18h], r15d
0x18004b596  jnz     short loc_18004B59D
0x18004b598  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18004b59d  mov     rcx, [rbp+57h+var_30]
0x18004b5a1  xor     rcx, rsp; StackCookie
0x18004b5a4  call    __security_check_cookie
0x18004b5a9  lea     r11, [rsp+0E0h+var_20]
0x18004b5b1  mov     rbx, [r11+38h]
0x18004b5b5  mov     rsi, [r11+40h]
0x18004b5b9  mov     rsp, r11
0x18004b5bc  pop     r15
0x18004b5be  pop     r14
0x18004b5c0  pop     r12
0x18004b5c2  pop     rdi
0x18004b5c3  pop     rbp
0x18004b5c4  retn
```
