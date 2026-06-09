# CopyProperty(tagDBPROP *,tagDBPROP const *,bool,ulong)

- ea: `0x180013394`
- end: `0x180013610`
- name: `?CopyProperty@@YAJPEAUtagDBPROP@@PEBU1@_NK@Z`
- size: `636`
- prototype: `__int64 __fastcall(struct tagDBPROP *, const struct tagDBPROP *, bool, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000feec`
- `0x180012250`
- `0x1800130d0`
- `0x18001d49c`
- `0x180070950`
- `0x180074850`
- `0x180076e50`

## callees

- `0x180011c74`
- `0x180013394`
- `0x180013870`
- `0x18002ec26`
- `0x18003c2e8`
- `0x180049f18`
- `0x18004a084`

## import_xrefs

- `MSDART!mpMalloc` at `0x180013488`
- `MSDART!mpMalloc` at `0x1800134b2`
- `MSDART!mpMalloc` at `0x180013488`
- `MSDART!mpMalloc` at `0x1800134b2`
- `OLEAUT32!__imp_VariantCopy` at `0x18001354e`
- `OLEAUT32!__imp_VariantCopy` at `0x18001354e`
- `ole32!CoTaskMemAlloc` at `0x18001345a`
- `ole32!CoTaskMemAlloc` at `0x180013471`
- `ole32!CoTaskMemAlloc` at `0x18001345a`
- `ole32!CoTaskMemAlloc` at `0x180013471`

## string_xrefs

- `0x1800135ff`: `<CopyProperty|OLEDB|ERR> `

## pseudocode

