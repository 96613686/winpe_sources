# ApplyIpcpSettings

- ea: `0x18001bab4`
- end: `0x18001c1b5`
- name: `ApplyIpcpSettings`
- size: `1793`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x18001ea80`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001bab4`
- `0x1800204c4`
- `0x180020920`
- `0x18002b0dc`
- `0x18002d88c`
- `0x18002de38`
- `0x18002e1ec`
- `0x18002e214`
- `0x18002e2a4`
- `0x18002ebd0`
- `0x18002f4a4`
- `0x18002f53c`
- `0x18002fce0`
- `0x180032024`
- `0x180032b1c`
- `0x180034010`

## string_xrefs

- `0x18001bde1`: `IPCP:RasUpdateDefaultRouteSettings failed. Error %d`
- `0x18001be29`: `IPCP:RasUpdateDefaultRouteSettings success`

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
  __int64 v20; // rbx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  int *v26; // r8
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v33[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v31[0] = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  if ( !a1 && !a2 )
    return 87;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    v7 = *(_QWORD *)(a1 + 1248);
    LOWORD(v32) = 0;
    FormatRRASErrorString((wchar_t *)&v32, L"IPCP:LoadTcpipInfo(Device=%ws)", v7);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v32);
  }
  TcpipInfo = LoadTcpipInfo(v31, *(const wchar_t **)(a1 + 1248), 1);
  v6 = TcpipInfo;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString((wchar_t *)&v32, L"IPCP: LoadTcpipInfo done(%d)", TcpipInfo);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v32);
  }
  v9 = v31[0];
  if ( v6 )
    goto LABEL_76;
  AbcdWszFromIpAddress(*(unsigned int *)(a1 + 144), v31[0] + 16);
  AbcdWszFromIpAddress((unsigned int)a2[147], v9 + 58);
  v10 = *((_QWORD *)&xmmword_18004D860 + 1);
  *(_DWORD *)(v9 + 4) = *(_DWORD *)(a1 + 84);
  *(_DWORD *)v9 = 1;
  if ( v10 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      v10,
      L"IPCP: SaveTcpipInfo...");
  v11 = SaveTcpipInfo(v9);
  v6 = v11;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString((wchar_t *)&v32, L"IPCP: SaveTcpipInfo done(%d)", v11);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v32);
  }
  if ( v6 )
    goto LABEL_14;
  if ( *a2 != 2 )
  {
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      v12 = *(unsigned int *)(a1 + 16);
      v13 = *(unsigned int *)(a1 + 144);
      LOWORD(v32) = 0;
      FormatRRASErrorString((wchar_t *)&v32, L"IPCP: HelperSetDefaultInterfaceNet(a=%08x,f=%d)", v13, v12);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v32);
    }
    v14 = *(_DWORD *)(a1 + 1256) & 0xFFFFFF | 0x17000000LL;
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString((wchar_t *)&v32, L"IPCP: Interface Type and Luid Index  %d %d", 23);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v32);
    }
    v15 = v14 << 24;
    v16 = HelperSetDefaultInterfaceNet(
            *(_DWORD *)(a1 + 144),
            *(_DWORD *)(a1 + 148),
            *(_DWORD *)(a1 + 16),
            *(_DWORD *)(a1 + 20) == 0,
            (NET_LUID)v15);
    v6 = v16;
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString((wchar_t *)&v32, L"IPCP: HelperSetDefaultInterfaceNet done(%d)", v16);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v32);
    }
    if ( v6 )
      goto LABEL_14;
    if ( *(_DWORD *)(a1 + 16) )
    {
      LOBYTE(v17) = 1;
      LOBYTE(v18) = 1;
      if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64))xmmword_18004D450)(v18, v17, v15) )
      {
        v6 = 1003;
        if ( (_QWORD)xmmword_18004D860 )
        {
          LOWORD(v32) = 0;
          FormatRRASErrorString((wchar_t *)&v32, L"IPCP:RasUpdateDefaultRouteSettings failed. Error %d", 1003);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            xmmword_18004D860,
            &v32);
        }
LABEL_14:
        ResetNetBTConfigInfo(a1);
