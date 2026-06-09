# ApplyIpcpSettings

- ea: `0x18001b074`
- end: `0x18001b7b9`
- name: `ApplyIpcpSettings`
- size: `1861`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x18001df60`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001b074`
- `0x18001f910`
- `0x18001fd58`
- `0x18002a138`
- `0x18002c76c`
- `0x18002cce0`
- `0x18002d06c`
- `0x18002d08c`
- `0x18002d904`
- `0x18002e150`
- `0x18002e1e0`
- `0x18002e92c`
- `0x180030acc`
- `0x18003153c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b5fa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b618`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b618`

## string_xrefs

- `0x18001b3a1`: `IPCP:RasUpdateDefaultRouteSettings failed. Error %d`
- `0x18001b3e9`: `IPCP:RasUpdateDefaultRouteSettings success`

## pseudocode

```c
__int64 __fastcall ApplyIpcpSettings(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  unsigned int v6; // edi
  __int64 v7; // r8
  unsigned int TcpipInfo; // eax
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  int *v24; // r8
  __int64 v25; // rax
  int cchWideChar; // edi
  WCHAR *lpWideCharStr; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v34[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v32[0] = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  if ( !a1 && !a2 )
    return 87;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    v7 = *(_QWORD *)(a1 + 1248);
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IPCP:LoadTcpipInfo(Device=%ws)", v7);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v33);
  }
  TcpipInfo = LoadTcpipInfo(v32, *(const wchar_t **)(a1 + 1248), 1);
  v6 = TcpipInfo;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IPCP: LoadTcpipInfo done(%d)", TcpipInfo);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v33);
  }
  v9 = v32[0];
  if ( v6 )
    goto LABEL_81;
  AbcdWszFromIpAddress(*(unsigned int *)(a1 + 144), v32[0] + 16);
  AbcdWszFromIpAddress((unsigned int)a2[147], v9 + 58);
  v10 = *((_QWORD *)&xmmword_18004C860 + 1);
  *(_DWORD *)(v9 + 4) = *(_DWORD *)(a1 + 84);
  *(_DWORD *)v9 = 1;
  if ( v10 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      v10,
      L"IPCP: SaveTcpipInfo...");
  v11 = SaveTcpipInfo(v9);
  v6 = v11;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IPCP: SaveTcpipInfo done(%d)", v11);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v33);
  }
  if ( v6 )
    goto LABEL_14;
  if ( *a2 != 2 )
  {
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      v12 = *(unsigned int *)(a1 + 16);
      v13 = *(unsigned int *)(a1 + 144);
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"IPCP: HelperSetDefaultInterfaceNet(a=%08x,f=%d)", v13, v12);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v33);
    }
    v14 = *(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL;
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"IPCP: Interface Type and Luid Index  %d %d", 23);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v33);
    }
    v15 = v14 << 24;
    v16 = HelperSetDefaultInterfaceNet(
            *(unsigned int *)(a1 + 144),
            *(unsigned int *)(a1 + 148),
            *(unsigned int *)(a1 + 16),
            *(_DWORD *)(a1 + 20) == 0,
            v15);
    v6 = v16;
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"IPCP: HelperSetDefaultInterfaceNet done(%d)", v16);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v33);
    }
    if ( v6 )
      goto LABEL_14;
    if ( *(_DWORD *)(a1 + 16) )
    {
      LOBYTE(v17) = 1;
      LOBYTE(v18) = 1;
      if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64))xmmword_18004C450)(v18, v17, v15) )
      {
        v6 = 1003;
        if ( (_QWORD)xmmword_18004C860 )
        {
          LOWORD(v33) = 0;
          FormatRRASErrorString(&v33, L"IPCP:RasUpdateDefaultRouteSettings failed. Error %d", 1003);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            xmmword_18004C860,
            &v33);
        }
LABEL_14:
        ResetNetBTConfigInfo(a1);
