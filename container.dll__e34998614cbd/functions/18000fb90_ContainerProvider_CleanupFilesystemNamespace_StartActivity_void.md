# ContainerProvider::CleanupFilesystemNamespace::StartActivity(void)

- ea: `0x18000fb90`
- end: `0x18000fc90`
- name: `?StartActivity@CleanupFilesystemNamespace@ContainerProvider@@QEAAXXZ`
- size: `256`
- prototype: `void __fastcall(ContainerProvider::CleanupFilesystemNamespace *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000da40`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x18000abe4`
- `0x18000fb90`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbca`

## pseudocode

```c
void __fastcall ContainerProvider::CleanupFilesystemNamespace::StartActivity(
        ContainerProvider::CleanupFilesystemNamespace *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  const GUID *v5; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v7; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v2 = ContainerProvider::Provider();
  v3 = *(unsigned int *)v2;
  if ( (unsigned int)v3 > 5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = (const GUID *)(v4 + 24), !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v2,
      (unsigned __int8 *)byte_18003C19D,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::CleanupFilesystemNamespace *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x18000fb90  mov     [rsp+arg_8], rbx
0x18000fb95  push    rdi
0x18000fb96  sub     rsp, 90h
0x18000fb9d  mov     rax, cs:__security_cookie
0x18000fba4  xor     rax, rsp
0x18000fba7  mov     [rsp+98h+var_18], rax
0x18000fbaf  mov     rbx, rcx
0x18000fbb2  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000fbb7  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000fbbc  mov     rdi, rax
0x18000fbbf  mov     edx, [rax]
0x18000fbc1  cmp     edx, 5
0x18000fbc4  jbe     loc_18000FC5B
0x18000fbca  call    cs:__imp_GetCurrentThreadId
0x18000fbd1  nop     dword ptr [rax+rax+00h]
0x18000fbd6  mov     [rsp+98h+var_68], eax
0x18000fbda  mov     [rsp+98h+var_60], 0
0x18000fbe3  mov     r8, [rbx+110h]
0x18000fbea  cmp     byte ptr [r8+4], 0
0x18000fbef  jz      short loc_18000FC10
0x18000fbf1  lea     r9, [r8+18h]
0x18000fbf5  cmp     dword ptr [r9], 0
0x18000fbf9  jnz     short loc_18000FC13
0x18000fbfb  cmp     dword ptr [r9+4], 0
0x18000fc00  jnz     short loc_18000FC13
0x18000fc02  cmp     dword ptr [r9+8], 0
0x18000fc07  jnz     short loc_18000FC13
0x18000fc09  cmp     dword ptr [r9+0Ch], 0
0x18000fc0e  jnz     short loc_18000FC13
0x18000fc10  xor     r9d, r9d
0x18000fc13  lea     rax, [rsp+98h+var_68]
0x18000fc18  mov     [rsp+98h+var_28], rax
0x18000fc1d  mov     ecx, 4
0x18000fc22  mov     [rsp+98h+var_20], rcx
0x18000fc27  lea     rax, [rsp+98h+var_60]
0x18000fc2c  mov     [rsp+98h+var_38], rax
0x18000fc31  mov     [rsp+98h+var_30], 8
0x18000fc3a  add     r8, 8
0x18000fc3e  lea     rax, [rsp+98h+var_58]
0x18000fc43  mov     [rsp+98h+var_70], rax
0x18000fc48  mov     [rsp+98h+var_78], ecx
0x18000fc4c  lea     rdx, byte_18003C19D
0x18000fc53  mov     rcx, rdi
0x18000fc56  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fc5b  lea     rcx, [rbx+120h]; this
0x18000fc62  cmp     dword ptr [rcx+18h], 0
0x18000fc66  jnz     short loc_18000FC6E
0x18000fc68  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000fc6d  nop
0x18000fc6e  mov     rcx, [rsp+98h+var_18]
0x18000fc76  xor     rcx, rsp; StackCookie
0x18000fc79  call    __security_check_cookie
0x18000fc7e  mov     rbx, [rsp+98h+arg_8]
0x18000fc86  add     rsp, 90h
0x18000fc8d  pop     rdi
0x18000fc8e  retn
```
