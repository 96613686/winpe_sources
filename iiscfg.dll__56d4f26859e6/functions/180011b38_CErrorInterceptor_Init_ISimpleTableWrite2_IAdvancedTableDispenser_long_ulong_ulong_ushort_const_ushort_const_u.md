# CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)

- ea: `0x180011b38`
- end: `0x180012163`
- name: `?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z`
- size: `1579`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `26`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800043f0`
- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`
- `0x180009acc`
- `0x180009e84`
- `0x18000a1c8`
- `0x18000a9b4`
- `0x18000ce00`
- `0x18000d110`
- `0x180015f34`
- `0x180017e84`
- `0x180019128`
- `0x1800199c8`
- `0x180019f9c`
- `0x18001b188`
- `0x18001b82c`
- `0x18001bd60`
- `0x18001c86c`
- `0x18001d2a0`
- `0x18001d604`
- `0x18001da08`
- `0x18001dd08`
- `0x1800234ac`
- `0x180028868`
- `0x18002ea35`

## callees

- `0x180011b38`
- `0x18001216c`
- `0x180012304`
- `0x18001250c`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180011dfb`
- `msvcrt!wcscat_s` at `0x180011dfb`
- `msvcrt!wcsncpy_s` at `0x180011f0b`
- `msvcrt!wcsncpy_s` at `0x180011f49`
- `msvcrt!wcsncpy_s` at `0x180011f8b`
- `msvcrt!wcsncpy_s` at `0x180011fcd`
- `msvcrt!wcsncpy_s` at `0x180011f0b`
- `msvcrt!wcsncpy_s` at `0x180011f49`
- `msvcrt!wcsncpy_s` at `0x180011f8b`
- `msvcrt!wcsncpy_s` at `0x180011fcd`
- `msvcrt!wcscpy_s` at `0x180011de5`
- `msvcrt!wcscpy_s` at `0x180011de5`
- `KERNEL32!GetSystemTime` at `0x180011ce3`
- `KERNEL32!GetSystemTime` at `0x180011ce3`
- `KERNEL32!GetComputerNameW` at `0x180011e9b`
- `KERNEL32!GetComputerNameW` at `0x180011e9b`
- `KERNEL32!GetDateFormatW` at `0x180011d5b`
- `KERNEL32!GetDateFormatW` at `0x180011d5b`
- `KERNEL32!GetModuleFileNameW` at `0x180011d0e`
- `KERNEL32!GetModuleFileNameW` at `0x180011d0e`
- `KERNEL32!GetTimeFormatW` at `0x180011d9e`
- `KERNEL32!GetTimeFormatW` at `0x180011d9e`
- `ole32!CoTaskMemAlloc` at `0x180011b8f`
- `ole32!CoTaskMemAlloc` at `0x180011b8f`
- `ADVAPI32!GetUserNameW` at `0x180011e6a`
- `ADVAPI32!GetUserNameW` at `0x180011e6a`

## string_xrefs

- `0x180011def`: ` Config`

## pseudocode

```c
_QWORD *__fastcall CErrorInterceptor::Init(
        CErrorInterceptor *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        const wchar_t *a7,
        const wchar_t *a8,
        const wchar_t *a9,
        const wchar_t *a10,
        int a11,
        __int64 a12,
        int a13,
        int a14,
        int a15,
        __int64 a16,
        int a17,
        __int64 a18,
        __int64 a19,
        int a20,
        int a21)
{
  const wchar_t *v22; // r13
  const wchar_t *v23; // r12
  unsigned __int64 v26; // r15
  _QWORD *result; // rax
  _QWORD *v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // rcx
  const wchar_t *v31; // r8
  int v32; // eax
  WCHAR *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  const wchar_t *v37; // rax
  const wchar_t *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  DWORD pcbBuffer; // [rsp+50h] [rbp-30h] BYREF
  const wchar_t *v53; // [rsp+58h] [rbp-28h]
  const wchar_t *v54; // [rsp+60h] [rbp-20h]
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-18h] BYREF

  v22 = a8;
  v23 = a7;
  v54 = a10;
  v53 = a9;
  v26 = a4;
  result = CoTaskMemAlloc(0x5E38u);
  v28 = result;
  if ( result )
  {
    result[35] = 0;
    result[37] = 0;
    result = memset_0(result + 2, 0, 0xE8u);
  }
  else
  {
    v28 = 0;
  }
  *((_QWORD *)a1 + 1) = v28;
  if ( !v28 )
  {
    *(_DWORD *)a1 = -2147024882;
    return result;
  }
  v28[35] = 0;
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 288LL) = 0;
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 296LL) = 0;
  *(_DWORD *)a1 = 0;
  if ( !a2 )
    goto LABEL_13;
  if ( *a2 )
  {
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 288LL) = *a2;
  }
  else
  {
    result = (_QWORD *)(*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, int, int, __int64))(*(_QWORD *)a3 + 24LL))(
                         a3,
                         L"ERRORS",
                         L"DETAILEDERRORS",
                         0,
                         0,
                         3,
                         16,
                         *((_QWORD *)a1 + 1) + 288LL);
    *(_DWORD *)a1 = (_DWORD)result;
    if ( (int)result < 0 )
      return result;
    *a2 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 288LL);
  }
  result = (_QWORD *)(***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*((_QWORD *)a1 + 1) + 288LL))(
                       *(_QWORD *)(*((_QWORD *)a1 + 1) + 288LL),
                       &IID_ISimpleTableController,
                       *((_QWORD *)a1 + 1) + 296LL);
  *(_DWORD *)a1 = (_DWORD)result;
  if ( (int)result >= 0 )
  {
    result = (_QWORD *)(***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*((_QWORD *)a1 + 1) + 288LL))(
                         *(_QWORD *)(*((_QWORD *)a1 + 1) + 288LL),
                         &IID_ISimpleTableController,
                         *((_QWORD *)a1 + 1) + 280LL);
    *(_DWORD *)a1 = (_DWORD)result;
    if ( (int)result >= 0 )
    {
LABEL_13:
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      *(_WORD *)(*((_QWORD *)a1 + 1) + 12340LL) = 0;
      GetModuleFileNameW(g_hModule, (LPWSTR)(*((_QWORD *)a1 + 1) + 12340LL), 0x100u);
      *(_WORD *)(*((_QWORD *)a1 + 1) + 12850LL) = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 48LL) = *((_QWORD *)a1 + 1) + 12340LL;
      CErrorInterceptor::SetErrorID(a1, &SystemTime);
      if ( GetDateFormatW(0, 0x80000001, &SystemTime, 0, (LPWSTR)(*((_QWORD *)a1 + 1) + 948LL), 256) )
        v29 = *((_QWORD *)a1 + 1) + 948LL;
      else
        v29 = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 32LL) = v29;
      if ( GetTimeFormatW(0, 0x80000000, &SystemTime, 0, (LPWSTR)(*((_QWORD *)a1 + 1) + 23092LL), 256) )
        v30 = *((_QWORD *)a1 + 1) + 23092LL;
      else
        v30 = 0;
      v31 = g_wszDefaultProduct;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 40LL) = v30;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 272LL) = a3;
      wcscpy_s((wchar_t *)(*((_QWORD *)a1 + 1) + 12212LL), 0x40u, v31);
      wcscat_s((wchar_t *)(*((_QWORD *)a1 + 1) + 12212LL), 0x40u, L" Config");
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 72LL) = *((_QWORD *)a1 + 1) + 12212LL;
      v32 = a17;
      if ( !a17 )
        v32 = *((_DWORD *)qword_1800342F8 + (v26 >> 30));
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 24116LL) = v32;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 80LL) = *((_QWORD *)a1 + 1) + 24116LL;
      CErrorInterceptor::SetCategory(a1, a5);
      v33 = (WCHAR *)(*((_QWORD *)a1 + 1) + 23604LL);
      pcbBuffer = 256;
      if ( GetUserNameW(v33, &pcbBuffer) )
        v34 = *((_QWORD *)a1 + 1) + 23604LL;
      else
        v34 = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL) = v34;
      v35 = *((_QWORD *)a1 + 1);
      pcbBuffer = 256;
      if ( GetComputerNameW((LPWSTR)(v35 + 436), &pcbBuffer) )
        v36 = *((_QWORD *)a1 + 1) + 436LL;
      else
        v36 = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL) = v36;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 112LL) = 0;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 248LL) = a6;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 120LL) = *((_QWORD *)a1 + 1) + 248LL;
      CErrorInterceptor::SetMessageString(a1);
      if ( !a7 )
        v23 = &word_180034198;
      wcsncpy_s((wchar_t *)(*((_QWORD *)a1 + 1) + 12852LL), 0x400u, v23, 0x400u);
      if ( !a8 )
        v22 = &word_180034198;
      *(_WORD *)(*((_QWORD *)a1 + 1) + 14898LL) = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 128LL) = *((_QWORD *)a1 + 1) + 12852LL;
      wcsncpy_s((wchar_t *)(*((_QWORD *)a1 + 1) + 14900LL), 0x400u, v22, 0x400u);
      *(_WORD *)(*((_QWORD *)a1 + 1) + 16946LL) = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 136LL) = *((_QWORD *)a1 + 1) + 14900LL;
      v37 = v53;
      if ( !v53 )
        v37 = &word_180034198;
      wcsncpy_s((wchar_t *)(*((_QWORD *)a1 + 1) + 16948LL), 0x400u, v37, 0x400u);
      *(_WORD *)(*((_QWORD *)a1 + 1) + 18994LL) = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 144LL) = *((_QWORD *)a1 + 1) + 16948LL;
      v38 = v54;
      if ( !v54 )
        v38 = &word_180034198;
      wcsncpy_s((wchar_t *)(*((_QWORD *)a1 + 1) + 18996LL), 0x400u, v38, 0x400u);
      *(_WORD *)(*((_QWORD *)a1 + 1) + 21042LL) = 0;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 152LL) = *((_QWORD *)a1 + 1) + 18996LL;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 8LL) = v26;
      v39 = 0;
      v40 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v40 + 8) )
        v39 = v40 + 8;
      *(_QWORD *)(v40 + 168) = v39;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 252LL) = a11;
      v41 = *((_QWORD *)a1 + 1);
      v42 = 0;
      if ( *(_DWORD *)(v41 + 252) )
        v42 = v41 + 252;
      *(_QWORD *)(v41 + 176) = v42;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 264LL) = a13;
      v43 = 0;
      v44 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v44 + 264) )
        v43 = v44 + 264;
      *(_QWORD *)(v44 + 192) = v43;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 200LL) = a12;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 208LL) = a16;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 304LL) = a14;
      v45 = 0;
      v46 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v46 + 304) != -1 )
        v45 = v46 + 304;
      *(_QWORD *)(v46 + 216) = v45;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL) = a15;
      v47 = 0;
      v48 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v48 + 4) != -1 )
        v47 = v48 + 4;
      *(_QWORD *)(v48 + 224) = v47;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 256LL) = a20;
      v49 = 0;
      v50 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v50 + 256) != -1 )
        v49 = v50 + 256;
      *(_QWORD *)(v50 + 232) = v49;
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 260LL) = a21;
      result = 0;
      v51 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v51 + 260) != -1 )
        result = (_QWORD *)(v51 + 260);
      *(_QWORD *)(v51 + 240) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011b38  mov     [rsp-38h+arg_18], rbx
