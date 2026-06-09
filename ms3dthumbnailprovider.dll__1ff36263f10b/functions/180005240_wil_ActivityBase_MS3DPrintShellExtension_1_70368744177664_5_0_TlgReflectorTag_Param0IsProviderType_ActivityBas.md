# wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180005240`
- end: `0x1800052b1`
- name: `??1?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180005624`

## callees

- `0x180001f44`
- `0x180005240`
- `0x1800052b8`
- `0x1800057b0`

## pseudocode

```c
void __fastcall wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rcx
  void *v3; // rdi

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v2 = *(volatile signed __int32 **)(a1 + 280);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *(void **)(a1 + 280);
      if ( v3 )
      {
        wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>((__int64)v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180005240  mov     [rsp+arg_0], rbx
0x180005245  push    rdi
0x180005246  sub     rsp, 20h
0x18000524a  mov     rbx, rcx
0x18000524d  add     rcx, 120h; this
0x180005254  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180005259  mov     rcx, [rbx+118h]
0x180005260  test    rcx, rcx
0x180005263  jz      short loc_18000529E
0x180005265  or      eax, 0FFFFFFFFh
0x180005268  lock xadd [rcx], eax
0x18000526c  cmp     eax, 1
0x18000526f  jnz     short loc_180005293
0x180005271  mov     rdi, [rbx+118h]
0x180005278  test    rdi, rdi
0x18000527b  jz      short loc_180005293
0x18000527d  lea     rcx, [rdi+8]
0x180005281  call    ??1?$ActivityData@VMS3DPrintShellExtension@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005286  mov     edx, 110h
0x18000528b  mov     rcx, rdi; Block
0x18000528e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005293  mov     qword ptr [rbx+118h], 0
0x18000529e  lea     rcx, [rbx+8]
0x1800052a2  mov     rbx, [rsp+28h+arg_0]
0x1800052a7  add     rsp, 20h
0x1800052ab  pop     rdi
0x1800052ac  jmp     ??1?$ActivityData@VMS3DPrintShellExtension@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(void)
```
