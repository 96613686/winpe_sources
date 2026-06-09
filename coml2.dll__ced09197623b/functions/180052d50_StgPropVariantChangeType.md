# StgPropVariantChangeType

- ea: `0x180052d50`
- end: `0x180052e37`
- name: `StgPropVariantChangeType`
- size: `231`
- prototype: `__int64 __usercall@<rax>(struct tagPROPVARIANT *@<rcx>, __int16)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052378`
- `0x180052980`
- `0x180055f40`

## callees

- `0x180050b44`
- `0x180051a7c`
- `0x180051b64`
- `0x180052d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052d8a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052d8a`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180052dba`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180052dba`

## pseudocode

```c
HRESULT __fastcall StgPropVariantChangeType(PROPVARIANT *a1, const PROPVARIANT *a2, LCID a3, USHORT a4, __int16 a5)
{
  unsigned __int16 v8; // di
  HRESULT result; // eax
  LCID v10; // r8d
  USHORT v11; // r9
  const VARIANTARG *v12; // r10
  VARTYPE vt; // r11
  tagPROPVARIANT *v14; // rdx
  tagPROPVARIANT v15; // [rsp+30h] [rbp-48h] BYREF

  if ( !a1 || !a2 )
    return -2147024809;
  v8 = *(_WORD *)a2;
  if ( a5 == *(_WORD *)a2 )
    return PropVariantCopy(a1, a2);
  if ( (unsigned int)FIsAVariantType(v8) && (unsigned int)FIsAVariantType(vt) )
    return VariantChangeTypeEx((VARIANTARG *)a1, v12, v10, v11, vt);
  if ( (v8 & 0x2000) != 0 || (vt & 0x4000) != 0 )
    return -2147352571;
  v14 = (tagPROPVARIANT *)v12;
  if ( (v8 & 0x4000) != 0 )
  {
    memset(&v15, 0, sizeof(v15));
    result = HrConvertByRef(&v15, (const struct tagPROPVARIANT *)v12);
    if ( result )
      return result;
    v11 = a4;
    v14 = &v15;
    v10 = a3;
  }
  return HrConvertPVTypes((struct tagPROPVARIANT *)a1, v14, v10, v11, vt);
}

```

## disassembly

```asm
0x180052d50  push    rbx
0x180052d52  push    rbp
0x180052d53  push    rsi
0x180052d54  push    rdi
0x180052d55  sub     rsp, 58h
0x180052d59  movzx   esi, r9w
0x180052d5d  mov     ebp, r8d
0x180052d60  mov     r10, rdx
0x180052d63  mov     rbx, rcx
0x180052d66  test    rcx, rcx
0x180052d69  jz      loc_180052E29
0x180052d6f  test    rdx, rdx
0x180052d72  jz      loc_180052E29
0x180052d78  movzx   edi, word ptr [rdx]
0x180052d7b  movzx   r11d, [rsp+78h+arg_20]
0x180052d84  cmp     r11w, di
0x180052d88  jnz     short loc_180052D95
0x180052d8a  call    cs:__imp_PropVariantCopy
0x180052d90  jmp     loc_180052E2E
0x180052d95  movzx   ecx, di; unsigned __int16
0x180052d98  call    ?FIsAVariantType@@YAHG@Z; FIsAVariantType(ushort)
0x180052d9d  test    eax, eax
0x180052d9f  jz      short loc_180052DC2
0x180052da1  movzx   ecx, r11w; unsigned __int16
0x180052da5  call    ?FIsAVariantType@@YAHG@Z; FIsAVariantType(ushort)
0x180052daa  test    eax, eax
0x180052dac  jz      short loc_180052DC2
0x180052dae  mov     rdx, r10; pvarSrc
0x180052db1  mov     [rsp+78h+vt], r11w; vt
0x180052db7  mov     rcx, rbx; pvargDest
0x180052dba  call    cs:__imp_VariantChangeTypeEx
0x180052dc0  jmp     short loc_180052E2E
0x180052dc2  mov     eax, 0Dh
0x180052dc7  bt      di, ax
0x180052dcb  mov     eax, 0Eh
0x180052dd0  setnb   cl
0x180052dd3  bt      r11w, ax
0x180052dd8  setnb   al
0x180052ddb  test    al, cl
0x180052ddd  jz      short loc_180052E22
0x180052ddf  bt      di, 0Eh
0x180052de4  mov     rdx, r10; struct tagPROPVARIANT *
0x180052de7  jnb     short loc_180052E12
0x180052de9  xorps   xmm0, xmm0
0x180052dec  lea     rcx, [rsp+78h+var_48]; struct tagPROPVARIANT *
0x180052df1  xor     eax, eax
0x180052df3  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x180052df8  mov     qword ptr [rsp+78h+var_48+10h], rax
0x180052dfd  call    ?HrConvertByRef@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; HrConvertByRef(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180052e02  test    eax, eax
0x180052e04  jnz     short loc_180052E2E
0x180052e06  movzx   r9d, si; unsigned __int16
0x180052e0a  lea     rdx, [rsp+78h+var_48]; struct tagPROPVARIANT *
0x180052e0f  mov     r8d, ebp; unsigned int
0x180052e12  mov     rcx, rbx; struct tagPROPVARIANT *
0x180052e15  mov     [rsp+78h+vt], r11w; unsigned __int16
0x180052e1b  call    ?HrConvertPVTypes@@YAJPEAUtagPROPVARIANT@@PEBU1@KGG@Z; HrConvertPVTypes(tagPROPVARIANT *,tagPROPVARIANT const *,ulong,ushort,ushort)
0x180052e20  jmp     short loc_180052E2E
0x180052e22  mov     eax, 80020005h
0x180052e27  jmp     short loc_180052E2E
0x180052e29  mov     eax, 80070057h
0x180052e2e  add     rsp, 58h
0x180052e32  pop     rdi
0x180052e33  pop     rsi
0x180052e34  pop     rbp
0x180052e35  pop     rbx
0x180052e36  retn
```
