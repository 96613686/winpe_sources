# ScriptEngineBase::ChangeTypeFromVar(void *,ushort,tagVARIANT *)

- ea: `0x18000c340`
- end: `0x18000c61e`
- name: `?ChangeTypeFromVar@ScriptEngineBase@@UEAAJPEAXGPEAUtagVARIANT@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(ScriptEngineBase *__hidden this, void *, unsigned __int16, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ba60`
- `0x18000c340`
- `0x18000d670`
- `0x18001aaa4`
- `0x1801681a4`
- `0x180168cf4`
- `0x1801a25bc`
- `0x18022fecc`
- `0x18043018c`
- `0x18043020c`
- `0x180442d18`
- `0x18044300c`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_controlfp_s` at `0x18000c484`
- `msvcrt!_controlfp_s` at `0x18000c484`
- `OLEAUT32!__imp_VariantInit` at `0x18000c3a3`
- `OLEAUT32!__imp_VariantInit` at `0x18000c427`
- `OLEAUT32!__imp_VariantInit` at `0x18000c3a3`
- `OLEAUT32!__imp_VariantInit` at `0x18000c427`
- `OLEAUT32!__imp_VariantClear` at `0x18000c3f8`
- `OLEAUT32!__imp_VariantClear` at `0x18000c466`
- `OLEAUT32!__imp_VariantClear` at `0x18000c60a`
- `OLEAUT32!__imp_VariantClear` at `0x18000c3f8`
- `OLEAUT32!__imp_VariantClear` at `0x18000c466`
- `OLEAUT32!__imp_VariantClear` at `0x18000c60a`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c3e6`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c3e6`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000c506`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000c506`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScriptEngineBase::ChangeTypeFromVar(
        ScriptEngineBase *this,
        void *a2,
        unsigned __int16 a3,
        struct tagVARIANT *a4)
{
  __int64 result; // rax
  void *v6; // r8
  int DispatchValue; // ebx
  struct Js::DynamicObject *v8; // rax
  int v9; // eax
  VARIANTARG *p_pvargSrc; // rdx
  VARIANTARG *v11; // r14
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r15d
  int v17; // eax
  struct Js::ScriptContext *v18; // r8
  int v19; // esi
  void *v20; // [rsp+20h] [rbp-50h] BYREF
  __int64 v21; // [rsp+28h] [rbp-48h] BYREF
  unsigned int NewValue[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v23; // [rsp+38h] [rbp-38h]
  VARIANTARG pvargSrc; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG v25; // [rsp+58h] [rbp-18h] BYREF

  v23 = -2;
  if ( !a4 )
    return 2147942487LL;
  *(_QWORD *)&a4->vt = 0;
  memset(&pvargSrc, 0, sizeof(pvargSrc));
  v20 = 0;
  result = ScriptEngineBase::VerifyOnEntry(this, 0);
  if ( (int)result >= 0 )
  {
    VariantInit(a4);
    if ( Js::DynamicObject::Is(a2) )
    {
      v8 = Js::DynamicObject::FromVar(v6);
      if ( a3 == 8 )
        v9 = ScriptSite::ExternalToPrimitive<1>(v8, &v20);
      else
        v9 = ScriptSite::ExternalToPrimitive<2>(v8, &v20);
      DispatchValue = v9;
      if ( v9 < 0 )
        return (unsigned int)DispatchValue;
      v6 = v20;
    }
    DispatchValue = DispatchHelper::MarshalJsVarToVariantNoThrow(v6, &pvargSrc, (struct Js::ScriptContext *)v6);
    if ( DispatchValue < 0 )
      return (unsigned int)DispatchValue;
    if ( a3 == 12 )
    {
      DispatchValue = VariantCopy(a4, &pvargSrc);
LABEL_7:
      VariantClear(&pvargSrc);
      return (unsigned int)DispatchValue;
    }
    memset(&v25, 0, sizeof(v25));
    VariantInit(&v25);
    DispatchValue = ScriptEngineBase::ValidateBaseThread(this);
    if ( DispatchValue < 0 )
      goto LABEL_7;
    SmartFPUControlT<1>::SmartFPUControlT<1>(NewValue);
    if ( NewValue[1] )
    {
      DispatchValue = NewValue[1];
      if ( (int)NewValue[1] > 0 )
        DispatchValue = LOWORD(NewValue[1]) | 0x80070000;
      SmartFPUControlT<1>::RestoreFPUControl(NewValue);
      goto LABEL_7;
    }
    if ( !*((_QWORD *)this + 4) )
    {
      DispatchValue = -2147418113;
      goto LABEL_14;
    }
    if ( pvargSrc.vt == a3 )
    {
      p_pvargSrc = &pvargSrc;
LABEL_29:
      DispatchValue = VariantCopyInd(a4, p_pvargSrc);
      goto LABEL_14;
    }
    v11 = &pvargSrc;
    if ( pvargSrc.vt == 9 )
    {
      v21 = 0;
      if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvargSrc.llVal)(
             pvargSrc.llVal,
             &GUID_ebade2e2_a8cc_4797_a430_2e863867efd0,
             &v21) < 0 )
      {
        DispatchValue = DispatchHelper::GetDispatchValue(
                          *((struct ScriptSite **)this + 4),
                          pvargSrc.pdispVal,
                          v12,
                          &v25);
        v11 = &v25;
      }
      else
      {
        v13 = v21;
        if ( v21 )
          v14 = v21 - 16;
        else
          v14 = 0;
        v20 = 0;
        v15 = *(_QWORD *)(v14 + 32);
        if ( v15 )
        {
          if ( a3 == 8 )
            v17 = ScriptSite::ExternalToPrimitive<1>(v15, &v20);
          else
            v17 = ScriptSite::ExternalToPrimitive<2>(v15, &v20);
          v16 = v17;
          DispatchValue = DispatchHelper::MarshalJsVarToVariantNoThrow(v20, &v25, v18);
          v11 = &v25;
          v13 = v21;
        }
        else
        {
          DispatchValue = 0;
          v16 = -2147024891;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( DispatchValue >= 0 )
          DispatchValue = v16;
      }
      if ( v11->vt == a3 )
      {
        p_pvargSrc = v11;
        goto LABEL_29;
      }
      if ( DispatchValue < 0 )
      {
LABEL_14:
        VariantClear(&v25);
        if ( NewValue[0] != -1 )
          _controlfp_s(0, NewValue[0], 0x308031Fu);
        goto LABEL_7;
      }
    }
    v19 = DispatchHelper::JscriptChangeType(v11, a4, a3, *((struct Js::ScriptContext *const *)this + 1));
    if ( v19 < 0 )
    {
      VariantClear(a4);
      DispatchValue = v19;
    }
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x18000c340  mov     rax, rsp
0x18000c343  mov     [rax+20h], r9
0x18000c347  mov     [rax+18h], r8w
0x18000c34c  mov     [rax+10h], rdx
0x18000c350  mov     [rax+8], rcx
0x18000c354  push    rbp
0x18000c355  push    rbx
0x18000c356  push    rsi
0x18000c357  push    rdi
0x18000c358  push    r13
0x18000c35a  push    r14
0x18000c35c  push    r15
0x18000c35e  mov     rbp, rsp
0x18000c361  sub     rsp, 70h
0x18000c365  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18000c36d  mov     rdi, [rbp+pvarg]
0x18000c371  test    rdi, rdi
0x18000c374  jz      loc_18000C4BC
0x18000c37a  xor     eax, eax
0x18000c37c  mov     [rdi], rax
0x18000c37f  xorps   xmm0, xmm0
0x18000c382  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x18000c386  mov     qword ptr [rbp+pvargSrc+10h], rax
0x18000c38a  mov     [rbp+var_50], rax
0x18000c38e  xor     edx, edx; int
0x18000c390  mov     r13, [rbp+arg_0]
0x18000c394  mov     rcx, r13; this
0x18000c397  call    ?VerifyOnEntry@ScriptEngineBase@@QEAAJH@Z; ScriptEngineBase::VerifyOnEntry(int)
0x18000c39c  test    eax, eax
0x18000c39e  js      short loc_18000C406
0x18000c3a0  mov     rcx, rdi; pvarg
0x18000c3a3  call    cs:__imp_VariantInit
0x18000c3aa  nop     dword ptr [rax+rax+00h]
0x18000c3af  mov     r8, [rbp+arg_8]
0x18000c3b3  mov     rcx, r8; void *
0x18000c3b6  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x18000c3bb  movzx   esi, [rbp+arg_10]
0x18000c3bf  test    al, al
0x18000c3c1  jnz     loc_18000C4C6
0x18000c3c7  lea     rdx, [rbp+pvargSrc]; struct tagVARIANT *
0x18000c3cb  mov     rcx, r8; void *
0x18000c3ce  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x18000c3d3  mov     ebx, eax
0x18000c3d5  test    eax, eax
0x18000c3d7  js      short loc_18000C404
0x18000c3d9  cmp     si, 0Ch
0x18000c3dd  jnz     short loc_18000C416
0x18000c3df  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18000c3e3  mov     rcx, rdi; pvargDest
0x18000c3e6  call    cs:__imp_VariantCopy
0x18000c3ed  nop     dword ptr [rax+rax+00h]
0x18000c3f2  mov     ebx, eax
0x18000c3f4  lea     rcx, [rbp+pvargSrc]; pvarg
0x18000c3f8  call    cs:__imp_VariantClear
0x18000c3ff  nop     dword ptr [rax+rax+00h]
0x18000c404  mov     eax, ebx
0x18000c406  add     rsp, 70h
0x18000c40a  pop     r15
0x18000c40c  pop     r14
0x18000c40e  pop     r13
0x18000c410  pop     rdi
0x18000c411  pop     rsi
0x18000c412  pop     rbx
0x18000c413  pop     rbp
0x18000c414  retn
0x18000c416  xorps   xmm0, xmm0
0x18000c419  xor     eax, eax
0x18000c41b  movups  xmmword ptr [rbp+var_18], xmm0
0x18000c41f  mov     qword ptr [rbp+var_18+10h], rax
0x18000c423  lea     rcx, [rbp+var_18]; pvarg
0x18000c427  call    cs:__imp_VariantInit
0x18000c42e  nop     dword ptr [rax+rax+00h]
0x18000c433  mov     rcx, r13; this
0x18000c436  call    ?ValidateBaseThread@ScriptEngineBase@@IEAAJXZ; ScriptEngineBase::ValidateBaseThread(void)
0x18000c43b  mov     ebx, eax
0x18000c43d  test    eax, eax
0x18000c43f  js      short loc_18000C3F4
0x18000c441  lea     rcx, [rbp+NewValue]
0x18000c445  call    ??0?$SmartFPUControlT@$00@@QEAA@XZ; SmartFPUControlT<1>::SmartFPUControlT<1>(void)
0x18000c44a  nop
0x18000c44b  mov     eax, [rbp+NewValue+4]
0x18000c44e  test    eax, eax
0x18000c450  jnz     short loc_18000C4A9
0x18000c452  cmp     qword ptr [r13+20h], 0
0x18000c457  jnz     loc_18000C4F4
0x18000c45d  mov     ebx, 8000FFFFh
0x18000c462  lea     rcx, [rbp+var_18]; pvarg
0x18000c466  call    cs:__imp_VariantClear
0x18000c46d  nop     dword ptr [rax+rax+00h]
0x18000c472  nop
0x18000c473  mov     rdx, qword ptr [rbp+NewValue]; NewValue
0x18000c477  cmp     edx, 0FFFFFFFFh
0x18000c47a  jz      short loc_18000C491
0x18000c47c  xor     ecx, ecx; CurrentState
0x18000c47e  mov     r8d, 308031Fh; Mask
0x18000c484  call    cs:__imp__controlfp_s
0x18000c48b  nop     dword ptr [rax+rax+00h]
0x18000c490  nop
0x18000c491  jmp     loc_18000C3F4
0x18000c496  mov     ebx, eax
0x18000c498  test    eax, eax
0x18000c49a  js      loc_18000C404
0x18000c4a0  mov     r8, [rbp+var_50]
0x18000c4a4  jmp     loc_18000C3C7
0x18000c4a9  mov     ebx, eax
0x18000c4ab  jg      short loc_18000C4E9
0x18000c4ad  lea     rcx, [rbp+NewValue]
0x18000c4b1  call    ?RestoreFPUControl@?$SmartFPUControlT@$00@@QEAAXXZ; SmartFPUControlT<1>::RestoreFPUControl(void)
0x18000c4b6  nop
0x18000c4b7  jmp     loc_18000C3F4
0x18000c4bc  mov     eax, 80070057h
0x18000c4c1  jmp     loc_18000C406
0x18000c4c6  mov     rcx, r8; void *
0x18000c4c9  call    ?FromVar@DynamicObject@Js@@SAPEAV12@PEAX@Z; Js::DynamicObject::FromVar(void *)
0x18000c4ce  lea     rdx, [rbp+var_50]
0x18000c4d2  mov     rcx, rax
0x18000c4d5  cmp     si, 8
0x18000c4d9  jnz     short loc_18000C4E2
0x18000c4db  call    ??$ExternalToPrimitive@$00@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<1>(Js::DynamicObject *,void * *,IServiceProvider *)
0x18000c4e0  jmp     short loc_18000C496
0x18000c4e2  call    ??$ExternalToPrimitive@$01@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<2>(Js::DynamicObject *,void * *,IServiceProvider *)
0x18000c4e7  jmp     short loc_18000C496
0x18000c4e9  movzx   ebx, ax
0x18000c4ec  or      ebx, 80070000h
0x18000c4f2  jmp     short loc_18000C4AD
0x18000c4f4  cmp     word ptr [rbp+pvargSrc], si
0x18000c4f8  jnz     short loc_18000C519
0x18000c4fa  lea     rdx, [rbp+pvargSrc]
0x18000c4fe  jmp     short loc_18000C503
0x18000c500  mov     rdx, r14; pvargSrc
0x18000c503  mov     rcx, rdi; pvarDest
0x18000c506  call    cs:__imp_VariantCopyInd
0x18000c50d  nop     dword ptr [rax+rax+00h]
0x18000c512  mov     ebx, eax
0x18000c514  jmp     loc_18000C462
0x18000c519  lea     r14, [rbp+pvargSrc]
0x18000c51d  cmp     word ptr [rbp+pvargSrc], 9
0x18000c522  jnz     loc_18000C5EA
0x18000c528  mov     [rbp+var_48], 0
0x18000c530  mov     rcx, qword ptr [rbp+pvargSrc+8]
0x18000c534  mov     rax, [rcx]
0x18000c537  lea     r8, [rbp+var_48]
0x18000c53b  lea     rdx, _GUID_ebade2e2_a8cc_4797_a430_2e863867efd0
0x18000c542  mov     rax, [rax]
0x18000c545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c54a  test    eax, eax
0x18000c54c  js      short loc_18000C5C1
0x18000c54e  mov     rcx, [rbp+var_48]
0x18000c552  test    rcx, rcx
0x18000c555  jz      short loc_18000C55D
0x18000c557  lea     rax, [rcx-10h]
0x18000c55b  jmp     short loc_18000C55F
0x18000c55d  xor     eax, eax
0x18000c55f  mov     [rbp+var_50], 0
0x18000c567  mov     rax, [rax+20h]
0x18000c56b  test    rax, rax
0x18000c56e  jnz     short loc_18000C57A
0x18000c570  xor     ebx, ebx
0x18000c572  mov     r15d, 80070005h
0x18000c578  jmp     short loc_18000C5AD
0x18000c57a  lea     rdx, [rbp+var_50]
0x18000c57e  mov     rcx, rax
0x18000c581  cmp     si, 8
0x18000c585  jnz     short loc_18000C58E
0x18000c587  call    ??$ExternalToPrimitive@$00@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<1>(Js::DynamicObject *,void * *,IServiceProvider *)
0x18000c58c  jmp     short loc_18000C593
0x18000c58e  call    ??$ExternalToPrimitive@$01@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<2>(Js::DynamicObject *,void * *,IServiceProvider *)
0x18000c593  mov     r15d, eax
0x18000c596  lea     rdx, [rbp+var_18]; struct tagVARIANT *
0x18000c59a  mov     rcx, [rbp+var_50]; void *
0x18000c59e  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x18000c5a3  mov     ebx, eax
0x18000c5a5  lea     r14, [rbp+var_18]
0x18000c5a9  mov     rcx, [rbp+var_48]
0x18000c5ad  mov     rax, [rcx]
0x18000c5b0  mov     rax, [rax+10h]
0x18000c5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b9  test    ebx, ebx
0x18000c5bb  cmovns  ebx, r15d
0x18000c5bf  jmp     short loc_18000C5D8
0x18000c5c1  lea     r9, [rbp+var_18]; struct tagVARIANT *
0x18000c5c5  mov     rdx, qword ptr [rbp+pvargSrc+8]; struct IDispatch *
0x18000c5c9  mov     rcx, [r13+20h]; struct ScriptSite *
0x18000c5cd  call    ?GetDispatchValue@DispatchHelper@@SAJPEAVScriptSite@@PEAUIDispatch@@JPEAUtagVARIANT@@@Z; DispatchHelper::GetDispatchValue(ScriptSite *,IDispatch *,long,tagVARIANT *)
0x18000c5d2  mov     ebx, eax
0x18000c5d4  lea     r14, [rbp+var_18]
0x18000c5d8  cmp     [r14], si
0x18000c5dc  jz      loc_18000C500
0x18000c5e2  test    ebx, ebx
0x18000c5e4  js      loc_18000C462
0x18000c5ea  mov     r9, [r13+8]; struct Js::ScriptContext *
0x18000c5ee  movzx   r8d, si; unsigned __int16
0x18000c5f2  mov     rdx, rdi; struct tagVARIANT *
0x18000c5f5  mov     rcx, r14; struct tagVARIANT *
0x18000c5f8  call    ?JscriptChangeType@DispatchHelper@@SAJPEAUtagVARIANT@@0GQEAVScriptContext@Js@@@Z; DispatchHelper::JscriptChangeType(tagVARIANT *,tagVARIANT *,ushort,Js::ScriptContext * const)
0x18000c5fd  mov     esi, eax
0x18000c5ff  test    eax, eax
0x18000c601  jns     loc_18000C462
0x18000c607  mov     rcx, rdi; pvarg
0x18000c60a  call    cs:__imp_VariantClear
0x18000c611  nop     dword ptr [rax+rax+00h]
0x18000c616  mov     ebx, esi
0x18000c618  jmp     loc_18000C462
```
