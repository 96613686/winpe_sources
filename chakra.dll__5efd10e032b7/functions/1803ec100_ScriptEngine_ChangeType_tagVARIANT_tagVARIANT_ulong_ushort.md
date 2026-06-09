# ScriptEngine::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)

- ea: `0x1803ec100`
- end: `0x1803ec308`
- name: `?ChangeType@ScriptEngine@@UEAAJPEAUtagVARIANT@@0KG@Z`
- size: `520`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x18000ba60`
- `0x18000d670`
- `0x1801681a4`
- `0x18022fecc`
- `0x1803ec100`
- `0x18043018c`
- `0x18043020c`
- `0x180442d18`
- `0x18044300c`
- `0x1805cd010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1803ec13b`
- `OLEAUT32!__imp_VariantInit` at `0x1803ec13b`
- `OLEAUT32!__imp_VariantClear` at `0x1803ec2c8`
- `OLEAUT32!__imp_VariantClear` at `0x1803ec2da`
- `OLEAUT32!__imp_VariantClear` at `0x1803ec2c8`
- `OLEAUT32!__imp_VariantClear` at `0x1803ec2da`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1803ec1ca`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1803ec1ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScriptEngine::ChangeType(
        ScriptEngine *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int64 a4,
        unsigned __int16 a5)
{
  __int64 result; // rax
  HRESULT DispatchValue; // ebx
  VARIANTARG *p_pvarg; // rsi
  unsigned int v8; // edi
  int v9; // r8d
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // r15d
  int v14; // eax
  struct Js::ScriptContext *v15; // r8
  int v16; // edi
  void *v17; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v19[4]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+34h] [rbp-34h]
  __int64 v21; // [rsp+38h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  v21 = -2;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  result = ScriptEngineBase::ValidateBaseThread((ScriptEngine *)((char *)this - 232));
  DispatchValue = result;
  if ( (int)result < 0 )
    return result;
  if ( !a2 )
    return 2147500035LL;
  p_pvarg = a3;
  if ( !a3 )
    return 2147500035LL;
  SmartFPUControlT<1>::SmartFPUControlT<1>(v19);
  v8 = v20;
  if ( !v20 )
  {
    if ( !*((_QWORD *)this - 25) )
    {
      DispatchValue = -2147418113;
LABEL_31:
      VariantClear(&pvarg);
      SmartFPUControlT<1>::RestoreFPUControl(v19);
      return (unsigned int)DispatchValue;
    }
    if ( a3->vt == a5 )
    {
LABEL_11:
      DispatchValue = VariantCopyInd(a2, p_pvarg);
      goto LABEL_31;
    }
    if ( a3->vt == 9 )
    {
      v18 = 0;
      if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))a3->llVal)(
             a3->llVal,
             &GUID_ebade2e2_a8cc_4797_a430_2e863867efd0,
             &v18) < 0 )
      {
        DispatchValue = DispatchHelper::GetDispatchValue(*((struct ScriptSite **)this - 25), a3->pdispVal, v9, &pvarg);
        p_pvarg = &pvarg;
      }
      else
      {
        v10 = v18;
        if ( v18 )
          v11 = v18 - 16;
        else
          v11 = 0;
        v17 = 0;
        v12 = *(_QWORD *)(v11 + 32);
        if ( v12 )
        {
          if ( a5 == 8 )
            v14 = ScriptSite::ExternalToPrimitive<1>(v12, &v17);
          else
            v14 = ScriptSite::ExternalToPrimitive<2>(v12, &v17);
          v13 = v14;
          DispatchValue = DispatchHelper::MarshalJsVarToVariantNoThrow(v17, &pvarg, v15);
          p_pvarg = &pvarg;
          v10 = v18;
        }
        else
        {
          DispatchValue = 0;
          v13 = -2147024891;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        if ( DispatchValue >= 0 )
          DispatchValue = v13;
      }
      if ( p_pvarg->vt == a5 )
        goto LABEL_11;
      if ( DispatchValue < 0 )
        goto LABEL_31;
    }
    v16 = DispatchHelper::JscriptChangeType(p_pvarg, a2, a5, *((struct Js::ScriptContext *const *)this - 28));
    if ( v16 < 0 )
    {
      VariantClear(a2);
      DispatchValue = v16;
    }
    goto LABEL_31;
  }
  if ( v20 > 0 )
    v8 = (unsigned __int16)v20 | 0x80070000;
  SmartFPUControlT<1>::RestoreFPUControl(v19);
  return v8;
}