LABEL_76:
        if ( v9 )
          FreeTcpipInfo(v31);
        return v6;
      }
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
          L"IPCP:RasUpdateDefaultRouteSettings success");
    }
    if ( a3 )
      *a3 = 1;
    if ( (unsigned int)AdjustSelfInterfaceMetrics(1, *(_DWORD *)(a1 + 168), v15) )
    {
      ResetNetBTConfigInfo(a1);
      v6 = 1003;
      if ( (_QWORD)xmmword_18004D860 )
      {
        LOWORD(v32) = 0;
        FormatRRASErrorString((wchar_t *)&v32, L"IPCP:AdjustSelfInterfaceMetrics failed. Error %d", 1003);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, xmmword_18004D860, &v32);
      }
      goto LABEL_76;
    }
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      v19 = *(unsigned int *)(a1 + 168);
      LOWORD(v32) = 0;
      FormatRRASErrorString((wchar_t *)&v32, L"IPCP:AdjustSelfInterfaceMetrics to value %d successful", v19);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v32);
    }
  }
  *(_DWORD *)v9 = 0;
  v20 = -1;
  v21 = *(unsigned int *)(a1 + 108);
  if ( (_DWORD)v21 )
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
    v6 = PrependDwIpAddress(v9 + 104, v23, v21);
    if ( v6 )
      goto LABEL_76;
  }
  v24 = *(unsigned int *)(a1 + 104);
  if ( (_DWORD)v24 )
  {
    v25 = *(_QWORD *)(v9 + 104);
    if ( v25 )
    {
      do
        ++v20;
      while ( *(_WORD *)(v25 + 2 * v20) );
    }
    else
    {
      LODWORD(v20) = 0;
    }
    v6 = PrependDwIpAddress(v9 + 104, (unsigned int)v20, v24);
    if ( v6 )
      goto LABEL_76;
  }
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    LOWORD(v32) = 0;
    v26 = &dword_18003DAF4;
    if ( *(_QWORD *)(v9 + 104) )
      v26 = *(int **)(v9 + 104);
    FormatRRASErrorString((wchar_t *)&v32, L"IPCP: New Dns=%ws", v26);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v32);
  }
  if ( *(_DWORD *)(a1 + 64) )
  {
    if ( *(_DWORD *)(a1 + 100) )
    {
      v6 = PrependDwIpAddressToMwsz(v9 + 112);
      if ( v6 )
        goto LABEL_76;
    }
    if ( *(_DWORD *)(a1 + 96) )
    {
      v6 = PrependDwIpAddressToMwsz(v9 + 112);
      if ( v6 )
        goto LABEL_76;
    }
    PrintMwsz((__int64)"IPCP: New Wins=", *(const void **)(v9 + 112));
  }
  if ( *(_BYTE *)(a1 + 1812) )
    AddDNSSuffix(v9, (const CHAR *)(a1 + 1812));
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: SaveTcpipInfo...");
  v27 = SaveTcpipInfo(v9);
  v6 = v27;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString((wchar_t *)&v32, L"IPCP: SaveTcpipInfo done(%d)", v27);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v32);
  }
  FreeTcpipInfo(v31);
  v31[0] = 0;
  v9 = 0;
  if ( !v6 )
  {
    if ( !*(_DWORD *)(a1 + 60) )
    {
      v28 = SetIPAddressOnInterface(*(_DWORD *)(a1 + 144), a2[147], *(_DWORD *)(a1 + 1256));
      v6 = v28;
      if ( v28 )
      {
        if ( *((_QWORD *)&xmmword_18004D860 + 1) )
        {
          LOWORD(v32) = 0;
          FormatRRASErrorString((wchar_t *)&v32, L"IpCP: SetIPAddressOnInterfacedone(%d)", v28);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            *((_QWORD *)&xmmword_18004D860 + 1),
            &v32);
        }
        return v6;
      }
      *(_DWORD *)(a1 + 88) = 1;
    }
    if ( *(_DWORD *)a1 )
      return v6;
    v29 = RasTcpAdjustMulticastRouteMetric(*(_DWORD *)(a1 + 144), 1);
    v6 = v29;
    if ( !v29 )
      return v6;
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString((wchar_t *)&v32, L"IPCP: =RasTcpAdjustMulticastRouteMetric%d", v29);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v32);
    }
    v6 = 0;
    goto LABEL_76;
  }
  return v6;
}

