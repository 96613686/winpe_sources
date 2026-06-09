# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StartActivity(void)

- ea: `0x18000fa98`
- end: `0x18000fbc1`
- name: `?StartActivity@ComputeStorage_HcsGetLayerVhdMountPath@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ`
- size: `297`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180014e80`

## callees

- `0x180001ed0`
- `0x180002690`
- `0x18000b9b4`
- `0x18000fa98`
- `0x18000ff58`
- `0x180013e8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000faf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000faf8`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StartActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *this)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  const GUID *v4; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = *((_QWORD *)ComputeStorage::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v2 > 4u
    && (*(_QWORD *)(v2 + 16) & 0x20040LL) != 0
    && (*(_QWORD *)(v2 + 24) & 0x20040LL) == *(_QWORD *)(v2 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = (const GUID *)(v3 + 24), !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v11 = 4;
    v8 = &v6;
    v9 = 8;
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)&dword_180053694, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000fa98  mov     [rsp+arg_8], rbx
0x18000fa9d  push    rdi
0x18000fa9e  sub     rsp, 90h
0x18000faa5  mov     rax, cs:__security_cookie
0x18000faac  xor     rax, rsp
0x18000faaf  mov     [rsp+98h+var_18], rax
0x18000fab7  mov     rbx, rcx
0x18000faba  call    ?zInternalStart@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000fabf  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18000fac4  mov     rdi, [rax+8]
0x18000fac8  mov     eax, [rdi]
0x18000faca  cmp     eax, 4
0x18000facd  jbe     loc_18000FB8C
0x18000fad3  mov     rcx, [rdi+18h]
0x18000fad7  mov     rax, [rdi+10h]
0x18000fadb  mov     edx, 20040h
0x18000fae0  test    rdx, rax
0x18000fae3  jz      loc_18000FB8C
0x18000fae9  mov     rax, rcx
0x18000faec  and     rax, rdx
0x18000faef  cmp     rax, rcx
0x18000faf2  jnz     loc_18000FB8C
0x18000faf8  call    cs:__imp_GetCurrentThreadId
0x18000faff  nop     dword ptr [rax+rax+00h]
0x18000fb04  mov     [rsp+98h+var_68], eax
0x18000fb08  mov     [rsp+98h+var_60], 0
0x18000fb11  mov     r8, [rbx+110h]
0x18000fb18  cmp     byte ptr [r8+4], 0
0x18000fb1d  jz      short loc_18000FB3E
0x18000fb1f  lea     r9, [r8+18h]
0x18000fb23  cmp     dword ptr [r9], 0
0x18000fb27  jnz     short loc_18000FB41
0x18000fb29  cmp     dword ptr [r9+4], 0
0x18000fb2e  jnz     short loc_18000FB41
0x18000fb30  cmp     dword ptr [r9+8], 0
0x18000fb35  jnz     short loc_18000FB41
0x18000fb37  cmp     dword ptr [r9+0Ch], 0
0x18000fb3c  jnz     short loc_18000FB41
0x18000fb3e  xor     r9d, r9d; int
0x18000fb41  lea     rax, [rsp+98h+var_68]
0x18000fb46  mov     [rsp+98h+var_28], rax
0x18000fb4b  mov     [rsp+98h+var_20], 4
0x18000fb54  lea     rax, [rsp+98h+var_60]
0x18000fb59  mov     [rsp+98h+var_38], rax
0x18000fb5e  mov     [rsp+98h+var_30], 8
0x18000fb67  add     r8, 8; int
0x18000fb6b  lea     rax, [rsp+98h+var_58]
0x18000fb70  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18000fb75  mov     [rsp+98h+var_78], 4; ULONG
0x18000fb7d  lea     rdx, dword_180053694; int
0x18000fb84  mov     rcx, rdi; int
0x18000fb87  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fb8c  lea     rcx, [rbx+120h]; this
0x18000fb93  cmp     dword ptr [rcx+18h], 0
0x18000fb97  jnz     short loc_18000FB9F
0x18000fb99  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000fb9e  nop
0x18000fb9f  mov     rcx, [rsp+98h+var_18]
0x18000fba7  xor     rcx, rsp; StackCookie
0x18000fbaa  call    __security_check_cookie
0x18000fbaf  mov     rbx, [rsp+98h+arg_8]
0x18000fbb7  add     rsp, 90h
0x18000fbbe  pop     rdi
0x18000fbbf  retn
```
