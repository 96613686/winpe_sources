# UnparseDatatype(String * *,tagVARIANT *,DataType)

- ea: `0x1007be5b`
- end: `0x1007c12b`
- name: `?UnparseDatatype@@YGJPAPAVString@@PAUtagVARIANT@@W4DataType@@@Z`
- size: `720`
- prototype: `HRESULT __userpurge@<eax>(String **ppReturn@<ecx>, tagVARIANT *pVar@<edx>, DataType dt)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1009c567`

## callees

- `0x1003fb13`
- `0x10040b56`
- `0x10040bb4`
- `0x1004fbae`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100781cb`
- `0x1007b94a`
- `0x1007bad0`
- `0x1007bce9`
- `0x1007be5b`
- `0x1007c1a7`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x1007c0cd`
- `OLEAUT32!__imp__VariantClear@4` at `0x1007c0cd`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x1007bf1c`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x1007bf1c`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x1007befd`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x1007befd`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007bf39`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007bf39`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007bf85`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007bf85`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007bfef`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007c048`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007bfef`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007c048`

## pseudocode

```c
HRESULT __fastcall UnparseDatatype(String **ppReturn, tagVARIANT *pVar, DataType dt)
{
  int LBound; // edi
  const wchar_t *bstrVal; // esi
  int v5; // ecx
  HRESULT v6; // eax
  const wchar_t *v7; // ecx
  int v8; // eax
  String *v9; // esi
  String *p; // ecx
  struct String **v12; // [esp+0h] [ebp-6Ch]
  struct String *v13; // [esp+4h] [ebp-68h]
  _GUID uuid; // [esp+10h] [ebp-5Ch] BYREF
  tagVARIANT var; // [esp+20h] [ebp-4Ch] BYREF
  String **v16; // [esp+30h] [ebp-3Ch]
  int lLBound; // [esp+34h] [ebp-38h] BYREF
  int lUBound; // [esp+38h] [ebp-34h] BYREF
  const wchar_t *pwsz; // [esp+3Ch] [ebp-30h]
  unsigned __int8 *pB; // [esp+40h] [ebp-2Ch] BYREF
  wchar_t wch[2]; // [esp+44h] [ebp-28h] BYREF
  tagVARIANT *v22; // [esp+48h] [ebp-24h]
  HRESULT hr; // [esp+4Ch] [ebp-20h]
  _reference<String> pString; // [esp+50h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+54h] [ebp-18h]

  v22 = pVar;
  v16 = ppReturn;
  LBound = 0;
  bstrVal = 0;
  pwsz = 0;
  *(_DWORD *)wch = 0;
  var.vt = 1;
  pString._p = 0;
  ms_exc.registration.TryLevel = 0;
  if ( dt <= DT_DATETIME_ISO8601 )
  {
    if ( dt != DT_DATETIME_ISO8601 )
    {
      switch ( dt )
      {
        case DT__NON_AV:
        case DT_BIN_HEX:
          pB = 0;
          LBound = SafeArrayGetLBound(pVar->parray, 1u, &lLBound);
          hr = LBound;
          if ( LBound < 0 )
            goto LABEL_39;
          LBound = SafeArrayGetUBound(v22->parray, 1u, &lUBound);
          hr = LBound;
          if ( LBound < 0 )
            goto LABEL_39;
          LBound = SafeArrayAccessData(v22->parray, (void **)&pB);
          hr = LBound;
          if ( LBound < 0 )
            goto LABEL_39;
          if ( dt == DT_BIN_HEX )
            v6 = UnparseBinHex(&pString._p, pB, lUBound - lLBound + 1);
          else
            v6 = UnparseBase64(&pString._p, v5, v12, v13);
          LBound = v6;
          hr = v6;
          SafeArrayUnaccessData(v22->parray);
          goto LABEL_21;
        case DT_BOOLEAN:
          bstrVal = L"1";
          if ( pVar->iVal != -1 )
            bstrVal = L"0";
          break;
        case DT_CHAR:
          wch[0] = pVar->uiVal;
          bstrVal = wch;
          break;
        case DT_DATE_ISO8601:
          goto LABEL_8;
        default:
          goto LABEL_23;
      }
      pwsz = bstrVal;
      goto LABEL_23;
    }
LABEL_8:
    LBound = UnparseISO8601(&pString._p, dt, &pVar->dblVal);
    hr = LBound;
LABEL_21:
    if ( LBound >= 0 )
    {
LABEL_22:
      pVar = v22;
      goto LABEL_23;
    }
    goto LABEL_39;
  }
  switch ( dt )
  {
    case DT_DATETIME_ISO8601TZ:
    case DT_TIME_ISO8601:
    case DT_TIME_ISO8601TZ:
      goto LABEL_8;
    case DT_UUID:
      LBound = VariantChangeTypeEx(&var, pVar, 0x409u, 1u, 8u);
      hr = LBound;
      if ( LBound >= 0 )
      {
        v8 = xstrlenw(var.bstrVal, 0x7FFFFFFFu);
        LBound = ParseUuid(var.bstrVal, v8, &uuid);
        hr = LBound;
        if ( LBound >= 0 )
        {
          bstrVal = var.bstrVal;
          pwsz = var.bstrVal;
          goto LABEL_22;
        }
      }
LABEL_39:
      ms_exc.registration.TryLevel = -2;
      goto CleanUp_50;
    case DT_USER_DEFINED:
      LBound = -2147467259;
      hr = -2147467259;
      goto LABEL_39;
  }
LABEL_23:
  ms_exc.registration.TryLevel = 1;
  if ( bstrVal )
  {
    v7 = bstrVal;
  }
  else
  {
    if ( pString._p )
      goto LABEL_36;
    LBound = VariantChangeTypeEx(&var, pVar, 0x409u, 1u, 8u);
    hr = LBound;
    if ( LBound < 0 )
      goto LABEL_36;
    v7 = var.bstrVal;
  }
  v9 = String::newString(v7);
  release(&pString._p);
  pString._p = v9;
LABEL_36:
  ms_exc.registration.TryLevel = -2;
CleanUp_50:
  VariantClear(&var);
  p = pString._p;
  pString._p = 0;
  *v16 = p;
  release(&pString._p);
  return LBound;
}

```

