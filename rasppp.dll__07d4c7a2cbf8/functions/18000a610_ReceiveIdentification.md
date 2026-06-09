# ReceiveIdentification

- ea: `0x18000a610`
- end: `0x18000aece`
- name: `ReceiveIdentification`
- size: `2238`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000a610`
- `0x18000b970`
- `0x180013908`
- `0x18001a200`
- `0x18001a330`
- `0x18001aa34`
- `0x18001aac0`
- `0x18002a138`
- `0x180032460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a755`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a76e`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a78a`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ac8f`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a755`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a76e`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000a78a`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ac8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a94c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a94c`

## string_xrefs

- `0x18000a7cb`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000a82f`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000a87c`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000a9c8`: `ReceiveIdentification: insufficient buffer while copying szComputerName`
- `0x18000aa2d`: `ReceiveIdentification: insufficient buffer while copying szComputerName`
- `0x18000ae40`: `ReceiveIdentification: Replaced userlist %p with %p`

## pseudocode

```c
char __fastcall ReceiveIdentification(__int64 a1, __int64 a2, __int64 a3, unsigned __int8 *a4)
{
  _DWORD *v4; // rsi
  int v6; // ebx
  int v7; // r14d
  char *v9; // rax
  __int64 v10; // rbx
  char *v11; // r13
  DWORD LastError; // eax
  __int64 v13; // rcx
  int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // r9
  bool v18; // zf
  __int64 v19; // r9
  __int64 *v20; // rdx
  unsigned int v21; // r14d
  unsigned int v22; // r12d
  __int64 v23; // rax
  DWORD v24; // eax
  __int64 v25; // rax
  const char *v26; // r8
  __int64 v27; // rbx
  size_t v28; // r9
  int v29; // r9d
  __int64 v30; // rax
  unsigned int v31; // eax
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  unsigned int v37; // r11d
  int v38; // r9d
  __int64 v39; // rax
  unsigned int v40; // eax
  __int64 v41; // r8
  int v42; // r9d
  __int64 v43; // rbx
  __int64 v44; // rax
  unsigned int v45; // eax
  __int64 v46; // rax
  _DWORD *v47; // r8
  size_t Size; // [rsp+20h] [rbp-E0h]
  size_t Sizea; // [rsp+20h] [rbp-E0h]
  size_t Sizeb; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+30h] [rbp-D0h]
  int v53; // [rsp+34h] [rbp-CCh]
  size_t cbToCopy; // [rsp+38h] [rbp-C8h]
  STRSAFE_PCNZCH pszSrc; // [rsp+40h] [rbp-C0h]
  int v56; // [rsp+48h] [rbp-B8h] BYREF
  char v57; // [rsp+4Ch] [rbp-B4h]
  unsigned __int8 v58; // [rsp+4Dh] [rbp-B3h]
  char v59[26]; // [rsp+4Eh] [rbp-B2h] BYREF
  int Src; // [rsp+68h] [rbp-98h] BYREF
  char v61; // [rsp+6Ch] [rbp-94h]
  unsigned __int8 v62; // [rsp+6Dh] [rbp-93h]
  char pszDest[34]; // [rsp+6Eh] [rbp-92h] BYREF
  int v64; // [rsp+90h] [rbp-70h] BYREF
  __int16 v65; // [rsp+94h] [rbp-6Ch]
  char v66[58]; // [rsp+96h] [rbp-6Ah] BYREF
  int v67; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v68[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v4 = *(_DWORD **)(a1 + 152);
  v6 = a4[2];
  v7 = a4[3];
  v67 = 0;
  memset_0(v68, 0, sizeof(v68));
  LOBYTE(v9) = byte_18004CF34 & 1;
  if ( (byte_18004CF34 & 1) != 0 )
    LOBYTE(v9) = McTemplateU0z_EventWriteTransfer(
                   &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   RasPppTraceInfo,
                   L"Identification packet received");
  if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
  {
    v10 = (unsigned int)(v7 + (v6 << 8));
    if ( (unsigned int)(v10 - 16) > 0xF )
    {
      *(_BYTE *)(*(_QWORD *)(a1 + 8) + 1276LL) = 0;
      v9 = *(char **)(a1 + 8);
      v9[1301] = 0;
      return (char)v9;
    }
    v9 = (char *)LocalAlloc(0x40u, (unsigned int)v10);
    v11 = v9;
    if ( !v9 )
    {
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v67) = 0;
        LastError = GetLastError();
        LOBYTE(v9) = FormatRRASErrorString(&v67, L"ReceiveIdentification: Failed to alloc memory %d", LastError);
        if ( byte_18004CF33 < 0 )
          LOBYTE(v9) = McTemplateU0z_EventWriteTransfer(
                         &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                         RasPppTraceError,
                         &v67);
      }
      return (char)v9;
    }
    v53 = 0;
    pszSrc = (STRSAFE_PCNZCH)(a4 + 8);
    v52 = 0;
    cbToCopy = v10 - 8;
    memcpy_0(v9, a4 + 8, v10 - 8);
    v11[v10 - 8] = 0;
    if ( strstr(v11, "MSRAS-0-") || strstr(v11, "MSRAS-1-") )
    {
      v14 = 1;
      if ( !RasAuthAttributeGetVendorSpecific(v13, 34, v4) )
        goto LABEL_26;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v19 = *(_QWORD *)(a1 + 16);
        LOWORD(v67) = 0;
        FormatRRASErrorString(&v67, L"ReceiveIndication: Client%hs already present for port %d", "Name", v19);
        v18 = (byte_18004CF34 & 1) == 0;
LABEL_23:
        if ( !v18 )
        {
LABEL_24:
          v20 = RasPppTraceInfo;
LABEL_25:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v20, &v67);
        }
      }
    }
    else
    {
      v14 = 0;
      if ( strstr(v11, "MSRASV") )
      {
        v53 = 1;
        if ( RasAuthAttributeGetVendorSpecific(v15, 35, v4) )
        {
          if ( (byte_18004CF34 & 1) == 0 )
            goto LABEL_92;
          v16 = *(_QWORD *)(a1 + 16);
          LOWORD(v67) = 0;
          FormatRRASErrorString(&v67, L"ReceiveIndication: Client%hs already present for port %d", "Version", v16);
          if ( (byte_18004CF34 & 1) == 0 )
            goto LABEL_92;
          goto LABEL_24;
        }
LABEL_26:
        v21 = 0;
        if ( *v4 )
        {
          do
            ++v21;
          while ( v4[4 * v21] );
        }
        v22 = v21;
        if ( v21 >= 0x15 )
        {
          v23 = RasAuthAttributeCopyWithAlloc(*(_QWORD *)(a1 + 152), 1);
          v4 = (_DWORD *)v23;
          if ( (byte_18004CF34 & 1) != 0 )
          {
            LOWORD(v67) = 0;
            FormatRRASErrorString(&v67, L"ReceiveIdentification: allocated new user list %p", v23);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
          }
          if ( !v4 )
          {
            if ( byte_18004CF33 >= 0 )
              goto LABEL_92;
            LOWORD(v67) = 0;
            v24 = GetLastError();
            FormatRRASErrorString(&v67, L"ReceiveIdentification: Failed to allocate attributes. %d", v24);
            if ( byte_18004CF33 >= 0 )
              goto LABEL_92;
            v20 = RasPppTraceError;
            goto LABEL_25;
          }
          v21 = 0;
        }
        if ( v14 )
        {
          v25 = *(_QWORD *)(a1 + 8);
          *(_OWORD *)(v25 + 1276) = 0;
          *(_OWORD *)(v25 + 1285) = 0;
          if ( StringCbCopyNA((STRSAFE_LPSTR)(*(_QWORD *)(a1 + 8) + 1276LL), 0x19u, v11, cbToCopy) && byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"ReceiveIdentification: insufficient buffer while copying szComputerName");
          v26 = (const char *)(*(_QWORD *)(a1 + 8) + 1276LL);
          v62 = v10 - 5;
          v27 = -1;
          Src = 922812416;
          v28 = -1;
          v61 = 34;
          do
            ++v28;
          while ( v26[v28] );
          if ( StringCbCopyNA(pszDest, 0x1Cu, v26, v28) && byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"ReceiveIdentification: insufficient buffer while copying szComputerName");
          v4[4 * v21] = -1;
          v30 = -1;
          do
            ++v30;
          while ( pszDest[v30] );
          LODWORD(Size) = v30 + 7;
          v31 = RasAuthAttributeInsert(v21, (int)v4, 26, v29, Size, &Src);
          if ( v31 )
          {
            if ( byte_18004CF33 < 0 )
            {
              v32 = *(_QWORD *)(a1 + 8) + 1276LL;
              LOWORD(v67) = 0;
              FormatRRASErrorString(&v67, L"Error inserting user attribute = %hs, %d", v32, v31);
              if ( byte_18004CF33 < 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
            }
          }
          if ( (byte_18004CF34 & 1) == 0 )
            goto LABEL_69;
          LOWORD(v67) = 0;
          do
            ++v27;
          while ( pszDest[v27] );
          v33 = v62;
          v34 = *(_QWORD *)(a1 + 8) + 1276LL;
        }
        else
        {
          if ( !v53 )
          {
            if ( v52 && strstr((const char *)(a1 + 1712), "{NA}") )
            {
              if ( (byte_18004CF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                FormatRRASErrorString(&v67, L"pPcb->CorrelationGuidStr = %hs", a1 + 1712);
                if ( (byte_18004CF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
              }
              *(_OWORD *)(a1 + 1692) = 0;
              *(_OWORD *)(a1 + 1692) = *(_OWORD *)pszSrc;
              PrintGuid((STRSAFE_LPSTR)(a1 + 1712));
              v64 = 922812416;
              v65 = 10552;
              StringCbCopyNA(v66, 0x2Cu, (STRSAFE_PCNZCH)(a1 + 1712), 0x28u);
              v43 = -1;
              v44 = -1;
              v4[4 * v21] = -1;
              do
                ++v44;
              while ( v66[v44] );
              LODWORD(Size) = v44 + 7;
              v45 = RasAuthAttributeInsert(v21, (int)v4, 26, v42, Size, &v64);
              if ( v45 )
              {
                if ( byte_18004CF33 < 0 )
                {
                  LOWORD(v67) = 0;
                  FormatRRASErrorString(&v67, L"Error inserting user attribute = %hs, %d", a1 + 1712, v45);
                  if ( byte_18004CF33 < 0 )
                    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
                }
              }
              if ( (byte_18004CF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                do
                  ++v43;
                while ( v66[v43] );
                LODWORD(Sizeb) = HIBYTE(v65);
                FormatRRASErrorString(&v67, L"Remote identification guid = %hs length %d-%d", a1 + 1712, v43 + 1, Sizeb);
                if ( (byte_18004CF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
              }
              ++v22;
            }
            goto LABEL_87;
          }
          v35 = *(_QWORD *)(a1 + 8);
          *(_QWORD *)(v35 + 1301) = 0;
          *(_DWORD *)(v35 + 1309) = 0;
          StringCbCopyNA((STRSAFE_LPSTR)(*(_QWORD *)(a1 + 8) + 1301LL), 0xCu, pszSrc, cbToCopy);
          v36 = *(_QWORD *)(a1 + 8);
          v56 = 922812416;
          v57 = 35;
          v58 = v10 - 5;
          StringCbCopyNA(v59, 0x18u, (STRSAFE_PCNZCH)(v36 + 1301), v37);
          v27 = -1;
          v39 = -1;
          v4[4 * v21] = -1;
          do
            ++v39;
          while ( v59[v39] );
          LODWORD(Size) = v39 + 7;
          v40 = RasAuthAttributeInsert(v21, (int)v4, 26, v38, Size, &v56);
          if ( v40 )
          {
            if ( byte_18004CF33 < 0 )
            {
              v41 = *(_QWORD *)(a1 + 8) + 1301LL;
              LOWORD(v67) = 0;
              FormatRRASErrorString(&v67, L"Error inserting user attribute = %hs, %d", v41, v40);
              if ( byte_18004CF33 < 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
            }
          }
          if ( (byte_18004CF34 & 1) == 0 )
          {
LABEL_69:
            ++v22;
LABEL_87:
            v46 = 2LL * v22;
            *(_QWORD *)&v4[2 * v46] = 0;
            *(_QWORD *)&v4[2 * v46 + 2] = 0;
            v47 = *(_DWORD **)(a1 + 152);
            if ( v47 != v4 )
            {
              if ( (byte_18004CF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                FormatRRASErrorString(&v67, L"ReceiveIdentification: Replaced userlist %p with %p", v47, v4);
                if ( (byte_18004CF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
              }
              RasAuthAttributeDestroy(*(HLOCAL *)(a1 + 152));
              *(_QWORD *)(a1 + 152) = v4;
            }
            goto LABEL_92;
          }
          LOWORD(v67) = 0;
          do
            ++v27;
          while ( v59[v27] );
          v33 = v58;
          v34 = *(_QWORD *)(a1 + 8) + 1301LL;
        }
        LODWORD(Sizea) = v33;
        FormatRRASErrorString(&v67, L"Remote identification = %hs length %d-%d", v34, v27 + 1, Sizea);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
        goto LABEL_69;
      }
      if ( (_DWORD)v10 != 24 )
        goto LABEL_26;
      v52 = 1;
      if ( !RasAuthAttributeGetVendorSpecific(v15, 56, v4) )
        goto LABEL_26;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v17 = *(_QWORD *)(a1 + 16);
        LOWORD(v67) = 0;
        FormatRRASErrorString(&v67, L"ReceiveIndication: Client%hs already present for port %d", "Version", v17);
        v18 = (byte_18004CF34 & 1) == 0;
        goto LABEL_23;
      }
    }
LABEL_92:
    LOBYTE(v9) = (unsigned __int8)LocalFree(v11);
  }
  return (char)v9;
}

```

## disassembly

```asm
0x18000a610  mov     [rsp-8+arg_8], rbx
0x18000a615  push    rbp
0x18000a616  push    rsi
0x18000a617  push    rdi
0x18000a618  push    r12
0x18000a61a  push    r13
0x18000a61c  push    r14
0x18000a61e  push    r15
0x18000a620  lea     rbp, [rsp-7E0h]
0x18000a628  sub     rsp, 8E0h
0x18000a62f  mov     rax, cs:__security_cookie
0x18000a636  xor     rax, rsp
0x18000a639  mov     [rbp+810h+var_40], rax
0x18000a640  mov     rsi, [rcx+98h]
0x18000a647  mov     rdi, rcx
0x18000a64a  movzx   ebx, byte ptr [r9+2]
0x18000a64f  lea     rcx, [rbp+810h+var_83C]; void *
0x18000a653  movzx   r14d, byte ptr [r9+3]
0x18000a658  xor     r12d, r12d
0x18000a65b  xor     edx, edx; Val
0x18000a65d  mov     [rbp+810h+var_840], r12d
0x18000a661  mov     r8d, 7FCh; Size
0x18000a667  mov     r15, r9
0x18000a66a  call    memset_0
0x18000a66f  mov     al, cs:byte_18004CF34
0x18000a675  and     al, 1
0x18000a677  mov     byte ptr [rsp+910h+var_8E0], al
0x18000a67b  jz      short loc_18000A697
0x18000a67d  lea     r8, aIdentification; "Identification packet received"
0x18000a684  lea     rdx, RasPppTraceInfo
0x18000a68b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a692  call    McTemplateU0z_EventWriteTransfer
0x18000a697  test    byte ptr [rdi+38h], 4
0x18000a69b  jz      loc_18000AEA4
0x18000a6a1  shl     ebx, 8
0x18000a6a4  add     ebx, r14d
0x18000a6a7  lea     eax, [rbx-10h]
0x18000a6aa  cmp     eax, 0Fh
0x18000a6ad  ja      loc_18000AE8E
0x18000a6b3  mov     edx, ebx; uBytes
0x18000a6b5  mov     ecx, 40h ; '@'; uFlags
0x18000a6ba  call    cs:__imp_LocalAlloc
0x18000a6c0  mov     r13, rax
0x18000a6c3  test    rax, rax
0x18000a6c6  jnz     short loc_18000A71C
0x18000a6c8  cmp     cs:byte_18004CF33, r12b
0x18000a6cf  jge     loc_18000AEA4
0x18000a6d5  mov     word ptr [rbp+810h+var_840], r12w
0x18000a6da  call    cs:__imp_GetLastError
0x18000a6e0  mov     r8d, eax
0x18000a6e3  lea     rdx, aReceiveidentif_3; "ReceiveIdentification: Failed to alloc "...
0x18000a6ea  lea     rcx, [rbp+810h+var_840]
0x18000a6ee  call    FormatRRASErrorString
0x18000a6f3  cmp     cs:byte_18004CF33, r12b
0x18000a6fa  jge     loc_18000AEA4
0x18000a700  lea     r8, [rbp+810h+var_840]
0x18000a704  lea     rdx, RasPppTraceError
0x18000a70b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a712  call    McTemplateU0z_EventWriteTransfer
0x18000a717  jmp     loc_18000AEA4
0x18000a71c  lea     rcx, [r15+8]
0x18000a720  mov     [rsp+910h+var_8DC], r12d
0x18000a725  lea     rax, [rbx-8]
0x18000a729  mov     [rsp+910h+pszSrc], rcx
0x18000a72e  mov     rdx, rcx; Src
0x18000a731  mov     [rsp+910h+var_8E0], r12d
0x18000a736  mov     rcx, r13; void *
0x18000a739  mov     [rsp+910h+cbToCopy], rax
0x18000a73e  mov     r8, rax; Size
0x18000a741  call    memcpy_0
0x18000a746  lea     rdx, SubStr; "MSRAS-0-"
0x18000a74d  mov     [rbx+r13-8], r12b
0x18000a752  mov     rcx, r13; Str
0x18000a755  call    cs:__imp_strstr
0x18000a75b  test    rax, rax
0x18000a75e  jnz     loc_18000A84D
0x18000a764  lea     rdx, aMsras1; "MSRAS-1-"
0x18000a76b  mov     rcx, r13; Str
0x18000a76e  call    cs:__imp_strstr
0x18000a774  test    rax, rax
0x18000a777  jnz     loc_18000A84D
0x18000a77d  lea     rdx, aMsrasv; "MSRASV"
0x18000a784  mov     rcx, r13; Str
0x18000a787  mov     r15d, r12d
0x18000a78a  call    cs:__imp_strstr
0x18000a790  test    rax, rax
0x18000a793  jz      short loc_18000A7F2
0x18000a795  mov     r8, rsi
0x18000a798  mov     [rsp+910h+var_8DC], 1
0x18000a7a0  mov     edx, 23h ; '#'
0x18000a7a5  call    RasAuthAttributeGetVendorSpecific
0x18000a7aa  test    rax, rax
0x18000a7ad  jz      loc_18000A8BA
0x18000a7b3  test    cs:byte_18004CF34, 1
0x18000a7ba  jz      loc_18000AE83
0x18000a7c0  mov     r9, [rdi+10h]
0x18000a7c4  lea     r8, aVersion; "Version"
0x18000a7cb  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000a7d2  mov     word ptr [rbp+810h+var_840], r12w
0x18000a7d7  lea     rcx, [rbp+810h+var_840]
0x18000a7db  call    FormatRRASErrorString
0x18000a7e0  test    cs:byte_18004CF34, 1
0x18000a7e7  jnz     loc_18000A89E
0x18000a7ed  jmp     loc_18000AE83
0x18000a7f2  cmp     ebx, 18h
0x18000a7f5  jnz     loc_18000A8BA
0x18000a7fb  mov     r8, rsi
0x18000a7fe  mov     [rsp+910h+var_8E0], 1
0x18000a806  lea     edx, [rbx+20h]
0x18000a809  call    RasAuthAttributeGetVendorSpecific
0x18000a80e  test    rax, rax
0x18000a811  jz      loc_18000A8BA
0x18000a817  test    cs:byte_18004CF34, 1
0x18000a81e  jz      loc_18000AE83
0x18000a824  mov     r9, [rdi+10h]
0x18000a828  lea     r8, aVersion; "Version"
0x18000a82f  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000a836  mov     word ptr [rbp+810h+var_840], r12w
0x18000a83b  lea     rcx, [rbp+810h+var_840]
0x18000a83f  call    FormatRRASErrorString
0x18000a844  test    cs:byte_18004CF34, 1
0x18000a84b  jmp     short loc_18000A898
0x18000a84d  mov     r15d, 1
0x18000a853  mov     r8, rsi
0x18000a856  lea     edx, [r15+21h]
0x18000a85a  call    RasAuthAttributeGetVendorSpecific
0x18000a85f  test    rax, rax
0x18000a862  jz      short loc_18000A8BA
0x18000a864  test    cs:byte_18004CF34, r15b
0x18000a86b  jz      loc_18000AE83
0x18000a871  mov     r9, [rdi+10h]
0x18000a875  lea     r8, aName; "Name"
0x18000a87c  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000a883  mov     word ptr [rbp+810h+var_840], r12w
0x18000a888  lea     rcx, [rbp+810h+var_840]
0x18000a88c  call    FormatRRASErrorString
0x18000a891  test    cs:byte_18004CF34, r15b
0x18000a898  jz      loc_18000AE83
0x18000a89e  lea     rdx, RasPppTraceInfo
0x18000a8a5  lea     r8, [rbp+810h+var_840]
0x18000a8a9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a8b0  call    McTemplateU0z_EventWriteTransfer
0x18000a8b5  jmp     loc_18000AE83
0x18000a8ba  mov     r14d, r12d
0x18000a8bd  cmp     [rsi], r12d
0x18000a8c0  jz      short loc_18000A8D1
0x18000a8c2  inc     r14d
0x18000a8c5  mov     eax, r14d
0x18000a8c8  add     rax, rax
0x18000a8cb  cmp     [rsi+rax*8], r12d
0x18000a8cf  jnz     short loc_18000A8C2
0x18000a8d1  mov     r12d, r14d
0x18000a8d4  cmp     r14d, 15h
0x18000a8d8  jb      loc_18000A981
0x18000a8de  mov     rcx, [rdi+98h]
0x18000a8e5  mov     edx, 1
0x18000a8ea  call    RasAuthAttributeCopyWithAlloc
0x18000a8ef  test    cs:byte_18004CF34, 1
0x18000a8f6  mov     rsi, rax
0x18000a8f9  jz      short loc_18000A934
0x18000a8fb  xor     ecx, ecx
0x18000a8fd  lea     rdx, aReceiveidentif_1; "ReceiveIdentification: allocated new us"...
0x18000a904  mov     word ptr [rbp+810h+var_840], cx
0x18000a908  mov     r8, rax
0x18000a90b  lea     rcx, [rbp+810h+var_840]
0x18000a90f  call    FormatRRASErrorString
0x18000a914  test    cs:byte_18004CF34, 1
0x18000a91b  jz      short loc_18000A934
0x18000a91d  lea     r8, [rbp+810h+var_840]
0x18000a921  lea     rdx, RasPppTraceInfo
0x18000a928  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a92f  call    McTemplateU0z_EventWriteTransfer
0x18000a934  test    rsi, rsi
0x18000a937  jnz     short loc_18000A97E
0x18000a939  cmp     cs:byte_18004CF33, sil
0x18000a940  jge     loc_18000AE83
0x18000a946  xor     eax, eax
0x18000a948  mov     word ptr [rbp+810h+var_840], ax
0x18000a94c  call    cs:__imp_GetLastError
0x18000a952  mov     r8d, eax
0x18000a955  lea     rdx, aReceiveidentif_2; "ReceiveIdentification: Failed to alloca"...
0x18000a95c  lea     rcx, [rbp+810h+var_840]
0x18000a960  call    FormatRRASErrorString
0x18000a965  cmp     cs:byte_18004CF33, sil
0x18000a96c  jge     loc_18000AE83
0x18000a972  lea     rdx, RasPppTraceError
0x18000a979  jmp     loc_18000A8A5
0x18000a97e  xor     r14d, r14d
0x18000a981  test    r15d, r15d
0x18000a984  jz      loc_18000AB08
0x18000a98a  mov     rax, [rdi+8]
0x18000a98e  mov     edx, 4FCh
0x18000a993  mov     r9, [rsp+910h+cbToCopy]; cbToCopy
0x18000a998  xorps   xmm0, xmm0
0x18000a99b  mov     r8, r13; pszSrc
0x18000a99e  movups  xmmword ptr [rax+rdx], xmm0
0x18000a9a2  movups  xmmword ptr [rax+rdx+9], xmm0
0x18000a9a7  mov     rcx, [rdi+8]
0x18000a9ab  add     rcx, rdx; pszDest
0x18000a9ae  mov     edx, 19h; cbDest
0x18000a9b3  call    StringCbCopyNA
0x18000a9b8  xor     r15d, r15d
0x18000a9bb  test    eax, eax
0x18000a9bd  jz      short loc_18000A9E2
0x18000a9bf  test    cs:byte_18004CF33, 80h
0x18000a9c6  jz      short loc_18000A9E2
0x18000a9c8  lea     r8, aReceiveidentif; "ReceiveIdentification: insufficient buf"...
0x18000a9cf  lea     rdx, RasPppTraceError
0x18000a9d6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a9dd  call    McTemplateU0z_EventWriteTransfer
0x18000a9e2  mov     r8, [rdi+8]
0x18000a9e6  sub     bl, 5
0x18000a9e9  add     r8, 4FCh; pszSrc
0x18000a9f0  mov     [rsp+910h+var_8A3], bl
0x18000a9f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a9f8  mov     [rsp+910h+var_8A8], 37010000h
0x18000aa00  mov     r9, rbx
0x18000aa03  mov     [rsp+910h+var_8A4], 22h ; '"'
0x18000aa08  inc     r9; cbToCopy
0x18000aa0b  cmp     [r8+r9], r15b
0x18000aa0f  jnz     short loc_18000AA08
0x18000aa11  mov     edx, 1Ch; cbDest
0x18000aa16  lea     rcx, [rsp+910h+pszDest]; pszDest
0x18000aa1b  call    StringCbCopyNA
0x18000aa20  test    eax, eax
0x18000aa22  jz      short loc_18000AA47
0x18000aa24  test    cs:byte_18004CF33, 80h
0x18000aa2b  jz      short loc_18000AA47
0x18000aa2d  lea     r8, aReceiveidentif; "ReceiveIdentification: insufficient buf"...
0x18000aa34  lea     rdx, RasPppTraceError
0x18000aa3b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aa42  call    McTemplateU0z_EventWriteTransfer
0x18000aa47  mov     eax, r14d
0x18000aa4a  lea     rcx, [rsp+910h+pszDest]
0x18000aa4f  add     rax, rax
0x18000aa52  mov     [rsi+rax*8], ebx
0x18000aa55  mov     rax, rbx
0x18000aa58  inc     rax
0x18000aa5b  cmp     [rcx+rax], r15b
0x18000aa5f  jnz     short loc_18000AA58
0x18000aa61  lea     rcx, [rsp+910h+var_8A8]
0x18000aa66  add     eax, 7
0x18000aa69  mov     [rsp+910h+Src], rcx; Src
0x18000aa6e  mov     r8d, 1Ah; int
0x18000aa74  mov     ecx, r14d; int
0x18000aa77  mov     dword ptr [rsp+910h+Size], eax; Size
0x18000aa7b  mov     rdx, rsi; int
0x18000aa7e  call    RasAuthAttributeInsert
0x18000aa83  test    eax, eax
0x18000aa85  jz      short loc_18000AAD3
0x18000aa87  cmp     cs:byte_18004CF33, r15b
0x18000aa8e  jge     short loc_18000AAD3
0x18000aa90  mov     r8, [rdi+8]
0x18000aa94  lea     rdx, aErrorInserting; "Error inserting user attribute = %hs, %"...
0x18000aa9b  add     r8, 4FCh
0x18000aaa2  mov     word ptr [rbp+810h+var_840], r15w
0x18000aaa7  mov     r9d, eax
0x18000aaaa  lea     rcx, [rbp+810h+var_840]
0x18000aaae  call    FormatRRASErrorString
0x18000aab3  cmp     cs:byte_18004CF33, r15b
0x18000aaba  jge     short loc_18000AAD3
0x18000aabc  lea     r8, [rbp+810h+var_840]
0x18000aac0  lea     rdx, RasPppTraceError
0x18000aac7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aace  call    McTemplateU0z_EventWriteTransfer
0x18000aad3  test    cs:byte_18004CF34, 1
0x18000aada  jz      loc_18000AC6B
0x18000aae0  mov     word ptr [rbp+810h+var_840], r15w
0x18000aae5  lea     rax, [rsp+910h+pszDest]
0x18000aaea  inc     rbx
0x18000aaed  cmp     [rax+rbx], r15b
0x18000aaf1  jnz     short loc_18000AAEA
0x18000aaf3  mov     r8, [rdi+8]
0x18000aaf7  movzx   eax, [rsp+910h+var_8A3]
0x18000aafc  add     r8, 4FCh
0x18000ab03  jmp     loc_18000AC33
0x18000ab08  xor     r15d, r15d
0x18000ab0b  cmp     [rsp+910h+var_8DC], r15d
0x18000ab10  jz      loc_18000AC73
0x18000ab16  mov     rax, [rdi+8]
0x18000ab1a  lea     r11d, [r15+0Ch]
0x18000ab1e  mov     r9, [rsp+910h+cbToCopy]; cbToCopy
0x18000ab23  xor     ecx, ecx
0x18000ab25  mov     r8, [rsp+910h+pszSrc]; pszSrc
0x18000ab2a  mov     edx, 515h
0x18000ab2f  mov     [rax+rdx], rcx
0x18000ab33  mov     [rax+rdx+8], ecx
0x18000ab37  mov     rcx, [rdi+8]
0x18000ab3b  add     rcx, rdx; pszDest
0x18000ab3e  mov     edx, r11d; cbDest
0x18000ab41  call    StringCbCopyNA
0x18000ab46  mov     r8, [rdi+8]
0x18000ab4a  lea     edx, [r15+18h]; cbDest
0x18000ab4e  sub     bl, 5
0x18000ab51  mov     [rsp+910h+var_8C8], 37010000h
0x18000ab59  add     r8, 515h; pszSrc
0x18000ab60  mov     [rsp+910h+var_8C4], 23h ; '#'
0x18000ab65  mov     r9d, r11d; cbToCopy
0x18000ab68  mov     [rsp+910h+var_8C3], bl
0x18000ab6c  lea     rcx, [rsp+910h+var_8C2]; pszDest
  ... truncated ...
```
