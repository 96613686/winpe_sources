# ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<ushort const *>(ushort const * &&)

- ea: `0x18001a9c8`
- end: `0x18001ab7d`
- name: `??$StartActivity@PEBG@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG@Z`
- size: `437`
- prototype: `void __fastcall(__int64, __int64 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180001ed0`
- `0x180002690`
- `0x18000bc04`
- `0x18000ff58`
- `0x18001a9c8`
- `0x18001f068`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001aa33`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001aa33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa99`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<unsigned short const *>(
        __int64 a1,
        __int64 **a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  RTL_SRWLOCK *v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  int v8; // edi
  __int64 *v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // rax
  int v14; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  __int64 v16; // [rsp+38h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-19h]
  __int64 v19; // [rsp+68h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-9h]
  __int64 v21; // [rsp+78h] [rbp-1h]
  __int64 *v22; // [rsp+80h] [rbp+7h]
  int v23; // [rsp+88h] [rbp+Fh]
  int v24; // [rsp+8Ch] [rbp+13h]

  SRWLock = 0;
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v5 > 4u && (*((_QWORD *)v5 + 2) & 0x40) != 0 && (*((_QWORD *)v5 + 3) & 0x40LL) == *((_QWORD *)v5 + 3) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v7 = ComputeLib::Diagnostics::TraceProvider::Provider();
  v8 = (int)v7;
  if ( *(_DWORD *)v7 > 4u && (*((_QWORD *)v7 + 2) & 0x40) != 0 && (*((_QWORD *)v7 + 3) & 0x40LL) == *((_QWORD *)v7 + 3) )
  {
    v9 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    if ( v9 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)v9 + v13) );
      v14 = 2 * v13 + 2;
    }
    else
    {
      v9 = &qword_18004C4D0;
      v14 = 2;
    }
    v23 = v14;
    v22 = v9;
    p_SRWLock = &SRWLock;
    v24 = 0;
    v18 = &v16;
    v21 = 4;
    v19 = 8;
    tlgWriteTransfer_EventWriteTransfer(v8, (int)&byte_18005529D, v11 + 8, v12, 5u, &v17);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18001a9c8  push    rbp
