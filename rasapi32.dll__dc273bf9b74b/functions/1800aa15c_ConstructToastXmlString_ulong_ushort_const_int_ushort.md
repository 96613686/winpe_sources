# ConstructToastXmlString(ulong,ushort const *,int,ushort * *)

- ea: `0x1800aa15c`
- end: `0x1800aa528`
- name: `?ConstructToastXmlString@@YAJKPEBGHPEAPEAG@Z`
- size: `972`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800af670`

## callees

- `0x18004e580`
- `0x18007e5f0`
- `0x1800aa15c`
- `0x1800aab8c`
- `0x1800ae864`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa40f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa40f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa39c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa39c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800aa3c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800aa3c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800aa37a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800aa37a`

## string_xrefs

- `0x1800aa373`: `rasapi32.dll`
- `0x1800aa1bc`: `\n<toast launch="ms-settings:network-vpn" activationType="protocol">\n    <visual>\n        <binding template="ToastGeneric">\n            <text id="1">%1!ws!</text>\n        </binding>\n    </visual>\n</toast>`
- `0x1800aa22b`: `\n<toast>\n    <visual>\n        <binding template="ToastGeneric">\n            <text id="1">%1!ws!</text>\n        </binding>\n    </visual>\n</toast>`
- `0x1800aa2a9`: `\n<toast duration="long" launch="ms-settings:network-vpn" activationType="protocol">\n    <visual>\n        <binding template="ToastGeneric">\n            <text id="1">%1!ws!</text>\n        </binding>\n    </visual>\n</toast>`
- `0x1800aa2a2`: `\n<toast duration="long">\n    <visual>\n        <binding template="ToastGeneric">\n            <text id="1">%1!ws!</text>\n        </binding>\n    </visual>\n</toast>`

## pseudocode

