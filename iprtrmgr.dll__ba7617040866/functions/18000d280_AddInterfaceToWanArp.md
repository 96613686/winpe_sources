# AddInterfaceToWanArp

- ea: `0x18000d280`
- end: `0x18000dd2c`
- name: `AddInterfaceToWanArp`
- size: `2732`
- prototype: `__int64 __fastcall(struct _ICB *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e5c`

## callees

- `0x180001f30`
- `0x18000d280`
- `0x18000e340`
- `0x18000f2ac`
- `0x180011790`
- `0x1800124e8`
- `0x180057bac`
- `0x180057c8c`
- `0x180057d48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000d606`
- `msvcrt!swprintf_s` at `0x18000d606`
- `ntdll!RtlNtStatusToDosError` at `0x18000da32`
- `ntdll!RtlNtStatusToDosError` at `0x18000da32`
- `ntdll!NtDeviceIoControlFile` at `0x18000d99d`
- `ntdll!NtDeviceIoControlFile` at `0x18000d99d`
- `KERNEL32!HeapAlloc` at `0x18000da99`
- `KERNEL32!HeapAlloc` at `0x18000da99`

## string_xrefs

- `0x18000d750`: `INFO: AddInterfaceToWanarp: InterfaceLuid already exists with IfIndex %d. Reusing it for IfIndex %d`
- `0x18000d7dd`: `AddInterfaceToWANARP: InterfaceLookup failed for interface %ws. Protocol %d`
- `0x18000dc83`: `AddInterfaceToWANARP: GetInterfaceHandle failed for interface %ws. Protocol %d`

## pseudocode

