# SBackendEntrySuccess

- ea: `0x180009540`
- end: `0x180009bd0`
- name: `SBackendEntrySuccess`
- size: `1680`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180008d40`
- `0x180009540`
- `0x18000abc0`
- `0x18000cf70`
- `0x180010ae0`
- `0x180010d40`
- `0x180012478`
- `0x1800214f0`
- `0x18002578c`
- `0x180027ae4`
- `0x18002830c`
- `0x180028724`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x1800096e3`
- `MobileNetworking!SetBufferAndLength` at `0x180009793`
- `MobileNetworking!SetBufferAndLength` at `0x180009839`
- `MobileNetworking!SetBufferAndLength` at `0x1800096e3`
- `MobileNetworking!SetBufferAndLength` at `0x180009793`
- `MobileNetworking!SetBufferAndLength` at `0x180009839`
- `MobileNetworking!AllocateMemory` at `0x180009a37`
- `MobileNetworking!AllocateMemory` at `0x180009a37`

## string_xrefs

- `0x180009a26`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall SBackendEntrySuccess(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v2; // r14d
  __int64 v3; // rbx
  _QWORD *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebp
  unsigned int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  unsigned int v12; // ebp
  unsigned int v13; // eax
  unsigned int v14; // edi
  _QWORD *v15; // rcx
  unsigned int v16; // ebp
  unsigned int v17; // eax
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  int updated; // eax
  __int64 result; // rax
  unsigned int v22; // edi
  _BYTE *v23; // rcx
  int v24; // eax
  _QWORD *v25; // rcx
  unsigned int v26; // ebp
  unsigned int v27; // ebx
  unsigned int v28; // eax
  _QWORD *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v2 = *(_DWORD *)(v1 + 20);
  v3 = v1 + 2496;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 118, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(v1 + 2508) )
  {
    v5 = EapCacheIdentityInfo((EAP_SESSIONID *)(v1 + 2496));
    if ( v5 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 119, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v5);
    v6 = EapNotifyNetworkInfoData(v1 + 2496);
    if ( !v6 )
      goto LABEL_13;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 120, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v6);
LABEL_13:
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( *(_DWORD *)(v1 + 2708) )
  {
    *(_DWORD *)(v1 + 2708) = 0;
    if ( *(_DWORD *)(v1 + 2712) )
    {
      v7 = MSMNotifyDiagnosticsHint(v1, 1, 3);
      if ( v7 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 121, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v7);
      *(_DWORD *)(v1 + 2712) = 0;
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 0x10) != 0 )
  {
    WPP_SF_d(v4[7], 122, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
    v4 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(*(_QWORD *)v3 + 20LL);
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_(v4[7], 28, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v9 = SetBufferAndLength(v1 + 2632, 0, 0, 0);
  *(_DWORD *)(v1 + 2624) = -1;
  v10 = v9;
  if ( !v9 )
    goto LABEL_32;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8, v9);
LABEL_32:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v11[7], 30, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v10);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_36:
  v12 = *(_DWORD *)(*(_QWORD *)v3 + 20LL);
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_(v11[7], 31, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v13 = SetBufferAndLength(v1 + 2640, 0, 0, 0);
  v14 = v13;
  if ( !v13 )
    goto LABEL_43;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_47;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v12, v13);
LABEL_43:
    v15 = WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v15[7], 33, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v14);
    v15 = WPP_GLOBAL_Control;
  }
LABEL_47:
  v16 = *(_DWORD *)(*(_QWORD *)v3 + 20LL);
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x800) != 0 )
    WPP_SF_(v15[7], 34, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v17 = SetBufferAndLength(v1 + 2648, 0, 0, 0);
  v18 = v17;
  if ( !v17 )
    goto LABEL_54;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_58;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v16, v17);
LABEL_54:
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 17) & 0x800) != 0 )
    WPP_SF_D(v19[7], 36, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v18);
