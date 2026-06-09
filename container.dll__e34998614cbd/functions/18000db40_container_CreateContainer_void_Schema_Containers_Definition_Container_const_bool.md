# container::CreateContainer(void *,Schema::Containers::Definition::Container const &,bool)

- ea: `0x18000db40`
- end: `0x18000dc42`
- name: `?CreateContainer@container@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z`
- size: `258`
- prototype: `void __fastcall(container *this, char *, const struct Schema::Containers::Definition::Container *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180012250`

## callees

- `0x180002ad0`
- `0x1800063f0`
- `0x18000cf64`
- `0x18000d028`
- `0x18000d134`
- `0x18000db40`
- `0x18000dc48`
- `0x18000fe54`
- `0x180010418`
- `0x180023900`

## string_xrefs

- `0x18000db73`: `CreateContainer`

## pseudocode

```c
void __fastcall container::CreateContainer(
        container *this,
        char *a2,
        const struct Schema::Containers::Definition::Container *a3,
        __int64 a4)
{
  char v4; // bl
  const struct Schema::Containers::Definition::Container *v6; // r8
  bool v7; // r9
  container_runtime *v8; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v9[2]; // [rsp+28h] [rbp-D8h] BYREF
  char v10; // [rsp+38h] [rbp-C8h]
  _QWORD v11[42]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = (char)a3;
  v8 = this;
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "CreateContainer",
    a3,
    a4);
  v11[0] = &ContainerProvider::CreateContainer::`vftable';
  ContainerProvider::CreateContainer::StartActivity((ContainerProvider::CreateContainer *)v11, v8);
  LOBYTE(v6) = v4;
  container_runtime::CreateContainerObject(v8, a2, v6, v7);
  v9[0] = &v8;
  v9[1] = a2;
  v10 = 1;
  if ( v4 && a2[592] )
    container::DownlevelProvider::InjectHostFiles(a2 + 568, a2 + 536, v8);
  v10 = 0;
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, 0);
  wil::details::lambda_call__lambda_145ea1ab3e93ef5529c0a1d1da3448ef___::_lambda_call__lambda_145ea1ab3e93ef5529c0a1d1da3448ef___(v9);
  v11[0] = &ContainerProvider::CreateContainer::`vftable';
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v11);
}

```

## disassembly

```asm
0x18000db40  mov     [rsp-8+arg_10], rbx
0x18000db45  push    rbp
0x18000db46  push    rsi
0x18000db47  push    rdi
0x18000db48  lea     rbp, [rsp-0A0h]
0x18000db50  sub     rsp, 1A0h
0x18000db57  mov     rax, cs:__security_cookie
0x18000db5e  xor     rax, rsp
0x18000db61  mov     [rbp+0B0h+var_20], rax
0x18000db68  mov     bl, r8b
0x18000db6b  mov     rdi, rdx
0x18000db6e  mov     [rsp+1B0h+var_190], rcx
0x18000db73  lea     rdx, aCreatecontaine_0; "CreateContainer"
0x18000db7a  lea     rcx, [rsp+1B0h+var_170]
0x18000db7f  call    ??0?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000db84  lea     rsi, ??_7CreateContainer@ContainerProvider@@6B@; const ContainerProvider::CreateContainer::`vftable'
0x18000db8b  mov     [rsp+1B0h+var_170], rsi
0x18000db90  mov     rdx, [rsp+1B0h+var_190]; void *
0x18000db95  lea     rcx, [rsp+1B0h+var_170]; this
0x18000db9a  call    ?StartActivity@CreateContainer@ContainerProvider@@QEAAXPEAX@Z; ContainerProvider::CreateContainer::StartActivity(void *)
0x18000db9f  nop
0x18000dba0  mov     r8b, bl; struct Schema::Containers::Definition::Container *
0x18000dba3  mov     rdx, rdi; void *
0x18000dba6  mov     rcx, [rsp+1B0h+var_190]; this
0x18000dbab  call    ?CreateContainerObject@container_runtime@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z; container_runtime::CreateContainerObject(void *,Schema::Containers::Definition::Container const &,bool)
0x18000dbb0  lea     rax, [rsp+1B0h+var_190]
0x18000dbb5  mov     [rsp+1B0h+var_188], rax
0x18000dbba  mov     [rsp+1B0h+var_180], rdi
0x18000dbbf  mov     [rsp+1B0h+var_178], 1
0x18000dbc4  test    bl, bl
0x18000dbc6  jz      short loc_18000DBE9
0x18000dbc8  cmp     byte ptr [rdi+250h], 0
0x18000dbcf  jz      short loc_18000DBE9
0x18000dbd1  lea     rdx, [rdi+218h]
0x18000dbd8  lea     rcx, [rdi+238h]
0x18000dbdf  mov     r8, [rsp+1B0h+var_190]
0x18000dbe4  call    ?InjectHostFiles@DownlevelProvider@container@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX@Z; container::DownlevelProvider::InjectHostFiles(std::vector<std::wstring> const &,std::wstring const &,void *)
0x18000dbe9  mov     [rsp+1B0h+var_178], 0
0x18000dbee  xor     edx, edx
0x18000dbf0  lea     rcx, [rsp+1B0h+var_170]
0x18000dbf5  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000dbfa  nop
0x18000dbfb  lea     rcx, [rsp+1B0h+var_188]
0x18000dc00  call    wil__details__lambda_call__lambda_145ea1ab3e93ef5529c0a1d1da3448ef______lambda_call__lambda_145ea1ab3e93ef5529c0a1d1da3448ef___
0x18000dc05  nop
0x18000dc06  mov     [rsp+1B0h+var_170], rsi
0x18000dc0b  lea     rcx, [rsp+1B0h+var_170]
0x18000dc10  call    ?Destroy@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000dc15  lea     rcx, [rsp+1B0h+var_170]
0x18000dc1a  call    ??1?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000dc1f  mov     rcx, [rbp+0B0h+var_20]
0x18000dc26  xor     rcx, rsp; StackCookie
0x18000dc29  call    __security_check_cookie
0x18000dc2e  mov     rbx, [rsp+1B0h+arg_10]
0x18000dc36  add     rsp, 1A0h
0x18000dc3d  pop     rdi
0x18000dc3e  pop     rsi
0x18000dc3f  pop     rbp
0x18000dc40  retn
```