```

## disassembly

```asm
0x1803ec100  mov     rax, rsp
0x1803ec103  mov     [rax+20h], r9d
0x1803ec107  mov     [rax+18h], r8
0x1803ec10b  mov     [rax+10h], rdx
0x1803ec10f  mov     [rax+8], rcx
0x1803ec113  push    rbp
0x1803ec114  push    rbx
0x1803ec115  push    rsi
0x1803ec116  push    rdi
0x1803ec117  push    r13
0x1803ec119  push    r15
0x1803ec11b  mov     rbp, rsp
0x1803ec11e  sub     rsp, 68h
0x1803ec122  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1803ec12a  xorps   xmm0, xmm0
0x1803ec12d  xor     eax, eax
0x1803ec12f  movups  xmmword ptr [rbp+pvarg], xmm0
0x1803ec133  mov     qword ptr [rbp+pvarg+10h], rax
0x1803ec137  lea     rcx, [rbp+pvarg]; pvarg
0x1803ec13b  call    cs:__imp_VariantInit
0x1803ec142  nop     dword ptr [rax+rax+00h]
0x1803ec147  mov     r13, [rbp+arg_0]
0x1803ec14b  lea     rcx, [r13-0E8h]; this
0x1803ec152  call    ?ValidateBaseThread@ScriptEngineBase@@IEAAJXZ; ScriptEngineBase::ValidateBaseThread(void)
0x1803ec157  mov     ebx, eax
0x1803ec159  test    eax, eax
0x1803ec15b  js      loc_1803EC2FA
0x1803ec161  cmp     [rbp+pvarDest], 0
0x1803ec166  jz      loc_1803EC2F5
0x1803ec16c  mov     rsi, [rbp+pvargSrc]
0x1803ec170  test    rsi, rsi
0x1803ec173  jz      loc_1803EC2F5
0x1803ec179  lea     rcx, [rbp+var_38]
0x1803ec17d  call    ??0?$SmartFPUControlT@$00@@QEAA@XZ; SmartFPUControlT<1>::SmartFPUControlT<1>(void)
0x1803ec182  nop
0x1803ec183  mov     edi, [rbp+var_34]
0x1803ec186  test    edi, edi
0x1803ec188  jz      short loc_1803EC1A6
0x1803ec18a  jle     short loc_1803EC195
0x1803ec18c  movzx   edi, di
0x1803ec18f  or      edi, 80070000h
0x1803ec195  lea     rcx, [rbp+var_38]
0x1803ec199  call    ?RestoreFPUControl@?$SmartFPUControlT@$00@@QEAAXXZ; SmartFPUControlT<1>::RestoreFPUControl(void)
0x1803ec19e  nop
0x1803ec19f  mov     eax, edi
0x1803ec1a1  jmp     loc_1803EC2FA
0x1803ec1a6  cmp     qword ptr [r13-0C8h], 0
0x1803ec1ae  jnz     short loc_1803EC1BA
0x1803ec1b0  mov     ebx, 8000FFFFh
0x1803ec1b5  jmp     loc_1803EC2D6
0x1803ec1ba  movzx   edi, [rbp+arg_20]
0x1803ec1be  cmp     [rsi], di
0x1803ec1c1  jnz     short loc_1803EC1DD
0x1803ec1c3  mov     rdx, rsi; pvargSrc
0x1803ec1c6  mov     rcx, [rbp+pvarDest]; pvarDest
0x1803ec1ca  call    cs:__imp_VariantCopyInd
0x1803ec1d1  nop     dword ptr [rax+rax+00h]
0x1803ec1d6  mov     ebx, eax
0x1803ec1d8  jmp     loc_1803EC2D6
0x1803ec1dd  cmp     word ptr [rsi], 9
0x1803ec1e1  jnz     loc_1803EC2A7
0x1803ec1e7  mov     [rbp+var_40], 0
0x1803ec1ef  mov     rcx, [rsi+8]
0x1803ec1f3  mov     rax, [rcx]
0x1803ec1f6  lea     r8, [rbp+var_40]
0x1803ec1fa  lea     rdx, _GUID_ebade2e2_a8cc_4797_a430_2e863867efd0
0x1803ec201  mov     rax, [rax]
0x1803ec204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ec209  test    eax, eax
0x1803ec20b  js      short loc_1803EC280
0x1803ec20d  mov     rcx, [rbp+var_40]
0x1803ec211  test    rcx, rcx
0x1803ec214  jz      short loc_1803EC21C
0x1803ec216  lea     rax, [rcx-10h]
0x1803ec21a  jmp     short loc_1803EC21E
0x1803ec21c  xor     eax, eax
0x1803ec21e  mov     [rbp+var_48], 0
0x1803ec226  mov     rax, [rax+20h]
0x1803ec22a  test    rax, rax
0x1803ec22d  jnz     short loc_1803EC239
0x1803ec22f  xor     ebx, ebx
0x1803ec231  mov     r15d, 80070005h
0x1803ec237  jmp     short loc_1803EC26C
0x1803ec239  lea     rdx, [rbp+var_48]
0x1803ec23d  mov     rcx, rax
0x1803ec240  cmp     di, 8
0x1803ec244  jnz     short loc_1803EC24D
0x1803ec246  call    ??$ExternalToPrimitive@$00@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<1>(Js::DynamicObject *,void * *,IServiceProvider *)
0x1803ec24b  jmp     short loc_1803EC252
0x1803ec24d  call    ??$ExternalToPrimitive@$01@ScriptSite@@SAJPEAVDynamicObject@Js@@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive<2>(Js::DynamicObject *,void * *,IServiceProvider *)
0x1803ec252  mov     r15d, eax
0x1803ec255  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x1803ec259  mov     rcx, [rbp+var_48]; void *
0x1803ec25d  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x1803ec262  mov     ebx, eax
0x1803ec264  lea     rsi, [rbp+pvarg]
0x1803ec268  mov     rcx, [rbp+var_40]
0x1803ec26c  mov     rax, [rcx]
0x1803ec26f  mov     rax, [rax+10h]
0x1803ec273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ec278  test    ebx, ebx
0x1803ec27a  cmovns  ebx, r15d
0x1803ec27e  jmp     short loc_1803EC29A
0x1803ec280  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x1803ec284  mov     rdx, [rsi+8]; struct IDispatch *
0x1803ec288  mov     rcx, [r13-0C8h]; struct ScriptSite *
0x1803ec28f  call    ?GetDispatchValue@DispatchHelper@@SAJPEAVScriptSite@@PEAUIDispatch@@JPEAUtagVARIANT@@@Z; DispatchHelper::GetDispatchValue(ScriptSite *,IDispatch *,long,tagVARIANT *)
0x1803ec294  mov     ebx, eax
0x1803ec296  lea     rsi, [rbp+pvarg]
0x1803ec29a  cmp     [rsi], di
0x1803ec29d  jz      loc_1803EC1C3
0x1803ec2a3  test    ebx, ebx
0x1803ec2a5  js      short loc_1803EC2D6
0x1803ec2a7  mov     r9, [r13-0E0h]; struct Js::ScriptContext *
0x1803ec2ae  movzx   r8d, di; unsigned __int16
0x1803ec2b2  mov     rdx, [rbp+pvarDest]; struct tagVARIANT *
0x1803ec2b6  mov     rcx, rsi; struct tagVARIANT *
0x1803ec2b9  call    ?JscriptChangeType@DispatchHelper@@SAJPEAUtagVARIANT@@0GQEAVScriptContext@Js@@@Z; DispatchHelper::JscriptChangeType(tagVARIANT *,tagVARIANT *,ushort,Js::ScriptContext * const)
0x1803ec2be  mov     edi, eax
0x1803ec2c0  test    eax, eax
0x1803ec2c2  jns     short loc_1803EC2D6
0x1803ec2c4  mov     rcx, [rbp+pvarDest]; pvarg
0x1803ec2c8  call    cs:__imp_VariantClear
0x1803ec2cf  nop     dword ptr [rax+rax+00h]
0x1803ec2d4  mov     ebx, edi
0x1803ec2d6  lea     rcx, [rbp+pvarg]; pvarg
0x1803ec2da  call    cs:__imp_VariantClear
0x1803ec2e1  nop     dword ptr [rax+rax+00h]
0x1803ec2e6  nop
0x1803ec2e7  lea     rcx, [rbp+var_38]
0x1803ec2eb  call    ?RestoreFPUControl@?$SmartFPUControlT@$00@@QEAAXXZ; SmartFPUControlT<1>::RestoreFPUControl(void)
0x1803ec2f0  nop
0x1803ec2f1  mov     eax, ebx
0x1803ec2f3  jmp     short loc_1803EC2FA
0x1803ec2f5  mov     eax, 80004003h
0x1803ec2fa  add     rsp, 68h
0x1803ec2fe  pop     r15
0x1803ec300  pop     r13
0x1803ec302  pop     rdi
0x1803ec303  pop     rsi
0x1803ec304  pop     rbx
0x1803ec305  pop     rbp
0x1803ec306  retn
```
