# SCHEMA_ATTRIBUTE::CopyVariant(tagVARIANT,ATTRIBUTE_VALUE *,VALIDATION_EXCEPTION * *)

- ea: `0x1800364e8`
- end: `0x1800366db`
- name: `?CopyVariant@SCHEMA_ATTRIBUTE@@QEAAJUtagVARIANT@@PEAVATTRIBUTE_VALUE@@PEAPEAVVALIDATION_EXCEPTION@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(SCHEMA_ATTRIBUTE *__hidden this, VARIANTARG *pvargSrc, struct ATTRIBUTE_VALUE *, struct VALIDATION_EXCEPTION **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180058160`

## callees

- `0x1800124bc`
- `0x180017e90`
- `0x18001bdc4`
- `0x18001d584`
- `0x18001d5c4`
- `0x18001d640`
- `0x18001d680`
- `0x18001d6c0`
- `0x18001d7f0`
- `0x18001d830`
- `0x1800364e8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180036517`
- `OLEAUT32!__imp_VariantInit` at `0x180036517`
- `OLEAUT32!__imp_VariantClear` at `0x1800366c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800366c4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800365ea`
- `OLEAUT32!__imp_VariantCopy` at `0x1800365ea`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800365db`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800365db`

## pseudocode

```c
__int64 __fastcall SCHEMA_ATTRIBUTE::CopyVariant(
        SCHEMA_ATTRIBUTE *this,
        VARIANTARG *pvargSrc,
        struct ATTRIBUTE_VALUE *a3,
        struct VALIDATION_EXCEPTION **a4)
{
  int v8; // ecx
  VARTYPE v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // edi
  HRESULT v12; // eax
  int v13; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a3 || !a4 )
  {
    v11 = -2147024809;
    goto LABEL_45;
  }
  v8 = *((_DWORD *)this + 10);
  if ( v8 == 1 )
  {
    v9 = 8;
    goto LABEL_18;
  }
  if ( v8 == 2 || (unsigned int)(v8 - 5) <= 1 )
  {
    v9 = 3;
  }
  else
  {
    switch ( v8 )
    {
      case 9:
        v9 = 19;
        break;
      case 4:
        v9 = 11;
        break;
      case 7:
        goto LABEL_12;
      case 3:
        v9 = 20;
        break;
      case 10:
LABEL_12:
        v9 = 21;
        break;
      default:
        v9 = 1;
        break;
    }
  }
LABEL_18:
  if ( v9 == pvargSrc->vt )
  {
    v12 = VariantCopy(&pvarg, pvargSrc);
  }
  else
  {
    if ( pvargSrc->vt == 8 )
    {
      v10 = SCHEMA_ATTRIBUTE::CopyString(this, pvargSrc->bstrVal, a3, 0, a4, 42, 0);
LABEL_21:
      v11 = v10;
      goto LABEL_45;
    }
    v12 = VariantChangeType(&pvarg, pvargSrc, 0, v9);
  }
  v11 = v12;
  if ( v12 < 0 )
    goto LABEL_45;
  v13 = *((_DWORD *)this + 10);
  switch ( v13 )
  {
    case 1:
      v10 = ATTRIBUTE_VALUE::SetString(a3, pvarg.bstrVal, 1);
      goto LABEL_21;
    case 2:
      ATTRIBUTE_VALUE::SetInt(a3, pvarg.lVal);
      break;
    case 6:
      ATTRIBUTE_VALUE::SetEnum(a3, pvarg.cyVal.Lo);
      break;
    case 5:
      ATTRIBUTE_VALUE::SetFlags(a3, pvarg.cyVal.Lo);
      break;
    case 7:
      ATTRIBUTE_VALUE::SetTimeSpan(a3, pvarg.llVal);
      break;
    case 4:
      ATTRIBUTE_VALUE::SetBool(a3, pvarg.iVal == -1);
      break;
    case 9:
      ATTRIBUTE_VALUE::SetUInt(a3, pvarg.cyVal.Lo);
      break;
    case 3:
      ATTRIBUTE_VALUE::SetInt64(a3, pvarg.llVal);
      break;
    case 10:
      ATTRIBUTE_VALUE::SetUInt64(a3, pvarg.ullVal);
      break;
    default:
      v11 = -2147024846;
      break;
  }
LABEL_45:
  VariantClear(&pvarg);
  return v11;
}

```

## disassembly