LABEL_58:
  if ( *(_DWORD *)(v1 + 2828) == 3
    && !(unsigned int)SupplicantIsDoingPLAP(v1 + 2384)
    && (*(_DWORD *)(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)v3 + 2760LL) + 16LL)
                  + *(_QWORD *)(*(_QWORD *)v3 + 2760LL)
                  + 20LL)
      & 4) == 0 )
  {
    updated = EapUpdateUserDataInMemoryAndInPersistentStore(v1 + 2496, 0, 0, 4);
    if ( updated )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          123,
          WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids,
          v2,
          updated);
    }
  }
  if ( (*(_BYTE *)(v1 + 2784) & 0x20) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)(v1 + 2744) + 12LL) &= ~0x20u;
    result = MSMSetOneXConnectionProfile(v1, *(_DWORD *)(*(_QWORD *)(v1 + 2744) + 4LL), *(_QWORD *)(v1 + 2744));
    v22 = result;
    if ( (_DWORD)result )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_107;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 124, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, result);
      goto LABEL_106;
    }
  }
  *(_QWORD *)(v1 + 2680) = 0;
  *(_QWORD *)(v1 + 2688) = 0;
  *(_QWORD *)(v1 + 2700) = 0;
  *(_QWORD *)(v1 + 2708) = 0;
  v24 = EapEndSession((EAP_SESSIONID *)(v1 + 2496));
  if ( !v24 )
    goto LABEL_74;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 125, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, v24);
LABEL_74:
    v25 = WPP_GLOBAL_Control;
  }
  v26 = *(_DWORD *)(v1 + 20);
  v31 = 0;
  if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v25[7], 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v25 = WPP_GLOBAL_Control;
  }
  v27 = *(_DWORD *)(v1 + 20);
  if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 17) & 0x800) != 0 )
    WPP_SF_(v25[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v28 = AllocateMemory(56, &v31, "OneXCreateEvent", 67);
  v22 = v28;
  if ( !v28 )
  {
    *(_DWORD *)(v31 + 16) = 18;
    *(_DWORD *)(v31 + 32) = 0;
    *(_QWORD *)(v31 + 24) = v1;
    goto LABEL_86;
  }
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_98:
    OneXDeleteEvent(v31);
    goto LABEL_99;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v27, v28);
LABEL_86:
    v29 = WPP_GLOBAL_Control;
  }
  if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v29[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v22);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v22 )
  {
    if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 68) & 1) != 0 )
      WPP_SF_dd(v29[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v26, v22);
    goto LABEL_98;
  }
  v30 = QueueSupplicantEvent(v31);
  v22 = v30;
  if ( v30 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v26, v30);
    goto LABEL_98;
  }
LABEL_99:
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v22);
    v23 = WPP_GLOBAL_Control;
  }
  if ( !v22 )
    goto LABEL_107;
  if ( v23 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v23[68] & 1) == 0 )
      goto LABEL_107;
    WPP_SF_dd(*((_QWORD *)v23 + 7), 126, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, v22);
LABEL_106:
    v23 = WPP_GLOBAL_Control;
LABEL_107:
    if ( v23 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v23 + 17) & 0x800) != 0 )
      WPP_SF_D(*((_QWORD *)v23 + 7), 127, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v22);
  }
  return v22;
}

