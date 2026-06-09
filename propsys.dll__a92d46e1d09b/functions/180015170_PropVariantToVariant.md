# PropVariantToVariant

- ea: `0x180015170`
- end: `0x180015495`
- name: `PropVariantToVariant`
- size: `805`
- prototype: `HRESULT __stdcall(const PROPVARIANT *pPropVar, VARIANT *pVar)`
- caller_count: `35`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009590`
- `0x18000b560`
- `0x18000ca30`
- `0x18000df60`
- `0x18000f050`
- `0x180014ef0`
- `0x180015170`
- `0x18002b3d4`
- `0x18002d370`
- `0x18002d640`
- `0x180051abc`
- `0x18005b8c0`
- `0x180062828`
- `0x180088f74`
- `0x18008909c`
- `0x1800891c0`
- `0x1800892e4`
- `0x180089408`
- `0x180089530`
- `0x180089654`
- `0x18008976c`
- `0x180089894`
- `0x1800899c0`
- `0x180089b24`
- `0x180089c88`
- `0x180089de8`
- `0x180089f4c`
- `0x18008a0b0`
- `0x18008a1f8`
- `0x18008a35c`
- `0x18008a4c0`
- `0x18008a624`
- `0x18008a780`
- `0x18008ee80`
- `0x180096da0`

## callees

- `0x180015170`
- `0x18005b8c0`
- `0x18006b7b8`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180015380`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180015380`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001534b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001534b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800151ff`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800151ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015399`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015399`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180015371`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180015371`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800152ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800152ba`
- `OLEAUT32!__imp_SysAllocString` at `0x180015329`
- `OLEAUT32!__imp_SysAllocString` at `0x1800153ad`
- `OLEAUT32!__imp_SysAllocString` at `0x180015329`
- `OLEAUT32!__imp_SysAllocString` at `0x1800153ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800151bc`
- `OLEAUT32!__imp_VariantInit` at `0x1800151bc`
- `OLEAUT32!__imp_VariantCopy` at `0x180015280`
- `OLEAUT32!__imp_VariantCopy` at `0x180015280`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180015215`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180015215`

## pseudocode

```c
HRESULT __stdcall PropVariantToVariant(const PROPVARIANT *pPropVar, VARIANT *pVar)
{
  int v4; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  VARIANT *v9; // rax
  BSTR v10; // rax
  HGLOBAL v11; // rax
  void *v12; // r14
  BSTR v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  LPSTREAM ppstm; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+38h] [rbp-31h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-19h] BYREF

  if ( pVar && pPropVar )
  {
    v4 = -2147024882;
    VariantInit(pVar);
    v6 = *(unsigned __int16 *)pPropVar;
    if ( v6 <= 0x44 )
    {
      switch ( v6 )
      {
        case 0x44u:
          return -2147316576;
        case 0x1Eu:
          v10 = SysAllocStringA(*((const char **)pPropVar + 1));
          break;
        case 0x1Fu:
          v10 = SysAllocString(*((const OLECHAR **)pPropVar + 1));
          break;
        case 0x40u:
          SystemTime = 0;
          if ( FileTimeToSystemTime((const FILETIME *)pPropVar + 1, &SystemTime)
            && SystemTimeToVariantTime(&SystemTime, &pVar->dblVal) )
          {
            pVar->vt = 7;
            return 0;
          }
          return -2147316576;
        case 0x41u:
          v11 = GlobalAlloc(2u, 0);
          v12 = v11;
          if ( v11 )
          {
            ppstm = 0;
            v4 = CreateStreamOnHGlobal(v11, 1, &ppstm);
            if ( v4 >= 0 )
            {
              v14 = *((unsigned int *)pPropVar + 2);
              v15 = *((_QWORD *)pPropVar + 2);
              v17 = 0;
              v4 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, int *))(*(_QWORD *)ppstm + 32LL))(
                     ppstm,
                     v15,
                     v14,
                     &v17);
              if ( v4 >= 0 )
              {
                *(_QWORD *)&SystemTime.wYear = 0;
                v4 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                       ppstm,
                       0,
                       0,
                       0);
                if ( v4 >= 0 )
                {
                  v4 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(
                         ppstm,
                         &IID_IUnknown,
                         (ULONG *)&pVar->cyVal);
                  if ( v4 >= 0 )
                    pVar->vt = 13;
                }
              }
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
            }
            else
            {
              GlobalFree(v12);
            }
          }
          return v4;
        case 0x42u:
          v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, ULONG *))pPropVar + 1))(
                 *((_QWORD *)pPropVar + 1),
                 &IID_IUnknown,
                 (ULONG *)&pVar->cyVal);
          if ( v4 >= 0 )
            pVar->vt = 13;
          return v4;
        case 0x43u:
          return -2147316576;
        default:
