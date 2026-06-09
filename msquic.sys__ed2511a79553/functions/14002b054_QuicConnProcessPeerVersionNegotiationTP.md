# QuicConnProcessPeerVersionNegotiationTP

- ea: `0x14002b054`
- end: `0x14002b5bb`
- name: `QuicConnProcessPeerVersionNegotiationTP`
- size: `1383`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001cd20`

## callees

- `0x140005184`
- `0x14001c638`
- `0x14002a130`
- `0x14002a55c`
- `0x14002a694`
- `0x14002b054`
- `0x14002f204`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002b1d2`
- `ntoskrnl!_snprintf_s` at `0x14002b27f`
- `ntoskrnl!_snprintf_s` at `0x14002b2dd`
- `ntoskrnl!_snprintf_s` at `0x14002b320`
- `ntoskrnl!_snprintf_s` at `0x14002b43a`
- `ntoskrnl!_snprintf_s` at `0x14002b544`
- `ntoskrnl!_snprintf_s` at `0x14002b591`
- `ntoskrnl!_snprintf_s` at `0x14002b1d2`
- `ntoskrnl!_snprintf_s` at `0x14002b27f`
- `ntoskrnl!_snprintf_s` at `0x14002b2dd`
- `ntoskrnl!_snprintf_s` at `0x14002b320`
- `ntoskrnl!_snprintf_s` at `0x14002b43a`
- `ntoskrnl!_snprintf_s` at `0x14002b544`
- `ntoskrnl!_snprintf_s` at `0x14002b591`

## string_xrefs

- `0x14002b1b5`: `Compatible version upgrade! Old: 0x%x, New: 0x%x`
- `0x14002b528`: `Compatible version upgrade! Old: 0x%x, New: 0x%x`
- `0x14002b4c1`: `Compatible Version negotiation not compatible with client: original 0x%x, upgrade: 0x%x`

## pseudocode

