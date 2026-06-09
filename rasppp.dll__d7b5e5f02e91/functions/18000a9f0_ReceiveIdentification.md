# ReceiveIdentification

- ea: `0x18000a9f0`
- end: `0x18000b2df`
- name: `ReceiveIdentification`
- size: `2287`
- prototype: `char __fastcall(__int64, __int64, __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000a9f0`
- `0x18000bd94`
- `0x180013fcc`
- `0x18001aba0`
- `0x18001acd8`
- `0x18001b424`
- `0x18001b4b0`
- `0x18002b0dc`
- `0x180033a80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab41`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab60`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab82`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000b093`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab41`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab60`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000ab82`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000b093`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b290`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad4a`

## string_xrefs

- `0x18000abc9`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000ac2d`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000ac7a`: `ReceiveIndication: Client%hs already present for port %d`
- `0x18000adcc`: `ReceiveIdentification: insufficient buffer while copying szComputerName`
- `0x18000ae31`: `ReceiveIdentification: insufficient buffer while copying szComputerName`
- `0x18000b24a`: `ReceiveIdentification: Replaced userlist %p with %p`

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
  _DWORD *v23; // rax
  DWORD v24; // eax
  __int64 v25; // rax
  const char *v26; // r8
  __int64 v27; // rbx
  size_t v28; // r9
  __int64 v29; // r9
  __int64 v30; // rax
  DWORD v31; // eax
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  unsigned int v37; // r11d
  __int64 v38; // r9
  __int64 v39; // rax
  DWORD v40; // eax
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rbx
  __int64 v44; // rax
  DWORD v45; // eax
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
  LOBYTE(v9) = byte_18004DF34 & 1;
  if ( (byte_18004DF34 & 1) != 0 )
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
      if ( byte_18004DF33 < 0 )
      {
        LOWORD(v67) = 0;
        LastError = GetLastError();
        LOBYTE(v9) = FormatRRASErrorString(
                       (wchar_t *)&v67,
                       L"ReceiveIdentification: Failed to alloc memory %d",
                       LastError);
        if ( byte_18004DF33 < 0 )
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
      if ( !RasAuthAttributeGetVendorSpecific(v13, 34, (__int64)v4) )
        goto LABEL_26;
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v19 = *(_QWORD *)(a1 + 16);
        LOWORD(v67) = 0;
        FormatRRASErrorString((wchar_t *)&v67, L"ReceiveIndication: Client%hs already present for port %d", "Name", v19);
        v18 = (byte_18004DF34 & 1) == 0;
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
        if ( RasAuthAttributeGetVendorSpecific(v15, 35, (__int64)v4) )
        {
          if ( (byte_18004DF34 & 1) == 0 )
            goto LABEL_92;
          v16 = *(_QWORD *)(a1 + 16);
          LOWORD(v67) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v67,
            L"ReceiveIndication: Client%hs already present for port %d",
            "Version",
            v16);
          if ( (byte_18004DF34 & 1) == 0 )
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
          v23 = RasAuthAttributeCopyWithAlloc(*(_DWORD **)(a1 + 152), 1u);
          v4 = v23;
          if ( (byte_18004DF34 & 1) != 0 )
          {
            LOWORD(v67) = 0;
            FormatRRASErrorString((wchar_t *)&v67, L"ReceiveIdentification: allocated new user list %p", v23);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
          }
          if ( !v4 )
          {
            if ( byte_18004DF33 >= 0 )
              goto LABEL_92;
            LOWORD(v67) = 0;
            v24 = GetLastError();
            FormatRRASErrorString((wchar_t *)&v67, L"ReceiveIdentification: Failed to allocate attributes. %d", v24);
            if ( byte_18004DF33 >= 0 )
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
          if ( StringCbCopyNA((STRSAFE_LPSTR)(*(_QWORD *)(a1 + 8) + 1276LL), 0x19u, v11, cbToCopy) && byte_18004DF33 < 0 )
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
          if ( StringCbCopyNA(pszDest, 0x1Cu, v26, v28) && byte_18004DF33 < 0 )
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
          v31 = RasAuthAttributeInsert(v21, (__int64)v4, 26, v29, Size, &Src);
          if ( v31 )
          {
            if ( byte_18004DF33 < 0 )
            {
              v32 = *(_QWORD *)(a1 + 8) + 1276LL;
              LOWORD(v67) = 0;
              FormatRRASErrorString((wchar_t *)&v67, L"Error inserting user attribute = %hs, %d", v32, v31);
              if ( byte_18004DF33 < 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
            }
          }
          if ( (byte_18004DF34 & 1) == 0 )
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
              if ( (byte_18004DF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                FormatRRASErrorString((wchar_t *)&v67, L"pPcb->CorrelationGuidStr = %hs", a1 + 1712);
                if ( (byte_18004DF34 & 1) != 0 )
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
              v45 = RasAuthAttributeInsert(v21, (__int64)v4, 26, v42, Size, &v64);
              if ( v45 )
              {
                if ( byte_18004DF33 < 0 )
                {
                  LOWORD(v67) = 0;
                  FormatRRASErrorString((wchar_t *)&v67, L"Error inserting user attribute = %hs, %d", a1 + 1712, v45);
                  if ( byte_18004DF33 < 0 )
                    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
                }
              }
              if ( (byte_18004DF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                do
                  ++v43;
                while ( v66[v43] );
                LODWORD(Sizeb) = HIBYTE(v65);
                FormatRRASErrorString(
                  (wchar_t *)&v67,
                  L"Remote identification guid = %hs length %d-%d",
                  a1 + 1712,
                  v43 + 1,
                  Sizeb);
                if ( (byte_18004DF34 & 1) != 0 )
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
          v40 = RasAuthAttributeInsert(v21, (__int64)v4, 26, v38, Size, &v56);
          if ( v40 )
          {
            if ( byte_18004DF33 < 0 )
            {
              v41 = *(_QWORD *)(a1 + 8) + 1301LL;
              LOWORD(v67) = 0;
              FormatRRASErrorString((wchar_t *)&v67, L"Error inserting user attribute = %hs, %d", v41, v40);
              if ( byte_18004DF33 < 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v67);
            }
          }
          if ( (byte_18004DF34 & 1) == 0 )
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
              if ( (byte_18004DF34 & 1) != 0 )
              {
                LOWORD(v67) = 0;
                FormatRRASErrorString((wchar_t *)&v67, L"ReceiveIdentification: Replaced userlist %p with %p", v47, v4);
                if ( (byte_18004DF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
              }
              RasAuthAttributeDestroy(*(_DWORD **)(a1 + 152));
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
        FormatRRASErrorString((wchar_t *)&v67, L"Remote identification = %hs length %d-%d", v34, v27 + 1, Sizea);
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v67);
        goto LABEL_69;
      }
      if ( (_DWORD)v10 != 24 )
        goto LABEL_26;
      v52 = 1;
      if ( !RasAuthAttributeGetVendorSpecific(v15, 56, (__int64)v4) )
        goto LABEL_26;
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v17 = *(_QWORD *)(a1 + 16);
        LOWORD(v67) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v67,
          L"ReceiveIndication: Client%hs already present for port %d",
          "Version",
          v17);
        v18 = (byte_18004DF34 & 1) == 0;
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
0x18000a9f0  mov     [rsp-8+arg_8], rbx
0x18000a9f5  push    rbp
0x18000a9f6  push    rsi
0x18000a9f7  push    rdi
0x18000a9f8  push    r12
0x18000a9fa  push    r13
0x18000a9fc  push    r14
0x18000a9fe  push    r15
0x18000aa00  lea     rbp, [rsp-7E0h]
0x18000aa08  sub     rsp, 8E0h
0x18000aa0f  mov     rax, cs:__security_cookie
0x18000aa16  xor     rax, rsp
0x18000aa19  mov     [rbp+810h+var_40], rax
0x18000aa20  mov     rsi, [rcx+98h]
0x18000aa27  mov     rdi, rcx
0x18000aa2a  movzx   ebx, byte ptr [r9+2]
0x18000aa2f  lea     rcx, [rbp+810h+var_83C]; void *
0x18000aa33  movzx   r14d, byte ptr [r9+3]
0x18000aa38  xor     r12d, r12d
0x18000aa3b  xor     edx, edx; Val
0x18000aa3d  mov     [rbp+810h+var_840], r12d
0x18000aa41  mov     r8d, 7FCh; Size
0x18000aa47  mov     r15, r9
0x18000aa4a  call    memset_0
0x18000aa4f  mov     al, cs:byte_18004DF34
0x18000aa55  and     al, 1
0x18000aa57  mov     byte ptr [rsp+910h+var_8E0], al
0x18000aa5b  jz      short loc_18000AA77
0x18000aa5d  lea     r8, aIdentification; "Identification packet received"
0x18000aa64  lea     rdx, RasPppTraceInfo
0x18000aa6b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aa72  call    McTemplateU0z_EventWriteTransfer
0x18000aa77  test    byte ptr [rdi+38h], 4
0x18000aa7b  jz      loc_18000B2B4
0x18000aa81  shl     ebx, 8
0x18000aa84  add     ebx, r14d
0x18000aa87  lea     eax, [rbx-10h]
0x18000aa8a  cmp     eax, 0Fh
0x18000aa8d  ja      loc_18000B29E
0x18000aa93  mov     edx, ebx; uBytes
0x18000aa95  mov     ecx, 40h ; '@'; uFlags
0x18000aa9a  call    cs:__imp_LocalAlloc
0x18000aaa1  nop     dword ptr [rax+rax+00h]
0x18000aaa6  mov     r13, rax
0x18000aaa9  test    rax, rax
0x18000aaac  jnz     short loc_18000AB08
0x18000aaae  cmp     cs:byte_18004DF33, r12b
0x18000aab5  jge     loc_18000B2B4
0x18000aabb  mov     word ptr [rbp+810h+var_840], r12w
0x18000aac0  call    cs:__imp_GetLastError
0x18000aac7  nop     dword ptr [rax+rax+00h]
0x18000aacc  mov     r8d, eax
0x18000aacf  lea     rdx, aReceiveidentif_3; "ReceiveIdentification: Failed to alloc "...
0x18000aad6  lea     rcx, [rbp+810h+var_840]
0x18000aada  call    FormatRRASErrorString
0x18000aadf  cmp     cs:byte_18004DF33, r12b
0x18000aae6  jge     loc_18000B2B4
0x18000aaec  lea     r8, [rbp+810h+var_840]
0x18000aaf0  lea     rdx, RasPppTraceError
0x18000aaf7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aafe  call    McTemplateU0z_EventWriteTransfer
0x18000ab03  jmp     loc_18000B2B4
0x18000ab08  lea     rcx, [r15+8]
0x18000ab0c  mov     [rsp+910h+var_8DC], r12d
0x18000ab11  lea     rax, [rbx-8]
0x18000ab15  mov     [rsp+910h+pszSrc], rcx
0x18000ab1a  mov     rdx, rcx; Src
0x18000ab1d  mov     [rsp+910h+var_8E0], r12d
0x18000ab22  mov     rcx, r13; void *
0x18000ab25  mov     [rsp+910h+cbToCopy], rax
0x18000ab2a  mov     r8, rax; Size
0x18000ab2d  call    memcpy_0
0x18000ab32  lea     rdx, SubStr; "MSRAS-0-"
0x18000ab39  mov     [rbx+r13-8], r12b
0x18000ab3e  mov     rcx, r13; Str
0x18000ab41  call    cs:__imp_strstr
0x18000ab48  nop     dword ptr [rax+rax+00h]
0x18000ab4d  test    rax, rax
0x18000ab50  jnz     loc_18000AC4B
0x18000ab56  lea     rdx, aMsras1; "MSRAS-1-"
0x18000ab5d  mov     rcx, r13; Str
0x18000ab60  call    cs:__imp_strstr
0x18000ab67  nop     dword ptr [rax+rax+00h]
0x18000ab6c  test    rax, rax
0x18000ab6f  jnz     loc_18000AC4B
0x18000ab75  lea     rdx, aMsrasv; "MSRASV"
0x18000ab7c  mov     rcx, r13; Str
0x18000ab7f  mov     r15d, r12d
0x18000ab82  call    cs:__imp_strstr
0x18000ab89  nop     dword ptr [rax+rax+00h]
0x18000ab8e  test    rax, rax
0x18000ab91  jz      short loc_18000ABF0
0x18000ab93  mov     r8, rsi
0x18000ab96  mov     [rsp+910h+var_8DC], 1
0x18000ab9e  mov     edx, 23h ; '#'
0x18000aba3  call    RasAuthAttributeGetVendorSpecific
0x18000aba8  test    rax, rax
0x18000abab  jz      loc_18000ACB8
0x18000abb1  test    cs:byte_18004DF34, 1
0x18000abb8  jz      loc_18000B28D
0x18000abbe  mov     r9, [rdi+10h]
0x18000abc2  lea     r8, aVersion; "Version"
0x18000abc9  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000abd0  mov     word ptr [rbp+810h+var_840], r12w
0x18000abd5  lea     rcx, [rbp+810h+var_840]
0x18000abd9  call    FormatRRASErrorString
0x18000abde  test    cs:byte_18004DF34, 1
0x18000abe5  jnz     loc_18000AC9C
0x18000abeb  jmp     loc_18000B28D
0x18000abf0  cmp     ebx, 18h
0x18000abf3  jnz     loc_18000ACB8
0x18000abf9  mov     r8, rsi
0x18000abfc  mov     [rsp+910h+var_8E0], 1
0x18000ac04  lea     edx, [rbx+20h]
0x18000ac07  call    RasAuthAttributeGetVendorSpecific
0x18000ac0c  test    rax, rax
0x18000ac0f  jz      loc_18000ACB8
0x18000ac15  test    cs:byte_18004DF34, 1
0x18000ac1c  jz      loc_18000B28D
0x18000ac22  mov     r9, [rdi+10h]
0x18000ac26  lea     r8, aVersion; "Version"
0x18000ac2d  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000ac34  mov     word ptr [rbp+810h+var_840], r12w
0x18000ac39  lea     rcx, [rbp+810h+var_840]
0x18000ac3d  call    FormatRRASErrorString
0x18000ac42  test    cs:byte_18004DF34, 1
0x18000ac49  jmp     short loc_18000AC96
0x18000ac4b  mov     r15d, 1
0x18000ac51  mov     r8, rsi
0x18000ac54  lea     edx, [r15+21h]
0x18000ac58  call    RasAuthAttributeGetVendorSpecific
0x18000ac5d  test    rax, rax
0x18000ac60  jz      short loc_18000ACB8
0x18000ac62  test    cs:byte_18004DF34, r15b
0x18000ac69  jz      loc_18000B28D
0x18000ac6f  mov     r9, [rdi+10h]
0x18000ac73  lea     r8, aName; "Name"
0x18000ac7a  lea     rdx, aReceiveindicat; "ReceiveIndication: Client%hs already pr"...
0x18000ac81  mov     word ptr [rbp+810h+var_840], r12w
0x18000ac86  lea     rcx, [rbp+810h+var_840]
0x18000ac8a  call    FormatRRASErrorString
0x18000ac8f  test    cs:byte_18004DF34, r15b
0x18000ac96  jz      loc_18000B28D
0x18000ac9c  lea     rdx, RasPppTraceInfo
0x18000aca3  lea     r8, [rbp+810h+var_840]
0x18000aca7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000acae  call    McTemplateU0z_EventWriteTransfer
0x18000acb3  jmp     loc_18000B28D
0x18000acb8  mov     r14d, r12d
0x18000acbb  cmp     [rsi], r12d
0x18000acbe  jz      short loc_18000ACCF
0x18000acc0  inc     r14d
0x18000acc3  mov     eax, r14d
0x18000acc6  add     rax, rax
0x18000acc9  cmp     [rsi+rax*8], r12d
0x18000accd  jnz     short loc_18000ACC0
0x18000accf  mov     r12d, r14d
0x18000acd2  cmp     r14d, 15h
0x18000acd6  jb      loc_18000AD85
0x18000acdc  mov     rcx, [rdi+98h]
0x18000ace3  mov     edx, 1
0x18000ace8  call    RasAuthAttributeCopyWithAlloc
0x18000aced  test    cs:byte_18004DF34, 1
0x18000acf4  mov     rsi, rax
0x18000acf7  jz      short loc_18000AD32
0x18000acf9  xor     ecx, ecx
0x18000acfb  lea     rdx, aReceiveidentif_1; "ReceiveIdentification: allocated new us"...
0x18000ad02  mov     word ptr [rbp+810h+var_840], cx
0x18000ad06  mov     r8, rax
0x18000ad09  lea     rcx, [rbp+810h+var_840]
0x18000ad0d  call    FormatRRASErrorString
0x18000ad12  test    cs:byte_18004DF34, 1
0x18000ad19  jz      short loc_18000AD32
0x18000ad1b  lea     r8, [rbp+810h+var_840]
0x18000ad1f  lea     rdx, RasPppTraceInfo
0x18000ad26  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ad2d  call    McTemplateU0z_EventWriteTransfer
0x18000ad32  test    rsi, rsi
0x18000ad35  jnz     short loc_18000AD82
0x18000ad37  cmp     cs:byte_18004DF33, sil
0x18000ad3e  jge     loc_18000B28D
0x18000ad44  xor     eax, eax
0x18000ad46  mov     word ptr [rbp+810h+var_840], ax
0x18000ad4a  call    cs:__imp_GetLastError
0x18000ad51  nop     dword ptr [rax+rax+00h]
0x18000ad56  mov     r8d, eax
0x18000ad59  lea     rdx, aReceiveidentif_2; "ReceiveIdentification: Failed to alloca"...
0x18000ad60  lea     rcx, [rbp+810h+var_840]
0x18000ad64  call    FormatRRASErrorString
0x18000ad69  cmp     cs:byte_18004DF33, sil
0x18000ad70  jge     loc_18000B28D
0x18000ad76  lea     rdx, RasPppTraceError
0x18000ad7d  jmp     loc_18000ACA3
0x18000ad82  xor     r14d, r14d
0x18000ad85  test    r15d, r15d
0x18000ad88  jz      loc_18000AF0C
0x18000ad8e  mov     rax, [rdi+8]
0x18000ad92  mov     edx, 4FCh
0x18000ad97  mov     r9, [rsp+910h+cbToCopy]; cbToCopy
0x18000ad9c  xorps   xmm0, xmm0
0x18000ad9f  mov     r8, r13; pszSrc
0x18000ada2  movups  xmmword ptr [rax+rdx], xmm0
0x18000ada6  movups  xmmword ptr [rax+rdx+9], xmm0
0x18000adab  mov     rcx, [rdi+8]
0x18000adaf  add     rcx, rdx; pszDest
0x18000adb2  mov     edx, 19h; cbDest
0x18000adb7  call    StringCbCopyNA
0x18000adbc  xor     r15d, r15d
0x18000adbf  test    eax, eax
0x18000adc1  jz      short loc_18000ADE6
0x18000adc3  test    cs:byte_18004DF33, 80h
0x18000adca  jz      short loc_18000ADE6
0x18000adcc  lea     r8, aReceiveidentif; "ReceiveIdentification: insufficient buf"...
0x18000add3  lea     rdx, RasPppTraceError
0x18000adda  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ade1  call    McTemplateU0z_EventWriteTransfer
0x18000ade6  mov     r8, [rdi+8]
0x18000adea  sub     bl, 5
0x18000aded  add     r8, 4FCh; pszSrc
0x18000adf4  mov     [rsp+910h+var_8A3], bl
0x18000adf8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000adfc  mov     [rsp+910h+var_8A8], 37010000h
0x18000ae04  mov     r9, rbx
0x18000ae07  mov     [rsp+910h+var_8A4], 22h ; '"'
0x18000ae0c  inc     r9; cbToCopy
0x18000ae0f  cmp     [r8+r9], r15b
0x18000ae13  jnz     short loc_18000AE0C
0x18000ae15  mov     edx, 1Ch; cbDest
0x18000ae1a  lea     rcx, [rsp+910h+pszDest]; pszDest
0x18000ae1f  call    StringCbCopyNA
0x18000ae24  test    eax, eax
0x18000ae26  jz      short loc_18000AE4B
0x18000ae28  test    cs:byte_18004DF33, 80h
0x18000ae2f  jz      short loc_18000AE4B
0x18000ae31  lea     r8, aReceiveidentif; "ReceiveIdentification: insufficient buf"...
0x18000ae38  lea     rdx, RasPppTraceError
0x18000ae3f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ae46  call    McTemplateU0z_EventWriteTransfer
0x18000ae4b  mov     eax, r14d
0x18000ae4e  lea     rcx, [rsp+910h+pszDest]
0x18000ae53  add     rax, rax
0x18000ae56  mov     [rsi+rax*8], ebx
0x18000ae59  mov     rax, rbx
0x18000ae5c  inc     rax
0x18000ae5f  cmp     [rcx+rax], r15b
0x18000ae63  jnz     short loc_18000AE5C
0x18000ae65  lea     rcx, [rsp+910h+var_8A8]
0x18000ae6a  add     eax, 7
0x18000ae6d  mov     [rsp+910h+Src], rcx; Src
0x18000ae72  mov     r8d, 1Ah; int
0x18000ae78  mov     ecx, r14d; int
0x18000ae7b  mov     dword ptr [rsp+910h+Size], eax; Size
0x18000ae7f  mov     rdx, rsi; int
0x18000ae82  call    RasAuthAttributeInsert
0x18000ae87  test    eax, eax
0x18000ae89  jz      short loc_18000AED7
0x18000ae8b  cmp     cs:byte_18004DF33, r15b
0x18000ae92  jge     short loc_18000AED7
0x18000ae94  mov     r8, [rdi+8]
0x18000ae98  lea     rdx, aErrorInserting; "Error inserting user attribute = %hs, %"...
0x18000ae9f  add     r8, 4FCh
0x18000aea6  mov     word ptr [rbp+810h+var_840], r15w
0x18000aeab  mov     r9d, eax
0x18000aeae  lea     rcx, [rbp+810h+var_840]
0x18000aeb2  call    FormatRRASErrorString
0x18000aeb7  cmp     cs:byte_18004DF33, r15b
0x18000aebe  jge     short loc_18000AED7
0x18000aec0  lea     r8, [rbp+810h+var_840]
0x18000aec4  lea     rdx, RasPppTraceError
0x18000aecb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aed2  call    McTemplateU0z_EventWriteTransfer
0x18000aed7  test    cs:byte_18004DF34, 1
0x18000aede  jz      loc_18000B06F
0x18000aee4  mov     word ptr [rbp+810h+var_840], r15w
0x18000aee9  lea     rax, [rsp+910h+pszDest]
0x18000aeee  inc     rbx
0x18000aef1  cmp     [rax+rbx], r15b
0x18000aef5  jnz     short loc_18000AEEE
0x18000aef7  mov     r8, [rdi+8]
0x18000aefb  movzx   eax, [rsp+910h+var_8A3]
0x18000af00  add     r8, 4FCh
0x18000af07  jmp     loc_18000B037
0x18000af0c  xor     r15d, r15d
0x18000af0f  cmp     [rsp+910h+var_8DC], r15d
0x18000af14  jz      loc_18000B077
0x18000af1a  mov     rax, [rdi+8]
0x18000af1e  lea     r11d, [r15+0Ch]
0x18000af22  mov     r9, [rsp+910h+cbToCopy]; cbToCopy
0x18000af27  xor     ecx, ecx
0x18000af29  mov     r8, [rsp+910h+pszSrc]; pszSrc
0x18000af2e  mov     edx, 515h
0x18000af33  mov     [rax+rdx], rcx
0x18000af37  mov     [rax+rdx+8], ecx
0x18000af3b  mov     rcx, [rdi+8]
0x18000af3f  add     rcx, rdx; pszDest
0x18000af42  mov     edx, r11d; cbDest
0x18000af45  call    StringCbCopyNA
0x18000af4a  mov     r8, [rdi+8]
0x18000af4e  lea     edx, [r15+18h]; cbDest
0x18000af52  sub     bl, 5
  ... truncated ...
```
