# ProcessPacketFromWanArp

- ea: `0x180011b38`
- end: `0x180012180`
- name: `ProcessPacketFromWanArp`
- size: `1608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe0c`

## callees

- `0x180011790`
- `0x180011b38`
- `0x180012480`
- `0x18001255c`
- `0x180054df8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringA` at `0x180011fc1`
- `ntdll!RtlIpv6AddressToStringA` at `0x180011fd3`
- `ntdll!RtlIpv6AddressToStringA` at `0x180011fc1`
- `ntdll!RtlIpv6AddressToStringA` at `0x180011fd3`
- `KERNEL32!WideCharToMultiByte` at `0x180012032`
- `KERNEL32!WideCharToMultiByte` at `0x180012032`
- `rtutils!RouterLogEventDataA` at `0x1800120f4`
- `rtutils!RouterLogEventDataA` at `0x1800120f4`
- `WS2_32!__imp_inet_ntoa` at `0x180011f7f`
- `WS2_32!__imp_inet_ntoa` at `0x180011f9f`
- `WS2_32!__imp_inet_ntoa` at `0x180011f7f`
- `WS2_32!__imp_inet_ntoa` at `0x180011f9f`

## string_xrefs

- `0x180011cf2`: `ProcPktFromWanarp: Packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x had 0 size!!`
- `0x180011dbd`: `ProcPktFromWanarp: Result %d action %ws for packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x`
- `0x180011f08`: `ProcPktFromWanarp: Result %d for packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x`

## pseudocode

