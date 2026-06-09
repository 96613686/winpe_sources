# GetSizeOfInterfaceConfig

- ea: `0x18001e94c`
- end: `0x18001f16a`
- name: `GetSizeOfInterfaceConfig`
- size: `2078`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800263b8`
- `0x18003cce8`

## callees

- `0x180011790`
- `0x18001e94c`
- `0x180040f8c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001ede7`
- `ntdll!RtlReleaseResource` at `0x18001edf9`
- `ntdll!RtlReleaseResource` at `0x18001ede7`
- `ntdll!RtlReleaseResource` at `0x18001edf9`
- `ntdll!RtlAcquireResourceShared` at `0x18001ec21`
- `ntdll!RtlAcquireResourceShared` at `0x18001ec21`

## string_xrefs

- `0x18001ea26`: `Entered: GetSizeOfInterfaceConfig`
- `0x18001f0db`: `GetSizeOfInterfaceConfig: Error %d in multiplication in getting the size to hold the routes \n`
- `0x18001f0c8`: `GetSizeOfInterfaceConfig: Error %d in addition \n`
- `0x18001eba1`: `GetSizeOfInterfaceConfig: Error %d in addition for router discovery info\n`
- `0x18001f0b5`: `GetSizeOfInterfaceConfig: Error %d in in addition for interface status info \n`
- `0x18001eb30`: `GetSizeOfInterfaceConfig: Error %d in GetIfInfo for %hs\n`
- `0x18001ebdd`: `GetSizeOfInterfaceConfig: Error %d in addition  \n`
- `0x18001ed27`: `GetSizeOfInterfaceConfig: Error %d in addition  \n`
- `0x18001ed82`: `GetSizeOfInterfaceConfig: Error %d in addition  \n`
- `0x18001ec96`: `GetSizeOfInterfaceConfig: Error %d in GetIfInfo for %ws\n`
- `0x18001ee47`: `GetSizeOfInterfaceConfig: Error %d in Multiplication for inbound filters \n`
- `0x18001eec9`: `GetSizeOfInterfaceConfig: Error %d in addition for inbound filters  \n`
- `0x18001ef0f`: `GetSizeOfInterfaceConfig: Error %d in addition for inbound filters  \n`
- `0x18001ef3f`: `GetSizeOfInterfaceConfig: Error %d in Multiplication for outbound filters \n`
- `0x18001ef6c`: `GetSizeOfInterfaceConfig: Error %d in addition for outbound filters \n`
- `0x18001efc2`: `GetSizeOfInterfaceConfig: Error %d in addition for outbound filters\n`
- `0x18001efee`: `GetSizeOfInterfaceConfig: Error %d in Multiplication for Demand-dial filters \n`
- `0x18001f06e`: `GetSizeOfInterfaceConfig: Error %d in addition for Demand-dial filters  \n`
- `0x18001f09d`: `GetSizeOfInterfaceConfig: Error %d in addition for Demand-dial filters \n`

## pseudocode

```c
__int64 __fastcall GetSizeOfInterfaceConfig(__int64 a1, unsigned int *a2)
{
  int v2; // ebx
  __int64 *v3; // rax
  unsigned int v5; // r13d
  __int128 *v7; // r9
  int v9; // esi
  unsigned __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // r15d
  unsigned int i; // r12d
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *); // rax
  unsigned int v15; // eax
  __int128 *v16; // r9
  const wchar_t *v17; // rdx
  unsigned int v18; // ecx
  const wchar_t *v19; // rdx
  __int64 *j; // r12
  unsigned int v21; // eax
  __int128 *v22; // r9
  unsigned int v23; // ecx
  __int128 *v24; // r9
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // r12d
  const wchar_t *v30; // rdx
  __int128 *v31; // r9
  unsigned int v32; // edx
  int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // edx
  int v39; // ecx
  unsigned int v40; // ecx
  __int64 v41; // rax
  __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned int v44; // eax
  unsigned int v45; // r15d
  const wchar_t *v46; // rdx
  __int128 *v47; // r9
  unsigned int v48; // edx
  __int128 *v49; // r9
  unsigned int v50; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v51; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v52; // [rsp+48h] [rbp-B8h]
  int v53; // [rsp+4Ch] [rbp-B4h] BYREF
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+54h] [rbp-ACh] BYREF
  __int64 *v56; // [rsp+58h] [rbp-A8h]
  unsigned int *v57; // [rsp+68h] [rbp-98h]
  __int128 v58; // [rsp+70h] [rbp-90h] BYREF
  int v59; // [rsp+80h] [rbp-80h] BYREF
  __int128 v60; // [rsp+84h] [rbp-7Ch]
  __int128 v61; // [rsp+94h] [rbp-6Ch]
  int v62; // [rsp+A4h] [rbp-5Ch]
  int v63; // [rsp+B0h] [rbp-50h] BYREF
  char v64[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v2 = *(_DWORD *)(a1 + 516);
  v3 = &g_rgicInfoCbv4;
  v57 = a2;
  v51 = 0;
  v50 = 0;
  v54 = 0;
  if ( v2 != 1 )
    v3 = &g_rgicInfoCbv6;
  v55 = 0;
  v56 = v3;
  v5 = 5;
  v53 = 0;
  if ( v2 != 1 )
    v5 = 3;
  v63 = 0;
  v52 = v5;
  memset_0(v64, 0, sizeof(v64));
  v59 = 0;
  v60 = 0;
  v62 = 0;
  v61 = 0;
  v58 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v59) = 0;
    v7 = &v58;
    if ( a1 != -688 )
      LODWORD(v7) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: GetSizeOfInterfaceConfig",
      (_DWORD)v7,
      *(_QWORD *)(a1 + 72),
      (__int64)&v59);
  }
  if ( !a2 )
    return 87;
  v9 = -1;
  v10 = 72LL * (unsigned int)GetNumStaticRoutes(a1);
  if ( v10 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 2147942934LL;
    v17 = L"GetSizeOfInterfaceConfig: Error %d in multiplication in getting the size to hold the routes \n";
LABEL_135:
    LOWORD(v63) = 0;
    LOWORD(v59) = 0;
    FormatRRASErrorString(&v63, v17, 2147942934LL);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
LABEL_136:
      v49 = &v58;
      if ( a1 != -688 )
        LODWORD(v49) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v63,
        (_DWORD)v49,
        *(_QWORD *)(a1 + 72),
        (__int64)&v59);
      return 2147942934LL;
    }
    return 2147942934LL;
  }
  if ( (int)v10 + 24 < (unsigned int)v10 || (v11 = v10 + 36, (unsigned int)(v10 + 36) < 0xC) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 2147942934LL;
    v17 = L"GetSizeOfInterfaceConfig: Error %d in addition \n";
    goto LABEL_135;
  }
  if ( v2 )
  {
    if ( (int)v10 + 76 < (unsigned int)(v10 + 36) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return 2147942934LL;
      v17 = L"GetSizeOfInterfaceConfig: Error %d in addition for router discovery info\n";
      goto LABEL_135;
    }
    v11 = v10 + 76;
  }
  v12 = v11 + 28;
  if ( v11 + 28 < v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 2147942934LL;
    v17 = L"GetSizeOfInterfaceConfig: Error %d in in addition for interface status info \n";
    goto LABEL_135;
  }
  for ( i = 0; i < v5; ++i )
  {
    v14 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))v56[5 * i + 1];
    if ( v14 )
    {
      v50 = 0;
      v15 = v14(a1, 0, 0, 0, 0, &v50);
      if ( !v15 || v15 == 122 )
      {
        v18 = v50 + 24;
        if ( v50 + 24 < v50 || v18 + v12 < v12 )
          goto LABEL_34;
        v12 += v18;
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v63) = 0;
        LOWORD(v59) = 0;
        FormatRRASErrorString(&v63, L"GetSizeOfInterfaceConfig: Error %d in GetIfInfo for %hs\n", v15, v56[5 * i]);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = &v58;
          if ( a1 != -688 )
            LODWORD(v16) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v63,
            (_DWORD)v16,
            *(_QWORD *)(a1 + 72),
            (__int64)&v59);
        }
      }
    }
    v5 = v52;
  }
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  for ( j = *(__int64 **)(a1 + 56); j != (__int64 *)(a1 + 56); j = (__int64 *)*j )
  {
    if ( !*((_DWORD *)j + 4) )
    {
      v51 = 0;
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, int *, int *, int *))(j[3] + 152))(
              *(unsigned int *)(a1 + 16),
              0,
              &v51,
              &v55,
              &v54,
              &v53);
      if ( !v21 || v21 == 122 )
      {
        v23 = v51 + 24;
        if ( v51 + 24 < v51 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v63) = 0;
            LOWORD(v59) = 0;
            FormatRRASErrorString(&v63, L"GetSizeOfInterfaceConfig: Error %d in addition  \n", 2147942934LL);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v24 = &v58;
              if ( a1 != -688 )
                LODWORD(v24) = a1 + 688;
LABEL_61:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v63,
                (_DWORD)v24,
                *(_QWORD *)(a1 + 72),
                (__int64)&v59);
            }
          }
