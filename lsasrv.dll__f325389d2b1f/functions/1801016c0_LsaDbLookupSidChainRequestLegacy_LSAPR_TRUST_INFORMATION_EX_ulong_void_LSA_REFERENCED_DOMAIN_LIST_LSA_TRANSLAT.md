# LsaDbLookupSidChainRequestLegacy(_LSAPR_TRUST_INFORMATION_EX *,ulong,void * *,_LSA_REFERENCED_DOMAIN_LIST * *,_LSA_TRANSLATED_NAME_EX * *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *)

- ea: `0x1801016c0`
- end: `0x180101c37`
- name: `?LsaDbLookupSidChainRequestLegacy@@YAJPEAU_LSAPR_TRUST_INFORMATION_EX@@KPEAPEAXPEAPEAU_LSA_REFERENCED_DOMAIN_LIST@@PEAPEAU_LSA_TRANSLATED_NAME_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK5@Z`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800afa00`

## callees

- `0x180013b20`
- `0x1800293c0`
- `0x180071d00`
- `0x18008e360`
- `0x180097c3c`
- `0x1800b1b90`
- `0x1800c7e28`
- `0x1800ec654`
- `0x18010141c`
- `0x1801016c0`
- `0x180101d1c`
- `0x1801032e8`
- `0x1801038f8`
- `0x18011d51c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801018f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801018f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101bc6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180101760`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180101b0d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180101760`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180101b0d`
- `ntdll!RtlInitUnicodeString` at `0x180101b4c`
- `ntdll!RtlInitUnicodeString` at `0x180101b4c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupSids` at `0x180101a31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupSids` at `0x180101a31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupSidsWithCreds` at `0x180101875`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaICLookupSidsWithCreds` at `0x180101875`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180101c07`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180101c07`

## pseudocode

