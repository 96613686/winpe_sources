# RRouterInterfaceCreate

- ea: `0x1800057f0`
- end: `0x180005d0c`
- name: `RRouterInterfaceCreate`
- size: `1308`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180003f40`
- `0x180005340`
- `0x180005358`
- `0x180005670`
- `0x1800056c4`
- `0x1800057f0`
- `0x180005d14`
- `0x1800076ac`
- `0x18000d984`
- `0x18000def0`
- `0x180012be0`
- `0x1800182a0`
- `0x180018f28`
- `0x180019950`
- `0x1800288a8`
- `0x180032aa8`
- `0x180036430`
- `0x180045d40`
- `0x180045d7c`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b79`
- `MPRDDM!IfObjectSetDialoutHoursRestriction` at `0x180005ca8`
- `MPRDDM!IfObjectSetDialoutHoursRestriction` at `0x180005ca8`

## string_xrefs

- `0x180005b20`: `InterfaceCreate returned %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRouterInterfaceCreate(__int64 a1, unsigned int a2, __int64 a3, _DWORD *a4)
{
  _DWORD *v4; // r13
  void *v7; // r15
  int v8; // ebx
  DWORD LastError; // edi
  __int64 v11; // rsi
  unsigned int v12; // ecx
  SIZE_T SizeOfMultiSz; // r15
  __int64 v14; // r13
  __int64 v15; // rsi
  CDimInterfaceTable *v16; // rcx
  int v17; // ecx
  int v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL AccessStatus; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  std::tr1::_Ref_count_base *v23; // [rsp+80h] [rbp-80h]
  _DWORD *v24; // [rsp+88h] [rbp-78h]
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  std::tr1::_Ref_count_base *v26; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v4 = a4;
  v24 = a4;
  v7 = 0;
  AccessStatus = 0;
  v18[0] = 0;
  ActivityId = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v8 = SetRasServerActivityId(&ActivityId);
  LastError = IsMultiTenancyEnabled(v18);
  if ( LastError )
  {
LABEL_2:
    if ( v8 )
      ReSetActivityId(&ActivityId);
    return LastError;
  }
  if ( v18[0] )
    goto LABEL_25;
  if ( DimSecObjAccessCheck(1u, &AccessStatus) || AccessStatus )
  {
    if ( v8 )
      ReSetActivityId(&ActivityId);
    return 5;
  }
  if ( a2 > 3 )
    goto LABEL_25;
  if ( !a3 )
    goto LABEL_82;
  if ( !*(_DWORD *)a3 )
    goto LABEL_82;
  v11 = *(_QWORD *)(a3 + 8);
  if ( !v11 || !v4 || !a2 && *(_DWORD *)a3 < 0x21Cu )
    goto LABEL_82;
  if ( a2 == 1 && *(_DWORD *)a3 < 0x220u || a2 == 2 && *(_DWORD *)a3 < 0x9A4u || a2 == 3 && *(_DWORD *)a3 < 0x9D0u )
    goto LABEL_82;
  if ( *(_DWORD *)(v11 + 524) == 6 )
  {
LABEL_25:
    if ( v8 )
      ReSetActivityId(&ActivityId);
    return 50;
  }
  LastError = InterfaceAjustVLSPointers(a2, *(unsigned __int8 **)(a3 + 8));
  v18[0] = LastError;
  if ( LastError )
    goto LABEL_2;
  v12 = *(_DWORD *)(v11 + 524);
  if ( v12 - 3 <= 3 )
  {
    if ( !*(_DWORD *)(v11 + 520) )
      goto LABEL_82;
    v20 = 2;
    v21 = 1;
  }
  else
  {
    if ( v12 > 2 )
      goto LABEL_82;
    if ( (gblDIMConfigInfo & 0x12) == gblDIMConfigInfo )
    {
      if ( v8 )
        ReSetActivityId(&ActivityId);
      return 903;
    }
    v21 = 0;
    v20 = 0;
  }
  if ( a2 != 1 || !*(_DWORD *)(v11 + 540) )
    goto LABEL_50;
  SizeOfMultiSz = (unsigned int)MprUtilGetSizeOfMultiSz((STRSAFE_PCNZWCH)(v11 + 544), 0x7D0u);
  LastError = v18[0];
  if ( v18[0] )
    goto LABEL_2;
  if ( (int)SizeOfMultiSz + 544 >= (unsigned int)SizeOfMultiSz && (unsigned int)(SizeOfMultiSz + 544) <= *(_DWORD *)a3 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Creating l1 interface with %d bytes of dohr", (unsigned int)SizeOfMultiSz);
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v28);
    }
    v7 = HeapAlloc(hHeap, 8u, SizeOfMultiSz);
    if ( !v7 )
    {
      if ( v8 )
        ReSetActivityId(&ActivityId);
      return 8;
    }
LABEL_50:
    *(_QWORD *)v18 = 0;
    CDimInterfaceTable::AcquireExclusive(g_pCDimInterfaceTable);
    if ( *(_DWORD *)(v11 + 524) )
    {
      v14 = *CDimInterfaceTable::GetInterfaceByName((__int64)g_pCDimInterfaceTable, &v25, v11, 0);
      if ( v26 )
        std::tr1::_Ref_count_base::_Decref(v26);
      if ( v14 )
      {
        LastError = 904;
        goto LABEL_55;
      }
      v4 = v24;
    }
    if ( (a2 != 2 || (LastError = RpbkSetEntry(2u, (unsigned __int8 *)v11, *(_DWORD *)a3)) == 0)
      && (a2 != 3 || (LastError = RpbkSetEntry(3u, (unsigned __int8 *)v11, *(_DWORD *)a3)) == 0) )
    {
      v17 = *(_DWORD *)(v11 + 524);
      if ( v17 == 2 )
      {
        UpdateGlobalPhoneBookContext();
        v17 = *(_DWORD *)(v11 + 524);
      }
      CDimInterfaceTable::CreateInterface(
        (__int64)g_pCDimInterfaceTable,
        &v22,
        v11,
        v20,
        v17,
        0,
        *(_DWORD *)(v11 + 520) == 1,
        60,
        21600,
        (__int64)v7,
        0);
      if ( v22 )
      {
        CDimInterfaceTable::InsertInterface((__int64)g_pCDimInterfaceTable, &v22);
        *v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v23 )
          std::tr1::_Ref_count_base::_Decref(v23);
LABEL_56:
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v28, L"InterfaceCreate returned %d", LastError);
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v28);
        }
        CDimInterfaceTable::ReleaseExclusive(g_pCDimInterfaceTable);
        if ( LastError )
        {
          if ( v7 )
            HeapFree(hHeap, 0, v7);
        }
        else
        {
          if ( v7 )
            IfObjectSetDialoutHoursRestriction(v15);
          if ( !v21 )
            goto LABEL_81;
          RouterIdentityObjectUpdateAttributes(0);
        }
        if ( LastError )
          goto LABEL_2;
LABEL_81:
        CDimInterfaceTable::UpdateTelemetry(v16);
        goto LABEL_2;
      }
      LastError = GetLastError();
      if ( v23 )
        std::tr1::_Ref_count_base::_Decref(v23);
    }
LABEL_55:
    v15 = *(_QWORD *)v18;
    goto LABEL_56;
  }
LABEL_82:
  if ( v8 )
    ReSetActivityId(&ActivityId);
  return 87;
}

```