```c
__int64 __fastcall QuicConnProcessPeerVersionNegotiationTP(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // ecx
  __int64 *v4; // r14
  unsigned __int16 v6; // r8
  int *v7; // rdx
  unsigned int v8; // r12d
  __int64 v9; // rcx
  unsigned int v10; // ecx
  __int64 v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // r10d
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  int *v17; // rdx
  unsigned int v18; // r10d
  __int64 v19; // r8
  unsigned int v20; // r15d
  __int64 v21; // rdi
  __int64 v22; // r12
  int v23; // r11d
  char v24; // r14
  __int64 v25; // rdx
  int v26; // ecx
  const char *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // edi
  int v31; // r10d
  char v32; // r11
  __int64 v33; // rcx
  __int64 v34; // [rsp+20h] [rbp-89h]
  __int128 v35; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v36; // [rsp+40h] [rbp-69h]
  char DstBuf[128]; // [rsp+50h] [rbp-59h] BYREF

  if ( *(_DWORD *)a1 != 4 )
  {
    v16 = *(_WORD *)(a1 + 1864);
    v17 = *(int **)(a1 + 1872);
    v35 = 0;
    if ( (int)QuicVersionNegotiationExtParseVersionInfo((_DWORD *)a1, v17, v16, (__int64)&v35) < 0 )
      goto LABEL_42;
    v18 = v35;
    if ( !(_DWORD)v35 )
      goto LABEL_36;
    if ( *(_DWORD *)(a1 + 3636) != (_DWORD)v35 )
    {
      if ( (byte_14005C48B & 0x20) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Server Chosen Version doesn't match long header. 0x%x != 0x%x",
          (_DWORD)v35,
          *(_DWORD *)(a1 + 3636));
        goto LABEL_41;
      }
      goto LABEL_42;
    }
    v20 = DWORD1(v35);
    v21 = 0;
    v22 = *((_QWORD *)&v35 + 1);
    v23 = 0;
    v24 = 0;
    if ( DWORD1(v35) )
    {
      while ( 1 )
      {
        v25 = *(unsigned int *)(v22 + 4 * v21);
        if ( !(_DWORD)v25 )
          break;
        if ( (*(_DWORD *)(a1 + 3632) & 1) != 0
          && !v23
          && (unsigned __int8)QuicVersionNegotiationExtIsVersionClientSupported(a1, v25) )
        {
          v23 = v25;
        }
        if ( *(_DWORD *)(a1 + 3884) == (_DWORD)v25 )
          v24 = 1;
        v21 = (unsigned int)(v21 + 1);
        if ( (unsigned int)v21 >= v20 )
        {
          if ( v23 )
            goto LABEL_56;
          goto LABEL_54;
        }
      }
      if ( (byte_14005C48B & 0x20) == 0 )
        goto LABEL_42;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Version Info Available Versions contains a zero version! Index = %u",
        v21);
      goto LABEL_41;
    }
LABEL_54:
    if ( !(unsigned __int8)QuicVersionNegotiationExtIsVersionClientSupported(a1, v18) )
      goto LABEL_81;
    v23 = v18;
LABEL_56:
    if ( v23 != *(_DWORD *)(a1 + 3884) && v23 != v18 )
    {
LABEL_81:
      if ( (byte_14005C48B & 0x20) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Client Chosen Version doesn't match Server Chosen Version: 0x%x vs. 0x%x",
          v23,
          v18);
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    v26 = *(_DWORD *)(a1 + 3880);
    if ( v26 )
    {
      if ( v26 == v18 )
      {
        if ( (byte_14005C48B & 0x20) != 0 )
        {
          v27 = "Previous Client Version is Server Chosen Version: 0x%x";
LABEL_62:
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v27, *(_DWORD *)(a1 + 3880));
LABEL_83:
          McTemplateU0ps_EtwWriteTransfer(v28, QuicConnLogError, a1, DstBuf);
        }
LABEL_84:
        v19 = 17;
        goto LABEL_43;
      }
      if ( (v26 & 0xF0F0F0F) != 0xA0A0A0A )
      {
        v29 = 0;
        if ( v20 )
        {
          while ( v26 != *(_DWORD *)(v22 + 4 * v29) )
          {
            v29 = (unsigned int)(v29 + 1);
            if ( (unsigned int)v29 >= v20 )
              goto LABEL_69;
          }
          if ( (byte_14005C48B & 0x20) == 0 )
            goto LABEL_84;
          v27 = "Previous Client Version in Server Available Versions list: 0x%x";
          goto LABEL_62;
        }
      }
    }
LABEL_69:
    if ( (*(_BYTE *)(a1 + 251) & 0x40) == 0 )
      return 0;
    v30 = *(_DWORD *)(a1 + 3884);
    if ( (unsigned __int8)QuicVersionNegotiationExtAreVersionsCompatible(v30, v18) )
    {
      if ( v24 )
      {
        *(_BYTE *)(a1 + 251) = v32 | 0x80;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Compatible version upgrade! Old: 0x%x, New: 0x%x",
            v30,
            *(_DWORD *)(a1 + 3636));
          McTemplateU0ps_EtwWriteTransfer(v33, QuicConnLogVerbose, a1, DstBuf);
        }
        return 0;
      }
      if ( (byte_14005C48B & 0x20) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "OriginalVersion not found in server's TP: original 0x%x, upgrade: 0x%x",
          v30,
          v31);
        goto LABEL_83;
      }
    }
    else if ( (byte_14005C48B & 0x20) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Compatible Version negotiation not compatible with client: original 0x%x, upgrade: 0x%x",
        v30,
        v31);
      goto LABEL_83;
    }
    goto LABEL_84;
  }
  v2 = 0;
  if ( (qword_14005C4B0 & 0x40000000) != 0 )
  {
    v3 = *(_DWORD *)(qword_14005C4B8 + 24);
    v4 = *(__int64 **)qword_14005C4B8;
    if ( !v3 )
      goto LABEL_8;
  }
  else
  {
    v3 = 4;
    v4 = DefaultSupportedVersionsList;
  }
  do
  {
    if ( *(_DWORD *)(a1 + 3636) == *((_DWORD *)v4 + v2) )
      break;
    v2 = (unsigned int)(v2 + 1);
  }
  while ( (unsigned int)v2 < v3 );
LABEL_8:
  if ( (_DWORD)v2 == v3 )
    return 3223584769LL;
  v6 = *(_WORD *)(a1 + 1864);
  v7 = *(int **)(a1 + 1872);
  v35 = 0;
  if ( (int)QuicVersionNegotiationExtParseVersionInfo((_DWORD *)a1, v7, v6, (__int64)&v35) < 0 )
    goto LABEL_42;
  v8 = v35;
  if ( !(_DWORD)v35 )
  {
LABEL_36:
    if ( (byte_14005C48B & 0x20) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Version Info Chosen Version is zero!");
      goto LABEL_41;
    }
LABEL_42:
    v19 = 8;
LABEL_43:
    QuicConnCloseLocally(a1, 2, v19);
    return 3223584772LL;
  }
  if ( *(_DWORD *)(a1 + 3636) != (_DWORD)v35 )
  {
    if ( (byte_14005C48B & 0x20) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Client Chosen Version doesn't match long header. 0x%x != 0x%x",
        (_DWORD)v35,
        *(_DWORD *)(a1 + 3636));
LABEL_41:
      McTemplateU0ps_EtwWriteTransfer(v9, QuicConnLogError, a1, DstBuf);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v10 = 0;
  v36 = 0;
  if ( (_DWORD)v2 )
  {
    while ( 1 )
    {
      if ( (*(_DWORD *)v4 & 0xF0F0F0F) != 0xA0A0A0A )
      {
        v11 = 0;
        if ( DWORD1(v35) )
          break;
      }
LABEL_29:
      ++v10;
      v4 = (__int64 *)((char *)v4 + 4);
      v36 = v10;
      if ( v10 >= (unsigned int)v2 )
        return 0;
    }
    v12 = *((_QWORD *)&v35 + 1);
    while ( 1 )
    {
      v13 = *(unsigned int *)(v12 + 4 * v11);
      if ( !(_DWORD)v13 )
        break;
      if ( (v13 & 0xF0F0F0F) != 0xA0A0A0A && (_DWORD)v13 == *(_DWORD *)v4 )
      {
        if ( (unsigned __int8)QuicVersionNegotiationExtAreVersionsCompatible(v8, v13) )
        {
          if ( (byte_14005C48C & 1) != 0 )
          {
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "Compatible version upgrade! Old: 0x%x, New: 0x%x",
              *(_DWORD *)(a1 + 3636),
              v14);
            McTemplateU0ps_EtwWriteTransfer(v15, QuicConnLogVerbose, a1, DstBuf);
          }
          *(_DWORD *)(a1 + 3636) = *(_DWORD *)v4;
          QuicConnOnQuicVersionSet(a1);
          if ( (int)QuicCryptoOnVersionChange(a1 + 2784) < 0 )
          {
            QuicConnCloseLocally(a1, 2, 17);
            return 3223584771LL;
          }
        }
        v12 = *((_QWORD *)&v35 + 1);
      }
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= DWORD1(v35) )
      {
        v10 = v36;
        goto LABEL_29;
      }
    }
    if ( (byte_14005C48B & 0x20) == 0 )
      goto LABEL_42;
    LODWORD(v34) = v11;
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Version Info.AvailableVersions contains a zero version! Index = %u",
      v34);
    goto LABEL_41;
  }
  return 0;
}

```