LABEL_62:
          RtlReleaseResource(&stru_18008C4A0);
          return 2147942934LL;
        }
        if ( v23 + v12 < v12 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v63) = 0;
            LOWORD(v59) = 0;
            FormatRRASErrorString(&v63, L"GetSizeOfInterfaceConfig: Error %d in addition  \n", 2147942934LL);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v24 = &v58;
              if ( a1 != -688 )
                LODWORD(v24) = a1 + 688;
              goto LABEL_61;
            }
          }
          goto LABEL_62;
        }
        v12 += v23;
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v63) = 0;
        LOWORD(v59) = 0;
        FormatRRASErrorString(
          &v63,
          L"GetSizeOfInterfaceConfig: Error %d in GetIfInfo for %ws\n",
          v21,
          *(_QWORD *)(j[3] + 32));
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v22 = &v58;
          if ( a1 != -688 )
            LODWORD(v22) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v63,
            (_DWORD)v22,
            *(_QWORD *)(a1 + 72),
            (__int64)&v59);
        }
      }
    }
  }
  RtlReleaseResource(&stru_18008C4A0);
  v25 = *(_QWORD *)(a1 + 112);
  if ( v25 )
  {
    v26 = *(unsigned int *)(v25 + 4);
    if ( *(_DWORD *)(a1 + 516) )
      v27 = 28 * v26;
    else
      v27 = 52 * v26;
    v28 = v27;
    if ( v27 > 0xFFFFFFFF )
      v28 = -1;
    v29 = v27 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v27 > 0xFFFFFFFF )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v30 = L"GetSizeOfInterfaceConfig: Error %d in Multiplication for inbound filters \n";
        goto LABEL_72;
      }
      return v29;
    }
    v32 = v28 + 36;
    v33 = -1;
    if ( v28 + 36 >= v28 )
      v33 = v28 + 36;
    v29 = v32 < v28 ? 0x80070216 : 0;
    if ( v32 < v28 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v29;
      v30 = L"GetSizeOfInterfaceConfig: Error %d in addition for inbound filters  \n";
LABEL_72:
      LOWORD(v59) = 0;
      LOWORD(v63) = 0;
      FormatRRASErrorString(&v63, v30, v29, 2147942934LL);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v31 = &v58;
        if ( a1 != -688 )
          LODWORD(v31) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v63,
          (_DWORD)v31,
          *(_QWORD *)(a1 + 72),
          (__int64)&v59);
      }
      return v29;
    }
    if ( v33 + v12 < v12 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v19 = L"GetSizeOfInterfaceConfig: Error %d in addition for inbound filters  \n";
        goto LABEL_36;
      }
      return 2147942934LL;
    }
    v12 += v33;
  }
  v34 = *(_QWORD *)(a1 + 120);
  if ( v34 )
  {
    v35 = *(unsigned int *)(v34 + 4);
    if ( *(_DWORD *)(a1 + 516) )
      v36 = 28 * v35;
    else
      v36 = 52 * v35;
    v37 = v36;
    if ( v36 > 0xFFFFFFFF )
      v37 = -1;
    v29 = v36 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v36 > 0xFFFFFFFF )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v29;
      v30 = L"GetSizeOfInterfaceConfig: Error %d in Multiplication for outbound filters \n";
      goto LABEL_72;
    }
    v38 = v37 + 36;
    v39 = -1;
    if ( v37 + 36 >= v37 )
      v39 = v37 + 36;
    v29 = v38 < v37 ? 0x80070216 : 0;
    if ( v38 < v37 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v29;
      v30 = L"GetSizeOfInterfaceConfig: Error %d in addition for outbound filters \n";
      goto LABEL_72;
    }
    if ( v39 + v12 < v12 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v19 = L"GetSizeOfInterfaceConfig: Error %d in addition for outbound filters\n";
        goto LABEL_36;
      }
      return 2147942934LL;
    }
    v12 += v39;
  }
  v40 = v12 + 28;
  if ( v12 + 28 < v12 )
  {
LABEL_34:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 2147942934LL;
    v19 = L"GetSizeOfInterfaceConfig: Error %d in addition  \n";
LABEL_36:
    LOWORD(v59) = 0;
    LOWORD(v63) = 0;
    FormatRRASErrorString(&v63, v19, 2147942934LL);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return 2147942934LL;
    goto LABEL_136;
  }
  v41 = *(_QWORD *)(a1 + 128);
  if ( !v41 )
  {
LABEL_126:
    *v57 = v40;
    return 0;
  }
  v42 = *(unsigned int *)(v41 + 4);
  if ( *(_DWORD *)(a1 + 516) )
    v43 = 28 * v42;
  else
    v43 = 52 * v42;
  v44 = v43;
  if ( v43 > 0xFFFFFFFF )
    v44 = -1;
  v45 = v43 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v43 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v46 = L"GetSizeOfInterfaceConfig: Error %d in Multiplication for Demand-dial filters \n";
      goto LABEL_114;
    }
    return v45;
  }
  v48 = v44 + 36;
  if ( v44 + 36 >= v44 )
    v9 = v44 + 36;
  v45 = v48 < v44 ? 0x80070216 : 0;
  if ( v48 < v44 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v46 = L"GetSizeOfInterfaceConfig: Error %d in addition for Demand-dial filters  \n";
LABEL_114:
      LOWORD(v59) = 0;
      LOWORD(v63) = 0;
      FormatRRASErrorString(&v63, v46, v45, 2147942934LL);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v47 = &v58;
        if ( a1 != -688 )
          LODWORD(v47) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v63,
          (_DWORD)v47,
          *(_QWORD *)(a1 + 72),
          (__int64)&v59);
      }
    }
    return v45;
  }
  if ( v40 + v9 >= v40 )
  {
    v40 += v9;
    goto LABEL_126;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v19 = L"GetSizeOfInterfaceConfig: Error %d in addition for Demand-dial filters \n";
    goto LABEL_36;
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x18001e94c  mov     [rsp-8+arg_10], rbx
0x18001e951  push    rbp
0x18001e952  push    rsi
0x18001e953  push    rdi
0x18001e954  push    r12
0x18001e956  push    r13
0x18001e958  push    r14
0x18001e95a  push    r15
0x18001e95c  lea     rbp, [rsp-7C0h]
0x18001e964  sub     rsp, 8C0h
0x18001e96b  mov     rax, cs:__security_cookie
0x18001e972  xor     rax, rsp
0x18001e975  mov     [rbp+7F0h+var_40], rax
0x18001e97c  mov     ebx, [rcx+204h]
0x18001e982  lea     rax, g_rgicInfoCbv4
0x18001e989  xor     r14d, r14d
0x18001e98c  mov     [rsp+8F0h+var_888], rdx
0x18001e991  mov     rdi, rcx
0x18001e994  mov     [rsp+8F0h+var_8AC], r14d
0x18001e999  cmp     ebx, 1
0x18001e99c  mov     [rsp+8F0h+var_8B0], r14d
0x18001e9a1  lea     rcx, g_rgicInfoCbv6
0x18001e9a8  mov     [rsp+8F0h+var_8A0], r14d
0x18001e9ad  cmovnz  rax, rcx
0x18001e9b1  mov     [rsp+8F0h+var_89C], r14d
0x18001e9b6  mov     [rsp+8F0h+var_898], rax
0x18001e9bb  lea     r13d, [r14+5]
0x18001e9bf  lea     eax, [r14+3]
0x18001e9c3  mov     [rsp+8F0h+var_8A4], r14d
0x18001e9c8  cmovnz  r13d, eax
0x18001e9cc  mov     [rbp+7F0h+var_840], r14d
0x18001e9d0  mov     rsi, rdx
0x18001e9d3  mov     [rsp+8F0h+var_8A8], r13d
0x18001e9d8  xor     edx, edx; Val
0x18001e9da  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18001e9de  mov     r8d, 7FCh; Size
0x18001e9e4  call    memset_0
0x18001e9e9  xorps   xmm0, xmm0
0x18001e9ec  mov     [rbp+7F0h+var_870], r14d
0x18001e9f0  xor     eax, eax
0x18001e9f2  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e9f9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001ea00  movups  [rbp+7F0h+var_86C], xmm0
0x18001ea04  mov     [rbp+7F0h+var_84C], eax
0x18001ea07  movups  [rbp+7F0h+var_85C], xmm0
0x18001ea0b  movups  [rsp+8F0h+var_880], xmm0
0x18001ea10  jz      short loc_18001EA52
0x18001ea12  lea     rax, [rdi+2B0h]
0x18001ea19  mov     word ptr [rbp+7F0h+var_870], r14w
0x18001ea1e  test    rax, rax
0x18001ea21  lea     r9, [rsp+8F0h+var_880]
0x18001ea26  lea     r8, aEnteredGetsize; "Entered: GetSizeOfInterfaceConfig"
0x18001ea2d  mov     rcx, r12
0x18001ea30  cmovnz  r9, rax
0x18001ea34  lea     rdx, RasRtrmgrParamTraceInfo
0x18001ea3b  lea     rax, [rbp+7F0h+var_870]
0x18001ea3f  mov     [rsp+8F0h+var_8C8], rax
0x18001ea44  mov     rax, [rdi+48h]
0x18001ea48  mov     [rsp+8F0h+var_8D0], rax
0x18001ea4d  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ea52  test    rsi, rsi
0x18001ea55  jnz     short loc_18001EA5F
0x18001ea57  lea     eax, [rsi+57h]
0x18001ea5a  jmp     loc_18001F140
0x18001ea5f  mov     rcx, rdi
0x18001ea62  call    GetNumStaticRoutes
0x18001ea67  mov     eax, eax
0x18001ea69  mov     esi, 0FFFFFFFFh
0x18001ea6e  lea     rcx, [rax+rax*8]
0x18001ea72  shl     rcx, 3
0x18001ea76  cmp     rcx, rsi
0x18001ea79  ja      loc_18001F0D1
0x18001ea7f  lea     eax, [rcx+18h]
0x18001ea82  cmp     eax, ecx
0x18001ea84  jb      loc_18001F0BE
0x18001ea8a  add     eax, 0Ch
0x18001ea8d  cmp     eax, 0Ch
0x18001ea90  jb      loc_18001F0BE
0x18001ea96  test    ebx, ebx
0x18001ea98  jz      short loc_18001EAA7
0x18001ea9a  lea     ecx, [rax+28h]
0x18001ea9d  cmp     ecx, eax
0x18001ea9f  jb      loc_18001EB93
0x18001eaa5  mov     eax, ecx
0x18001eaa7  lea     r15d, [rax+1Ch]
0x18001eaab  mov     bl, 40h ; '@'
0x18001eaad  cmp     r15d, eax
0x18001eab0  jb      loc_18001F0A9
0x18001eab6  mov     r12d, r14d
0x18001eab9  lea     r14, RasRtrMgrParamTraceError
0x18001eac0  cmp     r12d, r13d
0x18001eac3  jnb     loc_18001EC18
0x18001eac9  mov     eax, r12d
0x18001eacc  lea     r13, [rax+rax*4]
0x18001ead0  mov     rax, [rsp+8F0h+var_898]
0x18001ead5  mov     rax, [rax+r13*8+8]
0x18001eada  test    rax, rax
0x18001eadd  jz      loc_18001EBC4
0x18001eae3  lea     rcx, [rsp+8F0h+var_8B0]
0x18001eae8  mov     [rsp+8F0h+var_8B0], 0
0x18001eaf0  mov     [rsp+8F0h+var_8C8], rcx
0x18001eaf5  xor     r9d, r9d
0x18001eaf8  mov     rcx, rdi
0x18001eafb  mov     [rsp+8F0h+var_8D0], 0
0x18001eb04  xor     r8d, r8d
0x18001eb07  xor     edx, edx
0x18001eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb0e  mov     r8d, eax
0x18001eb11  test    eax, eax
0x18001eb13  jz      loc_18001EBAD
0x18001eb19  cmp     eax, 7Ah ; 'z'
0x18001eb1c  jz      loc_18001EBAD
0x18001eb22  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001eb28  jz      loc_18001EBC4
0x18001eb2e  xor     eax, eax
0x18001eb30  lea     rdx, aGetsizeofinter_11; "GetSizeOfInterfaceConfig: Error %d in G"...
0x18001eb37  mov     word ptr [rbp+7F0h+var_840], ax
0x18001eb3b  lea     rcx, [rbp+7F0h+var_840]
0x18001eb3f  mov     word ptr [rbp+7F0h+var_870], ax
0x18001eb43  mov     rax, [rsp+8F0h+var_898]
0x18001eb48  mov     r9, [rax+r13*8]
0x18001eb4c  call    FormatRRASErrorString
0x18001eb51  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001eb57  jz      short loc_18001EBC4
0x18001eb59  lea     rax, [rdi+2B0h]
0x18001eb60  mov     rdx, r14
0x18001eb63  test    rax, rax
0x18001eb66  lea     r9, [rsp+8F0h+var_880]
0x18001eb6b  lea     r8, [rbp+7F0h+var_840]
0x18001eb6f  cmovnz  r9, rax
0x18001eb73  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001eb7a  lea     rax, [rbp+7F0h+var_870]
0x18001eb7e  mov     [rsp+8F0h+var_8C8], rax
0x18001eb83  mov     rax, [rdi+48h]
0x18001eb87  mov     [rsp+8F0h+var_8D0], rax
0x18001eb8c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001eb91  jmp     short loc_18001EBC4
0x18001eb93  mov     bl, 40h ; '@'
0x18001eb95  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001eb9b  jz      loc_18001F13B
0x18001eba1  lea     rdx, aGetsizeofinter_3; "GetSizeOfInterfaceConfig: Error %d in a"...
0x18001eba8  jmp     loc_18001F0E2
0x18001ebad  mov     eax, [rsp+8F0h+var_8B0]
0x18001ebb1  lea     ecx, [rax+18h]
0x18001ebb4  cmp     ecx, eax
0x18001ebb6  jb      short loc_18001EBD1
0x18001ebb8  lea     eax, [rcx+r15]
0x18001ebbc  cmp     eax, r15d
0x18001ebbf  jb      short loc_18001EBD1
0x18001ebc1  mov     r15d, eax
0x18001ebc4  mov     r13d, [rsp+8F0h+var_8A8]
0x18001ebc9  inc     r12d
0x18001ebcc  jmp     loc_18001EAC0
0x18001ebd1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ebd7  jz      loc_18001F13B
0x18001ebdd  lea     rdx, aGetsizeofinter_5; "GetSizeOfInterfaceConfig: Error %d in a"...
0x18001ebe4  xor     eax, eax
0x18001ebe6  lea     rcx, [rbp+7F0h+var_840]
0x18001ebea  mov     r8d, 80070216h
0x18001ebf0  mov     word ptr [rbp+7F0h+var_870], ax
0x18001ebf4  mov     word ptr [rbp+7F0h+var_840], ax
0x18001ebf8  call    FormatRRASErrorString
0x18001ebfd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ec03  jz      loc_18001F13B
0x18001ec09  mov     rdx, r14
0x18001ec0c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ec13  jmp     loc_18001F10D
0x18001ec18  mov     dl, 1; Wait
0x18001ec1a  lea     rcx, stru_18008C4A0; Resource
0x18001ec21  call    cs:__imp_RtlAcquireResourceShared
0x18001ec27  lea     r13, [rdi+38h]
0x18001ec2b  mov     r12, [r13+0]
0x18001ec2f  cmp     r12, r13
0x18001ec32  jz      loc_18001EDF2
0x18001ec38  cmp     dword ptr [r12+10h], 0
0x18001ec3e  jnz     loc_18001ED10
0x18001ec44  mov     [rsp+8F0h+var_8AC], 0
0x18001ec4c  lea     rcx, [rsp+8F0h+var_8A4]
0x18001ec51  mov     rax, [r12+18h]
0x18001ec56  lea     r9, [rsp+8F0h+var_89C]
0x18001ec5b  mov     [rsp+8F0h+var_8C8], rcx
0x18001ec60  lea     r8, [rsp+8F0h+var_8AC]
0x18001ec65  lea     rcx, [rsp+8F0h+var_8A0]
0x18001ec6a  xor     edx, edx
0x18001ec6c  mov     [rsp+8F0h+var_8D0], rcx
0x18001ec71  mov     ecx, [rdi+10h]
0x18001ec74  mov     rax, [rax+98h]
0x18001ec7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec80  mov     r8d, eax
0x18001ec83  test    eax, eax
0x18001ec85  jz      short loc_18001ECF9
0x18001ec87  cmp     eax, 7Ah ; 'z'
0x18001ec8a  jz      short loc_18001ECF9
0x18001ec8c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ec92  jz      short loc_18001ED10
0x18001ec94  xor     eax, eax
0x18001ec96  lea     rdx, aGetsizeofinter_10; "GetSizeOfInterfaceConfig: Error %d in G"...
0x18001ec9d  mov     word ptr [rbp+7F0h+var_840], ax
0x18001eca1  lea     rcx, [rbp+7F0h+var_840]
0x18001eca5  mov     word ptr [rbp+7F0h+var_870], ax
0x18001eca9  mov     r9, [r12+18h]
0x18001ecae  mov     r9, [r9+20h]
0x18001ecb2  call    FormatRRASErrorString
0x18001ecb7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ecbd  jz      short loc_18001ED10
0x18001ecbf  lea     rax, [rdi+2B0h]
0x18001ecc6  mov     rdx, r14
0x18001ecc9  test    rax, rax
0x18001eccc  lea     r9, [rsp+8F0h+var_880]
0x18001ecd1  lea     r8, [rbp+7F0h+var_840]
0x18001ecd5  cmovnz  r9, rax
0x18001ecd9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ece0  lea     rax, [rbp+7F0h+var_870]
0x18001ece4  mov     [rsp+8F0h+var_8C8], rax
0x18001ece9  mov     rax, [rdi+48h]
0x18001eced  mov     [rsp+8F0h+var_8D0], rax
0x18001ecf2  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ecf7  jmp     short loc_18001ED10
0x18001ecf9  mov     eax, [rsp+8F0h+var_8AC]
0x18001ecfd  lea     ecx, [rax+18h]
0x18001ed00  cmp     ecx, eax
0x18001ed02  jb      short loc_18001ED78
0x18001ed04  lea     eax, [rcx+r15]
0x18001ed08  cmp     eax, r15d
0x18001ed0b  jb      short loc_18001ED19
0x18001ed0d  mov     r15d, eax
0x18001ed10  mov     r12, [r12]
0x18001ed14  jmp     loc_18001EC2F
0x18001ed19  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ed1f  jz      loc_18001EDE0
0x18001ed25  xor     eax, eax
0x18001ed27  lea     rdx, aGetsizeofinter_5; "GetSizeOfInterfaceConfig: Error %d in a"...
0x18001ed2e  mov     r8d, 80070216h
0x18001ed34  mov     word ptr [rbp+7F0h+var_840], ax
0x18001ed38  lea     rcx, [rbp+7F0h+var_840]
0x18001ed3c  mov     word ptr [rbp+7F0h+var_870], ax
0x18001ed40  call    FormatRRASErrorString
0x18001ed45  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ed4b  jz      loc_18001EDE0
0x18001ed51  lea     rax, [rdi+2B0h]
0x18001ed58  test    rax, rax
0x18001ed5b  lea     r9, [rsp+8F0h+var_880]
0x18001ed60  cmovnz  r9, rax
0x18001ed64  lea     rax, [rbp+7F0h+var_870]
0x18001ed68  mov     [rsp+8F0h+var_8C8], rax
0x18001ed6d  mov     rax, [rdi+48h]
0x18001ed71  mov     [rsp+8F0h+var_8D0], rax
0x18001ed76  jmp     short loc_18001EDCD
0x18001ed78  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ed7e  jz      short loc_18001EDE0
0x18001ed80  xor     eax, eax
0x18001ed82  lea     rdx, aGetsizeofinter_5; "GetSizeOfInterfaceConfig: Error %d in a"...
0x18001ed89  mov     r8d, 80070216h
0x18001ed8f  mov     word ptr [rbp+7F0h+var_840], ax
0x18001ed93  lea     rcx, [rbp+7F0h+var_840]
0x18001ed97  mov     word ptr [rbp+7F0h+var_870], ax
0x18001ed9b  call    FormatRRASErrorString
0x18001eda0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001eda6  jz      short loc_18001EDE0
0x18001eda8  lea     rax, [rdi+2B0h]
0x18001edaf  lea     rdx, [rbp+7F0h+var_870]
0x18001edb3  test    rax, rax
0x18001edb6  mov     [rsp+8F0h+var_8C8], rdx
0x18001edbb  lea     r9, [rsp+8F0h+var_880]
0x18001edc0  mov     rdx, [rdi+48h]
0x18001edc4  cmovnz  r9, rax
0x18001edc8  mov     [rsp+8F0h+var_8D0], rdx
0x18001edcd  lea     r8, [rbp+7F0h+var_840]
0x18001edd1  mov     rdx, r14
0x18001edd4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001eddb  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ede0  lea     rcx, stru_18008C4A0; Resource
0x18001ede7  call    cs:__imp_RtlReleaseResource
0x18001eded  jmp     loc_18001F13B
0x18001edf2  lea     rcx, stru_18008C4A0; Resource
0x18001edf9  call    cs:__imp_RtlReleaseResource
0x18001edff  mov     rax, [rdi+70h]
0x18001ee03  mov     r9d, 80070216h
0x18001ee09  test    rax, rax
0x18001ee0c  jz      loc_18001EEE1
0x18001ee12  mov     r8d, [rdi+204h]
0x18001ee19  mov     ecx, [rax+4]
0x18001ee1c  test    r8d, r8d
0x18001ee1f  jz      short loc_18001EE27
0x18001ee21  imul    rcx, 1Ch
0x18001ee25  jmp     short loc_18001EE2B
0x18001ee27  imul    rcx, 34h ; '4'
0x18001ee2b  mov     eax, ecx
0x18001ee2d  cmp     rsi, rcx
0x18001ee30  jnb     short loc_18001EE34
0x18001ee32  mov     eax, esi
0x18001ee34  sbb     r12d, r12d
0x18001ee37  and     r12d, r9d
0x18001ee3a  test    r12d, r12d
0x18001ee3d  jns     short loc_18001EEAC
0x18001ee3f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ee45  jz      short loc_18001EEA4
0x18001ee47  lea     rdx, aGetsizeofinter_8; "GetSizeOfInterfaceConfig: Error %d in M"...
0x18001ee4e  xor     eax, eax
0x18001ee50  lea     rcx, [rbp+7F0h+var_840]
  ... truncated ...
```
