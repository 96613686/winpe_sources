# ContainerProvider::ConvertToServerSilo::StartActivity(void *)

- ea: `0x18000fc98`
- end: `0x18000fe4b`
- name: `?StartActivity@ConvertToServerSilo@ContainerProvider@@QEAAXPEAX@Z`
- size: `435`
- prototype: `void(ContainerProvider::ConvertToServerSilo *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e5a0`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x180007dd0`
- `0x18000895c`
- `0x18000abe4`
- `0x18000fc98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fd4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fd4d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fd29`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fd29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd9a`

## pseudocode

```c
void __fastcall ContainerProvider::ConvertToServerSilo::StartActivity(
        ContainerProvider::ConvertToServerSilo *this,
        container_runtime *a2)
{
  __int64 v3; // rbx
  const struct _tlgProvider_t *v4; // rax
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  const struct _tlgProvider_t *v8; // rbx
  __int64 v9; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  unsigned int *v13; // [rsp+20h] [rbp-60h]
  struct _GUID v14; // [rsp+40h] [rbp-40h] BYREF
  struct _GUID *v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  struct _GUID v17; // [rsp+60h] [rbp-20h] BYREF

  v14.Data1 = 0;
  v17 = 0;
  container_runtime::GetContainerIdentifier(a2, 0, &v17, &v14, v13);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    v14.Data4);
  v3 = *((_QWORD *)this + 34);
  v4 = ContainerProvider::Provider();
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v3 + 8));
  }
  else
  {
    *(_OWORD *)(v3 + 8) = 0;
  }
  v5 = *(RTL_SRWLOCK **)v14.Data4;
  *(_DWORD *)v3 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v6 = ContainerProvider::Provider();
  v8 = v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    v9 = *((_QWORD *)v6 + 3);
    if ( (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
    {
      v15 = &v17;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      *(_DWORD *)v14.Data4 = CurrentThreadId;
      v16 = 0x2000000;
      if ( !*(_BYTE *)(v11 + 4)
        || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
        && !*(_DWORD *)(v11 + 28)
        && !*(_DWORD *)(v11 + 32)
        && !*(_DWORD *)(v11 + 36) )
      {
        v12 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&unk_18003AF68,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)v14.Data4,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::ConvertToServerSilo *)((char *)this + 288),
      v7);
}

```

## disassembly