## disassembly

```asm
0x14002b054  mov     [rsp-8+arg_8], rbx
0x14002b059  mov     [rsp-8+arg_10], rsi
0x14002b05e  push    rbp
0x14002b05f  push    rdi
0x14002b060  push    r12
0x14002b062  push    r14
0x14002b064  push    r15
0x14002b066  lea     rbp, [rsp-37h]
0x14002b06b  sub     rsp, 0E0h
0x14002b072  mov     rax, cs:__security_cookie
0x14002b079  xor     rax, rsp
0x14002b07c  mov     [rbp+57h+var_30], rax
0x14002b080  cmp     dword ptr [rcx], 4
0x14002b083  mov     rbx, rcx
0x14002b086  jnz     loc_14002B290
0x14002b08c  xor     edi, edi
0x14002b08e  mov     esi, 1
0x14002b093  test    cs:qword_14005C4B0, 40000000h
0x14002b09e  jz      short loc_14002B0B3
0x14002b0a0  mov     rax, cs:qword_14005C4B8
0x14002b0a7  mov     ecx, [rax+18h]
0x14002b0aa  mov     r14, [rax]
0x14002b0ad  test    ecx, ecx
0x14002b0af  jz      short loc_14002B0D1
0x14002b0b1  jmp     short loc_14002B0BF
0x14002b0b3  mov     ecx, 4
0x14002b0b8  lea     r14, DefaultSupportedVersionsList
0x14002b0bf  mov     edx, [rbx+0E34h]
0x14002b0c5  cmp     edx, [r14+rdi*4]
0x14002b0c9  jz      short loc_14002B0D1
0x14002b0cb  add     edi, esi
0x14002b0cd  cmp     edi, ecx
0x14002b0cf  jb      short loc_14002B0C5
0x14002b0d1  cmp     edi, ecx
0x14002b0d3  jnz     short loc_14002B0DF
0x14002b0d5  mov     eax, 0C0240001h
0x14002b0da  jmp     loc_14002B359
0x14002b0df  movzx   r8d, word ptr [rbx+748h]
0x14002b0e7  lea     r9, [rbp+57h+var_D0]
0x14002b0eb  mov     rdx, [rbx+750h]
0x14002b0f2  xorps   xmm0, xmm0
0x14002b0f5  mov     rcx, rbx
0x14002b0f8  movups  [rbp+57h+var_D0], xmm0
0x14002b0fc  call    QuicVersionNegotiationExtParseVersionInfo
0x14002b101  test    eax, eax
0x14002b103  js      loc_14002B33F
0x14002b109  mov     r12d, dword ptr [rbp+57h+var_D0]
0x14002b10d  test    r12d, r12d
0x14002b110  jz      loc_14002B2C0
0x14002b116  mov     ecx, [rbx+0E34h]
0x14002b11c  cmp     ecx, r12d
0x14002b11f  jz      short loc_14002B143
0x14002b121  test    cs:byte_14005C48B, 20h
0x14002b128  jz      loc_14002B33F
0x14002b12e  mov     [rsp+100h+var_D8], ecx
0x14002b132  lea     r9, aClientChosenVe_0; "Client Chosen Version doesn't match lon"...
0x14002b139  mov     dword ptr [rsp+100h+var_E0], r12d
0x14002b13e  jmp     loc_14002B313
0x14002b143  xor     ecx, ecx
0x14002b145  mov     [rbp+57h+var_C0], ecx
0x14002b148  test    edi, edi
0x14002b14a  jz      loc_14002B563
0x14002b150  mov     eax, [r14]
0x14002b153  and     eax, 0F0F0F0Fh
0x14002b158  cmp     eax, 0A0A0A0Ah
0x14002b15d  jz      loc_14002B226
0x14002b163  xor     r15d, r15d
0x14002b166  cmp     dword ptr [rbp+57h+var_D0+4], r15d
0x14002b16a  jbe     loc_14002B226
0x14002b170  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x14002b174  mov     edx, [rcx+r15*4]
0x14002b178  test    edx, edx
0x14002b17a  jz      loc_14002B259
0x14002b180  mov     eax, edx
0x14002b182  and     eax, 0F0F0F0Fh
0x14002b187  cmp     eax, 0A0A0A0Ah
0x14002b18c  jz      loc_14002B216
0x14002b192  mov     r10d, [r14]
0x14002b195  cmp     edx, r10d
0x14002b198  jnz     short loc_14002B216
0x14002b19a  mov     ecx, r12d
0x14002b19d  call    QuicVersionNegotiationExtAreVersionsCompatible
0x14002b1a2  test    al, al
0x14002b1a4  jz      short loc_14002B212
0x14002b1a6  test    cs:byte_14005C48C, sil
0x14002b1ad  jz      short loc_14002B1F1
0x14002b1af  mov     eax, [rbx+0E34h]
0x14002b1b5  lea     r9, aCompatibleVers; "Compatible version upgrade! Old: 0x%x, "...
0x14002b1bc  mov     [rsp+100h+var_D8], r10d
0x14002b1c1  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b1c5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b1c9  mov     dword ptr [rsp+100h+var_E0], eax
0x14002b1cd  mov     edx, 80h; SizeInBytes
0x14002b1d2  call    cs:__imp__snprintf_s
0x14002b1d9  nop     dword ptr [rax+rax+00h]
0x14002b1de  lea     r9, [rbp+57h+DstBuf]
0x14002b1e2  mov     r8, rbx
0x14002b1e5  lea     rdx, QuicConnLogVerbose
0x14002b1ec  call    McTemplateU0ps_EtwWriteTransfer
0x14002b1f1  mov     eax, [r14]
0x14002b1f4  mov     rcx, rbx
0x14002b1f7  mov     [rbx+0E34h], eax
0x14002b1fd  call    QuicConnOnQuicVersionSet
0x14002b202  lea     rcx, [rbx+0AE0h]
0x14002b209  call    QuicCryptoOnVersionChange
0x14002b20e  test    eax, eax
0x14002b210  js      short loc_14002B23C
0x14002b212  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x14002b216  add     r15d, esi
0x14002b219  cmp     r15d, dword ptr [rbp+57h+var_D0+4]
0x14002b21d  jb      loc_14002B174
0x14002b223  mov     ecx, [rbp+57h+var_C0]
0x14002b226  add     ecx, esi
0x14002b228  add     r14, 4
0x14002b22c  mov     [rbp+57h+var_C0], ecx
0x14002b22f  cmp     ecx, edi
0x14002b231  jb      loc_14002B150
0x14002b237  jmp     loc_14002B563
0x14002b23c  xor     r9d, r9d
0x14002b23f  mov     rcx, rbx
0x14002b242  lea     edx, [r9+2]
0x14002b246  lea     r8d, [r9+11h]
0x14002b24a  call    QuicConnCloseLocally
0x14002b24f  mov     eax, 0C0240003h
0x14002b254  jmp     loc_14002B359
0x14002b259  test    cs:byte_14005C48B, 20h
0x14002b260  jz      loc_14002B33F
0x14002b266  mov     dword ptr [rsp+100h+var_E0], r15d
0x14002b26b  lea     r9, aVersionInfoAva_0; "Version Info.AvailableVersions contains"...
0x14002b272  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b276  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b27a  mov     edx, 80h; SizeInBytes
0x14002b27f  call    cs:__imp__snprintf_s
0x14002b286  nop     dword ptr [rax+rax+00h]
0x14002b28b  jmp     loc_14002B32C
0x14002b290  movzx   r8d, word ptr [rcx+748h]
0x14002b298  lea     r9, [rbp+57h+var_D0]
0x14002b29c  mov     rdx, [rcx+750h]
0x14002b2a3  xorps   xmm0, xmm0
0x14002b2a6  movups  [rbp+57h+var_D0], xmm0
0x14002b2aa  call    QuicVersionNegotiationExtParseVersionInfo
0x14002b2af  test    eax, eax
0x14002b2b1  js      loc_14002B33F
0x14002b2b7  mov     r10d, dword ptr [rbp+57h+var_D0]
0x14002b2bb  test    r10d, r10d
0x14002b2be  jnz     short loc_14002B2EB
0x14002b2c0  test    cs:byte_14005C48B, 20h
0x14002b2c7  jz      short loc_14002B33F
0x14002b2c9  lea     r9, aVersionInfoCho; "Version Info Chosen Version is zero!"
0x14002b2d0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b2d4  mov     edx, 80h; SizeInBytes
0x14002b2d9  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b2dd  call    cs:__imp__snprintf_s
0x14002b2e4  nop     dword ptr [rax+rax+00h]
0x14002b2e9  jmp     short loc_14002B32C
0x14002b2eb  mov     ecx, [rbx+0E34h]
0x14002b2f1  cmp     ecx, r10d
0x14002b2f4  jz      loc_14002B382
0x14002b2fa  test    cs:byte_14005C48B, 20h
0x14002b301  jz      short loc_14002B33F
0x14002b303  mov     [rsp+100h+var_D8], ecx
0x14002b307  lea     r9, aServerChosenVe; "Server Chosen Version doesn't match lon"...
0x14002b30e  mov     dword ptr [rsp+100h+var_E0], r10d
0x14002b313  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b317  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b31b  mov     edx, 80h; SizeInBytes
0x14002b320  call    cs:__imp__snprintf_s
0x14002b327  nop     dword ptr [rax+rax+00h]
0x14002b32c  lea     r9, [rbp+57h+DstBuf]
0x14002b330  mov     r8, rbx
0x14002b333  lea     rdx, QuicConnLogError
0x14002b33a  call    McTemplateU0ps_EtwWriteTransfer
0x14002b33f  mov     r8d, 8
0x14002b345  xor     r9d, r9d
0x14002b348  mov     rcx, rbx
0x14002b34b  lea     edx, [r9+2]
0x14002b34f  call    QuicConnCloseLocally
0x14002b354  mov     eax, 0C0240004h
0x14002b359  mov     rcx, [rbp+57h+var_30]
0x14002b35d  xor     rcx, rsp; StackCookie
0x14002b360  call    __security_check_cookie
0x14002b365  lea     r11, [rsp+100h+var_20]
0x14002b36d  mov     rbx, [r11+38h]
0x14002b371  mov     rsi, [r11+40h]
0x14002b375  mov     rsp, r11
0x14002b378  pop     r15
0x14002b37a  pop     r14
0x14002b37c  pop     r12
0x14002b37e  pop     rdi
0x14002b37f  pop     rbp
0x14002b380  retn
0x14002b382  mov     r15d, dword ptr [rbp+57h+var_D0+4]
0x14002b386  xor     edi, edi
0x14002b388  mov     r12, qword ptr [rbp+57h+var_D0+8]
0x14002b38c  xor     r11d, r11d
0x14002b38f  xor     r14b, r14b
0x14002b392  lea     esi, [rdi+1]
0x14002b395  test    r15d, r15d
0x14002b398  jz      short loc_14002B3DE
0x14002b39a  mov     edx, [r12+rdi*4]
0x14002b39e  test    edx, edx
0x14002b3a0  jz      loc_14002B44B
0x14002b3a6  mov     eax, [rbx+0E30h]
0x14002b3ac  test    sil, al
0x14002b3af  jz      short loc_14002B3C4
0x14002b3b1  test    r11d, r11d
0x14002b3b4  jnz     short loc_14002B3C4
0x14002b3b6  mov     rcx, rbx
0x14002b3b9  call    QuicVersionNegotiationExtIsVersionClientSupported
0x14002b3be  test    al, al
0x14002b3c0  cmovnz  r11d, edx
0x14002b3c4  cmp     [rbx+0F2Ch], edx
0x14002b3ca  movzx   r14d, r14b
0x14002b3ce  cmovz   r14d, esi
0x14002b3d2  add     edi, esi
0x14002b3d4  cmp     edi, r15d
0x14002b3d7  jb      short loc_14002B39A
0x14002b3d9  test    r11d, r11d
0x14002b3dc  jnz     short loc_14002B3F4
0x14002b3de  mov     edx, r10d
0x14002b3e1  mov     rcx, rbx
0x14002b3e4  call    QuicVersionNegotiationExtIsVersionClientSupported
0x14002b3e9  test    al, al
0x14002b3eb  jz      loc_14002B56A
0x14002b3f1  mov     r11d, r10d
0x14002b3f4  cmp     r11d, [rbx+0F2Ch]
0x14002b3fb  jz      short loc_14002B406
0x14002b3fd  cmp     r11d, r10d
0x14002b400  jnz     loc_14002B56A
0x14002b406  mov     ecx, [rbx+0F28h]
0x14002b40c  test    ecx, ecx
0x14002b40e  jz      short loc_14002B48A
0x14002b410  cmp     ecx, r10d
0x14002b413  jnz     short loc_14002B468
0x14002b415  test    cs:byte_14005C48B, 20h
0x14002b41c  jz      loc_14002B5B0
0x14002b422  lea     r9, aPreviousClient; "Previous Client Version is Server Chose"...
0x14002b429  mov     dword ptr [rsp+100h+var_E0], ecx
0x14002b42d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b431  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b435  mov     edx, 80h; SizeInBytes
0x14002b43a  call    cs:__imp__snprintf_s
0x14002b441  nop     dword ptr [rax+rax+00h]
0x14002b446  jmp     loc_14002B59D
0x14002b44b  test    cs:byte_14005C48B, 20h
0x14002b452  jz      loc_14002B33F
0x14002b458  mov     dword ptr [rsp+100h+var_E0], edi
0x14002b45c  lea     r9, aVersionInfoAva; "Version Info Available Versions contain"...
0x14002b463  jmp     loc_14002B272
0x14002b468  mov     eax, ecx
0x14002b46a  and     eax, 0F0F0F0Fh
0x14002b46f  cmp     eax, 0A0A0A0Ah
0x14002b474  jz      short loc_14002B48A
0x14002b476  xor     edx, edx
0x14002b478  test    r15d, r15d
0x14002b47b  jz      short loc_14002B48A
0x14002b47d  cmp     ecx, [r12+rdx*4]
0x14002b481  jz      short loc_14002B4D1
0x14002b483  add     edx, esi
0x14002b485  cmp     edx, r15d
0x14002b488  jb      short loc_14002B47D
0x14002b48a  mov     r11b, [rbx+0FBh]
0x14002b491  test    r11b, 40h
0x14002b495  jz      loc_14002B563
0x14002b49b  mov     edi, [rbx+0F2Ch]
0x14002b4a1  mov     edx, r10d
0x14002b4a4  mov     ecx, edi
0x14002b4a6  call    QuicVersionNegotiationExtAreVersionsCompatible
0x14002b4ab  test    al, al
0x14002b4ad  jnz     short loc_14002B4EA
0x14002b4af  test    cs:byte_14005C48B, 20h
0x14002b4b6  jz      loc_14002B5B0
0x14002b4bc  mov     [rsp+100h+var_D8], r10d
0x14002b4c1  lea     r9, aCompatibleVers_0; "Compatible Version negotiation not comp"...
0x14002b4c8  mov     dword ptr [rsp+100h+var_E0], edi
0x14002b4cc  jmp     loc_14002B584
0x14002b4d1  test    cs:byte_14005C48B, 20h
0x14002b4d8  jz      loc_14002B5B0
0x14002b4de  lea     r9, aPreviousClient_0; "Previous Client Version in Server Avail"...
0x14002b4e5  jmp     loc_14002B429
0x14002b4ea  test    r14b, r14b
0x14002b4ed  jnz     short loc_14002B50E
0x14002b4ef  test    cs:byte_14005C48B, 20h
0x14002b4f6  jz      loc_14002B5B0
0x14002b4fc  mov     [rsp+100h+var_D8], r10d
0x14002b501  lea     r9, aOriginalversio; "OriginalVersion not found in server's T"...
0x14002b508  mov     dword ptr [rsp+100h+var_E0], edi
0x14002b50c  jmp     short loc_14002B584
0x14002b50e  or      r11b, 80h
0x14002b512  mov     [rbx+0FBh], r11b
0x14002b519  test    cs:byte_14005C48C, sil
0x14002b520  jz      short loc_14002B563
0x14002b522  mov     eax, [rbx+0E34h]
0x14002b528  lea     r9, aCompatibleVers; "Compatible version upgrade! Old: 0x%x, "...
0x14002b52f  mov     [rsp+100h+var_D8], eax
0x14002b533  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14002b537  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002b53b  mov     dword ptr [rsp+100h+var_E0], edi
0x14002b53f  mov     edx, 80h; SizeInBytes
0x14002b544  call    cs:__imp__snprintf_s
  ... truncated ...
```
