# ContainerProvider::SetRegistryFlushState::StartActivity(void *)

- ea: `0x1800100c8`
- end: `0x1800101e6`
- name: `?StartActivity@SetRegistryFlushState@ContainerProvider@@QEAAXPEAX@Z`
- size: `286`
- prototype: `void(ContainerProvider::SetRegistryFlushState *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000f560`

## callees

- `0x180001eb4`
- `0x180002ad0`
- `0x180006e98`
- `0x18000895c`
- `0x18000abe4`
- `0x1800100c8`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010137`

## pseudocode

```c
void __fastcall ContainerProvider::SetRegistryFlushState::StartActivity(
        ContainerProvider::SetRegistryFlushState *this,
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
      (unsigned int)&dword_18003C6C4,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&v10.Data2,
      (__int64)v10.Data4,
      (__int64)&v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::SetRegistryFlushState *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x1800100c8  mov     [rsp-8+arg_10], rbx
0x1800100cd  mov     [rsp-8+arg_18], rdi
0x1800100d2  push    rbp
0x1800100d3  mov     rbp, rsp
0x1800100d6  sub     rsp, 70h
0x1800100da  mov     rax, cs:__security_cookie
0x1800100e1  xor     rax, rsp
0x1800100e4  mov     [rbp+var_8], rax
0x1800100e8  mov     rax, rdx
0x1800100eb  mov     [rbp+var_30.Data1], 0
0x1800100f2  mov     rbx, rcx
0x1800100f5  lea     r9, [rbp+var_30]; struct _GUID *
0x1800100f9  xorps   xmm0, xmm0
0x1800100fc  lea     r8, [rbp+var_18]; struct _GUID *
0x180010100  mov     rcx, rax; this
0x180010103  xor     edx, edx; void *
0x180010105  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x180010109  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18001010e  mov     rcx, rbx
0x180010111  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180010116  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001011b  mov     rdi, rax
0x18001011e  mov     ecx, [rax]
0x180010120  cmp     ecx, 5
0x180010123  jbe     loc_1800101B5
0x180010129  mov     ecx, [rbp+var_30.Data1]
0x18001012c  lea     rax, [rbp+var_18]
0x180010130  mov     qword ptr [rbp+var_30.Data4], rax
0x180010134  mov     [rbp+var_30.Data1], ecx
0x180010137  call    cs:__imp_GetCurrentThreadId
0x18001013e  nop     dword ptr [rax+rax+00h]
0x180010143  mov     r8, [rbx+110h]
0x18001014a  mov     dword ptr [rbp+var_30.Data2], eax
0x18001014d  mov     [rbp+var_20], 0
0x180010155  cmp     byte ptr [r8+4], 0
0x18001015a  jz      short loc_18001017B
0x18001015c  lea     r9, [r8+18h]
0x180010160  cmp     dword ptr [r9], 0
0x180010164  jnz     short loc_18001017E
0x180010166  cmp     dword ptr [r9+4], 0
0x18001016b  jnz     short loc_18001017E
0x18001016d  cmp     dword ptr [r9+8], 0
0x180010172  jnz     short loc_18001017E
0x180010174  cmp     dword ptr [r9+0Ch], 0
0x180010179  jnz     short loc_18001017E
0x18001017b  xor     r9d, r9d
0x18001017e  lea     rax, [rbp+var_30]
0x180010182  add     r8, 8
0x180010186  mov     [rsp+70h+var_38], rax
0x18001018b  lea     rdx, dword_18003C6C4
0x180010192  lea     rax, [rbp+var_30.Data4]
0x180010196  mov     rcx, rdi
0x180010199  mov     [rsp+70h+var_40], rax
0x18001019e  lea     rax, [rbp+var_30.Data2]
0x1800101a2  mov     [rsp+70h+var_48], rax
0x1800101a7  lea     rax, [rbp+var_20]
0x1800101ab  mov     [rsp+70h+var_50], rax
0x1800101b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800101b5  lea     rcx, [rbx+120h]; this
0x1800101bc  cmp     dword ptr [rcx+18h], 0
0x1800101c0  jnz     short loc_1800101C7
0x1800101c2  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800101c7  mov     rcx, [rbp+var_8]
0x1800101cb  xor     rcx, rsp; StackCookie
0x1800101ce  call    __security_check_cookie
0x1800101d3  lea     r11, [rsp+70h+var_s0]
0x1800101d8  mov     rbx, [r11+20h]
0x1800101dc  mov     rdi, [r11+28h]
0x1800101e0  mov     rsp, r11
0x1800101e3  pop     rbp
0x1800101e4  retn
```