LABEL_81:
        if ( v9 )
          FreeTcpipInfo(v32);
        return v6;
      }
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          L"IPCP:RasUpdateDefaultRouteSettings success");
    }
    if ( a3 )
      *a3 = 1;
    LOBYTE(v18) = 1;
    if ( (unsigned int)AdjustSelfInterfaceMetrics(v18, *(unsigned int *)(a1 + 168), v15) )
    {
      ResetNetBTConfigInfo(a1);
      v6 = 1003;
      if ( (_QWORD)xmmword_18004C860 )
      {
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v33, L"IPCP:AdjustSelfInterfaceMetrics failed. Error %d", 1003);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, xmmword_18004C860, &v33);
      }
      goto LABEL_81;
    }
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      v19 = *(unsigned int *)(a1 + 168);
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"IPCP:AdjustSelfInterfaceMetrics to value %d successful", v19);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v33);
    }
  }
  *(_DWORD *)v9 = 0;
  if ( *(_DWORD *)(a1 + 108) )
  {
    v20 = *(_QWORD *)(v9 + 104);
    if ( v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v20 + 2 * v21) );
    }
    else
    {
      v21 = 0;
    }
    v6 = PrependDwIpAddress(v9 + 104, v21);
    if ( v6 )
      goto LABEL_81;
  }
  if ( *(_DWORD *)(a1 + 104) )
  {
    v22 = *(_QWORD *)(v9 + 104);
    if ( v22 )
    {
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(v22 + 2 * v23) );
    }
    else
    {
      v23 = 0;
    }
    v6 = PrependDwIpAddress(v9 + 104, v23);
    if ( v6 )
      goto LABEL_81;
  }
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    LOWORD(v33) = 0;
    v24 = &dword_18003CAF4;
    if ( *(_QWORD *)(v9 + 104) )
      v24 = *(int **)(v9 + 104);
    FormatRRASErrorString(&v33, L"IPCP: New Dns=%ws", v24);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v33);
  }
  if ( *(_DWORD *)(a1 + 64) )
  {
    if ( *(_DWORD *)(a1 + 100) )
    {
      v6 = PrependDwIpAddressToMwsz(v9 + 112);
      if ( v6 )
        goto LABEL_81;
    }
    if ( *(_DWORD *)(a1 + 96) )
    {
      v6 = PrependDwIpAddressToMwsz(v9 + 112);
      if ( v6 )
        goto LABEL_81;
    }
    PrintMwsz("IPCP: New Wins=", *(_QWORD *)(v9 + 112));
  }
  if ( *(_BYTE *)(a1 + 1812) )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(a1 + 1812 + v25) );
    cchWideChar = v25 + 1;
    lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v25 + 1));
    *(_QWORD *)(v9 + 120) = lpWideCharStr;
    if ( lpWideCharStr )
      MultiByteToWideChar(0xFDE9u, 0, (LPCCH)(a1 + 1812), -1, lpWideCharStr, cchWideChar);
    else
      GetLastError();
  }
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: SaveTcpipInfo...");
  v28 = SaveTcpipInfo(v9);
  v6 = v28;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IPCP: SaveTcpipInfo done(%d)", v28);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v33);
  }
  FreeTcpipInfo(v32);
  v32[0] = 0;
  v9 = 0;
  if ( !v6 )
  {
    if ( !*(_DWORD *)(a1 + 60) )
    {
      v29 = SetIPAddressOnInterface(*(unsigned int *)(a1 + 144), (unsigned int)a2[147], *(unsigned int *)(a1 + 1256));
      v6 = v29;
      if ( v29 )
      {
        if ( *((_QWORD *)&xmmword_18004C860 + 1) )
        {
          LOWORD(v33) = 0;
          FormatRRASErrorString(&v33, L"IpCP: SetIPAddressOnInterfacedone(%d)", v29);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004C860 + 1),
            &v33);
        }
        return v6;
      }
      *(_DWORD *)(a1 + 88) = 1;
    }
    if ( *(_DWORD *)a1 )
      return v6;
    v30 = RasTcpAdjustMulticastRouteMetric(*(unsigned int *)(a1 + 144), 1);
    v6 = v30;
    if ( !v30 )
      return v6;
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"IPCP: =RasTcpAdjustMulticastRouteMetric%d", v30);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        &v33);
    }
    v6 = 0;
    goto LABEL_81;
  }
  return v6;
}