0x180011b3d  push    rbp
0x180011b3e  push    rsi
0x180011b3f  push    rdi
0x180011b40  push    r12
0x180011b42  push    r13
0x180011b44  push    r14
0x180011b46  push    r15
0x180011b48  mov     rbp, rsp
0x180011b4b  sub     rsp, 80h
0x180011b52  mov     rax, cs:__security_cookie
0x180011b59  xor     rax, rsp
0x180011b5c  mov     [rbp+var_8], rax
0x180011b60  mov     rax, [rbp+arg_48]
0x180011b67  mov     rbx, rcx
0x180011b6a  mov     r13, [rbp+arg_38]
0x180011b6e  mov     ecx, 5E38h; cb
0x180011b73  mov     r12, [rbp+arg_30]
0x180011b77  mov     r14, r8
0x180011b7a  mov     [rbp+var_20], rax
0x180011b7e  mov     rsi, rdx
0x180011b81  mov     rax, [rbp+arg_40]
0x180011b88  mov     [rbp+var_28], rax
0x180011b8c  mov     r15d, r9d
0x180011b8f  call    cs:__imp_CoTaskMemAlloc
0x180011b95  mov     rdi, rax
0x180011b98  test    rax, rax
0x180011b9b  jz      short loc_180011BC6
0x180011b9d  lea     rcx, [rax+10h]; void *
0x180011ba1  mov     qword ptr [rax+118h], 0
0x180011bac  xor     edx, edx; Val
0x180011bae  mov     qword ptr [rax+128h], 0
0x180011bb9  mov     r8d, 0E8h; Size
0x180011bbf  call    memset_0
0x180011bc4  jmp     short loc_180011BC8
0x180011bc6  xor     edi, edi
0x180011bc8  mov     [rbx+8], rdi
0x180011bcc  test    rdi, rdi
0x180011bcf  jnz     short loc_180011BDC
0x180011bd1  mov     dword ptr [rbx], 8007000Eh
0x180011bd7  jmp     loc_18001213C
0x180011bdc  mov     qword ptr [rdi+118h], 0
0x180011be7  xor     edi, edi
0x180011be9  mov     rax, [rbx+8]
0x180011bed  mov     [rax+120h], rdi
0x180011bf4  mov     rax, [rbx+8]
0x180011bf8  mov     [rax+128h], rdi
0x180011bff  mov     [rbx], edi
0x180011c01  test    rsi, rsi
0x180011c04  jz      loc_180011CD8
0x180011c0a  mov     rcx, [rsi]
0x180011c0d  test    rcx, rcx
0x180011c10  jnz     short loc_180011C71
0x180011c12  mov     rcx, [rbx+8]
0x180011c16  lea     r8, aDetailederrors; "DETAILEDERRORS"
0x180011c1d  mov     rax, [r14]
0x180011c20  lea     rdx, aErrors; "ERRORS"
0x180011c27  add     rcx, 120h
0x180011c2e  xor     r9d, r9d
0x180011c31  mov     [rsp+80h+var_48], rcx
0x180011c36  mov     rcx, r14
0x180011c39  mov     [rsp+80h+var_50], 10h
0x180011c41  mov     rax, [rax+18h]
0x180011c45  mov     [rsp+80h+cchDate], 3
0x180011c4d  mov     [rsp+80h+lpDateStr], rdi
0x180011c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c57  mov     [rbx], eax
0x180011c59  test    eax, eax
0x180011c5b  js      loc_18001213C
0x180011c61  mov     rax, [rbx+8]
0x180011c65  mov     rcx, [rax+120h]
0x180011c6c  mov     [rsi], rcx
0x180011c6f  jmp     short loc_180011C7C
0x180011c71  mov     rax, [rbx+8]
0x180011c75  mov     [rax+120h], rcx
0x180011c7c  mov     r8, [rbx+8]
0x180011c80  lea     rdx, IID_ISimpleTableController
0x180011c87  mov     rcx, [r8+120h]
0x180011c8e  add     r8, 128h
0x180011c95  mov     rax, [rcx]
0x180011c98  mov     rax, [rax]
0x180011c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca0  mov     [rbx], eax
0x180011ca2  test    eax, eax
0x180011ca4  js      loc_18001213C
0x180011caa  mov     r8, [rbx+8]
0x180011cae  lea     rdx, IID_ISimpleTableController
0x180011cb5  mov     rcx, [r8+120h]
0x180011cbc  add     r8, 118h
0x180011cc3  mov     rax, [rcx]
0x180011cc6  mov     rax, [rax]
0x180011cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cce  mov     [rbx], eax
0x180011cd0  test    eax, eax
0x180011cd2  js      loc_18001213C
0x180011cd8  xorps   xmm0, xmm0
0x180011cdb  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180011cdf  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180011ce3  call    cs:__imp_GetSystemTime
0x180011ce9  mov     rcx, [rbx+8]
0x180011ced  mov     esi, 100h
0x180011cf2  mov     r8d, esi; nSize
0x180011cf5  mov     [rcx+3034h], di
0x180011cfc  mov     rdx, [rbx+8]
0x180011d00  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180011d07  add     rdx, 3034h; lpFilename
0x180011d0e  call    cs:__imp_GetModuleFileNameW
0x180011d14  mov     rcx, [rbx+8]
0x180011d18  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180011d1c  mov     [rcx+3232h], di
0x180011d23  mov     rcx, [rbx+8]
0x180011d27  lea     rax, [rcx+3034h]
0x180011d2e  mov     [rcx+30h], rax
0x180011d32  mov     rcx, rbx; this
0x180011d35  call    ?SetErrorID@CErrorInterceptor@@AEAAXAEAU_SYSTEMTIME@@@Z; CErrorInterceptor::SetErrorID(_SYSTEMTIME &)
0x180011d3a  mov     rax, [rbx+8]
0x180011d3e  lea     r8, [rbp+SystemTime]; lpDate
0x180011d42  add     rax, 3B4h
0x180011d48  mov     [rsp+80h+cchDate], esi; cchDate
0x180011d4c  xor     r9d, r9d; lpFormat
0x180011d4f  mov     [rsp+80h+lpDateStr], rax; lpDateStr
0x180011d54  mov     edx, 80000001h; dwFlags
0x180011d59  xor     ecx, ecx; Locale
0x180011d5b  call    cs:__imp_GetDateFormatW
0x180011d61  test    eax, eax
0x180011d63  jz      short loc_180011D72
0x180011d65  mov     rcx, [rbx+8]
0x180011d69  add     rcx, 3B4h
0x180011d70  jmp     short loc_180011D75
0x180011d72  mov     rcx, rdi
0x180011d75  mov     rax, [rbx+8]
0x180011d79  lea     r8, [rbp+SystemTime]; lpTime
0x180011d7d  mov     [rsp+80h+cchDate], esi; cchTime
0x180011d81  xor     r9d, r9d; lpFormat
0x180011d84  mov     edx, 80000000h; dwFlags
0x180011d89  mov     [rax+20h], rcx
0x180011d8d  xor     ecx, ecx; Locale
0x180011d8f  mov     rax, [rbx+8]
0x180011d93  add     rax, 5A34h
0x180011d99  mov     [rsp+80h+lpDateStr], rax; lpTimeStr
0x180011d9e  call    cs:__imp_GetTimeFormatW
0x180011da4  test    eax, eax
0x180011da6  jz      short loc_180011DB5
0x180011da8  mov     rcx, [rbx+8]
0x180011dac  add     rcx, 5A34h
0x180011db3  jmp     short loc_180011DB8
0x180011db5  mov     rcx, rdi
0x180011db8  mov     rax, [rbx+8]
0x180011dbc  mov     esi, 2FB4h
0x180011dc1  mov     r8, cs:?g_wszDefaultProduct@@3PEAGEA; Source
0x180011dc8  mov     edi, 40h ; '@'
0x180011dcd  mov     edx, edi; SizeInWords
0x180011dcf  mov     [rax+28h], rcx
0x180011dd3  mov     rax, [rbx+8]
0x180011dd7  mov     [rax+110h], r14
0x180011dde  mov     rcx, [rbx+8]
0x180011de2  add     rcx, rsi; Destination
0x180011de5  call    cs:__imp_wcscpy_s
0x180011deb  mov     rcx, [rbx+8]
0x180011def  lea     r8, aConfig; " Config"
0x180011df6  add     rcx, rsi; Destination
0x180011df9  mov     edx, edi; SizeInWords
0x180011dfb  call    cs:__imp_wcscat_s
0x180011e01  mov     rcx, [rbx+8]
0x180011e05  xor     r14d, r14d
0x180011e08  lea     rax, [rcx+2FB4h]
0x180011e0f  mov     [rcx+48h], rax
0x180011e13  mov     eax, [rbp+arg_80]
0x180011e19  mov     rcx, [rbx+8]
0x180011e1d  test    eax, eax
0x180011e1f  jnz     short loc_180011E32
0x180011e21  mov     rax, r15
0x180011e24  lea     rdx, qword_1800342F8
0x180011e2b  shr     rax, 1Eh
0x180011e2f  mov     eax, [rdx+rax*4]
0x180011e32  mov     edx, [rbp+arg_20]; unsigned int
0x180011e35  mov     [rcx+5E34h], eax
0x180011e3b  mov     rcx, [rbx+8]
0x180011e3f  lea     rax, [rcx+5E34h]
0x180011e46  mov     [rcx+50h], rax
0x180011e4a  mov     rcx, rbx; this
0x180011e4d  call    ?SetCategory@CErrorInterceptor@@AEAAXK@Z; CErrorInterceptor::SetCategory(ulong)
0x180011e52  mov     rcx, [rbx+8]
0x180011e56  lea     rdx, [rbp+pcbBuffer]; pcbBuffer
0x180011e5a  mov     esi, 5C34h
0x180011e5f  mov     edi, 100h
0x180011e64  add     rcx, rsi; lpBuffer
0x180011e67  mov     [rbp+pcbBuffer], edi
0x180011e6a  call    cs:__imp_GetUserNameW
0x180011e70  test    eax, eax
0x180011e72  jz      short loc_180011E7D
0x180011e74  mov     rcx, [rbx+8]
0x180011e78  add     rcx, rsi
0x180011e7b  jmp     short loc_180011E80
0x180011e7d  mov     rcx, r14
0x180011e80  mov     rax, [rbx+8]
0x180011e84  lea     rdx, [rbp+pcbBuffer]; nSize
0x180011e88  mov     [rax+60h], rcx
0x180011e8c  mov     rcx, [rbx+8]
0x180011e90  mov     [rbp+pcbBuffer], edi
0x180011e93  mov     edi, 1B4h
0x180011e98  add     rcx, rdi; lpBuffer
0x180011e9b  call    cs:__imp_GetComputerNameW
0x180011ea1  test    eax, eax
0x180011ea3  jz      short loc_180011EAE
0x180011ea5  mov     rcx, [rbx+8]
0x180011ea9  add     rcx, rdi
0x180011eac  jmp     short loc_180011EB1
0x180011eae  mov     rcx, r14
0x180011eb1  mov     rax, [rbx+8]
0x180011eb5  mov     [rax+68h], rcx
0x180011eb9  mov     rax, [rbx+8]
0x180011ebd  mov     [rax+70h], r14
0x180011ec1  mov     rcx, [rbx+8]
0x180011ec5  mov     eax, [rbp+arg_28]
0x180011ec8  mov     [rcx+0F8h], eax
0x180011ece  mov     rcx, [rbx+8]
0x180011ed2  lea     rax, [rcx+0F8h]
0x180011ed9  mov     [rcx+78h], rax
0x180011edd  mov     rcx, rbx; this
0x180011ee0  call    ?SetMessageString@CErrorInterceptor@@AEAAXXZ; CErrorInterceptor::SetMessageString(void)
0x180011ee5  mov     rcx, [rbx+8]
0x180011ee9  lea     rsi, word_180034198
0x180011ef0  mov     edi, 400h
0x180011ef5  test    r12, r12
0x180011ef8  mov     r9d, edi; MaxCount
0x180011efb  mov     edx, edi; SizeInWords
0x180011efd  cmovz   r12, rsi
0x180011f01  add     rcx, 3234h; Destination
0x180011f08  mov     r8, r12; Source
0x180011f0b  call    cs:__imp_wcsncpy_s
0x180011f11  mov     rcx, [rbx+8]
0x180011f15  test    r13, r13
0x180011f18  mov     r9d, edi; MaxCount
0x180011f1b  mov     edx, edi; SizeInWords
0x180011f1d  cmovz   r13, rsi
0x180011f21  mov     r8, r13; Source
0x180011f24  mov     [rcx+3A32h], r14w
0x180011f2c  mov     rcx, [rbx+8]
0x180011f30  lea     rax, [rcx+3234h]
0x180011f37  mov     [rcx+80h], rax
0x180011f3e  mov     rcx, [rbx+8]
0x180011f42  add     rcx, 3A34h; Destination
0x180011f49  call    cs:__imp_wcsncpy_s
0x180011f4f  mov     rcx, [rbx+8]
0x180011f53  mov     r9d, edi; MaxCount
0x180011f56  mov     edx, edi; SizeInWords
0x180011f58  mov     [rcx+4232h], r14w
0x180011f60  mov     rcx, [rbx+8]
0x180011f64  lea     rax, [rcx+3A34h]
0x180011f6b  mov     [rcx+88h], rax
0x180011f72  mov     rax, [rbp+var_28]
0x180011f76  mov     rcx, [rbx+8]
0x180011f7a  test    rax, rax
0x180011f7d  cmovz   rax, rsi
0x180011f81  add     rcx, 4234h; Destination
0x180011f88  mov     r8, rax; Source
0x180011f8b  call    cs:__imp_wcsncpy_s
0x180011f91  mov     rcx, [rbx+8]
0x180011f95  mov     r9d, edi; MaxCount
0x180011f98  mov     edx, edi; SizeInWords
0x180011f9a  mov     [rcx+4A32h], r14w
0x180011fa2  mov     rcx, [rbx+8]
0x180011fa6  lea     rax, [rcx+4234h]
0x180011fad  mov     [rcx+90h], rax
0x180011fb4  mov     rax, [rbp+var_20]
0x180011fb8  mov     rcx, [rbx+8]
0x180011fbc  test    rax, rax
0x180011fbf  cmovz   rax, rsi
0x180011fc3  add     rcx, 4A34h; Destination
0x180011fca  mov     r8, rax; Source
0x180011fcd  call    cs:__imp_wcsncpy_s
0x180011fd3  mov     rcx, [rbx+8]
0x180011fd7  mov     [rcx+5232h], r14w
0x180011fdf  mov     rcx, [rbx+8]
0x180011fe3  lea     rax, [rcx+4A34h]
0x180011fea  mov     [rcx+98h], rax
0x180011ff1  mov     rax, [rbx+8]
0x180011ff5  mov     [rax+8], r15d
0x180011ff9  mov     rax, r14
0x180011ffc  mov     rdx, [rbx+8]
0x180012000  lea     rcx, [rdx+8]
0x180012004  cmp     [rcx], r14d
0x180012007  cmovnz  rax, rcx
0x18001200b  mov     [rdx+0A8h], rax
0x180012012  mov     rcx, [rbx+8]
0x180012016  mov     eax, [rbp+arg_50]
0x18001201c  mov     [rcx+0FCh], eax
0x180012022  mov     rdx, [rbx+8]
0x180012026  lea     rcx, [rdx+0FCh]
0x18001202d  cmp     [rcx], r14d
0x180012030  mov     rax, r14
0x180012033  cmovnz  rax, rcx
0x180012037  mov     [rdx+0B0h], rax
0x18001203e  mov     rcx, [rbx+8]
0x180012042  mov     eax, [rbp+arg_60]
0x180012048  mov     [rcx+108h], eax
0x18001204e  mov     rax, r14
0x180012051  mov     rdx, [rbx+8]
0x180012055  lea     rcx, [rdx+108h]
  ... truncated ...
```
