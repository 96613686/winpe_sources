# ContainerProvider::AddRuntimeVirtualKeysToContainer::StartActivity(void *)

- ea: `0x18000f7cc`
- end: `0x18000f8ea`
- name: `?StartActivity@AddRuntimeVirtualKeysToContainer@ContainerProvider@@QEAAXPEAX@Z`
- size: `286`
- prototype: `void(ContainerProvider::AddRuntimeVirtualKeysToContainer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d710`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x18000f7cc`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f83b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f83b`

## pseudocode

```c
void __fastcall ContainerProvider::AddRuntimeVirtualKeysToContainer::StartActivity(
        ContainerProvider::AddRuntimeVirtualKeysToContainer *this,
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
      (unsigned int)byte_18003C3A3,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&v10.Data2,
      (__int64)v10.Data4,
      (__int64)&v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::AddRuntimeVirtualKeysToContainer *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x18000f7cc  mov     [rsp-8+arg_10], rbx
0x18000f7d1  mov     [rsp-8+arg_18], rdi
0x18000f7d6  push    rbp
0x18000f7d7  mov     rbp, rsp
0x18000f7da  sub     rsp, 70h
0x18000f7de  mov     rax, cs:__security_cookie
0x18000f7e5  xor     rax, rsp
0x18000f7e8  mov     [rbp+var_8], rax
0x18000f7ec  mov     rax, rdx
0x18000f7ef  mov     [rbp+var_30.Data1], 0
0x18000f7f6  mov     rbx, rcx
0x18000f7f9  lea     r9, [rbp+var_30]; struct _GUID *
0x18000f7fd  xorps   xmm0, xmm0
0x18000f800  lea     r8, [rbp+var_18]; struct _GUID *
0x18000f804  mov     rcx, rax; this
0x18000f807  xor     edx, edx; void *
0x18000f809  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000f80d  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000f812  mov     rcx, rbx
0x18000f815  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000f81a  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000f81f  mov     rdi, rax
0x18000f822  mov     ecx, [rax]
0x18000f824  cmp     ecx, 5
0x18000f827  jbe     loc_18000F8B9
0x18000f82d  mov     ecx, [rbp+var_30.Data1]
0x18000f830  lea     rax, [rbp+var_18]
0x18000f834  mov     qword ptr [rbp+var_30.Data4], rax
0x18000f838  mov     [rbp+var_30.Data1], ecx
0x18000f83b  call    cs:__imp_GetCurrentThreadId
0x18000f842  nop     dword ptr [rax+rax+00h]
0x18000f847  mov     r8, [rbx+110h]
0x18000f84e  mov     dword ptr [rbp+var_30.Data2], eax
0x18000f851  mov     [rbp+var_20], 0
0x18000f859  cmp     byte ptr [r8+4], 0
0x18000f85e  jz      short loc_18000F87F
0x18000f860  lea     r9, [r8+18h]
0x18000f864  cmp     dword ptr [r9], 0
0x18000f868  jnz     short loc_18000F882
0x18000f86a  cmp     dword ptr [r9+4], 0
0x18000f86f  jnz     short loc_18000F882
0x18000f871  cmp     dword ptr [r9+8], 0
0x18000f876  jnz     short loc_18000F882
0x18000f878  cmp     dword ptr [r9+0Ch], 0
0x18000f87d  jnz     short loc_18000F882
0x18000f87f  xor     r9d, r9d
0x18000f882  lea     rax, [rbp+var_30]
0x18000f886  add     r8, 8
0x18000f88a  mov     [rsp+70h+var_38], rax
0x18000f88f  lea     rdx, byte_18003C3A3
0x18000f896  lea     rax, [rbp+var_30.Data4]
0x18000f89a  mov     rcx, rdi
0x18000f89d  mov     [rsp+70h+var_40], rax
0x18000f8a2  lea     rax, [rbp+var_30.Data2]
0x18000f8a6  mov     [rsp+70h+var_48], rax
0x18000f8ab  lea     rax, [rbp+var_20]
0x18000f8af  mov     [rsp+70h+var_50], rax
0x18000f8b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18000f8b9  lea     rcx, [rbx+120h]; this
0x18000f8c0  cmp     dword ptr [rcx+18h], 0
0x18000f8c4  jnz     short loc_18000F8CB
0x18000f8c6  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000f8cb  mov     rcx, [rbp+var_8]
0x18000f8cf  xor     rcx, rsp; StackCookie
0x18000f8d2  call    __security_check_cookie
0x18000f8d7  lea     r11, [rsp+70h+var_s0]
0x18000f8dc  mov     rbx, [r11+20h]
0x18000f8e0  mov     rdi, [r11+28h]
0x18000f8e4  mov     rsp, r11
0x18000f8e7  pop     rbp
0x18000f8e8  retn
```