```c
__int64 __fastcall ProcessPacketFromWanArp(__int64 a1, __int64 a2)
{
  int v2; // r12d
  unsigned int v5; // ebx
  char v6; // al
  unsigned __int64 v7; // rdx
  __int128 *v8; // r9
  void *v9; // rcx
  unsigned int v10; // r15d
  int v11; // ecx
  int v12; // edx
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  const wchar_t *v16; // r8
  bool v17; // zf
  unsigned int v18; // r13d
  int v19; // ecx
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  __int128 *v24; // r9
  __int128 *v25; // r9
  int v27; // ecx
  int v28; // edx
  int v29; // r8d
  int v30; // eax
  __int64 v31; // r9
  __int128 *v32; // r9
  const struct in6_addr *v33; // rcx
  char *v34; // rax
  char *v35; // rax
  __int128 *v36; // r9
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-AD8h]
  LPSTR lpMultiByteStra; // [rsp+20h] [rbp-AD8h]
  int cbMultiByte[2]; // [rsp+28h] [rbp-AD0h]
  int v40; // [rsp+40h] [rbp-AB8h]
  int v41; // [rsp+48h] [rbp-AB0h]
  int v42; // [rsp+48h] [rbp-AB0h]
  int v43; // [rsp+50h] [rbp-AA8h]
  int v44; // [rsp+50h] [rbp-AA8h]
  int v45; // [rsp+50h] [rbp-AA8h]
  int v46; // [rsp+58h] [rbp-AA0h]
  int v47; // [rsp+58h] [rbp-AA0h]
  int v48; // [rsp+60h] [rbp-A98h]
  _PfForwardAction v49; // [rsp+74h] [rbp-A84h] BYREF
  unsigned int v50; // [rsp+78h] [rbp-A80h]
  unsigned __int64 v51; // [rsp+80h] [rbp-A78h]
  __int128 v52; // [rsp+88h] [rbp-A70h] BYREF
  LPSTR plpszSubStringArray[5]; // [rsp+98h] [rbp-A60h] BYREF
  int v54; // [rsp+C0h] [rbp-A38h] BYREF
  __int128 v55; // [rsp+C4h] [rbp-A34h]
  __int128 v56; // [rsp+D4h] [rbp-A24h]
  int v57; // [rsp+E4h] [rbp-A14h]
  char v58[8]; // [rsp+E8h] [rbp-A10h] BYREF
  char v59[32]; // [rsp+F0h] [rbp-A08h] BYREF
  char pszDest[80]; // [rsp+110h] [rbp-9E8h] BYREF
  CHAR S[80]; // [rsp+160h] [rbp-998h] BYREF
  CHAR MultiByteStr[272]; // [rsp+1B0h] [rbp-948h] BYREF
  int v63; // [rsp+2C0h] [rbp-838h] BYREF
  _BYTE v64[2044]; // [rsp+2C4h] [rbp-834h] BYREF

  v2 = *(_DWORD *)(a1 + 516);
  v49 = PF_ACTION_FORWARD;
  v50 = v2 != 0 ? 20 : 40;
  v5 = *(_DWORD *)((-(__int64)(v2 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + a2 + 48);
  v63 = 0;
  memset_0(v64, 0, sizeof(v64));
  v54 = 0;
  v57 = 0;
  v6 = Microsoft_Windows_RRASEnableBits;
  v7 = (-(__int64)(v2 != 0) & 0xFFFFFFFFFFFFFFE7uLL) + 54;
  v51 = v7;
  v55 = 0;
  v56 = 0;
  v52 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v54) = 0;
    v8 = &v52;
    if ( a1 != -688 )
      LODWORD(v8) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: ProcessPacketFromWanArp",
      (_DWORD)v8,
      *(_QWORD *)(a1 + 72),
      (__int64)&v54);
    v6 = Microsoft_Windows_RRASEnableBits;
    v7 = v51;
  }
  v9 = *(void **)(a1 + 104);
  v10 = 1514;
  if ( v5 < 0x5EA )
    v10 = v5;
  if ( v9 != (void *)-1LL )
  {
    if ( !v10 )
    {
      if ( v2 )
      {
        if ( v6 < 0 )
        {
          v11 = *(unsigned __int8 *)(a2 + 19);
          v12 = *(unsigned __int8 *)(a2 + 18);
          v13 = *(unsigned __int8 *)(a2 + 20);
          v14 = *(unsigned __int8 *)(a2 + 17);
          v15 = *(unsigned __int8 *)(a2 + 16);
          v43 = *(unsigned __int8 *)(a2 + 28);
          v41 = *(unsigned __int8 *)(a2 + 23);
          v40 = *(unsigned __int8 *)(a2 + 22);
          LOWORD(v63) = 0;
          LOWORD(v54) = 0;
          cbMultiByte[0] = v11;
          LODWORD(lpMultiByteStr) = v12;
          FormatRRASErrorString(
            &v63,
            L"ProcPktFromWanarp: Packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x had 0 size!!",
            v15,
            v14,
            lpMultiByteStr,
            *(_QWORD *)cbMultiByte,
            v13,
            *(unsigned __int8 *)(a2 + 21),
            v40,
            v41,
            v43);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v16 = (const wchar_t *)&v63;
LABEL_25:
            v25 = &v52;
            if ( a1 != -688 )
              LODWORD(v25) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (_DWORD)v16,
              (_DWORD)v25,
              *(_QWORD *)(a1 + 72),
              (__int64)&v54);
            return 13;
          }
        }
        return 13;
      }
      v17 = v6 >= 0;
LABEL_23:
      if ( !v17 )
      {
        v16 = L"Leaving: ProcessPacketFromWanArp";
        LOWORD(v54) = 0;
        goto LABEL_25;
      }
      return 13;
    }
    v18 = PfInternTestPacket(v9, 0, v10, (unsigned __int8 *)(v7 + a2), &v49);
    if ( v18 )
    {
      if ( v2 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v27 = *(unsigned __int8 *)(a2 + 19);
          v28 = *(unsigned __int8 *)(a2 + 18);
          v29 = *(unsigned __int8 *)(a2 + 17);
          v30 = *(unsigned __int8 *)(a2 + 20);
          v31 = *(unsigned __int8 *)(a2 + 16);
          v47 = *(unsigned __int8 *)(a2 + 28);
          v45 = *(unsigned __int8 *)(a2 + 23);
          v42 = *(unsigned __int8 *)(a2 + 22);
          LOWORD(v63) = 0;
          LOWORD(v54) = 0;
          cbMultiByte[0] = v28;
          LODWORD(lpMultiByteStra) = v29;
          FormatRRASErrorString(
            &v63,
            L"ProcPktFromWanarp: Result %d for packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x",
            v18,
            v31,
            lpMultiByteStra,
            *(_QWORD *)cbMultiByte,
            v27,
            v30,
            *(unsigned __int8 *)(a2 + 21),
            v42,
            v45,
            v47);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v32 = &v52;
            if ( a1 != -688 )
              LODWORD(v32) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v63,
              (_DWORD)v32,
              *(_QWORD *)(a1 + 72),
              (__int64)&v54);
            v33 = (const struct in6_addr *)(a2 + 16);
            goto LABEL_36;
          }
        }
      }
    }
    else if ( v49 == PF_ACTION_DROP )
    {
      if ( v2 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v19 = *(unsigned __int8 *)(a2 + 20);
          v20 = *(unsigned __int8 *)(a2 + 19);
          v21 = *(unsigned __int8 *)(a2 + 18);
          v22 = *(unsigned __int8 *)(a2 + 17);
          v23 = *(unsigned __int8 *)(a2 + 16);
          v48 = *(unsigned __int8 *)(a2 + 28);
          v46 = *(unsigned __int8 *)(a2 + 23);
          v44 = *(unsigned __int8 *)(a2 + 22);
          LOWORD(v63) = 0;
          LOWORD(v54) = 0;
          cbMultiByte[0] = v22;
          LODWORD(lpMultiByteStra) = v23;
          FormatRRASErrorString(
            &v63,
            L"ProcPktFromWanarp: Result %d action %ws for packet from %d.%d.%d.%d to %d.%d.%d.%d protocol 0x%02x",
            0,
            L"Drop",
            lpMultiByteStra,
            *(_QWORD *)cbMultiByte,
            v21,
            v20,
            v19,
            *(unsigned __int8 *)(a2 + 21),
            v44,
            v46,
            v48);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v24 = &v52;
            if ( a1 != -688 )
              LODWORD(v24) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v63,
              (_DWORD)v24,
              *(_QWORD *)(a1 + 72),
              (__int64)&v54);
          }
        }
      }
      v17 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
      goto LABEL_23;
    }
  }
  v33 = (const struct in6_addr *)(a2 + 16);
  if ( !v2 )
  {
    RtlIpv6AddressToStringA(v33, pszDest);
    RtlIpv6AddressToStringA((const struct in6_addr *)(a2 + 32), S);
    goto LABEL_38;
  }
LABEL_36:
  v34 = inet_ntoa(*(struct in_addr *)v33->u.Byte);
  StringCbCopyA(pszDest, 0x41u, v34);
  v35 = inet_ntoa(*(struct in_addr *)(a2 + 20));
  StringCbCopyA(S, 0x41u, v35);
LABEL_38:
  StringCbPrintfA(v58, 5u, "%02x", *(unsigned __int8 *)((-(__int64)(v2 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + a2 + 52));
  WideCharToMultiByte(0, 0x400u, *(LPCWCH *)(a1 + 72), -1, MultiByteStr, 256, 0, 0);
  MultiByteStr[256] = 0;
  StringCbPrintfA(v59, 0x20u, "%d", v10);
  if ( (unsigned int)g_dwLoggingLevel >= 2 )
  {
    plpszSubStringArray[0] = pszDest;
    plpszSubStringArray[1] = S;
    plpszSubStringArray[2] = v58;
    plpszSubStringArray[3] = MultiByteStr;
    plpszSubStringArray[4] = v59;
    RouterLogEventDataA(g_hLogHandle, 2u, 0x4E9Eu, 5u, plpszSubStringArray, v10 - v50, (LPBYTE)(a2 + v51 + v50));
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v54) = 0;
    v36 = &v52;
    if ( a1 != -688 )
      LODWORD(v36) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: ProcessPacketFromWanArp",
      (_DWORD)v36,
      *(_QWORD *)(a1 + 72),
      (__int64)&v54);
  }
  return 0;
}

```

