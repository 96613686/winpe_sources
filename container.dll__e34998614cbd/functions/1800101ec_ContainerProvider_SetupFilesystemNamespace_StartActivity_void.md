# ContainerProvider::SetupFilesystemNamespace::StartActivity(void)

- ea: `0x1800101ec`
- end: `0x1800102ec`
- name: `?StartActivity@SetupFilesystemNamespace@ContainerProvider@@QEAAXXZ`
- size: `256`
- prototype: `void __fastcall(ContainerProvider::SetupFilesystemNamespace *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000f620`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x18000abe4`
- `0x1800101ec`
- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010226`

## pseudocode

```c
void __fastcall ContainerProvider::SetupFilesystemNamespace::StartActivity(
        ContainerProvider::SetupFilesystemNamespace *this)
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
      (unsigned __int8 *)&unk_18003B210,
      (const GUID *)(v4 + 8),
      v5,
      4u,
      &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ContainerProvider::SetupFilesystemNamespace *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x1800101ec  mov     [rsp+arg_8], rbx
0x1800101f1  push    rdi
0x1800101f2  sub     rsp, 90h
0x1800101f9  mov     rax, cs:__security_cookie
0x180010200  xor     rax, rsp
0x180010203  mov     [rsp+98h+var_18], rax
0x18001020b  mov     rbx, rcx
0x18001020e  call    ?zInternalStart@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180010213  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010218  mov     rdi, rax
0x18001021b  mov     edx, [rax]
0x18001021d  cmp     edx, 5
0x180010220  jbe     loc_1800102B7
0x180010226  call    cs:__imp_GetCurrentThreadId
0x18001022d  nop     dword ptr [rax+rax+00h]
0x180010232  mov     [rsp+98h+var_68], eax
0x180010236  mov     [rsp+98h+var_60], 0
0x18001023f  mov     r8, [rbx+110h]
0x180010246  cmp     byte ptr [r8+4], 0
0x18001024b  jz      short loc_18001026C
0x18001024d  lea     r9, [r8+18h]
0x180010251  cmp     dword ptr [r9], 0
0x180010255  jnz     short loc_18001026F
0x180010257  cmp     dword ptr [r9+4], 0
0x18001025c  jnz     short loc_18001026F
0x18001025e  cmp     dword ptr [r9+8], 0
0x180010263  jnz     short loc_18001026F
0x180010265  cmp     dword ptr [r9+0Ch], 0
0x18001026a  jnz     short loc_18001026F
0x18001026c  xor     r9d, r9d
0x18001026f  lea     rax, [rsp+98h+var_68]
0x180010274  mov     [rsp+98h+var_28], rax
0x180010279  mov     ecx, 4
0x18001027e  mov     [rsp+98h+var_20], rcx
0x180010283  lea     rax, [rsp+98h+var_60]
0x180010288  mov     [rsp+98h+var_38], rax
0x18001028d  mov     [rsp+98h+var_30], 8
0x180010296  add     r8, 8
0x18001029a  lea     rax, [rsp+98h+var_58]
0x18001029f  mov     [rsp+98h+var_70], rax
0x1800102a4  mov     [rsp+98h+var_78], ecx
0x1800102a8  lea     rdx, unk_18003B210
0x1800102af  mov     rcx, rdi
0x1800102b2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800102b7  lea     rcx, [rbx+120h]; this
0x1800102be  cmp     dword ptr [rcx+18h], 0
0x1800102c2  jnz     short loc_1800102CA
0x1800102c4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800102c9  nop
0x1800102ca  mov     rcx, [rsp+98h+var_18]
0x1800102d2  xor     rcx, rsp; StackCookie
0x1800102d5  call    __security_check_cookie
0x1800102da  mov     rbx, [rsp+98h+arg_8]
0x1800102e2  add     rsp, 90h
0x1800102e9  pop     rdi
0x1800102ea  retn
```