LABEL_17:
          if ( (v6 & 0x1000) != 0 )
            return HrPropVarVECTORToSAFEARRAYVariant(pVar, (const struct tagPROPVARIANT *)pPropVar, v5, v6 & 0xEFFF);
          else
            return VariantCopy(pVar, (const VARIANTARG *)pPropVar);
      }
      if ( !v10 )
        return v4;
      pVar->llVal = (LONGLONG)v10;
      pVar->vt = 8;
      return 0;
    }
    switch ( v6 )
    {
      case 0x45u:
      case 0x46u:
      case 0x47u:
        return -2147316576;
      case 0x48u:
        v4 = StringFromGUID2(*((const GUID *const *)pPropVar + 1), sz, 39);
        if ( v4 >= 0 )
        {
          v13 = SysAllocString(sz);
          if ( v13 )
          {
            pVar->llVal = (LONGLONG)v13;
            pVar->vt = 8;
          }
          else
          {
            return -2147024882;
          }
        }
        return v4;
      case 0x1047u:
        return -2147316576;
      case 0x400Cu:
        v9 = (VARIANT *)CoTaskMemAlloc(0x18u);
        pVar->llVal = (LONGLONG)v9;
        if ( v9 )
        {
          v4 = PropVariantToVariant(*((const PROPVARIANT **)pPropVar + 1), v9);
          if ( v4 < 0 )
          {
            CoTaskMemFree(pVar->bstrVal);
            pVar->llVal = 0;
          }
          else
          {
            pVar->vt = 16396;
          }
        }
        return v4;
    }
    goto LABEL_17;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180015170  mov     [rsp-8+arg_10], rbx
