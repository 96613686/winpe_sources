# container::SetRegistryFlushState(void *,uchar)

- ea: `0x18000f560`
- end: `0x18000f618`
- name: `?SetRegistryFlushState@container@@YAXPEAXE@Z`
- size: `184`
- prototype: `void __fastcall(container *this, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180012590`

## callees

- `0x180002ad0`
- `0x18000cf64`
- `0x18000d028`
- `0x18000dc48`
- `0x1800100c8`
- `0x180010418`
- `0x1800297b4`

## string_xrefs

- `0x18000f589`: `SetRegistryFlushState`

## pseudocode

```c
void __fastcall container::SetRegistryFlushState(container *this, void *a2, __int64 a3, __int64 a4)
{
  char v4; // bl
  unsigned int v6; // r9d
  _QWORD v7[42]; // [rsp+20h] [rbp-168h] BYREF

  v4 = (char)a2;
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v7,
    "SetRegistryFlushState",
    a3,
    a4);
  v7[0] = &ContainerProvider::SetRegistryFlushState::`vftable';
  ContainerProvider::SetRegistryFlushState::StartActivity((ContainerProvider::SetRegistryFlushState *)v7, this);
  container::RegistryProvider::ModifyFlags(this, (void *)(v4 == 0), v4 != 0, v6);
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v7, 0);
  v7[0] = &ContainerProvider::SetRegistryFlushState::`vftable';
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v7);
}

```

## disassembly

```asm
0x18000f560  mov     [rsp+arg_8], rbx
0x18000f565  mov     [rsp+arg_10], rsi
0x18000f56a  push    rdi
0x18000f56b  sub     rsp, 180h
0x18000f572  mov     rax, cs:__security_cookie
0x18000f579  xor     rax, rsp
0x18000f57c  mov     [rsp+188h+var_18], rax
0x18000f584  mov     bl, dl
0x18000f586  mov     rdi, rcx
0x18000f589  lea     rdx, aSetregistryflu_0; "SetRegistryFlushState"
0x18000f590  lea     rcx, [rsp+188h+var_168]
0x18000f595  call    ??0?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f59a  lea     rsi, ??_7SetRegistryFlushState@ContainerProvider@@6B@; const ContainerProvider::SetRegistryFlushState::`vftable'
0x18000f5a1  mov     [rsp+188h+var_168], rsi
0x18000f5a6  mov     rdx, rdi; void *
0x18000f5a9  lea     rcx, [rsp+188h+var_168]; this
0x18000f5ae  call    ?StartActivity@SetRegistryFlushState@ContainerProvider@@QEAAXPEAX@Z; ContainerProvider::SetRegistryFlushState::StartActivity(void *)
0x18000f5b3  nop
0x18000f5b4  xor     r8d, r8d
0x18000f5b7  test    bl, bl
0x18000f5b9  setnz   r8b; unsigned int
0x18000f5bd  xor     edx, edx
0x18000f5bf  test    bl, bl
0x18000f5c1  setz    dl; void *
0x18000f5c4  mov     rcx, rdi; this
0x18000f5c7  call    ?ModifyFlags@RegistryProvider@container@@YAXPEAXKK@Z; container::RegistryProvider::ModifyFlags(void *,ulong,ulong)
0x18000f5cc  xor     edx, edx
0x18000f5ce  lea     rcx, [rsp+188h+var_168]
0x18000f5d3  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000f5d8  nop
0x18000f5d9  mov     [rsp+188h+var_168], rsi
0x18000f5de  lea     rcx, [rsp+188h+var_168]
0x18000f5e3  call    ?Destroy@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000f5e8  lea     rcx, [rsp+188h+var_168]
0x18000f5ed  call    ??1?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000f5f2  mov     rcx, [rsp+188h+var_18]
0x18000f5fa  xor     rcx, rsp; StackCookie
0x18000f5fd  call    __security_check_cookie
0x18000f602  lea     r11, [rsp+188h+var_8]
0x18000f60a  mov     rbx, [r11+18h]
0x18000f60e  mov     rsi, [r11+20h]
0x18000f612  mov     rsp, r11
0x18000f615  pop     rdi
0x18000f616  retn
```
