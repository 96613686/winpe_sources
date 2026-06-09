# DispatchHelper::ConvertToString(tagVARIANT *,tagVARIANT *,Js::ScriptContext *)

- ea: `0x180102960`
- end: `0x180102a8c`
- name: `?ConvertToString@DispatchHelper@@CAJPEAUtagVARIANT@@0PEAVScriptContext@Js@@@Z`
- size: `300`
- prototype: `static int(struct tagVARIANT *, struct tagVARIANT *, struct Js::ScriptContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180102504`

## callees

- `0x180102960`
- `0x1801b4af8`
- `0x1801e8738`
- `0x180341dd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801029c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1801029c8`
- `OLEAUT32!__imp_VariantCopy` at `0x180102a81`
- `OLEAUT32!__imp_VariantCopy` at `0x180102a81`

## pseudocode

```c
int __fastcall DispatchHelper::ConvertToString(
        struct tagVARIANT *a1,
        struct tagVARIANT *a2,
        struct Js::ScriptContext *a3)
{
  int result; // eax
  BSTR v5; // rax
  const VARIANTARG *v6; // rdx
  OLECHAR psz[256]; // [rsp+20h] [rbp-218h] BYREF

  if ( !a2 )
    return -2147024809;
  if ( !a1->vt )
  {
    v6 = &cbstrUndefined;
    return VariantCopy(a2, v6);
  }
  if ( a1->vt == 1 )
    goto LABEL_20;
  if ( a1->vt != 3 && a1->vt != 5 )
  {
    if ( a1->vt == 7 )
      return DispatchHelper::ConvertVarDateToStr(a1->dblVal, a2, a3);
    if ( a1->vt == 8 )
    {
      if ( a1->llVal )
        return 0;
      v6 = (const VARIANTARG *)&cbstrEmpty;
      return VariantCopy(a2, v6);
    }
    if ( a1->vt != 9 )
    {
      if ( a1->vt == 11 )
      {
        v6 = (const VARIANTARG *)&cbstrTrue;
        if ( !a1->iVal )
          v6 = (const VARIANTARG *)&cbstrFalse;
        return VariantCopy(a2, v6);
      }
      return -2146823283;
    }
    if ( a1->llVal )
      return -2146823283;
LABEL_20:
    v6 = (const VARIANTARG *)&cbstrNull;
    return VariantCopy(a2, v6);
  }
  result = DispatchHelper::GetStringForNumber(a1, psz, (int)a3);
  if ( result < 0 )
    return result;
  v5 = SysAllocString(psz);
  if ( !v5 )
    return -2147024882;
  a2->vt = 8;
  a2->llVal = (LONGLONG)v5;
  return 0;
}

```

## disassembly

```asm
0x180102960  mov     r11, rsp
0x180102963  mov     [r11+20h], rbx
0x180102967  mov     [r11+18h], r8
0x18010296b  mov     [r11+10h], rdx
0x18010296f  mov     [r11+8], rcx
0x180102973  push    rdi
0x180102974  sub     rsp, 230h
0x18010297b  mov     rax, cs:__security_cookie
0x180102982  xor     rax, rsp
0x180102985  mov     [rsp+238h+var_18], rax
0x18010298d  xor     edi, edi
0x18010298f  mov     rbx, rdx
0x180102992  test    rdx, rdx
0x180102995  jz      short loc_180102A03
0x180102997  movzx   edx, word ptr [rcx]
0x18010299a  test    edx, edx
0x18010299c  jz      loc_180102A77
0x1801029a2  sub     edx, 1
0x1801029a5  jz      loc_180102A3C
0x1801029ab  sub     edx, 2
0x1801029ae  jz      short loc_1801029B5
0x1801029b0  sub     edx, 2
0x1801029b3  jnz     short loc_180102A0A
0x1801029b5  lea     rdx, [rsp+238h+psz]; unsigned __int16 *
0x1801029ba  call    ?GetStringForNumber@DispatchHelper@@CAJPEAUtagVARIANT@@PEAGH@Z; DispatchHelper::GetStringForNumber(tagVARIANT *,ushort *,int)
0x1801029bf  test    eax, eax
0x1801029c1  js      short loc_1801029E2
0x1801029c3  lea     rcx, [rsp+238h+psz]; psz
0x1801029c8  call    cs:__imp_SysAllocString
0x1801029ce  test    rax, rax
0x1801029d1  jz      loc_180102A6D
0x1801029d7  mov     word ptr [rbx], 8
0x1801029dc  mov     [rbx+8], rax
0x1801029e0  xor     eax, eax
0x1801029e2  mov     rcx, [rsp+238h+var_18]
0x1801029ea  xor     rcx, rsp; StackCookie
0x1801029ed  call    __security_check_cookie
0x1801029f2  mov     rbx, [rsp+238h+arg_18]
0x1801029fa  add     rsp, 230h
0x180102a01  pop     rdi
0x180102a02  retn
0x180102a03  mov     eax, 80070057h
0x180102a08  jmp     short loc_1801029E2
0x180102a0a  sub     edx, 2
0x180102a0d  jz      short loc_180102A5B
0x180102a0f  sub     edx, 1
0x180102a12  jz      short loc_180102A4C
0x180102a14  sub     edx, 1
0x180102a17  jz      short loc_180102A36
0x180102a19  cmp     edx, 2
0x180102a1c  jnz     short loc_180102A45
0x180102a1e  cmp     [rcx+8], di
0x180102a22  lea     rax, ?cbstrFalse@@3UConstBstr@@A; ConstBstr cbstrFalse
0x180102a29  lea     rdx, ?cbstrTrue@@3UConstBstr@@A; ConstBstr cbstrTrue
0x180102a30  cmovz   rdx, rax
0x180102a34  jmp     short loc_180102A7E
0x180102a36  cmp     [rcx+8], rdi
0x180102a3a  jnz     short loc_180102A45
0x180102a3c  lea     rdx, ?cbstrNull@@3UConstBstr@@A; ConstBstr cbstrNull
0x180102a43  jmp     short loc_180102A7E
0x180102a45  mov     eax, 800A138Dh
0x180102a4a  jmp     short loc_1801029E2
0x180102a4c  cmp     [rcx+8], rdi
0x180102a50  jnz     short loc_1801029E0
0x180102a52  lea     rdx, ?cbstrEmpty@@3UConstBstr@@A; ConstBstr cbstrEmpty
0x180102a59  jmp     short loc_180102A7E
0x180102a5b  movsd   xmm0, qword ptr [rcx+8]; double
0x180102a60  mov     rdx, rbx; struct tagVARIANT *
0x180102a63  call    ?ConvertVarDateToStr@DispatchHelper@@CAJNPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::ConvertVarDateToStr(double,tagVARIANT *,Js::ScriptContext *)
0x180102a68  jmp     loc_1801029E2
0x180102a6d  mov     eax, 8007000Eh
0x180102a72  jmp     loc_1801029E2
0x180102a77  lea     rdx, ?cbstrUndefined@@3UConstBstr@@A; pvargSrc
0x180102a7e  mov     rcx, rbx; pvargDest
0x180102a81  call    cs:__imp_VariantCopy
0x180102a87  jmp     loc_1801029E2
```
