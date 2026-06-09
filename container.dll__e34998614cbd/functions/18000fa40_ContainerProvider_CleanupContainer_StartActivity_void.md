# ContainerProvider::CleanupContainer::StartActivity(void *)

- ea: `0x18000fa40`
- end: `0x18000fb88`
- name: `?StartActivity@CleanupContainer@ContainerProvider@@QEAAXPEAX@Z`
- size: `328`
- prototype: `void(ContainerProvider::CleanupContainer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d8f0`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x18000fa40`
- `0x180012160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fad9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fad9`

## pseudocode

```c
void __fastcall ContainerProvider::CleanupContainer::StartActivity(
        ContainerProvider::CleanupContainer *this,
        container_runtime *a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  int v5; // ebx
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
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v3 = ContainerProvider::Provider();
  v5 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    v4 = *((_QWORD *)v3 + 3);
    if ( (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0 && (v4 & 0x400000000000LL) == v4 )
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
        (unsigned int)byte_18003C52D,
        v7 + 8,
        v8,
        (__int64)&v11,
        (__int64)&v10.Data2,
        (__int64)v10.Data4,
        (__int64)&v10);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::CleanupContainer *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x18000fa40  mov     [rsp-8+arg_10], rbx
0x18000fa45  mov     [rsp-8+arg_18], rdi
0x18000fa4a  push    rbp
0x18000fa4b  mov     rbp, rsp
0x18000fa4e  sub     rsp, 70h
0x18000fa52  mov     rax, cs:__security_cookie
0x18000fa59  xor     rax, rsp
0x18000fa5c  mov     [rbp+var_8], rax
0x18000fa60  mov     rax, rdx
0x18000fa63  mov     [rbp+var_30.Data1], 0
0x18000fa6a  mov     rdi, rcx
0x18000fa6d  lea     r9, [rbp+var_30]; struct _GUID *
0x18000fa71  xorps   xmm0, xmm0
0x18000fa74  lea     r8, [rbp+var_18]; struct _GUID *
0x18000fa78  mov     rcx, rax; this
0x18000fa7b  xor     edx, edx; void *
0x18000fa7d  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000fa81  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000fa86  mov     rcx, rdi
0x18000fa89  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000fa8e  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000fa93  mov     rbx, rax
0x18000fa96  mov     ecx, [rax]
0x18000fa98  cmp     ecx, 5
0x18000fa9b  jbe     loc_18000FB57
0x18000faa1  mov     rdx, [rax+18h]
0x18000faa5  mov     rcx, [rax+10h]
0x18000faa9  mov     rax, 400000000000h
0x18000fab3  test    rax, rcx
0x18000fab6  jz      loc_18000FB57
0x18000fabc  mov     rcx, rdx
0x18000fabf  and     rcx, rax
0x18000fac2  cmp     rcx, rdx
0x18000fac5  jnz     loc_18000FB57
0x18000facb  mov     eax, [rbp+var_30.Data1]
0x18000face  mov     [rbp+var_30.Data1], eax
0x18000fad1  lea     rax, [rbp+var_18]
0x18000fad5  mov     qword ptr [rbp+var_30.Data4], rax
0x18000fad9  call    cs:__imp_GetCurrentThreadId
0x18000fae0  nop     dword ptr [rax+rax+00h]
0x18000fae5  mov     r8, [rdi+110h]
0x18000faec  mov     dword ptr [rbp+var_30.Data2], eax
0x18000faef  mov     [rbp+var_20], 0
0x18000faf7  cmp     byte ptr [r8+4], 0
0x18000fafc  jz      short loc_18000FB1D
0x18000fafe  lea     r9, [r8+18h]
0x18000fb02  cmp     dword ptr [r9], 0
0x18000fb06  jnz     short loc_18000FB20
0x18000fb08  cmp     dword ptr [r9+4], 0
0x18000fb0d  jnz     short loc_18000FB20
0x18000fb0f  cmp     dword ptr [r9+8], 0
0x18000fb14  jnz     short loc_18000FB20
0x18000fb16  cmp     dword ptr [r9+0Ch], 0
0x18000fb1b  jnz     short loc_18000FB20
0x18000fb1d  xor     r9d, r9d
0x18000fb20  lea     rax, [rbp+var_30]
0x18000fb24  add     r8, 8
0x18000fb28  mov     [rsp+70h+var_38], rax
0x18000fb2d  lea     rdx, byte_18003C52D
0x18000fb34  lea     rax, [rbp+var_30.Data4]
0x18000fb38  mov     rcx, rbx
0x18000fb3b  mov     [rsp+70h+var_40], rax
0x18000fb40  lea     rax, [rbp+var_30.Data2]
0x18000fb44  mov     [rsp+70h+var_48], rax
0x18000fb49  lea     rax, [rbp+var_20]
0x18000fb4d  mov     [rsp+70h+var_50], rax
0x18000fb52  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18000fb57  lea     rcx, [rdi+120h]; this
0x18000fb5e  cmp     dword ptr [rcx+18h], 0
0x18000fb62  jnz     short loc_18000FB69
0x18000fb64  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000fb69  mov     rcx, [rbp+var_8]
0x18000fb6d  xor     rcx, rsp; StackCookie
0x18000fb70  call    __security_check_cookie
0x18000fb75  lea     r11, [rsp+70h+var_s0]
0x18000fb7a  mov     rbx, [r11+20h]
0x18000fb7e  mov     rdi, [r11+28h]
0x18000fb82  mov     rsp, r11
0x18000fb85  pop     rbp
0x18000fb86  retn
```
