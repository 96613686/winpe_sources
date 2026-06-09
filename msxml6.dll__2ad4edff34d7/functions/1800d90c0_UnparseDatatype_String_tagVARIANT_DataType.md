# UnparseDatatype(String * *,tagVARIANT *,DataType)

- ea: `0x1800d90c0`
- end: `0x1800d940c`
- name: `?UnparseDatatype@@YAJPEAPEAVString@@PEAUtagVARIANT@@W4DataType@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(String **ppReturn, tagVARIANT *pVar, DataType dt)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180087f50`

## callees

- `0x180009490`
- `0x18000d688`
- `0x18000d7d0`
- `0x1800502b0`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800d65dc`
- `0x1800d8b70`
- `0x1800d8d14`
- `0x1800d8f58`
- `0x1800d90c0`
- `0x1800d94a8`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800d93b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800d93b0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800d91d9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800d91d9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800d91b9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800d91b9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d91f6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d91f6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d9251`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d9251`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d92ba`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d9328`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d92ba`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d9328`

## pseudocode

```c
__int64 __fastcall UnparseDatatype(String **ppReturn, tagVARIANT *pVar, DataType dt)
{
  HRESULT LBound; // edi
  const wchar_t *bstrVal; // r14
  const wchar_t *v8; // rcx
  String *v9; // r9
  HRESULT v10; // eax
  int v11; // eax
  String *v12; // rbx
  String *p; // rax
  _reference<String> pString; // [rsp+38h] [rbp-70h] BYREF
  int lUBound; // [rsp+40h] [rbp-68h] BYREF
  int lLBound; // [rsp+44h] [rbp-64h] BYREF
  const wchar_t *pwsz; // [rsp+48h] [rbp-60h]
  tagVARIANT var; // [rsp+50h] [rbp-58h] BYREF
  _GUID uuid; // [rsp+68h] [rbp-40h] BYREF
  wchar_t wch[2]; // [rsp+C8h] [rbp+20h] BYREF

  LBound = 0;
  memset(&var, 0, sizeof(var));
  bstrVal = 0;
  pwsz = 0;
  *(_DWORD *)wch = 0;
  var.vt = 1;
  pString._p = 0;
  if ( dt > DT_DATETIME_ISO8601 )
  {
    if ( dt != DT_DATETIME_ISO8601TZ && dt != DT_TIME_ISO8601 && dt != DT_TIME_ISO8601TZ )
    {
      if ( dt == DT_UUID )
      {
        uuid = 0;
        LBound = VariantChangeTypeEx(&var, pVar, 0x409u, 1u, 8u);
        if ( LBound < 0 )
          goto $CleanUp_184;
        v11 = xstrlenw(var.bstrVal, 0x7FFFFFFFu);
        LBound = ParseUuid(var.bstrVal, v11, &uuid);
        if ( LBound < 0 )
          goto $CleanUp_184;
        bstrVal = var.bstrVal;
        pwsz = var.bstrVal;
      }
      else if ( dt == DT_USER_DEFINED )
      {
        LBound = -2147467259;
        goto $CleanUp_184;
      }
      goto LABEL_9;
    }
    goto LABEL_8;
  }
  switch ( dt )
  {
    case DT_DATETIME_ISO8601:
LABEL_8:
      LBound = UnparseISO8601(&pString._p, dt, &pVar->dblVal);
      if ( LBound < 0 )
        goto $CleanUp_184;
      break;
    case DT__NON_AV:
    case DT_BIN_HEX:
      lLBound = 0;
      lUBound = 0;
      *(_QWORD *)&uuid.Data1 = 0;
      LBound = SafeArrayGetLBound(pVar->parray, 1u, &lLBound);
      if ( LBound < 0 )
        goto $CleanUp_184;
      LBound = SafeArrayGetUBound(pVar->parray, 1u, &lUBound);
      if ( LBound < 0 )
        goto $CleanUp_184;
      LBound = SafeArrayAccessData(pVar->parray, (void **)&uuid);
      if ( LBound < 0 )
        goto $CleanUp_184;
      v10 = dt == DT_BIN_HEX
          ? UnparseBinHex(&pString._p, *(unsigned __int8 **)&uuid.Data1, lUBound - lLBound + 1)
          : UnparseBase64(*(unsigned __int8 **)&uuid.Data1, lUBound - lLBound + 1, &pString._p, v9);
      LBound = v10;
      SafeArrayUnaccessData(pVar->parray);
      if ( LBound < 0 )
        goto $CleanUp_184;
      break;
    case DT_BOOLEAN:
      bstrVal = L"1";
      if ( pVar->iVal != -1 )
        bstrVal = L"0";
      goto LABEL_12;
    case DT_CHAR:
      wch[0] = pVar->uiVal;
      bstrVal = wch;
LABEL_12:
      pwsz = bstrVal;
      break;
    case DT_DATE_ISO8601:
      goto LABEL_8;
  }
LABEL_9:
  if ( bstrVal )
  {
    v8 = bstrVal;
LABEL_36:
    v12 = String::newString(v8);
    release(&pString._p);
    pString._p = v12;
    goto $CleanUp_184;
  }
  if ( !pString._p )
  {
    LBound = VariantChangeTypeEx(&var, pVar, 0x409u, 1u, 8u);
    if ( LBound >= 0 )
    {
      v8 = var.bstrVal;
      goto LABEL_36;
    }
  }
$CleanUp_184:
  VariantClear(&var);
  p = pString._p;
  pString._p = 0;
  *ppReturn = p;
  release(&pString._p);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x1800d90c0  mov     r11, rsp
0x1800d90c3  mov     [r11+10h], rbx
0x1800d90c7  mov     [r11+18h], rsi
0x1800d90cb  mov     [r11+8], ppReturn
0x1800d90cf  push    rdi
0x1800d90d0  push    r12
0x1800d90d2  push    r13
0x1800d90d4  push    r14
0x1800d90d6  push    r15
0x1800d90d8  sub     rsp, 80h
0x1800d90df  mov     ebx, dt
0x1800d90e2  mov     r15, pVar
0x1800d90e5  mov     r12, ppReturn
0x1800d90e8  xor     esi, esi
0x1800d90ea  mov     edi, esi
0x1800d90ec  xorps   xmm0, xmm0
0x1800d90ef  xor     eax, eax
0x1800d90f1  movups  xmmword ptr [rsp+0A8h+var.___u0], xmm0
0x1800d90f6  mov     [r11-48h], rax
0x1800d90fa  mov     r14d, esi
0x1800d90fd  mov     [r11-60h], rsi
0x1800d9101  mov     [r11+20h], esi
0x1800d9105  lea     r13d, [rsi+1]
0x1800d9109  mov     [r11-58h], r13w
0x1800d910e  mov     [r11-70h], rsi
0x1800d9112  cmp     ebx, 11h
0x1800d9115  jg      loc_1800D9264
0x1800d911b  jz      short loc_1800D9138
0x1800d911d  mov     ecx, ebx
0x1800d911f  sub     ecx, 0Ch
0x1800d9122  jz      short loc_1800D91A0
0x1800d9124  sub     ecx, r13d
0x1800d9127  jz      short loc_1800D91A0
0x1800d9129  sub     ecx, r13d
0x1800d912c  jz      short loc_1800D9187
0x1800d912e  sub     ecx, r13d
0x1800d9131  jz      short loc_1800D916C
0x1800d9133  cmp     ecx, r13d
0x1800d9136  jnz     short loc_1800D9156
0x1800d9138  lea     r8, [pVar+8]; pdate
0x1800d913c  mov     edx, ebx; dt
0x1800d913e  lea     ppReturn, [rsp+0A8h+pString]; ppReturn
0x1800d9143  call    ?UnparseISO8601@@YAJPEAPEAVString@@W4DataType@@PEAN@Z; UnparseISO8601(String * *,DataType,double *)
0x1800d9148  mov     edi, eax
0x1800d914a  mov     [rsp+0A8h+hr], eax
0x1800d914e  test    eax, eax
0x1800d9150  js      $CleanUp_184
0x1800d9156  mov     ebx, 8
0x1800d915b  test    r14, r14
0x1800d915e  jz      loc_1800D930B
0x1800d9164  mov     ppReturn, r14
0x1800d9167  jmp     loc_1800D933D
0x1800d916c  movzx   eax, word ptr [pVar+8]
0x1800d9170  mov     [rsp+0A8h+wch], ax
0x1800d9178  lea     r14, [rsp+0A8h+wch]
0x1800d9180  mov     [rsp+0A8h+pwsz], r14
0x1800d9185  jmp     short loc_1800D9156
0x1800d9187  lea     r14, a1_0; "1"
0x1800d918e  lea     rax, a0_0; "0"
0x1800d9195  cmp     word ptr [pVar+8], 0FFFFh
0x1800d919a  cmovnz  r14, rax
0x1800d919e  jmp     short loc_1800D9180
0x1800d91a0  mov     [rsp+0A8h+lLBound], esi
0x1800d91a4  mov     [rsp+0A8h+lUBound], esi
0x1800d91a8  mov     qword ptr [rsp+0A8h+uuid.Data1], rsi
0x1800d91ad  lea     r8, [rsp+0A8h+lLBound]; plLbound
0x1800d91b2  mov     edx, r13d; nDim
0x1800d91b5  mov     ppReturn, [r15+8]; psa
0x1800d91b9  call    cs:__imp_SafeArrayGetLBound
0x1800d91bf  mov     edi, eax
0x1800d91c1  mov     [rsp+0A8h+hr], eax
0x1800d91c5  test    eax, eax
0x1800d91c7  js      $CleanUp_184
0x1800d91cd  lea     r8, [rsp+0A8h+lUBound]; plUbound
0x1800d91d2  mov     edx, r13d; nDim
0x1800d91d5  mov     ppReturn, [r15+8]; psa
0x1800d91d9  call    cs:__imp_SafeArrayGetUBound
0x1800d91df  mov     edi, eax
0x1800d91e1  mov     [rsp+0A8h+hr], eax
0x1800d91e5  test    eax, eax
0x1800d91e7  js      $CleanUp_184
0x1800d91ed  lea     pVar, [rsp+0A8h+uuid]; ppvData
0x1800d91f2  mov     ppReturn, [r15+8]; psa
0x1800d91f6  call    cs:__imp_SafeArrayAccessData
0x1800d91fc  mov     edi, eax
0x1800d91fe  mov     [rsp+0A8h+hr], eax
0x1800d9202  test    eax, eax
0x1800d9204  js      $CleanUp_184
0x1800d920a  cmp     ebx, 0Dh
0x1800d920d  jnz     short loc_1800D922D
0x1800d920f  mov     dt, [rsp+0A8h+lUBound]
0x1800d9214  sub     dt, [rsp+0A8h+lLBound]
0x1800d9219  add     dt, r13d; lLen
0x1800d921c  mov     pVar, qword ptr [rsp+0A8h+uuid.Data1]; abData
0x1800d9221  lea     ppReturn, [rsp+0A8h+pString]; ppReturn
0x1800d9226  call    ?UnparseBinHex@@YAJPEAPEAVString@@PEAEJ@Z; UnparseBinHex(String * *,uchar *,long)
0x1800d922b  jmp     short loc_1800D9247
0x1800d922d  mov     edx, [rsp+0A8h+lUBound]
0x1800d9231  sub     edx, [rsp+0A8h+lLBound]
0x1800d9235  add     edx, r13d; cbData
0x1800d9238  lea     r8, [rsp+0A8h+pString]; ppReturn
0x1800d923d  mov     ppReturn, qword ptr [rsp+0A8h+uuid.Data1]; pvData
0x1800d9242  call    ?UnparseBase64@@YAJPEAXHPEAPEAVString@@PEAV1@@Z; UnparseBase64(void *,int,String * *,String *)
0x1800d9247  mov     [rsp+0A8h+hr], eax
0x1800d924b  mov     edi, eax
0x1800d924d  mov     ppReturn, [r15+8]; psa
0x1800d9251  call    cs:__imp_SafeArrayUnaccessData
0x1800d9257  test    edi, edi
0x1800d9259  jns     loc_1800D9156
0x1800d925f  jmp     $CleanUp_184
0x1800d9264  mov     ecx, ebx
0x1800d9266  sub     ecx, 12h
0x1800d9269  jz      loc_1800D9138
0x1800d926f  sub     ecx, 0Dh
0x1800d9272  jz      loc_1800D9138
0x1800d9278  sub     ecx, 1
0x1800d927b  jz      loc_1800D9138
0x1800d9281  sub     ecx, 6
0x1800d9284  jz      short loc_1800D929D
0x1800d9286  cmp     ecx, 1
0x1800d9289  jnz     loc_1800D9156
0x1800d928f  mov     edi, 80004005h
0x1800d9294  mov     [rsp+0A8h+hr], edi
0x1800d9298  jmp     $CleanUp_184
0x1800d929d  movups  xmmword ptr [rsp+0A8h+uuid.Data1], xmm0
0x1800d92a2  mov     ebx, 8
0x1800d92a7  mov     r9d, r13d; wFlags
0x1800d92aa  mov     [rsp+0A8h+vt], bx; vt
0x1800d92af  mov     dt, 409h; lcid
0x1800d92b5  lea     ppReturn, [rsp+0A8h+var]; pvargDest
0x1800d92ba  call    cs:__imp_VariantChangeTypeEx
0x1800d92c0  mov     edi, eax
0x1800d92c2  mov     [rsp+0A8h+hr], eax
0x1800d92c6  test    eax, eax
0x1800d92c8  js      $CleanUp_184
0x1800d92ce  mov     edx, 7FFFFFFFh; cchMax
0x1800d92d3  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; psz
0x1800d92d8  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800d92dd  mov     edx, eax; cch
0x1800d92df  lea     r8, [rsp+0A8h+uuid]; pUuid
0x1800d92e4  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; pS
0x1800d92e9  call    ?ParseUuid@@YAJPEBGHPEAU_GUID@@@Z; ParseUuid(ushort const *,int,_GUID *)
0x1800d92ee  mov     edi, eax
0x1800d92f0  mov     [rsp+0A8h+hr], eax
0x1800d92f4  test    eax, eax
0x1800d92f6  js      $CleanUp_184
0x1800d92fc  mov     r14, qword ptr [rsp+0A8h+var.___u0+8]
0x1800d9301  mov     [rsp+0A8h+pwsz], r14
0x1800d9306  jmp     loc_1800D915B
0x1800d930b  cmp     [rsp+0A8h+pString._p], rsi
0x1800d9310  jnz     short loc_1800D9354
0x1800d9312  mov     r9d, r13d; wFlags
0x1800d9315  mov     [rsp+0A8h+vt], bx; vt
0x1800d931a  mov     dt, 409h; lcid
0x1800d9320  mov     pVar, r15; pvarSrc
0x1800d9323  lea     ppReturn, [rsp+0A8h+var]; pvargDest
0x1800d9328  call    cs:__imp_VariantChangeTypeEx
0x1800d932e  mov     edi, eax
0x1800d9330  mov     [rsp+0A8h+hr], eax
0x1800d9334  test    eax, eax
0x1800d9336  js      short $CleanUp_184
0x1800d9338  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; c
0x1800d933d  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800d9342  mov     rbx, rax
0x1800d9345  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800d934a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d934f  mov     [rsp+0A8h+pString._p], rbx
0x1800d9354  jmp     short $CleanUp_184
0x1800d9356  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800d935b  cmp     [rsp+0A8h+pString._p], 0
0x1800d9361  jz      short loc_1800D936F
0x1800d9363  xor     edx, edx; pref
0x1800d9365  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800d936a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d936f  mov     ecx, cs:_tls_index
0x1800d9375  mov     rax, gs:58h
0x1800d937e  mov     edx, 8
0x1800d9383  mov     rax, [rax+ppReturn*8]
0x1800d9387  mov     ppReturn, [rax+pVar]
0x1800d938b  mov     ppReturn, [ppReturn+8]
0x1800d938f  mov     rax, [ppReturn]
0x1800d9392  mov     rax, [rax+68h]
0x1800d9396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d939b  mov     edi, eax
0x1800d939d  mov     [rsp+0A8h+hr], eax
0x1800d93a1  xor     esi, esi
0x1800d93a3  mov     r12, [rsp+0A8h+arg_0]
0x1800d93ab  lea     ppReturn, [rsp+0A8h+var]; pvarg
0x1800d93b0  call    cs:__imp_VariantClear
0x1800d93b6  mov     rax, [rsp+0A8h+pString._p]
0x1800d93bb  mov     [rsp+0A8h+pString._p], rsi
0x1800d93c0  mov     [r12], rax
0x1800d93c4  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800d93c9  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d93ce  mov     eax, edi
0x1800d93d0  lea     r11, [rsp+0A8h+var_28]
0x1800d93d8  mov     rbx, [r11+38h]
0x1800d93dc  mov     rsi, [r11+40h]
0x1800d93e0  mov     rsp, r11
0x1800d93e3  pop     r15
0x1800d93e5  pop     r14
0x1800d93e7  pop     r13
0x1800d93e9  pop     r12
0x1800d93eb  pop     rdi
0x1800d93ec  retn
0x1800d93ed  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800d93f2  cmp     [rsp+0A8h+pString._p], 0
0x1800d93f8  jz      short loc_1800D9406
0x1800d93fa  xor     edx, edx; pref
0x1800d93fc  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800d9401  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d9406  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x18017ee25  push    rbp
0x18017ee27  sub     rsp, 30h
0x18017ee2b  mov     rbp, rdx
0x18017ee2e  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017ee33  nop
0x18017ee34  add     rsp, 30h
0x18017ee38  pop     rbp
0x18017ee39  retn
0x18017ee3b  push    rbp
0x18017ee3d  sub     rsp, 30h
0x18017ee41  mov     rbp, rdx
0x18017ee44  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017ee49  nop
0x18017ee4a  add     rsp, 30h
0x18017ee4e  pop     rbp
0x18017ee4f  retn
```
