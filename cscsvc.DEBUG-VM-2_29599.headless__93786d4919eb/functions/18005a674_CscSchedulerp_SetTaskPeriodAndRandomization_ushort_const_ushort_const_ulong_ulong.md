# CscSchedulerp_SetTaskPeriodAndRandomization(ushort const *,ushort const *,ulong *,ulong *)

- ea: `0x18005a674`
- end: `0x18005ac64`
- name: `?CscSchedulerp_SetTaskPeriodAndRandomization@@YAJPEBG0PEAK1@Z`
- size: `1520`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005a240`

## callees

- `0x180033ddc`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18005a674`
- `0x180089010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005ab93`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ab9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ab93`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ab9d`
- `OLEAUT32!__imp_VariantInit` at `0x18005a6f5`
- `OLEAUT32!__imp_VariantInit` at `0x18005a6f5`
- `OLEAUT32!__imp_VariantClear` at `0x18005a75c`
- `OLEAUT32!__imp_VariantClear` at `0x18005a75c`
- `KERNEL32!CompareStringW` at `0x18005a92e`
- `KERNEL32!CompareStringW` at `0x18005a9ec`
- `KERNEL32!CompareStringW` at `0x18005a92e`
- `KERNEL32!CompareStringW` at `0x18005a9ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a6cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a6cd`

## pseudocode

