# UnparseDatatype(String * *,tagVARIANT *,DataType)

- ea: `0x1007be1b`
- end: `0x1007c0eb`
- name: `?UnparseDatatype@@YGJPAPAVString@@PAUtagVARIANT@@W4DataType@@@Z`
- size: `720`
- prototype: `HRESULT __userpurge@<eax>(String **ppReturn@<ecx>, tagVARIANT *pVar@<edx>, DataType dt)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1009c4a7`

## callees

- `0x1003fba3`
- `0x10040be6`
- `0x10040c44`
- `0x1004fc3e`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1007818b`
- `0x1007b90a`
- `0x1007ba90`
- `0x1007bca9`
- `0x1007be1b`
- `0x1007c167`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x1007c08d`
- `OLEAUT32!__imp__VariantClear@4` at `0x1007c08d`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x1007bedc`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x1007bedc`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x1007bebd`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x1007bebd`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007bef9`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007bef9`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007bf45`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007bf45`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007bfaf`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007c008`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007bfaf`
- `OLEAUT32!__imp__VariantChangeTypeEx@20` at `0x1007c008`

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
0x1007be1b  push    4Ch
0x1007be1d  push    offset stru_10174428
0x1007be22  call    __SEH_prolog4
0x1007be27  mov     [ebp+var_24], pVar
0x1007be2a  mov     [ebp+var_3C], ppReturn
0x1007be2d  xor     edi, edi
0x1007be2f  xor     esi, esi
0x1007be31  mov     [ebp+pwsz], esi
0x1007be34  xor     eax, eax
0x1007be36  mov     dword ptr [ebp+wch], eax
0x1007be39  xor     ppReturn, ppReturn
0x1007be3b  inc     ppReturn
0x1007be3c  mov     word ptr [ebp+var.___u0], cx
0x1007be40  mov     [ebp+pString._p], eax
0x1007be43  mov     [ebp+ms_exc.registration.TryLevel], eax
0x1007be46  mov     ebx, [ebp+dt]
0x1007be49  cmp     ebx, 11h
0x1007be4c  jg      loc_1007BF71
0x1007be52  jz      short loc_1007BE6F
0x1007be54  mov     eax, ebx
0x1007be56  sub     eax, 0Ch
0x1007be59  jz      short loc_1007BEAE
0x1007be5b  sub     eax, ppReturn
0x1007be5d  jz      short loc_1007BEAE
0x1007be5f  sub     eax, ppReturn
0x1007be61  jz      short loc_1007BE9A
0x1007be63  sub     eax, ppReturn
0x1007be65  jz      short loc_1007BE87
0x1007be67  sub     eax, ppReturn
0x1007be69  jnz     loc_1007BF59
0x1007be6f  lea     eax, [pVar+8]
0x1007be72  push    eax; pdate
0x1007be73  mov     pVar, ebx; dt
0x1007be75  lea     ppReturn, [ebp+pString]; ppReturn
0x1007be78  call    ?UnparseISO8601@@YGJPAPAVString@@W4DataType@@PAN@Z; UnparseISO8601(String * *,DataType,double *)
0x1007be7d  mov     edi, eax
0x1007be7f  mov     [ebp+hr], edi
0x1007be82  jmp     loc_1007BF4B
0x1007be87  mov     ax, [pVar+8]
0x1007be8b  mov     [ebp+wch], ax
0x1007be8f  lea     esi, [ebp+wch]
0x1007be92  mov     [ebp+pwsz], esi
0x1007be95  jmp     loc_1007BF59
0x1007be9a  mov     esi, offset a1_1; "1"
0x1007be9f  mov     eax, offset a0_1; "0"
0x1007bea4  cmp     word ptr [pVar+8], 0FFFFh
0x1007bea9  cmovnz  esi, eax
0x1007beac  jmp     short loc_1007BE92
0x1007beae  mov     [ebp+pB], 0
0x1007beb5  lea     eax, [ebp+lLBound]
0x1007beb8  push    eax; plLbound
0x1007beb9  push    ppReturn; nDim
0x1007beba  push    dword ptr [pVar+8]; psa
0x1007bebd  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x1007bec3  mov     edi, eax
0x1007bec5  mov     [ebp+hr], edi
0x1007bec8  test    edi, edi
0x1007beca  js      loc_1007C082
0x1007bed0  lea     eax, [ebp+lUBound]
0x1007bed3  push    eax; plUbound
0x1007bed4  push    1; nDim
0x1007bed6  mov     eax, [ebp+var_24]
0x1007bed9  push    dword ptr [eax+8]; psa
0x1007bedc  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x1007bee2  mov     edi, eax
0x1007bee4  mov     [ebp+hr], edi
0x1007bee7  test    edi, edi
0x1007bee9  js      loc_1007C082
0x1007beef  lea     eax, [ebp+pB]
0x1007bef2  push    eax; ppvData
0x1007bef3  mov     eax, [ebp+var_24]
0x1007bef6  push    dword ptr [eax+8]; psa
0x1007bef9  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1007beff  mov     edi, eax
0x1007bf01  mov     [ebp+hr], edi
0x1007bf04  test    edi, edi
0x1007bf06  js      loc_1007C082
0x1007bf0c  cmp     ebx, 0Dh
0x1007bf0f  jnz     short loc_1007BF26
0x1007bf11  mov     eax, [ebp+lUBound]
0x1007bf14  sub     eax, [ebp+lLBound]
0x1007bf17  inc     eax
0x1007bf18  push    eax; lLen
0x1007bf19  mov     pVar, [ebp+pB]; abData
0x1007bf1c  lea     ppReturn, [ebp+pString]; ppReturn
0x1007bf1f  call    ?UnparseBinHex@@YGJPAPAVString@@PAEJ@Z; UnparseBinHex(String * *,uchar *,long)
0x1007bf24  jmp     short loc_1007BF3A
0x1007bf26  mov     pVar, [ebp+lUBound]
0x1007bf29  sub     pVar, [ebp+lLBound]
0x1007bf2c  inc     pVar; cbData
0x1007bf2d  push    ppReturn
0x1007bf2e  lea     eax, [ebp+pString]
0x1007bf31  push    eax; ppReturn
0x1007bf32  mov     ppReturn, [ebp+pB]; pvData
0x1007bf35  call    ?UnparseBase64@@YGJPAXHPAPAVString@@PAV1@@Z; UnparseBase64(void *,int,String * *,String *)
0x1007bf3a  mov     edi, eax
0x1007bf3c  mov     [ebp+hr], edi
0x1007bf3f  mov     eax, [ebp+var_24]
0x1007bf42  push    dword ptr [eax+8]; psa
0x1007bf45  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1007bf4b  test    edi, edi
0x1007bf4d  js      loc_1007C082
0x1007bf53  xor     ppReturn, ppReturn
0x1007bf55  inc     ppReturn
0x1007bf56  mov     pVar, [ebp+var_24]
0x1007bf59  push    0FFFFFFFEh
0x1007bf5b  pop     ebx
0x1007bf5c  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1007bf5f  mov     [ebp+ms_exc.registration.TryLevel], ppReturn
0x1007bf62  test    esi, esi
0x1007bf64  jz      loc_1007BFF5
0x1007bf6a  mov     ppReturn, esi
0x1007bf6c  jmp     loc_1007C01F
0x1007bf71  mov     eax, ebx
0x1007bf73  sub     eax, 12h
0x1007bf76  jz      loc_1007BE6F
0x1007bf7c  sub     eax, 0Dh
0x1007bf7f  jz      loc_1007BE6F
0x1007bf85  sub     eax, 1
0x1007bf88  jz      loc_1007BE6F
0x1007bf8e  sub     eax, 6
0x1007bf91  jz      short loc_1007BFA2
0x1007bf93  sub     eax, 1
0x1007bf96  jnz     short loc_1007BF59
0x1007bf98  mov     edi, 80004005h
0x1007bf9d  jmp     loc_1007C07F
0x1007bfa2  push    8; vt
0x1007bfa4  push    ppReturn; wFlags
0x1007bfa5  push    409h; lcid
0x1007bfaa  push    pVar; pvarSrc
0x1007bfab  lea     eax, [ebp+var]
0x1007bfae  push    eax; pvargDest
0x1007bfaf  call    ds:__imp__VariantChangeTypeEx@20; VariantChangeTypeEx(x,x,x,x,x)
0x1007bfb5  mov     edi, eax
0x1007bfb7  mov     [ebp+hr], edi
0x1007bfba  test    edi, edi
0x1007bfbc  js      loc_1007C082
0x1007bfc2  lea     eax, [ebp+uuid]
0x1007bfc5  push    eax; pUuid
0x1007bfc6  mov     pVar, 7FFFFFFFh; cchMax
0x1007bfcb  mov     ppReturn, dword ptr [ebp+var.___u0+8]; psz
0x1007bfce  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x1007bfd3  mov     pVar, eax; cch
0x1007bfd5  mov     ppReturn, dword ptr [ebp+var.___u0+8]; pS
0x1007bfd8  call    ?ParseUuid@@YGJPBGHPAU_GUID@@@Z; ParseUuid(ushort const *,int,_GUID *)
0x1007bfdd  mov     edi, eax
0x1007bfdf  mov     [ebp+hr], edi
0x1007bfe2  test    edi, edi
0x1007bfe4  js      loc_1007C082
0x1007bfea  mov     esi, dword ptr [ebp+var.___u0+8]
0x1007bfed  mov     [ebp+pwsz], esi
0x1007bff0  jmp     loc_1007BF53
0x1007bff5  cmp     [ebp+pString._p], 0
0x1007bff9  jnz     short loc_1007C017
0x1007bffb  push    8; vt
0x1007bffd  push    ppReturn; wFlags
0x1007bffe  push    409h; lcid
0x1007c003  push    pVar; pvarSrc
0x1007c004  lea     eax, [ebp+var]
0x1007c007  push    eax; pvargDest
0x1007c008  call    ds:__imp__VariantChangeTypeEx@20; VariantChangeTypeEx(x,x,x,x,x)
0x1007c00e  mov     edi, eax
0x1007c010  mov     [ebp+hr], edi
0x1007c013  test    edi, edi
0x1007c015  jns     short loc_1007C01C
0x1007c017  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1007c01a  jmp     short CleanUp_50
0x1007c01c  mov     ppReturn, dword ptr [ebp+var.___u0+8]; c
0x1007c01f  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1007c024  mov     esi, eax
0x1007c026  lea     ppReturn, [ebp+pString]; ppref
0x1007c029  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1007c02e  mov     [ebp+pString._p], esi
0x1007c031  jmp     short loc_1007C017
0x1007c033  mov     ppReturn, [ebp+ms_exc.exc_ptr]; ep
0x1007c036  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007c03b  retn
0x1007c03c  mov     esp, [ebp+ms_exc.old_esp]
0x1007c03f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007c044  cmp     [ebp+pString._p], 0
0x1007c048  jz      short loc_1007C054
0x1007c04a  xor     pVar, pVar; pref
0x1007c04c  lea     ppReturn, [ebp+pString]; ppref
0x1007c04f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1007c054  mov     ppReturn, __tls_index
0x1007c05a  mov     eax, large fs:2Ch
0x1007c060  mov     eax, [eax+ppReturn*4]
0x1007c063  mov     eax, [eax+4]
0x1007c069  mov     edi, [eax+8]
0x1007c06c  mov     eax, [edi]
0x1007c06e  mov     esi, [eax+34h]
0x1007c071  mov     ppReturn, esi; this
0x1007c073  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1007c079  mov     ppReturn, edi
0x1007c07b  call    esi
0x1007c07d  mov     edi, eax
0x1007c07f  mov     [ebp+hr], edi
0x1007c082  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007c089  lea     eax, [ebp+var]
0x1007c08c  push    eax; pvarg
0x1007c08d  call    ds:__imp__VariantClear@4; VariantClear(x)
0x1007c093  mov     ppReturn, [ebp+pString._p]
0x1007c096  mov     [ebp+pString._p], 0
0x1007c09d  mov     eax, [ebp+var_3C]
0x1007c0a0  mov     [eax], ppReturn
0x1007c0a2  lea     ppReturn, [ebp+pString]; ppref
0x1007c0a5  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1007c0aa  mov     eax, edi
0x1007c0ac  mov     ppReturn, [ebp+ms_exc.registration.Next]
0x1007c0af  mov     large fs:0, ppReturn
0x1007c0b6  pop     ppReturn
0x1007c0b7  pop     edi
0x1007c0b8  pop     esi
0x1007c0b9  pop     ebx
0x1007c0ba  leave
0x1007c0bb  retn    4
0x1007c0be  mov     ppReturn, [ebp+ms_exc.exc_ptr]; ep
0x1007c0c1  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007c0c6  retn
0x1007c0c7  mov     esp, [ebp+ms_exc.old_esp]
0x1007c0ca  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007c0cf  cmp     [ebp+pString._p], 0
0x1007c0d3  jz      short loc_1007C0DF
0x1007c0d5  xor     pVar, pVar; pref
0x1007c0d7  lea     ppReturn, [ebp+pString]; ppref
0x1007c0da  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1007c0df  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
```
