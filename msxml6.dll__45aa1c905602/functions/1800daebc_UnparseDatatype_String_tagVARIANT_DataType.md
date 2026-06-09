# UnparseDatatype(String * *,tagVARIANT *,DataType)

- ea: `0x1800daebc`
- end: `0x1800db233`
- name: `?UnparseDatatype@@YAJPEAPEAVString@@PEAUtagVARIANT@@W4DataType@@@Z`
- size: `887`
- prototype: `HRESULT __fastcall(String **ppReturn, tagVARIANT *pVar, DataType dt)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800878e4`

## callees

- `0x180015a80`
- `0x180019cd0`
- `0x180019e20`
- `0x180054310`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d82c0`
- `0x1800da96c`
- `0x1800dab10`
- `0x1800dad54`
- `0x1800daebc`
- `0x1800db2d0`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800db1d0`
- `OLEAUT32!__imp_VariantClear` at `0x1800db1d0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800dafdb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800dafdb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800dafb5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800dafb5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800daffe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800daffe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800db05f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800db05f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800db0ce`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800db142`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800db0ce`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800db142`

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
          : UnparseBase64(*(void **)&uuid.Data1, lUBound - lLBound + 1, &pString._p, v9);
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
0x1800daebc  mov     r11, rsp
0x1800daebf  mov     [r11+10h], rbx
0x1800daec3  mov     [r11+18h], rsi
0x1800daec7  mov     [r11+8], ppReturn
0x1800daecb  push    rdi
0x1800daecc  push    r12
0x1800daece  push    r13
0x1800daed0  push    r14
0x1800daed2  push    r15
0x1800daed4  sub     rsp, 80h
0x1800daedb  mov     ebx, dt
0x1800daede  mov     r15, pVar
0x1800daee1  mov     r12, ppReturn
0x1800daee4  xor     esi, esi
0x1800daee6  mov     edi, esi
0x1800daee8  xorps   xmm0, xmm0
0x1800daeeb  xor     eax, eax
0x1800daeed  movups  xmmword ptr [rsp+0A8h+var.___u0], xmm0
0x1800daef2  mov     [r11-48h], rax
0x1800daef6  mov     r14d, esi
0x1800daef9  mov     [r11-60h], rsi
0x1800daefd  mov     [r11+20h], esi
0x1800daf01  lea     r13d, [rsi+1]
0x1800daf05  mov     [r11-58h], r13w
0x1800daf0a  mov     [r11-70h], rsi
0x1800daf0e  cmp     ebx, 11h
0x1800daf11  jg      loc_1800DB078
0x1800daf17  jz      short loc_1800DAF34
0x1800daf19  mov     ecx, ebx
0x1800daf1b  sub     ecx, 0Ch
0x1800daf1e  jz      short loc_1800DAF9C
0x1800daf20  sub     ecx, r13d
0x1800daf23  jz      short loc_1800DAF9C
0x1800daf25  sub     ecx, r13d
0x1800daf28  jz      short loc_1800DAF83
0x1800daf2a  sub     ecx, r13d
0x1800daf2d  jz      short loc_1800DAF68
0x1800daf2f  cmp     ecx, r13d
0x1800daf32  jnz     short loc_1800DAF52
0x1800daf34  lea     r8, [pVar+8]; pdate
0x1800daf38  mov     edx, ebx; dt
0x1800daf3a  lea     ppReturn, [rsp+0A8h+pString]; ppReturn
0x1800daf3f  call    ?UnparseISO8601@@YAJPEAPEAVString@@W4DataType@@PEAN@Z; UnparseISO8601(String * *,DataType,double *)
0x1800daf44  mov     edi, eax
0x1800daf46  mov     [rsp+0A8h+hr], eax
0x1800daf4a  test    eax, eax
0x1800daf4c  js      $CleanUp_184
0x1800daf52  mov     ebx, 8
0x1800daf57  test    r14, r14
0x1800daf5a  jz      loc_1800DB125
0x1800daf60  mov     ppReturn, r14
0x1800daf63  jmp     loc_1800DB15D
0x1800daf68  movzx   eax, word ptr [pVar+8]
0x1800daf6c  mov     [rsp+0A8h+wch], ax
0x1800daf74  lea     r14, [rsp+0A8h+wch]
0x1800daf7c  mov     [rsp+0A8h+pwsz], r14
0x1800daf81  jmp     short loc_1800DAF52
0x1800daf83  lea     r14, a1_0; "1"
0x1800daf8a  lea     rax, a0_0; "0"
0x1800daf91  cmp     word ptr [pVar+8], 0FFFFh
0x1800daf96  cmovnz  r14, rax
0x1800daf9a  jmp     short loc_1800DAF7C
0x1800daf9c  mov     [rsp+0A8h+lLBound], esi
0x1800dafa0  mov     [rsp+0A8h+lUBound], esi
0x1800dafa4  mov     qword ptr [rsp+0A8h+uuid.Data1], rsi
0x1800dafa9  lea     r8, [rsp+0A8h+lLBound]; plLbound
0x1800dafae  mov     edx, r13d; nDim
0x1800dafb1  mov     ppReturn, [r15+8]; psa
0x1800dafb5  call    cs:__imp_SafeArrayGetLBound
0x1800dafbc  nop     dword ptr [rax+rax+00h]
0x1800dafc1  mov     edi, eax
0x1800dafc3  mov     [rsp+0A8h+hr], eax
0x1800dafc7  test    eax, eax
0x1800dafc9  js      $CleanUp_184
0x1800dafcf  lea     r8, [rsp+0A8h+lUBound]; plUbound
0x1800dafd4  mov     edx, r13d; nDim
0x1800dafd7  mov     ppReturn, [r15+8]; psa
0x1800dafdb  call    cs:__imp_SafeArrayGetUBound
0x1800dafe2  nop     dword ptr [rax+rax+00h]
0x1800dafe7  mov     edi, eax
0x1800dafe9  mov     [rsp+0A8h+hr], eax
0x1800dafed  test    eax, eax
0x1800dafef  js      $CleanUp_184
0x1800daff5  lea     pVar, [rsp+0A8h+uuid]; ppvData
0x1800daffa  mov     ppReturn, [r15+8]; psa
0x1800daffe  call    cs:__imp_SafeArrayAccessData
0x1800db005  nop     dword ptr [rax+rax+00h]
0x1800db00a  mov     edi, eax
0x1800db00c  mov     [rsp+0A8h+hr], eax
0x1800db010  test    eax, eax
0x1800db012  js      $CleanUp_184
0x1800db018  cmp     ebx, 0Dh
0x1800db01b  jnz     short loc_1800DB03B
0x1800db01d  mov     dt, [rsp+0A8h+lUBound]
0x1800db022  sub     dt, [rsp+0A8h+lLBound]
0x1800db027  add     dt, r13d; lLen
0x1800db02a  mov     pVar, qword ptr [rsp+0A8h+uuid.Data1]; abData
0x1800db02f  lea     ppReturn, [rsp+0A8h+pString]; ppReturn
0x1800db034  call    ?UnparseBinHex@@YAJPEAPEAVString@@PEAEJ@Z; UnparseBinHex(String * *,uchar *,long)
0x1800db039  jmp     short loc_1800DB055
0x1800db03b  mov     edx, [rsp+0A8h+lUBound]
0x1800db03f  sub     edx, [rsp+0A8h+lLBound]
0x1800db043  add     edx, r13d; cbData
0x1800db046  lea     r8, [rsp+0A8h+pString]; ppReturn
0x1800db04b  mov     ppReturn, qword ptr [rsp+0A8h+uuid.Data1]; pvData
0x1800db050  call    ?UnparseBase64@@YAJPEAXHPEAPEAVString@@PEAV1@@Z; UnparseBase64(void *,int,String * *,String *)
0x1800db055  mov     [rsp+0A8h+hr], eax
0x1800db059  mov     edi, eax
0x1800db05b  mov     ppReturn, [r15+8]; psa
0x1800db05f  call    cs:__imp_SafeArrayUnaccessData
0x1800db066  nop     dword ptr [rax+rax+00h]
0x1800db06b  test    edi, edi
0x1800db06d  jns     loc_1800DAF52
0x1800db073  jmp     $CleanUp_184
0x1800db078  mov     ecx, ebx
0x1800db07a  sub     ecx, 12h
0x1800db07d  jz      loc_1800DAF34
0x1800db083  sub     ecx, 0Dh
0x1800db086  jz      loc_1800DAF34
0x1800db08c  sub     ecx, 1
0x1800db08f  jz      loc_1800DAF34
0x1800db095  sub     ecx, 6
0x1800db098  jz      short loc_1800DB0B1
0x1800db09a  cmp     ecx, 1
0x1800db09d  jnz     loc_1800DAF52
0x1800db0a3  mov     edi, 80004005h
0x1800db0a8  mov     [rsp+0A8h+hr], edi
0x1800db0ac  jmp     $CleanUp_184
0x1800db0b1  movups  xmmword ptr [rsp+0A8h+uuid.Data1], xmm0
0x1800db0b6  mov     ebx, 8
0x1800db0bb  mov     r9d, r13d; wFlags
0x1800db0be  mov     [rsp+0A8h+vt], bx; vt
0x1800db0c3  mov     dt, 409h; lcid
0x1800db0c9  lea     ppReturn, [rsp+0A8h+var]; pvargDest
0x1800db0ce  call    cs:__imp_VariantChangeTypeEx
0x1800db0d5  nop     dword ptr [rax+rax+00h]
0x1800db0da  mov     edi, eax
0x1800db0dc  mov     [rsp+0A8h+hr], eax
0x1800db0e0  test    eax, eax
0x1800db0e2  js      $CleanUp_184
0x1800db0e8  mov     edx, 7FFFFFFFh; cchMax
0x1800db0ed  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; psz
0x1800db0f2  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800db0f7  mov     edx, eax; cch
0x1800db0f9  lea     r8, [rsp+0A8h+uuid]; pUuid
0x1800db0fe  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; pS
0x1800db103  call    ?ParseUuid@@YAJPEBGHPEAU_GUID@@@Z; ParseUuid(ushort const *,int,_GUID *)
0x1800db108  mov     edi, eax
0x1800db10a  mov     [rsp+0A8h+hr], eax
0x1800db10e  test    eax, eax
0x1800db110  js      $CleanUp_184
0x1800db116  mov     r14, qword ptr [rsp+0A8h+var.___u0+8]
0x1800db11b  mov     [rsp+0A8h+pwsz], r14
0x1800db120  jmp     loc_1800DAF57
0x1800db125  cmp     [rsp+0A8h+pString._p], rsi
0x1800db12a  jnz     short loc_1800DB174
0x1800db12c  mov     r9d, r13d; wFlags
0x1800db12f  mov     [rsp+0A8h+vt], bx; vt
0x1800db134  mov     dt, 409h; lcid
0x1800db13a  mov     pVar, r15; pvarSrc
0x1800db13d  lea     ppReturn, [rsp+0A8h+var]; pvargDest
0x1800db142  call    cs:__imp_VariantChangeTypeEx
0x1800db149  nop     dword ptr [rax+rax+00h]
0x1800db14e  mov     edi, eax
0x1800db150  mov     [rsp+0A8h+hr], eax
0x1800db154  test    eax, eax
0x1800db156  js      short $CleanUp_184
0x1800db158  mov     ppReturn, qword ptr [rsp+0A8h+var.___u0+8]; c
0x1800db15d  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800db162  mov     rbx, rax
0x1800db165  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800db16a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800db16f  mov     [rsp+0A8h+pString._p], rbx
0x1800db174  jmp     short $CleanUp_184
0x1800db176  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800db17b  cmp     [rsp+0A8h+pString._p], 0
0x1800db181  jz      short loc_1800DB18F
0x1800db183  xor     edx, edx; pref
0x1800db185  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800db18a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800db18f  mov     ecx, cs:_tls_index
0x1800db195  mov     rax, gs:58h
0x1800db19e  mov     edx, 8
0x1800db1a3  mov     rax, [rax+ppReturn*8]
0x1800db1a7  mov     ppReturn, [rax+pVar]
0x1800db1ab  mov     ppReturn, [ppReturn+8]
0x1800db1af  mov     rax, [ppReturn]
0x1800db1b2  mov     rax, [rax+68h]
0x1800db1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db1bb  mov     edi, eax
0x1800db1bd  mov     [rsp+0A8h+hr], eax
0x1800db1c1  xor     esi, esi
0x1800db1c3  mov     r12, [rsp+0A8h+arg_0]
0x1800db1cb  lea     ppReturn, [rsp+0A8h+var]; pvarg
0x1800db1d0  call    cs:__imp_VariantClear
0x1800db1d7  nop     dword ptr [rax+rax+00h]
0x1800db1dc  mov     rax, [rsp+0A8h+pString._p]
0x1800db1e1  mov     [rsp+0A8h+pString._p], rsi
0x1800db1e6  mov     [r12], rax
0x1800db1ea  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800db1ef  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800db1f4  mov     eax, edi
0x1800db1f6  lea     r11, [rsp+0A8h+var_28]
0x1800db1fe  mov     rbx, [r11+38h]
0x1800db202  mov     rsi, [r11+40h]
0x1800db206  mov     rsp, r11
0x1800db209  pop     r15
0x1800db20b  pop     r14
0x1800db20d  pop     r13
0x1800db20f  pop     r12
0x1800db211  pop     rdi
0x1800db212  retn
0x1800db214  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800db219  cmp     [rsp+0A8h+pString._p], 0
0x1800db21f  jz      short loc_1800DB22D
0x1800db221  xor     edx, edx; pref
0x1800db223  lea     ppReturn, [rsp+0A8h+pString]; ppref
0x1800db228  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800db22d  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180182ae3  push    rbp
0x180182ae5  sub     rsp, 30h
0x180182ae9  mov     rbp, rdx
0x180182aec  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x180182af1  nop
0x180182af2  add     rsp, 30h
0x180182af6  pop     rbp
0x180182af7  retn
0x180182af9  push    rbp
0x180182afb  sub     rsp, 30h
0x180182aff  mov     rbp, rdx
0x180182b02  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x180182b07  nop
0x180182b08  add     rsp, 30h
0x180182b0c  pop     rbp
0x180182b0d  retn
```