0x180015175  mov     [rsp-8+arg_18], rsi
0x18001517a  push    rbp
0x18001517b  push    rdi
0x18001517c  push    r14
0x18001517e  lea     rbp, [rsp-47h]
0x180015183  sub     rsp, 0B0h
0x18001518a  mov     rax, cs:__security_cookie
0x180015191  xor     rax, rsp
0x180015194  mov     [rbp+57h+var_20], rax
0x180015198  mov     rdi, rdx
0x18001519b  mov     rsi, rcx
0x18001519e  test    rdx, rdx
0x1800151a1  jz      loc_180015250
0x1800151a7  test    rcx, rcx
0x1800151aa  jz      loc_180015250
0x1800151b0  mov     r14d, 8007000Eh
0x1800151b6  mov     rcx, rdx; pvarg
0x1800151b9  mov     ebx, r14d
0x1800151bc  call    cs:__imp_VariantInit
0x1800151c2  movzx   r9d, word ptr [rsi]
0x1800151c6  cmp     r9d, 44h ; 'D'
0x1800151ca  ja      loc_18001528A
0x1800151d0  jz      loc_1800152ED
0x1800151d6  mov     ecx, r9d
0x1800151d9  sub     ecx, 1Eh
0x1800151dc  jz      loc_180015455
0x1800151e2  sub     ecx, 1
0x1800151e5  jz      loc_180015325
0x1800151eb  sub     ecx, 21h ; '!'
0x1800151ee  jnz     short loc_180015257
0x1800151f0  xorps   xmm0, xmm0
0x1800151f3  lea     rcx, [rsi+8]; lpFileTime
0x1800151f7  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800151fb  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800151ff  call    cs:__imp_FileTimeToSystemTime
0x180015205  test    eax, eax
0x180015207  jz      loc_1800152ED
0x18001520d  lea     rdx, [rdi+8]; pvtime
0x180015211  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180015215  call    cs:__imp_SystemTimeToVariantTime
0x18001521b  test    eax, eax
0x18001521d  jz      loc_1800152ED
0x180015223  mov     word ptr [rdi], 7
0x180015228  xor     ebx, ebx
0x18001522a  mov     eax, ebx
0x18001522c  mov     rcx, [rbp+57h+var_20]
0x180015230  xor     rcx, rsp; StackCookie
0x180015233  call    __security_check_cookie
0x180015238  lea     r11, [rsp+0C0h+var_10]
0x180015240  mov     rbx, [r11+30h]
0x180015244  mov     rsi, [r11+38h]
0x180015248  mov     rsp, r11
0x18001524b  pop     r14
0x18001524d  pop     rdi
0x18001524e  pop     rbp
0x18001524f  retn
0x180015250  mov     eax, 80070057h
0x180015255  jmp     short loc_18001522C
0x180015257  sub     ecx, 1
0x18001525a  jz      loc_180015346
0x180015260  sub     ecx, 1
0x180015263  jz      loc_1800152F7
0x180015269  cmp     ecx, 1
0x18001526c  jz      short loc_1800152ED
0x18001526e  bt      r9w, 0Ch
0x180015274  mov     rdx, rsi; struct tagPROPVARIANT *
0x180015277  mov     rcx, rdi; struct tagVARIANT *
0x18001527a  jb      loc_18001546B
0x180015280  call    cs:__imp_VariantCopy
0x180015286  mov     ebx, eax
0x180015288  jmp     short loc_18001522A
0x18001528a  mov     ecx, r9d
0x18001528d  sub     ecx, 45h ; 'E'
0x180015290  jz      short loc_1800152ED
0x180015292  sub     ecx, 1
0x180015295  jz      short loc_1800152ED
0x180015297  sub     ecx, 1
0x18001529a  jz      short loc_1800152ED
0x18001529c  sub     ecx, 1
0x18001529f  jz      loc_18001538B
0x1800152a5  sub     ecx, 0FFFh
0x1800152ab  jz      short loc_1800152ED
0x1800152ad  cmp     ecx, 2FC5h
0x1800152b3  jnz     short loc_18001526E
0x1800152b5  mov     ecx, 18h; cb
0x1800152ba  call    cs:__imp_CoTaskMemAlloc
0x1800152c0  mov     [rdi+8], rax
0x1800152c4  test    rax, rax
0x1800152c7  jz      loc_18001522A
0x1800152cd  mov     rcx, [rsi+8]; pPropVar
0x1800152d1  mov     rdx, rax; pVar
0x1800152d4  call    PropVariantToVariant
0x1800152d9  mov     ebx, eax
0x1800152db  test    eax, eax
0x1800152dd  js      loc_18001547E
0x1800152e3  mov     word ptr [rdi], 400Ch
0x1800152e8  jmp     loc_18001522A
0x1800152ed  mov     ebx, 80028CA0h
0x1800152f2  jmp     loc_18001522A
0x1800152f7  mov     rcx, [rsi+8]
0x1800152fb  lea     r8, [rdi+8]
0x1800152ff  lea     rdx, IID_IUnknown
0x180015306  mov     rax, [rcx]
0x180015309  mov     rax, [rax]
0x18001530c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015311  mov     ebx, eax
0x180015313  test    eax, eax
0x180015315  js      loc_18001522A
0x18001531b  mov     word ptr [rdi], 0Dh
0x180015320  jmp     loc_18001522A
0x180015325  mov     rcx, [rsi+8]; psz
0x180015329  call    cs:__imp_SysAllocString
0x18001532f  test    rax, rax
0x180015332  jz      loc_18001522A
0x180015338  mov     [rdi+8], rax
0x18001533c  mov     word ptr [rdi], 8
0x180015341  jmp     loc_180015228
0x180015346  xor     edx, edx; dwBytes
0x180015348  lea     ecx, [rdx+2]; uFlags
0x18001534b  call    cs:__imp_GlobalAlloc
0x180015351  mov     r14, rax
0x180015354  test    rax, rax
0x180015357  jz      loc_18001522A
0x18001535d  lea     r8, [rbp+57h+ppstm]; ppstm
0x180015361  mov     [rbp+57h+ppstm], 0
0x180015369  mov     edx, 1; fDeleteOnRelease
0x18001536e  mov     rcx, rax; hGlobal
0x180015371  call    cs:__imp_CreateStreamOnHGlobal
0x180015377  mov     ebx, eax
0x180015379  test    eax, eax
0x18001537b  jns     short loc_1800153CA
0x18001537d  mov     rcx, r14; hMem
0x180015380  call    cs:__imp_GlobalFree
0x180015386  jmp     loc_18001522A
0x18001538b  mov     rcx, [rsi+8]; rguid
0x18001538f  lea     rdx, [rbp+57h+sz]; lpsz
0x180015393  mov     r8d, 27h ; '''; cchMax
0x180015399  call    cs:__imp_StringFromGUID2
0x18001539f  mov     ebx, eax
0x1800153a1  test    eax, eax
0x1800153a3  js      loc_18001522A
0x1800153a9  lea     rcx, [rbp+57h+sz]; psz
0x1800153ad  call    cs:__imp_SysAllocString
0x1800153b3  test    rax, rax
0x1800153b6  jz      loc_180015463
0x1800153bc  mov     [rdi+8], rax
0x1800153c0  mov     word ptr [rdi], 8
0x1800153c5  jmp     loc_18001522A
0x1800153ca  mov     rcx, [rbp+57h+ppstm]
0x1800153ce  lea     r9, [rbp+57h+var_88]
0x1800153d2  mov     r8d, [rsi+8]
0x1800153d6  mov     rdx, [rsi+10h]
0x1800153da  mov     [rbp+57h+var_88], 0
0x1800153e1  mov     rax, [rcx]
0x1800153e4  mov     rax, [rax+20h]
0x1800153e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ed  mov     ebx, eax
0x1800153ef  test    eax, eax
0x1800153f1  js      short loc_180015440
0x1800153f3  mov     rcx, [rbp+57h+ppstm]
0x1800153f7  xor     r9d, r9d
0x1800153fa  mov     qword ptr [rbp+57h+SystemTime.wYear], 0
0x180015402  xor     r8d, r8d
0x180015405  mov     rdx, qword ptr [rbp+57h+SystemTime.wYear]
0x180015409  mov     rax, [rcx]
0x18001540c  mov     rax, [rax+28h]
0x180015410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015415  mov     ebx, eax
0x180015417  test    eax, eax
0x180015419  js      short loc_180015440
0x18001541b  mov     rcx, [rbp+57h+ppstm]
0x18001541f  lea     r8, [rdi+8]
0x180015423  lea     rdx, IID_IUnknown
0x18001542a  mov     rax, [rcx]
0x18001542d  mov     rax, [rax]
0x180015430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015435  mov     ebx, eax
0x180015437  test    eax, eax
0x180015439  js      short loc_180015440
0x18001543b  mov     word ptr [rdi], 0Dh
0x180015440  mov     rcx, [rbp+57h+ppstm]
0x180015444  mov     rax, [rcx]
0x180015447  mov     rax, [rax+10h]
0x18001544b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015450  jmp     loc_18001522A
0x180015455  mov     rcx, [rsi+8]; char *
0x180015459  call    ?SysAllocStringA@@YAPEAGPEBD@Z; SysAllocStringA(char const *)
0x18001545e  jmp     loc_18001532F
0x180015463  mov     ebx, r14d
0x180015466  jmp     loc_18001522A
0x18001546b  mov     eax, 0EFFFh
0x180015470  and     r9w, ax; unsigned __int16
0x180015474  call    ?HrPropVarVECTORToSAFEARRAYVariant@@YAJPEAUtagVARIANT@@AEBUtagPROPVARIANT@@KG@Z; HrPropVarVECTORToSAFEARRAYVariant(tagVARIANT *,tagPROPVARIANT const &,ulong,ushort)
0x180015479  jmp     loc_180015286
0x18001547e  mov     rcx, [rdi+8]; pv
0x180015482  call    cs:__imp_CoTaskMemFree
0x180015488  mov     qword ptr [rdi+8], 0
0x180015490  jmp     loc_18001522A
```