```

## disassembly

```asm
0x180009540  mov     [rsp+arg_8], rbx
0x180009545  mov     [rsp+arg_10], rbp
0x18000954a  push    rsi
0x18000954b  push    rdi
0x18000954c  push    r12
0x18000954e  push    r14
0x180009550  push    r15
0x180009552  sub     rsp, 30h
0x180009556  mov     rsi, [rcx+18h]
0x18000955a  mov     r14d, [rsi+14h]
0x18000955e  lea     rbx, [rsi+9C0h]
0x180009565  mov     rcx, cs:WPP_GLOBAL_Control
0x18000956c  lea     r15, WPP_GLOBAL_Control
0x180009573  cmp     rcx, r15
0x180009576  jz      short loc_18000959D
0x180009578  test    dword ptr [rcx+44h], 800h
0x18000957f  jz      short loc_18000959D
0x180009581  mov     rcx, [rcx+38h]
0x180009585  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x18000958c  mov     edx, 76h ; 'v'
0x180009591  call    WPP_SF_
0x180009596  mov     rcx, cs:WPP_GLOBAL_Control
0x18000959d  cmp     dword ptr [rbx+0Ch], 0
0x1800095a1  jz      short loc_180009616
0x1800095a3  mov     rcx, rbx
0x1800095a6  call    EapCacheIdentityInfo
0x1800095ab  test    eax, eax
0x1800095ad  jz      short loc_1800095D9
0x1800095af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095b6  cmp     rcx, r15
0x1800095b9  jz      short loc_1800095D9
0x1800095bb  test    byte ptr [rcx+44h], 1
0x1800095bf  jz      short loc_1800095D9
0x1800095c1  mov     rcx, [rcx+38h]
0x1800095c5  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x1800095cc  mov     edx, 77h ; 'w'
0x1800095d1  mov     r9d, eax
0x1800095d4  call    WPP_SF_D
0x1800095d9  mov     rcx, rbx
0x1800095dc  call    EapNotifyNetworkInfoData
0x1800095e1  test    eax, eax
0x1800095e3  jz      short loc_18000960F
0x1800095e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ec  cmp     rcx, r15
0x1800095ef  jz      short loc_180009616
0x1800095f1  test    byte ptr [rcx+44h], 1
0x1800095f5  jz      short loc_180009616
0x1800095f7  mov     rcx, [rcx+38h]
0x1800095fb  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009602  mov     edx, 78h ; 'x'
0x180009607  mov     r9d, eax
0x18000960a  call    WPP_SF_D
0x18000960f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009616  xor     r12d, r12d
0x180009619  cmp     [rbx+0D4h], r12d
0x180009620  jz      short loc_180009681
0x180009622  mov     [rbx+0D4h], r12d
0x180009629  cmp     [rbx+0D8h], r12d
0x180009630  jz      short loc_18000967A
0x180009632  mov     edx, 1
0x180009637  mov     r8d, 3
0x18000963d  mov     rcx, rsi
0x180009640  call    MSMNotifyDiagnosticsHint
0x180009645  test    eax, eax
0x180009647  jz      short loc_180009673
0x180009649  mov     rcx, cs:WPP_GLOBAL_Control
0x180009650  cmp     rcx, r15
0x180009653  jz      short loc_180009673
0x180009655  test    byte ptr [rcx+44h], 1
0x180009659  jz      short loc_180009673
0x18000965b  mov     rcx, [rcx+38h]
0x18000965f  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009666  mov     edx, 79h ; 'y'
0x18000966b  mov     r9d, eax
0x18000966e  call    WPP_SF_D
0x180009673  mov     [rbx+0D8h], r12d
0x18000967a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009681  cmp     rcx, r15
0x180009684  jz      short loc_1800096AB
0x180009686  test    byte ptr [rcx+44h], 10h
0x18000968a  jz      short loc_1800096AB
0x18000968c  mov     rcx, [rcx+38h]
0x180009690  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009697  mov     edx, 7Ah ; 'z'
0x18000969c  mov     r9d, r14d
0x18000969f  call    WPP_SF_d
0x1800096a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096ab  mov     rax, [rbx]
0x1800096ae  mov     ebp, [rax+14h]
0x1800096b1  cmp     rcx, r15
0x1800096b4  jz      short loc_1800096D4
0x1800096b6  test    dword ptr [rcx+44h], 800h
0x1800096bd  jz      short loc_1800096D4
0x1800096bf  mov     rcx, [rcx+38h]
0x1800096c3  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800096ca  mov     edx, 1Ch
0x1800096cf  call    WPP_SF_
0x1800096d4  lea     rcx, [rbx+88h]
0x1800096db  xor     r9d, r9d
0x1800096de  xor     r8d, r8d
0x1800096e1  xor     edx, edx
0x1800096e3  call    cs:__imp_SetBufferAndLength
0x1800096e9  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x1800096f3  mov     edi, eax
0x1800096f5  test    eax, eax
0x1800096f7  jz      short loc_180009727
0x1800096f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009700  cmp     rcx, r15
0x180009703  jz      short loc_18000975B
0x180009705  test    byte ptr [rcx+44h], 1
0x180009709  jz      short loc_18000972E
0x18000970b  mov     rcx, [rcx+38h]
0x18000970f  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009716  mov     edx, 1Dh
0x18000971b  mov     [rsp+58h+var_38], eax
0x18000971f  mov     r9d, ebp
0x180009722  call    WPP_SF_dd
0x180009727  mov     rcx, cs:WPP_GLOBAL_Control
0x18000972e  cmp     rcx, r15
0x180009731  jz      short loc_18000975B
0x180009733  test    dword ptr [rcx+44h], 800h
0x18000973a  jz      short loc_18000975B
0x18000973c  mov     rcx, [rcx+38h]
0x180009740  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009747  mov     edx, 1Eh
0x18000974c  mov     r9d, edi
0x18000974f  call    WPP_SF_D
0x180009754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000975b  mov     rax, [rbx]
0x18000975e  mov     ebp, [rax+14h]
0x180009761  cmp     rcx, r15
0x180009764  jz      short loc_180009784
0x180009766  test    dword ptr [rcx+44h], 800h
0x18000976d  jz      short loc_180009784
0x18000976f  mov     rcx, [rcx+38h]
0x180009773  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18000977a  mov     edx, 1Fh
0x18000977f  call    WPP_SF_
0x180009784  lea     rcx, [rbx+90h]
0x18000978b  xor     r9d, r9d
0x18000978e  xor     r8d, r8d
0x180009791  xor     edx, edx
0x180009793  call    cs:__imp_SetBufferAndLength
0x180009799  mov     edi, eax
0x18000979b  test    eax, eax
0x18000979d  jz      short loc_1800097CD
0x18000979f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097a6  cmp     rcx, r15
0x1800097a9  jz      short loc_180009801
0x1800097ab  test    byte ptr [rcx+44h], 1
0x1800097af  jz      short loc_1800097D4
0x1800097b1  mov     rcx, [rcx+38h]
0x1800097b5  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800097bc  mov     edx, 20h ; ' '
0x1800097c1  mov     [rsp+58h+var_38], eax
0x1800097c5  mov     r9d, ebp
0x1800097c8  call    WPP_SF_dd
0x1800097cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097d4  cmp     rcx, r15
0x1800097d7  jz      short loc_180009801
0x1800097d9  test    dword ptr [rcx+44h], 800h
0x1800097e0  jz      short loc_180009801
0x1800097e2  mov     rcx, [rcx+38h]
0x1800097e6  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800097ed  mov     edx, 21h ; '!'
0x1800097f2  mov     r9d, edi
0x1800097f5  call    WPP_SF_D
0x1800097fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009801  mov     rax, [rbx]
0x180009804  mov     ebp, [rax+14h]
0x180009807  cmp     rcx, r15
0x18000980a  jz      short loc_18000982A
0x18000980c  test    dword ptr [rcx+44h], 800h
0x180009813  jz      short loc_18000982A
0x180009815  mov     rcx, [rcx+38h]
0x180009819  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009820  mov     edx, 22h ; '"'
0x180009825  call    WPP_SF_
0x18000982a  lea     rcx, [rbx+98h]
0x180009831  xor     r9d, r9d
0x180009834  xor     r8d, r8d
0x180009837  xor     edx, edx
0x180009839  call    cs:__imp_SetBufferAndLength
0x18000983f  mov     edi, eax
0x180009841  test    eax, eax
0x180009843  jz      short loc_180009873
0x180009845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000984c  cmp     rcx, r15
0x18000984f  jz      short loc_1800098A0
0x180009851  test    byte ptr [rcx+44h], 1
0x180009855  jz      short loc_18000987A
0x180009857  mov     rcx, [rcx+38h]
0x18000985b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009862  mov     edx, 23h ; '#'
0x180009867  mov     [rsp+58h+var_38], eax
0x18000986b  mov     r9d, ebp
0x18000986e  call    WPP_SF_dd
0x180009873  mov     rcx, cs:WPP_GLOBAL_Control
0x18000987a  cmp     rcx, r15
0x18000987d  jz      short loc_1800098A0
0x18000987f  test    dword ptr [rcx+44h], 800h
0x180009886  jz      short loc_1800098A0
0x180009888  mov     rcx, [rcx+38h]
0x18000988c  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009893  mov     edx, 24h ; '$'
0x180009898  mov     r9d, edi
0x18000989b  call    WPP_SF_D
0x1800098a0  cmp     dword ptr [rsi+0B0Ch], 3
0x1800098a7  lea     rcx, [rsi+950h]
0x1800098ae  jnz     short loc_180009914
0x1800098b0  call    SupplicantIsDoingPLAP
0x1800098b5  test    eax, eax
0x1800098b7  jnz     short loc_180009914
0x1800098b9  mov     rax, [rbx]
0x1800098bc  mov     rcx, [rax+0AC8h]
0x1800098c3  mov     eax, [rcx+10h]
0x1800098c6  mov     edx, [rax+rcx+14h]
0x1800098ca  test    dl, 4
0x1800098cd  jnz     short loc_180009914
0x1800098cf  mov     r9d, 4
0x1800098d5  xor     r8d, r8d
0x1800098d8  xor     edx, edx
0x1800098da  mov     rcx, rbx
0x1800098dd  call    EapUpdateUserDataInMemoryAndInPersistentStore
0x1800098e2  test    eax, eax
0x1800098e4  jz      short loc_180009914
0x1800098e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ed  cmp     rcx, r15
0x1800098f0  jz      short loc_180009914
0x1800098f2  test    byte ptr [rcx+44h], 1
0x1800098f6  jz      short loc_180009914
0x1800098f8  mov     rcx, [rcx+38h]
0x1800098fc  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009903  mov     edx, 7Bh ; '{'
0x180009908  mov     [rsp+58h+var_38], eax
0x18000990c  mov     r9d, r14d
0x18000990f  call    WPP_SF_dd
0x180009914  test    byte ptr [rsi+0AE0h], 20h
0x18000991b  jz      short loc_18000996B
0x18000991d  mov     rax, [rsi+0AB8h]
0x180009924  mov     rcx, rsi
0x180009927  and     dword ptr [rax+0Ch], 0FFFFFFDFh
0x18000992b  mov     rdx, [rsi+0AB8h]
0x180009932  mov     r8, rdx
0x180009935  mov     edx, [rdx+4]
0x180009938  call    MSMSetOneXConnectionProfile
0x18000993d  mov     edi, eax
0x18000993f  test    eax, eax
0x180009941  jz      short loc_18000996B
0x180009943  mov     rcx, cs:WPP_GLOBAL_Control
0x18000994a  cmp     rcx, r15
0x18000994d  jz      loc_180009BB9
0x180009953  test    byte ptr [rcx+44h], 1
0x180009957  jz      loc_180009B91
0x18000995d  mov     edx, 7Ch ; '|'
0x180009962  mov     [rsp+58h+var_38], eax
0x180009966  jmp     loc_180009B77
0x18000996b  mov     rcx, rbx
0x18000996e  mov     [rbx+0B8h], r12
0x180009975  mov     [rbx+0C0h], r12
0x18000997c  mov     [rbx+0CCh], r12
0x180009983  mov     [rbx+0D4h], r12
0x18000998a  call    EapEndSession
0x18000998f  test    eax, eax
0x180009991  jz      short loc_1800099C1
0x180009993  mov     rcx, cs:WPP_GLOBAL_Control
0x18000999a  cmp     rcx, r15
0x18000999d  jz      short loc_1800099C8
0x18000999f  test    byte ptr [rcx+44h], 1
0x1800099a3  jz      short loc_1800099C8
0x1800099a5  mov     rcx, [rcx+38h]
0x1800099a9  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x1800099b0  mov     edx, 7Dh ; '}'
0x1800099b5  mov     [rsp+58h+var_38], eax
0x1800099b9  mov     r9d, r14d
0x1800099bc  call    WPP_SF_dd
0x1800099c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099c8  mov     ebp, [rsi+14h]
0x1800099cb  mov     [rsp+58h+arg_0], r12
0x1800099d0  cmp     rcx, r15
0x1800099d3  jz      short loc_1800099FA
0x1800099d5  test    dword ptr [rcx+44h], 800h
0x1800099dc  jz      short loc_1800099FA
0x1800099de  mov     rcx, [rcx+38h]
0x1800099e2  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x1800099e9  mov     edx, 12h
0x1800099ee  call    WPP_SF_
0x1800099f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099fa  mov     ebx, [rsi+14h]
0x1800099fd  cmp     rcx, r15
0x180009a00  jz      short loc_180009A20
0x180009a02  test    dword ptr [rcx+44h], 800h
0x180009a09  jz      short loc_180009A20
0x180009a0b  mov     rcx, [rcx+38h]
0x180009a0f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180009a16  mov     edx, 0Ah
0x180009a1b  call    WPP_SF_
0x180009a20  mov     r9d, 43h ; 'C'
0x180009a26  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x180009a2d  lea     rdx, [rsp+58h+arg_0]
  ... truncated ...
```
