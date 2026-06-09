# GetManagedModuleInfo(ushort *,ulong * *,ulong *,_GUID * *,ushort * * *,ulong * *,long * *,__MIDL___MIDL_itf_registrar_0000_0000_0001)

- ea: `0x180029744`
- end: `0x180029b0c`
- name: `?GetManagedModuleInfo@@YAJPEAGPEAPEAKPEAKPEAPEAU_GUID@@PEAPEAPEAG1PEAPEAJW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029c14`

## callees

- `0x18000a01c`
- `0x18000a654`
- `0x180013910`
- `0x180029744`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!wcstol` at `0x180029863`
- `msvcrt!wcstol` at `0x180029863`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ad6`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ad6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180029a41`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180029a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002989f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002991c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002989f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002991c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a66`

## pseudocode

```c
__int64 __fastcall GetManagedModuleInfo(
        unsigned __int16 *a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        char *a7,
        int a8)
{
  int v10; // eax
  unsigned int v11; // r11d
  int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rsi
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  unsigned int v17; // edi
  unsigned int v18; // ecx
  unsigned int v19; // r8d
  _DWORD *v20; // rdi
  unsigned __int64 i; // rcx
  __int64 v22; // rdx
  char *v23; // rax
  unsigned int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // r14d
  __int64 v27; // rcx
  void *v28; // rax
  _QWORD *v29; // r12
  void *v30; // rax
  _QWORD *v31; // r13
  wchar_t **v32; // r8
  wchar_t *v33; // rax
  wchar_t **v34; // r8
  unsigned int j; // r15d
  const unsigned __int16 *v36; // r14
  HRESULT v37; // eax
  __int64 v38; // rax
  unsigned __int64 v39; // rbx
  LPVOID v40; // rax
  unsigned __int16 *v41; // rcx
  wchar_t **v42; // r8
  unsigned int v43; // edi
  wchar_t *EndPtr; // [rsp+50h] [rbp-71h] BYREF
  wchar_t *String[2]; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v47; // [rsp+68h] [rbp-59h] BYREF
  _QWORD *v48; // [rsp+70h] [rbp-51h]
  struct _GUID v49; // [rsp+80h] [rbp-41h] BYREF
  struct _GUID v50; // [rsp+90h] [rbp-31h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp-21h] BYREF

  EndPtr = 0;
  v48 = a4;
  *(_QWORD *)&pclsid.Data1 = a5;
  *(_OWORD *)String = 0;
  if ( !a1 || !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
    return 2147942487LL;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *(_QWORD *)a7 = 0;
  v47 = a1;
  v49 = IID_IComManagedImportUtil;
  v50 = CLSID_ComManagedImportUtil;
  v10 = ExecuteManagedRequestBitnessAware(a1, a8 != 1, &v50, &v49, 4u, 1u, &v47, 2u, String);
  v11 = 0;
  v12 = v10;
  if ( v10 >= 0 )
  {
    v13 = wcstol(String[0], &EndPtr, 10);
    v14 = v13;
    *a3 = v13;
    v15 = CoTaskMemAlloc(4u);
    v11 = 0;
    *a2 = v15;
    if ( !v15 )
      goto LABEL_43;
    *v15 = (_DWORD)v14 != 0 ? 0x2A : 0;
    v16 = CoTaskMemAlloc(4 * v14);
    v11 = 0;
    *a6 = v16;
    if ( !v16 )
      goto LABEL_43;
    if ( (_DWORD)v14 )
    {
      v17 = 0;
      if ( (unsigned int)v14 < 4 || v16 <= (_DWORD *)a6 && &v16[(unsigned int)(v14 - 1)] >= (_DWORD *)a6 )
        goto LABEL_50;
      v18 = v14 - (v14 & 3);
      do
      {
        v17 += 4;
        v19 = v17;
      }
      while ( v17 < v18 );
      v20 = v16;
      for ( i = (16 * ((unsigned __int64)(v18 + 3) >> 2)) >> 2; i; --i )
        *v20++ = 9;
      v17 = v19;
      if ( v19 < (unsigned int)v14 )
      {
LABEL_50:
        do
        {
          v22 = v17++;
          *(_DWORD *)(*a6 + 4 * v22) = 9;
        }
        while ( v17 < (unsigned int)v14 );
      }
    }
    v23 = (char *)CoTaskMemAlloc(4 * v14);
    v11 = 0;
    *(_QWORD *)a7 = v23;
    if ( !v23 )
      goto LABEL_43;
    if ( (_DWORD)v14 )
    {
      v24 = 0;
      if ( (unsigned int)v14 < 4 || v23 <= a7 && &v23[4 * (unsigned int)(v14 - 1)] >= a7 )
        goto LABEL_51;
      v25 = v14 - (v14 & 3);
      do
      {
        v24 += 4;
        v26 = v24;
      }
      while ( v24 < v25 );
      memset_0(v23, 0, 16 * ((unsigned __int64)(v25 + 3) >> 2));
      v24 = v26;
      if ( v26 < (unsigned int)v14 )
      {
LABEL_51:
        do
        {
          v27 = v24++;
          *(_DWORD *)(*(_QWORD *)a7 + 4 * v27) = 0;
        }
        while ( v24 < (unsigned int)v14 );
      }
    }
    v28 = CoTaskMemAlloc(16 * v14);
    v29 = v48;
    v11 = 0;
    *v48 = v28;
    if ( !v28 )
      goto LABEL_43;
    memset_0(v28, 0, 16 * v14);
    v30 = CoTaskMemAlloc(8 * v14);
    v31 = *(_QWORD **)&pclsid.Data1;
    v11 = 0;
    **(_QWORD **)&pclsid.Data1 = v30;
    if ( v30 )
    {
      memset_0(v30, 0, 8 * v14);
      v33 = wcstok_mvcrt_legacy_two_parameter_form(String[1], L",", v32);
      v11 = 0;
      for ( j = 0; ; ++j )
      {
        EndPtr = v33;
        v36 = v33;
        if ( j >= (unsigned int)v14 )
          break;
        pclsid = 0;
        EndPtr = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v34);
        v37 = CLSIDFromString(EndPtr, &pclsid);
        v11 = 0;
        v12 = v37;
        if ( v37 < 0 )
          break;
        v38 = -1;
        do
          ++v38;
        while ( v36[v38] );
        v39 = v38 + 1;
        v40 = CoTaskMemAlloc(2 * (v38 + 1));
        v11 = 0;
        *(_QWORD *)(*v31 + 8LL * j) = v40;
        v41 = *(unsigned __int16 **)(*v31 + 8LL * j);
        if ( !v41 )
          goto LABEL_43;
        v12 = StringCchCopyW(v41, v39, v36);
        if ( v12 < 0 )
          break;
        if ( *v29 )
          *(GUID *)(*v29 + 16LL * j) = pclsid;
        v33 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v42);
        v11 = 0;
      }
    }
    else
    {
LABEL_43:
      v12 = -2147024882;
    }
  }
  v43 = v11;
  do
    SysFreeString(String[v43++]);
  while ( v43 < 2 );
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180029744  push    rbp
0x180029746  push    rbx
0x180029747  push    rsi
0x180029748  push    rdi
0x180029749  push    r12
0x18002974b  push    r13
0x18002974d  push    r14
0x18002974f  push    r15
0x180029751  lea     rbp, [rsp-7]
0x180029756  sub     rsp, 0C8h
0x18002975d  mov     rax, cs:__security_cookie
0x180029764  xor     rax, rsp
0x180029767  mov     [rbp+3Fh+var_50], rax
0x18002976b  mov     r14, [rbp+3Fh+arg_28]
0x18002976f  mov     r12, r8
0x180029772  mov     r15, [rbp+3Fh+arg_30]
0x180029776  xor     r8d, r8d
0x180029779  mov     [rbp+3Fh+EndPtr], r8
0x18002977d  mov     rdi, rdx
0x180029780  mov     rdx, [rbp+3Fh+arg_20]
0x180029784  mov     rax, r9
0x180029787  mov     [rbp+3Fh+var_90], rax
0x18002978b  xorps   xmm0, xmm0
0x18002978e  mov     qword ptr [rbp+3Fh+pclsid.Data1], rdx
0x180029792  movdqu  xmmword ptr [rbp+3Fh+String], xmm0
0x180029797  test    rcx, rcx
0x18002979a  jz      loc_180029AE7
0x1800297a0  test    rdi, rdi
0x1800297a3  jz      loc_180029AE7
0x1800297a9  test    r12, r12
0x1800297ac  jz      loc_180029AE7
0x1800297b2  test    rax, rax
0x1800297b5  jz      loc_180029AE7
0x1800297bb  test    rdx, rdx
0x1800297be  jz      loc_180029AE7
0x1800297c4  test    r14, r14
0x1800297c7  jz      loc_180029AE7
0x1800297cd  test    r15, r15
0x1800297d0  jz      loc_180029AE7
0x1800297d6  movups  xmm1, xmmword ptr cs:CLSID_ComManagedImportUtil.Data1
0x1800297dd  cmp     [rbp+3Fh+arg_38], 1
0x1800297e4  lea     r13d, [r8+4]
0x1800297e8  movups  xmm0, xmmword ptr cs:IID_IComManagedImportUtil.Data1
0x1800297ef  mov     [rdi], r8
0x1800297f2  lea     rax, [rbp+3Fh+String]
0x1800297f6  mov     [r12], r8d
0x1800297fa  mov     [r9], r8
0x1800297fd  lea     r9, [rbp+3Fh+var_80]; struct _GUID
0x180029801  mov     [rsp+100h+var_C0], rax; unsigned __int16 **
0x180029806  lea     rax, [rbp+3Fh+var_98]
0x18002980a  mov     [rdx], r8
0x18002980d  mov     edx, r8d
0x180029810  mov     [r14], r8
0x180029813  setnz   dl; int
0x180029816  mov     [rsp+100h+var_C8], 2; unsigned int
0x18002981e  mov     [rsp+100h+var_D0], rax; unsigned __int16 **
0x180029823  mov     [r15], r8
0x180029826  lea     r8, [rbp+3Fh+var_70]; struct _GUID
0x18002982a  mov     [rsp+100h+var_D8], 1; unsigned int
0x180029832  mov     [rsp+100h+var_E0], r13d; unsigned int
0x180029837  mov     [rbp+3Fh+var_98], rcx
0x18002983b  movdqu  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x180029840  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm1
0x180029845  call    ?ExecuteManagedRequestBitnessAware@@YAJPEBGHU_GUID@@1KKPEAPEAGK2@Z; ExecuteManagedRequestBitnessAware(ushort const *,int,_GUID,_GUID,ulong,ulong,ushort * *,ulong,ushort * *)
0x18002984a  xor     r11d, r11d
0x18002984d  mov     ebx, eax
0x18002984f  test    eax, eax
0x180029851  js      loc_180029ACB
0x180029857  mov     rcx, [rbp+3Fh+String]; String
0x18002985b  lea     r8d, [r13+6]; Radix
0x18002985f  lea     rdx, [rbp+3Fh+EndPtr]; EndPtr
0x180029863  call    cs:__imp_wcstol
0x180029869  mov     esi, eax
0x18002986b  mov     ecx, r13d; cb
0x18002986e  mov     [r12], esi
0x180029872  call    cs:__imp_CoTaskMemAlloc
0x180029878  xor     r11d, r11d
0x18002987b  mov     [rdi], rax
0x18002987e  mov     rcx, rax
0x180029881  test    rax, rax
0x180029884  jz      loc_180029AC6
0x18002988a  cmp     r11d, esi
0x18002988d  lea     r12, ds:0[rsi*4]
0x180029895  sbb     eax, eax
0x180029897  and     eax, 2Ah
0x18002989a  mov     [rcx], eax
0x18002989c  mov     rcx, r12; cb
0x18002989f  call    cs:__imp_CoTaskMemAlloc
0x1800298a5  xor     r11d, r11d
0x1800298a8  mov     [r14], rax
0x1800298ab  mov     rdx, rax
0x1800298ae  test    rax, rax
0x1800298b1  jz      loc_180029AC6
0x1800298b7  test    esi, esi
0x1800298b9  jz      short loc_180029919
0x1800298bb  lea     r9d, [r13+5]
0x1800298bf  mov     edi, r11d
0x1800298c2  cmp     esi, r13d
0x1800298c5  jb      short loc_18002990A
0x1800298c7  cmp     rax, r14
0x1800298ca  ja      short loc_1800298D8
0x1800298cc  lea     eax, [rsi-1]
0x1800298cf  lea     rax, [rdx+rax*4]
0x1800298d3  cmp     rax, r14
0x1800298d6  jnb     short loc_18002990A
0x1800298d8  mov     eax, esi
0x1800298da  mov     ecx, esi
0x1800298dc  and     eax, 3
0x1800298df  sub     ecx, eax
0x1800298e1  add     edi, r13d
0x1800298e4  mov     r8d, edi
0x1800298e7  cmp     edi, ecx
0x1800298e9  jb      short loc_1800298E1
0x1800298eb  add     ecx, 3
0x1800298ee  mov     rdi, rdx
0x1800298f1  shr     rcx, 2
0x1800298f5  mov     rax, r9
0x1800298f8  shl     rcx, 4
0x1800298fc  shr     rcx, 2
0x180029900  rep stosd
0x180029902  mov     edi, r8d
0x180029905  cmp     r8d, esi
0x180029908  jnb     short loc_180029919
0x18002990a  mov     rax, [r14]
0x18002990d  mov     edx, edi
0x18002990f  inc     edi
0x180029911  mov     [rax+rdx*4], r9d
0x180029915  cmp     edi, esi
0x180029917  jb      short loc_18002990A
0x180029919  mov     rcx, r12; cb
0x18002991c  call    cs:__imp_CoTaskMemAlloc
0x180029922  xor     r11d, r11d
0x180029925  mov     [r15], rax
0x180029928  mov     rdi, rax
0x18002992b  test    rax, rax
0x18002992e  jz      loc_180029AC6
0x180029934  test    esi, esi
0x180029936  jz      short loc_180029998
0x180029938  mov     edx, r11d
0x18002993b  cmp     esi, r13d
0x18002993e  jb      short loc_180029989
0x180029940  cmp     rax, r15
0x180029943  ja      short loc_180029951
0x180029945  lea     eax, [rsi-1]
0x180029948  lea     rax, [rdi+rax*4]
0x18002994c  cmp     rax, r15
0x18002994f  jnb     short loc_180029989
0x180029951  mov     eax, esi
0x180029953  mov     ecx, esi
0x180029955  and     eax, 3
0x180029958  sub     ecx, eax
0x18002995a  add     edx, r13d
0x18002995d  mov     r14d, edx
0x180029960  cmp     edx, ecx
0x180029962  jb      short loc_18002995A
0x180029964  lea     r8d, [rcx+3]
0x180029968  xor     edx, edx; Val
0x18002996a  shr     r8, 2
0x18002996e  mov     rcx, rdi; void *
0x180029971  shl     r8, 4
0x180029975  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x180029979  call    memset_0
0x18002997e  mov     edx, r14d
0x180029981  cmp     r14d, esi
0x180029984  jnb     short loc_180029998
0x180029986  xor     r11d, r11d
0x180029989  mov     rax, [r15]
0x18002998c  mov     ecx, edx
0x18002998e  inc     edx
0x180029990  mov     [rax+rcx*4], r11d
0x180029994  cmp     edx, esi
0x180029996  jb      short loc_180029989
0x180029998  mov     rdi, rsi
0x18002999b  shl     rdi, 4
0x18002999f  mov     rcx, rdi; cb
0x1800299a2  call    cs:__imp_CoTaskMemAlloc
0x1800299a8  mov     r12, [rbp+3Fh+var_90]
0x1800299ac  xor     r11d, r11d
0x1800299af  mov     [r12], rax
0x1800299b3  test    rax, rax
0x1800299b6  jz      loc_180029AC6
0x1800299bc  mov     r8, rdi; Size
0x1800299bf  xor     edx, edx; Val
0x1800299c1  mov     rcx, rax; void *
0x1800299c4  call    memset_0
0x1800299c9  lea     rdi, ds:0[rsi*8]
0x1800299d1  mov     rcx, rdi; cb
0x1800299d4  call    cs:__imp_CoTaskMemAlloc
0x1800299da  mov     r13, qword ptr [rbp+3Fh+pclsid.Data1]
0x1800299de  xor     r11d, r11d
0x1800299e1  mov     [r13+0], rax
0x1800299e5  test    rax, rax
0x1800299e8  jz      loc_180029AC6
0x1800299ee  mov     r8, rdi; Size
0x1800299f1  xor     edx, edx; Val
0x1800299f3  mov     rcx, rax; void *
0x1800299f6  call    memset_0
0x1800299fb  mov     rcx, [rbp+3Fh+String+8]; String
0x1800299ff  lea     rdx, Delimiter; ","
0x180029a06  call    wcstok_mvcrt_legacy_two_parameter_form
0x180029a0b  xor     r11d, r11d
0x180029a0e  mov     r15d, r11d
0x180029a11  mov     [rbp+3Fh+EndPtr], rax
0x180029a15  mov     r14, rax
0x180029a18  cmp     r15d, esi
0x180029a1b  jnb     loc_180029ACB
0x180029a21  xorps   xmm0, xmm0
0x180029a24  lea     rdx, Delimiter; ","
0x180029a2b  xor     ecx, ecx; String
0x180029a2d  movups  xmmword ptr [rbp+3Fh+pclsid.Data1], xmm0
0x180029a31  call    wcstok_mvcrt_legacy_two_parameter_form
0x180029a36  lea     rdx, [rbp+3Fh+pclsid]; pclsid
0x180029a3a  mov     [rbp+3Fh+EndPtr], rax
0x180029a3e  mov     rcx, rax; lpsz
0x180029a41  call    cs:__imp_CLSIDFromString
0x180029a47  xor     r11d, r11d
0x180029a4a  mov     ebx, eax
0x180029a4c  test    eax, eax
0x180029a4e  js      short loc_180029ACB
0x180029a50  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029a54  inc     rax
0x180029a57  cmp     [r14+rax*2], r11w
0x180029a5c  jnz     short loc_180029A54
0x180029a5e  lea     rbx, [rax+1]
0x180029a62  lea     rcx, [rbx+rbx]; cb
0x180029a66  call    cs:__imp_CoTaskMemAlloc
0x180029a6c  mov     rcx, [r13+0]
0x180029a70  xor     r11d, r11d
0x180029a73  mov     edi, r15d
0x180029a76  mov     [rcx+rdi*8], rax
0x180029a7a  mov     rax, [r13+0]
0x180029a7e  mov     rcx, [rax+rdi*8]; unsigned __int16 *
0x180029a82  test    rcx, rcx
0x180029a85  jz      short loc_180029AC6
0x180029a87  mov     r8, r14; unsigned __int16 *
0x180029a8a  mov     rdx, rbx; unsigned __int64
0x180029a8d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029a92  mov     ebx, eax
0x180029a94  test    eax, eax
0x180029a96  js      short loc_180029ACB
0x180029a98  mov     rax, [r12]
0x180029a9c  test    rax, rax
0x180029a9f  jz      short loc_180029AAD
0x180029aa1  movups  xmm0, xmmword ptr [rbp+3Fh+pclsid.Data1]
0x180029aa5  add     rdi, rdi
0x180029aa8  movdqu  xmmword ptr [rax+rdi*8], xmm0
0x180029aad  lea     rdx, Delimiter; ","
0x180029ab4  xor     ecx, ecx; String
0x180029ab6  call    wcstok_mvcrt_legacy_two_parameter_form
0x180029abb  inc     r15d
0x180029abe  xor     r11d, r11d
0x180029ac1  jmp     loc_180029A11
0x180029ac6  mov     ebx, 8007000Eh
0x180029acb  mov     edi, r11d
0x180029ace  movsxd  rcx, edi
0x180029ad1  mov     rcx, [rbp+rcx*8+3Fh+String]; bstrString
0x180029ad6  call    cs:__imp_SysFreeString
0x180029adc  inc     edi
0x180029ade  cmp     edi, 2
0x180029ae1  jb      short loc_180029ACE
0x180029ae3  mov     eax, ebx
0x180029ae5  jmp     short loc_180029AEC
0x180029ae7  mov     eax, 80070057h
0x180029aec  mov     rcx, [rbp+3Fh+var_50]
0x180029af0  xor     rcx, rsp; StackCookie
0x180029af3  call    __security_check_cookie
0x180029af8  add     rsp, 0C8h
0x180029aff  pop     r15
0x180029b01  pop     r14
0x180029b03  pop     r13
0x180029b05  pop     r12
0x180029b07  pop     rdi
0x180029b08  pop     rsi
0x180029b09  pop     rbx
0x180029b0a  pop     rbp
0x180029b0b  retn
```
