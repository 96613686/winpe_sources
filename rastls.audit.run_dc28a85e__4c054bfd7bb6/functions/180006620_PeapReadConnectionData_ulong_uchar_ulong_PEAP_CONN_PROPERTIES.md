# PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)

- ea: `0x180006620`
- end: `0x18000694f`
- name: `?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z`
- size: `815`
- prototype: `unsigned int(unsigned int, unsigned __int8 *, unsigned int, struct _PEAP_CONN_PROPERTIES **)`
- caller_count: `11`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180002500`
- `0x18000437c`
- `0x180005060`
- `0x1800055e0`
- `0x180005be0`
- `0x180058618`
- `0x18005c4f0`
- `0x18005d270`
- `0x180061fc4`
- `0x180062a50`
- `0x180070884`

## callees

- `0x180004d90`
- `0x180004e80`
- `0x180005010`
- `0x180006620`
- `0x180007d00`
- `0x1800189a0`
- `0x180020d80`
- `0x180038e4c`
- `0x180060158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000669a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000685a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000669a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000685a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006686`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006846`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006686`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006933`
- `rtutils!TraceDumpExA` at `0x1800067f9`
- `rtutils!TraceDumpExA` at `0x1800067f9`

## pseudocode

```c
__int64 __fastcall PeapReadConnectionData(char a1, unsigned __int8 *a2, unsigned int a3, BYTE **a4)
{
  SIZE_T v5; // rdi
  BYTE *v8; // rax
  BYTE *v9; // rbx
  DWORD LastError; // eax
  unsigned int v11; // edi
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned __int64 v16; // rax
  unsigned int v17; // r8d
  __int64 v18; // rax
  __int64 v19; // rdx
  struct _PEAP_CONN_PROPERTIES *v20; // rax
  struct _PEAP_ENTRY_CONN_PROPERTIES *v21; // rax
  struct _PEAP_ENTRY_CONN_PROPERTIES *v23; // [rsp+40h] [rbp-48h] BYREF

  v5 = a3;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, a3);
  if ( (unsigned int)v5 >= 0x24 && a2 )
  {
    v8 = (BYTE *)LocalAlloc(0x40u, v5);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v11 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v13 = 15;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, LastError);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
    memcpy_0(v8, a2, v5);
    if ( *((_DWORD *)v9 + 1) != (_DWORD)v5 )
      goto LABEL_22;
    v14 = *((_DWORD *)v9 + 5);
    v15 = v14 + 16;
    if ( v14 + 16 < v14 )
      goto LABEL_22;
    v16 = 16LL * *((unsigned int *)v9 + 2);
    if ( v16 > 0xFFFFFFFF )
      goto LABEL_22;
    if ( (unsigned int)v16 + v15 < v15 )
      goto LABEL_22;
    if ( (unsigned int)v16 + v15 > (unsigned int)v5 )
      goto LABEL_22;
    if ( v14 < 0x14 )
      goto LABEL_22;
    if ( !(unsigned int)IsEaptlsConnPropV1Valid(v9 + 16) )
      goto LABEL_22;
    v17 = *((_DWORD *)v9 + 2);
    if ( v17 )
    {
      v18 = -1;
      v19 = (__int64)&v9[16 * *((unsigned int *)v9 + 7) + 32 + 8 * *((unsigned int *)v9 + 7)];
      do
        ++v18;
      while ( *(_WORD *)(v19 + 2 * v18) );
      if ( !(unsigned int)IsPeapEntryArrayInPeapConnPropValid(
                            (struct _PEAP_ENTRY_CONN_PROPERTIES *)(v19 + 2 * (v18 + 1)),
                            (int)v5 + (int)v9 - ((int)v19 + 2 * ((int)v18 + 1)),
                            v17) )
        goto LABEL_22;
    }
    if ( !(unsigned int)IsIdentityPrivacyInPeapConnPropValid((struct _PEAP_CONN_PROPERTIES *)v9) )
    {
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
LABEL_24:
        if ( (unsigned int)v5 >= 0x100 )
          LODWORD(v5) = 256;
        TraceDumpExA(g_dwEapTlsTraceId, 1u, v9, v5, 1u, 1, 0);
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids);
        v11 = 13;
        goto LABEL_42;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids);
LABEL_22:
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids,
          (unsigned int)v5);
      goto LABEL_24;
    }
    *((_DWORD *)v9 + 6) |= 1u;
    *((_DWORD *)v9 + 1) = v5;
LABEL_41:
    v11 = 0;
    *a4 = v9;
    v9 = 0;
    goto LABEL_42;
  }
  v20 = (struct _PEAP_CONN_PROPERTIES *)LocalAlloc(0x40u, 0x37u);
  v9 = (BYTE *)v20;
  if ( v20 )
  {
    *((_DWORD *)v20 + 6) |= 0x11u;
    *((_DWORD *)v20 + 3) |= 1u;
    *(_DWORD *)v20 = 1;
    *((_DWORD *)v20 + 1) = 55;
    *((_DWORD *)v20 + 4) = 2;
    *((_DWORD *)v20 + 5) = 22;
    *((_DWORD *)v20 + 2) = 1;
    PeapGetFirstEntryConnProp(v20, &v23);
    if ( a1 < 0 )
    {
      *((_DWORD *)v9 + 6) |= 4u;
      if ( !(unsigned int)isMachineJoinedToDomain() )
      {
        *((_DWORD *)v9 + 6) |= 0x200u;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids);
      }
    }
    if ( (a1 & 1) != 0 )
      *((_DWORD *)v9 + 6) |= 4u;
    v21 = v23;
    *(_DWORD *)v23 = 1;
    *((_DWORD *)v21 + 1) = 15;
    *((_DWORD *)v21 + 2) = 26;
    goto LABEL_41;
  }
  LastError = GetLastError();
  v11 = LastError;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v13 = 13;
    goto LABEL_33;
  }
LABEL_42:
  LocalFree(v9);
  return v11;
}

```

