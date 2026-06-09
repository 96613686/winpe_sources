# ContainerProvider::BootContainer::StartActivity(void *)

- ea: `0x18000f8f0`
- end: `0x18000fa38`
- name: `?StartActivity@BootContainer@ContainerProvider@@QEAAXPEAX@Z`
- size: `328`
- prototype: `void(ContainerProvider::BootContainer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e5a0`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x18000f8f0`
- `0x180012160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f989`

## pseudocode

```c
void __fastcall ContainerProvider::BootContainer::StartActivity(
        ContainerProvider::BootContainer *this,
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
        (unsigned int)&word_18003B5BE,
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
      (ContainerProvider::BootContainer *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x18000f8f0  mov     [rsp-8+arg_10], rbx
0x18000f8f5  mov     [rsp-8+arg_18], rdi
0x18000f8fa  push    rbp
0x18000f8fb  mov     rbp, rsp
0x18000f8fe  sub     rsp, 70h
0x18000f902  mov     rax, cs:__security_cookie
0x18000f909  xor     rax, rsp
0x18000f90c  mov     [rbp+var_8], rax
0x18000f910  mov     rax, rdx
0x18000f913  mov     [rbp+var_30.Data1], 0
0x18000f91a  mov     rdi, rcx
0x18000f91d  lea     r9, [rbp+var_30]; struct _GUID *
0x18000f921  xorps   xmm0, xmm0
0x18000f924  lea     r8, [rbp+var_18]; struct _GUID *
0x18000f928  mov     rcx, rax; this
0x18000f92b  xor     edx, edx; void *
0x18000f92d  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000f931  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000f936  mov     rcx, rdi
0x18000f939  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000f93e  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000f943  mov     rbx, rax
0x18000f946  mov     ecx, [rax]
0x18000f948  cmp     ecx, 5
0x18000f94b  jbe     loc_18000FA07
0x18000f951  mov     rdx, [rax+18h]
0x18000f955  mov     rcx, [rax+10h]
0x18000f959  mov     rax, 400000000000h
0x18000f963  test    rax, rcx
0x18000f966  jz      loc_18000FA07
0x18000f96c  mov     rcx, rdx
0x18000f96f  and     rcx, rax
0x18000f972  cmp     rcx, rdx
0x18000f975  jnz     loc_18000FA07
0x18000f97b  mov     eax, [rbp+var_30.Data1]
0x18000f97e  mov     [rbp+var_30.Data1], eax
0x18000f981  lea     rax, [rbp+var_18]
0x18000f985  mov     qword ptr [rbp+var_30.Data4], rax
0x18000f989  call    cs:__imp_GetCurrentThreadId
0x18000f990  nop     dword ptr [rax+rax+00h]
0x18000f995  mov     r8, [rdi+110h]
0x18000f99c  mov     dword ptr [rbp+var_30.Data2], eax
0x18000f99f  mov     [rbp+var_20], 0
0x18000f9a7  cmp     byte ptr [r8+4], 0
0x18000f9ac  jz      short loc_18000F9CD
0x18000f9ae  lea     r9, [r8+18h]
0x18000f9b2  cmp     dword ptr [r9], 0
0x18000f9b6  jnz     short loc_18000F9D0
0x18000f9b8  cmp     dword ptr [r9+4], 0
0x18000f9bd  jnz     short loc_18000F9D0
0x18000f9bf  cmp     dword ptr [r9+8], 0
0x18000f9c4  jnz     short loc_18000F9D0
0x18000f9c6  cmp     dword ptr [r9+0Ch], 0
0x18000f9cb  jnz     short loc_18000F9D0
0x18000f9cd  xor     r9d, r9d
0x18000f9d0  lea     rax, [rbp+var_30]
0x18000f9d4  add     r8, 8
0x18000f9d8  mov     [rsp+70h+var_38], rax
0x18000f9dd  lea     rdx, word_18003B5BE
0x18000f9e4  lea     rax, [rbp+var_30.Data4]
0x18000f9e8  mov     rcx, rbx
0x18000f9eb  mov     [rsp+70h+var_40], rax
0x18000f9f0  lea     rax, [rbp+var_30.Data2]
0x18000f9f4  mov     [rsp+70h+var_48], rax
0x18000f9f9  lea     rax, [rbp+var_20]
0x18000f9fd  mov     [rsp+70h+var_50], rax
0x18000fa02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18000fa07  lea     rcx, [rdi+120h]; this
0x18000fa0e  cmp     dword ptr [rcx+18h], 0
0x18000fa12  jnz     short loc_18000FA19
0x18000fa14  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000fa19  mov     rcx, [rbp+var_8]
0x18000fa1d  xor     rcx, rsp; StackCookie
0x18000fa20  call    __security_check_cookie
0x18000fa25  lea     r11, [rsp+70h+var_s0]
0x18000fa2a  mov     rbx, [r11+20h]
0x18000fa2e  mov     rdi, [r11+28h]
0x18000fa32  mov     rsp, r11
0x18000fa35  pop     rbp
0x18000fa36  retn
```
