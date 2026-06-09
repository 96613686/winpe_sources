# ContainerProvider::ReadXmlString::StartActivity(void)

- ea: `0x180020bc4`
- end: `0x180020cc4`
- name: `?StartActivity@ReadXmlString@ContainerProvider@@QEAAXXZ`
- size: `256`
- prototype: `void __fastcall(ContainerProvider::ReadXmlString *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180022580`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x18000abe4`
- `0x1800120f0`
- `0x180020bc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bfe`

## pseudocode

```c
void __fastcall ContainerProvider::ReadXmlString::StartActivity(ContainerProvider::ReadXmlString *this)
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
      (unsigned __int8 *)word_18003C852,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::ReadXmlString *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x180020bc4  mov     [rsp+arg_8], rbx
0x180020bc9  push    rdi
0x180020bca  sub     rsp, 90h
0x180020bd1  mov     rax, cs:__security_cookie
0x180020bd8  xor     rax, rsp
0x180020bdb  mov     [rsp+98h+var_18], rax
0x180020be3  mov     rbx, rcx
0x180020be6  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020beb  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180020bf0  mov     rdi, rax
0x180020bf3  mov     edx, [rax]
0x180020bf5  cmp     edx, 5
0x180020bf8  jbe     loc_180020C8F
0x180020bfe  call    cs:__imp_GetCurrentThreadId
0x180020c05  nop     dword ptr [rax+rax+00h]
0x180020c0a  mov     [rsp+98h+var_68], eax
0x180020c0e  mov     [rsp+98h+var_60], 0
0x180020c17  mov     r8, [rbx+110h]
0x180020c1e  cmp     byte ptr [r8+4], 0
0x180020c23  jz      short loc_180020C44
0x180020c25  lea     r9, [r8+18h]
0x180020c29  cmp     dword ptr [r9], 0
0x180020c2d  jnz     short loc_180020C47
0x180020c2f  cmp     dword ptr [r9+4], 0
0x180020c34  jnz     short loc_180020C47
0x180020c36  cmp     dword ptr [r9+8], 0
0x180020c3b  jnz     short loc_180020C47
0x180020c3d  cmp     dword ptr [r9+0Ch], 0
0x180020c42  jnz     short loc_180020C47
0x180020c44  xor     r9d, r9d
0x180020c47  lea     rax, [rsp+98h+var_68]
0x180020c4c  mov     [rsp+98h+var_28], rax
0x180020c51  mov     ecx, 4
0x180020c56  mov     [rsp+98h+var_20], rcx
0x180020c5b  lea     rax, [rsp+98h+var_60]
0x180020c60  mov     [rsp+98h+var_38], rax
0x180020c65  mov     [rsp+98h+var_30], 8
0x180020c6e  add     r8, 8
0x180020c72  lea     rax, [rsp+98h+var_58]
0x180020c77  mov     [rsp+98h+var_70], rax
0x180020c7c  mov     [rsp+98h+var_78], ecx
0x180020c80  lea     rdx, word_18003C852
0x180020c87  mov     rcx, rdi
0x180020c8a  call    _tlgWriteTransfer_EventWriteTransfer
0x180020c8f  lea     rcx, [rbx+120h]; this
0x180020c96  cmp     dword ptr [rcx+18h], 0
0x180020c9a  jnz     short loc_180020CA2
0x180020c9c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180020ca1  nop
0x180020ca2  mov     rcx, [rsp+98h+var_18]
0x180020caa  xor     rcx, rsp; StackCookie
0x180020cad  call    __security_check_cookie
0x180020cb2  mov     rbx, [rsp+98h+arg_8]
0x180020cba  add     rsp, 90h
0x180020cc1  pop     rdi
0x180020cc2  retn
```
