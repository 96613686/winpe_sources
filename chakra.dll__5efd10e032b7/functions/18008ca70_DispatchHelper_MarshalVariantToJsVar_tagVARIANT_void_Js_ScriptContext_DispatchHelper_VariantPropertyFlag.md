# DispatchHelper::MarshalVariantToJsVar(tagVARIANT *,void * *,Js::ScriptContext *,DispatchHelper::VariantPropertyFlag)

- ea: `0x18008ca70`
- end: `0x18008cb8b`
- name: `?MarshalVariantToJsVar@DispatchHelper@@CAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@W4VariantPropertyFlag@1@@Z`
- size: `283`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18008ca38`
- `0x18008cd34`
- `0x180309b74`
- `0x1804432fc`
- `0x180448520`

## callees

- `0x18008ca70`
- `0x18008cb94`
- `0x18008cbc8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18008caca`
- `OLEAUT32!__imp_VariantInit` at `0x18008cb67`
- `OLEAUT32!__imp_VariantInit` at `0x18008caca`
- `OLEAUT32!__imp_VariantInit` at `0x18008cb67`
- `OLEAUT32!__imp_VariantClear` at `0x18008cb1d`
- `OLEAUT32!__imp_VariantClear` at `0x18008cb1d`
- `OLEAUT32!__imp_VariantCopy` at `0x18008cadd`
- `OLEAUT32!__imp_VariantCopy` at `0x18008cadd`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008cb7a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008cb7a`

## pseudocode

```c
HRESULT __fastcall DispatchHelper::MarshalVariantToJsVar(VARIANTARG *a1, void **a2, struct Js::ScriptContext *a3)
{
  VARIANTARG *p_pvarg; // rbx
  HRESULT result; // eax
  int v5; // edi
  unsigned int v6; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF

  p_pvarg = a1;
  if ( !a1 || !a2 )
    return -2147024809;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (a1->vt & 0x4000) != 0 )
  {
    v6 = a1->vt & 0xBFFF;
    if ( v6 != 0x2000 && v6 != 8 && v6 != 12 )
    {
      if ( v6 >= 2 )
      {
        VariantInit(&pvarg);
        result = VariantCopyInd(&pvarg, p_pvarg);
        goto LABEL_6;
      }
      return -2147024809;
    }
  }
  if ( a1->vt == 8 )
    goto LABEL_8;
  VariantInit(&pvarg);
  result = VariantCopy(&pvarg, p_pvarg);
LABEL_6:
  if ( result < 0 )
    return result;
  p_pvarg = &pvarg;
LABEL_8:
  v5 = DispatchHelper::SimplifyVariant(p_pvarg);
  if ( v5 >= 0 )
    v5 = DispatchHelper::MarshalVariantToJsVarDerefedNoThrow(p_pvarg, a2, a3);
  if ( p_pvarg == &pvarg )
    VariantClear(p_pvarg);
  return v5;
}

```

## disassembly

```asm
0x18008ca70  mov     rax, rsp
0x18008ca73  mov     [rax+20h], r9d
0x18008ca77  mov     [rax+18h], r8
0x18008ca7b  mov     [rax+10h], rdx
0x18008ca7f  mov     [rax+8], rcx
0x18008ca83  push    rbp
0x18008ca84  push    rbx
0x18008ca85  push    rdi
0x18008ca86  mov     rbp, rsp
0x18008ca89  sub     rsp, 40h
0x18008ca8d  mov     rbx, [rbp+pvargSrc]
0x18008ca91  test    rbx, rbx
0x18008ca94  jz      loc_18008CB34
0x18008ca9a  cmp     [rbp+arg_8], 0
0x18008ca9f  jz      loc_18008CB34
0x18008caa5  xor     eax, eax
0x18008caa7  xorps   xmm0, xmm0
0x18008caaa  mov     qword ptr [rbp+pvarg+10h], rax
0x18008caae  mov     ecx, 8
0x18008cab3  mov     eax, 4000h
0x18008cab8  movups  xmmword ptr [rbp+pvarg], xmm0
0x18008cabc  test    [rbx], ax
0x18008cabf  jnz     short loc_18008CB3B
0x18008cac1  cmp     [rbx], cx
0x18008cac4  jz      short loc_18008CAF1
0x18008cac6  lea     rcx, [rbp+pvarg]; pvarg
0x18008caca  call    cs:__imp_VariantInit
0x18008cad1  nop     dword ptr [rax+rax+00h]
0x18008cad6  mov     rdx, rbx; pvargSrc
0x18008cad9  lea     rcx, [rbp+pvarg]; pvargDest
0x18008cadd  call    cs:__imp_VariantCopy
0x18008cae4  nop     dword ptr [rax+rax+00h]
0x18008cae9  test    eax, eax
0x18008caeb  js      short loc_18008CB2B
0x18008caed  lea     rbx, [rbp+pvarg]
0x18008caf1  mov     rcx, rbx; struct tagVARIANT *
0x18008caf4  call    ?SimplifyVariant@DispatchHelper@@CAJPEAUtagVARIANT@@@Z; DispatchHelper::SimplifyVariant(tagVARIANT *)
0x18008caf9  mov     edi, eax
0x18008cafb  test    eax, eax
0x18008cafd  js      short loc_18008CB11
0x18008caff  mov     r8, [rbp+arg_10]; struct Js::ScriptContext *
0x18008cb03  mov     rcx, rbx; struct tagVARIANT *
0x18008cb06  mov     rdx, [rbp+arg_8]; void **
0x18008cb0a  call    ?MarshalVariantToJsVarDerefedNoThrow@DispatchHelper@@CAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@@Z; DispatchHelper::MarshalVariantToJsVarDerefedNoThrow(tagVARIANT *,void * *,Js::ScriptContext *)
0x18008cb0f  mov     edi, eax
0x18008cb11  lea     rax, [rbp+pvarg]
0x18008cb15  cmp     rbx, rax
0x18008cb18  jnz     short loc_18008CB29
0x18008cb1a  mov     rcx, rbx; pvarg
0x18008cb1d  call    cs:__imp_VariantClear
0x18008cb24  nop     dword ptr [rax+rax+00h]
0x18008cb29  mov     eax, edi
0x18008cb2b  add     rsp, 40h
0x18008cb2f  pop     rdi
0x18008cb30  pop     rbx
0x18008cb31  pop     rbp
0x18008cb32  retn
0x18008cb34  mov     eax, 80070057h
0x18008cb39  jmp     short loc_18008CB2B
0x18008cb3b  movzx   eax, word ptr [rbx]
0x18008cb3e  btr     eax, 0Eh
0x18008cb42  cmp     eax, 2000h
0x18008cb47  jz      loc_18008CAC1
0x18008cb4d  cmp     eax, ecx
0x18008cb4f  jz      loc_18008CAC1
0x18008cb55  cmp     eax, 0Ch
0x18008cb58  jz      loc_18008CAC1
0x18008cb5e  cmp     eax, 2
0x18008cb61  jb      short loc_18008CB34
0x18008cb63  lea     rcx, [rbp+pvarg]; pvarg
0x18008cb67  call    cs:__imp_VariantInit
0x18008cb6e  nop     dword ptr [rax+rax+00h]
0x18008cb73  mov     rdx, rbx; pvargSrc
0x18008cb76  lea     rcx, [rbp+pvarg]; pvarDest
0x18008cb7a  call    cs:__imp_VariantCopyInd
0x18008cb81  nop     dword ptr [rax+rax+00h]
0x18008cb86  jmp     loc_18008CAE9
```