## disassembly

```asm
0x1800057f0  mov     [rsp-8+arg_0], rbx
0x1800057f5  push    rbp
0x1800057f6  push    rsi
0x1800057f7  push    rdi
0x1800057f8  push    r12
0x1800057fa  push    r13
0x1800057fc  push    r14
0x1800057fe  push    r15
0x180005800  lea     rbp, [rsp-7C0h]
0x180005808  sub     rsp, 8C0h
0x18000580f  mov     rax, cs:__security_cookie
0x180005816  xor     rax, rsp
0x180005819  mov     [rbp+7F0h+var_40], rax
0x180005820  mov     r13, r9
0x180005823  mov     [rbp+7F0h+var_868], r9
0x180005827  mov     r12, r8
0x18000582a  mov     r14d, edx
0x18000582d  xor     r15d, r15d
0x180005830  mov     [rsp+8F0h+AccessStatus], r15d
0x180005835  mov     [rsp+8F0h+var_890], r15d
0x18000583a  xorps   xmm0, xmm0
0x18000583d  movups  xmmword ptr [rbp+7F0h+ActivityId.Data1], xmm0
0x180005841  mov     [rbp+7F0h+var_840], r15d
0x180005845  xor     edx, edx; Val
0x180005847  mov     r8d, 7FCh; Size
0x18000584d  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180005851  call    memset_0
0x180005856  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x18000585a  call    SetRasServerActivityId
0x18000585f  mov     ebx, eax
0x180005861  lea     rcx, [rsp+8F0h+var_890]; int *
0x180005866  call    IsMultiTenancyEnabled
0x18000586b  mov     edi, eax
0x18000586d  test    eax, eax
0x18000586f  jz      short loc_180005885
0x180005871  test    ebx, ebx
0x180005873  jz      short loc_18000587E
0x180005875  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x180005879  call    ReSetActivityId
0x18000587e  mov     eax, edi
0x180005880  jmp     loc_180005CE2
0x180005885  cmp     [rsp+8F0h+var_890], r15d
0x18000588a  jnz     loc_18000594D
0x180005890  lea     rdx, [rsp+8F0h+AccessStatus]; AccessStatus
0x180005895  mov     ecx, 1; DesiredAccess
0x18000589a  call    ?DimSecObjAccessCheck@@YAKKPEAK@Z; DimSecObjAccessCheck(ulong,ulong *)
0x18000589f  test    eax, eax
0x1800058a1  jnz     short loc_1800058AA
0x1800058a3  cmp     [rsp+8F0h+AccessStatus], r15d
0x1800058a8  jz      short loc_1800058C1
0x1800058aa  test    ebx, ebx
0x1800058ac  jz      short loc_1800058B7
0x1800058ae  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x1800058b2  call    ReSetActivityId
0x1800058b7  mov     eax, 5
0x1800058bc  jmp     loc_180005CE2
0x1800058c1  cmp     r14d, 3
0x1800058c5  ja      loc_18000594D
0x1800058cb  test    r12, r12
0x1800058ce  jz      loc_180005CD0
0x1800058d4  cmp     [r12], r15d
0x1800058d8  jz      loc_180005CD0
0x1800058de  mov     rsi, [r12+8]
0x1800058e3  test    rsi, rsi
0x1800058e6  jz      loc_180005CD0
0x1800058ec  test    r13, r13
0x1800058ef  jz      loc_180005CD0
0x1800058f5  test    r14d, r14d
0x1800058f8  jnz     short loc_180005908
0x1800058fa  cmp     dword ptr [r12], 21Ch
0x180005902  jb      loc_180005CD0
0x180005908  cmp     r14d, 1
0x18000590c  jnz     short loc_18000591C
0x18000590e  cmp     dword ptr [r12], 220h
0x180005916  jb      loc_180005CD0
0x18000591c  cmp     r14d, 2
0x180005920  jnz     short loc_180005930
0x180005922  cmp     dword ptr [r12], 9A4h
0x18000592a  jb      loc_180005CD0
0x180005930  cmp     r14d, 3
0x180005934  jnz     short loc_180005944
0x180005936  cmp     dword ptr [r12], 9D0h
0x18000593e  jb      loc_180005CD0
0x180005944  cmp     dword ptr [rsi+20Ch], 6
0x18000594b  jnz     short loc_180005964
0x18000594d  test    ebx, ebx
0x18000594f  jz      short loc_18000595A
0x180005951  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x180005955  call    ReSetActivityId
0x18000595a  mov     eax, 32h ; '2'
0x18000595f  jmp     loc_180005CE2
0x180005964  mov     rdx, rsi; unsigned __int8 *
0x180005967  mov     ecx, r14d; unsigned int
0x18000596a  call    ?InterfaceAjustVLSPointers@@YAKKPEAE@Z; InterfaceAjustVLSPointers(ulong,uchar *)
0x18000596f  mov     edi, eax
0x180005971  mov     [rsp+8F0h+var_890], eax
0x180005975  test    eax, eax
0x180005977  jnz     loc_180005871
0x18000597d  mov     ecx, [rsi+20Ch]
0x180005983  lea     eax, [rcx-3]
0x180005986  cmp     eax, 3
0x180005989  jbe     short loc_1800059C8
0x18000598b  cmp     ecx, 2
0x18000598e  ja      loc_180005CD0
0x180005994  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18000599a  and     eax, 12h
0x18000599d  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x1800059a3  jnz     short loc_1800059BC
0x1800059a5  test    ebx, ebx
0x1800059a7  jz      short loc_1800059B2
0x1800059a9  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x1800059ad  call    ReSetActivityId
0x1800059b2  mov     eax, 387h
0x1800059b7  jmp     loc_180005CE2
0x1800059bc  mov     [rsp+8F0h+var_880], r15d
0x1800059c1  mov     [rsp+8F0h+var_884], r15d
0x1800059c6  jmp     short loc_1800059E5
0x1800059c8  cmp     [rsi+208h], r15d
0x1800059cf  jz      loc_180005CD0
0x1800059d5  mov     [rsp+8F0h+var_884], 2
0x1800059dd  mov     [rsp+8F0h+var_880], 1
0x1800059e5  cmp     r14d, 1
0x1800059e9  jnz     loc_180005AB1
0x1800059ef  cmp     [rsi+21Ch], r15d
0x1800059f6  jz      loc_180005AB1
0x1800059fc  lea     rcx, [rsi+220h]; psz
0x180005a03  lea     r8, [rsp+8F0h+var_890]
0x180005a08  mov     edx, 7D0h; cchMax
0x180005a0d  call    MprUtilGetSizeOfMultiSz
0x180005a12  mov     r15d, eax
0x180005a15  mov     edi, [rsp+8F0h+var_890]
0x180005a19  test    edi, edi
0x180005a1b  jnz     loc_180005871
0x180005a21  lea     eax, [r15+220h]
0x180005a28  cmp     eax, r15d
0x180005a2b  jb      loc_180005CD0
0x180005a31  cmp     eax, [r12]
0x180005a35  ja      loc_180005CD0
0x180005a3b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180005a42  jz      short loc_180005A7D
0x180005a44  xor     eax, eax
0x180005a46  mov     word ptr [rbp+7F0h+var_840], ax
0x180005a4a  mov     r8d, r15d
0x180005a4d  lea     rdx, aCreatingL1Inte; "Creating l1 interface with %d bytes of "...
0x180005a54  lea     rcx, [rbp+7F0h+var_840]
0x180005a58  call    FormatRRASErrorString
0x180005a5d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180005a64  jz      short loc_180005A7D
0x180005a66  lea     r8, [rbp+7F0h+var_840]
0x180005a6a  lea     rdx, RasDimTraceInfo
0x180005a71  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005a78  call    McTemplateU0z_EventWriteTransfer
0x180005a7d  mov     r8, r15; dwBytes
0x180005a80  mov     edx, 8; dwFlags
0x180005a85  mov     rcx, cs:hHeap; hHeap
0x180005a8c  call    cs:__imp_HeapAlloc
0x180005a92  mov     r15, rax
0x180005a95  test    rax, rax
0x180005a98  jnz     short loc_180005AB1
0x180005a9a  test    ebx, ebx
0x180005a9c  jz      short loc_180005AA7
0x180005a9e  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x180005aa2  call    ReSetActivityId
0x180005aa7  mov     eax, 8
0x180005aac  jmp     loc_180005CE2
0x180005ab1  mov     qword ptr [rsp+8F0h+var_890], 0
0x180005aba  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x180005ac1  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x180005ac6  cmp     dword ptr [rsi+20Ch], 0
0x180005acd  jz      loc_180005B88
0x180005ad3  xor     r9d, r9d
0x180005ad6  mov     r8, rsi
0x180005ad9  lea     rdx, [rbp+7F0h+var_860]
0x180005add  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180005ae4  call    ?GetInterfaceByName@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAG_N@Z; CDimInterfaceTable::GetInterfaceByName(ushort *,bool)
0x180005ae9  mov     r13, [rax]
0x180005aec  mov     rcx, [rbp+7F0h+var_858]; this
0x180005af0  test    rcx, rcx
0x180005af3  jz      short loc_180005AFB
0x180005af5  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005afa  nop
0x180005afb  test    r13, r13
0x180005afe  jz      loc_180005B84
0x180005b04  mov     edi, 388h
0x180005b09  mov     rsi, qword ptr [rsp+8F0h+var_890]
0x180005b0e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180005b15  jz      short loc_180005B50
0x180005b17  xor     eax, eax
0x180005b19  mov     word ptr [rbp+7F0h+var_840], ax
0x180005b1d  mov     r8d, edi
0x180005b20  lea     rdx, aInterfacecreat; "InterfaceCreate returned %d"
0x180005b27  lea     rcx, [rbp+7F0h+var_840]
0x180005b2b  call    FormatRRASErrorString
0x180005b30  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180005b37  jz      short loc_180005B50
0x180005b39  lea     r8, [rbp+7F0h+var_840]
0x180005b3d  lea     rdx, RasDimTraceInfo
0x180005b44  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005b4b  call    McTemplateU0z_EventWriteTransfer
0x180005b50  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x180005b57  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x180005b5c  test    edi, edi
0x180005b5e  jz      loc_180005CA0
0x180005b64  test    r15, r15
0x180005b67  jz      loc_180005CBE
0x180005b6d  mov     r8, r15; lpMem
0x180005b70  xor     edx, edx; dwFlags
0x180005b72  mov     rcx, cs:hHeap; hHeap
0x180005b79  call    cs:__imp_HeapFree
0x180005b7f  jmp     loc_180005CBE
0x180005b84  mov     r13, [rbp+7F0h+var_868]
0x180005b88  cmp     r14d, 2
0x180005b8c  jnz     short loc_180005BA7
0x180005b8e  mov     r8d, [r12]; unsigned int
0x180005b92  mov     rdx, rsi; unsigned __int8 *
0x180005b95  mov     ecx, r14d; unsigned int
0x180005b98  call    ?RpbkSetEntry@@YAKKPEAEK@Z; RpbkSetEntry(ulong,uchar *,ulong)
0x180005b9d  mov     edi, eax
0x180005b9f  test    eax, eax
0x180005ba1  jnz     loc_180005B09
0x180005ba7  cmp     r14d, 3
0x180005bab  jnz     short loc_180005BC6
0x180005bad  mov     r8d, [r12]; unsigned int
0x180005bb1  mov     rdx, rsi; unsigned __int8 *
0x180005bb4  mov     ecx, r14d; unsigned int
0x180005bb7  call    ?RpbkSetEntry@@YAKKPEAEK@Z; RpbkSetEntry(ulong,uchar *,ulong)
0x180005bbc  mov     edi, eax
0x180005bbe  test    eax, eax
0x180005bc0  jnz     loc_180005B09
0x180005bc6  mov     ecx, [rsi+20Ch]
0x180005bcc  cmp     ecx, 2
0x180005bcf  jnz     short loc_180005BDC
0x180005bd1  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x180005bd6  mov     ecx, [rsi+20Ch]
0x180005bdc  cmp     dword ptr [rsi+208h], 1
0x180005be3  setz    al
0x180005be6  mov     [rsp+8F0h+var_8A0], 0
0x180005bef  mov     [rsp+8F0h+var_8A8], r15
0x180005bf4  mov     [rsp+8F0h+var_8B0], 5460h
0x180005bfc  mov     [rsp+8F0h+var_8B8], 3Ch ; '<'
0x180005c04  mov     [rsp+8F0h+var_8C0], al
0x180005c08  mov     [rsp+8F0h+var_8C8], 0
0x180005c11  mov     [rsp+8F0h+var_8D0], ecx
0x180005c15  mov     r9d, [rsp+8F0h+var_884]
0x180005c1a  mov     r8, rsi
0x180005c1d  lea     rdx, [rsp+8F0h+var_878]
0x180005c22  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180005c29  call    ?CreateInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAGW4ROUTER_INTERFACE_STATE@@W4_ROUTER_INTERFACE_TYPE@@PEAX_NKK0PEAU_DIM_INTERFACE_OBJECT_EXTRA_INFO@@@Z; CDimInterfaceTable::CreateInterface(ushort *,ROUTER_INTERFACE_STATE,_ROUTER_INTERFACE_TYPE,void *,bool,ulong,ulong,ushort *,_DIM_INTERFACE_OBJECT_EXTRA_INFO *)
0x180005c2e  cmp     [rsp+8F0h+var_878], 0
0x180005c34  jnz     short loc_180005C52
0x180005c36  call    cs:__imp_GetLastError
0x180005c3c  mov     edi, eax
0x180005c3e  mov     rcx, [rbp+7F0h+var_870]; this
0x180005c42  test    rcx, rcx
0x180005c45  jz      short loc_180005C4D
0x180005c47  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005c4c  nop
0x180005c4d  jmp     loc_180005B09
0x180005c52  lea     rdx, [rsp+8F0h+var_878]
0x180005c57  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180005c5e  call    ?InsertInterface@CDimInterfaceTable@@QEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterface(std::tr1::shared_ptr<CDimInterface> const &)
0x180005c63  mov     rcx, [rsp+8F0h+var_878]
0x180005c68  mov     rax, [rcx]
0x180005c6b  mov     rax, [rax+10h]
0x180005c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c74  mov     [r13+0], eax
0x180005c78  mov     rcx, [rsp+8F0h+var_878]
0x180005c7d  mov     rax, [rcx]
0x180005c80  mov     rax, [rax+10h]
0x180005c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c89  mov     rsi, rax
0x180005c8c  mov     rcx, [rbp+7F0h+var_870]; this
0x180005c90  test    rcx, rcx
0x180005c93  jz      short loc_180005C9B
0x180005c95  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005c9a  nop
0x180005c9b  jmp     loc_180005B0E
0x180005ca0  test    r15, r15
0x180005ca3  jz      short loc_180005CAE
0x180005ca5  mov     rcx, rsi
0x180005ca8  call    cs:__imp_IfObjectSetDialoutHoursRestriction
0x180005cae  cmp     [rsp+8F0h+var_880], 0
0x180005cb3  jz      short loc_180005CC6
0x180005cb5  xor     edx, edx; BOOLEAN
0x180005cb7  xor     ecx, ecx; PVOID
0x180005cb9  call    ?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z; RouterIdentityObjectUpdateAttributes(void *,uchar)
0x180005cbe  test    edi, edi
0x180005cc0  jnz     loc_180005871
0x180005cc6  call    ?UpdateTelemetry@CDimInterfaceTable@@QEAAXXZ; CDimInterfaceTable::UpdateTelemetry(void)
0x180005ccb  jmp     loc_180005871
0x180005cd0  test    ebx, ebx
0x180005cd2  jz      short loc_180005CDD
0x180005cd4  lea     rcx, [rbp+7F0h+ActivityId]; ActivityId
0x180005cd8  call    ReSetActivityId
0x180005cdd  mov     eax, 57h ; 'W'
0x180005ce2  mov     rcx, [rbp+7F0h+var_40]
0x180005ce9  xor     rcx, rsp; StackCookie
0x180005cec  call    __security_check_cookie
0x180005cf1  mov     rbx, [rsp+8F0h+arg_0]
0x180005cf9  add     rsp, 8C0h
  ... truncated ...
```
