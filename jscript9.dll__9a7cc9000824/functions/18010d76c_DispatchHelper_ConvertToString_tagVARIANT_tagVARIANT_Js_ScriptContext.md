# DispatchHelper::ConvertToString(tagVARIANT *,tagVARIANT *,Js::ScriptContext *)

- ea: `0x18010d76c`
- end: `0x18010d8a5`
- name: `?ConvertToString@DispatchHelper@@CAJPEAUtagVARIANT@@0PEAVScriptContext@Js@@@Z`
- size: `313`
- prototype: `int __fastcall(struct tagVARIANT *, struct tagVARIANT *, struct Js::ScriptContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18010d304`

## callees

- `0x18010d76c`
- `0x1801b7254`
- `0x1801ebb68`
- `0x1803481f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18010d7d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18010d7d4`
- `OLEAUT32!__imp_VariantCopy` at `0x18010d894`
- `OLEAUT32!__imp_VariantCopy` at `0x18010d894`

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
  result = DispatchHelper::GetStringForNumber(a1, psz);
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
0x18010d76c  mov     r11, rsp
0x18010d76f  mov     [r11+20h], rbx
0x18010d773  mov     [r11+18h], r8
0x18010d777  mov     [r11+10h], rdx
0x18010d77b  mov     [r11+8], rcx
0x18010d77f  push    rdi
0x18010d780  sub     rsp, 230h
0x18010d787  mov     rax, cs:__security_cookie
0x18010d78e  xor     rax, rsp
0x18010d791  mov     [rsp+238h+var_18], rax
0x18010d799  xor     edi, edi
0x18010d79b  mov     rbx, rdx
0x18010d79e  test    rdx, rdx
0x18010d7a1  jz      short loc_18010D816
0x18010d7a3  movzx   edx, word ptr [rcx]
0x18010d7a6  test    edx, edx
0x18010d7a8  jz      loc_18010D88A
0x18010d7ae  sub     edx, 1
0x18010d7b1  jz      loc_18010D84F
0x18010d7b7  sub     edx, 2
0x18010d7ba  jz      short loc_18010D7C1
0x18010d7bc  sub     edx, 2
0x18010d7bf  jnz     short loc_18010D81D
0x18010d7c1  lea     rdx, [rsp+238h+psz]; unsigned __int16 *
0x18010d7c6  call    ?GetStringForNumber@DispatchHelper@@CAJPEAUtagVARIANT@@PEAGH@Z; DispatchHelper::GetStringForNumber(tagVARIANT *,ushort *,int)
0x18010d7cb  test    eax, eax
0x18010d7cd  js      short loc_18010D7F4
0x18010d7cf  lea     rcx, [rsp+238h+psz]; psz
0x18010d7d4  call    cs:__imp_SysAllocString
0x18010d7db  nop     dword ptr [rax+rax+00h]
0x18010d7e0  test    rax, rax
0x18010d7e3  jz      loc_18010D880
0x18010d7e9  mov     word ptr [rbx], 8
0x18010d7ee  mov     [rbx+8], rax
0x18010d7f2  xor     eax, eax
0x18010d7f4  mov     rcx, [rsp+238h+var_18]
0x18010d7fc  xor     rcx, rsp; StackCookie
0x18010d7ff  call    __security_check_cookie
0x18010d804  mov     rbx, [rsp+238h+arg_18]
0x18010d80c  add     rsp, 230h
0x18010d813  pop     rdi
0x18010d814  retn
0x18010d816  mov     eax, 80070057h
0x18010d81b  jmp     short loc_18010D7F4
0x18010d81d  sub     edx, 2
0x18010d820  jz      short loc_18010D86E
0x18010d822  sub     edx, 1
0x18010d825  jz      short loc_18010D85F
0x18010d827  sub     edx, 1
0x18010d82a  jz      short loc_18010D849
0x18010d82c  cmp     edx, 2
0x18010d82f  jnz     short loc_18010D858
0x18010d831  cmp     [rcx+8], di
0x18010d835  lea     rax, ?cbstrFalse@@3UConstBstr@@A; ConstBstr cbstrFalse
0x18010d83c  lea     rdx, ?cbstrTrue@@3UConstBstr@@A; ConstBstr cbstrTrue
0x18010d843  cmovz   rdx, rax
0x18010d847  jmp     short loc_18010D891
0x18010d849  cmp     [rcx+8], rdi
0x18010d84d  jnz     short loc_18010D858
0x18010d84f  lea     rdx, ?cbstrNull@@3UConstBstr@@A; ConstBstr cbstrNull
0x18010d856  jmp     short loc_18010D891
0x18010d858  mov     eax, 800A138Dh
0x18010d85d  jmp     short loc_18010D7F4
0x18010d85f  cmp     [rcx+8], rdi
0x18010d863  jnz     short loc_18010D7F2
0x18010d865  lea     rdx, ?cbstrEmpty@@3UConstBstr@@A; ConstBstr cbstrEmpty
0x18010d86c  jmp     short loc_18010D891
0x18010d86e  movsd   xmm0, qword ptr [rcx+8]; double
0x18010d873  mov     rdx, rbx; struct tagVARIANT *
0x18010d876  call    ?ConvertVarDateToStr@DispatchHelper@@CAJNPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::ConvertVarDateToStr(double,tagVARIANT *,Js::ScriptContext *)
0x18010d87b  jmp     loc_18010D7F4
0x18010d880  mov     eax, 8007000Eh
0x18010d885  jmp     loc_18010D7F4
0x18010d88a  lea     rdx, ?cbstrUndefined@@3UConstBstr@@A; pvargSrc
0x18010d891  mov     rcx, rbx; pvargDest
0x18010d894  call    cs:__imp_VariantCopy
0x18010d89b  nop     dword ptr [rax+rax+00h]
0x18010d8a0  jmp     loc_18010D7F4
```