```c
__int64 __fastcall AddInterfaceToWanArp(struct _ICB *a1, unsigned int a2)
{
  unsigned int v4; // r13d
  char v5; // al
  __int128 *v6; // r9
  __int64 v7; // r8
  __int128 *v8; // r9
  bool v9; // zf
  int v10; // r12d
  __int64 InternalInterfaceForRoutingDomain; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  ULONG v14; // eax
  ULONG v15; // edi
  __int64 v16; // r8
  __int128 *v17; // r9
  __int64 *v18; // rdx
  unsigned __int64 v19; // rcx
  ULONG v20; // eax
  __int64 v21; // rcx
  __int128 *v22; // r9
  __int64 v23; // rcx
  ULONG v24; // eax
  __int64 v25; // r8
  unsigned int v26; // esi
  ULONG v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r9
  __int128 *v31; // r9
  const wchar_t *v32; // rdx
  const wchar_t *v33; // rdx
  __int64 v34; // r8
  __int128 *v35; // r9
  __int64 v36; // r8
  unsigned __int64 v37; // rax
  HANDLE v38; // rcx
  unsigned int v39; // eax
  NTSTATUS v40; // esi
  __int64 v41; // r9
  __int128 *v42; // r9
  __int64 v43; // rsi
  __int64 v44; // rax
  SIZE_T v45; // r14
  wchar_t *v46; // rax
  __int128 *v47; // r9
  __int64 v48; // r9
  __int64 v49; // r8
  __int128 *v50; // r9
  const wchar_t *v51; // r8
  __int64 v52; // r8
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-D08h]
  unsigned int v55; // [rsp+50h] [rbp-CD8h] BYREF
  __int64 v56; // [rsp+58h] [rbp-CD0h] BYREF
  struct _IO_STATUS_BLOCK v57; // [rsp+60h] [rbp-CC8h] BYREF
  __int128 v58; // [rsp+70h] [rbp-CB8h] BYREF
  int InputBuffer; // [rsp+80h] [rbp-CA8h] BYREF
  int v60; // [rsp+84h] [rbp-CA4h]
  int v61; // [rsp+88h] [rbp-CA0h]
  wchar_t pszSrc[258]; // [rsp+8Ch] [rbp-C9Ch] BYREF
  unsigned __int64 v63; // [rsp+290h] [rbp-A98h]
  _BYTE v64[16]; // [rsp+298h] [rbp-A90h] BYREF
  wchar_t Buffer[260]; // [rsp+2A8h] [rbp-A80h] BYREF
  int v66; // [rsp+4B0h] [rbp-878h]
  int v67; // [rsp+4C0h] [rbp-868h] BYREF
  __int128 v68; // [rsp+4C4h] [rbp-864h]
  __int128 v69; // [rsp+4D4h] [rbp-854h]
  int v70; // [rsp+4E4h] [rbp-844h]
  int v71; // [rsp+4F0h] [rbp-838h] BYREF
  _BYTE v72[2044]; // [rsp+4F4h] [rbp-834h] BYREF

  v57 = 0;
  memset_0(&InputBuffer, 0, 0x438u);
  v55 = 0;
  v71 = 0;
  v4 = 0;
  memset_0(v72, 0, sizeof(v72));
  v67 = 0;
  v70 = 0;
  v5 = Microsoft_Windows_RRASEnableBits;
  LOBYTE(v56) = Microsoft_Windows_RRASEnableBits & 0x80;
  v68 = 0;
  v69 = 0;
  v58 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v67) = 0;
    v6 = &v58;
    if ( a1 != (struct _ICB *)-688LL )
      LODWORD(v6) = (_DWORD)a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"AddInterfaceToWanArp",
      (_DWORD)v6,
      *((_QWORD *)a1 + 9),
      (__int64)&v67);
    v5 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v5 < 0 )
  {
    v7 = *((_QWORD *)a1 + 9);
    LOWORD(v71) = 0;
    LOWORD(v67) = 0;
    FormatRRASErrorString(&v71, L"AddInterfaceToWanArp: Adding %ws to WanArp", v7);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = &v58;
      if ( a1 != (struct _ICB *)-688LL )
        LODWORD(v8) = (_DWORD)a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v71,
        (_DWORD)v8,
        *((_QWORD *)a1 + 9),
        (__int64)&v67);
    }
  }
  v9 = *((_DWORD *)a1 + 36) == 4;
  v10 = 0;
  InputBuffer = *((_DWORD *)a1 + 22);
  v66 = *((_DWORD *)a1 + 176);
  v61 = -1;
  if ( !v9 )
  {
    v23 = *((_QWORD *)a1 + 23);
    v56 = 0;
    v60 = 0;
    v24 = ((__int64 (__fastcall *)(__int64, _BYTE *))GetInterfaceDeviceGuid)(v23, v64);
    v15 = v24;
    if ( v24 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return v15;
      v25 = *((_QWORD *)a1 + 9);
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      FormatRRASErrorString(
        &v71,
        L"AddInterfaceToWanarp: Unable to query the router phone book for %ws: 0x%x",
        v25,
        v24);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return v15;
      v17 = &v58;
      v18 = RasRtrmgrParamTraceInfo;
      if ( a1 != (struct _ICB *)-688LL )
        LODWORD(v17) = (_DWORD)a1 + 688;
      goto LABEL_101;
    }
    StringCbCopyW(Buffer, 0x200u, *((STRSAFE_LPCWSTR *)a1 + 9));
    v26 = *((_DWORD *)a1 + 129) != 0 ? 87 : 33;
    v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))GetInterfaceHandle)(*((_QWORD *)a1 + 9), v26, &v56);
    v15 = v27;
    if ( v27 )
    {
      if ( v27 != 15012 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return v15;
        v32 = L"AddInterfaceToWANARP: GetInterfaceHandle failed for interface %ws. Protocol %d";
LABEL_97:
        v52 = *((_QWORD *)a1 + 9);
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        FormatRRASErrorString(&v71, v32, v52, v26);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return v15;
        v17 = &v58;
        if ( a1 != (struct _ICB *)-688LL )
          LODWORD(v17) = (_DWORD)a1 + 688;
LABEL_100:
        v18 = RasRtrmgrParamTraceInfo;
        goto LABEL_101;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v33 = L"INFO:2 AddInterfaceToWanarp: This is the first interface context for %ws";
LABEL_50:
        v34 = *((_QWORD *)a1 + 9);
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        FormatRRASErrorString(&v71, v33, v34);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v35 = &v58;
          if ( a1 != (struct _ICB *)-688LL )
            LODWORD(v35) = (_DWORD)a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v71,
            (_DWORD)v35,
            *((_QWORD *)a1 + 9),
            (__int64)&v67);
        }
      }
    }
    else
    {
      v28 = v56;
      if ( (unsigned __int64)(v56 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v29 = InterfaceLookupByICBSeqNumber(v56);
        if ( v29 )
        {
          v63 = *(_QWORD *)(v29 + 160);
          *((_QWORD *)a1 + 20) = *(_QWORD *)(v29 + 160);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v30 = *((unsigned int *)a1 + 4);
            LOWORD(v71) = 0;
            LOWORD(v67) = 0;
            FormatRRASErrorString(
              &v71,
              L"INFO: AddInterfaceToWanarp: InterfaceLuid already exists with IfIndex %d. Reusing it for IfIndex %d",
              *(unsigned int *)(v29 + 16),
              v30);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v31 = &v58;
              if ( a1 != (struct _ICB *)-688LL )
                LODWORD(v31) = (_DWORD)a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v71,
                (_DWORD)v31,
                *((_QWORD *)a1 + 9),
                (__int64)&v67);
            }
          }
          goto LABEL_61;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return v15;
        v32 = L"AddInterfaceToWANARP: InterfaceLookup failed for interface %ws. Protocol %d";
        goto LABEL_97;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v33 = L"INFO:1 AddInterfaceToWanarp: This is the first interface context for %ws";
        goto LABEL_50;
      }
    }
    v15 = AllocInterfaceLuidIndex(v28, a2, (char *)a1 + 688, &v55);
    if ( !v15 )
    {
      v4 = v55;
      *((_WORD *)a1 + 83) = 23;
      v10 = 1;
      v37 = ((unsigned __int64)v4 << 24) ^ (*((_QWORD *)a1 + 20) ^ ((unsigned __int64)v4 << 24)) & 0xFFFF000000000000uLL;
      *((_QWORD *)a1 + 20) = v37;
      v63 = v37;
      goto LABEL_61;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v15;
    v36 = *((_QWORD *)a1 + 9);
    LOWORD(v71) = 0;
    LOWORD(v67) = 0;
    FormatRRASErrorString(&v71, L"AddInterfaceToWANARP: Unable to allocate ifLuid when adding %ws to wanarp", v36);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v15;
    v17 = &v58;
    if ( a1 != (struct _ICB *)-688LL )
      LODWORD(v17) = (_DWORD)a1 + 688;
    goto LABEL_100;
  }
  v60 = 1;
  if ( !(unsigned int)IsMultiTenancyEnabled() )
  {
    v15 = 0;
    v63 = 0;
    goto LABEL_61;
  }
  InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain((struct _GUID *)a1 + 43, a2 != 0 ? 87 : 33);
  if ( !InternalInterfaceForRoutingDomain )
  {
    v14 = AllocInterfaceLuidIndex(v12, a2, (char *)a1 + 688, &v55);
    v15 = v14;
    if ( !v14 )
    {
      v4 = v55;
      *((_WORD *)a1 + 83) = 23;
      v10 = 1;
      v19 = ((unsigned __int64)v4 << 24) ^ (*((_QWORD *)a1 + 20) ^ ((unsigned __int64)v4 << 24)) & 0xFFFF000000FFFFFFuLL;
      *((_QWORD *)a1 + 20) = v19;
      v13 = v19 & 0xFFFFFFFFFF000000uLL;
      goto LABEL_21;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return v15;
    v16 = *((_QWORD *)a1 + 9);
    LOWORD(v71) = 0;
    LOWORD(v67) = 0;
    FormatRRASErrorString(
      &v71,
      L"AddInterfaceToWANARP: Unable to allocate ifLuid when adding %ws to wanarp, Error: %d",
      v16,
      v14);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return v15;
    v17 = &v58;
    v18 = RasRtrMgrParamTraceError;
    if ( a1 != (struct _ICB *)-688LL )
      LODWORD(v17) = (_DWORD)a1 + 688;
LABEL_101:
    v51 = (const wchar_t *)&v71;
    goto LABEL_102;
  }
  v13 = *(_QWORD *)(InternalInterfaceForRoutingDomain + 160);
LABEL_21:
  *((_QWORD *)a1 + 20) = v13;
  v63 = v13;
  v20 = ((__int64 (__fastcall *)(_QWORD, _BYTE *))GetInterfaceDeviceGuid)(*((_QWORD *)a1 + 23), v64);
  v15 = v20;
  if ( v20 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v71) = 0;
      LOWORD(v67) = 0;
      FormatRRASErrorString(
        &v71,
        L"AddInterfaceToWanarp: Unable to get device GUID for dial in interface from DIM.Error: %d",
        v20);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v22 = &v58;
        if ( a1 != (struct _ICB *)-688LL )
          LODWORD(v22) = (_DWORD)a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v71,
          (_DWORD)v22,
          *((_QWORD *)a1 + 9),
          (__int64)&v67);
      }
    }
LABEL_83:
    if ( v10 )
      FreeInterfaceLuidIndex(v21, a2, (char *)a1 + 688, v4);
    return v15;
  }
  LODWORD(IoStatusBlock) = v66;
  swprintf_s(Buffer, 0x100u, L"%s - %d", L"RAS (Dial In) Interface", IoStatusBlock);
LABEL_61:
  v38 = (HANDLE)g_hWanarpWriteV6;
  if ( a2 )
    v38 = g_hWanarpWrite;
  v39 = NtDeviceIoControlFile(v38, 0, 0, 0, &v57, 0x90018004, &InputBuffer, 0x438u, &InputBuffer, 0x438u);
  v40 = v39;
  if ( !v39 )
  {
    v9 = *((_DWORD *)a1 + 36) == 4;
    *((_DWORD *)a1 + 4) = v61;
    if ( v9 )
    {
      v43 = -1;
      pszSrc[256] = 0;
      v44 = -1;
      do
        ++v44;
      while ( pszSrc[v44] );
      v45 = (unsigned int)(2 * v44 + 2);
      v46 = (wchar_t *)HeapAlloc(IPRouterHeap, 8u, v45);
      *((_QWORD *)a1 + 10) = v46;
      if ( !v46 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v71) = 0;
          LOWORD(v67) = 0;
          do
            ++v43;
          while ( pszSrc[v43] );
          FormatRRASErrorString(
            &v71,
            L"AddInterfaceToWANARP: Unable to allocate %d bytes when adding %ws to wanarp",
            2 * v43 + 2,
            *((_QWORD *)a1 + 9));
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v47 = &v58;
            if ( a1 != (struct _ICB *)-688LL )
              LODWORD(v47) = (_DWORD)a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v71,
              (_DWORD)v47,
              *((_QWORD *)a1 + 9),
              (__int64)&v67);
          }
        }
        v15 = 8;
        goto LABEL_83;
      }
      StringCbCopyW(v46, v45, pszSrc);
      *((_QWORD *)a1 + 20) = v63;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v48 = *((_QWORD *)a1 + 10);
        v49 = *((_QWORD *)a1 + 9);
        LOWORD(v71) = 0;
        LOWORD(v67) = 0;
        FormatRRASErrorString(&v71, L"AddInterfaceToWANARP: %ws device name %ws\n", v49, v48);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v50 = &v58;
          if ( a1 != (struct _ICB *)-688LL )
            LODWORD(v50) = (_DWORD)a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v71,
            (_DWORD)v50,
            *((_QWORD *)a1 + 9),
            (__int64)&v67);
        }
      }
      SetInternalInterfaceForRoutingDomain((struct _GUID *)a1 + 43, *((_DWORD *)a1 + 129) != 0 ? 33 : 87, a1);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v15;
    LOWORD(v67) = 0;
    v17 = &v58;
    v51 = L"Leaving: AddInterfaceToWANARP";
    if ( a1 != (struct _ICB *)-688LL )
      LODWORD(v17) = (_DWORD)a1 + 688;
    v18 = RasRtrmgrParamTraceInfo;
LABEL_102:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (_DWORD)v18,
      (_DWORD)v51,
      (_DWORD)v17,
      *((_QWORD *)a1 + 9),
      (__int64)&v67);
    return v15;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v41 = *((_QWORD *)a1 + 9);
    LOWORD(v71) = 0;
    LOWORD(v67) = 0;
    FormatRRASErrorString(&v71, L"AddInterfaceToWANARP: Status %x adding %ws to WanArp", v39, v41);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v42 = &v58;
      if ( a1 != (struct _ICB *)-688LL )
        LODWORD(v42) = (_DWORD)a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v71,
        (_DWORD)v42,
        *((_QWORD *)a1 + 9),
        (__int64)&v67);
    }
  }
  v15 = RtlNtStatusToDosError(v40);
  if ( v15 )
    goto LABEL_83;
  return v15;
}

```

