# AddV6DemandFilterInterface

- ea: `0x18000dd34`
- end: `0x18000e338`
- name: `AddV6DemandFilterInterface`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000ca48`

## callees

- `0x18000dd34`
- `0x180011790`
- `0x18001e490`
- `0x180053c38`
- `0x180053d48`
- `0x180054bb0`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000e183`
- `KERNEL32!HeapFree` at `0x18000e226`
- `KERNEL32!HeapFree` at `0x18000e183`
- `KERNEL32!HeapFree` at `0x18000e226`
- `KERNEL32!HeapAlloc` at `0x18000de77`
- `KERNEL32!HeapAlloc` at `0x18000df5c`
- `KERNEL32!HeapAlloc` at `0x18000de77`
- `KERNEL32!HeapAlloc` at `0x18000df5c`

## string_xrefs

- `0x18000df44`: `AddV6DemandFilterInterface: Integer arithmetic overflow error allocating %d bytes for pf filter descriptors`

## pseudocode

```c
__int64 __fastcall AddV6DemandFilterInterface(__int64 a1, __int64 a2)
{
  __int128 *v4; // r9
  unsigned int v5; // edi
  __int64 PointerToTocEntry; // rax
  unsigned int v7; // ecx
  unsigned int *v8; // r14
  __int64 v9; // r15
  const wchar_t *v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // edi
  void *v13; // rax
  const wchar_t *v14; // rdx
  __int128 *v15; // r9
  char *v16; // rsi
  InterfaceContainer *v17; // rcx
  enum _PfForwardAction v18; // r13d
  unsigned int v19; // eax
  const wchar_t *v20; // rdx
  unsigned int v21; // r9d
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rax
  void **v25; // r14
  unsigned int v26; // eax
  __int64 v27; // r9
  __int128 *v28; // r9
  InterfaceContainer *v29; // rcx
  __int64 v30; // r9
  __int128 *v31; // r9
  __int128 *v32; // r9
  void *v33; // r8
  __int64 v34; // r8
  __int128 *v35; // r9
  __int128 *v36; // r9
  __int128 v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v40; // [rsp+5Ch] [rbp-A4h]
  __int128 v41; // [rsp+6Ch] [rbp-94h]
  int v42; // [rsp+7Ch] [rbp-84h]
  int v43; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v43 = 0;
  memset_0(v44, 0, sizeof(v44));
  v39 = 0;
  v40 = 0;
  v42 = 0;
  v41 = 0;
  v38 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v39) = 0;
    v4 = &v38;
    if ( a1 != -688 )
      LODWORD(v4) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"AddV6DemandFilterInterface",
      (_DWORD)v4,
      *(_QWORD *)(a1 + 72),
      (__int64)&v39);
  }
  v5 = 0;
  PointerToTocEntry = GetPointerToTocEntry(4294901779LL, a2);
  if ( !PointerToTocEntry || !*(_DWORD *)(PointerToTocEntry + 4) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_68;
    v10 = L"AddV6DemandFilterInterface: filter info NULL or info size 0 for %ws, so leaving";
    goto LABEL_64;
  }
  v7 = *(_DWORD *)(PointerToTocEntry + 12);
  if ( v7 >= *(_DWORD *)(a2 + 4) || (v8 = (unsigned int *)(a2 + v7)) == 0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_68;
    v10 = L"AddV6DemandFilterInterface: filter info NULL for %ws, so leaving";
    goto LABEL_64;
  }
  v9 = v8[1];
  if ( !*(_QWORD *)(v8 + 1) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_68;
    v10 = L"AddV6DemandFilterInterface: 0 filters and default of FORWARD for %ws, so leaving";
LABEL_64:
    v34 = *(_QWORD *)(a1 + 72);
    LOWORD(v43) = 0;
    LOWORD(v39) = 0;
    FormatRRASErrorString(&v43, v10, v34);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v35 = &v38;
      if ( a1 != -688 )
        LODWORD(v35) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v43,
        (_DWORD)v35,
        *(_QWORD *)(a1 + 72),
        (__int64)&v39);
    }
    goto LABEL_68;
  }
  v11 = 52 * v9;
  if ( (unsigned __int64)(52 * v9) > 0xFFFFFFFF || (v12 = v11 + 12, v11 + 12 < v11) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v20 = L"AddV6DemandFilterInterface: Integer arithmetic overflow error allocating %d bytes for demand dial filters";
LABEL_53:
      LOWORD(v43) = 0;
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v43, v20);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v32 = &v38;
        if ( a1 != -688 )
          LODWORD(v32) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v43,
          (_DWORD)v32,
          *(_QWORD *)(a1 + 72),
          (__int64)&v39);
      }
    }
LABEL_57:
    v5 = 534;
LABEL_58:
    v33 = *(void **)(a1 + 128);
    *(_QWORD *)(a1 + 104) = -1;
    if ( v33 )
    {
      HeapFree(IPRouterHeap, 0, v33);
      *(_QWORD *)(a1 + 128) = 0;
    }
    goto LABEL_68;
  }
  v13 = HeapAlloc(IPRouterHeap, 0, v12);
  *(_QWORD *)(a1 + 128) = v13;
  if ( !v13 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v14 = L"AddV6DemandFilterInterface: Error allocating %d bytes for demand dial filters";
      goto LABEL_17;
    }
    goto LABEL_21;
  }
  v16 = 0;
  memcpy_0(v13, v8, v12);
  v18 = v8[2];
  if ( (_DWORD)v9 )
  {
    v19 = 80 * v9;
    if ( (unsigned __int64)(80 * v9) > 0xFFFFFFFF || (v12 = v19 + 8, v19 + 8 < v19) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v20 = L"AddV6DemandFilterInterface: Integer arithmetic overflow error allocating %d bytes for pf filter descriptors";
        goto LABEL_53;
      }
      goto LABEL_57;
    }
    v16 = (char *)HeapAlloc(IPRouterHeap, 0, v12);
    if ( !v16 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v14 = L"AddV6DemandFilterInterface: Error allocating %d bytes";
LABEL_17:
        LOWORD(v39) = 0;
        LOWORD(v43) = 0;
        FormatRRASErrorString(&v43, v14, v12);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v15 = &v38;
          if ( a1 != -688 )
            LODWORD(v15) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v43,
            (_DWORD)v15,
            *(_QWORD *)(a1 + 72),
            (__int64)&v39);
        }
      }
LABEL_21:
      v5 = 8;
      goto LABEL_58;
    }
    v21 = 0;
    v22 = 0;
    do
    {
      v17 = (InterfaceContainer *)(52 * v22);
      v23 = v22 << 6;
      v24 = (__int64)&v8[13 * v22 + 3];
      ++v21;
      ++v22;
      *(_QWORD *)&v16[v23 + 16] = v24;
      *(_QWORD *)&v16[v23] = 0;
      *(_QWORD *)&v16[v23 + 24] = (char *)v8 + (_QWORD)v17 + 28;
      *(_DWORD *)&v16[v23 + 8] = 1;
      *(_QWORD *)&v16[v23 + 32] = (char *)v8 + (_QWORD)v17 + 32;
      *(_QWORD *)&v16[v23 + 40] = (char *)v8 + (_QWORD)v17 + 48;
      *(_DWORD *)&v16[v23 + 48] = *(_DWORD *)((char *)v17 + (_QWORD)v8 + 52);
      *(_DWORD *)&v16[v23 + 52] = 0;
      *(_WORD *)&v16[v23 + 56] = *(_WORD *)((char *)v17 + (_QWORD)v8 + 60);
      *(_WORD *)&v16[v23 + 58] = *(_WORD *)((char *)v17 + (_QWORD)v8 + 62);
      *(_DWORD *)&v16[v23 + 60] = 0;
    }
    while ( v21 < (unsigned int)v9 );
  }
  v25 = (void **)(a1 + 104);
  v26 = InterfaceContainer::AddInterface(v17, 0, v18, PF_ACTION_FORWARD, 0, 0, (void **)(a1 + 104), PF_IPV6);
  v5 = v26;
  if ( v26 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v27 = *(_QWORD *)(a1 + 72);
      LOWORD(v43) = 0;
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v43, L"AddDemandFilterInterface: Err %d creating filter i/f for %ws", v26, v27);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v28 = &v38;
        if ( a1 != -688 )
          LODWORD(v28) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v43,
          (_DWORD)v28,
          *(_QWORD *)(a1 + 72),
          (__int64)&v39);
      }
    }
  }
  else if ( (_DWORD)v9 )
  {
    v5 = PfInternAddFiltersToInterface(*v25, 0, 0);
    if ( v5 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v30 = *(_QWORD *)(a1 + 72);
        LOWORD(v43) = 0;
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v43, L"AddDemandFilterInterface: Err %d setting filters on %ws", v5, v30);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v31 = &v38;
          if ( a1 != -688 )
            LODWORD(v31) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v43,
            (_DWORD)v31,
            *(_QWORD *)(a1 + 72),
            (__int64)&v39);
        }
      }
      InterfaceContainer::DeleteInterface(v29, *v25);
    }
  }
  if ( v16 )
    HeapFree(IPRouterHeap, 0, v16);
  if ( v5 )
    goto LABEL_58;
LABEL_68:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v36 = &v38;
    LOWORD(v39) = 0;
    if ( a1 != -688 )
      LODWORD(v36) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"AddV6DemandFilterInterface",
      (_DWORD)v36,
      *(_QWORD *)(a1 + 72),
      (__int64)&v39);
  }
  return v5;
}

```

