# EodParseReceiveInfo

- ea: `0x1800259b8`
- end: `0x180025e60`
- name: `EodParseReceiveInfo`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180022a80`

## callees

- `0x1800023bb`
- `0x18000a9a8`
- `0x18001d1ac`
- `0x180024308`
- `0x1800258d0`
- `0x1800259b8`
- `0x180025f18`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180025bfd`
- `OLEAUT32!__imp_SysAllocString` at `0x180025bfd`
- `OLEAUT32!__imp_VariantInit` at `0x1800259e3`
- `OLEAUT32!__imp_VariantInit` at `0x180025d92`
- `OLEAUT32!__imp_VariantInit` at `0x1800259e3`
- `OLEAUT32!__imp_VariantInit` at `0x180025d92`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025a01`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025b36`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025a01`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025b36`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025b72`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025b72`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025d89`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025d89`

## string_xrefs

- `0x180025cce`: `LastAccessTime`

## pseudocode

```c
void __fastcall EodParseReceiveInfo(__int64 a1, VARIANTARG *a2)
{
  SAFEARRAY *v4; // rax
  __int64 v5; // rax
  unsigned int v6; // edi
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // r14
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r12
  int v12; // eax
  __int64 v13; // rax
  int BstrFromGuid; // eax
  __int64 v15; // rcx
  SAFEARRAYBOUND v16; // [rsp+20h] [rbp-60h] BYREF
  __int64 v17; // [rsp+28h] [rbp-58h] BYREF
  const OLECHAR *v18; // [rsp+30h] [rbp-50h]
  struct tagVARIANT pExceptionObject; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v20[40]; // [rsp+58h] [rbp-28h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C0h] [rbp+40h] BYREF
  _QWORD *v22; // [rsp+D0h] [rbp+50h]
  void *ppvData; // [rsp+D8h] [rbp+58h] BYREF

  if ( *(_WORD *)a1 == 1 )
  {
    VariantInit(a2);
    a2->vt = 8204;
    rgsabound = 0;
    v4 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( !v4 )
    {
      bad_hresult::bad_hresult((bad_hresult *)&pExceptionObject, -2147024882);
      throw (bad_hresult *)&pExceptionObject;
    }
    a2->llVal = (LONGLONG)v4;
  }
  else
  {
    if ( *(_WORD *)a1 != 4108 )
    {
      bad_hresult::bad_hresult((bad_hresult *)&pExceptionObject, -2147467259);
      throw (bad_hresult *)&pExceptionObject;
    }
    v5 = *(_QWORD *)(a1 + 16);
    if ( !v5 || *(_DWORD *)(a1 + 8) != 6 )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    if ( *(_WORD *)v5 != 4127 )
    {
      bad_hresult::bad_hresult((bad_hresult *)&pExceptionObject, -2147467259);
      throw (bad_hresult *)&pExceptionObject;
    }
    if ( *(_WORD *)(v5 + 24) != 4168 || (v6 = *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 + 32) != v6) )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    if ( *(_WORD *)(v5 + 48) != 4117 || *(_DWORD *)(v5 + 56) != v6 )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    if ( *(_WORD *)(v5 + 72) != 4115 || *(_DWORD *)(v5 + 80) != v6 )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    if ( *(_WORD *)(v5 + 96) != 4099 || *(_DWORD *)(v5 + 104) != v6 )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    if ( *(_WORD *)(v5 + 120) != 4115 || *(_DWORD *)(v5 + 128) != v6 )
    {
      bad_hresult::bad_hresult((bad_hresult *)v20, -2147467259);
      throw (bad_hresult *)v20;
    }
    v16.cElements = *(_DWORD *)(v5 + 8);
    v16.lLbound = 0;
    v7 = SafeArrayCreate(0xCu, 1u, &v16);
    v8 = v7;
    if ( !v7 )
    {
      bad_hresult::bad_hresult((bad_hresult *)&pExceptionObject, -2147024882);
      throw (bad_hresult *)&pExceptionObject;
    }
    ppvData = 0;
    v9 = SafeArrayAccessData(v7, &ppvData);
    if ( v9 < 0 )
    {
      bad_hresult::bad_hresult((bad_hresult *)&pExceptionObject, v9);
      throw (bad_hresult *)&pExceptionObject;
    }
    v11 = 0;
    while ( (unsigned int)v11 < v6 )
    {
      v22 = *(_QWORD **)(a1 + 16);
      v17 = 0;
      rgsabound = 0;
      v12 = CNewMsmqObj<CMSMQCollection>::NewObj(&rgsabound, v10, &v17);
      if ( v12 < 0 )
      {
        bad_hresult::bad_hresult((bad_hresult *)v20, v12);
        throw (bad_hresult *)v20;
      }
      memset(&pExceptionObject, 0, sizeof(pExceptionObject));
      v13 = v22[2];
      pExceptionObject.vt = 8;
      v18 = *(const OLECHAR **)(v13 + 8 * v11);
      pExceptionObject.llVal = (LONGLONG)SysAllocString(v18);
      if ( !pExceptionObject.llVal && v18 )
      {
        bad_hresult::bad_hresult((bad_hresult *)v20, -2147024882);
        throw (bad_hresult *)v20;
      }
      CMSMQCollection::Add(*(CMSMQCollection **)&rgsabound, L"QueueFormatName", &pExceptionObject);
      memset(&pExceptionObject, 0, sizeof(pExceptionObject));
      pExceptionObject.vt = 8;
      BstrFromGuid = GetBstrFromGuid((GUID *)(v22[5] + 16LL * (unsigned int)v11), &pExceptionObject.bstrVal);
      if ( BstrFromGuid < 0 )
      {
        bad_hresult::bad_hresult((bad_hresult *)v20, BstrFromGuid);
        throw (bad_hresult *)v20;
      }
      CMSMQCollection::Add(*(CMSMQCollection **)&rgsabound, L"SenderID", &pExceptionObject);
      memset(&pExceptionObject, 0, sizeof(pExceptionObject));
      pExceptionObject.vt = 21;
      pExceptionObject.llVal = *(_QWORD *)(v22[8] + 8 * v11);
      CMSMQCollection::Add(*(CMSMQCollection **)&rgsabound, L"SeqID", &pExceptionObject);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AddLong)(*(unsigned int *)(v22[11] + 4 * v11), L"SeqNo", rgsabound);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AddLong)(
        *(unsigned int *)(v22[14] + 4 * v11),
        L"LastAccessTime",
        rgsabound);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AddLong)(
        *(unsigned int *)(v22[17] + 4 * v11),
        L"RejectCount",
        rgsabound);
      v15 = v17;
      v10 = (unsigned int)v11 + 2 * v11;
      v11 = (unsigned int)(v11 + 1);
      *((_WORD *)ppvData + 4 * v10) = 9;
      *((_QWORD *)ppvData + v10 + 1) = v15;
    }
    SafeArrayUnaccessData(v8);
    VariantInit(a2);
    a2->vt = 8204;
    a2->llVal = (LONGLONG)v8;
  }
}

```