```asm
0x1800364e8  push    rbp
0x1800364ea  push    rbx
0x1800364eb  push    rsi
0x1800364ec  push    rdi
0x1800364ed  push    r12
0x1800364ef  push    r14
0x1800364f1  push    r15
0x1800364f3  mov     rbp, rsp
0x1800364f6  sub     rsp, 60h
0x1800364fa  mov     r14, rcx
0x1800364fd  xorps   xmm0, xmm0
0x180036500  xor     eax, eax
0x180036502  lea     rcx, [rbp+pvarg]; pvarg
0x180036506  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003650a  mov     qword ptr [rbp+pvarg+10h], rax
0x18003650e  mov     rsi, r9
0x180036511  mov     rbx, r8
0x180036514  mov     rdi, rdx
0x180036517  call    cs:__imp_VariantInit
0x18003651d  test    rbx, rbx
0x180036520  jz      loc_1800366BB
0x180036526  test    rsi, rsi
0x180036529  jz      loc_1800366BB
0x18003652f  mov     ecx, [r14+28h]
0x180036533  mov     edx, 8
0x180036538  lea     r15d, [rdx-7]
0x18003653c  lea     r12d, [rdx-5]
0x180036540  cmp     ecx, r15d
0x180036543  jnz     short loc_18003654B
0x180036545  movzx   r9d, dx
0x180036549  jmp     short loc_180036597
0x18003654b  cmp     ecx, 2
0x18003654e  jz      short loc_180036593
0x180036550  lea     eax, [rcx-5]
0x180036553  cmp     eax, r15d
0x180036556  jbe     short loc_180036593
0x180036558  cmp     ecx, 9
0x18003655b  jnz     short loc_180036563
0x18003655d  lea     r9d, [rcx+0Ah]
0x180036561  jmp     short loc_180036597
0x180036563  cmp     ecx, 4
0x180036566  jnz     short loc_18003656E
0x180036568  lea     r9d, [rcx+7]
0x18003656c  jmp     short loc_180036597
0x18003656e  cmp     ecx, 7
0x180036571  jnz     short loc_18003657B
0x180036573  mov     r9d, 15h
0x180036579  jmp     short loc_180036597
0x18003657b  cmp     ecx, r12d
0x18003657e  jnz     short loc_180036588
0x180036580  mov     r9d, 14h
0x180036586  jmp     short loc_180036597
0x180036588  cmp     ecx, 0Ah
0x18003658b  jz      short loc_180036573
0x18003658d  movzx   r9d, r15w
0x180036591  jmp     short loc_180036597
0x180036593  movzx   r9d, r12w; vt
0x180036597  cmp     r9w, [rdi]
0x18003659b  jz      short loc_1800365E3
0x18003659d  cmp     [rdi], dx
0x1800365a0  jnz     short loc_1800365D1
0x1800365a2  mov     rdx, [rdi+8]; String1
0x1800365a6  xor     r9d, r9d; struct CONFIG_FILE *
0x1800365a9  mov     [rsp+60h+var_30], 0; int *
0x1800365b2  mov     r8, rbx; struct ATTRIBUTE_VALUE *
0x1800365b5  mov     [rsp+60h+var_38], 2Ah ; '*'; unsigned int
0x1800365bd  mov     rcx, r14; this
0x1800365c0  mov     [rsp+60h+var_40], rsi; struct VALIDATION_EXCEPTION **
0x1800365c5  call    ?CopyString@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@PEAVCONFIG_FILE@@PEAPEAVVALIDATION_EXCEPTION@@KPEAH@Z; SCHEMA_ATTRIBUTE::CopyString(ushort const *,ATTRIBUTE_VALUE *,CONFIG_FILE *,VALIDATION_EXCEPTION * *,ulong,int *)
0x1800365ca  mov     edi, eax
0x1800365cc  jmp     loc_1800366C0
0x1800365d1  xor     r8d, r8d; wFlags
0x1800365d4  lea     rcx, [rbp+pvarg]; pvargDest
0x1800365d8  mov     rdx, rdi; pvarSrc
0x1800365db  call    cs:__imp_VariantChangeType
0x1800365e1  jmp     short loc_1800365F0
0x1800365e3  mov     rdx, rdi; pvargSrc
0x1800365e6  lea     rcx, [rbp+pvarg]; pvargDest
0x1800365ea  call    cs:__imp_VariantCopy
0x1800365f0  mov     edi, eax
0x1800365f2  test    eax, eax
0x1800365f4  js      loc_1800366C0
0x1800365fa  mov     eax, [r14+28h]
0x1800365fe  cmp     eax, r15d
0x180036601  jnz     short loc_180036614
0x180036603  mov     rdx, qword ptr [rbp+pvarg+8]; Src
0x180036607  mov     r8d, r15d; int
0x18003660a  mov     rcx, rbx; this
0x18003660d  call    ?SetString@ATTRIBUTE_VALUE@@QEAAJPEBGH@Z; ATTRIBUTE_VALUE::SetString(ushort const *,int)
0x180036612  jmp     short loc_1800365CA
0x180036614  cmp     eax, 2
0x180036617  jnz     short loc_180036629
0x180036619  mov     edx, dword ptr [rbp+pvarg+8]; int
0x18003661c  mov     rcx, rbx; this
0x18003661f  call    ?SetInt@ATTRIBUTE_VALUE@@QEAAJH@Z; ATTRIBUTE_VALUE::SetInt(int)
0x180036624  jmp     loc_1800366C0
0x180036629  cmp     eax, 6
0x18003662c  jnz     short loc_18003663E
0x18003662e  mov     edx, dword ptr [rbp+pvarg+8]; unsigned int
0x180036631  mov     rcx, rbx; this
0x180036634  call    ?SetEnum@ATTRIBUTE_VALUE@@QEAAJK@Z; ATTRIBUTE_VALUE::SetEnum(ulong)
0x180036639  jmp     loc_1800366C0
0x18003663e  cmp     eax, 5
0x180036641  jnz     short loc_180036650
0x180036643  mov     edx, dword ptr [rbp+pvarg+8]; unsigned int
0x180036646  mov     rcx, rbx; this
0x180036649  call    ?SetFlags@ATTRIBUTE_VALUE@@QEAAJK@Z; ATTRIBUTE_VALUE::SetFlags(ulong)
0x18003664e  jmp     short loc_1800366C0
0x180036650  cmp     eax, 7
0x180036653  jnz     short loc_180036663
0x180036655  mov     rdx, qword ptr [rbp+pvarg+8]; __int64
0x180036659  mov     rcx, rbx; this
0x18003665c  call    ?SetTimeSpan@ATTRIBUTE_VALUE@@QEAAJ_J@Z; ATTRIBUTE_VALUE::SetTimeSpan(__int64)
0x180036661  jmp     short loc_1800366C0
0x180036663  cmp     eax, 4
0x180036666  jnz     short loc_18003667C
0x180036668  xor     edx, edx
0x18003666a  mov     rcx, rbx; this
0x18003666d  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x180036672  setz    dl; int
0x180036675  call    ?SetBool@ATTRIBUTE_VALUE@@QEAAJH@Z; ATTRIBUTE_VALUE::SetBool(int)
0x18003667a  jmp     short loc_1800366C0
0x18003667c  cmp     eax, 9
0x18003667f  jnz     short loc_18003668E
0x180036681  mov     edx, dword ptr [rbp+pvarg+8]; unsigned int
0x180036684  mov     rcx, rbx; this
0x180036687  call    ?SetUInt@ATTRIBUTE_VALUE@@QEAAJI@Z; ATTRIBUTE_VALUE::SetUInt(uint)
0x18003668c  jmp     short loc_1800366C0
0x18003668e  cmp     eax, r12d
0x180036691  jnz     short loc_1800366A1
0x180036693  mov     rdx, qword ptr [rbp+pvarg+8]; __int64
0x180036697  mov     rcx, rbx; this
0x18003669a  call    ?SetInt64@ATTRIBUTE_VALUE@@QEAAJ_J@Z; ATTRIBUTE_VALUE::SetInt64(__int64)
0x18003669f  jmp     short loc_1800366C0
0x1800366a1  cmp     eax, 0Ah
0x1800366a4  jnz     short loc_1800366B4
0x1800366a6  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int64
0x1800366aa  mov     rcx, rbx; this
0x1800366ad  call    ?SetUInt64@ATTRIBUTE_VALUE@@QEAAJ_K@Z; ATTRIBUTE_VALUE::SetUInt64(unsigned __int64)
0x1800366b2  jmp     short loc_1800366C0
0x1800366b4  mov     edi, 80070032h
0x1800366b9  jmp     short loc_1800366C0
0x1800366bb  mov     edi, 80070057h
0x1800366c0  lea     rcx, [rbp+pvarg]; pvarg
0x1800366c4  call    cs:__imp_VariantClear
0x1800366ca  mov     eax, edi
0x1800366cc  add     rsp, 60h
0x1800366d0  pop     r15
0x1800366d2  pop     r14
0x1800366d4  pop     r12
0x1800366d6  pop     rdi
0x1800366d7  pop     rsi
0x1800366d8  pop     rbx
0x1800366d9  pop     rbp
0x1800366da  retn
```