```

## disassembly

```asm
0x18001bab4  mov     [rsp-8+arg_18], rbx
0x18001bab9  push    rbp
0x18001baba  push    rsi
0x18001babb  push    rdi
0x18001babc  push    r12
0x18001babe  push    r13
0x18001bac0  push    r14
0x18001bac2  push    r15
0x18001bac4  lea     rbp, [rsp-750h]
0x18001bacc  sub     rsp, 850h
0x18001bad3  mov     rax, cs:__security_cookie
0x18001bada  xor     rax, rsp
0x18001badd  mov     [rbp+780h+var_40], rax
0x18001bae4  mov     r15, r8
0x18001bae7  mov     r13, rdx
0x18001baea  mov     rsi, rcx
0x18001baed  xor     r12d, r12d
0x18001baf0  xor     edx, edx; Val
0x18001baf2  mov     [rsp+880h+var_850], r12
0x18001baf7  mov     r8d, 7FCh; Size
0x18001bafd  mov     [rsp+880h+var_840], r12d
0x18001bb02  lea     rcx, [rsp+880h+var_83C]; void *
0x18001bb07  call    memset_0
0x18001bb0c  test    rsi, rsi
0x18001bb0f  jnz     short loc_18001BB1E
0x18001bb11  test    r13, r13
0x18001bb14  jnz     short loc_18001BB1E
0x18001bb16  lea     edi, [rsi+57h]
0x18001bb19  jmp     loc_18001C188
0x18001bb1e  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bb25  jz      short loc_18001BB64
0x18001bb27  mov     r8, [rsi+4E0h]
0x18001bb2e  lea     rdx, aIpcpLoadtcpipi_1; "IPCP:LoadTcpipInfo(Device=%ws)"
0x18001bb35  lea     rcx, [rsp+880h+var_840]
0x18001bb3a  mov     word ptr [rsp+880h+var_840], r12w
0x18001bb40  call    FormatRRASErrorString
0x18001bb45  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bb4c  lea     r8, [rsp+880h+var_840]
0x18001bb51  mov     rcx, cs:gRasIpcpEtwContext
0x18001bb58  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb64  mov     rdx, [rsi+4E0h]
0x18001bb6b  lea     rcx, [rsp+880h+var_850]
0x18001bb70  mov     ebx, 1
0x18001bb75  mov     r8d, ebx
0x18001bb78  call    LoadTcpipInfo
0x18001bb7d  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bb84  mov     edi, eax
0x18001bb86  jz      short loc_18001BBC1
0x18001bb88  mov     r8d, eax
0x18001bb8b  mov     word ptr [rsp+880h+var_840], r12w
0x18001bb91  lea     rdx, aIpcpLoadtcpipi_0; "IPCP: LoadTcpipInfo done(%d)"
0x18001bb98  lea     rcx, [rsp+880h+var_840]
0x18001bb9d  call    FormatRRASErrorString
0x18001bba2  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bba9  lea     r8, [rsp+880h+var_840]
0x18001bbae  mov     rcx, cs:gRasIpcpEtwContext
0x18001bbb5  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc1  mov     r14, [rsp+880h+var_850]
0x18001bbc6  test    edi, edi
0x18001bbc8  jnz     loc_18001C179
0x18001bbce  mov     ecx, [rsi+90h]
0x18001bbd4  lea     rdx, [r14+10h]
0x18001bbd8  call    AbcdWszFromIpAddress
0x18001bbdd  mov     ecx, [r13+24Ch]
0x18001bbe4  lea     rdx, [r14+3Ah]
0x18001bbe8  call    AbcdWszFromIpAddress
0x18001bbed  mov     eax, [rsi+54h]
0x18001bbf0  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bbf7  mov     [r14+4], eax
0x18001bbfb  mov     [r14], ebx
0x18001bbfe  test    rdx, rdx
0x18001bc01  jz      short loc_18001BC1D
0x18001bc03  mov     rcx, cs:gRasIpcpEtwContext
0x18001bc0a  lea     r8, aIpcpSavetcpipi; "IPCP: SaveTcpipInfo..."
0x18001bc11  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc1d  mov     rcx, r14
0x18001bc20  call    SaveTcpipInfo
0x18001bc25  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bc2c  mov     edi, eax
0x18001bc2e  jz      short loc_18001BC69
0x18001bc30  mov     r8d, eax
0x18001bc33  mov     word ptr [rsp+880h+var_840], r12w
0x18001bc39  lea     rdx, aIpcpSavetcpipi_0; "IPCP: SaveTcpipInfo done(%d)"
0x18001bc40  lea     rcx, [rsp+880h+var_840]
0x18001bc45  call    FormatRRASErrorString
0x18001bc4a  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bc51  lea     r8, [rsp+880h+var_840]
0x18001bc56  mov     rcx, cs:gRasIpcpEtwContext
0x18001bc5d  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc69  test    edi, edi
0x18001bc6b  jz      short loc_18001BC7A
0x18001bc6d  mov     rcx, rsi
0x18001bc70  call    ResetNetBTConfigInfo
0x18001bc75  jmp     loc_18001C179
0x18001bc7a  cmp     dword ptr [r13+0], 2
0x18001bc7f  jz      loc_18001BEFA
0x18001bc85  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bc8c  jz      short loc_18001BCCF
0x18001bc8e  mov     r9d, [rsi+10h]
0x18001bc92  lea     rdx, aIpcpHelpersetd_0; "IPCP: HelperSetDefaultInterfaceNet(a=%0"...
0x18001bc99  mov     r8d, [rsi+90h]
0x18001bca0  lea     rcx, [rsp+880h+var_840]
0x18001bca5  mov     word ptr [rsp+880h+var_840], r12w
0x18001bcab  call    FormatRRASErrorString
0x18001bcb0  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bcb7  lea     r8, [rsp+880h+var_840]
0x18001bcbc  mov     rcx, cs:gRasIpcpEtwContext
0x18001bcc3  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bccf  mov     r9d, [rsi+4E8h]
0x18001bcd6  mov     ebx, r9d
0x18001bcd9  and     ebx, 0FFFFFFh
0x18001bcdf  or      rbx, 17000000h
0x18001bce6  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bced  jz      short loc_18001BD2B
0x18001bcef  mov     r8d, 17h
0x18001bcf5  mov     word ptr [rsp+880h+var_840], r12w
0x18001bcfb  lea     rdx, aIpcpInterfaceT; "IPCP: Interface Type and Luid Index  %d"...
0x18001bd02  lea     rcx, [rsp+880h+var_840]
0x18001bd07  call    FormatRRASErrorString
0x18001bd0c  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bd13  lea     r8, [rsp+880h+var_840]
0x18001bd18  mov     rcx, cs:gRasIpcpEtwContext
0x18001bd1f  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd2b  mov     r8d, [rsi+10h]
0x18001bd2f  mov     r9d, r12d
0x18001bd32  mov     edx, [rsi+94h]
0x18001bd38  mov     ecx, [rsi+90h]
0x18001bd3e  shl     rbx, 18h
0x18001bd42  cmp     [rsi+14h], r12d
0x18001bd46  mov     [rsp+880h+var_860], rbx
0x18001bd4b  setz    r9b
0x18001bd4f  call    HelperSetDefaultInterfaceNet
0x18001bd54  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bd5b  mov     edi, eax
0x18001bd5d  jz      short loc_18001BD98
0x18001bd5f  mov     r8d, eax
0x18001bd62  mov     word ptr [rsp+880h+var_840], r12w
0x18001bd68  lea     rdx, aIpcpHelpersetd; "IPCP: HelperSetDefaultInterfaceNet done"...
0x18001bd6f  lea     rcx, [rsp+880h+var_840]
0x18001bd74  call    FormatRRASErrorString
0x18001bd79  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bd80  lea     r8, [rsp+880h+var_840]
0x18001bd85  mov     rcx, cs:gRasIpcpEtwContext
0x18001bd8c  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd98  test    edi, edi
0x18001bd9a  jnz     loc_18001BC6D
0x18001bda0  cmp     [rsi+10h], r12d
0x18001bda4  jz      loc_18001BE3C
0x18001bdaa  mov     rax, qword ptr cs:xmmword_18004D450
0x18001bdb1  mov     r9b, 1
0x18001bdb4  mov     dl, r9b
0x18001bdb7  mov     cl, r9b
0x18001bdba  mov     r8, rbx
0x18001bdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdc2  test    eax, eax
0x18001bdc4  jz      short loc_18001BE16
0x18001bdc6  cmp     qword ptr cs:xmmword_18004D860, r12
0x18001bdcd  mov     edi, 3EBh
0x18001bdd2  jz      loc_18001BC6D
0x18001bdd8  mov     r8d, edi
0x18001bddb  mov     word ptr [rsp+880h+var_840], r12w
0x18001bde1  lea     rdx, aIpcpRasupdated_0; "IPCP:RasUpdateDefaultRouteSettings fail"...
0x18001bde8  lea     rcx, [rsp+880h+var_840]
0x18001bded  call    FormatRRASErrorString
0x18001bdf2  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001bdf9  lea     r8, [rsp+880h+var_840]
0x18001bdfe  mov     rcx, cs:gRasIpcpEtwContext
0x18001be05  mov     rax, cs:gRasIpcpTemplateFunc
0x18001be0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be11  jmp     loc_18001BC6D
0x18001be16  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001be1d  test    rdx, rdx
0x18001be20  jz      short loc_18001BE3C
0x18001be22  mov     rcx, cs:gRasIpcpEtwContext
0x18001be29  lea     r8, aIpcpRasupdated; "IPCP:RasUpdateDefaultRouteSettings succ"...
0x18001be30  mov     rax, cs:gRasIpcpTemplateFunc
0x18001be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be3c  test    r15, r15
0x18001be3f  jz      short loc_18001BE48
0x18001be41  mov     dword ptr [r15], 1
0x18001be48  mov     edx, [rsi+0A8h]
0x18001be4e  mov     r8, rbx
0x18001be51  mov     cl, 1
0x18001be53  call    AdjustSelfInterfaceMetrics
0x18001be58  test    eax, eax
0x18001be5a  jz      short loc_18001BEB4
0x18001be5c  mov     rcx, rsi
0x18001be5f  call    ResetNetBTConfigInfo
0x18001be64  cmp     qword ptr cs:xmmword_18004D860, r12
0x18001be6b  mov     edi, 3EBh
0x18001be70  jz      loc_18001C179
0x18001be76  mov     r8d, edi
0x18001be79  mov     word ptr [rsp+880h+var_840], r12w
0x18001be7f  lea     rdx, aIpcpAdjustself_0; "IPCP:AdjustSelfInterfaceMetrics failed."...
0x18001be86  lea     rcx, [rsp+880h+var_840]
0x18001be8b  call    FormatRRASErrorString
0x18001be90  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001be97  lea     r8, [rsp+880h+var_840]
0x18001be9c  mov     rcx, cs:gRasIpcpEtwContext
0x18001bea3  mov     rax, cs:gRasIpcpTemplateFunc
0x18001beaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beaf  jmp     loc_18001C179
0x18001beb4  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bebb  jz      short loc_18001BEFA
0x18001bebd  mov     r8d, [rsi+0A8h]
0x18001bec4  lea     rdx, aIpcpAdjustself; "IPCP:AdjustSelfInterfaceMetrics to valu"...
0x18001becb  lea     rcx, [rsp+880h+var_840]
0x18001bed0  mov     word ptr [rsp+880h+var_840], r12w
0x18001bed6  call    FormatRRASErrorString
0x18001bedb  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bee2  lea     r8, [rsp+880h+var_840]
0x18001bee7  mov     rcx, cs:gRasIpcpEtwContext
0x18001beee  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001befa  mov     [r14], r12d
0x18001befd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001bf01  mov     r8d, [rsi+6Ch]
0x18001bf05  test    r8d, r8d
0x18001bf08  jz      short loc_18001BF37
0x18001bf0a  lea     rcx, [r14+68h]
0x18001bf0e  mov     rax, [rcx]
0x18001bf11  test    rax, rax
0x18001bf14  jz      short loc_18001BF25
0x18001bf16  mov     rdx, rbx
0x18001bf19  inc     rdx
0x18001bf1c  cmp     [rax+rdx*2], r12w
0x18001bf21  jnz     short loc_18001BF19
0x18001bf23  jmp     short loc_18001BF28
0x18001bf25  mov     rdx, r12
0x18001bf28  call    PrependDwIpAddress
0x18001bf2d  mov     edi, eax
0x18001bf2f  test    eax, eax
0x18001bf31  jnz     loc_18001C179
0x18001bf37  mov     r8d, [rsi+68h]
0x18001bf3b  test    r8d, r8d
0x18001bf3e  jz      short loc_18001BF6C
0x18001bf40  lea     rcx, [r14+68h]
0x18001bf44  mov     rax, [rcx]
0x18001bf47  test    rax, rax
0x18001bf4a  jz      short loc_18001BF58
0x18001bf4c  inc     rbx
0x18001bf4f  cmp     [rax+rbx*2], r12w
0x18001bf54  jnz     short loc_18001BF4C
0x18001bf56  jmp     short loc_18001BF5B
0x18001bf58  mov     rbx, r12
0x18001bf5b  mov     edx, ebx
0x18001bf5d  call    PrependDwIpAddress
0x18001bf62  mov     edi, eax
0x18001bf64  test    eax, eax
0x18001bf66  jnz     loc_18001C179
0x18001bf6c  cmp     qword ptr cs:xmmword_18004D860+8, r12
0x18001bf73  jz      short loc_18001BFBB
0x18001bf75  mov     word ptr [rsp+880h+var_840], r12w
0x18001bf7b  lea     r8, dword_18003DAF4
0x18001bf82  cmp     [r14+68h], r12
0x18001bf86  lea     rdx, aIpcpNewDnsWs; "IPCP: New Dns=%ws"
0x18001bf8d  lea     rcx, [rsp+880h+var_840]
0x18001bf92  cmovnz  r8, [r14+68h]
0x18001bf97  call    FormatRRASErrorString
0x18001bf9c  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001bfa3  lea     r8, [rsp+880h+var_840]
0x18001bfa8  mov     rcx, cs:gRasIpcpEtwContext
0x18001bfaf  mov     rax, cs:gRasIpcpTemplateFunc
0x18001bfb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfbb  cmp     [rsi+40h], r12d
0x18001bfbf  jz      short loc_18001C005
0x18001bfc1  mov     edx, [rsi+64h]
0x18001bfc4  test    edx, edx
0x18001bfc6  jz      short loc_18001BFDB
0x18001bfc8  lea     rcx, [r14+70h]
0x18001bfcc  call    PrependDwIpAddressToMwsz
0x18001bfd1  mov     edi, eax
0x18001bfd3  test    eax, eax
0x18001bfd5  jnz     loc_18001C179
0x18001bfdb  mov     edx, [rsi+60h]
0x18001bfde  test    edx, edx
0x18001bfe0  jz      short loc_18001BFF5
0x18001bfe2  lea     rcx, [r14+70h]
0x18001bfe6  call    PrependDwIpAddressToMwsz
0x18001bfeb  mov     edi, eax
0x18001bfed  test    eax, eax
0x18001bfef  jnz     loc_18001C179
0x18001bff5  mov     rdx, [r14+70h]
0x18001bff9  lea     rcx, aIpcpNewWins; "IPCP: New Wins="
0x18001c000  call    PrintMwsz
0x18001c005  lea     rdx, [rsi+714h]
0x18001c00c  cmp     [rdx], r12b
0x18001c00f  jz      short loc_18001C019
0x18001c011  mov     rcx, r14
0x18001c014  call    AddDNSSuffix
0x18001c019  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001c020  test    rdx, rdx
0x18001c023  jz      short loc_18001C03F
  ... truncated ...
```