## disassembly

```asm
0x180006620  push    rbx
0x180006622  push    rbp
0x180006623  push    rsi
0x180006624  push    rdi
0x180006625  push    r12
0x180006627  push    r14
0x180006629  sub     rsp, 58h
0x18000662d  mov     r14, r9
0x180006630  mov     edi, r8d
0x180006633  mov     rsi, rdx
0x180006636  mov     [rsp+88h+var_48], 0
0x18000663f  mov     ebp, ecx
0x180006641  mov     rcx, cs:WPP_GLOBAL_Control
0x180006648  lea     r12, WPP_GLOBAL_Control
0x18000664f  cmp     rcx, r12
0x180006652  jz      short loc_18000666C
0x180006654  mov     rcx, [rcx+10h]
0x180006658  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000665f  mov     edx, 0Ch
0x180006664  mov     r9d, edi
0x180006667  call    WPP_SF_d
0x18000666c  cmp     edi, 24h ; '$'
0x18000666f  jb      loc_18000683C
0x180006675  test    rsi, rsi
0x180006678  jz      loc_18000683C
0x18000667e  mov     rdx, rdi; uBytes
0x180006681  mov     ecx, 40h ; '@'; uFlags
0x180006686  call    cs:__imp_LocalAlloc
0x18000668d  nop     dword ptr [rax+rax+00h]
0x180006692  mov     rbx, rax
0x180006695  test    rax, rax
0x180006698  jnz     short loc_1800066C2
0x18000669a  call    cs:__imp_GetLastError
0x1800066a1  nop     dword ptr [rax+rax+00h]
0x1800066a6  mov     edi, eax
0x1800066a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066af  cmp     rcx, r12
0x1800066b2  jz      loc_180006930
0x1800066b8  mov     edx, 0Fh
0x1800066bd  jmp     loc_18000687D
0x1800066c2  mov     r8, rdi; Size
0x1800066c5  mov     rdx, rsi; Src
0x1800066c8  mov     rcx, rbx; void *
0x1800066cb  call    memcpy_0
0x1800066d0  cmp     [rbx+4], edi
0x1800066d3  jnz     loc_1800067A1
0x1800066d9  mov     ecx, [rbx+14h]
0x1800066dc  lea     rsi, [rbx+10h]
0x1800066e0  lea     edx, [rcx+10h]
0x1800066e3  cmp     edx, ecx
0x1800066e5  jb      loc_1800067A1
0x1800066eb  mov     eax, [rbx+8]
0x1800066ee  mov     r8d, 0FFFFFFFFh
0x1800066f4  shl     rax, 4
0x1800066f8  cmp     rax, r8
0x1800066fb  ja      loc_1800067A1
0x180006701  lea     r8d, [rax+rdx]
0x180006705  cmp     r8d, edx
0x180006708  jb      loc_1800067A1
0x18000670e  cmp     r8d, edi
0x180006711  ja      loc_1800067A1
0x180006717  cmp     ecx, 14h
0x18000671a  jb      loc_1800067A1
0x180006720  mov     rcx, rsi; lpbBytes
0x180006723  call    ?IsEaptlsConnPropV1Valid@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; IsEaptlsConnPropV1Valid(_EAPTLS_CONN_PROPERTIES_V1 *)
0x180006728  test    eax, eax
0x18000672a  jz      short loc_1800067A1
0x18000672c  mov     r8d, [rbx+8]; unsigned int
0x180006730  test    r8d, r8d
0x180006733  jz      short loc_180006770
0x180006735  mov     eax, [rsi+0Ch]
0x180006738  lea     rdx, [rax+1]
0x18000673c  lea     rdx, [rax+rdx*2]
0x180006740  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006747  lea     rdx, [rsi+rdx*8]
0x18000674b  nop     dword ptr [rax+rax+00h]
0x180006750  inc     rax
0x180006753  cmp     word ptr [rdx+rax*2], 0
0x180006758  jnz     short loc_180006750
0x18000675a  inc     rax
0x18000675d  lea     rcx, [rdx+rax*2]; struct _PEAP_ENTRY_CONN_PROPERTIES *
0x180006761  mov     edx, ebx
0x180006763  sub     edx, ecx
0x180006765  add     edx, edi; unsigned int
0x180006767  call    ?IsPeapEntryArrayInPeapConnPropValid@@YAHPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@KK@Z; IsPeapEntryArrayInPeapConnPropValid(_PEAP_ENTRY_CONN_PROPERTIES *,ulong,ulong)
0x18000676c  test    eax, eax
0x18000676e  jz      short loc_1800067A1
0x180006770  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x180006773  call    ?IsIdentityPrivacyInPeapConnPropValid@@YAHPEAU_PEAP_CONN_PROPERTIES@@@Z; IsIdentityPrivacyInPeapConnPropValid(_PEAP_CONN_PROPERTIES *)
0x180006778  test    eax, eax
0x18000677a  jnz     loc_180006830
0x180006780  mov     rcx, cs:WPP_GLOBAL_Control
0x180006787  cmp     rcx, r12
0x18000678a  jz      short loc_1800067C5
0x18000678c  mov     rcx, [rcx+10h]
0x180006790  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180006797  mov     edx, 1Eh
0x18000679c  call    WPP_SF_
0x1800067a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067a8  cmp     rcx, r12
0x1800067ab  jz      short loc_1800067C5
0x1800067ad  mov     rcx, [rcx+10h]
0x1800067b1  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800067b8  mov     edx, 1Fh
0x1800067bd  mov     r9d, edi
0x1800067c0  call    WPP_SF_d
0x1800067c5  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x1800067cb  mov     eax, 100h
0x1800067d0  cmp     edi, eax
0x1800067d2  mov     [rsp+88h+lpszPrefix], 0; lpszPrefix
0x1800067db  mov     [rsp+88h+bAddressPrefix], 1; bAddressPrefix
0x1800067e3  mov     r8, rbx; lpbBytes
0x1800067e6  cmovnb  edi, eax
0x1800067e9  mov     [rsp+88h+dwGroupSize], 1; dwGroupSize
0x1800067f1  mov     r9d, edi; dwByteCount
0x1800067f4  mov     edx, 1; dwFlags
0x1800067f9  call    cs:__imp_TraceDumpExA
0x180006800  nop     dword ptr [rax+rax+00h]
0x180006805  mov     rcx, cs:WPP_GLOBAL_Control
0x18000680c  cmp     rcx, r12
0x18000680f  jz      short loc_180006826
0x180006811  mov     rcx, [rcx+10h]
0x180006815  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000681c  mov     edx, 10h
0x180006821  call    WPP_SF_
0x180006826  mov     edi, 0Dh
0x18000682b  jmp     loc_180006930
0x180006830  or      dword ptr [rbx+18h], 1
0x180006834  mov     [rbx+4], edi
0x180006837  jmp     loc_180006929
0x18000683c  mov     edx, 37h ; '7'; uBytes
0x180006841  mov     ecx, 40h ; '@'; uFlags
0x180006846  call    cs:__imp_LocalAlloc
0x18000684d  nop     dword ptr [rax+rax+00h]
0x180006852  mov     rbx, rax
0x180006855  test    rax, rax
0x180006858  jnz     short loc_180006895
0x18000685a  call    cs:__imp_GetLastError
0x180006861  nop     dword ptr [rax+rax+00h]
0x180006866  mov     edi, eax
0x180006868  mov     rcx, cs:WPP_GLOBAL_Control
0x18000686f  cmp     rcx, r12
0x180006872  jz      loc_180006930
0x180006878  mov     edx, 0Dh
0x18000687d  mov     rcx, [rcx+10h]
0x180006881  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180006888  mov     r9d, eax
0x18000688b  call    WPP_SF_d
0x180006890  jmp     loc_180006930
0x180006895  or      dword ptr [rax+18h], 11h
0x180006899  lea     rdx, [rsp+88h+var_48]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18000689e  or      dword ptr [rax+0Ch], 1
0x1800068a2  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x1800068a5  mov     dword ptr [rax], 1
0x1800068ab  mov     dword ptr [rax+4], 37h ; '7'
0x1800068b2  mov     dword ptr [rax+10h], 2
0x1800068b9  mov     dword ptr [rax+14h], 16h
0x1800068c0  mov     dword ptr [rax+8], 1
0x1800068c7  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x1800068cc  test    bpl, bpl
0x1800068cf  jns     short loc_180006906
0x1800068d1  or      dword ptr [rbx+18h], 4
0x1800068d5  call    isMachineJoinedToDomain
0x1800068da  test    eax, eax
0x1800068dc  jnz     short loc_180006906
0x1800068de  or      dword ptr [rbx+18h], 200h
0x1800068e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ec  cmp     rcx, r12
0x1800068ef  jz      short loc_180006906
0x1800068f1  mov     rcx, [rcx+10h]
0x1800068f5  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800068fc  mov     edx, 0Eh
0x180006901  call    WPP_SF_
0x180006906  test    bpl, 1
0x18000690a  jz      short loc_180006910
0x18000690c  or      dword ptr [rbx+18h], 4
0x180006910  mov     rax, [rsp+88h+var_48]
0x180006915  mov     dword ptr [rax], 1
0x18000691b  mov     dword ptr [rax+4], 0Fh
0x180006922  mov     dword ptr [rax+8], 1Ah
0x180006929  xor     edi, edi
0x18000692b  mov     [r14], rbx
0x18000692e  xor     ebx, ebx
0x180006930  mov     rcx, rbx; hMem
0x180006933  call    cs:__imp_LocalFree
0x18000693a  nop     dword ptr [rax+rax+00h]
0x18000693f  mov     eax, edi
0x180006941  add     rsp, 58h
0x180006945  pop     r14
0x180006947  pop     r12
0x180006949  pop     rdi
0x18000694a  pop     rsi
0x18000694b  pop     rbp
0x18000694c  pop     rbx
0x18000694d  retn
```