```c
__int64 __fastcall ConstructToastXmlString(unsigned int a1, const unsigned __int16 *a2, int a3, unsigned __int16 **a4)
{
  __int64 v8; // rdx
  _OWORD *v9; // rcx
  const wchar_t *v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int64 v20; // rdx
  _OWORD *v21; // rcx
  const wchar_t *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  wchar_t v32; // ax
  __int64 v33; // rdx
  __int64 v34; // r8
  const wchar_t *v35; // rax
  const wchar_t *v36; // rsi
  _QWORD *v37; // rcx
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  UINT v43; // edi
  HMODULE ModuleHandleW; // r15
  int LastError; // ebx
  __int64 v46; // rdx
  _QWORD *v47; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v51[510]; // [rsp+32h] [rbp-CEh] BYREF
  _BYTE v52[304]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v53[416]; // [rsp+360h] [rbp+260h] BYREF

  Buffer = 0;
  memset_0(v51, 0, sizeof(v51));
  v8 = 3;
  v9 = v53;
  v10 = L"\n"
         "<toast launch=\"ms-settings:network-vpn\" activationType=\"protocol\">\n"
         "    <visual>\n"
         "        <binding template=\"ToastGeneric\">\n"
         "            <text id=\"1\">%1!ws!</text>\n"
         "        </binding>\n"
         "    </visual>\n"
         "</toast>";
  do
  {
    v11 = *((_OWORD *)v10 + 1);
    *v9 = *(_OWORD *)v10;
    v12 = *((_OWORD *)v10 + 2);
    v9[1] = v11;
    v13 = *((_OWORD *)v10 + 3);
    v9[2] = v12;
    v14 = *((_OWORD *)v10 + 4);
    v9[3] = v13;
    v15 = *((_OWORD *)v10 + 5);
    v9[4] = v14;
    v16 = *((_OWORD *)v10 + 6);
    v9[5] = v15;
    v17 = *((_OWORD *)v10 + 7);
    v10 += 64;
    v9[6] = v16;
    v9[7] = v17;
    v9 += 8;
    --v8;
  }
  while ( v8 );
  v18 = *(_OWORD *)v10;
  v19 = *((_QWORD *)v10 + 2);
  v20 = 2;
  *v9 = v18;
  *((_QWORD *)v9 + 2) = v19;
  v21 = v52;
  v22 = L"\n"
         "<toast>\n"
         "    <visual>\n"
         "        <binding template=\"ToastGeneric\">\n"
         "            <text id=\"1\">%1!ws!</text>\n"
         "        </binding>\n"
         "    </visual>\n"
         "</toast>";
  do
  {
    v23 = *((_OWORD *)v22 + 1);
    *v21 = *(_OWORD *)v22;
    v24 = *((_OWORD *)v22 + 2);
    v21[1] = v23;
    v25 = *((_OWORD *)v22 + 3);
    v21[2] = v24;
    v26 = *((_OWORD *)v22 + 4);
    v21[3] = v25;
    v27 = *((_OWORD *)v22 + 5);
    v21[4] = v26;
    v28 = *((_OWORD *)v22 + 6);
    v21[5] = v27;
    v29 = *((_OWORD *)v22 + 7);
    v22 += 64;
    v21[6] = v28;
    v21[7] = v29;
    v21 += 8;
    --v20;
  }
  while ( v20 );
  v30 = *(_OWORD *)v22;
  v31 = *((_OWORD *)v22 + 1);
  v32 = v22[16];
  *v21 = v30;
  v21[1] = v31;
  *((_WORD *)v21 + 16) = v32;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::GetImpl'::`2'::impl,
                          0,
                          128) )
  {
    v35 = L"\n"
           "<toast duration=\"long\">\n"
           "    <visual>\n"
           "        <binding template=\"ToastGeneric\">\n"
           "            <text id=\"1\">%1!ws!</text>\n"
           "        </binding>\n"
           "    </visual>\n"
           "</toast>";
    v36 = L"\n"
           "<toast duration=\"long\" launch=\"ms-settings:network-vpn\" activationType=\"protocol\">\n"
           "    <visual>\n"
           "        <binding template=\"ToastGeneric\">\n"
           "            <text id=\"1\">%1!ws!</text>\n"
           "        </binding>\n"
           "    </visual>\n"
           "</toast>";
  }
  else
  {
    v36 = (const wchar_t *)v53;
    v35 = (const wchar_t *)v52;
  }
  if ( !a3 )
    v36 = v35;
  if ( !a4 || !a2 )
  {
    LastError = -2147024809;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v46 = 13;
LABEL_45:
    WPP_SF_d(v37[2], v46, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, 2147942487LL);
    goto LABEL_46;
  }
  *a4 = 0;
  v37 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, a1);
    v37 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
    goto LABEL_37;
  v38 = a1 - 1;
  if ( !v38 )
  {
    v43 = 1001;
    goto LABEL_29;
  }
  v39 = v38 - 1;
  if ( !v39 )
  {
    v43 = 1002;
    goto LABEL_29;
  }
  v40 = v39 - 1;
  if ( !v40 )
  {
    v43 = 1003;
    goto LABEL_29;
  }
  v41 = v40 - 1;
  if ( !v41 )
  {
    v43 = 1006;
    goto LABEL_29;
  }
  v42 = v41 - 1;
  if ( !v42 )
  {
    v43 = 1007;
    goto LABEL_29;
  }
  if ( v42 != 1 )
  {
LABEL_37:
    LastError = -2147024809;
    if ( v37 == &WPP_GLOBAL_Control || (*((_DWORD *)v37 + 7) & 0x800) == 0 || *((_BYTE *)v37 + 25) < 2u )
      goto LABEL_46;
    v46 = 15;
    goto LABEL_45;
  }
  v43 = 1005;
