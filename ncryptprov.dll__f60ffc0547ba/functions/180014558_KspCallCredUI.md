# KspCallCredUI

- ea: `0x180014558`
- end: `0x180014be3`
- name: `KspCallCredUI`
- size: `1675`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b340`
- `0x180014160`
- `0x18002a0c0`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x1800140b4`
- `0x180014558`
- `0x180038970`
- `0x18004c200`
- `0x180052304`
- `0x180052480`
- `0x18005bf60`
- `0x18005c2bc`
- `0x18005c3fc`
- `0x18005c514`
- `0x18005c688`
- `0x18005ed0c`
- `0x180061f24`
- `0x180061fe8`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x1800148b7`
- `ntdll!WinSqmIncrementDWORD` at `0x180014962`
- `ntdll!WinSqmIncrementDWORD` at `0x180014b07`
- `ntdll!WinSqmIncrementDWORD` at `0x1800148b7`
- `ntdll!WinSqmIncrementDWORD` at `0x180014962`
- `ntdll!WinSqmIncrementDWORD` at `0x180014b07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001472e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001472e`

## string_xrefs

- `0x18001462a`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x1800146a8`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x18001470f`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x18001478d`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x1800147f6`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x18001482d`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`
- `0x180014939`: `onecore\ds\security\cryptoapi\ncrypt\storage\ui.c`

## pseudocode

```c
__int64 __fastcall KspCallCredUI(__int64 a1, unsigned int a2)
{
  int v4; // edx
  __int64 v5; // r15
  __int64 v6; // r13
  __int64 v7; // rsi
  unsigned int v8; // ebx
  unsigned int KeyProperties; // eax
  int v10; // r8d
  int v11; // r9d
  LPVOID v12; // r15
  unsigned int v13; // esi
  int v14; // r12d
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  void *v18; // rax
  int v19; // r8d
  int v20; // r9d
  unsigned int v21; // eax
  __int64 v22; // r9
  void *v23; // r14
  LPVOID v24; // rdx
  unsigned int v25; // eax
  unsigned int StringFromResourceFiles; // eax
  __int64 v27; // r9
  int v28; // eax
  int v29; // r9d
  __int64 v30; // r9
  const char *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rcx
  _BYTE *v37; // rcx
  __int64 v38; // rax
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v43; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  int v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  LPVOID v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h]
  int v49; // [rsp+90h] [rbp-70h] BYREF
  int v50; // [rsp+94h] [rbp-6Ch] BYREF
  UCHAR *v51; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  int *v54; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  __int64 v58; // [rsp+D0h] [rbp-30h]
  HLOCAL v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+190h] [rbp+90h] BYREF
  SIZE_T cb; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v65; // [rsp+1A8h] [rbp+A8h] BYREF

  v45 = 0;
  memset_0(&v56, 0, 0x88u);
  v50 = -8888;
  pv = &dword_18006B48C;
  v5 = 0;
  v54 = &dword_18006B48C;
  v6 = 0;
  LODWORD(cb) = 0;
  v7 = 0;
  v47 = 0;
  v43 = 0;
  v49 = 0;
  v65 = 0;
  v63 = 0;
  v53 = 0;
  v51 = 0;
  v42 = 0;
  hMem = 0;
  v44 = 0;
  v55 = 0;
  v40 = 0;
  v48 = 0;
  v46 = 0;
  if ( a1 )
  {
    KeyProperties = RetrieveKeyProperties(
                      a1,
                      a2,
                      (unsigned int)&pv,
                      (unsigned int)&v54,
                      (__int64)&v55,
                      (__int64)&v63,
                      (__int64)&v65,
                      (__int64)&v40,
                      (__int64)&v45);
    v8 = KeyProperties;
    if ( KeyProperties )
    {
      DebugTraceError(KeyProperties, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c", 910);
      goto LABEL_68;
    }
    v12 = pv;
    v13 = v65;
    v14 = v40;
    v15 = CNG_PackCredUIData(v63, (_DWORD)pv, v10, v11, v40, v65, (__int64)&cb, 0);
    v8 = v15;
    if ( v15 )
    {
      v16 = 931;
      v17 = v15;
LABEL_9:
      DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c", v16);
      v5 = v44;
LABEL_67:
      v7 = v46;
      goto LABEL_68;
    }
    v18 = CoTaskMemAlloc((unsigned int)cb);
    pv = v18;
    if ( !v18 )
    {
      v8 = -2146893810;
      v16 = 939;
      v17 = 2148073486LL;
      goto LABEL_9;
    }
    v21 = CNG_PackCredUIData(v63, (_DWORD)v12, v19, v20, v14, v13, (__int64)&cb, (__int64)v18);
    v8 = v21;
    if ( v21 )
    {
      v22 = 955;
LABEL_14:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c", v22);
      v5 = v44;
LABEL_15:
      v23 = pv;
LABEL_66:
      CoTaskMemFree(v23);
      goto LABEL_67;
    }
    v21 = LoadTitleAndDescriptionFormatStrings(v13, a2, &hMem, &v44);
    v8 = v21;
    if ( v21 )
    {
      v22 = 971;
      goto LABEL_14;
    }
    v24 = v12;
    v5 = v44;
    v25 = ConstructMessageContentBuffer(v44, v24, v54, &v53);
    v8 = v25;
    if ( v25 )
    {
      DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c", 987);
      goto LABEL_15;
    }
    if ( a2 == 1 )
    {
      StringFromResourceFiles = LoadStringFromResourceFiles(0x4B8u);
      v8 = StringFromResourceFiles;
      if ( StringFromResourceFiles )
      {
        v27 = 1000;
LABEL_23:
        DebugTraceError(
          StringFromResourceFiles,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c",
          v27);
        v6 = v48;
        goto LABEL_15;
      }
      StringFromResourceFiles = LoadStringFromResourceFiles(0x4B9u);
      v8 = StringFromResourceFiles;
      if ( StringFromResourceFiles )
      {
        v27 = 1009;
        goto LABEL_23;
      }
      v6 = v48;
      v61 = v48;
      v62 = v46;
      v60 = 768;
    }
    v57 = v55;
    v58 = v53;
    v59 = hMem;
    v56 = 136;
    if ( !v13 && (*(_BYTE *)(a1 + 428) & 0x20) != 0 )
    {
      WinSqmIncrementDWORD(0, 12418, 1);
      SqmAppcontainer();
    }
    v23 = pv;
    v28 = SPCryptPromptForCredentials(
            (unsigned int)&v56,
            v45,
            (unsigned int)&v50,
            (_DWORD)pv,
            cb,
            (__int64)&v47,
            (__int64)&v43,
            (__int64)&v49);
    if ( v28 )
    {
      if ( v28 == 1223 )
      {
        v8 = -2146893808;
      }
      else if ( v28 > 0 )
      {
        v8 = (unsigned __int16)v28 | 0x80070000;
      }
      else
      {
        v8 = v28;
      }
      v30 = 1053;
      v31 = "dwStatus";
      goto LABEL_37;
    }
    if ( !v13 && (*(_BYTE *)(a1 + 428) & 0x20) != 0 )
      WinSqmIncrementDWORD(0, 12223, 1);
    v28 = CNG_UnpackCredUIData(
            v43,
            (_DWORD)v47,
            (unsigned int)&v63,
            v29,
            (__int64)&v51,
            (__int64)&v42,
            (__int64)&v40,
            (__int64)&v65);
    v8 = v28;
    if ( v28 )
    {
      v30 = 1078;
LABEL_44:
      v31 = "Status";
LABEL_37:
      v32 = (unsigned int)v28;
LABEL_38:
      DebugTraceError(v32, v31, "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c", v30);
      goto LABEL_66;
    }
    *(_DWORD *)(a1 + 428) |= 2u;
    v34 = *(_DWORD *)(a1 + 428);
    if ( v65 == 3 )
    {
      if ( v42 != 8 )
      {
        v8 = -2146893792;
        v31 = "Status";
        v30 = 1094;
        v32 = 2148073504LL;
        goto LABEL_38;
      }
      v28 = DecryptPinAndSetPinHashOnKey(*(_QWORD *)v51, a1);
      v8 = v28;
      if ( v28 )
      {
        v30 = 1108;
        goto LABEL_44;
      }
    }
    else if ( v65 == 2 )
    {
      *(_DWORD *)(a1 + 428) = v34 | 1;
      if ( !v63 )
      {
        v63 = 1;
        v28 = SetUIKeyProperties(a1, (unsigned int)L"MSSP/UI Internal Flags", 18, (unsigned int)&v63, 4);
        v8 = v28;
        if ( v28 )
        {
          v30 = 1141;
          goto LABEL_44;
        }
        v35 = *(_QWORD *)(a1 + 416);
        if ( v35 )
        {
          if ( (*(_BYTE *)(v35 + 4) & 1) != 0 )
          {
            *(_DWORD *)(v35 + 4) = 2;
            v28 = SetUIKeyProperties(a1, (unsigned int)L"UI Policy", 12, *(_QWORD *)(a1 + 416), *(_DWORD *)(a1 + 424));
            v8 = v28;
            if ( v28 )
            {
              v30 = 1168;
              goto LABEL_44;
            }
          }
        }
      }
      v28 = ComputeAndSetPasswordHashOnTheKey(a1, v51, v42, v33);
      v8 = v28;
      if ( v28 )
      {
        v30 = 1183;
        goto LABEL_44;
      }
    }
    else if ( v40 )
    {
      if ( !v65 && (v34 & 0x20) != 0 )
      {
        WinSqmIncrementDWORD(0, 12224, 1);
        v28 = OpenConsentKeyForAppContainer(v36, a1, 1);
        v8 = v28;
        if ( v28 )
        {
          v30 = 1209;
          goto LABEL_44;
        }
      }
    }
    v8 = 0;
    goto LABEL_66;
  }
  v8 = 87;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_73;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v4,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c",
    (unsigned int)"Status",
    87,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\ui.c",
    121);
