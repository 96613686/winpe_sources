# ContainerProvider::LaunchApplicationContainer::StartActivity(void *)

- ea: `0x18000ff78`
- end: `0x1800100c0`
- name: `?StartActivity@LaunchApplicationContainer@ContainerProvider@@QEAAXPEAX@Z`
- size: `328`
- prototype: `void(ContainerProvider::LaunchApplicationContainer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e140`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x18000ff78`
- `0x180012160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010011`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010011`

## pseudocode

```c
void __fastcall ContainerProvider::LaunchApplicationContainer::StartActivity(
        ContainerProvider::LaunchApplicationContainer *this,
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
        (unsigned int)&unk_18003B398,
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
      (ContainerProvider::LaunchApplicationContainer *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x18000ff78  mov     [rsp-8+arg_10], rbx
0x18000ff7d  mov     [rsp-8+arg_18], rdi
0x18000ff82  push    rbp
0x18000ff83  mov     rbp, rsp
0x18000ff86  sub     rsp, 70h
0x18000ff8a  mov     rax, cs:__security_cookie
0x18000ff91  xor     rax, rsp
0x18000ff94  mov     [rbp+var_8], rax
0x18000ff98  mov     rax, rdx
0x18000ff9b  mov     [rbp+var_30.Data1], 0
0x18000ffa2  mov     rdi, rcx
0x18000ffa5  lea     r9, [rbp+var_30]; struct _GUID *
0x18000ffa9  xorps   xmm0, xmm0
0x18000ffac  lea     r8, [rbp+var_18]; struct _GUID *
0x18000ffb0  mov     rcx, rax; this
0x18000ffb3  xor     edx, edx; void *
0x18000ffb5  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000ffb9  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000ffbe  mov     rcx, rdi
0x18000ffc1  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000ffc6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000ffcb  mov     rbx, rax
0x18000ffce  mov     ecx, [rax]
0x18000ffd0  cmp     ecx, 5
0x18000ffd3  jbe     loc_18001008F
0x18000ffd9  mov     rdx, [rax+18h]
0x18000ffdd  mov     rcx, [rax+10h]
0x18000ffe1  mov     rax, 400000000000h
0x18000ffeb  test    rax, rcx
0x18000ffee  jz      loc_18001008F
0x18000fff4  mov     rcx, rdx
0x18000fff7  and     rcx, rax
0x18000fffa  cmp     rcx, rdx
0x18000fffd  jnz     loc_18001008F
0x180010003  mov     eax, [rbp+var_30.Data1]
0x180010006  mov     [rbp+var_30.Data1], eax
0x180010009  lea     rax, [rbp+var_18]
0x18001000d  mov     qword ptr [rbp+var_30.Data4], rax
0x180010011  call    cs:__imp_GetCurrentThreadId
0x180010018  nop     dword ptr [rax+rax+00h]
0x18001001d  mov     r8, [rdi+110h]
0x180010024  mov     dword ptr [rbp+var_30.Data2], eax
0x180010027  mov     [rbp+var_20], 0
0x18001002f  cmp     byte ptr [r8+4], 0
0x180010034  jz      short loc_180010055
0x180010036  lea     r9, [r8+18h]
0x18001003a  cmp     dword ptr [r9], 0
0x18001003e  jnz     short loc_180010058
0x180010040  cmp     dword ptr [r9+4], 0
0x180010045  jnz     short loc_180010058
0x180010047  cmp     dword ptr [r9+8], 0
0x18001004c  jnz     short loc_180010058
0x18001004e  cmp     dword ptr [r9+0Ch], 0
0x180010053  jnz     short loc_180010058
0x180010055  xor     r9d, r9d
0x180010058  lea     rax, [rbp+var_30]
0x18001005c  add     r8, 8
0x180010060  mov     [rsp+70h+var_38], rax
0x180010065  lea     rdx, unk_18003B398
0x18001006c  lea     rax, [rbp+var_30.Data4]
0x180010070  mov     rcx, rbx
0x180010073  mov     [rsp+70h+var_40], rax
0x180010078  lea     rax, [rbp+var_30.Data2]
0x18001007c  mov     [rsp+70h+var_48], rax
0x180010081  lea     rax, [rbp+var_20]
0x180010085  mov     [rsp+70h+var_50], rax
0x18001008a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001008f  lea     rcx, [rdi+120h]; this
0x180010096  cmp     dword ptr [rcx+18h], 0
0x18001009a  jnz     short loc_1800100A1
0x18001009c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800100a1  mov     rcx, [rbp+var_8]
0x1800100a5  xor     rcx, rsp; StackCookie
0x1800100a8  call    __security_check_cookie
0x1800100ad  lea     r11, [rsp+70h+var_s0]
0x1800100b2  mov     rbx, [r11+20h]
0x1800100b6  mov     rdi, [r11+28h]
0x1800100ba  mov     rsp, r11
0x1800100bd  pop     rbp
0x1800100be  retn
```