LABEL_29:
  ModuleHandleW = GetModuleHandleW(L"rasapi32.dll");
  if ( ModuleHandleW
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0x80070000)
      : (LastError = GetLastError()),
        LastError >= 0) )
  {
    LastError = LoadStringW(ModuleHandleW, v43, &Buffer, 256);
    if ( LastError >= 0 )
    {
      hMem = 0;
      LastError = FormatToastMessage(&Buffer, (unsigned __int16 **)&hMem, a2);
      if ( LastError >= 0 )
      {
        LastError = FormatToastMessage(v36, a4, hMem);
        LocalFree(hMem);
      }
    }
  }
LABEL_46:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::GetImpl'::`2'::impl,
                           v33,
                           v34) )
    return (unsigned int)LastError;
  if ( a4 && *a4 )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)LastError;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_54;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, *a4);
  }
  v47 = WPP_GLOBAL_Control;
LABEL_54:
  if ( v47 != &WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x800) != 0 && *((_BYTE *)v47 + 25) >= 6u )
    WPP_SF_d(v47[2], 17, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800aa15c  mov     [rsp-8+arg_10], rbx
0x1800aa161  push    rbp
0x1800aa162  push    rsi
0x1800aa163  push    rdi
0x1800aa164  push    r12
0x1800aa166  push    r13
0x1800aa168  push    r14
0x1800aa16a  push    r15
0x1800aa16c  lea     rbp, [rsp-410h]
0x1800aa174  sub     rsp, 510h
0x1800aa17b  mov     rax, cs:__security_cookie
0x1800aa182  xor     rax, rsp
0x1800aa185  mov     [rbp+440h+var_40], rax
0x1800aa18c  mov     edi, r8d
0x1800aa18f  mov     r13, rdx
0x1800aa192  mov     ebx, ecx
0x1800aa194  xor     eax, eax
0x1800aa196  xor     edx, edx; Val
0x1800aa198  mov     [rsp+540h+Buffer], ax
0x1800aa19d  mov     r8d, 1FEh; Size
0x1800aa1a3  lea     rcx, [rsp+540h+var_50E]; void *
0x1800aa1a8  mov     r12, r9
0x1800aa1ab  call    memset_0
0x1800aa1b0  mov     edx, 3
0x1800aa1b5  lea     rcx, [rbp+440h+var_1E0]
0x1800aa1bc  lea     rax, aToastLaunchMsS; "\n<toast launch=\"ms-settings:network-v"...
0x1800aa1c3  lea     r8d, [rdx+7Dh]
0x1800aa1c7  movups  xmm0, xmmword ptr [rax]
0x1800aa1ca  movups  xmm1, xmmword ptr [rax+10h]
0x1800aa1ce  movups  xmmword ptr [rcx], xmm0
0x1800aa1d1  movups  xmm0, xmmword ptr [rax+20h]
0x1800aa1d5  movups  xmmword ptr [rcx+10h], xmm1
0x1800aa1d9  movups  xmm1, xmmword ptr [rax+30h]
0x1800aa1dd  movups  xmmword ptr [rcx+20h], xmm0
0x1800aa1e1  movups  xmm0, xmmword ptr [rax+40h]
0x1800aa1e5  movups  xmmword ptr [rcx+30h], xmm1
0x1800aa1e9  movups  xmm1, xmmword ptr [rax+50h]
0x1800aa1ed  movups  xmmword ptr [rcx+40h], xmm0
0x1800aa1f1  movups  xmm0, xmmword ptr [rax+60h]
0x1800aa1f5  movups  xmmword ptr [rcx+50h], xmm1
0x1800aa1f9  movups  xmm1, xmmword ptr [rax+70h]
0x1800aa1fd  add     rax, r8
0x1800aa200  movups  xmmword ptr [rcx+60h], xmm0
0x1800aa204  movups  xmmword ptr [rcx+70h], xmm1
0x1800aa208  add     rcx, r8
0x1800aa20b  sub     rdx, 1
0x1800aa20f  jnz     short loc_1800AA1C7
0x1800aa211  movups  xmm0, xmmword ptr [rax]
0x1800aa214  mov     rax, [rax+10h]
0x1800aa218  mov     edx, 2
0x1800aa21d  movups  xmmword ptr [rcx], xmm0
0x1800aa220  mov     [rcx+10h], rax
0x1800aa224  lea     rcx, [rbp+440h+var_310]
0x1800aa22b  lea     rax, aToastVisualBin; "\n<toast>\n    <visual>\n        <bindi"...
0x1800aa232  movups  xmm0, xmmword ptr [rax]
0x1800aa235  movups  xmm1, xmmword ptr [rax+10h]
0x1800aa239  movups  xmmword ptr [rcx], xmm0
0x1800aa23c  movups  xmm0, xmmword ptr [rax+20h]
0x1800aa240  movups  xmmword ptr [rcx+10h], xmm1
0x1800aa244  movups  xmm1, xmmword ptr [rax+30h]
0x1800aa248  movups  xmmword ptr [rcx+20h], xmm0
0x1800aa24c  movups  xmm0, xmmword ptr [rax+40h]
0x1800aa250  movups  xmmword ptr [rcx+30h], xmm1
0x1800aa254  movups  xmm1, xmmword ptr [rax+50h]
0x1800aa258  movups  xmmword ptr [rcx+40h], xmm0
0x1800aa25c  movups  xmm0, xmmword ptr [rax+60h]
0x1800aa260  movups  xmmword ptr [rcx+50h], xmm1
0x1800aa264  movups  xmm1, xmmword ptr [rax+70h]
0x1800aa268  add     rax, r8
0x1800aa26b  movups  xmmword ptr [rcx+60h], xmm0
0x1800aa26f  movups  xmmword ptr [rcx+70h], xmm1
0x1800aa273  add     rcx, r8
0x1800aa276  sub     rdx, 1
0x1800aa27a  jnz     short loc_1800AA232
0x1800aa27c  movups  xmm0, xmmword ptr [rax]
0x1800aa27f  movups  xmm1, xmmword ptr [rax+10h]
0x1800aa283  movzx   eax, word ptr [rax+20h]
0x1800aa287  movups  xmmword ptr [rcx], xmm0
0x1800aa28a  movups  xmmword ptr [rcx+10h], xmm1
0x1800aa28e  mov     [rcx+20h], ax
0x1800aa292  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::GetImpl(void)'::`2'::impl
0x1800aa299  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::__private_IsEnabled(void)
0x1800aa29e  test    al, al
0x1800aa2a0  jz      short loc_1800AA2B2
0x1800aa2a2  lea     rax, aToastDurationL; "\n<toast duration=\"long\">\n    <visua"...
0x1800aa2a9  lea     rsi, aToastDurationL_0; "\n<toast duration=\"long\" launch=\"ms-"...
0x1800aa2b0  jmp     short loc_1800AA2C0
0x1800aa2b2  lea     rsi, [rbp+440h+var_1E0]
0x1800aa2b9  lea     rax, [rbp+440h+var_310]
0x1800aa2c0  test    edi, edi
0x1800aa2c2  cmovz   rsi, rax
0x1800aa2c6  test    r12, r12
0x1800aa2c9  jz      loc_1800AA43B
0x1800aa2cf  test    r13, r13
0x1800aa2d2  jz      loc_1800AA43B
0x1800aa2d8  mov     qword ptr [r12], 0
0x1800aa2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa2e7  lea     r14, WPP_GLOBAL_Control
0x1800aa2ee  cmp     rcx, r14
0x1800aa2f1  jz      short loc_1800AA321
0x1800aa2f3  test    dword ptr [rcx+1Ch], 800h
0x1800aa2fa  jz      short loc_1800AA321
0x1800aa2fc  cmp     byte ptr [rcx+19h], 5
0x1800aa300  jb      short loc_1800AA321
0x1800aa302  mov     rcx, [rcx+10h]
0x1800aa306  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800aa30d  mov     edx, 0Eh
0x1800aa312  mov     r9d, ebx
0x1800aa315  call    WPP_SF_d
0x1800aa31a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa321  test    ebx, ebx
0x1800aa323  jz      loc_1800AA417
0x1800aa329  sub     ebx, 1
0x1800aa32c  jz      short loc_1800AA36E
0x1800aa32e  sub     ebx, 1
0x1800aa331  jz      short loc_1800AA367
0x1800aa333  sub     ebx, 1
0x1800aa336  jz      short loc_1800AA360
0x1800aa338  sub     ebx, 1
0x1800aa33b  jz      short loc_1800AA359
0x1800aa33d  sub     ebx, 1
0x1800aa340  jz      short loc_1800AA352
0x1800aa342  cmp     ebx, 1
0x1800aa345  jnz     loc_1800AA417
0x1800aa34b  mov     edi, 3EDh
0x1800aa350  jmp     short loc_1800AA373
0x1800aa352  mov     edi, 3EFh
0x1800aa357  jmp     short loc_1800AA373
0x1800aa359  mov     edi, 3EEh
0x1800aa35e  jmp     short loc_1800AA373
0x1800aa360  mov     edi, 3EBh
0x1800aa365  jmp     short loc_1800AA373
0x1800aa367  mov     edi, 3EAh
0x1800aa36c  jmp     short loc_1800AA373
0x1800aa36e  mov     edi, 3E9h
0x1800aa373  lea     rcx, aRasapi32Dll_0; "rasapi32.dll"
0x1800aa37a  call    cs:__imp_GetModuleHandleW
0x1800aa380  mov     r15, rax
0x1800aa383  test    rax, rax
0x1800aa386  jnz     short loc_1800AA3B3
0x1800aa388  call    cs:__imp_GetLastError
0x1800aa38e  test    eax, eax
0x1800aa390  jg      short loc_1800AA39C
0x1800aa392  call    cs:__imp_GetLastError
0x1800aa398  mov     ebx, eax
0x1800aa39a  jmp     short loc_1800AA3AB
0x1800aa39c  call    cs:__imp_GetLastError
0x1800aa3a2  movzx   ebx, ax
0x1800aa3a5  or      ebx, 80070000h
0x1800aa3ab  test    ebx, ebx
0x1800aa3ad  js      loc_1800AA47B
0x1800aa3b3  mov     r9d, 100h; cchBufferMax
0x1800aa3b9  lea     r8, [rsp+540h+Buffer]; lpBuffer
0x1800aa3be  mov     edx, edi; uID
0x1800aa3c0  mov     rcx, r15; hInstance
0x1800aa3c3  call    cs:__imp_LoadStringW
0x1800aa3c9  mov     ebx, eax
0x1800aa3cb  test    eax, eax
0x1800aa3cd  js      loc_1800AA47B
0x1800aa3d3  mov     r8, r13
0x1800aa3d6  mov     [rsp+540h+hMem], 0
0x1800aa3df  lea     rdx, [rsp+540h+hMem]; unsigned __int16 **
0x1800aa3e4  lea     rcx, [rsp+540h+Buffer]; lpSource
0x1800aa3e9  call    ?FormatToastMessage@@YAJPEBGPEAPEAGZZ; FormatToastMessage(ushort const *,ushort * *,...)
0x1800aa3ee  mov     ebx, eax
0x1800aa3f0  test    eax, eax
0x1800aa3f2  js      loc_1800AA47B
0x1800aa3f8  mov     r8, [rsp+540h+hMem]
0x1800aa3fd  mov     rdx, r12; unsigned __int16 **
0x1800aa400  mov     rcx, rsi; lpSource
0x1800aa403  call    ?FormatToastMessage@@YAJPEBGPEAPEAGZZ; FormatToastMessage(ushort const *,ushort * *,...)
0x1800aa408  mov     rcx, [rsp+540h+hMem]; hMem
0x1800aa40d  mov     ebx, eax
0x1800aa40f  call    cs:__imp_LocalFree
0x1800aa415  jmp     short loc_1800AA47B
0x1800aa417  mov     r9d, 80070057h
0x1800aa41d  mov     ebx, r9d
0x1800aa420  cmp     rcx, r14
0x1800aa423  jz      short loc_1800AA47B
0x1800aa425  test    dword ptr [rcx+1Ch], 800h
0x1800aa42c  jz      short loc_1800AA47B
0x1800aa42e  cmp     byte ptr [rcx+19h], 2
0x1800aa432  jb      short loc_1800AA47B
0x1800aa434  mov     edx, 0Fh
0x1800aa439  jmp     short loc_1800AA46B
0x1800aa43b  mov     r9d, 80070057h
0x1800aa441  mov     ebx, r9d
0x1800aa444  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa44b  lea     r14, WPP_GLOBAL_Control
0x1800aa452  cmp     rcx, r14
0x1800aa455  jz      short loc_1800AA47B
0x1800aa457  test    dword ptr [rcx+1Ch], 800h
0x1800aa45e  jz      short loc_1800AA47B
0x1800aa460  cmp     byte ptr [rcx+19h], 2
0x1800aa464  jb      short loc_1800AA47B
0x1800aa466  mov     edx, 0Dh
0x1800aa46b  mov     rcx, [rcx+10h]
0x1800aa46f  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800aa476  call    WPP_SF_d
0x1800aa47b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::GetImpl(void)'::`2'::impl
0x1800aa482  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_LongDuration_Toast>::__private_IsEnabled(void)
0x1800aa487  test    al, al
0x1800aa489  jz      short loc_1800AA4FC
0x1800aa48b  test    r12, r12
0x1800aa48e  jz      short loc_1800AA4C9
0x1800aa490  mov     r9, [r12]
0x1800aa494  test    r9, r9
0x1800aa497  jz      short loc_1800AA4C9
0x1800aa499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa4a0  cmp     rcx, r14
0x1800aa4a3  jz      short loc_1800AA4FC
0x1800aa4a5  test    dword ptr [rcx+1Ch], 800h
0x1800aa4ac  jz      short loc_1800AA4D0
0x1800aa4ae  cmp     byte ptr [rcx+19h], 5
0x1800aa4b2  jb      short loc_1800AA4D0
0x1800aa4b4  mov     rcx, [rcx+10h]
0x1800aa4b8  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800aa4bf  mov     edx, 10h
0x1800aa4c4  call    WPP_SF_S
0x1800aa4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa4d0  cmp     rcx, r14
0x1800aa4d3  jz      short loc_1800AA4FC
0x1800aa4d5  test    dword ptr [rcx+1Ch], 800h
0x1800aa4dc  jz      short loc_1800AA4FC
0x1800aa4de  cmp     byte ptr [rcx+19h], 6
0x1800aa4e2  jb      short loc_1800AA4FC
0x1800aa4e4  mov     rcx, [rcx+10h]
0x1800aa4e8  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800aa4ef  mov     edx, 11h
0x1800aa4f4  mov     r9d, ebx
0x1800aa4f7  call    WPP_SF_d
0x1800aa4fc  mov     eax, ebx
0x1800aa4fe  mov     rcx, [rbp+440h+var_40]
0x1800aa505  xor     rcx, rsp; StackCookie
0x1800aa508  call    __security_check_cookie
0x1800aa50d  mov     rbx, [rsp+540h+arg_10]
0x1800aa515  add     rsp, 510h
0x1800aa51c  pop     r15
0x1800aa51e  pop     r14
0x1800aa520  pop     r13
0x1800aa522  pop     r12
0x1800aa524  pop     rdi
0x1800aa525  pop     rsi
0x1800aa526  pop     rbp
0x1800aa527  retn
```