```c
__int64 LsaDbLookupSidChainRequestLegacy(
        _WORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        ...)
{
  const WCHAR *v7; // rbx
  __int64 *v9; // r15
  int v10; // esi
  struct _LSAP_BINDING_CACHE_ENTRY *v11; // rbx
  const wchar_t *v12; // rcx
  int v13; // eax
  LsaHandleCache *v14; // r11
  const wchar_t *v15; // r9
  char v16; // si
  HLOCAL v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // r15d
  LSA_HANDLE v21; // rsi
  int v22; // eax
  int v23; // r8d
  LsaHandleCache *v24; // r10
  HLOCAL hMem; // [rsp+68h] [rbp-69h] BYREF
  unsigned int v27; // [rsp+70h] [rbp-61h] BYREF
  unsigned int v28; // [rsp+74h] [rbp-5Dh] BYREF
  unsigned int v29; // [rsp+78h] [rbp-59h] BYREF
  __int64 v30; // [rsp+80h] [rbp-51h] BYREF
  __int64 v31; // [rsp+88h] [rbp-49h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+90h] [rbp-41h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-39h] BYREF
  int ChainingFlags; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-29h] BYREF
  struct _LSAP_BINDING_CACHE_ENTRY *v36; // [rsp+B0h] [rbp-21h] BYREF
  LARGE_INTEGER v37; // [rsp+B8h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v42; // [rsp+150h] [rbp+7Fh] BYREF
  va_list va; // [rsp+150h] [rbp+7Fh]
  va_list va1; // [rsp+158h] [rbp+87h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v42 = va_arg(va1, _QWORD);
  v7 = 0;
  LODWORD(v42) = 0;
  v9 = 0;
  hMem = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v27 = 0;
  ObjectHandle = 0;
  v36 = 0;
  v35 = 0;
  PerformanceCount.QuadPart = 0;
  v37.QuadPart = 0;
  v10 = (int)a1;
  if ( !*a1 )
    v10 = (_DWORD)a1 + 16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      36,
      (unsigned int)&WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids,
      v10,
      a6);
  LsaLookupPerfCounterIncrementCount(0x1Au);
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    PerformanceCount.QuadPart = 0;
  while ( 1 )
  {
    LODWORD(v42) = LsapDbLookupGetServerConnection(
                     a1,
                     a6,
                     v9,
                     &hMem,
                     &v29,
                     &v30,
                     &v31,
                     &v28,
                     &v27,
                     &ObjectHandle,
                     &v36,
                     &v35);
    if ( (int)v42 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
        WPP_SF_ZD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          37,
          (unsigned int)&WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids,
          v10,
          v42);
      goto LABEL_47;
    }
    v11 = v36;
    if ( ObjectHandle || v36 )
      break;
    v12 = L"Kerberos";
    if ( v27 != 16 )
      v12 = L"Netlogon";
    TracePrintChainLookupSids(v12, hMem, a2, a3, a6, v36, *a7);
    v7 = 0;
    v13 = LsaICLookupSidsWithCreds(hMem, v30, v28, v27, v31, 0, a2, a3, a4, a5, a6, a7);
    LODWORD(v42) = v13;
    v14 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    {
      v15 = L"Kerberos";
      if ( v27 != 16 )
        v15 = L"Netlogon";
      WPP_SF_SSDd(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, *a7, (_DWORD)v15, (__int64)hMem, v13, *a7);
      v14 = WPP_GLOBAL_Control;
    }
    if ( (_DWORD)v42 != -1073741790 && !(unsigned int)IsRpcError(v42) || v9 )
    {
      v7 = (const WCHAR *)hMem;
      if ( (int)(v42 + 0x80000000) >= 0 && (_DWORD)v42 != -1073741709 )
      {
        if ( (*((_BYTE *)v14 + 108) & 0x40) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)v14 + 12),
            39,
            (unsigned int)&WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids,
            (_DWORD)hMem,
            v42);
LABEL_30:
        v16 = 1;
        goto LABEL_48;
      }
      if ( (*((_BYTE *)v14 + 108) & 0x40) != 0 )
      {
        v17 = hMem;
        v18 = 40;
        v19 = *((_QWORD *)v14 + 12);
LABEL_33:
        WPP_SF_S(v19, v18, &WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids, v17);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( v30 )
    {
      ((void (*)(void))pfnLsapINetlogonFree)();
      v30 = 0;
    }
    if ( v31 )
    {
      ((void (*)(void))pfnLsapINetlogonFree)();
      v31 = 0;
    }
    v9 = &v35;
  }
  ChainingFlags = LsapLookupGetChainingFlags(v29);
  v20 = ChainingFlags;
  if ( v11 )
  {
    v21 = (LSA_HANDLE)*((_QWORD *)v11 + 9);
    v7 = (const WCHAR *)*((_QWORD *)v11 + 6);
  }
  else
  {
    v21 = ObjectHandle;
    v7 = (const WCHAR *)hMem;
  }
  TracePrintChainLookupSids(L"Downlevel", v7, a2, a3, a6, &ChainingFlags, *a7);
  v22 = LsaICLookupSids(v21, a2, a3, a4, a5, a6, v20, a7, 0);
  LODWORD(v42) = v22;
  v24 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
  {
    WPP_SF_SSDd(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, v23, (unsigned int)L"Downlevel", (__int64)v7, v22, *a7);
    v24 = WPP_GLOBAL_Control;
  }
  if ( (int)(v42 + 0x80000000) >= 0 && (_DWORD)v42 != -1073741709 )
  {
    if ( (*((_BYTE *)v24 + 108) & 0x40) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)v24 + 12),
        42,
        (unsigned int)&WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids,
        (_DWORD)v7,
        v42);
    goto LABEL_30;
  }
  if ( (*((_BYTE *)v24 + 108) & 0x40) != 0 )
  {
    v19 = *((_QWORD *)v24 + 12);
    v18 = 43;
    v17 = (HLOCAL)v7;
    goto LABEL_33;
  }
LABEL_47:
  v16 = 0;
LABEL_48:
  if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v37) )
  {
    LsaLookupPerfCounterAddLargeAmount(0x1Du, v37.QuadPart - PerformanceCount.QuadPart);
    LsaLookupPerfCounterIncrementCount(0x1Eu);
  }
  if ( v16 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v7);
    if ( LsapLookupLogLevel )
      SpmpEventWrite(&LSAEVENT_LOOKUP_SC_LOOKUP_FAILED, L"uub", &DestinationString, &DestinationString, 4, va);
  }
  if ( (((_DWORD)v42 + 0x80000000) & 0x80000000) == 0
    && (_DWORD)v42 != -1073741709
    && !(unsigned __int8)LsapDbIsStatusConnectionFailure() )
  {
    LODWORD(v42) = -(a6 != 2) - 1073741427;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v30 )
    ((void (*)(void))pfnLsapINetlogonFree)();
  if ( v31 )
    ((void (*)(void))pfnLsapINetlogonFree)();
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( v36 )
    LsaDbExtDereferenceBindingCacheEntry(v36);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x1801016c0  mov     rax, rsp
0x1801016c3  mov     [rax+20h], r9
0x1801016c7  mov     [rax+18h], r8
0x1801016cb  mov     [rax+10h], edx
0x1801016ce  push    rbp
0x1801016cf  push    rbx
0x1801016d0  push    rsi
0x1801016d1  push    rdi
0x1801016d2  push    r12
0x1801016d4  push    r13
0x1801016d6  push    r15
0x1801016d8  lea     rbp, [rax-3Fh]
0x1801016dc  sub     rsp, 0D0h
0x1801016e3  xor     ebx, ebx
0x1801016e5  mov     r13, rcx
0x1801016e8  mov     dword ptr [rbp+37h+arg_38], ebx
0x1801016eb  mov     r15d, ebx
0x1801016ee  mov     [rbp+37h+hMem], rbx
0x1801016f2  mov     [rbp+37h+var_90], ebx
0x1801016f5  mov     [rbp+37h+var_88], rbx
0x1801016f9  mov     [rbp+37h+var_80], rbx
0x1801016fd  mov     [rbp+37h+var_94], ebx
0x180101700  mov     [rbp+37h+var_98], ebx
0x180101703  mov     [rbp+37h+ObjectHandle], rbx
0x180101707  mov     [rbp+37h+arg_0], bl
0x18010170a  mov     [rbp+37h+var_58], rbx
0x18010170e  mov     [rbp+37h+var_60], rbx
0x180101712  mov     qword ptr [rbp+37h+PerformanceCount], rbx
0x180101716  mov     qword ptr [rbp+37h+var_50], rbx
0x18010171a  cmp     [rcx], bx
0x18010171d  lea     rax, [rcx+10h]
0x180101721  mov     edi, [rbp+37h+arg_28]
0x180101724  mov     rsi, rcx
0x180101727  mov     rcx, cs:WPP_GLOBAL_Control
0x18010172e  cmovbe  rsi, rax
0x180101732  test    byte ptr [rcx+6Ch], 40h
0x180101736  jz      short loc_180101752
0x180101738  mov     rcx, [rcx+60h]
0x18010173c  lea     edx, [rbx+24h]
0x18010173f  mov     r9, rsi
0x180101742  mov     dword ptr [rsp+100h+var_E0], edi
0x180101746  lea     r8, WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids
0x18010174d  call    WPP_SF_ZD
0x180101752  mov     ecx, 1Ah; unsigned int
0x180101757  call    ?LsaLookupPerfCounterIncrementCount@@YAXK@Z; LsaLookupPerfCounterIncrementCount(ulong)
0x18010175c  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x180101760  call    cs:__imp_QueryPerformanceCounter
0x180101767  nop     dword ptr [rax+rax+00h]
0x18010176c  test    eax, eax
0x18010176e  jnz     short loc_180101774
0x180101770  mov     qword ptr [rbp+37h+PerformanceCount], rbx
0x180101774  mov     r12, [rbp+37h+arg_30]
0x180101778  lea     rax, [rbp+37h+var_60]
0x18010177c  mov     r8, r15
0x18010177f  mov     [rsp+58h], rax
0x180101784  lea     r9, [rbp+37h+hMem]
0x180101788  lea     rax, [rbp+37h+var_58]
0x18010178c  mov     edx, edi
0x18010178e  mov     [rsp+100h+var_B0], rax
0x180101793  mov     rcx, r13
0x180101796  lea     rax, [rbp+37h+ObjectHandle]
0x18010179a  mov     [rsp+100h+var_B8], rax
0x18010179f  lea     rax, [rbp+37h+var_98]
0x1801017a3  mov     [rsp+100h+var_C0], rax
0x1801017a8  lea     rax, [rbp+37h+var_94]
0x1801017ac  mov     [rsp+100h+var_C8], rax
0x1801017b1  lea     rax, [rbp+37h+var_80]
0x1801017b5  mov     [rsp+100h+var_D0], rax
0x1801017ba  lea     rax, [rbp+37h+var_88]
0x1801017be  mov     [rsp+100h+var_D8], rax
0x1801017c3  lea     rax, [rbp+37h+var_90]
0x1801017c7  mov     [rsp+100h+var_E0], rax
0x1801017cc  call    ?LsapDbLookupGetServerConnection@@YAJPEAU_LSAPR_TRUST_INFORMATION_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAT_LARGE_INTEGER@@PEAPEAGPEAW4_NL_OS_VERSION@@3PEAPEAXPEAK65PEAPEAU_LSAP_BINDING_CACHE_ENTRY@@2@Z; LsapDbLookupGetServerConnection(_LSAPR_TRUST_INFORMATION_EX *,_LSAP_LOOKUP_LEVEL,_LARGE_INTEGER *,ushort * *,_NL_OS_VERSION *,ushort * *,void * *,ulong *,ulong *,void * *,_LSAP_BINDING_CACHE_ENTRY * *,_LARGE_INTEGER *)
0x1801017d1  mov     dword ptr [rbp+37h+arg_38], eax
0x1801017d4  test    eax, eax
0x1801017d6  js      loc_180101ACC
0x1801017dc  cmp     [rbp+37h+ObjectHandle], 0
0x1801017e1  mov     rbx, [rbp+37h+var_58]
0x1801017e5  jnz     loc_1801019B2
0x1801017eb  test    rbx, rbx
0x1801017ee  jnz     loc_1801019B2
0x1801017f4  mov     eax, [r12]
0x1801017f8  lea     rdx, aNetlogon; "Netlogon"
0x1801017ff  cmp     [rbp+37h+var_98], 10h
0x180101803  lea     rcx, aKerberos_0; "Kerberos"
0x18010180a  mov     r8d, [rbp+37h+arg_8]
0x18010180e  mov     dword ptr [rsp+100h+var_D0], eax
0x180101812  cmovnz  rcx, rdx
0x180101816  mov     rdx, [rbp+37h+hMem]
0x18010181a  mov     [rsp+100h+var_D8], rbx
0x18010181f  mov     rbx, [rbp+37h+arg_10]
0x180101823  mov     r9, rbx
0x180101826  mov     dword ptr [rsp+100h+var_E0], edi
0x18010182a  call    ?TracePrintChainLookupSids@@YAXPEBG0KPEAPEAXW4_LSAP_LOOKUP_LEVEL@@PEAKK@Z; TracePrintChainLookupSids(ushort const *,ushort const *,ulong,void * *,_LSAP_LOOKUP_LEVEL,ulong *,ulong)
0x18010182f  mov     rax, [rbp+37h+arg_20]
0x180101833  mov     r9d, [rbp+37h+var_98]
0x180101837  mov     r8d, [rbp+37h+var_94]
0x18010183b  mov     rdx, [rbp+37h+var_88]
0x18010183f  mov     rcx, [rbp+37h+hMem]
0x180101843  mov     [rsp+58h], r12
0x180101848  mov     dword ptr [rsp+100h+var_B0], edi
0x18010184c  mov     [rsp+100h+var_B8], rax
0x180101851  mov     rax, [rbp+37h+arg_18]
0x180101855  mov     [rsp+100h+var_C0], rax
0x18010185a  mov     eax, [rbp+37h+arg_8]
0x18010185d  mov     [rsp+100h+var_C8], rbx
0x180101862  xor     ebx, ebx
0x180101864  mov     dword ptr [rsp+100h+var_D0], eax
0x180101868  mov     rax, [rbp+37h+var_80]
0x18010186c  mov     dword ptr [rsp+100h+var_D8], ebx
0x180101870  mov     [rsp+100h+var_E0], rax
0x180101875  call    cs:__imp_LsaICLookupSidsWithCreds
0x18010187c  nop     dword ptr [rax+rax+00h]
0x180101881  mov     ecx, eax
0x180101883  mov     dword ptr [rbp+37h+arg_38], eax
0x180101886  mov     r11, cs:WPP_GLOBAL_Control
0x18010188d  test    byte ptr [r11+6Ch], 40h
0x180101892  jz      short loc_1801018D3
0x180101894  mov     r8d, [r12]
0x180101898  lea     rax, aNetlogon; "Netlogon"
0x18010189f  cmp     [rbp+37h+var_98], 10h
0x1801018a3  lea     r9, aKerberos_0; "Kerberos"
0x1801018aa  mov     r10, [rbp+37h+hMem]
0x1801018ae  lea     edx, [rbx+26h]
0x1801018b1  mov     dword ptr [rsp+100h+var_D0], r8d
0x1801018b6  cmovnz  r9, rax
0x1801018ba  mov     dword ptr [rsp+100h+var_D8], ecx
0x1801018be  mov     rcx, [r11+60h]
0x1801018c2  mov     [rsp+100h+var_E0], r10
0x1801018c7  call    WPP_SF_SSDd
0x1801018cc  mov     r11, cs:WPP_GLOBAL_Control
0x1801018d3  mov     ecx, dword ptr [rbp+37h+arg_38]; int
0x1801018d6  cmp     ecx, 0C0000022h
0x1801018dc  jz      short loc_1801018E7
0x1801018de  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x1801018e3  test    eax, eax
0x1801018e5  jz      short loc_180101940
0x1801018e7  test    r15, r15
0x1801018ea  jnz     short loc_180101940
0x1801018ec  mov     rcx, [rbp+37h+hMem]; hMem
0x1801018f0  test    rcx, rcx
0x1801018f3  jz      short loc_180101905
0x1801018f5  call    cs:__imp_LocalFree
0x1801018fc  nop     dword ptr [rax+rax+00h]
0x180101901  mov     [rbp+37h+hMem], rbx
0x180101905  mov     rcx, [rbp+37h+var_88]
0x180101909  test    rcx, rcx
0x18010190c  jz      short loc_18010191E
0x18010190e  mov     rax, cs:?pfnLsapINetlogonFree@@3P6AXPEAX@ZEA; void (*pfnLsapINetlogonFree)(void *)
0x180101915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010191a  mov     [rbp+37h+var_88], rbx
0x18010191e  mov     rcx, [rbp+37h+var_80]
0x180101922  test    rcx, rcx
0x180101925  jz      short loc_180101937
0x180101927  mov     rax, cs:?pfnLsapINetlogonFree@@3P6AXPEAX@ZEA; void (*pfnLsapINetlogonFree)(void *)
0x18010192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101933  mov     [rbp+37h+var_80], rbx
0x180101937  lea     r15, [rbp+37h+var_60]
0x18010193b  jmp     loc_180101778
0x180101940  mov     ecx, dword ptr [rbp+37h+arg_38]
0x180101943  mov     r15d, 80000000h
0x180101949  mov     rbx, [rbp+37h+hMem]
0x18010194d  lea     eax, [rcx+r15]
0x180101951  test    r15d, eax
0x180101954  jnz     short loc_180101989
0x180101956  cmp     ecx, 0C0000073h
0x18010195c  jz      short loc_180101989
0x18010195e  test    byte ptr [r11+6Ch], 40h
0x180101963  jz      short loc_180101981
0x180101965  mov     dword ptr [rsp+100h+var_E0], ecx
0x180101969  mov     edx, 27h ; '''
0x18010196e  mov     rcx, [r11+60h]
0x180101972  lea     r8, WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids
0x180101979  mov     r9, rbx
0x18010197c  call    WPP_SF_Sd
0x180101981  mov     sil, 1
0x180101984  jmp     loc_180101B02
0x180101989  test    byte ptr [r11+6Ch], 40h
0x18010198e  jz      loc_180101AFE
0x180101994  mov     r9, [rbp+37h+hMem]
0x180101998  mov     edx, 28h ; '('
0x18010199d  mov     rcx, [r11+60h]
0x1801019a1  lea     r8, WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids
0x1801019a8  call    WPP_SF_S
0x1801019ad  jmp     loc_180101AFE
0x1801019b2  mov     ecx, [rbp+37h+var_90]
0x1801019b5  call    ?LsapLookupGetChainingFlags@@YAKW4_NL_OS_VERSION@@@Z; LsapLookupGetChainingFlags(_NL_OS_VERSION)
0x1801019ba  mov     [rbp+37h+var_68], eax
0x1801019bd  mov     r15d, eax
0x1801019c0  test    rbx, rbx
0x1801019c3  jz      short loc_1801019CF
0x1801019c5  mov     rsi, [rbx+48h]
0x1801019c9  mov     rbx, [rbx+30h]
0x1801019cd  jmp     short loc_1801019D7
0x1801019cf  mov     rsi, [rbp+37h+ObjectHandle]
0x1801019d3  mov     rbx, [rbp+37h+hMem]
0x1801019d7  mov     eax, [r12]
0x1801019db  lea     rcx, aDownlevel; "Downlevel"
0x1801019e2  mov     r9, [rbp+37h+arg_10]
0x1801019e6  mov     rdx, rbx
0x1801019e9  mov     r8d, [rbp+37h+arg_8]
0x1801019ed  mov     dword ptr [rsp+100h+var_D0], eax
0x1801019f1  lea     rax, [rbp+37h+var_68]
0x1801019f5  mov     [rsp+100h+var_D8], rax
0x1801019fa  mov     dword ptr [rsp+100h+var_E0], edi
0x1801019fe  call    ?TracePrintChainLookupSids@@YAXPEBG0KPEAPEAXW4_LSAP_LOOKUP_LEVEL@@PEAKK@Z; TracePrintChainLookupSids(ushort const *,ushort const *,ulong,void * *,_LSAP_LOOKUP_LEVEL,ulong *,ulong)
0x180101a03  mov     rax, [rbp+37h+arg_20]
0x180101a07  mov     rcx, rsi
0x180101a0a  mov     r9, [rbp+37h+arg_18]
0x180101a0e  mov     r8, [rbp+37h+arg_10]
0x180101a12  mov     edx, [rbp+37h+arg_8]
0x180101a15  mov     [rsp+100h+var_C0], 0
0x180101a1e  mov     [rsp+100h+var_C8], r12
0x180101a23  mov     dword ptr [rsp+100h+var_D0], r15d
0x180101a28  mov     dword ptr [rsp+100h+var_D8], edi
0x180101a2c  mov     [rsp+100h+var_E0], rax
0x180101a31  call    cs:__imp_LsaICLookupSids
0x180101a38  nop     dword ptr [rax+rax+00h]
0x180101a3d  mov     ecx, eax
0x180101a3f  mov     dword ptr [rbp+37h+arg_38], eax
0x180101a42  mov     r10, cs:WPP_GLOBAL_Control
0x180101a49  test    byte ptr [r10+6Ch], 40h
0x180101a4e  jz      short loc_180101A7D
0x180101a50  mov     eax, [r12]
0x180101a54  lea     r9, aDownlevel; "Downlevel"
0x180101a5b  mov     dword ptr [rsp+100h+var_D0], eax
0x180101a5f  mov     edx, 29h ; ')'
0x180101a64  mov     dword ptr [rsp+100h+var_D8], ecx
0x180101a68  mov     rcx, [r10+60h]
0x180101a6c  mov     [rsp+100h+var_E0], rbx
0x180101a71  call    WPP_SF_SSDd
0x180101a76  mov     r10, cs:WPP_GLOBAL_Control
0x180101a7d  mov     ecx, dword ptr [rbp+37h+arg_38]
0x180101a80  mov     r15d, 80000000h
0x180101a86  lea     eax, [rcx+r15]
0x180101a8a  test    r15d, eax
0x180101a8d  jnz     short loc_180101AB4
0x180101a8f  cmp     ecx, 0C0000073h
0x180101a95  jz      short loc_180101AB4
0x180101a97  test    byte ptr [r10+6Ch], 40h
0x180101a9c  jz      loc_180101981
0x180101aa2  mov     dword ptr [rsp+100h+var_E0], ecx
0x180101aa6  mov     edx, 2Ah ; '*'
0x180101aab  mov     rcx, [r10+60h]
0x180101aaf  jmp     loc_180101972
0x180101ab4  test    byte ptr [r10+6Ch], 40h
0x180101ab9  jz      short loc_180101AFE
0x180101abb  mov     rcx, [r10+60h]
0x180101abf  mov     edx, 2Bh ; '+'
0x180101ac4  mov     r9, rbx
0x180101ac7  jmp     loc_1801019A1
0x180101acc  mov     rcx, cs:WPP_GLOBAL_Control
0x180101ad3  test    byte ptr [rcx+6Ch], 40h
0x180101ad7  jz      short loc_180101AF8
0x180101ad9  mov     eax, dword ptr [rbp+37h+arg_38]
0x180101adc  lea     r8, WPP_792ac6c5cdd33993a01f23d7478998c8_Traceguids
0x180101ae3  mov     rcx, [rcx+60h]
0x180101ae7  mov     edx, 25h ; '%'
0x180101aec  mov     r9, rsi
0x180101aef  mov     dword ptr [rsp+100h+var_E0], eax
0x180101af3  call    WPP_SF_ZD
0x180101af8  mov     r15d, 80000000h
0x180101afe  mov     sil, [rbp+37h+arg_0]
0x180101b02  cmp     qword ptr [rbp+37h+PerformanceCount], 0
0x180101b07  jz      short loc_180101B39
0x180101b09  lea     rcx, [rbp+37h+var_50]; lpPerformanceCount
0x180101b0d  call    cs:__imp_QueryPerformanceCounter
0x180101b14  nop     dword ptr [rax+rax+00h]
0x180101b19  test    eax, eax
0x180101b1b  jz      short loc_180101B39
0x180101b1d  mov     rdx, qword ptr [rbp+37h+var_50]
0x180101b21  mov     ecx, 1Dh; unsigned int
0x180101b26  sub     rdx, qword ptr [rbp+37h+PerformanceCount]; unsigned __int64
0x180101b2a  call    ?LsaLookupPerfCounterAddLargeAmount@@YAXK_K@Z; LsaLookupPerfCounterAddLargeAmount(ulong,unsigned __int64)
0x180101b2f  mov     ecx, 1Eh; unsigned int
0x180101b34  call    ?LsaLookupPerfCounterIncrementCount@@YAXK@Z; LsaLookupPerfCounterIncrementCount(ulong)
0x180101b39  test    sil, sil
0x180101b3c  jz      short loc_180101B8E
0x180101b3e  xorps   xmm0, xmm0
0x180101b41  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180101b45  mov     rdx, rbx; SourceString
0x180101b48  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180101b4c  call    cs:__imp_RtlInitUnicodeString
0x180101b53  nop     dword ptr [rax+rax+00h]
0x180101b58  cmp     cs:?LsapLookupLogLevel@@3KA, 1; ulong LsapLookupLogLevel
0x180101b5f  jb      short loc_180101B8E
0x180101b61  lea     rax, [rbp+37h+arg_38]
0x180101b65  mov     [rsp+100h+var_D8], rax
0x180101b6a  lea     r9, [rbp+37h+DestinationString]
0x180101b6e  lea     r8, [rbp+37h+DestinationString]
0x180101b72  mov     [rsp+100h+var_E0], 4
0x180101b7b  lea     rdx, aUub; "uub"
0x180101b82  lea     rcx, LSAEVENT_LOOKUP_SC_LOOKUP_FAILED; struct _EVENT_DESCRIPTOR *
0x180101b89  call    ?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180101b8e  mov     ecx, dword ptr [rbp+37h+arg_38]
0x180101b91  lea     eax, [rcx+r15]
0x180101b95  test    r15d, eax
0x180101b98  jnz     short loc_180101BBA
0x180101b9a  cmp     ecx, 0C0000073h
0x180101ba0  jz      short loc_180101BBA
  ... truncated ...
```
