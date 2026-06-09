# ScriptEngine::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)

- ea: `0x18010d0b0`
- end: `0x18010d2fb`
- name: `?ChangeType@ScriptEngine@@UEAAJPEAUtagVARIANT@@0KG@Z`
- size: `587`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180172940`

## callees

- `0x1800327fc`
- `0x180033c7c`
- `0x18010d0b0`
- `0x18010d304`
- `0x1801ebc10`
- `0x1802256f0`
- `0x180364010`

## import_xrefs

- `msvcrt!_controlfp_s` at `0x18010d13d`
- `msvcrt!_controlfp_s` at `0x18010d158`
- `msvcrt!_controlfp_s` at `0x18010d1af`
- `msvcrt!_controlfp_s` at `0x18010d13d`
- `msvcrt!_controlfp_s` at `0x18010d158`
- `msvcrt!_controlfp_s` at `0x18010d1af`
- `OLEAUT32!__imp_VariantInit` at `0x18010d0e4`
- `OLEAUT32!__imp_VariantInit` at `0x18010d0e4`
- `OLEAUT32!__imp_VariantClear` at `0x18010d19a`
- `OLEAUT32!__imp_VariantClear` at `0x18010d1fc`
- `OLEAUT32!__imp_VariantClear` at `0x18010d19a`
- `OLEAUT32!__imp_VariantClear` at `0x18010d1fc`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18010d188`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18010d188`

## pseudocode

```c
errno_t __fastcall ScriptEngine::ChangeType(
        ScriptEngine *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int64 a4,
        unsigned __int16 a5)
{
  errno_t result; // eax
  HRESULT DispatchValue; // ebx
  VARIANTARG *p_pvarg; // rdi
  bool v8; // cc
  int v9; // edi
  int (__fastcall ***llVal)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r12d
  HRESULT v15; // eax
  unsigned int CurrentState; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+28h] [rbp-30h] BYREF
  void *v18; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  result = ScriptEngineBase::ValidateBaseThread((ScriptEngine *)((char *)this - 192));
  DispatchValue = result;
  if ( result < 0 )
    return result;
  if ( !a2 )
    return -2147467261;
  p_pvarg = a3;
  if ( !a3 )
    return -2147467261;
  CurrentState = 0;
  result = _controlfp_s(&CurrentState, 0, 0);
  v8 = result <= 0;
  if ( !result )
  {
    result = _controlfp_s(0, 0x1Fu, 0x30F031Fu);
    v8 = result <= 0;
    if ( !result )
    {
      if ( !*((_QWORD *)this - 20) )
      {
        DispatchValue = -2147418113;
        goto LABEL_10;
      }
      if ( a3->vt == a5 )
      {
LABEL_9:
        DispatchValue = VariantCopyInd(a2, p_pvarg);
LABEL_10:
        VariantClear(&pvarg);
        _controlfp_s(0, CurrentState, 0xFFFFFFFF);
        return DispatchValue;
      }
      if ( a3->vt == 9 )
      {
        llVal = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))a3->llVal;
        v17 = 0;
        if ( (**llVal)(llVal, &GUID_ebade2e2_a8cc_4797_a430_2e863867efd0, &v17) < 0 )
        {
          DispatchValue = DispatchHelper::GetDispatchValue(
                            *((struct ScriptSite **)this - 20),
                            a3->pdispVal,
                            v11,
                            &pvarg);
          p_pvarg = &pvarg;
        }
        else
        {
          v12 = v17;
          if ( v17 )
            v13 = v17 - 24;
          else
            v13 = 0;
          v18 = 0;
          if ( *(_QWORD *)(v13 + 40) )
          {
            v14 = ScriptSite::ExternalToPrimitive(*(_QWORD *)(v13 + 40), (unsigned int)(a5 != 8) + 1, &v18, 0);
            v15 = DispatchHelper::MarshalJsVarToVariantNoThrow(
                    (unsigned __int64)v18,
                    &pvarg,
                    *(void (__fastcall ***)(struct Js::ScriptContext *))(*((_QWORD *)this - 20) + 160LL));
            v12 = v17;
            p_pvarg = &pvarg;
            DispatchValue = v15;
          }
          else
          {
            DispatchValue = 0;
            v14 = -2147024891;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( DispatchValue >= 0 )
            DispatchValue = v14;
        }
        if ( p_pvarg->vt == a5 )
          goto LABEL_9;
        if ( DispatchValue < 0 )
          goto LABEL_10;
      }
      v9 = DispatchHelper::JscriptChangeType(p_pvarg, a2, a5, *((struct Js::ScriptContext *const *)this - 23));
      if ( v9 < 0 )
      {
        VariantClear(a2);
        DispatchValue = v9;
      }
      goto LABEL_10;
    }
  }
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18010d0b0  mov     rax, rsp
0x18010d0b3  mov     [rax+20h], r9d
0x18010d0b7  mov     [rax+18h], r8
0x18010d0bb  mov     [rax+10h], rdx
0x18010d0bf  mov     [rax+8], rcx
0x18010d0c3  push    rbp
0x18010d0c4  push    rbx
0x18010d0c5  push    rdi
0x18010d0c6  push    r12
0x18010d0c8  push    r14
0x18010d0ca  push    r15
0x18010d0cc  mov     rbp, rsp
0x18010d0cf  sub     rsp, 58h
0x18010d0d3  xorps   xmm0, xmm0
0x18010d0d6  lea     rcx, [rbp+pvarg]; pvarg
0x18010d0da  xor     eax, eax
0x18010d0dc  movups  xmmword ptr [rbp+pvarg], xmm0
0x18010d0e0  mov     qword ptr [rbp+pvarg+10h], rax
0x18010d0e4  call    cs:__imp_VariantInit
0x18010d0eb  nop     dword ptr [rax+rax+00h]
0x18010d0f0  mov     r14, [rbp+arg_0]
0x18010d0f4  lea     rcx, [r14-0C0h]; this
0x18010d0fb  call    ?ValidateBaseThread@ScriptEngineBase@@IEAAJXZ; ScriptEngineBase::ValidateBaseThread(void)
0x18010d100  mov     ebx, eax
0x18010d102  test    eax, eax
0x18010d104  jns     short loc_18010D115
0x18010d106  add     rsp, 58h
0x18010d10a  pop     r15
0x18010d10c  pop     r14
0x18010d10e  pop     r12
0x18010d110  pop     rdi
0x18010d111  pop     rbx
0x18010d112  pop     rbp
0x18010d113  retn
0x18010d115  cmp     [rbp+pvarDest], 0
0x18010d11a  jz      loc_18010D2F1
0x18010d120  mov     rdi, [rbp+pvargSrc]
0x18010d124  test    rdi, rdi
0x18010d127  jz      loc_18010D2F1
0x18010d12d  xor     r8d, r8d; Mask
0x18010d130  mov     [rbp+CurrentState], 0
0x18010d137  xor     edx, edx; NewValue
0x18010d139  lea     rcx, [rbp+CurrentState]; CurrentState
0x18010d13d  call    cs:__imp__controlfp_s
0x18010d144  nop     dword ptr [rax+rax+00h]
0x18010d149  test    eax, eax
0x18010d14b  jnz     short loc_18010D1C2
0x18010d14d  lea     edx, [rax+1Fh]; NewValue
0x18010d150  xor     ecx, ecx; CurrentState
0x18010d152  mov     r8d, 30F031Fh; Mask
0x18010d158  call    cs:__imp__controlfp_s
0x18010d15f  nop     dword ptr [rax+rax+00h]
0x18010d164  test    eax, eax
0x18010d166  jnz     short loc_18010D1C2
0x18010d168  cmp     qword ptr [r14-0A0h], 0
0x18010d170  jz      loc_18010D212
0x18010d176  movzx   r15d, [rbp+arg_20]
0x18010d17b  cmp     [rdi], r15w
0x18010d17f  jnz     short loc_18010D1D5
0x18010d181  mov     rcx, [rbp+pvarDest]; pvarDest
0x18010d185  mov     rdx, rdi; pvargSrc
0x18010d188  call    cs:__imp_VariantCopyInd
0x18010d18f  nop     dword ptr [rax+rax+00h]
0x18010d194  mov     ebx, eax
0x18010d196  lea     rcx, [rbp+pvarg]; pvarg
0x18010d19a  call    cs:__imp_VariantClear
0x18010d1a1  nop     dword ptr [rax+rax+00h]
0x18010d1a6  mov     edx, [rbp+CurrentState]; NewValue
0x18010d1a9  or      r8d, 0FFFFFFFFh; Mask
0x18010d1ad  xor     ecx, ecx; CurrentState
0x18010d1af  call    cs:__imp__controlfp_s
0x18010d1b6  nop     dword ptr [rax+rax+00h]
0x18010d1bb  mov     eax, ebx
0x18010d1bd  jmp     loc_18010D106
0x18010d1c2  jle     loc_18010D106
0x18010d1c8  movzx   eax, ax
0x18010d1cb  or      eax, 80070000h
0x18010d1d0  jmp     loc_18010D106
0x18010d1d5  cmp     word ptr [rdi], 9
0x18010d1d9  jz      short loc_18010D21C
0x18010d1db  mov     r9, [r14-0B8h]; struct Js::ScriptContext *
0x18010d1e2  movzx   r8d, r15w; unsigned __int16
0x18010d1e6  mov     rdx, [rbp+pvarDest]; struct tagVARIANT *
0x18010d1ea  mov     rcx, rdi; struct tagVARIANT *
0x18010d1ed  call    ?JscriptChangeType@DispatchHelper@@SAJPEAUtagVARIANT@@0GQEAVScriptContext@Js@@@Z; DispatchHelper::JscriptChangeType(tagVARIANT *,tagVARIANT *,ushort,Js::ScriptContext * const)
0x18010d1f2  mov     edi, eax
0x18010d1f4  test    eax, eax
0x18010d1f6  jns     short loc_18010D196
0x18010d1f8  mov     rcx, [rbp+pvarDest]; pvarg
0x18010d1fc  call    cs:__imp_VariantClear
0x18010d203  nop     dword ptr [rax+rax+00h]
0x18010d208  mov     ebx, edi
0x18010d20a  jmp     short loc_18010D196
0x18010d20c  test    ebx, ebx
0x18010d20e  jns     short loc_18010D1DB
0x18010d210  jmp     short loc_18010D196
0x18010d212  mov     ebx, 8000FFFFh
0x18010d217  jmp     loc_18010D196
0x18010d21c  mov     rcx, [rdi+8]
0x18010d220  lea     r8, [rbp+var_30]
0x18010d224  mov     [rbp+var_30], 0
0x18010d22c  lea     rdx, _GUID_ebade2e2_a8cc_4797_a430_2e863867efd0
0x18010d233  mov     rax, [rcx]
0x18010d236  mov     rax, [rax]
0x18010d239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d23e  test    eax, eax
0x18010d240  js      loc_18010D2C8
0x18010d246  mov     rcx, [rbp+var_30]
0x18010d24a  test    rcx, rcx
0x18010d24d  jz      short loc_18010D255
0x18010d24f  lea     rax, [rcx-18h]
0x18010d253  jmp     short loc_18010D257
0x18010d255  xor     eax, eax
0x18010d257  xor     edx, edx
0x18010d259  mov     [rbp+var_28], 0
0x18010d261  cmp     r15w, 8
0x18010d266  setnz   dl
0x18010d269  inc     edx
0x18010d26b  cmp     qword ptr [rax+28h], 0
0x18010d270  jnz     short loc_18010D27C
0x18010d272  xor     ebx, ebx
0x18010d274  mov     r12d, 80070005h
0x18010d27a  jmp     short loc_18010D2B4
0x18010d27c  mov     rcx, [rax+28h]
0x18010d280  lea     r8, [rbp+var_28]
0x18010d284  xor     r9d, r9d
0x18010d287  call    ?ExternalToPrimitive@ScriptSite@@SAJPEAVRecyclableObject@Js@@UJavascriptHint@3@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive(Js::RecyclableObject *,Js::JavascriptHint,void * *,IServiceProvider *)
0x18010d28c  mov     r8, [r14-0A0h]
0x18010d293  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x18010d297  mov     rcx, [rbp+var_28]; void *
0x18010d29b  mov     r12d, eax
0x18010d29e  mov     r8, [r8+0A0h]; struct Js::ScriptContext *
0x18010d2a5  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x18010d2aa  mov     rcx, [rbp+var_30]
0x18010d2ae  lea     rdi, [rbp+pvarg]
0x18010d2b2  mov     ebx, eax
0x18010d2b4  mov     rdx, [rcx]
0x18010d2b7  mov     rax, [rdx+10h]
0x18010d2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d2c0  test    ebx, ebx
0x18010d2c2  cmovns  ebx, r12d
0x18010d2c6  jmp     short loc_18010D2E2
0x18010d2c8  mov     rdx, [rdi+8]; struct IDispatch *
0x18010d2cc  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x18010d2d0  mov     rcx, [r14-0A0h]; struct ScriptSite *
0x18010d2d7  call    ?GetDispatchValue@DispatchHelper@@SAJPEAVScriptSite@@PEAUIDispatch@@JPEAUtagVARIANT@@@Z; DispatchHelper::GetDispatchValue(ScriptSite *,IDispatch *,long,tagVARIANT *)
0x18010d2dc  mov     ebx, eax
0x18010d2de  lea     rdi, [rbp+pvarg]
0x18010d2e2  cmp     [rdi], r15w
0x18010d2e6  jz      loc_18010D181
0x18010d2ec  jmp     loc_18010D20C
0x18010d2f1  mov     eax, 80004003h
0x18010d2f6  jmp     loc_18010D106
```