## disassembly

```asm
0x1800259b8  push    rbp
0x1800259ba  push    rsi
0x1800259bb  push    rdi
0x1800259bc  push    r12
0x1800259be  push    r13
0x1800259c0  push    r14
0x1800259c2  push    r15
0x1800259c4  mov     rbp, rsp
0x1800259c7  sub     rsp, 80h
0x1800259ce  mov     r14d, 1
0x1800259d4  mov     rsi, rdx
0x1800259d7  mov     r15, rcx
0x1800259da  cmp     [rcx], r14w
0x1800259de  jnz     short loc_180025A42
0x1800259e0  mov     rcx, rdx; pvarg
0x1800259e3  call    cs:__imp_VariantInit
0x1800259e9  lea     ecx, [r14+0Bh]; vt
0x1800259ed  mov     word ptr [rsi], 200Ch
0x1800259f2  lea     r8, [rbp+rgsabound]; rgsabound
0x1800259f6  mov     qword ptr [rbp+rgsabound.cElements], 0
0x1800259fe  mov     edx, r14d; cDims
0x180025a01  call    cs:__imp_SafeArrayCreate
0x180025a07  test    rax, rax
0x180025a0a  jnz     short loc_180025A2B
0x180025a0c  mov     edx, 8007000Eh; int
0x180025a11  lea     rcx, [rbp+pExceptionObject]; this
0x180025a15  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025a1a  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025a21  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025a25  call    _CxxThrowException_0
0x180025a2b  mov     [rsi+8], rax
0x180025a2f  add     rsp, 80h
0x180025a36  pop     r15
0x180025a38  pop     r14
0x180025a3a  pop     r13
0x180025a3c  pop     r12
0x180025a3e  pop     rdi
0x180025a3f  pop     rsi
0x180025a40  pop     rbp
0x180025a41  retn
0x180025a42  mov     eax, 100Ch
0x180025a47  cmp     [rcx], ax
0x180025a4a  jz      short loc_180025A6B
0x180025a4c  mov     edx, 80004005h; int
0x180025a51  lea     rcx, [rbp+pExceptionObject]; this
0x180025a55  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025a5a  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025a61  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025a65  call    _CxxThrowException_0
0x180025a6b  mov     rax, [rcx+10h]
0x180025a6f  test    rax, rax
0x180025a72  jz      loc_180025E41
0x180025a78  cmp     dword ptr [rcx+8], 6
0x180025a7c  jnz     loc_180025E41
0x180025a82  mov     ecx, 101Fh
0x180025a87  cmp     [rax], cx
0x180025a8a  jz      short loc_180025AAB
0x180025a8c  mov     edx, 80004005h; int
0x180025a91  lea     rcx, [rbp+pExceptionObject]; this
0x180025a95  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025a9a  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025aa1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025aa5  call    _CxxThrowException_0
0x180025aab  mov     ecx, 1048h
0x180025ab0  cmp     [rax+18h], cx
0x180025ab4  jnz     loc_180025E22
0x180025aba  mov     edi, [rax+8]
0x180025abd  cmp     [rax+20h], edi
0x180025ac0  jnz     loc_180025E22
0x180025ac6  mov     ecx, 1015h
0x180025acb  cmp     [rax+30h], cx
0x180025acf  jnz     loc_180025E03
0x180025ad5  cmp     [rax+38h], edi
0x180025ad8  jnz     loc_180025E03
0x180025ade  lea     edx, [rcx-2]
0x180025ae1  cmp     [rax+48h], dx
0x180025ae5  jnz     loc_180025DE4
0x180025aeb  cmp     [rax+50h], edi
0x180025aee  jnz     loc_180025DE4
0x180025af4  lea     ecx, [rdx-10h]
0x180025af7  cmp     [rax+60h], cx
0x180025afb  jnz     loc_180025DC5
0x180025b01  cmp     [rax+68h], edi
0x180025b04  jnz     loc_180025DC5
0x180025b0a  cmp     [rax+78h], dx
0x180025b0e  jnz     loc_180025DA6
0x180025b14  cmp     [rax+80h], edi
0x180025b1a  jnz     loc_180025DA6
0x180025b20  mov     ecx, 0Ch; vt
0x180025b25  mov     [rbp+var_60.cElements], edi
0x180025b28  lea     r8, [rbp+var_60]; rgsabound
0x180025b2c  mov     [rbp+var_60.lLbound], 0
0x180025b33  mov     edx, r14d; cDims
0x180025b36  call    cs:__imp_SafeArrayCreate
0x180025b3c  mov     r14, rax
0x180025b3f  test    rax, rax
0x180025b42  jnz     short loc_180025B63
0x180025b44  mov     edx, 8007000Eh; int
0x180025b49  lea     rcx, [rbp+pExceptionObject]; this
0x180025b4d  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025b52  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025b59  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025b5d  call    _CxxThrowException_0
0x180025b63  lea     rdx, [rbp+ppvData]; ppvData
0x180025b67  mov     [rbp+ppvData], 0
0x180025b6f  mov     rcx, r14; psa
0x180025b72  call    cs:__imp_SafeArrayAccessData
0x180025b78  test    eax, eax
0x180025b7a  jns     short loc_180025B98
0x180025b7c  mov     edx, eax; int
0x180025b7e  lea     rcx, [rbp+pExceptionObject]; this
0x180025b82  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025b87  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025b8e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025b92  call    _CxxThrowException_0
0x180025b98  xor     r12d, r12d
0x180025b9b  cmp     r12d, edi
0x180025b9e  jnb     loc_180025D86
0x180025ba4  mov     rax, [r15+10h]
0x180025ba8  lea     r8, [rbp+var_58]
0x180025bac  lea     rcx, [rbp+rgsabound]
0x180025bb0  mov     [rbp+arg_10], rax
0x180025bb4  mov     [rbp+var_58], 0
0x180025bbc  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180025bc4  call    ?NewObj@?$CNewMsmqObj@VCMSMQCollection@@@@SAJPEAPEAV?$CComObject@VCMSMQCollection@@@ATL@@PEBU_GUID@@PEAPEAUIUnknown@@@Z; CNewMsmqObj<CMSMQCollection>::NewObj(ATL::CComObject<CMSMQCollection> * *,_GUID const *,IUnknown * *)
0x180025bc9  test    eax, eax
0x180025bcb  js      loc_180025D6A
0x180025bd1  mov     rax, [rbp+arg_10]
0x180025bd5  xor     ecx, ecx
0x180025bd7  mov     [rbp+var_38], rcx
0x180025bdb  xorps   xmm0, xmm0
0x180025bde  mov     ecx, 8
0x180025be3  mov     r13d, r12d
0x180025be6  movups  [rbp+pExceptionObject], xmm0
0x180025bea  mov     rax, [rax+10h]
0x180025bee  mov     word ptr [rbp+pExceptionObject], cx
0x180025bf2  mov     rax, [rax+r12*8]
0x180025bf6  mov     rcx, rax; psz
0x180025bf9  mov     [rbp+var_50], rax
0x180025bfd  call    cs:__imp_SysAllocString
0x180025c03  mov     qword ptr [rbp+pExceptionObject+8], rax
0x180025c07  test    rax, rax
0x180025c0a  jnz     short loc_180025C16
0x180025c0c  cmp     [rbp+var_50], rax
0x180025c10  jnz     loc_180025D2F
0x180025c16  mov     rcx, qword ptr [rbp+rgsabound.cElements]; this
0x180025c1a  lea     r8, [rbp+pExceptionObject]; struct tagVARIANT *
0x180025c1e  lea     rdx, aQueueformatnam; "QueueFormatName"
0x180025c25  call    ?Add@CMSMQCollection@@QEAAXPEB_WAEBUtagVARIANT@@@Z; CMSMQCollection::Add(wchar_t const *,tagVARIANT const &)
0x180025c2a  xor     eax, eax
0x180025c2c  lea     rdx, [rbp+pExceptionObject+8]; wchar_t **
0x180025c30  mov     [rbp+var_38], rax
0x180025c34  xorps   xmm0, xmm0
0x180025c37  mov     eax, 8
0x180025c3c  mov     rcx, r13
0x180025c3f  movups  [rbp+pExceptionObject], xmm0
0x180025c43  mov     word ptr [rbp+pExceptionObject], ax
0x180025c47  mov     rax, [rbp+arg_10]
0x180025c4b  shl     rcx, 4
0x180025c4f  add     rcx, [rax+28h]; rguid
0x180025c53  call    ?GetBstrFromGuid@@YAJPEAU_GUID@@PEAPEA_W@Z; GetBstrFromGuid(_GUID *,wchar_t * *)
0x180025c58  test    eax, eax
0x180025c5a  js      loc_180025D4E
0x180025c60  mov     rcx, qword ptr [rbp+rgsabound.cElements]; this
0x180025c64  lea     r8, [rbp+pExceptionObject]; struct tagVARIANT *
0x180025c68  lea     rdx, aSenderid; "SenderID"
0x180025c6f  call    ?Add@CMSMQCollection@@QEAAXPEB_WAEBUtagVARIANT@@@Z; CMSMQCollection::Add(wchar_t const *,tagVARIANT const &)
0x180025c74  xor     eax, eax
0x180025c76  lea     r8, [rbp+pExceptionObject]; struct tagVARIANT *
0x180025c7a  mov     [rbp+var_38], rax
0x180025c7e  lea     rdx, aSeqid; "SeqID"
0x180025c85  xorps   xmm0, xmm0
0x180025c88  mov     eax, 15h
0x180025c8d  movups  [rbp+pExceptionObject], xmm0
0x180025c91  mov     word ptr [rbp+pExceptionObject], ax
0x180025c95  mov     rax, [rbp+arg_10]
0x180025c99  mov     rax, [rax+40h]
0x180025c9d  mov     rcx, [rax+r12*8]
0x180025ca1  mov     qword ptr [rbp+pExceptionObject+8], rcx
0x180025ca5  mov     rcx, qword ptr [rbp+rgsabound.cElements]; this
0x180025ca9  call    ?Add@CMSMQCollection@@QEAAXPEB_WAEBUtagVARIANT@@@Z; CMSMQCollection::Add(wchar_t const *,tagVARIANT const &)
0x180025cae  mov     rax, [rbp+arg_10]
0x180025cb2  lea     rdx, aSeqno; "SeqNo"
0x180025cb9  mov     r8, qword ptr [rbp+rgsabound.cElements]
0x180025cbd  mov     rcx, [rax+58h]
0x180025cc1  mov     ecx, [rcx+r12*4]
0x180025cc5  call    AddLong
0x180025cca  mov     rax, [rbp+arg_10]
0x180025cce  lea     rdx, aLastaccesstime; "LastAccessTime"
0x180025cd5  mov     r8, qword ptr [rbp+rgsabound.cElements]
0x180025cd9  mov     rcx, [rax+70h]
0x180025cdd  mov     ecx, [rcx+r12*4]
0x180025ce1  call    AddLong
0x180025ce6  mov     rax, [rbp+arg_10]
0x180025cea  lea     rdx, aRejectcount; "RejectCount"
0x180025cf1  mov     r8, qword ptr [rbp+rgsabound.cElements]
0x180025cf5  mov     rcx, [rax+88h]
0x180025cfc  mov     ecx, [rcx+r12*4]
0x180025d00  call    AddLong
0x180025d05  mov     rax, [rbp+ppvData]
0x180025d09  lea     rdx, ds:0[r12*2]
0x180025d11  mov     rcx, [rbp+var_58]
0x180025d15  add     rdx, r13
0x180025d18  inc     r12d
0x180025d1b  mov     word ptr [rax+rdx*8], 9
0x180025d21  mov     rax, [rbp+ppvData]
0x180025d25  mov     [rax+rdx*8+8], rcx
0x180025d2a  jmp     loc_180025B9B
0x180025d2f  mov     edx, 8007000Eh; int
0x180025d34  lea     rcx, [rbp+var_28]; this
0x180025d38  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025d3d  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025d44  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025d48  call    _CxxThrowException_0
0x180025d4e  mov     edx, eax; int
0x180025d50  lea     rcx, [rbp+var_28]; this
0x180025d54  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025d59  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025d60  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025d64  call    _CxxThrowException_0
0x180025d6a  mov     edx, eax; int
0x180025d6c  lea     rcx, [rbp+var_28]; this
0x180025d70  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025d75  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025d7c  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025d80  call    _CxxThrowException_0
0x180025d86  mov     rcx, r14; psa
0x180025d89  call    cs:__imp_SafeArrayUnaccessData
0x180025d8f  mov     rcx, rsi; pvarg
0x180025d92  call    cs:__imp_VariantInit
0x180025d98  mov     word ptr [rsi], 200Ch
0x180025d9d  mov     [rsi+8], r14
0x180025da1  jmp     loc_180025A2F
0x180025da6  mov     edx, 80004005h; int
0x180025dab  lea     rcx, [rbp+var_28]; this
0x180025daf  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025db4  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025dbb  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025dbf  call    _CxxThrowException_0
0x180025dc5  mov     edx, 80004005h; int
0x180025dca  lea     rcx, [rbp+var_28]; this
0x180025dce  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025dd3  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025dda  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025dde  call    _CxxThrowException_0
0x180025de4  mov     edx, 80004005h; int
0x180025de9  lea     rcx, [rbp+var_28]; this
0x180025ded  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025df2  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025df9  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025dfd  call    _CxxThrowException_0
0x180025e03  mov     edx, 80004005h; int
0x180025e08  lea     rcx, [rbp+var_28]; this
0x180025e0c  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025e11  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025e18  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025e1c  call    _CxxThrowException_0
0x180025e22  mov     edx, 80004005h; int
0x180025e27  lea     rcx, [rbp+var_28]; this
0x180025e2b  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025e30  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025e37  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025e3b  call    _CxxThrowException_0
0x180025e41  mov     edx, 80004005h; int
0x180025e46  lea     rcx, [rbp+var_28]; this
0x180025e4a  call    ??0bad_hresult@@QEAA@J@Z; bad_hresult::bad_hresult(long)
0x180025e4f  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180025e56  lea     rcx, [rbp+var_28]; pExceptionObject
0x180025e5a  call    _CxxThrowException_0
```