0x18001a9ca  push    rbx
0x18001a9cb  push    rsi
0x18001a9cc  push    rdi
0x18001a9cd  push    r14
0x18001a9cf  push    r15
0x18001a9d1  lea     rbp, [rsp-2Fh]
0x18001a9d6  sub     rsp, 0A8h
0x18001a9dd  mov     rax, cs:__security_cookie
0x18001a9e4  xor     rax, rsp
0x18001a9e7  mov     [rbp+57h+var_40], rax
0x18001a9eb  mov     r14, rdx
0x18001a9ee  xor     r15d, r15d
0x18001a9f1  lea     rdx, [rbp+57h+SRWLock]
0x18001a9f5  mov     [rbp+57h+SRWLock], r15
0x18001a9f9  mov     rsi, rcx
0x18001a9fc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001aa01  mov     rbx, [rsi+110h]
0x18001aa08  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18001aa0d  mov     edx, [rax]
0x18001aa0f  cmp     edx, 4
0x18001aa12  jbe     short loc_18001AA41
0x18001aa14  mov     rcx, [rax+18h]
0x18001aa18  mov     rax, [rax+10h]
0x18001aa1c  test    al, 40h
0x18001aa1e  jz      short loc_18001AA41
0x18001aa20  mov     rax, rcx
0x18001aa23  and     eax, 40h
0x18001aa26  cmp     rax, rcx
0x18001aa29  jnz     short loc_18001AA41
0x18001aa2b  lea     rdx, [rbx+8]; ActivityId
0x18001aa2f  lea     ecx, [r15+3]; ControlCode
0x18001aa33  call    cs:__imp_EventActivityIdControl
0x18001aa3a  nop     dword ptr [rax+rax+00h]
0x18001aa3f  jmp     short loc_18001AA48
0x18001aa41  xorps   xmm0, xmm0
0x18001aa44  movups  xmmword ptr [rbx+8], xmm0
0x18001aa48  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001aa4c  mov     dword ptr [rbx], 1
0x18001aa52  test    rcx, rcx
0x18001aa55  jz      short loc_18001AA63
0x18001aa57  call    cs:__imp_ReleaseSRWLockExclusive
0x18001aa5e  nop     dword ptr [rax+rax+00h]
0x18001aa63  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18001aa68  mov     rdi, rax
0x18001aa6b  mov     ecx, [rax]
0x18001aa6d  cmp     ecx, 4
0x18001aa70  jbe     loc_18001AB4E
0x18001aa76  mov     rdx, [rax+18h]
0x18001aa7a  mov     rcx, [rax+10h]
0x18001aa7e  test    cl, 40h
0x18001aa81  jz      loc_18001AB4E
0x18001aa87  mov     rcx, rdx
0x18001aa8a  and     ecx, 40h
0x18001aa8d  cmp     rcx, rdx
0x18001aa90  jnz     loc_18001AB4E
0x18001aa96  mov     rbx, [r14]
0x18001aa99  call    cs:__imp_GetCurrentThreadId
0x18001aaa0  nop     dword ptr [rax+rax+00h]
0x18001aaa5  mov     r8, [rsi+110h]
0x18001aaac  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001aaaf  mov     [rbp+57h+var_98], r15
0x18001aab3  cmp     [r8+4], r15b
0x18001aab7  jz      short loc_18001AAD4
0x18001aab9  lea     r9, [r8+18h]
0x18001aabd  cmp     [r9], r15d
0x18001aac0  jnz     short loc_18001AAD7
0x18001aac2  cmp     [r9+4], r15d
0x18001aac6  jnz     short loc_18001AAD7
0x18001aac8  cmp     [r9+8], r15d
0x18001aacc  jnz     short loc_18001AAD7
0x18001aace  cmp     [r9+0Ch], r15d
0x18001aad2  jnz     short loc_18001AAD7
0x18001aad4  mov     r9, r15; int
0x18001aad7  test    rbx, rbx
0x18001aada  jz      short loc_18001AAF3
0x18001aadc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aae0  inc     rax
0x18001aae3  cmp     [rbx+rax*2], r15w
0x18001aae8  jnz     short loc_18001AAE0
0x18001aaea  lea     eax, ds:2[rax*2]
0x18001aaf1  jmp     short loc_18001AAFF
0x18001aaf3  lea     rbx, qword_18004C4D0
0x18001aafa  mov     eax, 2
0x18001aaff  mov     [rbp+57h+var_48], eax
0x18001ab02  lea     rdx, byte_18005529D; int
0x18001ab09  lea     rax, [rbp+57h+SRWLock]
0x18001ab0d  mov     [rbp+57h+var_50], rbx
0x18001ab11  mov     [rbp+57h+var_60], rax
0x18001ab15  add     r8, 8; int
0x18001ab19  lea     rax, [rbp+57h+var_98]
0x18001ab1d  mov     [rbp+57h+var_44], r15d
0x18001ab21  mov     [rbp+57h+var_70], rax
0x18001ab25  mov     rcx, rdi; int
0x18001ab28  lea     rax, [rbp+57h+var_90]
0x18001ab2c  mov     [rbp+57h+var_58], 4
0x18001ab34  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x18001ab39  mov     [rsp+0D0h+var_B0], 5; ULONG
0x18001ab41  mov     [rbp+57h+var_68], 8
0x18001ab49  call    _tlgWriteTransfer_EventWriteTransfer
0x18001ab4e  lea     rcx, [rsi+120h]; this
0x18001ab55  cmp     [rcx+18h], r15d
0x18001ab59  jnz     short loc_18001AB60
0x18001ab5b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001ab60  mov     rcx, [rbp+57h+var_40]
0x18001ab64  xor     rcx, rsp; StackCookie
0x18001ab67  call    __security_check_cookie
0x18001ab6c  add     rsp, 0A8h
0x18001ab73  pop     r15
0x18001ab75  pop     r14
0x18001ab77  pop     rdi
0x18001ab78  pop     rsi
0x18001ab79  pop     rbx
0x18001ab7a  pop     rbp
0x18001ab7b  retn
```