## disassembly

```asm
0x18000dd34  mov     [rsp-8+arg_10], rbx
0x18000dd39  push    rbp
0x18000dd3a  push    rsi
0x18000dd3b  push    rdi
0x18000dd3c  push    r12
0x18000dd3e  push    r13
0x18000dd40  push    r14
0x18000dd42  push    r15
0x18000dd44  lea     rbp, [rsp-790h]
0x18000dd4c  sub     rsp, 890h
0x18000dd53  mov     rax, cs:__security_cookie
0x18000dd5a  xor     rax, rsp
0x18000dd5d  mov     [rbp+7C0h+var_40], rax
0x18000dd64  mov     rsi, rdx
0x18000dd67  mov     rbx, rcx
0x18000dd6a  xor     eax, eax
0x18000dd6c  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18000dd70  xor     edx, edx; Val
0x18000dd72  mov     [rbp+7C0h+var_840], eax
0x18000dd75  mov     r8d, 7FCh; Size
0x18000dd7b  call    memset_0
0x18000dd80  xor     eax, eax
0x18000dd82  xorps   xmm0, xmm0
0x18000dd85  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000dd8c  mov     [rsp+8C0h+var_868], eax
0x18000dd90  movups  [rsp+8C0h+var_864], xmm0
0x18000dd95  mov     [rsp+8C0h+var_844], eax
0x18000dd99  movups  [rsp+8C0h+var_854], xmm0
0x18000dd9e  movups  [rsp+8C0h+var_878], xmm0
0x18000dda3  jz      short loc_18000DDEA
0x18000dda5  mov     word ptr [rsp+8C0h+var_868], ax
0x18000ddaa  lea     r9, [rsp+8C0h+var_878]
0x18000ddaf  lea     rax, [rbx+2B0h]
0x18000ddb6  test    rax, rax
0x18000ddb9  lea     r8, aAddv6demandfil_6; "AddV6DemandFilterInterface"
0x18000ddc0  lea     rdx, RasRtrmgrParamTraceInfo
0x18000ddc7  cmovnz  r9, rax
0x18000ddcb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ddd2  lea     rax, [rsp+8C0h+var_868]
0x18000ddd7  mov     [rsp+8C0h+var_898], rax
0x18000dddc  mov     rax, [rbx+48h]
0x18000dde0  mov     [rsp+8C0h+var_8A0], rax
0x18000dde5  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ddea  mov     rdx, rsi
0x18000dded  mov     ecx, 0FFFF0013h
0x18000ddf2  xor     edi, edi
0x18000ddf4  call    GetPointerToTocEntry
0x18000ddf9  test    rax, rax
0x18000ddfc  jz      loc_18000E24E
0x18000de02  cmp     [rax+4], edi
0x18000de05  jz      loc_18000E24E
0x18000de0b  mov     ecx, [rax+0Ch]
0x18000de0e  cmp     ecx, [rsi+4]
0x18000de11  jnb     loc_18000E23C
0x18000de17  mov     r14d, ecx
0x18000de1a  add     r14, rsi
0x18000de1d  jz      loc_18000E23C
0x18000de23  mov     r15d, [r14+4]
0x18000de27  test    r15d, r15d
0x18000de2a  jnz     short loc_18000DE4B
0x18000de2c  cmp     [r14+8], edi
0x18000de30  jnz     short loc_18000DE4B
0x18000de32  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18000de39  jge     loc_18000E2BC
0x18000de3f  lea     rdx, aAddv6demandfil_4; "AddV6DemandFilterInterface: 0 filters a"...
0x18000de46  jmp     loc_18000E25E
0x18000de4b  imul    rax, r15, 34h ; '4'
0x18000de4f  mov     ecx, 0FFFFFFFFh
0x18000de54  cmp     rax, rcx
0x18000de57  ja      loc_18000E193
0x18000de5d  lea     edi, [rax+0Ch]
0x18000de60  cmp     edi, eax
0x18000de62  jb      loc_18000E193
0x18000de68  mov     rcx, cs:IPRouterHeap; hHeap
0x18000de6f  xor     edx, edx; dwFlags
0x18000de71  mov     r8d, edi; dwBytes
0x18000de74  mov     r13d, edi
0x18000de77  call    cs:__imp_HeapAlloc
0x18000de7d  mov     [rbx+80h], rax
0x18000de84  test    rax, rax
0x18000de87  jnz     short loc_18000DF00
0x18000de89  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000de90  jz      short loc_18000DEF6
0x18000de92  lea     rdx, aAddv6demandfil_2; "AddV6DemandFilterInterface: Error alloc"...
0x18000de99  xor     eax, eax
0x18000de9b  lea     rcx, [rbp+7C0h+var_840]
0x18000de9f  mov     r8d, edi
0x18000dea2  mov     word ptr [rsp+8C0h+var_868], ax
0x18000dea7  mov     word ptr [rbp+7C0h+var_840], ax
0x18000deab  call    FormatRRASErrorString
0x18000deb0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000deb7  jz      short loc_18000DEF6
0x18000deb9  lea     rax, [rbx+2B0h]
0x18000dec0  test    rax, rax
0x18000dec3  lea     r9, [rsp+8C0h+var_878]
0x18000dec8  lea     r8, [rbp+7C0h+var_840]
0x18000decc  cmovnz  r9, rax
0x18000ded0  lea     rdx, RasRtrMgrParamTraceError
0x18000ded7  lea     rax, [rsp+8C0h+var_868]
0x18000dedc  mov     [rsp+8C0h+var_898], rax
0x18000dee1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000dee8  mov     rax, [rbx+48h]
0x18000deec  mov     [rsp+8C0h+var_8A0], rax
0x18000def1  call    McTemplateU0zjzz_EventWriteTransfer
0x18000def6  mov     edi, 8
0x18000defb  jmp     loc_18000E205
0x18000df00  mov     r8, r13; Size
0x18000df03  mov     rdx, r14; Src
0x18000df06  mov     rcx, rax; void *
0x18000df09  xor     esi, esi
0x18000df0b  call    memcpy_0
0x18000df10  mov     r13d, [r14+8]
0x18000df14  test    r15d, r15d
0x18000df17  jz      loc_18000E015
0x18000df1d  lea     rax, [r15+r15*4]
0x18000df21  mov     r8d, 0FFFFFFFFh
0x18000df27  shl     rax, 4
0x18000df2b  cmp     rax, r8
0x18000df2e  ja      short loc_18000DF37
0x18000df30  lea     edi, [rax+8]
0x18000df33  cmp     edi, eax
0x18000df35  jnb     short loc_18000DF50
0x18000df37  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000df3e  jz      loc_18000E200
0x18000df44  lea     rdx, aAddv6demandfil_1; "AddV6DemandFilterInterface: Integer ari"...
0x18000df4b  jmp     loc_18000E1A6
0x18000df50  mov     rcx, cs:IPRouterHeap; hHeap
0x18000df57  xor     edx, edx; dwFlags
0x18000df59  mov     r8d, edi; dwBytes
0x18000df5c  call    cs:__imp_HeapAlloc
0x18000df62  mov     rsi, rax
0x18000df65  test    rax, rax
0x18000df68  jnz     short loc_18000DF7F
0x18000df6a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000df71  jz      short loc_18000DEF6
0x18000df73  lea     rdx, aAddv6demandfil_5; "AddV6DemandFilterInterface: Error alloc"...
0x18000df7a  jmp     loc_18000DE99
0x18000df7f  xor     r9d, r9d
0x18000df82  test    r15d, r15d
0x18000df85  jz      loc_18000E015
0x18000df8b  xor     r8d, r8d
0x18000df8e  imul    rcx, r8, 34h ; '4'; this
0x18000df92  mov     rdx, r8
0x18000df95  lea     rax, [r14+0Ch]
0x18000df99  shl     rdx, 6
0x18000df9d  add     rax, rcx
0x18000dfa0  inc     r9d
0x18000dfa3  inc     r8
0x18000dfa6  mov     [rdx+rsi+10h], rax
0x18000dfab  lea     rax, [r14+1Ch]
0x18000dfaf  add     rax, rcx
0x18000dfb2  mov     qword ptr [rdx+rsi], 0
0x18000dfba  mov     [rdx+rsi+18h], rax
0x18000dfbf  lea     rax, [r14+20h]
0x18000dfc3  add     rax, rcx
0x18000dfc6  mov     dword ptr [rdx+rsi+8], 1
0x18000dfce  mov     [rdx+rsi+20h], rax
0x18000dfd3  lea     rax, [r14+30h]
0x18000dfd7  add     rax, rcx
0x18000dfda  mov     [rdx+rsi+28h], rax
0x18000dfdf  mov     eax, [r14+rcx+34h]
0x18000dfe4  mov     [rdx+rsi+30h], eax
0x18000dfe8  mov     dword ptr [rdx+rsi+34h], 0
0x18000dff0  movzx   eax, word ptr [r14+rcx+3Ch]
0x18000dff6  mov     [rdx+rsi+38h], ax
0x18000dffb  movzx   eax, word ptr [r14+rcx+3Eh]
0x18000e001  mov     [rdx+rsi+3Ah], ax
0x18000e006  xor     eax, eax
0x18000e008  mov     [rdx+rsi+3Ch], eax
0x18000e00c  cmp     r9d, r15d
0x18000e00f  jb      loc_18000DF8E
0x18000e015  mov     [rsp+8C0h+var_888], 1; enum _PfAddresType
0x18000e01d  lea     r14, [rbx+68h]
0x18000e021  mov     [rsp+8C0h+var_890], r14; void **
0x18000e026  xor     r9d, r9d; enum _PfForwardAction
0x18000e029  mov     dword ptr [rsp+8C0h+var_898], 0; int
0x18000e031  mov     r8d, r13d; enum _PfForwardAction
0x18000e034  xor     edx, edx; unsigned int
0x18000e036  mov     dword ptr [rsp+8C0h+var_8A0], 0; int
0x18000e03e  call    ?AddInterface@InterfaceContainer@@QEAAKKW4_PfForwardAction@@0HHPEAPEAXW4_PfAddresType@@@Z; InterfaceContainer::AddInterface(ulong,_PfForwardAction,_PfForwardAction,int,int,void * *,_PfAddresType)
0x18000e043  mov     edi, eax
0x18000e045  test    eax, eax
0x18000e047  jz      short loc_18000E0C7
0x18000e049  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e050  jge     loc_18000E172
0x18000e056  mov     r9, [rbx+48h]
0x18000e05a  lea     rdx, aAdddemandfilte_1; "AddDemandFilterInterface: Err %d creati"...
0x18000e061  xor     ecx, ecx
0x18000e063  mov     r8d, eax
0x18000e066  mov     word ptr [rbp+7C0h+var_840], cx
0x18000e06a  mov     word ptr [rsp+8C0h+var_868], cx
0x18000e06f  lea     rcx, [rbp+7C0h+var_840]
0x18000e073  call    FormatRRASErrorString
0x18000e078  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e07f  jge     loc_18000E172
0x18000e085  lea     rax, [rbx+2B0h]
0x18000e08c  test    rax, rax
0x18000e08f  lea     r9, [rsp+8C0h+var_878]
0x18000e094  lea     r8, [rbp+7C0h+var_840]
0x18000e098  cmovnz  r9, rax
0x18000e09c  lea     rdx, RasRtrmgrParamTraceInfo
0x18000e0a3  lea     rax, [rsp+8C0h+var_868]
0x18000e0a8  mov     [rsp+8C0h+var_898], rax
0x18000e0ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e0b4  mov     rax, [rbx+48h]
0x18000e0b8  mov     [rsp+8C0h+var_8A0], rax
0x18000e0bd  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e0c2  jmp     loc_18000E172
0x18000e0c7  test    r15d, r15d
0x18000e0ca  jz      loc_18000E172
0x18000e0d0  mov     rcx, [r14]; void *
0x18000e0d3  xor     r9d, r9d
0x18000e0d6  mov     [rsp+8C0h+var_898], 0; __int64
0x18000e0df  mov     r8, rsi
0x18000e0e2  mov     edx, r15d
0x18000e0e5  mov     [rsp+8C0h+var_8A0], 0; __int64
0x18000e0ee  call    PfInternAddFiltersToInterface
0x18000e0f3  mov     edi, eax
0x18000e0f5  test    eax, eax
0x18000e0f7  jz      short loc_18000E172
0x18000e0f9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e100  jge     short loc_18000E16A
0x18000e102  mov     r9, [rbx+48h]
0x18000e106  lea     rdx, aAdddemandfilte_3; "AddDemandFilterInterface: Err %d settin"...
0x18000e10d  xor     eax, eax
0x18000e10f  lea     rcx, [rbp+7C0h+var_840]
0x18000e113  mov     r8d, edi
0x18000e116  mov     word ptr [rbp+7C0h+var_840], ax
0x18000e11a  mov     word ptr [rsp+8C0h+var_868], ax
0x18000e11f  call    FormatRRASErrorString
0x18000e124  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e12b  jge     short loc_18000E16A
0x18000e12d  lea     rax, [rbx+2B0h]
0x18000e134  test    rax, rax
0x18000e137  lea     r9, [rsp+8C0h+var_878]
0x18000e13c  lea     r8, [rbp+7C0h+var_840]
0x18000e140  cmovnz  r9, rax
0x18000e144  lea     rdx, RasRtrmgrParamTraceInfo
0x18000e14b  lea     rax, [rsp+8C0h+var_868]
0x18000e150  mov     [rsp+8C0h+var_898], rax
0x18000e155  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e15c  mov     rax, [rbx+48h]
0x18000e160  mov     [rsp+8C0h+var_8A0], rax
0x18000e165  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e16a  mov     rdx, [r14]; void *
0x18000e16d  call    ?DeleteInterface@InterfaceContainer@@QEAAKPEAX@Z; InterfaceContainer::DeleteInterface(void *)
0x18000e172  test    rsi, rsi
0x18000e175  jz      short loc_18000E189
0x18000e177  mov     rcx, cs:IPRouterHeap; hHeap
0x18000e17e  mov     r8, rsi; lpMem
0x18000e181  xor     edx, edx; dwFlags
0x18000e183  call    cs:__imp_HeapFree
0x18000e189  test    edi, edi
0x18000e18b  jz      loc_18000E2BC
0x18000e191  jmp     short loc_18000E205
0x18000e193  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000e19a  jz      short loc_18000E200
0x18000e19c  mov     r8d, ecx
0x18000e19f  lea     rdx, aAddv6demandfil_3; "AddV6DemandFilterInterface: Integer ari"...
0x18000e1a6  xor     eax, eax
0x18000e1a8  lea     rcx, [rbp+7C0h+var_840]
0x18000e1ac  mov     word ptr [rbp+7C0h+var_840], ax
0x18000e1b0  mov     word ptr [rsp+8C0h+var_868], ax
0x18000e1b5  call    FormatRRASErrorString
0x18000e1ba  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000e1c1  jz      short loc_18000E200
0x18000e1c3  lea     rax, [rbx+2B0h]
0x18000e1ca  test    rax, rax
0x18000e1cd  lea     r9, [rsp+8C0h+var_878]
0x18000e1d2  lea     r8, [rbp+7C0h+var_840]
0x18000e1d6  cmovnz  r9, rax
0x18000e1da  lea     rdx, RasRtrMgrParamTraceError
0x18000e1e1  lea     rax, [rsp+8C0h+var_868]
0x18000e1e6  mov     [rsp+8C0h+var_898], rax
0x18000e1eb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e1f2  mov     rax, [rbx+48h]
0x18000e1f6  mov     [rsp+8C0h+var_8A0], rax
0x18000e1fb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e200  mov     edi, 216h
0x18000e205  mov     r8, [rbx+80h]; lpMem
0x18000e20c  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x18000e214  test    r8, r8
0x18000e217  jz      loc_18000E2BC
0x18000e21d  mov     rcx, cs:IPRouterHeap; hHeap
0x18000e224  xor     edx, edx; dwFlags
0x18000e226  call    cs:__imp_HeapFree
0x18000e22c  mov     qword ptr [rbx+80h], 0
0x18000e237  jmp     loc_18000E2BC
0x18000e23c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18000e243  jge     short loc_18000E2BC
0x18000e245  lea     rdx, aAddv6demandfil_0; "AddV6DemandFilterInterface: filter info"...
0x18000e24c  jmp     short loc_18000E25E
0x18000e24e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18000e255  jge     short loc_18000E2BC
0x18000e257  lea     rdx, aAddv6demandfil; "AddV6DemandFilterInterface: filter info"...
0x18000e25e  mov     r8, [rbx+48h]
0x18000e262  lea     rcx, [rbp+7C0h+var_840]
0x18000e266  xor     eax, eax
0x18000e268  mov     word ptr [rbp+7C0h+var_840], ax
0x18000e26c  mov     word ptr [rsp+8C0h+var_868], ax
  ... truncated ...
```