LABEL_68:
  v37 = v47;
  if ( v47 )
  {
    v38 = v43;
    if ( v43 )
    {
      do
      {
        *v37++ = 0;
        --v38;
      }
      while ( v38 );
      v37 = v47;
    }
    CoTaskMemFree(v37);
    v47 = 0;
  }
LABEL_73:
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    MSCryptFree(v5);
  if ( v6 )
    MSCryptFree(v6);
  if ( v7 )
    MSCryptFree(v7);
  if ( v53 )
    MSCryptFree(v53);
  return v8;
}

```

## disassembly

```asm
0x180014558  mov     [rsp-8+arg_8], rbx
0x18001455d  push    rbp
0x18001455e  push    rsi
0x18001455f  push    rdi
0x180014560  push    r12
0x180014562  push    r13
0x180014564  push    r14
0x180014566  push    r15
0x180014568  lea     rbp, [rsp-50h]
0x18001456d  sub     rsp, 150h
0x180014574  mov     r14d, edx
0x180014577  mov     rdi, rcx
0x18001457a  xor     r12d, r12d
0x18001457d  lea     rcx, [rbp+80h+var_C0]; void *
0x180014581  xor     edx, edx; Val
0x180014583  mov     [rsp+180h+var_110], r12d
0x180014588  mov     r8d, 88h; Size
0x18001458e  call    memset_0
0x180014593  mov     [rbp+80h+var_EC], 0FFFFDD48h
0x18001459a  lea     rax, dword_18006B48C
0x1800145a1  mov     [rsp+180h+pv], rax
0x1800145a6  mov     r15d, r12d
0x1800145a9  mov     [rbp+80h+var_D0], rax
0x1800145ad  mov     r13d, r12d
0x1800145b0  mov     dword ptr [rbp+80h+cb], r12d
0x1800145b7  mov     esi, r12d
0x1800145ba  mov     [rbp+80h+var_100], r12
0x1800145be  mov     [rsp+180h+var_11C], r12d
0x1800145c3  mov     [rbp+80h+var_F0], r12d
0x1800145c7  mov     [rbp+80h+arg_18], r12d
0x1800145ce  mov     [rbp+80h+arg_0], r12d
0x1800145d5  mov     [rbp+80h+var_D8], r12
0x1800145d9  mov     [rbp+80h+var_E8], r12
0x1800145dd  mov     [rsp+180h+var_120], r12d
0x1800145e2  mov     [rbp+80h+hMem], r12
0x1800145e6  mov     [rsp+180h+var_118], r12
0x1800145eb  mov     [rbp+80h+var_C8], r12
0x1800145ef  mov     [rsp+180h+var_130], r12d
0x1800145f4  mov     [rbp+80h+var_F8], r12
0x1800145f8  mov     [rsp+180h+var_108], r12
0x1800145fd  test    rdi, rdi
0x180014600  jnz     short loc_180014653
0x180014602  lea     ebx, [rdi+57h]
0x180014605  mov     rcx, cs:WPP_GLOBAL_Control
0x18001460c  lea     rax, WPP_GLOBAL_Control
0x180014613  cmp     rcx, rax
0x180014616  jz      loc_180014B7B
0x18001461c  test    byte ptr [rcx+1Ch], 1
0x180014620  jz      loc_180014B7B
0x180014626  mov     rcx, [rcx+10h]
0x18001462a  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014631  mov     dword ptr [rsp+180h+var_150], 379h
0x180014639  lea     r9, aStatus; "Status"
0x180014640  mov     [rsp+180h+var_158], r8
0x180014645  mov     dword ptr [rsp+180h+var_160], ebx
0x180014649  call    WPP_SF_sDsd
0x18001464e  jmp     loc_180014B49
0x180014653  lea     rax, [rsp+180h+var_110]
0x180014658  mov     edx, r14d
0x18001465b  mov     [rsp+180h+var_140], rax
0x180014660  lea     r9, [rbp+80h+var_D0]
0x180014664  lea     rax, [rsp+180h+var_130]
0x180014669  mov     rcx, rdi
0x18001466c  mov     [rsp+180h+var_148], rax
0x180014671  lea     r8, [rsp+180h+pv]
0x180014676  lea     rax, [rbp+80h+arg_18]
0x18001467d  mov     [rsp+180h+var_150], rax
0x180014682  lea     rax, [rbp+80h+arg_0]
0x180014689  mov     [rsp+180h+var_158], rax
0x18001468e  lea     rax, [rbp+80h+var_C8]
0x180014692  mov     [rsp+180h+var_160], rax
0x180014697  call    RetrieveKeyProperties
0x18001469c  mov     ebx, eax
0x18001469e  test    eax, eax
0x1800146a0  jz      short loc_1800146C2
0x1800146a2  mov     r9d, 38Eh
0x1800146a8  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800146af  lea     rdx, aStatus; "Status"
0x1800146b6  mov     ecx, eax
0x1800146b8  call    DebugTraceError
0x1800146bd  jmp     loc_180014B49
0x1800146c2  mov     r15, [rsp+180h+pv]
0x1800146c7  lea     rax, [rbp+80h+cb]
0x1800146ce  mov     esi, [rbp+80h+arg_18]
0x1800146d4  mov     rdx, r15
0x1800146d7  mov     ecx, [rbp+80h+arg_0]
0x1800146dd  mov     [rsp+180h+var_148], r12
0x1800146e2  mov     r12d, [rsp+180h+var_130]
0x1800146e7  mov     [rsp+180h+var_150], rax
0x1800146ec  mov     dword ptr [rsp+180h+var_158], esi
0x1800146f0  mov     dword ptr [rsp+180h+var_160], r12d
0x1800146f5  call    CNG_PackCredUIData
0x1800146fa  mov     ebx, eax
0x1800146fc  test    eax, eax
0x1800146fe  jz      short loc_180014728
0x180014700  mov     r9d, 3A3h
0x180014706  mov     ecx, eax
0x180014708  lea     rdx, aStatus; "Status"
0x18001470f  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014716  call    DebugTraceError
0x18001471b  mov     r15, [rsp+180h+var_118]
0x180014720  xor     r12d, r12d
0x180014723  jmp     loc_180014B44
0x180014728  mov     ecx, dword ptr [rbp+80h+cb]; cb
0x18001472e  call    cs:__imp_CoTaskMemAlloc
0x180014735  nop     dword ptr [rax+rax+00h]
0x18001473a  mov     [rsp+180h+pv], rax
0x18001473f  test    rax, rax
0x180014742  jnz     short loc_180014756
0x180014744  mov     ebx, 8009000Eh
0x180014749  mov     r9d, 3ABh
0x18001474f  mov     ecx, 8009000Eh
0x180014754  jmp     short loc_180014708
0x180014756  mov     ecx, [rbp+80h+arg_0]
0x18001475c  mov     rdx, r15
0x18001475f  mov     [rsp+180h+var_148], rax
0x180014764  lea     rax, [rbp+80h+cb]
0x18001476b  mov     [rsp+180h+var_150], rax
0x180014770  mov     dword ptr [rsp+180h+var_158], esi
0x180014774  mov     dword ptr [rsp+180h+var_160], r12d
0x180014779  call    CNG_PackCredUIData
0x18001477e  xor     r12d, r12d
0x180014781  mov     ebx, eax
0x180014783  test    eax, eax
0x180014785  jz      short loc_1800147B1
0x180014787  mov     r9d, 3BBh
0x18001478d  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014794  mov     ecx, eax
0x180014796  lea     rdx, aStatus; "Status"
0x18001479d  call    DebugTraceError
0x1800147a2  mov     r15, [rsp+180h+var_118]
0x1800147a7  mov     r14, [rsp+180h+pv]
0x1800147ac  jmp     loc_180014B35
0x1800147b1  lea     r9, [rsp+180h+var_118]
0x1800147b6  mov     edx, r14d
0x1800147b9  lea     r8, [rbp+80h+hMem]
0x1800147bd  mov     ecx, esi
0x1800147bf  call    LoadTitleAndDescriptionFormatStrings
0x1800147c4  mov     ebx, eax
0x1800147c6  test    eax, eax
0x1800147c8  jz      short loc_1800147D2
0x1800147ca  mov     r9d, 3CBh
0x1800147d0  jmp     short loc_18001478D
0x1800147d2  mov     r8, [rbp+80h+var_D0]
0x1800147d6  lea     r9, [rbp+80h+var_D8]
0x1800147da  mov     rdx, r15
0x1800147dd  mov     r15, [rsp+180h+var_118]
0x1800147e2  mov     rcx, r15
0x1800147e5  call    ConstructMessageContentBuffer
0x1800147ea  mov     ebx, eax
0x1800147ec  test    eax, eax
0x1800147ee  jz      short loc_18001480D
0x1800147f0  mov     r9d, 3DBh
0x1800147f6  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800147fd  lea     rdx, aStatus; "Status"
0x180014804  mov     ecx, eax
0x180014806  call    DebugTraceError
0x18001480b  jmp     short loc_1800147A7
0x18001480d  cmp     r14d, 1
0x180014811  jnz     short loc_180014880
0x180014813  lea     rdx, [rbp+80h+var_F8]
0x180014817  mov     ecx, 4B8h; uID
0x18001481c  call    LoadStringFromResourceFiles
0x180014821  mov     ebx, eax
0x180014823  test    eax, eax
0x180014825  jz      short loc_18001484B
0x180014827  mov     r9d, 3E8h
0x18001482d  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014834  mov     ecx, eax
0x180014836  lea     rdx, aStatus; "Status"
0x18001483d  call    DebugTraceError
0x180014842  mov     r13, [rbp+80h+var_F8]
0x180014846  jmp     loc_1800147A7
0x18001484b  lea     rdx, [rsp+180h+var_108]
0x180014850  mov     ecx, 4B9h; uID
0x180014855  call    LoadStringFromResourceFiles
0x18001485a  mov     ebx, eax
0x18001485c  test    eax, eax
0x18001485e  jz      short loc_180014868
0x180014860  mov     r9d, 3F1h
0x180014866  jmp     short loc_18001482D
0x180014868  mov     r13, [rbp+80h+var_F8]
0x18001486c  mov     rax, [rsp+180h+var_108]
0x180014871  mov     [rbp+80h+var_98], r13
0x180014875  mov     [rbp+80h+var_90], rax
0x180014879  mov     [rbp+80h+var_A0], 300h
0x180014880  mov     rax, [rbp+80h+var_C8]
0x180014884  mov     [rbp+80h+var_B8], rax
0x180014888  mov     rax, [rbp+80h+var_D8]
0x18001488c  mov     [rbp+80h+var_B0], rax
0x180014890  mov     rax, [rbp+80h+hMem]
0x180014894  mov     [rbp+80h+var_A8], rax
0x180014898  mov     [rbp+80h+var_C0], 88h
0x18001489f  test    esi, esi
0x1800148a1  jnz     short loc_1800148C8
0x1800148a3  test    byte ptr [rdi+1ACh], 20h
0x1800148aa  jz      short loc_1800148C8
0x1800148ac  mov     edx, 3082h
0x1800148b1  lea     r8d, [rsi+1]
0x1800148b5  xor     ecx, ecx
0x1800148b7  call    cs:__imp_WinSqmIncrementDWORD
0x1800148be  nop     dword ptr [rax+rax+00h]
0x1800148c3  call    SqmAppcontainer
0x1800148c8  mov     r14, [rsp+180h+pv]
0x1800148cd  lea     rax, [rbp+80h+var_F0]
0x1800148d1  mov     edx, [rsp+180h+var_110]
0x1800148d5  lea     r8, [rbp+80h+var_EC]
0x1800148d9  mov     [rsp+180h+var_148], rax
0x1800148de  lea     rcx, [rbp+80h+var_C0]
0x1800148e2  lea     rax, [rsp+180h+var_11C]
0x1800148e7  mov     r9, r14
0x1800148ea  mov     [rsp+180h+var_150], rax
0x1800148ef  lea     rax, [rbp+80h+var_100]
0x1800148f3  mov     [rsp+180h+var_158], rax
0x1800148f8  mov     eax, dword ptr [rbp+80h+cb]
0x1800148fe  mov     dword ptr [rsp+180h+var_160], eax
0x180014902  call    SPCryptPromptForCredentials
0x180014907  test    eax, eax
0x180014909  jz      short loc_18001494A
0x18001490b  cmp     eax, 4C7h
0x180014910  jnz     short loc_180014919
0x180014912  mov     ebx, 80090010h
0x180014917  jmp     short loc_18001492A
0x180014919  test    eax, eax
0x18001491b  jg      short loc_180014921
0x18001491d  mov     ebx, eax
0x18001491f  jmp     short loc_18001492A
0x180014921  movzx   ebx, ax
0x180014924  or      ebx, 80070000h
0x18001492a  mov     r9d, 41Dh
0x180014930  lea     rdx, aDwstatus; "dwStatus"
0x180014937  mov     ecx, eax
0x180014939  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014940  call    DebugTraceError
0x180014945  jmp     loc_180014B35
0x18001494a  test    esi, esi
0x18001494c  jnz     short loc_18001496E
0x18001494e  test    byte ptr [rdi+1ACh], 20h
0x180014955  jz      short loc_18001496E
0x180014957  mov     edx, 2FBFh
0x18001495c  lea     r8d, [rsi+1]
0x180014960  xor     ecx, ecx
0x180014962  call    cs:__imp_WinSqmIncrementDWORD
0x180014969  nop     dword ptr [rax+rax+00h]
0x18001496e  mov     rdx, [rbp+80h+var_100]
0x180014972  lea     rax, [rbp+80h+arg_18]
0x180014979  mov     ecx, [rsp+180h+var_11C]
0x18001497d  lea     r8, [rbp+80h+arg_0]
0x180014984  mov     [rsp+180h+var_148], rax
0x180014989  lea     rax, [rsp+180h+var_130]
0x18001498e  mov     [rsp+180h+var_150], rax
0x180014993  lea     rax, [rsp+180h+var_120]
0x180014998  mov     [rsp+180h+var_158], rax
0x18001499d  lea     rax, [rbp+80h+var_E8]
0x1800149a1  mov     [rsp+180h+var_160], rax
0x1800149a6  call    CNG_UnpackCredUIData
0x1800149ab  mov     ebx, eax
0x1800149ad  test    eax, eax
0x1800149af  jz      short loc_1800149C3
0x1800149b1  mov     r9d, 436h
0x1800149b7  lea     rdx, aStatus; "Status"
0x1800149be  jmp     loc_180014937
0x1800149c3  or      dword ptr [rdi+1ACh], 2
0x1800149ca  mov     ecx, [rbp+80h+arg_18]
0x1800149d0  mov     eax, [rdi+1ACh]
0x1800149d6  cmp     ecx, 3
0x1800149d9  jnz     short loc_180014A1F
0x1800149db  cmp     [rsp+180h+var_120], 8
0x1800149e0  jz      short loc_1800149FE
0x1800149e2  mov     ebx, 80090020h
0x1800149e7  lea     rdx, aStatus; "Status"
0x1800149ee  mov     r9d, 446h
0x1800149f4  mov     ecx, 80090020h
0x1800149f9  jmp     loc_180014939
0x1800149fe  mov     rax, [rbp+80h+var_E8]
0x180014a02  mov     rdx, rdi
0x180014a05  mov     rcx, [rax]
0x180014a08  call    DecryptPinAndSetPinHashOnKey
0x180014a0d  mov     ebx, eax
0x180014a0f  test    eax, eax
0x180014a11  jz      loc_180014B32
0x180014a17  mov     r9d, 454h
0x180014a1d  jmp     short loc_1800149B7
0x180014a1f  cmp     ecx, 2
0x180014a22  jnz     loc_180014AED
0x180014a28  or      eax, 1
0x180014a2b  mov     [rdi+1ACh], eax
0x180014a31  cmp     [rbp+80h+arg_0], r12d
0x180014a38  jnz     loc_180014ACB
0x180014a3e  lea     r8d, [rcx+10h]
0x180014a42  mov     [rbp+80h+arg_0], 1
0x180014a4c  mov     rcx, rdi
0x180014a4f  mov     dword ptr [rsp+180h+var_160], 4
0x180014a57  lea     r9, [rbp+80h+arg_0]
0x180014a5e  lea     rdx, aMsspUiInternal; "MSSP/UI Internal Flags"
0x180014a65  call    SetUIKeyProperties
0x180014a6a  mov     ebx, eax
0x180014a6c  test    eax, eax
0x180014a6e  jz      short loc_180014A7B
0x180014a70  mov     r9d, 475h
  ... truncated ...
```
