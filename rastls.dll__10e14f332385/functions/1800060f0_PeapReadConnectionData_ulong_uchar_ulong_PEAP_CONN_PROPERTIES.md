# PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)

- ea: `0x1800060f0`
- end: `0x1800063f6`
- name: `?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(char, unsigned __int8 *, unsigned int, BYTE **)`
- caller_count: `11`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180002490`
- `0x180003fec`
- `0x180004c10`
- `0x180005170`
- `0x180005730`
- `0x1800555d0`
- `0x180059200`
- `0x180059ee0`
- `0x18005e7f0`
- `0x18005f230`
- `0x18006c11c`

## callees

- `0x180004970`
- `0x180004a60`
- `0x180004bd0`
- `0x1800060f0`
- `0x1800075b0`
- `0x1800171d0`
- `0x18001f020`
- `0x18003623c`
- `0x18005caf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000630e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000630e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006156`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006300`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006156`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063e1`
- `rtutils!TraceDumpExA` at `0x1800062b9`
- `rtutils!TraceDumpExA` at `0x1800062b9`

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
0x1800060f0  push    rbx
0x1800060f2  push    rbp
0x1800060f3  push    rsi
0x1800060f4  push    rdi
0x1800060f5  push    r12
0x1800060f7  push    r14
0x1800060f9  sub     rsp, 58h
0x1800060fd  mov     r14, r9
0x180006100  mov     edi, r8d
0x180006103  mov     rsi, rdx
0x180006106  mov     [rsp+88h+var_48], 0
0x18000610f  mov     ebp, ecx
0x180006111  mov     rcx, cs:WPP_GLOBAL_Control
0x180006118  lea     r12, WPP_GLOBAL_Control
0x18000611f  cmp     rcx, r12
0x180006122  jz      short loc_18000613C
0x180006124  mov     rcx, [rcx+10h]
0x180006128  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000612f  mov     edx, 0Ch
0x180006134  mov     r9d, edi
0x180006137  call    WPP_SF_d
0x18000613c  cmp     edi, 24h ; '$'
0x18000613f  jb      loc_1800062F6
0x180006145  test    rsi, rsi
0x180006148  jz      loc_1800062F6
0x18000614e  mov     rdx, rdi; uBytes
0x180006151  mov     ecx, 40h ; '@'; uFlags
0x180006156  call    cs:__imp_LocalAlloc
0x18000615c  mov     rbx, rax
0x18000615f  test    rax, rax
0x180006162  jnz     short loc_180006186
0x180006164  call    cs:__imp_GetLastError
0x18000616a  mov     edi, eax
0x18000616c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006173  cmp     rcx, r12
0x180006176  jz      loc_1800063DE
0x18000617c  mov     edx, 0Fh
0x180006181  jmp     loc_18000632B
0x180006186  mov     r8, rdi; Size
0x180006189  mov     rdx, rsi; Src
0x18000618c  mov     rcx, rbx; void *
0x18000618f  call    memcpy_0
0x180006194  cmp     [rbx+4], edi
0x180006197  jnz     loc_180006261
0x18000619d  mov     ecx, [rbx+14h]
0x1800061a0  lea     rsi, [rbx+10h]
0x1800061a4  lea     edx, [rcx+10h]
0x1800061a7  cmp     edx, ecx
0x1800061a9  jb      loc_180006261
0x1800061af  mov     eax, [rbx+8]
0x1800061b2  mov     r8d, 0FFFFFFFFh
0x1800061b8  shl     rax, 4
0x1800061bc  cmp     rax, r8
0x1800061bf  ja      loc_180006261
0x1800061c5  lea     r8d, [rax+rdx]
0x1800061c9  cmp     r8d, edx
0x1800061cc  jb      loc_180006261
0x1800061d2  cmp     r8d, edi
0x1800061d5  ja      loc_180006261
0x1800061db  cmp     ecx, 14h
0x1800061de  jb      loc_180006261
0x1800061e4  mov     rcx, rsi; lpbBytes
0x1800061e7  call    ?IsEaptlsConnPropV1Valid@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; IsEaptlsConnPropV1Valid(_EAPTLS_CONN_PROPERTIES_V1 *)
0x1800061ec  test    eax, eax
0x1800061ee  jz      short loc_180006261
0x1800061f0  mov     r8d, [rbx+8]; unsigned int
0x1800061f4  test    r8d, r8d
0x1800061f7  jz      short loc_180006230
0x1800061f9  mov     eax, [rsi+0Ch]
0x1800061fc  lea     rdx, [rax+1]
0x180006200  lea     rdx, [rax+rdx*2]
0x180006204  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000620b  lea     rdx, [rsi+rdx*8]
0x18000620f  nop
0x180006210  inc     rax
0x180006213  cmp     word ptr [rdx+rax*2], 0
0x180006218  jnz     short loc_180006210
0x18000621a  inc     rax
0x18000621d  lea     rcx, [rdx+rax*2]; struct _PEAP_ENTRY_CONN_PROPERTIES *
0x180006221  mov     edx, ebx
0x180006223  sub     edx, ecx
0x180006225  add     edx, edi; unsigned int
0x180006227  call    ?IsPeapEntryArrayInPeapConnPropValid@@YAHPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@KK@Z; IsPeapEntryArrayInPeapConnPropValid(_PEAP_ENTRY_CONN_PROPERTIES *,ulong,ulong)
0x18000622c  test    eax, eax
0x18000622e  jz      short loc_180006261
0x180006230  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x180006233  call    ?IsIdentityPrivacyInPeapConnPropValid@@YAHPEAU_PEAP_CONN_PROPERTIES@@@Z; IsIdentityPrivacyInPeapConnPropValid(_PEAP_CONN_PROPERTIES *)
0x180006238  test    eax, eax
0x18000623a  jnz     loc_1800062EA
0x180006240  mov     rcx, cs:WPP_GLOBAL_Control
0x180006247  cmp     rcx, r12
0x18000624a  jz      short loc_180006285
0x18000624c  mov     rcx, [rcx+10h]
0x180006250  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180006257  mov     edx, 1Eh
0x18000625c  call    WPP_SF_
0x180006261  mov     rcx, cs:WPP_GLOBAL_Control
0x180006268  cmp     rcx, r12
0x18000626b  jz      short loc_180006285
0x18000626d  mov     rcx, [rcx+10h]
0x180006271  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180006278  mov     edx, 1Fh
0x18000627d  mov     r9d, edi
0x180006280  call    WPP_SF_d
0x180006285  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x18000628b  mov     eax, 100h
0x180006290  cmp     edi, eax
0x180006292  mov     [rsp+88h+lpszPrefix], 0; lpszPrefix
0x18000629b  mov     [rsp+88h+bAddressPrefix], 1; bAddressPrefix
0x1800062a3  mov     r8, rbx; lpbBytes
0x1800062a6  cmovnb  edi, eax
0x1800062a9  mov     [rsp+88h+dwGroupSize], 1; dwGroupSize
0x1800062b1  mov     r9d, edi; dwByteCount
0x1800062b4  mov     edx, 1; dwFlags
0x1800062b9  call    cs:__imp_TraceDumpExA
0x1800062bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062c6  cmp     rcx, r12
0x1800062c9  jz      short loc_1800062E0
0x1800062cb  mov     rcx, [rcx+10h]
0x1800062cf  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800062d6  mov     edx, 10h
0x1800062db  call    WPP_SF_
0x1800062e0  mov     edi, 0Dh
0x1800062e5  jmp     loc_1800063DE
0x1800062ea  or      dword ptr [rbx+18h], 1
0x1800062ee  mov     [rbx+4], edi
0x1800062f1  jmp     loc_1800063D7
0x1800062f6  mov     edx, 37h ; '7'; uBytes
0x1800062fb  mov     ecx, 40h ; '@'; uFlags
0x180006300  call    cs:__imp_LocalAlloc
0x180006306  mov     rbx, rax
0x180006309  test    rax, rax
0x18000630c  jnz     short loc_180006343
0x18000630e  call    cs:__imp_GetLastError
0x180006314  mov     edi, eax
0x180006316  mov     rcx, cs:WPP_GLOBAL_Control
0x18000631d  cmp     rcx, r12
0x180006320  jz      loc_1800063DE
0x180006326  mov     edx, 0Dh
0x18000632b  mov     rcx, [rcx+10h]
0x18000632f  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180006336  mov     r9d, eax
0x180006339  call    WPP_SF_d
0x18000633e  jmp     loc_1800063DE
0x180006343  or      dword ptr [rax+18h], 11h
0x180006347  lea     rdx, [rsp+88h+var_48]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18000634c  or      dword ptr [rax+0Ch], 1
0x180006350  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x180006353  mov     dword ptr [rax], 1
0x180006359  mov     dword ptr [rax+4], 37h ; '7'
0x180006360  mov     dword ptr [rax+10h], 2
0x180006367  mov     dword ptr [rax+14h], 16h
0x18000636e  mov     dword ptr [rax+8], 1
0x180006375  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x18000637a  test    bpl, bpl
0x18000637d  jns     short loc_1800063B4
0x18000637f  or      dword ptr [rbx+18h], 4
0x180006383  call    isMachineJoinedToDomain
0x180006388  test    eax, eax
0x18000638a  jnz     short loc_1800063B4
0x18000638c  or      dword ptr [rbx+18h], 200h
0x180006393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000639a  cmp     rcx, r12
0x18000639d  jz      short loc_1800063B4
0x18000639f  mov     rcx, [rcx+10h]
0x1800063a3  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x1800063aa  mov     edx, 0Eh
0x1800063af  call    WPP_SF_
0x1800063b4  test    bpl, 1
0x1800063b8  jz      short loc_1800063BE
0x1800063ba  or      dword ptr [rbx+18h], 4
0x1800063be  mov     rax, [rsp+88h+var_48]
0x1800063c3  mov     dword ptr [rax], 1
0x1800063c9  mov     dword ptr [rax+4], 0Fh
0x1800063d0  mov     dword ptr [rax+8], 1Ah
0x1800063d7  xor     edi, edi
0x1800063d9  mov     [r14], rbx
0x1800063dc  xor     ebx, ebx
0x1800063de  mov     rcx, rbx; hMem
0x1800063e1  call    cs:__imp_LocalFree
0x1800063e7  mov     eax, edi
0x1800063e9  add     rsp, 58h
0x1800063ed  pop     r14
0x1800063ef  pop     r12
0x1800063f1  pop     rdi
0x1800063f2  pop     rsi
0x1800063f3  pop     rbp
0x1800063f4  pop     rbx
0x1800063f5  retn
```