```c
__int64 __fastcall CscSchedulerp_SetTaskPeriodAndRandomization(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, WCHAR *); // rax
  int v9; // edi
  __int64 (__fastcall *v10)(__int64, const unsigned __int16 *, __int64); // rax
  unsigned int v11; // eax
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-78h] BYREF
  PCNZWCH v22; // [rsp+90h] [rbp-70h] BYREF
  PCNZWCH lpString1; // [rsp+98h] [rbp-68h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+C0h] [rbp-40h]
  VARIANTARG v27; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v28; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v29; // [rsp+110h] [rbp+10h] BYREF
  WCHAR String2[8]; // [rsp+130h] [rbp+30h] BYREF
  IRecordInfo *pRecInfo; // [rsp+140h] [rbp+40h]
  WCHAR v32[16]; // [rsp+150h] [rbp+50h] BYREF

  ppv = 0;
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v6 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 1;
    pvarg.llVal = 0;
    v7 = *(_QWORD *)ppv;
    *(_OWORD *)String2 = *(unsigned __int64 *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, WCHAR *))(v7 + 80);
    *(_OWORD *)&v27.vt = *(unsigned __int64 *)&pvarg.vt;
    v27.pRecInfo = pvarg.pRecInfo;
    *(_OWORD *)&v28.vt = *(unsigned __int64 *)&pvarg.vt;
    v28.pRecInfo = pvarg.pRecInfo;
    *(_OWORD *)&v29.vt = *(unsigned __int64 *)&pvarg.vt;
    v29.pRecInfo = pvarg.pRecInfo;
    v6 = v8(ppv, &v29, &v28, &v27, String2);
    VariantClear(&pvarg);
    if ( v6 < 0 )
      goto LABEL_46;
    v20 = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(
           ppv,
           L"\\Microsoft\\Windows\\Offline Files",
           &v20);
    if ( v6 < 0 )
      goto LABEL_46;
    v24 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v20 + 104LL))(
           v20,
           L"Background Synchronization",
           &v24);
    if ( v6 < 0 )
    {
LABEL_45:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_46:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_47;
    }
    v19 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 152LL))(v24, &v19);
    if ( v6 < 0 )
    {
LABEL_44:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_45;
    }
    v18 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 72LL))(v19, &v18);
    if ( v6 < 0 )
    {
LABEL_43:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_44;
    }
    v13 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v13);
    if ( v6 < 0 )
      goto LABEL_41;
    if ( v13 != 1 )
    {
LABEL_42:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_43;
    }
    v17 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, 1, &v17) < 0 )
    {
LABEL_41:
      v6 = -2147024809;
      goto LABEL_42;
    }
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v14);
    if ( v6 < 0
      || v14 != 1
      || (v15 = 0,
          v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(v17, &IID_ITimeTrigger, &v15),
          v6 < 0) )
    {
LABEL_40:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_42;
    }
    lpString1 = 0;
    v9 = 0;
    v22 = 0;
    v16 = 0;
    if ( a4 )
    {
      v6 = StringCchPrintfW(String2, 0x10u, L"PT%dM", *a4);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v15 + 160LL))(v15, &lpString1);
        if ( v6 >= 0 )
        {
          if ( CompareStringW(0x400u, 1u, lpString1, -1, String2, -1) == 2 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids);
            }
          }
          else
          {
            v6 = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v15 + 168LL))(v15, String2);
            v9 = 1;
          }
        }
      }
    }
    if ( a3 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 80LL))(v15, &v16);
      if ( v6 < 0 )
        goto LABEL_37;
      v6 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v16 + 56LL))(v16, &v22);
      if ( v6 < 0 )
        goto LABEL_37;
      v6 = StringCchPrintfW(v32, 0x10u, L"PT%dM", *a3);
      if ( v6 < 0 )
        goto LABEL_37;
      if ( CompareStringW(0x400u, 1u, v22, -1, v32, -1) == 2 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids);
        }
        goto LABEL_25;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v16 + 64LL))(v16, v32);
      v9 = 1;
    }
    if ( v6 >= 0 )
    {
LABEL_25:
      if ( v9 )
      {
        v26 = 0;
        v10 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v20 + 136LL);
        v29 = pvarg;
        v28 = pvarg;
        v27 = pvarg;
        v11 = v10(v20, L"Background Synchronization", v19);
        v6 = v11;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids, v11);
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
    }
LABEL_37:
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    SysFreeString((BSTR)v22);
    SysFreeString((BSTR)lpString1);
    goto LABEL_40;
  }
LABEL_47:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005a674  mov     [rsp-8+arg_0], rbx
0x18005a679  mov     [rsp-8+arg_8], rsi
0x18005a67e  push    rbp
0x18005a67f  push    rdi
0x18005a680  push    r12
0x18005a682  push    r14
0x18005a684  push    r15
0x18005a686  lea     rbp, [rsp-80h]
0x18005a68b  sub     rsp, 180h
0x18005a692  mov     rax, cs:__security_cookie
0x18005a699  xor     rax, rsp
0x18005a69c  mov     [rbp+0A0h+var_30], rax
0x18005a6a0  xor     r15d, r15d
0x18005a6a3  lea     rax, [rbp+0A0h+var_118]
0x18005a6a7  mov     rsi, r9
0x18005a6aa  mov     [rbp+0A0h+var_118], r15
0x18005a6ae  mov     r14, r8
0x18005a6b1  mov     [rsp+1A0h+ppv], rax; ppv
0x18005a6b6  lea     r9, IID_ITaskService; riid
0x18005a6bd  xor     edx, edx; pUnkOuter
0x18005a6bf  lea     r12d, [r15+1]
0x18005a6c3  mov     r8d, r12d; dwClsContext
0x18005a6c6  lea     rcx, CLSID_TaskScheduler; rclsid
0x18005a6cd  call    cs:__imp_CoCreateInstance
0x18005a6d3  lea     rdi, WPP_GLOBAL_Control
0x18005a6da  mov     ebx, eax
0x18005a6dc  test    eax, eax
0x18005a6de  js      loc_18005AC0D
0x18005a6e4  xorps   xmm0, xmm0
0x18005a6e7  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18005a6eb  xor     eax, eax
0x18005a6ed  movups  xmmword ptr [rbp+0A0h+pvarg], xmm0
0x18005a6f1  mov     qword ptr [rbp+0A0h+pvarg+10h], rax
0x18005a6f5  call    cs:__imp_VariantInit
0x18005a6fb  movsd   xmm0, qword ptr [rbp+0A0h+pvarg+10h]
0x18005a700  lea     rdx, [rbp+0A0h+String2]
0x18005a704  mov     rcx, [rbp+0A0h+var_118]
0x18005a708  lea     r9, [rbp+0A0h+var_D0]
0x18005a70c  mov     word ptr [rbp+0A0h+pvarg], r12w
0x18005a711  lea     r8, [rbp+0A0h+var_B0]
0x18005a715  mov     qword ptr [rbp+0A0h+pvarg+8], r15
0x18005a719  movups  xmm1, xmmword ptr [rbp+0A0h+pvarg]
0x18005a71d  mov     rax, [rcx]
0x18005a720  mov     [rsp+1A0h+ppv], rdx
0x18005a725  lea     rdx, [rbp+0A0h+var_90]
0x18005a729  movaps  xmmword ptr [rbp+0A0h+String2], xmm1
0x18005a72d  movsd   [rbp+0A0h+var_60], xmm0
0x18005a732  mov     rax, [rax+50h]
0x18005a736  movaps  [rbp+0A0h+var_D0], xmm1
0x18005a73a  movsd   [rbp+0A0h+var_C0], xmm0
0x18005a73f  movaps  [rbp+0A0h+var_B0], xmm1
0x18005a743  movsd   [rbp+0A0h+var_A0], xmm0
0x18005a748  movaps  [rbp+0A0h+var_90], xmm1
0x18005a74c  movsd   [rbp+0A0h+var_80], xmm0
0x18005a751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a756  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18005a75a  mov     ebx, eax
0x18005a75c  call    cs:__imp_VariantClear
0x18005a762  test    ebx, ebx
0x18005a764  js      loc_18005ABFD
0x18005a76a  mov     rcx, [rbp+0A0h+var_118]
0x18005a76e  lea     r8, [rbp+0A0h+var_120]
0x18005a772  mov     [rbp+0A0h+var_120], r15
0x18005a776  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Offline Files"
0x18005a77d  mov     rax, [rcx]
0x18005a780  mov     rax, [rax+38h]
0x18005a784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a789  mov     ebx, eax
0x18005a78b  test    eax, eax
0x18005a78d  js      loc_18005ABFD
0x18005a793  mov     rcx, [rbp+0A0h+var_120]
0x18005a797  lea     r8, [rbp+0A0h+var_100]
0x18005a79b  mov     [rbp+0A0h+var_100], r15
0x18005a79f  lea     rdx, aBackgroundSync; "Background Synchronization"
0x18005a7a6  mov     rax, [rcx]
0x18005a7a9  mov     rax, [rax+68h]
0x18005a7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7b2  mov     ebx, eax
0x18005a7b4  test    eax, eax
0x18005a7b6  js      loc_18005ABED
0x18005a7bc  mov     rcx, [rbp+0A0h+var_100]
0x18005a7c0  lea     rdx, [rsp+1A0h+var_128]
0x18005a7c5  mov     [rsp+1A0h+var_128], r15
0x18005a7ca  mov     rax, [rcx]
0x18005a7cd  mov     rax, [rax+98h]
0x18005a7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7d9  mov     ebx, eax
0x18005a7db  test    eax, eax
0x18005a7dd  js      loc_18005ABDD
0x18005a7e3  mov     rcx, [rsp+1A0h+var_128]
0x18005a7e8  lea     rdx, [rsp+1A0h+var_130]
0x18005a7ed  mov     [rsp+1A0h+var_130], r15
0x18005a7f2  mov     rax, [rcx]
0x18005a7f5  mov     rax, [rax+48h]
0x18005a7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7fe  mov     ebx, eax
0x18005a800  test    eax, eax
0x18005a802  js      loc_18005ABCC
0x18005a808  mov     rcx, [rsp+1A0h+var_130]
0x18005a80d  lea     rdx, [rsp+1A0h+var_150]
0x18005a812  mov     [rsp+1A0h+var_150], r15d
0x18005a817  mov     rax, [rcx]
0x18005a81a  mov     rax, [rax+38h]
0x18005a81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a823  mov     ebx, eax
0x18005a825  test    eax, eax
0x18005a827  js      loc_18005ABB6
0x18005a82d  cmp     [rsp+1A0h+var_150], r12d
0x18005a832  jnz     loc_18005ABBB
0x18005a838  mov     rcx, [rsp+1A0h+var_130]
0x18005a83d  lea     r8, [rsp+1A0h+var_138]
0x18005a842  mov     [rsp+1A0h+var_138], r15
0x18005a847  mov     edx, r12d
0x18005a84a  mov     rax, [rcx]
0x18005a84d  mov     rax, [rax+40h]
0x18005a851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a856  test    eax, eax
0x18005a858  js      loc_18005ABB6
0x18005a85e  mov     rcx, [rsp+1A0h+var_138]
0x18005a863  lea     rdx, [rsp+1A0h+var_14C]
0x18005a868  mov     [rsp+1A0h+var_14C], r15d
0x18005a86d  mov     rax, [rcx]
0x18005a870  mov     rax, [rax+38h]
0x18005a874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a879  mov     ebx, eax
0x18005a87b  test    eax, eax
0x18005a87d  js      loc_18005ABA3
0x18005a883  cmp     [rsp+1A0h+var_14C], r12d
0x18005a888  jnz     loc_18005ABA3
0x18005a88e  mov     rcx, [rsp+1A0h+var_138]
0x18005a893  lea     r8, [rsp+1A0h+var_148]
0x18005a898  mov     [rsp+1A0h+var_148], r15
0x18005a89d  lea     rdx, IID_ITimeTrigger
0x18005a8a4  mov     rax, [rcx]
0x18005a8a7  mov     rax, [rax]
0x18005a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8af  mov     ebx, eax
0x18005a8b1  test    eax, eax
0x18005a8b3  js      loc_18005ABA3
0x18005a8b9  mov     [rbp+0A0h+lpString1], r15
0x18005a8bd  mov     edi, r15d
0x18005a8c0  mov     [rbp+0A0h+var_110], r15
0x18005a8c4  mov     [rsp+1A0h+var_140], r15
0x18005a8c9  test    rsi, rsi
0x18005a8cc  jz      loc_18005A95A
0x18005a8d2  mov     r9d, [rsi]
0x18005a8d5  lea     r8, aPtDm; "PT%dM"
0x18005a8dc  lea     edx, [r15+10h]; unsigned __int64
0x18005a8e0  lea     rcx, [rbp+0A0h+String2]; unsigned __int16 *
0x18005a8e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a8e9  mov     ebx, eax
0x18005a8eb  test    eax, eax
0x18005a8ed  js      short loc_18005A95A
0x18005a8ef  mov     rcx, [rsp+1A0h+var_148]
0x18005a8f4  lea     rdx, [rbp+0A0h+lpString1]
0x18005a8f8  mov     rax, [rcx]
0x18005a8fb  mov     rax, [rax+0A0h]
0x18005a902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a907  mov     ebx, eax
0x18005a909  test    eax, eax
0x18005a90b  js      short loc_18005A95A
0x18005a90d  mov     r8, [rbp+0A0h+lpString1]; lpString1
0x18005a911  lea     rax, [rbp+0A0h+String2]
0x18005a915  mov     [rsp+1A0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005a91d  or      r9d, 0FFFFFFFFh; cchCount1
0x18005a921  mov     edx, r12d; dwCmpFlags
0x18005a924  mov     [rsp+1A0h+ppv], rax; lpString2
0x18005a929  mov     ecx, 400h; Locale
0x18005a92e  call    cs:__imp_CompareStringW
0x18005a934  cmp     eax, 2
0x18005a937  jz      loc_18005AAEC
0x18005a93d  mov     rcx, [rsp+1A0h+var_148]
0x18005a942  lea     rdx, [rbp+0A0h+String2]
0x18005a946  mov     rax, [rcx]
0x18005a949  mov     rax, [rax+0A8h]
0x18005a950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a955  mov     ebx, eax
0x18005a957  mov     edi, r12d
0x18005a95a  lea     rsi, WPP_GLOBAL_Control
0x18005a961  test    r14, r14
0x18005a964  jz      loc_18005AA15
0x18005a96a  mov     rcx, [rsp+1A0h+var_148]
0x18005a96f  lea     rdx, [rsp+1A0h+var_140]
0x18005a974  mov     rax, [rcx]
0x18005a977  mov     rax, [rax+50h]
0x18005a97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a980  mov     ebx, eax
0x18005a982  test    eax, eax
0x18005a984  js      loc_18005AB61
0x18005a98a  mov     rcx, [rsp+1A0h+var_140]
0x18005a98f  lea     rdx, [rbp+0A0h+var_110]
0x18005a993  mov     rax, [rcx]
0x18005a996  mov     rax, [rax+38h]
0x18005a99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a99f  mov     ebx, eax
0x18005a9a1  test    eax, eax
0x18005a9a3  js      loc_18005AB61
0x18005a9a9  mov     r9d, [r14]
0x18005a9ac  lea     r8, aPtDm; "PT%dM"
0x18005a9b3  mov     edx, 10h; unsigned __int64
0x18005a9b8  lea     rcx, [rbp+0A0h+var_50]; unsigned __int16 *
0x18005a9bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a9c1  mov     ebx, eax
0x18005a9c3  test    eax, eax
0x18005a9c5  js      loc_18005AB61
0x18005a9cb  mov     r8, [rbp+0A0h+var_110]; lpString1
0x18005a9cf  lea     rax, [rbp+0A0h+var_50]
0x18005a9d3  mov     [rsp+1A0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005a9db  or      r9d, 0FFFFFFFFh; cchCount1
0x18005a9df  mov     edx, r12d; dwCmpFlags
0x18005a9e2  mov     [rsp+1A0h+ppv], rax; lpString2
0x18005a9e7  mov     ecx, 400h; Locale
0x18005a9ec  call    cs:__imp_CompareStringW
0x18005a9f2  cmp     eax, 2
0x18005a9f5  jz      loc_18005AB2A
0x18005a9fb  mov     rcx, [rsp+1A0h+var_140]
0x18005aa00  lea     rdx, [rbp+0A0h+var_50]
0x18005aa04  mov     rax, [rcx]
0x18005aa07  mov     rax, [rax+40h]
0x18005aa0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa10  mov     ebx, eax
0x18005aa12  mov     edi, r12d
0x18005aa15  test    ebx, ebx
0x18005aa17  js      loc_18005AB61
0x18005aa1d  test    edi, edi
0x18005aa1f  jz      loc_18005AB61
0x18005aa25  movups  xmm1, xmmword ptr [rbp+0A0h+pvarg]
0x18005aa29  lea     r8, [rbp+0A0h+var_E0]
0x18005aa2d  mov     rcx, [rbp+0A0h+var_120]
0x18005aa31  movsd   xmm0, qword ptr [rbp+0A0h+pvarg+10h]
0x18005aa36  lea     rdx, aBackgroundSync; "Background Synchronization"
0x18005aa3d  mov     [rsp+1A0h+var_160], r8
0x18005aa42  mov     r9d, 4
0x18005aa48  lea     r8, [rbp+0A0h+var_90]
0x18005aa4c  mov     [rbp+0A0h+var_E0], r15
0x18005aa50  mov     rax, [rcx]
0x18005aa53  mov     [rsp+1A0h+var_168], r8
0x18005aa58  lea     r8, [rbp+0A0h+var_B0]
0x18005aa5c  mov     [rsp+1A0h+var_170], r9d
0x18005aa61  mov     qword ptr [rsp+1A0h+cchCount2], r8
0x18005aa66  lea     r8, [rbp+0A0h+var_D0]
0x18005aa6a  mov     rax, [rax+88h]
0x18005aa71  mov     [rsp+1A0h+ppv], r8
0x18005aa76  mov     r8, [rsp+1A0h+var_128]
0x18005aa7b  movaps  [rbp+0A0h+var_90], xmm1
0x18005aa7f  movsd   [rbp+0A0h+var_80], xmm0
0x18005aa84  movaps  [rbp+0A0h+var_B0], xmm1
0x18005aa88  movsd   [rbp+0A0h+var_A0], xmm0
0x18005aa8d  movaps  [rbp+0A0h+var_D0], xmm1
0x18005aa91  movsd   [rbp+0A0h+var_C0], xmm0
0x18005aa96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa9b  mov     ebx, eax
0x18005aa9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aaa4  lea     rdi, WPP_GLOBAL_Control
0x18005aaab  cmp     rcx, rdi
0x18005aaae  jz      short loc_18005AAD1
0x18005aab0  test    dword ptr [rcx+1Ch], 8000000h
0x18005aab7  jz      short loc_18005AAD1
0x18005aab9  mov     rcx, [rcx+10h]
0x18005aabd  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005aac4  mov     edx, 15h
0x18005aac9  mov     r9d, eax
0x18005aacc  call    WPP_SF_d
0x18005aad1  mov     rcx, [rbp+0A0h+var_E0]
0x18005aad5  test    rcx, rcx
0x18005aad8  jz      loc_18005AB68
0x18005aade  mov     rax, [rcx]
0x18005aae1  mov     rax, [rax+10h]
0x18005aae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aaea  jmp     short loc_18005AB68
0x18005aaec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aaf3  lea     rsi, WPP_GLOBAL_Control
0x18005aafa  cmp     rcx, rsi
0x18005aafd  jz      loc_18005A961
0x18005ab03  test    dword ptr [rcx+1Ch], 8000000h
0x18005ab0a  jz      loc_18005A961
0x18005ab10  mov     rcx, [rcx+10h]
0x18005ab14  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005ab1b  mov     edx, 13h
0x18005ab20  call    WPP_SF_
0x18005ab25  jmp     loc_18005A961
0x18005ab2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab31  cmp     rcx, rsi
0x18005ab34  jz      loc_18005AA1D
0x18005ab3a  test    dword ptr [rcx+1Ch], 8000000h
0x18005ab41  jz      loc_18005AA1D
0x18005ab47  mov     rcx, [rcx+10h]
0x18005ab4b  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005ab52  mov     edx, 14h
0x18005ab57  call    WPP_SF_
0x18005ab5c  jmp     loc_18005AA1D
0x18005ab61  lea     rdi, WPP_GLOBAL_Control
0x18005ab68  mov     rcx, [rsp+1A0h+var_140]
0x18005ab6d  test    rcx, rcx
0x18005ab70  jz      short loc_18005AB7E
0x18005ab72  mov     rax, [rcx]
0x18005ab75  mov     rax, [rax+10h]
0x18005ab79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab7e  mov     rcx, [rsp+1A0h+var_148]
0x18005ab83  mov     rax, [rcx]
  ... truncated ...
```