## disassembly

```asm
0x1007be5b  push    4Ch
0x1007be5d  push    offset stru_10174518
0x1007be62  call    __SEH_prolog4
0x1007be67  mov     [ebp+var_24], pVar
0x1007be6a  mov     [ebp+var_3C], ppReturn
0x1007be6d  xor     edi, edi
0x1007be6f  xor     esi, esi
0x1007be71  mov     [ebp+pwsz], esi
0x1007be74  xor     eax, eax
0x1007be76  mov     dword ptr [ebp+wch], eax
0x1007be79  xor     ppReturn, ppReturn
0x1007be7b  inc     ppReturn
0x1007be7c  mov     word ptr [ebp+var.___u0], cx
0x1007be80  mov     [ebp+pString._p], eax
0x1007be83  mov     [ebp+ms_exc.registration.TryLevel], eax
0x1007be86  mov     ebx, [ebp+dt]
0x1007be89  cmp     ebx, 11h
0x1007be8c  jg      loc_1007BFB1
0x1007be92  jz      short loc_1007BEAF
0x1007be94  mov     eax, ebx
0x1007be96  sub     eax, 0Ch
0x1007be99  jz      short loc_1007BEEE
0x1007be9b  sub     eax, ppReturn
0x1007be9d  jz      short loc_1007BEEE
0x1007be9f  sub     eax, ppReturn
0x1007bea1  jz      short loc_1007BEDA
0x1007bea3  sub     eax, ppReturn
0x1007bea5  jz      short loc_1007BEC7
0x1007bea7  sub     eax, ppReturn
0x1007bea9  jnz     loc_1007BF99
0x1007beaf  lea     eax, [pVar+8]
0x1007beb2  push    eax; pdate
0x1007beb3  mov     pVar, ebx; dt
0x1007beb5  lea     ppReturn, [ebp+pString]; ppReturn
0x1007beb8  call    ?UnparseISO8601@@YGJPAPAVString@@W4DataType@@PAN@Z; UnparseISO8601(String * *,DataType,double *)
0x1007bebd  mov     edi, eax
0x1007bebf  mov     [ebp+hr], edi
0x1007bec2  jmp     loc_1007BF8B
0x1007bec7  mov     ax, [pVar+8]
0x1007becb  mov     [ebp+wch], ax
0x1007becf  lea     esi, [ebp+wch]
0x1007bed2  mov     [ebp+pwsz], esi
0x1007bed5  jmp     loc_1007BF99
0x1007beda  mov     esi, offset a1_1; "1"
0x1007bedf  mov     eax, offset a0_1; "0"
0x1007bee4  cmp     word ptr [pVar+8], 0FFFFh
0x1007bee9  cmovnz  esi, eax
0x1007beec  jmp     short loc_1007BED2
0x1007beee  mov     [ebp+pB], 0
0x1007bef5  lea     eax, [ebp+lLBound]
0x1007bef8  push    eax; plLbound
0x1007bef9  push    ppReturn; nDim
0x1007befa  push    dword ptr [pVar+8]; psa
0x1007befd  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x1007bf03  mov     edi, eax
0x1007bf05  mov     [ebp+hr], edi
0x1007bf08  test    edi, edi
0x1007bf0a  js      loc_1007C0C2
0x1007bf10  lea     eax, [ebp+lUBound]
0x1007bf13  push    eax; plUbound
0x1007bf14  push    1; nDim
0x1007bf16  mov     eax, [ebp+var_24]
0x1007bf19  push    dword ptr [eax+8]; psa
0x1007bf1c  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x1007bf22  mov     edi, eax
0x1007bf24  mov     [ebp+hr], edi
0x1007bf27  test    edi, edi
0x1007bf29  js      loc_1007C0C2
0x1007bf2f  lea     eax, [ebp+pB]
0x1007bf32  push    eax; ppvData
0x1007bf33  mov     eax, [ebp+var_24]
0x1007bf36  push    dword ptr [eax+8]; psa
0x1007bf39  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1007bf3f  mov     edi, eax
0x1007bf41  mov     [ebp+hr], edi
0x1007bf44  test    edi, edi
0x1007bf46  js      loc_1007C0C2
0x1007bf4c  cmp     ebx, 0Dh
0x1007bf4f  jnz     short loc_1007BF66
0x1007bf51  mov     eax, [ebp+lUBound]
0x1007bf54  sub     eax, [ebp+lLBound]
0x1007bf57  inc     eax
0x1007bf58  push    eax; lLen
0x1007bf59  mov     pVar, [ebp+pB]; abData
0x1007bf5c  lea     ppReturn, [ebp+pString]; ppReturn
0x1007bf5f  call    ?UnparseBinHex@@YGJPAPAVString@@PAEJ@Z; UnparseBinHex(String * *,uchar *,long)
0x1007bf64  jmp     short loc_1007BF7A
0x1007bf66  mov     pVar, [ebp+lUBound]
0x1007bf69  sub     pVar, [ebp+lLBound]
0x1007bf6c  inc     pVar; cbData
0x1007bf6d  push    ppReturn
0x1007bf6e  lea     eax, [ebp+pString]
0x1007bf71  push    eax; ppReturn
0x1007bf72  mov     ppReturn, [ebp+pB]; pvData
0x1007bf75  call    ?UnparseBase64@@YGJPAXHPAPAVString@@PAV1@@Z; UnparseBase64(void *,int,String * *,String *)
0x1007bf7a  mov     edi, eax
0x1007bf7c  mov     [ebp+hr], edi
0x1007bf7f  mov     eax, [ebp+var_24]
0x1007bf82  push    dword ptr [eax+8]; psa
0x1007bf85  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1007bf8b  test    edi, edi
0x1007bf8d  js      loc_1007C0C2
0x1007bf93  xor     ppReturn, ppReturn
0x1007bf95  inc     ppReturn
0x1007bf96  mov     pVar, [ebp+var_24]
0x1007bf99  push    0FFFFFFFEh
0x1007bf9b  pop     ebx
0x1007bf9c  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1007bf9f  mov     [ebp+ms_exc.registration.TryLevel], ppReturn
0x1007bfa2  test    esi, esi
0x1007bfa4  jz      loc_1007C035
0x1007bfaa  mov     ppReturn, esi
0x1007bfac  jmp     loc_1007C05F
0x1007bfb1  mov     eax, ebx
0x1007bfb3  sub     eax, 12h
0x1007bfb6  jz      loc_1007BEAF
0x1007bfbc  sub     eax, 0Dh
0x1007bfbf  jz      loc_1007BEAF
0x1007bfc5  sub     eax, 1
0x1007bfc8  jz      loc_1007BEAF
0x1007bfce  sub     eax, 6
0x1007bfd1  jz      short loc_1007BFE2
0x1007bfd3  sub     eax, 1
0x1007bfd6  jnz     short loc_1007BF99
0x1007bfd8  mov     edi, 80004005h
0x1007bfdd  jmp     loc_1007C0BF
0x1007bfe2  push    8; vt
0x1007bfe4  push    ppReturn; wFlags
0x1007bfe5  push    409h; lcid
0x1007bfea  push    pVar; pvarSrc
0x1007bfeb  lea     eax, [ebp+var]
0x1007bfee  push    eax; pvargDest
0x1007bfef  call    ds:__imp__VariantChangeTypeEx@20; VariantChangeTypeEx(x,x,x,x,x)
0x1007bff5  mov     edi, eax
0x1007bff7  mov     [ebp+hr], edi
0x1007bffa  test    edi, edi
0x1007bffc  js      loc_1007C0C2
0x1007c002  lea     eax, [ebp+uuid]
0x1007c005  push    eax; pUuid
0x1007c006  mov     pVar, 7FFFFFFFh; cchMax
0x1007c00b  mov     ppReturn, dword ptr [ebp+var.___u0+8]; psz
0x1007c00e  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x1007c013  mov     pVar, eax; cch
0x1007c015  mov     ppReturn, dword ptr [ebp+var.___u0+8]; pS
0x1007c018  call    ?ParseUuid@@YGJPBGHPAU_GUID@@@Z; ParseUuid(ushort const *,int,_GUID *)
0x1007c01d  mov     edi, eax
0x1007c01f  mov     [ebp+hr], edi
0x1007c022  test    edi, edi
0x1007c024  js      loc_1007C0C2
0x1007c02a  mov     esi, dword ptr [ebp+var.___u0+8]
0x1007c02d  mov     [ebp+pwsz], esi
0x1007c030  jmp     loc_1007BF93
0x1007c035  cmp     [ebp+pString._p], 0
0x1007c039  jnz     short loc_1007C057
0x1007c03b  push    8; vt
0x1007c03d  push    ppReturn; wFlags
0x1007c03e  push    409h; lcid
0x1007c043  push    pVar; pvarSrc
0x1007c044  lea     eax, [ebp+var]
0x1007c047  push    eax; pvargDest
0x1007c048  call    ds:__imp__VariantChangeTypeEx@20; VariantChangeTypeEx(x,x,x,x,x)
0x1007c04e  mov     edi, eax
0x1007c050  mov     [ebp+hr], edi
0x1007c053  test    edi, edi
0x1007c055  jns     short loc_1007C05C
0x1007c057  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1007c05a  jmp     short CleanUp_50
0x1007c05c  mov     ppReturn, dword ptr [ebp+var.___u0+8]; c
0x1007c05f  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1007c064  mov     esi, eax
0x1007c066  lea     ppReturn, [ebp+pString]; ppref
0x1007c069  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1007c06e  mov     [ebp+pString._p], esi
0x1007c071  jmp     short loc_1007C057
0x1007c073  mov     ppReturn, [ebp+ms_exc.exc_ptr]; ep
0x1007c076  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007c07b  retn
0x1007c07c  mov     esp, [ebp+ms_exc.old_esp]
0x1007c07f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007c084  cmp     [ebp+pString._p], 0
0x1007c088  jz      short loc_1007C094
0x1007c08a  xor     pVar, pVar; pref
0x1007c08c  lea     ppReturn, [ebp+pString]; ppref
0x1007c08f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1007c094  mov     ppReturn, __tls_index
0x1007c09a  mov     eax, large fs:2Ch
0x1007c0a0  mov     eax, [eax+ppReturn*4]
0x1007c0a3  mov     eax, [eax+4]
0x1007c0a9  mov     edi, [eax+8]
0x1007c0ac  mov     eax, [edi]
0x1007c0ae  mov     esi, [eax+34h]
0x1007c0b1  mov     ppReturn, esi; this
0x1007c0b3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1007c0b9  mov     ppReturn, edi
0x1007c0bb  call    esi
0x1007c0bd  mov     edi, eax
0x1007c0bf  mov     [ebp+hr], edi
0x1007c0c2  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007c0c9  lea     eax, [ebp+var]
0x1007c0cc  push    eax; pvarg
0x1007c0cd  call    ds:__imp__VariantClear@4; VariantClear(x)
0x1007c0d3  mov     ppReturn, [ebp+pString._p]
0x1007c0d6  mov     [ebp+pString._p], 0
0x1007c0dd  mov     eax, [ebp+var_3C]
0x1007c0e0  mov     [eax], ppReturn
0x1007c0e2  lea     ppReturn, [ebp+pString]; ppref
0x1007c0e5  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1007c0ea  mov     eax, edi
0x1007c0ec  mov     ppReturn, [ebp+ms_exc.registration.Next]
0x1007c0ef  mov     large fs:0, ppReturn
0x1007c0f6  pop     ppReturn
0x1007c0f7  pop     edi
0x1007c0f8  pop     esi
0x1007c0f9  pop     ebx
0x1007c0fa  leave
0x1007c0fb  retn    4
0x1007c0fe  mov     ppReturn, [ebp+ms_exc.exc_ptr]; ep
0x1007c101  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007c106  retn
0x1007c107  mov     esp, [ebp+ms_exc.old_esp]
0x1007c10a  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007c10f  cmp     [ebp+pString._p], 0
0x1007c113  jz      short loc_1007C11F
0x1007c115  xor     pVar, pVar; pref
0x1007c117  lea     ppReturn, [ebp+pString]; ppref
0x1007c11a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1007c11f  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
```