```c
__int64 __fastcall CopyProperty(struct tagDBPROP *a1, const struct tagDBPROP *a2, char a3, int a4)
{
  DBKIND eKind; // ecx
  DBKIND v9; // ecx
  DBKIND v10; // ecx
  DBKIND v11; // ecx
  DBKIND v12; // ecx
  DBKIND v13; // ecx
  DBKIND v14; // ecx
  DBKIND v15; // ecx
  DBKIND v16; // ecx
  DBKIND v17; // ecx
  LPOLESTR pwszName; // rcx
  __int64 v19; // rax
  SIZE_T v20; // r14
  OLECHAR *v21; // rax
  GUID *v22; // rax
  VARIANTARG *p_vValue; // r15
  VARIANT *v24; // r14
  HRESULT v25; // eax
  unsigned int v26; // esi
  unsigned int v28; // r8d
  int v29; // ecx

  a1->dwPropertyID = a2->dwPropertyID;
  a1->dwOptions = a2->dwOptions;
  a1->dwStatus = a2->dwStatus;
  a1->colid = DB_NULLID;
  eKind = a2->colid.eKind;
  if ( !eKind || (v9 = eKind - 1) == 0 )
  {
LABEL_8:
    a1->colid.uGuid = a2->colid.uGuid;
    goto LABEL_9;
  }
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_9;
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( !v13 )
        goto LABEL_9;
      if ( v13 != 1 )
      {
LABEL_31:
        p_vValue = &a1->vValue;
        v24 = &a2->vValue;
        v25 = VariantCopy(&a1->vValue, &a2->vValue);
        v26 = v25;
        if ( v25 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v26;
          v28 = 421;
        }
        else
        {
          switch ( a4 )
          {
            case 2:
              if ( !v24->vt )
                return v26;
              if ( !a2->vValue.llVal )
                return v26;
              v25 = CDSLComVariant::DecryptBSTRValue(p_vValue);
              v26 = v25;
              if ( (bidGblFlags & 2) == 0 )
                return v26;
              v28 = 437;
              break;
            case 1:
              if ( !v24->vt )
                return v26;
              if ( !a2->vValue.llVal )
                return v26;
              v25 = CDSLComVariant::EncryptBSTRValue(p_vValue);
              v26 = v25;
              if ( (bidGblFlags & 2) == 0 )
                return v26;
              v28 = 449;
              break;
            case 0:
              return v26;
            default:
              v26 = -2147467259;
              if ( (bidGblFlags & 2) == 0 )
                return v26;
              v28 = 455;
              v29 = -2147467259;
              goto LABEL_50;
          }
        }
        v29 = v25;
LABEL_50:
        OLEDBTraceErr(v29, L"<CopyProperty|OLEDB|ERR> ", v28);
        return v26;
      }
      goto LABEL_8;
    }
  }
  if ( a3 )
    v22 = (GUID *)CoTaskMemAlloc(0x10u);
  else
    v22 = (GUID *)mpMalloc(16, a2);
  a1->colid.uGuid.pguid = v22;
  if ( !v22 )
    return 2147942414LL;
  *v22 = *a2->colid.uGuid.pguid;
LABEL_9:
  v14 = a2->colid.eKind;
  if ( !v14 )
    goto LABEL_13;
  v15 = v14 - 1;
  if ( !v15 )
  {
LABEL_26:
    a1->colid.uName.ulPropid = a2->colid.uName.ulPropid;
    goto LABEL_30;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      if ( v17 - 1 > 1 )
        goto LABEL_30;
      goto LABEL_26;
    }
  }
LABEL_13:
  pwszName = a2->colid.uName.pwszName;
  if ( !pwszName )
  {
LABEL_30:
    a1->colid.eKind = a2->colid.eKind;
    goto LABEL_31;
  }
  v19 = -1;
  do
    ++v19;
  while ( pwszName[v19] );
  v20 = (unsigned int)(2 * v19 + 2);
  if ( a3 )
    v21 = (OLECHAR *)CoTaskMemAlloc(v20);
  else
    v21 = (OLECHAR *)mpMalloc(v20, a2);
  a1->colid.uName.pwszName = v21;
  if ( v21 )
  {
    memcpy_0(v21, a2->colid.uName.pwszName, v20);
    goto LABEL_30;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180013394  mov     rax, rsp
0x180013397  mov     [rax+20h], r9d
0x18001339b  mov     [rax+18h], r8b
0x18001339f  mov     [rax+10h], rdx
0x1800133a3  mov     [rax+8], rcx
0x1800133a7  push    rbx
0x1800133a8  push    rsi
0x1800133a9  push    rdi
0x1800133aa  push    r12
0x1800133ac  push    r14
0x1800133ae  push    r15
0x1800133b0  sub     rsp, 28h
0x1800133b4  mov     r12d, r9d
0x1800133b7  mov     r15b, r8b
0x1800133ba  mov     rbx, rdx
0x1800133bd  mov     rsi, rcx
0x1800133c0  mov     eax, [rdx]
0x1800133c2  mov     [rcx], eax
0x1800133c4  mov     eax, [rdx+4]
0x1800133c7  mov     [rcx+4], eax
0x1800133ca  mov     eax, [rdx+8]
0x1800133cd  mov     [rcx+8], eax
0x1800133d0  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x1800133d7  movups  xmmword ptr [rcx+10h], xmm0
0x1800133db  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x1800133e2  movups  xmmword ptr [rcx+20h], xmm1
0x1800133e6  mov     ecx, [rdx+20h]
0x1800133e9  xor     edi, edi
0x1800133eb  test    ecx, ecx
0x1800133ed  jz      short loc_18001340D
0x1800133ef  sub     ecx, 1
0x1800133f2  jz      short loc_18001340D
0x1800133f4  sub     ecx, 1
0x1800133f7  jz      short loc_180013416
0x1800133f9  sub     ecx, 1
0x1800133fc  jz      short loc_180013467
0x1800133fe  sub     ecx, 1
0x180013401  jz      short loc_180013467
0x180013403  sub     ecx, 1
0x180013406  jz      short loc_180013416
0x180013408  cmp     ecx, 1
0x18001340b  jnz     short loc_180013462
0x18001340d  movups  xmm0, xmmword ptr [rdx+10h]
0x180013411  movdqu  xmmword ptr [rsi+10h], xmm0
0x180013416  mov     ecx, [rbx+20h]
0x180013419  test    ecx, ecx
0x18001341b  jz      short loc_180013430
0x18001341d  sub     ecx, 1
0x180013420  jz      loc_1800134AA
0x180013426  sub     ecx, 1
0x180013429  jz      short loc_180013430
0x18001342b  sub     ecx, 1
0x18001342e  jnz     short loc_1800134A0
0x180013430  mov     rcx, [rbx+28h]
0x180013434  test    rcx, rcx
0x180013437  jz      loc_1800134D4
0x18001343d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013441  inc     rax
0x180013444  cmp     [rcx+rax*2], di
0x180013448  jnz     short loc_180013441
0x18001344a  lea     r14d, ds:2[rax*2]
0x180013452  mov     ecx, r14d; cb
0x180013455  test    r15b, r15b
0x180013458  jz      short loc_1800134B2
0x18001345a  call    cs:__imp_CoTaskMemAlloc
0x180013460  jmp     short loc_1800134B8
0x180013462  jmp     loc_180013540
0x180013467  mov     ecx, 10h; cb
0x18001346c  test    r15b, r15b
0x18001346f  jz      short loc_180013488
0x180013471  call    cs:__imp_CoTaskMemAlloc
0x180013477  mov     [rsi+10h], rax
0x18001347b  mov     rcx, rax
0x18001347e  test    rax, rax
0x180013481  jnz     short loc_180013490
0x180013483  jmp     loc_18001358C
0x180013488  call    cs:__imp_mpMalloc
0x18001348e  jmp     short loc_180013477
0x180013490  mov     rax, [rbx+10h]
0x180013494  movups  xmm0, xmmword ptr [rax]
0x180013497  movdqu  xmmword ptr [rcx], xmm0
0x18001349b  jmp     loc_180013416
0x1800134a0  sub     ecx, 1
0x1800134a3  jz      short loc_1800134AA
0x1800134a5  cmp     ecx, 1
0x1800134a8  jnz     short loc_1800134D4
0x1800134aa  mov     eax, [rbx+28h]
0x1800134ad  mov     [rsi+28h], eax
0x1800134b0  jmp     short loc_1800134D4
0x1800134b2  call    cs:__imp_mpMalloc
0x1800134b8  mov     [rsi+28h], rax
0x1800134bc  test    rax, rax
0x1800134bf  jz      loc_18001358C
0x1800134c5  mov     r8, r14; Size
0x1800134c8  mov     rdx, [rbx+28h]; Src
0x1800134cc  mov     rcx, rax; void *
0x1800134cf  call    memcpy_0
0x1800134d4  mov     eax, [rbx+20h]
0x1800134d7  mov     [rsi+20h], eax
0x1800134da  jmp     short loc_180013540
0x1800134dc  test    byte ptr cs:_bidGblFlags, 2
0x1800134e3  jz      short loc_18001350C
0x1800134e5  mov     rax, cs:off_1800C8D90; "<CopyProperty|CATCH|ALL> "
0x1800134ec  test    rax, rax
0x1800134ef  jz      short loc_18001350C
0x1800134f1  xor     r9d, r9d
0x1800134f4  mov     r8, cs:off_1800C8D90; "<CopyProperty|CATCH|ALL> "
0x1800134fb  mov     edx, 66000h
0x180013500  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180013507  call    _bidTraceA
0x18001350c  mov     rsi, [rsp+58h+arg_0]
0x180013511  lea     rcx, [rsi+10h]; struct tagDBID *
0x180013515  mov     dl, [rsp+58h+arg_10]; bool
0x180013519  call    ?FreeDBID@@YAXPEAUtagDBID@@_N@Z; FreeDBID(tagDBID *,bool)
0x18001351e  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180013525  movups  xmmword ptr [rsi+10h], xmm0
0x180013529  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180013530  movups  xmmword ptr [rsi+20h], xmm1
0x180013534  xor     edi, edi
0x180013536  mov     r12d, [rsp+58h+arg_18]
0x18001353b  mov     rbx, [rsp+58h+arg_8]
0x180013540  lea     r15, [rsi+30h]
0x180013544  lea     r14, [rbx+30h]
0x180013548  mov     rdx, r14; pvargSrc
0x18001354b  mov     rcx, r15; pvargDest
0x18001354e  call    cs:__imp_VariantCopy
0x180013554  mov     esi, eax
0x180013556  test    eax, eax
0x180013558  js      short loc_18001357B
0x18001355a  cmp     r12d, 2
0x18001355e  jz      short loc_18001359D
0x180013560  cmp     r12d, 1
0x180013564  jz      short loc_1800135C4
0x180013566  test    r12d, r12d
0x180013569  jnz     short loc_1800135E5
0x18001356b  mov     eax, esi
0x18001356d  add     rsp, 28h
0x180013571  pop     r15
0x180013573  pop     r14
0x180013575  pop     r12
0x180013577  pop     rdi
0x180013578  pop     rsi
0x180013579  pop     rbx
0x18001357a  retn
0x18001357b  test    byte ptr cs:_bidGblFlags, 2
0x180013582  jz      short loc_18001356B
0x180013584  mov     r8d, 1A5h
0x18001358a  jmp     short loc_180013599
0x18001358c  mov     eax, 8007000Eh
0x180013591  jmp     short loc_18001356D
0x180013593  mov     r8d, 1C1h
0x180013599  mov     ecx, eax
0x18001359b  jmp     short loc_1800135FF
0x18001359d  cmp     [r14], di
0x1800135a1  jz      short loc_18001356B
0x1800135a3  cmp     [rbx+38h], rdi
0x1800135a7  jz      short loc_18001356B
0x1800135a9  mov     rcx, r15; pvarg
0x1800135ac  call    ?DecryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::DecryptBSTRValue(void)
0x1800135b1  mov     esi, eax
0x1800135b3  test    byte ptr cs:_bidGblFlags, 2
0x1800135ba  jz      short loc_18001356B
0x1800135bc  mov     r8d, 1B5h
0x1800135c2  jmp     short loc_180013599
0x1800135c4  cmp     [r14], di
0x1800135c8  jz      short loc_18001356B
0x1800135ca  cmp     [rbx+38h], rdi
0x1800135ce  jz      short loc_18001356B
0x1800135d0  mov     rcx, r15; pvarg
0x1800135d3  call    ?EncryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::EncryptBSTRValue(void)
0x1800135d8  mov     esi, eax
0x1800135da  test    byte ptr cs:_bidGblFlags, 2
0x1800135e1  jz      short loc_18001356B
0x1800135e3  jmp     short loc_180013593
0x1800135e5  mov     esi, 80004005h
0x1800135ea  test    byte ptr cs:_bidGblFlags, 2
0x1800135f1  jz      loc_18001356B
0x1800135f7  mov     r8d, 1C7h; unsigned int
0x1800135fd  mov     ecx, esi; int
0x1800135ff  lea     rdx, aCopypropertyOl; "<CopyProperty|OLEDB|ERR> "
0x180013606  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001360b  jmp     loc_18001356B
```