```

## disassembly

```asm
0x18001b074  mov     [rsp-8+arg_18], rbx
0x18001b079  push    rbp
0x18001b07a  push    rsi
0x18001b07b  push    rdi
0x18001b07c  push    r12
0x18001b07e  push    r13
0x18001b080  push    r14
0x18001b082  push    r15
0x18001b084  lea     rbp, [rsp-750h]
0x18001b08c  sub     rsp, 850h
0x18001b093  mov     rax, cs:__security_cookie
0x18001b09a  xor     rax, rsp
0x18001b09d  mov     [rbp+780h+var_40], rax
0x18001b0a4  mov     r15, r8
0x18001b0a7  mov     r13, rdx
0x18001b0aa  mov     rsi, rcx
0x18001b0ad  xor     r12d, r12d
0x18001b0b0  xor     edx, edx; Val
0x18001b0b2  mov     [rsp+880h+var_850], r12
0x18001b0b7  mov     r8d, 7FCh; Size
0x18001b0bd  mov     [rsp+880h+var_840], r12d
0x18001b0c2  lea     rcx, [rsp+880h+var_83C]; void *
0x18001b0c7  call    memset_0
0x18001b0cc  test    rsi, rsi
0x18001b0cf  jnz     short loc_18001B0DE
0x18001b0d1  test    r13, r13
0x18001b0d4  jnz     short loc_18001B0DE
0x18001b0d6  lea     edi, [rsi+57h]
0x18001b0d9  jmp     loc_18001B78D
0x18001b0de  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b0e5  jz      short loc_18001B124
0x18001b0e7  mov     r8, [rsi+4E0h]
0x18001b0ee  lea     rdx, aIpcpLoadtcpipi_1; "IPCP:LoadTcpipInfo(Device=%ws)"
0x18001b0f5  lea     rcx, [rsp+880h+var_840]
0x18001b0fa  mov     word ptr [rsp+880h+var_840], r12w
0x18001b100  call    FormatRRASErrorString
0x18001b105  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b10c  lea     r8, [rsp+880h+var_840]
0x18001b111  mov     rcx, cs:gRasIpcpEtwContext
0x18001b118  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b124  mov     rdx, [rsi+4E0h]
0x18001b12b  lea     rcx, [rsp+880h+var_850]
0x18001b130  mov     ebx, 1
0x18001b135  mov     r8d, ebx
0x18001b138  call    LoadTcpipInfo
0x18001b13d  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b144  mov     edi, eax
0x18001b146  jz      short loc_18001B181
0x18001b148  mov     r8d, eax
0x18001b14b  mov     word ptr [rsp+880h+var_840], r12w
0x18001b151  lea     rdx, aIpcpLoadtcpipi_0; "IPCP: LoadTcpipInfo done(%d)"
0x18001b158  lea     rcx, [rsp+880h+var_840]
0x18001b15d  call    FormatRRASErrorString
0x18001b162  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b169  lea     r8, [rsp+880h+var_840]
0x18001b16e  mov     rcx, cs:gRasIpcpEtwContext
0x18001b175  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b181  mov     r14, [rsp+880h+var_850]
0x18001b186  test    edi, edi
0x18001b188  jnz     loc_18001B77E
0x18001b18e  mov     ecx, [rsi+90h]
0x18001b194  lea     rdx, [r14+10h]
0x18001b198  call    AbcdWszFromIpAddress
0x18001b19d  mov     ecx, [r13+24Ch]
0x18001b1a4  lea     rdx, [r14+3Ah]
0x18001b1a8  call    AbcdWszFromIpAddress
0x18001b1ad  mov     eax, [rsi+54h]
0x18001b1b0  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b1b7  mov     [r14+4], eax
0x18001b1bb  mov     [r14], ebx
0x18001b1be  test    rdx, rdx
0x18001b1c1  jz      short loc_18001B1DD
0x18001b1c3  mov     rcx, cs:gRasIpcpEtwContext
0x18001b1ca  lea     r8, aIpcpSavetcpipi; "IPCP: SaveTcpipInfo..."
0x18001b1d1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1dd  mov     rcx, r14
0x18001b1e0  call    SaveTcpipInfo
0x18001b1e5  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b1ec  mov     edi, eax
0x18001b1ee  jz      short loc_18001B229
0x18001b1f0  mov     r8d, eax
0x18001b1f3  mov     word ptr [rsp+880h+var_840], r12w
0x18001b1f9  lea     rdx, aIpcpSavetcpipi_0; "IPCP: SaveTcpipInfo done(%d)"
0x18001b200  lea     rcx, [rsp+880h+var_840]
0x18001b205  call    FormatRRASErrorString
0x18001b20a  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b211  lea     r8, [rsp+880h+var_840]
0x18001b216  mov     rcx, cs:gRasIpcpEtwContext
0x18001b21d  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b229  test    edi, edi
0x18001b22b  jz      short loc_18001B23A
0x18001b22d  mov     rcx, rsi
0x18001b230  call    ResetNetBTConfigInfo
0x18001b235  jmp     loc_18001B77E
0x18001b23a  cmp     dword ptr [r13+0], 2
0x18001b23f  jz      loc_18001B4BA
0x18001b245  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b24c  jz      short loc_18001B28F
0x18001b24e  mov     r9d, [rsi+10h]
0x18001b252  lea     rdx, aIpcpHelpersetd_0; "IPCP: HelperSetDefaultInterfaceNet(a=%0"...
0x18001b259  mov     r8d, [rsi+90h]
0x18001b260  lea     rcx, [rsp+880h+var_840]
0x18001b265  mov     word ptr [rsp+880h+var_840], r12w
0x18001b26b  call    FormatRRASErrorString
0x18001b270  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b277  lea     r8, [rsp+880h+var_840]
0x18001b27c  mov     rcx, cs:gRasIpcpEtwContext
0x18001b283  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28f  mov     r9d, [rsi+4E8h]
0x18001b296  mov     ebx, r9d
0x18001b299  and     ebx, 0FFFFFFh
0x18001b29f  or      rbx, 17000000h
0x18001b2a6  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b2ad  jz      short loc_18001B2EB
0x18001b2af  mov     r8d, 17h
0x18001b2b5  mov     word ptr [rsp+880h+var_840], r12w
0x18001b2bb  lea     rdx, aIpcpInterfaceT; "IPCP: Interface Type and Luid Index  %d"...
0x18001b2c2  lea     rcx, [rsp+880h+var_840]
0x18001b2c7  call    FormatRRASErrorString
0x18001b2cc  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b2d3  lea     r8, [rsp+880h+var_840]
0x18001b2d8  mov     rcx, cs:gRasIpcpEtwContext
0x18001b2df  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2eb  mov     r8d, [rsi+10h]
0x18001b2ef  mov     r9d, r12d
0x18001b2f2  mov     edx, [rsi+94h]
0x18001b2f8  mov     ecx, [rsi+90h]
0x18001b2fe  shl     rbx, 18h
0x18001b302  cmp     [rsi+14h], r12d
0x18001b306  mov     [rsp+880h+lpWideCharStr], rbx
0x18001b30b  setz    r9b
0x18001b30f  call    HelperSetDefaultInterfaceNet
0x18001b314  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b31b  mov     edi, eax
0x18001b31d  jz      short loc_18001B358
0x18001b31f  mov     r8d, eax
0x18001b322  mov     word ptr [rsp+880h+var_840], r12w
0x18001b328  lea     rdx, aIpcpHelpersetd; "IPCP: HelperSetDefaultInterfaceNet done"...
0x18001b32f  lea     rcx, [rsp+880h+var_840]
0x18001b334  call    FormatRRASErrorString
0x18001b339  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b340  lea     r8, [rsp+880h+var_840]
0x18001b345  mov     rcx, cs:gRasIpcpEtwContext
0x18001b34c  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b358  test    edi, edi
0x18001b35a  jnz     loc_18001B22D
0x18001b360  cmp     [rsi+10h], r12d
0x18001b364  jz      loc_18001B3FC
0x18001b36a  mov     rax, qword ptr cs:xmmword_18004C450
0x18001b371  mov     r9b, 1
0x18001b374  mov     dl, r9b
0x18001b377  mov     cl, r9b
0x18001b37a  mov     r8, rbx
0x18001b37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b382  test    eax, eax
0x18001b384  jz      short loc_18001B3D6
0x18001b386  cmp     qword ptr cs:xmmword_18004C860, r12
0x18001b38d  mov     edi, 3EBh
0x18001b392  jz      loc_18001B22D
0x18001b398  mov     r8d, edi
0x18001b39b  mov     word ptr [rsp+880h+var_840], r12w
0x18001b3a1  lea     rdx, aIpcpRasupdated_0; "IPCP:RasUpdateDefaultRouteSettings fail"...
0x18001b3a8  lea     rcx, [rsp+880h+var_840]
0x18001b3ad  call    FormatRRASErrorString
0x18001b3b2  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001b3b9  lea     r8, [rsp+880h+var_840]
0x18001b3be  mov     rcx, cs:gRasIpcpEtwContext
0x18001b3c5  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d1  jmp     loc_18001B22D
0x18001b3d6  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b3dd  test    rdx, rdx
0x18001b3e0  jz      short loc_18001B3FC
0x18001b3e2  mov     rcx, cs:gRasIpcpEtwContext
0x18001b3e9  lea     r8, aIpcpRasupdated; "IPCP:RasUpdateDefaultRouteSettings succ"...
0x18001b3f0  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3fc  test    r15, r15
0x18001b3ff  jz      short loc_18001B408
0x18001b401  mov     dword ptr [r15], 1
0x18001b408  mov     edx, [rsi+0A8h]
0x18001b40e  mov     r8, rbx
0x18001b411  mov     cl, 1
0x18001b413  call    AdjustSelfInterfaceMetrics
0x18001b418  test    eax, eax
0x18001b41a  jz      short loc_18001B474
0x18001b41c  mov     rcx, rsi
0x18001b41f  call    ResetNetBTConfigInfo
0x18001b424  cmp     qword ptr cs:xmmword_18004C860, r12
0x18001b42b  mov     edi, 3EBh
0x18001b430  jz      loc_18001B77E
0x18001b436  mov     r8d, edi
0x18001b439  mov     word ptr [rsp+880h+var_840], r12w
0x18001b43f  lea     rdx, aIpcpAdjustself_0; "IPCP:AdjustSelfInterfaceMetrics failed."...
0x18001b446  lea     rcx, [rsp+880h+var_840]
0x18001b44b  call    FormatRRASErrorString
0x18001b450  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001b457  lea     r8, [rsp+880h+var_840]
0x18001b45c  mov     rcx, cs:gRasIpcpEtwContext
0x18001b463  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b46f  jmp     loc_18001B77E
0x18001b474  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b47b  jz      short loc_18001B4BA
0x18001b47d  mov     r8d, [rsi+0A8h]
0x18001b484  lea     rdx, aIpcpAdjustself; "IPCP:AdjustSelfInterfaceMetrics to valu"...
0x18001b48b  lea     rcx, [rsp+880h+var_840]
0x18001b490  mov     word ptr [rsp+880h+var_840], r12w
0x18001b496  call    FormatRRASErrorString
0x18001b49b  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b4a2  lea     r8, [rsp+880h+var_840]
0x18001b4a7  mov     rcx, cs:gRasIpcpEtwContext
0x18001b4ae  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ba  mov     [r14], r12d
0x18001b4bd  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001b4c1  mov     r8d, [rsi+6Ch]
0x18001b4c5  test    r8d, r8d
0x18001b4c8  jz      short loc_18001B4F7
0x18001b4ca  lea     rcx, [r14+68h]
0x18001b4ce  mov     rax, [rcx]
0x18001b4d1  test    rax, rax
0x18001b4d4  jz      short loc_18001B4E5
0x18001b4d6  mov     rdx, r15
0x18001b4d9  inc     rdx
0x18001b4dc  cmp     [rax+rdx*2], r12w
0x18001b4e1  jnz     short loc_18001B4D9
0x18001b4e3  jmp     short loc_18001B4E8
0x18001b4e5  mov     rdx, r12
0x18001b4e8  call    PrependDwIpAddress
0x18001b4ed  mov     edi, eax
0x18001b4ef  test    eax, eax
0x18001b4f1  jnz     loc_18001B77E
0x18001b4f7  mov     r8d, [rsi+68h]
0x18001b4fb  test    r8d, r8d
0x18001b4fe  jz      short loc_18001B52D
0x18001b500  lea     rcx, [r14+68h]
0x18001b504  mov     rax, [rcx]
0x18001b507  test    rax, rax
0x18001b50a  jz      short loc_18001B51B
0x18001b50c  mov     rdx, r15
0x18001b50f  inc     rdx
0x18001b512  cmp     [rax+rdx*2], r12w
0x18001b517  jnz     short loc_18001B50F
0x18001b519  jmp     short loc_18001B51E
0x18001b51b  mov     rdx, r12
0x18001b51e  call    PrependDwIpAddress
0x18001b523  mov     edi, eax
0x18001b525  test    eax, eax
0x18001b527  jnz     loc_18001B77E
0x18001b52d  cmp     qword ptr cs:xmmword_18004C860+8, r12
0x18001b534  jz      short loc_18001B57C
0x18001b536  mov     word ptr [rsp+880h+var_840], r12w
0x18001b53c  lea     r8, dword_18003CAF4
0x18001b543  cmp     [r14+68h], r12
0x18001b547  lea     rdx, aIpcpNewDnsWs; "IPCP: New Dns=%ws"
0x18001b54e  lea     rcx, [rsp+880h+var_840]
0x18001b553  cmovnz  r8, [r14+68h]
0x18001b558  call    FormatRRASErrorString
0x18001b55d  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b564  lea     r8, [rsp+880h+var_840]
0x18001b569  mov     rcx, cs:gRasIpcpEtwContext
0x18001b570  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b57c  cmp     [rsi+40h], r12d
0x18001b580  jz      short loc_18001B5C6
0x18001b582  mov     edx, [rsi+64h]
0x18001b585  test    edx, edx
0x18001b587  jz      short loc_18001B59C
0x18001b589  lea     rcx, [r14+70h]
0x18001b58d  call    PrependDwIpAddressToMwsz
0x18001b592  mov     edi, eax
0x18001b594  test    eax, eax
0x18001b596  jnz     loc_18001B77E
0x18001b59c  mov     edx, [rsi+60h]
0x18001b59f  test    edx, edx
0x18001b5a1  jz      short loc_18001B5B6
0x18001b5a3  lea     rcx, [r14+70h]
0x18001b5a7  call    PrependDwIpAddressToMwsz
0x18001b5ac  mov     edi, eax
0x18001b5ae  test    eax, eax
0x18001b5b0  jnz     loc_18001B77E
0x18001b5b6  mov     rdx, [r14+70h]
0x18001b5ba  lea     rcx, aIpcpNewWins; "IPCP: New Wins="
0x18001b5c1  call    PrintMwsz
0x18001b5c6  lea     rbx, [rsi+714h]
0x18001b5cd  cmp     [rbx], r12b
0x18001b5d0  jz      short loc_18001B61E
0x18001b5d2  mov     rax, r15
0x18001b5d5  inc     rax
0x18001b5d8  cmp     [rbx+rax], r12b
0x18001b5dc  jnz     short loc_18001B5D5
0x18001b5de  lea     edi, [rax+1]
  ... truncated ...
```
