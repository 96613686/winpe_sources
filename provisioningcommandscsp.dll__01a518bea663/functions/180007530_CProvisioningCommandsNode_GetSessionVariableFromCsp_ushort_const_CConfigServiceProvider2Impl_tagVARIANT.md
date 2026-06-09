# CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)

- ea: `0x180007530`
- end: `0x180007626`
- name: `?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z`
- size: `246`
- prototype: `void __fastcall(OLECHAR *psz, struct CConfigServiceProvider2Impl *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000747c`
- `0x1800074c4`

## callees

- `0x180007530`
- `0x180007800`
- `0x180007820`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007570`
- `OLEAUT32!__imp_SysAllocString` at `0x180007570`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075b8`
- `OLEAUT32!__imp_VariantInit` at `0x18000758f`
- `OLEAUT32!__imp_VariantInit` at `0x18000758f`

## string_xrefs

- `0x1800075ed`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x180007602`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x180007614`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
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
0x180007530  mov     [rsp+arg_0], rbx
0x180007535  push    rdi; int
0x180007536  sub     rsp, 20h
0x18000753a  mov     rdi, r8
0x18000753d  mov     r9, rdx
0x180007540  mov     rbx, rcx
0x180007543  mov     [rsp+28h+arg_8], 0
0x18000754c  mov     rax, [rdx]
0x18000754f  lea     rdx, [rsp+28h+arg_8]
0x180007554  mov     rcx, r9
0x180007557  mov     rax, [rax+30h]
0x18000755b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007560  mov     rcx, [rsp+28h]; this
0x180007565  test    eax, eax
0x180007567  js      loc_1800075FF
0x18000756d  mov     rcx, rbx; psz
0x180007570  call    cs:__imp_SysAllocString
0x180007576  mov     rbx, rax
0x180007579  mov     [rsp+28h+arg_18], rax
0x18000757e  mov     rcx, [rsp+28h]; this
0x180007583  test    rax, rax
0x180007586  jz      loc_180007614
0x18000758c  mov     rcx, rdi; pvarg
0x18000758f  call    cs:__imp_VariantInit
0x180007595  mov     rcx, [rsp+28h+arg_8]
0x18000759a  mov     rax, [rcx]
0x18000759d  mov     r8, rdi
0x1800075a0  mov     rdx, rbx
0x1800075a3  mov     rax, [rax+20h]
0x1800075a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ac  mov     rcx, [rsp+28h]; this
0x1800075b1  test    eax, eax
0x1800075b3  js      short loc_1800075EA
0x1800075b5  mov     rcx, rbx; bstrString
0x1800075b8  call    cs:__imp_SysFreeString
0x1800075be  nop
0x1800075bf  mov     rcx, [rsp+28h+arg_8]
0x1800075c4  test    rcx, rcx
0x1800075c7  jz      short loc_1800075DF
0x1800075c9  mov     [rsp+28h+arg_8], 0
0x1800075d2  mov     rax, [rcx]
0x1800075d5  mov     rax, [rax+10h]
0x1800075d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075de  nop
0x1800075df  mov     rbx, [rsp+28h+arg_0]
0x1800075e4  add     rsp, 20h
0x1800075e8  pop     rdi
0x1800075e9  retn
0x1800075ea  mov     r9d, eax; char *
0x1800075ed  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x1800075f4  mov     edx, 141h; void *
0x1800075f9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800075ff  mov     r9d, eax; char *
0x180007602  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180007609  mov     edx, 13Bh; void *
0x18000760e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007614  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000761b  mov     edx, 13Eh; void *
0x180007620  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