## disassembly

```asm
0x180011b38  mov     [rsp+arg_10], rbx
0x180011b3d  mov     [rsp+arg_18], rsi
0x180011b42  push    rdi
0x180011b43  push    r12
0x180011b45  push    r13
0x180011b47  push    r14
0x180011b49  push    r15
0x180011b4b  sub     rsp, 0AD0h
0x180011b52  mov     rax, cs:__security_cookie
0x180011b59  xor     rax, rsp
0x180011b5c  mov     [rsp+0AF8h+var_38], rax
0x180011b64  mov     r12d, [rcx+204h]
0x180011b6b  mov     r14, rcx
0x180011b6e  mov     eax, r12d
0x180011b71  mov     rsi, rdx
0x180011b74  neg     eax
0x180011b76  mov     r8d, 7FCh; Size
0x180011b7c  sbb     eax, eax
0x180011b7e  xor     edi, edi
0x180011b80  and     eax, 0FFFFFFECh
0x180011b83  mov     [rsp+0AF8h+var_A84], edi
0x180011b87  add     eax, 28h ; '('
0x180011b8a  mov     [rsp+0AF8h+var_A80], eax
0x180011b8e  mov     eax, r12d
0x180011b91  neg     eax
0x180011b93  sbb     rcx, rcx
0x180011b96  and     rcx, 0FFFFFFFFFFFFFFE8h
0x180011b9a  mov     ebx, [rcx+rdx+30h]
0x180011b9e  xor     edx, edx; Val
0x180011ba0  lea     rcx, [rsp+0AF8h+var_834]; void *
0x180011ba8  mov     [rsp+0AF8h+var_838], edi
0x180011baf  call    memset_0
0x180011bb4  xor     eax, eax
0x180011bb6  mov     [rsp+0AF8h+var_A38], edi
0x180011bbd  mov     [rsp+0AF8h+var_A14], eax
0x180011bc4  xorps   xmm0, xmm0
0x180011bc7  mov     eax, r12d
0x180011bca  neg     eax
0x180011bcc  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180011bd3  sbb     rdx, rdx
0x180011bd6  and     rdx, 0FFFFFFFFFFFFFFE7h
0x180011bda  add     rdx, 36h ; '6'
0x180011bde  mov     [rsp+0AF8h+var_A78], rdx
0x180011be6  movups  [rsp+0AF8h+var_A34], xmm0
0x180011bee  movups  [rsp+0AF8h+var_A24], xmm0
0x180011bf6  movups  [rsp+0AF8h+var_A70], xmm0
0x180011bfe  test    al, 80h
0x180011c00  jz      short loc_180011C5F
0x180011c02  lea     rax, [r14+2B0h]
0x180011c09  mov     word ptr [rsp+0AF8h+var_A38], di
0x180011c11  test    rax, rax
0x180011c14  lea     r9, [rsp+0AF8h+var_A70]
0x180011c1c  lea     r8, aEnteredProcess; "Entered: ProcessPacketFromWanArp"
0x180011c23  cmovnz  r9, rax
0x180011c27  lea     rdx, RasRtrmgrParamTraceInfo
0x180011c2e  lea     rax, [rsp+0AF8h+var_A38]
0x180011c36  mov     qword ptr [rsp+0AF8h+cbMultiByte], rax
0x180011c3b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011c42  mov     rax, [r14+48h]
0x180011c46  mov     [rsp+0AF8h+lpMultiByteStr], rax
0x180011c4b  call    McTemplateU0zjzz_EventWriteTransfer
0x180011c50  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180011c57  mov     rdx, [rsp+0AF8h+var_A78]
0x180011c5f  mov     rcx, [r14+68h]; void *
0x180011c63  mov     r15d, 5EAh
0x180011c69  cmp     ebx, r15d
0x180011c6c  cmovb   r15d, ebx
0x180011c70  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011c74  jz      loc_180011F74
0x180011c7a  test    r15d, r15d
0x180011c7d  jnz     loc_180011D1F
0x180011c83  test    r12d, r12d
0x180011c86  jz      loc_180011D18
0x180011c8c  test    al, al
0x180011c8e  jns     loc_180011E8A
0x180011c94  movzx   ecx, byte ptr [rsi+13h]
0x180011c98  movzx   edx, byte ptr [rsi+12h]
0x180011c9c  movzx   r10d, byte ptr [rsi+1Ch]
0x180011ca1  movzx   r11d, byte ptr [rsi+17h]
0x180011ca6  movzx   ebx, byte ptr [rsi+16h]
0x180011caa  movzx   eax, byte ptr [rsi+14h]
0x180011cae  movzx   r9d, byte ptr [rsi+11h]
0x180011cb3  movzx   r8d, byte ptr [rsi+10h]
0x180011cb8  mov     [rsp+0AF8h+var_AA8], r10d
0x180011cbd  mov     [rsp+0AF8h+var_AB0], r11d
0x180011cc2  mov     [rsp+0AF8h+var_AB8], ebx
0x180011cc6  mov     word ptr [rsp+0AF8h+var_838], di
0x180011cce  mov     word ptr [rsp+0AF8h+var_A38], di
0x180011cd6  movzx   edi, byte ptr [rsi+15h]
0x180011cda  mov     dword ptr [rsp+0AF8h+lpUsedDefaultChar], edi
0x180011cde  mov     dword ptr [rsp+0AF8h+lpDefaultChar], eax
0x180011ce2  mov     [rsp+0AF8h+cbMultiByte], ecx
0x180011ce6  lea     rcx, [rsp+0AF8h+var_838]
0x180011cee  mov     dword ptr [rsp+0AF8h+lpMultiByteStr], edx
0x180011cf2  lea     rdx, aProcpktfromwan; "ProcPktFromWanarp: Packet from %d.%d.%d"...
0x180011cf9  call    FormatRRASErrorString
0x180011cfe  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180011d05  jge     loc_180011E8A
0x180011d0b  lea     r8, [rsp+0AF8h+var_838]
0x180011d13  jmp     loc_180011E4B
0x180011d18  test    al, 80h
0x180011d1a  jmp     loc_180011E3A
0x180011d1f  lea     r9, [rdx+rsi]; unsigned __int8 *
0x180011d23  mov     r8d, r15d; unsigned int
0x180011d26  lea     rax, [rsp+0AF8h+var_A84]
0x180011d2b  xor     edx, edx; void *
0x180011d2d  mov     [rsp+0AF8h+lpMultiByteStr], rax; enum _PfForwardAction *
0x180011d32  call    PfInternTestPacket
0x180011d37  mov     r13d, eax
0x180011d3a  test    eax, eax
0x180011d3c  jnz     loc_180011E94
0x180011d42  cmp     [rsp+0AF8h+var_A84], 1
0x180011d47  jnz     loc_180011F74
0x180011d4d  test    r12d, r12d
0x180011d50  jz      loc_180011E33
0x180011d56  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180011d5d  jge     loc_180011E33
0x180011d63  movzx   ecx, byte ptr [rsi+14h]
0x180011d67  movzx   edx, byte ptr [rsi+13h]
0x180011d6b  movzx   r8d, byte ptr [rsi+12h]
0x180011d70  movzx   r9d, byte ptr [rsi+11h]
0x180011d75  movzx   r10d, byte ptr [rsi+1Ch]
0x180011d7a  movzx   r11d, byte ptr [rsi+17h]
0x180011d7f  movzx   ebx, byte ptr [rsi+16h]
0x180011d83  movzx   eax, byte ptr [rsi+10h]
0x180011d87  mov     [rsp+0AF8h+var_A98], r10d
0x180011d8c  mov     [rsp+0AF8h+var_AA0], r11d
0x180011d91  mov     [rsp+0AF8h+var_AA8], ebx
0x180011d95  mov     word ptr [rsp+0AF8h+var_838], di
0x180011d9d  mov     word ptr [rsp+0AF8h+var_A38], di
0x180011da5  movzx   edi, byte ptr [rsi+15h]
0x180011da9  mov     [rsp+0AF8h+var_AB0], edi
0x180011dad  mov     [rsp+0AF8h+var_AB8], ecx
0x180011db1  lea     rcx, [rsp+0AF8h+var_838]
0x180011db9  mov     dword ptr [rsp+0AF8h+lpUsedDefaultChar], edx
0x180011dbd  lea     rdx, aProcpktfromwan_0; "ProcPktFromWanarp: Result %d action %ws"...
0x180011dc4  mov     dword ptr [rsp+0AF8h+lpDefaultChar], r8d
0x180011dc9  xor     r8d, r8d
0x180011dcc  mov     [rsp+0AF8h+cbMultiByte], r9d
0x180011dd1  lea     r9, aDrop; "Drop"
0x180011dd8  mov     dword ptr [rsp+0AF8h+lpMultiByteStr], eax
0x180011ddc  call    FormatRRASErrorString
0x180011de1  xor     edi, edi
0x180011de3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180011dea  jge     short loc_180011E33
0x180011dec  lea     rax, [r14+2B0h]
0x180011df3  test    rax, rax
0x180011df6  lea     r9, [rsp+0AF8h+var_A70]
0x180011dfe  lea     r8, [rsp+0AF8h+var_838]
0x180011e06  cmovnz  r9, rax
0x180011e0a  lea     rdx, RasRtrmgrParamTraceInfo
0x180011e11  lea     rax, [rsp+0AF8h+var_A38]
0x180011e19  mov     qword ptr [rsp+0AF8h+cbMultiByte], rax
0x180011e1e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011e25  mov     rax, [r14+48h]
0x180011e29  mov     [rsp+0AF8h+lpMultiByteStr], rax
0x180011e2e  call    McTemplateU0zjzz_EventWriteTransfer
0x180011e33  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180011e3a  jz      short loc_180011E8A
0x180011e3c  lea     r8, aLeavingProcess; "Leaving: ProcessPacketFromWanArp"
0x180011e43  mov     word ptr [rsp+0AF8h+var_A38], di
0x180011e4b  lea     rax, [r14+2B0h]
0x180011e52  test    rax, rax
0x180011e55  lea     r9, [rsp+0AF8h+var_A70]
0x180011e5d  lea     rdx, RasRtrmgrParamTraceInfo
0x180011e64  cmovnz  r9, rax
0x180011e68  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011e6f  lea     rax, [rsp+0AF8h+var_A38]
0x180011e77  mov     qword ptr [rsp+0AF8h+cbMultiByte], rax
0x180011e7c  mov     rax, [r14+48h]
0x180011e80  mov     [rsp+0AF8h+lpMultiByteStr], rax
0x180011e85  call    McTemplateU0zjzz_EventWriteTransfer
0x180011e8a  mov     eax, 0Dh
0x180011e8f  jmp     loc_180012153
0x180011e94  test    r12d, r12d
0x180011e97  jz      loc_180011F74
0x180011e9d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180011ea4  jge     loc_180011F74
0x180011eaa  movzx   ecx, byte ptr [rsi+13h]
0x180011eae  movzx   edx, byte ptr [rsi+12h]
0x180011eb2  movzx   r8d, byte ptr [rsi+11h]
0x180011eb7  movzx   r10d, byte ptr [rsi+1Ch]
0x180011ebc  movzx   r11d, byte ptr [rsi+17h]
0x180011ec1  movzx   ebx, byte ptr [rsi+16h]
0x180011ec5  movzx   eax, byte ptr [rsi+14h]
0x180011ec9  movzx   r9d, byte ptr [rsi+10h]
0x180011ece  mov     [rsp+0AF8h+var_AA0], r10d
0x180011ed3  mov     [rsp+0AF8h+var_AA8], r11d
0x180011ed8  mov     [rsp+0AF8h+var_AB0], ebx
0x180011edc  mov     word ptr [rsp+0AF8h+var_838], di
0x180011ee4  mov     word ptr [rsp+0AF8h+var_A38], di
0x180011eec  movzx   edi, byte ptr [rsi+15h]
0x180011ef0  mov     [rsp+0AF8h+var_AB8], edi
0x180011ef4  mov     dword ptr [rsp+0AF8h+lpUsedDefaultChar], eax
0x180011ef8  mov     dword ptr [rsp+0AF8h+lpDefaultChar], ecx
0x180011efc  lea     rcx, [rsp+0AF8h+var_838]
0x180011f04  mov     [rsp+0AF8h+cbMultiByte], edx
0x180011f08  lea     rdx, aProcpktfromwan_1; "ProcPktFromWanarp: Result %d for packet"...
0x180011f0f  mov     dword ptr [rsp+0AF8h+lpMultiByteStr], r8d
0x180011f14  mov     r8d, r13d
0x180011f17  call    FormatRRASErrorString
0x180011f1c  xor     edi, edi
0x180011f1e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180011f25  jge     short loc_180011F74
0x180011f27  lea     rax, [r14+2B0h]
0x180011f2e  test    rax, rax
0x180011f31  lea     r9, [rsp+0AF8h+var_A70]
0x180011f39  lea     r8, [rsp+0AF8h+var_838]
0x180011f41  cmovnz  r9, rax
0x180011f45  lea     rdx, RasRtrmgrParamTraceInfo
0x180011f4c  lea     rax, [rsp+0AF8h+var_A38]
0x180011f54  mov     qword ptr [rsp+0AF8h+cbMultiByte], rax
0x180011f59  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011f60  mov     rax, [r14+48h]
0x180011f64  mov     [rsp+0AF8h+lpMultiByteStr], rax
0x180011f69  call    McTemplateU0zjzz_EventWriteTransfer
0x180011f6e  lea     rcx, [rsi+10h]
0x180011f72  jmp     short loc_180011F7D
0x180011f74  lea     rcx, [rsi+10h]; Addr
0x180011f78  test    r12d, r12d
0x180011f7b  jz      short loc_180011FB9
0x180011f7d  mov     ecx, [rcx]; in
0x180011f7f  call    cs:__imp_inet_ntoa
0x180011f85  mov     ebx, 41h ; 'A'
0x180011f8a  lea     rcx, [rsp+0AF8h+pszDest]; pszDest
0x180011f92  mov     r8, rax; pszSrc
0x180011f95  mov     edx, ebx; cbDest
0x180011f97  call    StringCbCopyA
0x180011f9c  mov     ecx, [rsi+14h]; in
0x180011f9f  call    cs:__imp_inet_ntoa
0x180011fa5  mov     edx, ebx; cbDest
0x180011fa7  lea     rcx, [rsp+0AF8h+S]; pszDest
0x180011faf  mov     r8, rax; pszSrc
0x180011fb2  call    StringCbCopyA
0x180011fb7  jmp     short loc_180011FD9
0x180011fb9  lea     rdx, [rsp+0AF8h+pszDest]; S
0x180011fc1  call    cs:__imp_RtlIpv6AddressToStringA
0x180011fc7  lea     rcx, [rsi+20h]; Addr
0x180011fcb  lea     rdx, [rsp+0AF8h+S]; S
0x180011fd3  call    cs:__imp_RtlIpv6AddressToStringA
0x180011fd9  neg     r12d
0x180011fdc  lea     r8, pszFormat; "%02x"
0x180011fe3  mov     ebx, 5
0x180011fe8  lea     rcx, [rsp+0AF8h+var_A10]; pszDest
0x180011ff0  sbb     rax, rax
0x180011ff3  mov     edx, ebx; cbDest
0x180011ff5  and     rax, 0FFFFFFFFFFFFFFE8h
0x180011ff9  movzx   r9d, byte ptr [rax+rsi+34h]
0x180011fff  call    StringCbPrintfA
0x180012004  mov     r8, [r14+48h]; lpWideCharStr
0x180012008  lea     rax, [rsp+0AF8h+MultiByteStr]
0x180012010  mov     [rsp+0AF8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180012015  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012019  mov     [rsp+0AF8h+lpDefaultChar], rdi; lpDefaultChar
0x18001201e  mov     edx, 400h; dwFlags
0x180012023  mov     [rsp+0AF8h+cbMultiByte], 100h; cbMultiByte
0x18001202b  xor     ecx, ecx; CodePage
0x18001202d  mov     [rsp+0AF8h+lpMultiByteStr], rax; lpMultiByteStr
0x180012032  call    cs:__imp_WideCharToMultiByte
0x180012038  mov     r9d, r15d
0x18001203b  mov     [rsp+0AF8h+var_848], dil
0x180012043  lea     r8, aD; "%d"
0x18001204a  lea     edx, [rbx+1Bh]; cbDest
0x18001204d  lea     rcx, [rsp+0AF8h+var_A08]; pszDest
0x180012055  call    StringCbPrintfA
0x18001205a  lea     edx, [rbx-3]; dwEventType
0x18001205d  cmp     cs:g_dwLoggingLevel, edx
0x180012063  jb      loc_1800120FA
0x180012069  mov     ecx, [rsp+0AF8h+var_A80]
0x18001206d  lea     rax, [rsp+0AF8h+pszDest]
0x180012075  mov     [rsp+0AF8h+plpszSubStringArray], rax
0x18001207d  sub     r15d, ecx
0x180012080  lea     rax, [rsp+0AF8h+S]
0x180012088  mov     r9d, ebx; dwSubStringCount
0x18001208b  mov     [rsp+0AF8h+var_A58], rax
0x180012093  mov     r8d, 4E9Eh; dwMessageId
0x180012099  lea     rax, [rsp+0AF8h+var_A10]
0x1800120a1  mov     [rsp+0AF8h+var_A50], rax
0x1800120a9  lea     rax, [rsp+0AF8h+MultiByteStr]
0x1800120b1  mov     [rsp+0AF8h+var_A48], rax
0x1800120b9  lea     rax, [rsp+0AF8h+var_A08]
0x1800120c1  mov     [rsp+0AF8h+var_A40], rax
0x1800120c9  mov     eax, ecx
0x1800120cb  add     rax, [rsp+0AF8h+var_A78]
0x1800120d3  mov     rcx, cs:g_hLogHandle; hLogHandle
0x1800120da  add     rax, rsi
0x1800120dd  mov     [rsp+0AF8h+lpDefaultChar], rax; lpDataBytes
0x1800120e2  lea     rax, [rsp+0AF8h+plpszSubStringArray]
0x1800120ea  mov     [rsp+0AF8h+cbMultiByte], r15d; dwDataBytes
0x1800120ef  mov     [rsp+0AF8h+lpMultiByteStr], rax; plpszSubStringArray
0x1800120f4  call    cs:__imp_RouterLogEventDataA
0x1800120fa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180012101  jz      short loc_180012151
0x180012103  lea     rax, [r14+2B0h]
0x18001210a  mov     word ptr [rsp+0AF8h+var_A38], di
0x180012112  test    rax, rax
0x180012115  lea     r9, [rsp+0AF8h+var_A70]
0x18001211d  lea     r8, aLeavingProcess; "Leaving: ProcessPacketFromWanArp"
0x180012124  cmovnz  r9, rax
0x180012128  lea     rdx, RasRtrmgrParamTraceInfo
  ... truncated ...
```
