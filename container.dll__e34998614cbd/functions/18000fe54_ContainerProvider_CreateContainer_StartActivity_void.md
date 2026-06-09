# ContainerProvider::CreateContainer::StartActivity(void *)

- ea: `0x18000fe54`
- end: `0x18000ff72`
- name: `?StartActivity@CreateContainer@ContainerProvider@@QEAAXPEAX@Z`
- size: `286`
- prototype: `void(ContainerProvider::CreateContainer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000db40`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x18000fe54`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fec3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fec3`

## pseudocode

```c
void __fastcall ContainerProvider::CreateContainer::StartActivity(
        ContainerProvider::CreateContainer *this,
        container_runtime *a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  int v5; // edi
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  int v8; // r9d
  unsigned int *v9; // [rsp+20h] [rbp-50h]
  struct _GUID v10; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID v12; // [rsp+58h] [rbp-18h] BYREF

  v10.Data1 = 0;
  v12 = 0;
  container_runtime::GetContainerIdentifier(a2, 0, &v12, &v10, v9);
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v3 = ContainerProvider::Provider();
  v5 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    *(_QWORD *)v10.Data4 = &v12;
    CurrentThreadId = GetCurrentThreadId();
    v7 = *((_QWORD *)this + 34);
    *(_DWORD *)&v10.Data2 = CurrentThreadId;
    v11 = 0;
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)word_18003B55A,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&v10.Data2,
      (__int64)v10.Data4,
      (__int64)&v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::CreateContainer *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x18000fe54  mov     [rsp-8+arg_10], rbx
0x18000fe59  mov     [rsp-8+arg_18], rdi
0x18000fe5e  push    rbp
0x18000fe5f  mov     rbp, rsp
0x18000fe62  sub     rsp, 70h
0x18000fe66  mov     rax, cs:__security_cookie
0x18000fe6d  xor     rax, rsp
0x18000fe70  mov     [rbp+var_8], rax
0x18000fe74  mov     rax, rdx
0x18000fe77  mov     [rbp+var_30.Data1], 0
0x18000fe7e  mov     rbx, rcx
0x18000fe81  lea     r9, [rbp+var_30]; struct _GUID *
0x18000fe85  xorps   xmm0, xmm0
0x18000fe88  lea     r8, [rbp+var_18]; struct _GUID *
0x18000fe8c  mov     rcx, rax; this
0x18000fe8f  xor     edx, edx; void *
0x18000fe91  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000fe95  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000fe9a  mov     rcx, rbx
0x18000fe9d  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000fea2  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000fea7  mov     rdi, rax
0x18000feaa  mov     ecx, [rax]
0x18000feac  cmp     ecx, 5
0x18000feaf  jbe     loc_18000FF41
0x18000feb5  mov     ecx, [rbp+var_30.Data1]
0x18000feb8  lea     rax, [rbp+var_18]
0x18000febc  mov     qword ptr [rbp+var_30.Data4], rax
0x18000fec0  mov     [rbp+var_30.Data1], ecx
0x18000fec3  call    cs:__imp_GetCurrentThreadId
0x18000feca  nop     dword ptr [rax+rax+00h]
0x18000fecf  mov     r8, [rbx+110h]
0x18000fed6  mov     dword ptr [rbp+var_30.Data2], eax
0x18000fed9  mov     [rbp+var_20], 0
0x18000fee1  cmp     byte ptr [r8+4], 0
0x18000fee6  jz      short loc_18000FF07
0x18000fee8  lea     r9, [r8+18h]
0x18000feec  cmp     dword ptr [r9], 0
0x18000fef0  jnz     short loc_18000FF0A
0x18000fef2  cmp     dword ptr [r9+4], 0
0x18000fef7  jnz     short loc_18000FF0A
0x18000fef9  cmp     dword ptr [r9+8], 0
0x18000fefe  jnz     short loc_18000FF0A
0x18000ff00  cmp     dword ptr [r9+0Ch], 0
0x18000ff05  jnz     short loc_18000FF0A
0x18000ff07  xor     r9d, r9d
0x18000ff0a  lea     rax, [rbp+var_30]
0x18000ff0e  add     r8, 8
0x18000ff12  mov     [rsp+70h+var_38], rax
0x18000ff17  lea     rdx, word_18003B55A
0x18000ff1e  lea     rax, [rbp+var_30.Data4]
0x18000ff22  mov     rcx, rdi
0x18000ff25  mov     [rsp+70h+var_40], rax
0x18000ff2a  lea     rax, [rbp+var_30.Data2]
0x18000ff2e  mov     [rsp+70h+var_48], rax
0x18000ff33  lea     rax, [rbp+var_20]
0x18000ff37  mov     [rsp+70h+var_50], rax
0x18000ff3c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18000ff41  lea     rcx, [rbx+120h]; this
0x18000ff48  cmp     dword ptr [rcx+18h], 0
0x18000ff4c  jnz     short loc_18000FF53
0x18000ff4e  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000ff53  mov     rcx, [rbp+var_8]
0x18000ff57  xor     rcx, rsp; StackCookie
0x18000ff5a  call    __security_check_cookie
0x18000ff5f  lea     r11, [rsp+70h+var_s0]
0x18000ff64  mov     rbx, [r11+20h]
0x18000ff68  mov     rdi, [r11+28h]
0x18000ff6c  mov     rsp, r11
0x18000ff6f  pop     rbp
0x18000ff70  retn
```
