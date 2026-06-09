# CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)

- ea: `0x180007888`
- end: `0x180007991`
- name: `?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z`
- size: `265`
- prototype: `void __fastcall(OLECHAR *psz, struct CConfigServiceProvider2Impl *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800077cc`
- `0x18000781c`

## callees

- `0x180007888`
- `0x180007b84`
- `0x180007ba4`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800078c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800078c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000791c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000791c`
- `OLEAUT32!__imp_VariantInit` at `0x1800078ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800078ed`

## string_xrefs

- `0x180007958`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x18000796d`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x18000797f`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CProvisioningCommandsNode::GetSessionVariableFromCsp(
        OLECHAR *psz,
        struct CConfigServiceProvider2Impl *a2,
        struct tagVARIANT *a3)
{
  int v5; // eax
  OLECHAR *v6; // rbx
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF
  OLECHAR *v13; // [rsp+48h] [rbp+20h]

  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(struct CConfigServiceProvider2Impl *, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v12);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
      (const char *)(unsigned int)v5,
      v10);
  v6 = SysAllocString(psz);
  v13 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x13E,
      (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
      v7);
  VariantInit(a3);
  v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, struct tagVARIANT *))(*(_QWORD *)v12 + 32LL))(v12, v6, a3);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
      (const char *)(unsigned int)v8,
      v10);
  SysFreeString(v6);
  v9 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
}

```

## disassembly

```asm
0x180007888  mov     [rsp+arg_0], rbx
0x18000788d  push    rdi; int
0x18000788e  sub     rsp, 20h
0x180007892  mov     rdi, r8
0x180007895  mov     r9, rdx
0x180007898  mov     rbx, rcx
0x18000789b  mov     [rsp+28h+arg_8], 0
0x1800078a4  mov     rax, [rdx]
0x1800078a7  lea     rdx, [rsp+28h+arg_8]
0x1800078ac  mov     rcx, r9
0x1800078af  mov     rax, [rax+30h]
0x1800078b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b8  mov     rcx, [rsp+28h]; this
0x1800078bd  test    eax, eax
0x1800078bf  js      loc_18000796A
0x1800078c5  mov     rcx, rbx; psz
0x1800078c8  call    cs:__imp_SysAllocString
0x1800078cf  nop     dword ptr [rax+rax+00h]
0x1800078d4  mov     rbx, rax
0x1800078d7  mov     [rsp+28h+arg_18], rax
0x1800078dc  mov     rcx, [rsp+28h]; this
0x1800078e1  test    rax, rax
0x1800078e4  jz      loc_18000797F
0x1800078ea  mov     rcx, rdi; pvarg
0x1800078ed  call    cs:__imp_VariantInit
0x1800078f4  nop     dword ptr [rax+rax+00h]
0x1800078f9  mov     rcx, [rsp+28h+arg_8]
0x1800078fe  mov     rax, [rcx]
0x180007901  mov     r8, rdi
0x180007904  mov     rdx, rbx
0x180007907  mov     rax, [rax+20h]
0x18000790b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007910  mov     rcx, [rsp+28h]; this
0x180007915  test    eax, eax
0x180007917  js      short loc_180007955
0x180007919  mov     rcx, rbx; bstrString
0x18000791c  call    cs:__imp_SysFreeString
0x180007923  nop     dword ptr [rax+rax+00h]
0x180007928  nop
0x180007929  mov     rcx, [rsp+28h+arg_8]
0x18000792e  test    rcx, rcx
0x180007931  jz      short loc_180007949
0x180007933  mov     [rsp+28h+arg_8], 0
0x18000793c  mov     rax, [rcx]
0x18000793f  mov     rax, [rax+10h]
0x180007943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007948  nop
0x180007949  mov     rbx, [rsp+28h+arg_0]
0x18000794e  add     rsp, 20h
0x180007952  pop     rdi
0x180007953  retn
0x180007955  mov     r9d, eax; char *
0x180007958  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000795f  mov     edx, 141h; void *
0x180007964  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000796a  mov     r9d, eax; char *
0x18000796d  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180007974  mov     edx, 13Bh; void *
0x180007979  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000797f  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180007986  mov     edx, 13Eh; void *
0x18000798b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