## disassembly

```asm
0x18000d280  mov     [rsp+arg_10], rbx
0x18000d285  mov     [rsp+arg_18], rsi
0x18000d28a  push    rdi
0x18000d28b  push    r12
0x18000d28d  push    r13
0x18000d28f  push    r14
0x18000d291  push    r15
0x18000d293  sub     rsp, 0D00h
0x18000d29a  mov     rax, cs:__security_cookie
0x18000d2a1  xor     rax, rsp
0x18000d2a4  mov     [rsp+0D28h+var_38], rax
0x18000d2ac  mov     r15d, edx
0x18000d2af  mov     rbx, rcx
0x18000d2b2  xorps   xmm0, xmm0
0x18000d2b5  lea     rcx, [rsp+0D28h+var_CA8]; void *
0x18000d2bd  xor     edx, edx; Val
0x18000d2bf  mov     r8d, 438h; Size
0x18000d2c5  movups  xmmword ptr [rsp+0D28h+var_CC8], xmm0
0x18000d2ca  call    memset_0
0x18000d2cf  xor     r14d, r14d
0x18000d2d2  lea     rcx, [rsp+0D28h+var_834]; void *
0x18000d2da  xor     edx, edx; Val
0x18000d2dc  mov     [rsp+0D28h+var_CD8], r14d
0x18000d2e1  mov     r8d, 7FCh; Size
0x18000d2e7  mov     [rsp+0D28h+var_838], r14d
0x18000d2ef  mov     r13d, r14d
0x18000d2f2  call    memset_0
0x18000d2f7  xor     eax, eax
0x18000d2f9  mov     [rsp+0D28h+var_868], r14d
0x18000d301  xorps   xmm0, xmm0
0x18000d304  mov     [rsp+0D28h+var_844], eax
0x18000d30b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000d312  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d319  mov     cl, al
0x18000d31b  lea     rdi, [rbx+2B0h]
0x18000d322  and     cl, 80h
0x18000d325  mov     byte ptr [rsp+0D28h+var_CD0], cl
0x18000d329  movups  [rsp+0D28h+var_864], xmm0
0x18000d331  movups  [rsp+0D28h+var_854], xmm0
0x18000d339  movups  [rsp+0D28h+var_CB8], xmm0
0x18000d33e  jz      short loc_18000D388
0x18000d340  lea     rax, [rsp+0D28h+var_868]
0x18000d348  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d351  mov     qword ptr [rsp+0D28h+IoControlCode], rax
0x18000d356  lea     r9, [rsp+0D28h+var_CB8]
0x18000d35b  mov     rax, [rbx+48h]
0x18000d35f  lea     r8, aAddinterfaceto_3; "AddInterfaceToWanArp"
0x18000d366  test    rdi, rdi
0x18000d369  mov     [rsp+0D28h+IoStatusBlock], rax
0x18000d36e  lea     rdx, RasRtrmgrParamTraceInfo
0x18000d375  mov     rcx, rsi
0x18000d378  cmovnz  r9, rdi
0x18000d37c  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d381  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000d388  test    al, al
0x18000d38a  jns     short loc_18000D3F8
0x18000d38c  mov     r8, [rbx+48h]
0x18000d390  lea     rdx, aAddinterfaceto_4; "AddInterfaceToWanArp: Adding %ws to Wan"...
0x18000d397  lea     rcx, [rsp+0D28h+var_838]
0x18000d39f  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d3a8  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d3b1  call    FormatRRASErrorString
0x18000d3b6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d3bd  jge     short loc_18000D3F8
0x18000d3bf  lea     rax, [rsp+0D28h+var_868]
0x18000d3c7  test    rdi, rdi
0x18000d3ca  mov     qword ptr [rsp+0D28h+IoControlCode], rax
0x18000d3cf  lea     r9, [rsp+0D28h+var_CB8]
0x18000d3d4  mov     rax, [rbx+48h]
0x18000d3d8  lea     r8, [rsp+0D28h+var_838]
0x18000d3e0  cmovnz  r9, rdi
0x18000d3e4  mov     [rsp+0D28h+IoStatusBlock], rax
0x18000d3e9  lea     rdx, RasRtrmgrParamTraceInfo
0x18000d3f0  mov     rcx, rsi
0x18000d3f3  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d3f8  cmp     dword ptr [rbx+90h], 4
0x18000d3ff  mov     r12d, r14d
0x18000d402  mov     eax, [rbx+58h]
0x18000d405  mov     [rsp+0D28h+var_CA8], eax
0x18000d40c  mov     eax, [rbx+2C0h]
0x18000d412  mov     [rsp+0D28h+var_878], eax
0x18000d419  mov     [rsp+0D28h+var_CA0], 0FFFFFFFFh
0x18000d424  jnz     loc_18000D621
0x18000d42a  mov     [rsp+0D28h+var_CA4], 1
0x18000d435  call    IsMultiTenancyEnabled
0x18000d43a  test    eax, eax
0x18000d43c  jz      loc_18000D611
0x18000d442  mov     eax, r15d
0x18000d445  lea     rsi, [rbx+2B0h]
0x18000d44c  neg     eax
0x18000d44e  mov     rcx, rsi; struct _GUID *
0x18000d451  sbb     edx, edx
0x18000d453  and     edx, 36h
0x18000d456  add     edx, 21h ; '!'; unsigned int
0x18000d459  call    GetInternalInterfaceForRoutingDomain
0x18000d45e  test    rax, rax
0x18000d461  jz      short loc_18000D46F
0x18000d463  mov     rcx, [rax+0A0h]
0x18000d46a  jmp     loc_18000D527
0x18000d46f  lea     r9, [rsp+0D28h+var_CD8]
0x18000d474  mov     r8, rsi
0x18000d477  mov     edx, r15d
0x18000d47a  call    AllocInterfaceLuidIndex
0x18000d47f  mov     edi, eax
0x18000d481  test    eax, eax
0x18000d483  jz      short loc_18000D4E4
0x18000d485  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000d48c  jz      loc_18000DCFD
0x18000d492  mov     r8, [rbx+48h]
0x18000d496  lea     rdx, aAddinterfaceto_7; "AddInterfaceToWANARP: Unable to allocat"...
0x18000d49d  mov     r9d, eax
0x18000d4a0  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d4a9  lea     rcx, [rsp+0D28h+var_838]
0x18000d4b1  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d4ba  call    FormatRRASErrorString
0x18000d4bf  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000d4c6  jz      loc_18000DCFD
0x18000d4cc  test    rsi, rsi
0x18000d4cf  lea     r9, [rsp+0D28h+var_CB8]
0x18000d4d4  lea     rdx, RasRtrMgrParamTraceError
0x18000d4db  cmovnz  r9, rsi
0x18000d4df  jmp     loc_18000DCD3
0x18000d4e4  mov     r13d, [rsp+0D28h+var_CD8]
0x18000d4e9  mov     rdx, 0FFFF000000FFFFFFh
0x18000d4f3  mov     word ptr [rbx+0A6h], 17h
0x18000d4fc  mov     eax, r13d
0x18000d4ff  shl     rax, 18h
0x18000d503  mov     r12d, 1
0x18000d509  mov     rcx, rax
0x18000d50c  xor     rcx, [rbx+0A0h]
0x18000d513  and     rcx, rdx
0x18000d516  xor     rcx, rax
0x18000d519  mov     [rbx+0A0h], rcx
0x18000d520  and     rcx, 0FFFFFFFFFF000000h
0x18000d527  mov     [rbx+0A0h], rcx
0x18000d52e  lea     rdx, [rsp+0D28h+var_A90]
0x18000d536  mov     rax, cs:GetInterfaceDeviceGuid
0x18000d53d  mov     [rsp+0D28h+var_A98], rcx
0x18000d545  mov     rcx, [rbx+0B8h]
0x18000d54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d551  mov     edi, eax
0x18000d553  test    eax, eax
0x18000d555  jz      loc_18000D5E0
0x18000d55b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000d562  jz      loc_18000DB52
0x18000d568  mov     r8d, eax
0x18000d56b  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d574  lea     rdx, aAddinterfaceto; "AddInterfaceToWanarp: Unable to get dev"...
0x18000d57b  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d584  lea     rcx, [rsp+0D28h+var_838]
0x18000d58c  call    FormatRRASErrorString
0x18000d591  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000d598  jz      loc_18000DB52
0x18000d59e  lea     rax, [rsp+0D28h+var_868]
0x18000d5a6  test    rsi, rsi
0x18000d5a9  mov     qword ptr [rsp+0D28h+IoControlCode], rax
0x18000d5ae  lea     r9, [rsp+0D28h+var_CB8]
0x18000d5b3  mov     rax, [rbx+48h]
0x18000d5b7  lea     r8, [rsp+0D28h+var_838]
0x18000d5bf  cmovnz  r9, rsi
0x18000d5c3  mov     [rsp+0D28h+IoStatusBlock], rax
0x18000d5c8  lea     rdx, RasRtrMgrParamTraceError
0x18000d5cf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d5d6  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d5db  jmp     loc_18000DB52
0x18000d5e0  mov     eax, [rsp+0D28h+var_878]
0x18000d5e7  lea     r9, aRasDialInInter; "RAS (Dial In) Interface"
0x18000d5ee  lea     r8, aSD; "%s - %d"
0x18000d5f5  mov     dword ptr [rsp+0D28h+IoStatusBlock], eax
0x18000d5f9  mov     edx, 100h; BufferCount
0x18000d5fe  lea     rcx, [rsp+0D28h+Buffer]; Buffer
0x18000d606  call    cs:__imp_swprintf_s
0x18000d60c  jmp     loc_18000D947
0x18000d611  mov     edi, r14d
0x18000d614  mov     [rsp+0D28h+var_A98], r14
0x18000d61c  jmp     loc_18000D947
0x18000d621  mov     rcx, [rbx+0B8h]
0x18000d628  lea     rdx, [rsp+0D28h+var_A90]
0x18000d630  mov     rax, cs:GetInterfaceDeviceGuid
0x18000d637  mov     [rsp+0D28h+var_CD0], r14
0x18000d63c  mov     [rsp+0D28h+var_CA4], r14d
0x18000d644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d649  mov     edi, eax
0x18000d64b  test    eax, eax
0x18000d64d  jz      short loc_18000D6B8
0x18000d64f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d656  jge     loc_18000DCFD
0x18000d65c  mov     r8, [rbx+48h]
0x18000d660  lea     rdx, aAddinterfaceto_15; "AddInterfaceToWanarp: Unable to query t"...
0x18000d667  mov     r9d, eax
0x18000d66a  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d673  lea     rcx, [rsp+0D28h+var_838]
0x18000d67b  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d684  call    FormatRRASErrorString
0x18000d689  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d690  jge     loc_18000DCFD
0x18000d696  lea     rax, [rbx+2B0h]
0x18000d69d  mov     rcx, rsi
0x18000d6a0  test    rax, rax
0x18000d6a3  lea     r9, [rsp+0D28h+var_CB8]
0x18000d6a8  lea     rdx, RasRtrmgrParamTraceInfo
0x18000d6af  cmovnz  r9, rax
0x18000d6b3  jmp     loc_18000DCDA
0x18000d6b8  mov     r8, [rbx+48h]; pszSrc
0x18000d6bc  lea     rcx, [rsp+0D28h+Buffer]; pszDest
0x18000d6c4  mov     edx, 200h; cbDest
0x18000d6c9  call    StringCbCopyW
0x18000d6ce  mov     r11d, [rbx+204h]
0x18000d6d5  lea     r8, [rsp+0D28h+var_CD0]
0x18000d6da  mov     rcx, [rbx+48h]
0x18000d6de  neg     r11d
0x18000d6e1  mov     rax, cs:GetInterfaceHandle
0x18000d6e8  sbb     esi, esi
0x18000d6ea  and     esi, 36h
0x18000d6ed  add     esi, 21h ; '!'
0x18000d6f0  mov     edx, esi
0x18000d6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6f7  mov     edi, eax
0x18000d6f9  test    eax, eax
0x18000d6fb  jnz     loc_18000D7FF
0x18000d701  mov     rcx, [rsp+0D28h+var_CD0]
0x18000d706  lea     rax, [rcx-1]
0x18000d70a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d70e  ja      loc_18000D7E9
0x18000d714  call    InterfaceLookupByICBSeqNumber
0x18000d719  test    rax, rax
0x18000d71c  jz      loc_18000D7D0
0x18000d722  mov     rcx, [rax+0A0h]
0x18000d729  mov     [rsp+0D28h+var_A98], rcx
0x18000d731  mov     rcx, [rax+0A0h]
0x18000d738  mov     [rbx+0A0h], rcx
0x18000d73f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d746  jge     loc_18000D947
0x18000d74c  mov     r9d, [rbx+10h]
0x18000d750  lea     rdx, aInfoAddinterfa; "INFO: AddInterfaceToWanarp: InterfaceLu"...
0x18000d757  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d760  lea     rcx, [rsp+0D28h+var_838]
0x18000d768  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d771  mov     r8d, [rax+10h]
0x18000d775  call    FormatRRASErrorString
0x18000d77a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d781  jge     loc_18000D947
0x18000d787  lea     rax, [rbx+2B0h]
0x18000d78e  test    rax, rax
0x18000d791  lea     r9, [rsp+0D28h+var_CB8]
0x18000d796  lea     r8, [rsp+0D28h+var_838]
0x18000d79e  cmovnz  r9, rax
0x18000d7a2  lea     rdx, RasRtrmgrParamTraceInfo
0x18000d7a9  lea     rax, [rsp+0D28h+var_868]
0x18000d7b1  mov     qword ptr [rsp+0D28h+IoControlCode], rax
0x18000d7b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7bd  mov     rax, [rbx+48h]
0x18000d7c1  mov     [rsp+0D28h+IoStatusBlock], rax
0x18000d7c6  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d7cb  jmp     loc_18000D947
0x18000d7d0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d7d7  jge     loc_18000DCFD
0x18000d7dd  lea     rdx, aAddinterfaceto_2; "AddInterfaceToWANARP: InterfaceLookup f"...
0x18000d7e4  jmp     loc_18000DC8A
0x18000d7e9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d7f0  jge     loc_18000D88A
0x18000d7f6  lea     rdx, aInfo1Addinterf; "INFO:1 AddInterfaceToWanarp: This is th"...
0x18000d7fd  jmp     short loc_18000D81A
0x18000d7ff  cmp     eax, 3AA4h
0x18000d804  jnz     loc_18000DC7A
0x18000d80a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d811  jge     short loc_18000D88A
0x18000d813  lea     rdx, aInfo2Addinterf; "INFO:2 AddInterfaceToWanarp: This is th"...
0x18000d81a  mov     r8, [rbx+48h]
0x18000d81e  lea     rcx, [rsp+0D28h+var_838]
0x18000d826  mov     word ptr [rsp+0D28h+var_838], r14w
0x18000d82f  mov     word ptr [rsp+0D28h+var_868], r14w
0x18000d838  call    FormatRRASErrorString
0x18000d83d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d844  jge     short loc_18000D88A
0x18000d846  lea     rax, [rbx+2B0h]
0x18000d84d  test    rax, rax
0x18000d850  lea     r9, [rsp+0D28h+var_CB8]
0x18000d855  lea     r8, [rsp+0D28h+var_838]
0x18000d85d  cmovnz  r9, rax
0x18000d861  lea     rdx, RasRtrmgrParamTraceInfo
0x18000d868  lea     rax, [rsp+0D28h+var_868]
0x18000d870  mov     qword ptr [rsp+0D28h+IoControlCode], rax
0x18000d875  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d87c  mov     rax, [rbx+48h]
0x18000d880  mov     [rsp+0D28h+IoStatusBlock], rax
0x18000d885  call    McTemplateU0zjzz_EventWriteTransfer
0x18000d88a  lea     rsi, [rbx+2B0h]
0x18000d891  mov     edx, r15d
0x18000d894  mov     r8, rsi
0x18000d897  lea     r9, [rsp+0D28h+var_CD8]
0x18000d89c  call    AllocInterfaceLuidIndex
0x18000d8a1  mov     edi, eax
0x18000d8a3  test    eax, eax
0x18000d8a5  jz      short loc_18000D8FC
0x18000d8a7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000d8ae  jge     loc_18000DCFD
0x18000d8b4  mov     r8, [rbx+48h]
0x18000d8b8  lea     rdx, aAddinterfaceto_13; "AddInterfaceToWANARP: Unable to allocat"...
0x18000d8bf  lea     rcx, [rsp+0D28h+var_838]
  ... truncated ...
```