```asm
0x18000fc98  mov     [rsp-18h+arg_10], rbx
0x18000fc9d  push    rbp
0x18000fc9e  push    rdi
0x18000fc9f  push    r14
0x18000fca1  mov     rbp, rsp
0x18000fca4  sub     rsp, 80h
0x18000fcab  mov     rax, cs:__security_cookie
0x18000fcb2  xor     rax, rsp
0x18000fcb5  mov     [rbp+var_10], rax
0x18000fcb9  mov     rax, rdx
0x18000fcbc  mov     [rbp+var_40.Data1], 0
0x18000fcc3  mov     rdi, rcx
0x18000fcc6  lea     r9, [rbp+var_40]; struct _GUID *
0x18000fcca  xorps   xmm0, xmm0
0x18000fccd  lea     r8, [rbp+var_20]; struct _GUID *
0x18000fcd1  mov     rcx, rax; this
0x18000fcd4  xor     edx, edx; void *
0x18000fcd6  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000fcda  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000fcdf  lea     rdx, [rbp+var_40.Data4]
0x18000fce3  mov     rcx, rdi
0x18000fce6  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fceb  mov     rbx, [rdi+110h]
0x18000fcf2  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000fcf7  mov     r14, 400000000000h
0x18000fd01  mov     ecx, [rax]
0x18000fd03  cmp     ecx, 5
0x18000fd06  jbe     short loc_18000FD37
0x18000fd08  mov     rcx, [rax+18h]
0x18000fd0c  mov     rax, [rax+10h]
0x18000fd10  test    r14, rax
0x18000fd13  jz      short loc_18000FD37
0x18000fd15  mov     rax, rcx
0x18000fd18  and     rax, r14
0x18000fd1b  cmp     rax, rcx
0x18000fd1e  jnz     short loc_18000FD37
0x18000fd20  lea     rdx, [rbx+8]; ActivityId
0x18000fd24  mov     ecx, 3; ControlCode
0x18000fd29  call    cs:__imp_EventActivityIdControl
0x18000fd30  nop     dword ptr [rax+rax+00h]
0x18000fd35  jmp     short loc_18000FD3E
0x18000fd37  xorps   xmm0, xmm0
0x18000fd3a  movups  xmmword ptr [rbx+8], xmm0
0x18000fd3e  mov     rcx, qword ptr [rbp+var_40.Data4]; SRWLock
0x18000fd42  mov     dword ptr [rbx], 1
0x18000fd48  test    rcx, rcx
0x18000fd4b  jz      short loc_18000FD59
0x18000fd4d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fd54  nop     dword ptr [rax+rax+00h]
0x18000fd59  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000fd5e  mov     rbx, rax
0x18000fd61  mov     ecx, [rax]
0x18000fd63  cmp     ecx, 5
0x18000fd66  jbe     loc_18000FE18
0x18000fd6c  mov     rax, [rax+18h]
0x18000fd70  mov     rcx, [rbx+10h]
0x18000fd74  test    r14, rcx
0x18000fd77  jz      loc_18000FE18
0x18000fd7d  mov     rcx, rax
0x18000fd80  and     rcx, r14
0x18000fd83  cmp     rcx, rax
0x18000fd86  jnz     loc_18000FE18
0x18000fd8c  mov     eax, [rbp+var_40.Data1]
0x18000fd8f  mov     [rbp+var_40.Data1], eax
0x18000fd92  lea     rax, [rbp+var_20]
0x18000fd96  mov     [rbp+var_30], rax
0x18000fd9a  call    cs:__imp_GetCurrentThreadId
0x18000fda1  nop     dword ptr [rax+rax+00h]
0x18000fda6  mov     r8, [rdi+110h]
0x18000fdad  mov     dword ptr [rbp+var_40.Data4], eax
0x18000fdb0  mov     [rbp+var_28], 2000000h
0x18000fdb8  cmp     byte ptr [r8+4], 0
0x18000fdbd  jz      short loc_18000FDDE
0x18000fdbf  lea     r9, [r8+18h]
0x18000fdc3  cmp     dword ptr [r9], 0
0x18000fdc7  jnz     short loc_18000FDE1
0x18000fdc9  cmp     dword ptr [r9+4], 0
0x18000fdce  jnz     short loc_18000FDE1
0x18000fdd0  cmp     dword ptr [r9+8], 0
0x18000fdd5  jnz     short loc_18000FDE1
0x18000fdd7  cmp     dword ptr [r9+0Ch], 0
0x18000fddc  jnz     short loc_18000FDE1
0x18000fdde  xor     r9d, r9d
0x18000fde1  lea     rax, [rbp+var_40]
0x18000fde5  add     r8, 8
0x18000fde9  mov     [rsp+80h+var_48], rax
0x18000fdee  lea     rdx, unk_18003AF68
0x18000fdf5  lea     rax, [rbp+var_30]
0x18000fdf9  mov     rcx, rbx
0x18000fdfc  mov     [rsp+80h+var_50], rax
0x18000fe01  lea     rax, [rbp+var_40.Data4]
0x18000fe05  mov     [rsp+80h+var_58], rax
0x18000fe0a  lea     rax, [rbp+var_28]
0x18000fe0e  mov     [rsp+80h+var_60], rax
0x18000fe13  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18000fe18  lea     rcx, [rdi+120h]; this
0x18000fe1f  cmp     dword ptr [rcx+18h], 0
0x18000fe23  jnz     short loc_18000FE2A
0x18000fe25  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000fe2a  mov     rcx, [rbp+var_10]
0x18000fe2e  xor     rcx, rsp; StackCookie
0x18000fe31  call    __security_check_cookie
0x18000fe36  mov     rbx, [rsp+80h+arg_10]
0x18000fe3e  add     rsp, 80h
0x18000fe45  pop     r14
0x18000fe47  pop     rdi
0x18000fe48  pop     rbp
0x18000fe49  retn
```
