# RasLineOpen

- ea: `0x180087a2c`
- end: `0x1800882c3`
- name: `RasLineOpen`
- size: `2199`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180026e38`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x180087a2c`
- `0x1800882cc`
- `0x1800884f8`
- `0x180089a9c`
- `0x18008a084`
- `0x18008c5e6`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180087c4f`
- `KERNEL32!ReleaseMutex` at `0x180087c4f`
- `KERNEL32!GetProcessHeap` at `0x180087b37`
- `KERNEL32!GetProcessHeap` at `0x180087c5a`
- `KERNEL32!GetProcessHeap` at `0x180087d7a`
- `KERNEL32!GetProcessHeap` at `0x18008823c`
- `KERNEL32!GetProcessHeap` at `0x180087b37`
- `KERNEL32!GetProcessHeap` at `0x180087c5a`
- `KERNEL32!GetProcessHeap` at `0x180087d7a`
- `KERNEL32!GetProcessHeap` at `0x18008823c`
- `KERNEL32!HeapAlloc` at `0x180087b48`
- `KERNEL32!HeapAlloc` at `0x18008824c`
- `KERNEL32!HeapAlloc` at `0x180087b48`
- `KERNEL32!HeapAlloc` at `0x18008824c`
- `KERNEL32!WaitForSingleObject` at `0x180087a9f`
- `KERNEL32!WaitForSingleObject` at `0x180087a9f`
- `KERNEL32!HeapFree` at `0x180087c68`
- `KERNEL32!HeapFree` at `0x180087d88`
- `KERNEL32!HeapFree` at `0x180087c68`
- `KERNEL32!HeapFree` at `0x180087d88`
- `rtutils!TracePrintfA` at `0x180087b15`
- `rtutils!TracePrintfA` at `0x180087c21`
- `rtutils!TracePrintfA` at `0x180087cb6`
- `rtutils!TracePrintfA` at `0x180087d4a`
- `rtutils!TracePrintfA` at `0x180087ded`
- `rtutils!TracePrintfA` at `0x180087e70`
- `rtutils!TracePrintfA` at `0x180087f3a`
- `rtutils!TracePrintfA` at `0x180087f5f`
- `rtutils!TracePrintfA` at `0x180087fd3`
- `rtutils!TracePrintfA` at `0x180088114`
- `rtutils!TracePrintfA` at `0x1800881be`
- `rtutils!TracePrintfA` at `0x18008822e`
- `rtutils!TracePrintfA` at `0x180087b15`
- `rtutils!TracePrintfA` at `0x180087c21`
- `rtutils!TracePrintfA` at `0x180087cb6`
- `rtutils!TracePrintfA` at `0x180087d4a`
- `rtutils!TracePrintfA` at `0x180087ded`
- `rtutils!TracePrintfA` at `0x180087e70`
- `rtutils!TracePrintfA` at `0x180087f3a`
- `rtutils!TracePrintfA` at `0x180087f5f`
- `rtutils!TracePrintfA` at `0x180087fd3`
- `rtutils!TracePrintfA` at `0x180088114`
- `rtutils!TracePrintfA` at `0x1800881be`
- `rtutils!TracePrintfA` at `0x18008822e`

## string_xrefs

- `0x180087b0e`: `RasLineOpen: WaitForSingleObject failed with error 0x%x`
- `0x180087ac3`: `RasLineOpen: WaitForSingleObject failed with error 0x%x`
- `0x180087c10`: `RasLineOpen: Line for device 0x%x already open with handle 0x%x and opened media modes 0x%x`
- `0x180087bc3`: `RasLineOpen: Line for device 0x%x already open with handle 0x%x and opened media modes 0x%x`
- `0x180087caf`: `RasLineOpen: Failed to create line obj`
- `0x180087b81`: `RasLineOpen: Failed to create line obj`
- `0x180087d43`: `RasLineOpen: PrepareSyncRequest failed with error (0x%x)`
- `0x180087d05`: `RasLineOpen: PrepareSyncRequest failed with error (0x%x)`
- `0x180087de6`: `RasLineOpen: Failed to map line object (%p) to handle`
- `0x180087da8`: `RasLineOpen: Failed to map line object (%p) to handle`
- `0x180087e69`: `RasLineOpen: SyncDriverRequest(OID_TAPI_OPEN) failed with error (0x%x)`
- `0x180087e37`: `RasLineOpen: SyncDriverRequest(OID_TAPI_OPEN) failed with error (0x%x)`
- `0x180087f30`: `RasLineOpen: RasTapi Line handle (%p)`
- `0x180087e99`: `RasLineOpen: RasTapi Line handle (%p)`
- `0x180087f55`: `RasLineOpen: NDProxy Line handle (%p)`
- `0x180087ee9`: `RasLineOpen: NDProxy Line handle (%p)`
- `0x180087fc9`: `RasLineOpen: MediaType(%ld)`
- `0x180087f84`: `RasLineOpen: MediaType(%ld)`
- `0x1800880eb`: `RasLineOpen: Guid %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x`
- `0x180088048`: `RasLineOpen: Guid %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x`
- `0x1800881b4`: `RasLineOpen: RasLineSetDefaultMediaDetection failed with error (0x%x) in setting media modes (0x%x)`
- `0x18008818a`: `RasLineOpen: RasLineSetDefaultMediaDetection failed with error (0x%x) in setting media modes (0x%x)`
- `0x180088227`: `RasLineOpen: Media modes = 0x%x`
- `0x1800881e6`: `RasLineOpen: Media modes = 0x%x`
- `0x180088291`: `RasLineOpen: Failed to create PRAS_LINE obj`
- `0x180088276`: `RasLineOpen: Failed to create PRAS_LINE obj`

## pseudocode

```c
__int64 __fastcall RasLineOpen(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // esi
  char *v6; // r13
  unsigned int v7; // r12d
  DWORD v9; // eax
  unsigned int v10; // ebx
  _DWORD *i; // r14
  HANDLE ProcessHeap; // rax
  char *v13; // rax
  char *v14; // rdi
  __int64 v15; // rdx
  const wchar_t *v16; // r8
  int v17; // edi
  _DWORD *v18; // rax
  HANDLE v19; // rax
  unsigned int v21; // eax
  HANDLE v22; // rax
  unsigned int v23; // eax
  DWORD v24; // r15d
  char *v25; // r9
  _DWORD *v26; // rbx
  unsigned int v27; // eax
  HANDLE v28; // rax
  unsigned int v29; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-8Ch]
  LPVOID lpInBuffer; // [rsp+78h] [rbp-88h] BYREF
  char *v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h] BYREF
  char v35[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v5 = a1;
  v33 = a5;
  v6 = 0;
  v30 = a1;
  v7 = 0;
  v34 = 0;
  lpInBuffer = 0;
  v29 = 0;
  memset_0(v35, 0, sizeof(v35));
  v9 = WaitForSingleObject(g_hRasOpenLinesMutex, 0xFFFFFFFF);
  v10 = v9;
  if ( v9 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"RasLineOpen: WaitForSingleObject failed with error 0x%x", v9);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineOpen: WaitForSingleObject failed with error 0x%x", v9);
    }
    return v10;
  }
  for ( i = g_pRasOpenLines; ; i = *(_DWORD **)i )
  {
    if ( !i )
    {
      ProcessHeap = GetProcessHeap();
      v13 = (char *)HeapAlloc(ProcessHeap, 8u, 0x40u);
      v32 = v13;
      v14 = v13;
      if ( !v13 )
      {
        v10 = 14;
        if ( gIsndpspEtwTracingAvailable )
        {
          v15 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
          if ( !*((_QWORD *)&xmmword_1800C9BE0 + 1) )
            goto LABEL_24;
          v16 = L"RasLineOpen: Failed to create line obj";
          goto LABEL_15;
        }
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineOpen: Failed to create line obj");
        goto LABEL_24;
      }
      *(_DWORD *)v13 = 1263290702;
      *((_DWORD *)v13 + 1) = v5;
      *((_QWORD *)v13 + 4) = a4;
      v21 = PrepareSyncRequest(117637399, v5, 44, &lpInBuffer);
      v10 = v21;
      if ( v21 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"RasLineOpen: PrepareSyncRequest failed with error (0x%x)", v21);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "RasLineOpen: PrepareSyncRequest failed with error (0x%x)", v21);
        }
        v6 = (char *)lpInBuffer;
        goto LABEL_24;
      }
      v6 = (char *)lpInBuffer;
      *((_DWORD *)lpInBuffer + 13) = v5;
      v10 = OpenObjHandle(v14, &v29);
      if ( v10 )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v14);
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"RasLineOpen: Failed to map line object (%p) to handle", v14);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "RasLineOpen: Failed to map line object (%p) to handle", v14);
        }
        v7 = v29;
        goto LABEL_24;
      }
      v7 = v29;
      *((_QWORD *)v6 + 7) = v29;
      v23 = SyncDriverRequest(0x8FFF23C8, v6);
      v10 = v23;
      if ( v23 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(&v34, L"RasLineOpen: SyncDriverRequest(OID_TAPI_OPEN) failed with error (0x%x)", v23);
            goto LABEL_50;
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "RasLineOpen: SyncDriverRequest(OID_TAPI_OPEN) failed with error (0x%x)", v23);
        }
        goto LABEL_24;
      }
      i = 0;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(&v34, L"RasLineOpen: RasTapi Line handle (%p)", *((_QWORD *)v6 + 7));
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
        }
      }
      else
      {
        v24 = dwTraceId;
        if ( dwTraceId == -1 )
          goto LABEL_64;
        TracePrintfA(dwTraceId, "RasLineOpen: RasTapi Line handle (%p)", *((const void **)v6 + 7));
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(&v34, L"RasLineOpen: NDProxy Line handle (%p)", *((_QWORD *)v6 + 8));
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
        }
      }
      else
      {
        v24 = dwTraceId;
        if ( dwTraceId == -1 )
          goto LABEL_64;
        TracePrintfA(dwTraceId, "RasLineOpen: NDProxy Line handle (%p)", *((const void **)v6 + 8));
      }
      v24 = dwTraceId;
LABEL_64:
      v25 = v6 + 72;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800C9BE0 )
          goto LABEL_70;
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"RasLineOpen: MediaType(%ld)", *((unsigned int *)v6 + 22));
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
      }
      else
      {
        if ( v24 == -1 )
          goto LABEL_76;
        TracePrintfA(v24, "RasLineOpen: MediaType(%ld)", *((_DWORD *)v6 + 22));
      }
      v24 = dwTraceId;
      v25 = v6 + 72;
LABEL_70:
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          v26 = v6 + 72;
          FormatRRASErrorString(
            &v34,
            L"RasLineOpen: Guid %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x",
            *((unsigned int *)v6 + 18),
            *((unsigned __int16 *)v25 + 2),
            *((unsigned __int16 *)v25 + 3),
            (unsigned __int8)v25[8],
            (unsigned __int8)v25[9],
            (unsigned __int8)v25[10],
            (unsigned __int8)v25[11],
            (unsigned __int8)v25[12],
            (unsigned __int8)v25[13],
            (unsigned __int8)v25[14],
            (unsigned __int8)v25[15]);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
          v14 = v32;
          v5 = v30;
        }
        else
        {
          v26 = v6 + 72;
        }
        goto LABEL_77;
      }
      if ( v24 != -1 )
      {
        v26 = v6 + 72;
        TracePrintfA(
          v24,
          "RasLineOpen: Guid %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x",
          *((_DWORD *)v6 + 18),
          *((unsigned __int16 *)v25 + 2),
          *((unsigned __int16 *)v25 + 3),
          (unsigned __int8)v25[8],
          (unsigned __int8)v25[9],
          (unsigned __int8)v25[10],
          (unsigned __int8)v25[11],
          (unsigned __int8)v25[12],
          (unsigned __int8)v25[13],
          (unsigned __int8)v25[14],
          (unsigned __int8)v25[15]);
        v14 = v32;
        v5 = v30;
LABEL_77:
        memmove_0(v14 + 40, v26, 0x10u);
        *((_DWORD *)v14 + 14) = v26[4];
        *((_QWORD *)v14 + 2) = *((_QWORD *)v6 + 8);
        *((_DWORD *)v14 + 2) = v7;
        v17 = 0;
        goto LABEL_78;
      }
LABEL_76:
      v26 = v6 + 72;
      goto LABEL_77;
    }
    if ( v5 == i[3] )
      break;
  }
  v7 = i[2];
  v17 = 1;
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v34) = 0;
      FormatRRASErrorString(
        &v34,
        L"RasLineOpen: Line for device 0x%x already open with handle 0x%x and opened media modes 0x%x",
        v5,
        v7,
        i[4]);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(
      dwTraceId,
      "RasLineOpen: Line for device 0x%x already open with handle 0x%x and opened media modes 0x%x",
      v5,
      v7,
      i[4]);
  }
  if ( i[4] == 258 )
  {
LABEL_22:
    ++i[5];
    goto LABEL_23;
  }
LABEL_78:
  v27 = RasLineSetDefaultMediaDetection(v7);
  v10 = v27;
  if ( v27 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(
          &v34,
          L"RasLineOpen: RasLineSetDefaultMediaDetection failed with error (0x%x) in setting media modes (0x%x)",
          v27,
          258);
LABEL_50:
        v15 = xmmword_1800C9BE0;
        v16 = (const wchar_t *)&v34;
LABEL_15:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v15, v16);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(
        dwTraceId,
        "RasLineOpen: RasLineSetDefaultMediaDetection failed with error (0x%x) in setting media modes (0x%x)",
        v27,
        258);
    }
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, L"RasLineOpen: Media modes = 0x%x", 258);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineOpen: Media modes = 0x%x", 258);
    }
    if ( v17 )
      goto LABEL_22;
    v28 = GetProcessHeap();
    i = HeapAlloc(v28, 8u, 0x18u);
    if ( i )
    {
      *(_QWORD *)i = g_pRasOpenLines;
      i[3] = v5;
      i[2] = v7;
      i[5] = 1;
      g_pRasOpenLines = i;
LABEL_23:
      v18 = (_DWORD *)v33;
      i[4] = 258;
      *v18 = v7;
    }
    else
    {
      v10 = 14;
      if ( gIsndpspEtwTracingAvailable )
      {
        v15 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
        if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
        {
          v16 = L"RasLineOpen: Failed to create PRAS_LINE obj";
          goto LABEL_15;
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineOpen: Failed to create PRAS_LINE obj");
      }
    }
  }
LABEL_24:
  ReleaseMutex(g_hRasOpenLinesMutex);
  if ( v6 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v6);
  }
  if ( v10 && v7 )
    CloseObjHandle(v7);
  return v10;
}

```

## disassembly

```asm
0x180087a2c  push    rbp
0x180087a2e  push    rbx
0x180087a2f  push    rsi
0x180087a30  push    rdi
0x180087a31  push    r12
0x180087a33  push    r13
0x180087a35  push    r14
0x180087a37  push    r15
0x180087a39  lea     rbp, [rsp-7A8h]
0x180087a41  sub     rsp, 8A8h
0x180087a48  mov     rax, cs:__security_cookie
0x180087a4f  xor     rax, rsp
0x180087a52  mov     [rbp+7E0h+var_50], rax
0x180087a59  mov     rax, [rbp+7E0h+arg_20]
0x180087a60  mov     esi, ecx
0x180087a62  mov     [rbp+7E0h+var_858], rax
0x180087a66  xor     r13d, r13d
0x180087a69  xor     eax, eax
0x180087a6b  mov     [rsp+8E0h+var_86C], ecx
0x180087a6f  xor     r12d, r12d
0x180087a72  mov     [rbp+7E0h+var_850], eax
0x180087a75  xor     edx, edx; Val
0x180087a77  mov     [rsp+8E0h+lpInBuffer], r13
0x180087a7c  mov     r8d, 7FCh; Size
0x180087a82  mov     [rsp+8E0h+var_870], r12d
0x180087a87  lea     rcx, [rbp+7E0h+var_84C]; void *
0x180087a8b  mov     r15, r9
0x180087a8e  call    memset_0
0x180087a93  mov     rcx, cs:g_hRasOpenLinesMutex; hHandle
0x180087a9a  or      edi, 0FFFFFFFFh
0x180087a9d  mov     edx, edi; dwMilliseconds
0x180087a9f  call    cs:__imp_WaitForSingleObject
0x180087aa5  mov     ebx, eax
0x180087aa7  test    eax, eax
0x180087aa9  jz      short loc_180087B20
0x180087aab  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180087ab2  jz      short loc_180087AFD
0x180087ab4  cmp     qword ptr cs:xmmword_1800C9BE0, r12
0x180087abb  jz      loc_180087C7F
0x180087ac1  xor     ecx, ecx
0x180087ac3  lea     rdx, aRaslineopenWai_0; "RasLineOpen: WaitForSingleObject failed"...
0x180087aca  mov     word ptr [rbp+7E0h+var_850], cx
0x180087ace  mov     r8d, eax
0x180087ad1  lea     rcx, [rbp+7E0h+var_850]
0x180087ad5  call    FormatRRASErrorString
0x180087ada  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087ae1  lea     r8, [rbp+7E0h+var_850]
0x180087ae5  mov     rcx, cs:gNdpspEtwContext
0x180087aec  mov     rax, cs:gNdpspTemplateFunc
0x180087af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087af8  jmp     loc_180087C7F
0x180087afd  mov     ecx, cs:dwTraceId; dwTraceID
0x180087b03  cmp     ecx, edi
0x180087b05  jz      loc_180087C7F
0x180087b0b  mov     r8d, ebx
0x180087b0e  lea     rdx, aRaslineopenWai; "RasLineOpen: WaitForSingleObject failed"...
0x180087b15  call    cs:__imp_TracePrintfA
0x180087b1b  jmp     loc_180087C7F
0x180087b20  mov     r14, cs:g_pRasOpenLines
0x180087b27  jmp     short loc_180087B32
0x180087b29  cmp     esi, [r14+0Ch]
0x180087b2d  jz      short loc_180087BA0
0x180087b2f  mov     r14, [r14]
0x180087b32  test    r14, r14
0x180087b35  jnz     short loc_180087B29
0x180087b37  call    cs:__imp_GetProcessHeap
0x180087b3d  mov     rcx, rax; hHeap
0x180087b40  lea     edx, [r14+8]; dwFlags
0x180087b44  lea     r8d, [r14+40h]; dwBytes
0x180087b48  call    cs:__imp_HeapAlloc
0x180087b4e  mov     [rbp+7E0h+var_860], rax
0x180087b52  mov     rdi, rax
0x180087b55  test    rax, rax
0x180087b58  jnz     loc_180087CBE
0x180087b5e  xor     r15d, r15d
0x180087b61  lea     ebx, [rax+0Eh]
0x180087b64  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087b6b  jz      loc_180087CA4
0x180087b71  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180087b78  test    rdx, rdx
0x180087b7b  jz      loc_180087C48
0x180087b81  lea     r8, aRaslineopenFai_2; "RasLineOpen: Failed to create line obj"
0x180087b88  mov     rcx, cs:gNdpspEtwContext
0x180087b8f  mov     rax, cs:gNdpspTemplateFunc
0x180087b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b9b  jmp     loc_180087C48
0x180087ba0  mov     r12d, [r14+8]
0x180087ba4  xor     r15d, r15d
0x180087ba7  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087bae  mov     edi, 1
0x180087bb3  jz      short loc_180087C01
0x180087bb5  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087bbc  jz      short loc_180087C27
0x180087bbe  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087bc3  lea     rdx, aRaslineopenLin; "RasLineOpen: Line for device 0x%x alrea"...
0x180087bca  mov     eax, [r14+10h]
0x180087bce  lea     rcx, [rbp+7E0h+var_850]
0x180087bd2  mov     r9d, r12d
0x180087bd5  mov     [rsp+8E0h+var_8C0], eax
0x180087bd9  mov     r8d, esi
0x180087bdc  call    FormatRRASErrorString
0x180087be1  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087be8  lea     r8, [rbp+7E0h+var_850]
0x180087bec  mov     rcx, cs:gNdpspEtwContext
0x180087bf3  mov     rax, cs:gNdpspTemplateFunc
0x180087bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087bff  jmp     short loc_180087C27
0x180087c01  mov     ecx, cs:dwTraceId; dwTraceID
0x180087c07  cmp     ecx, 0FFFFFFFFh
0x180087c0a  jz      short loc_180087C27
0x180087c0c  mov     eax, [r14+10h]
0x180087c10  lea     rdx, aRaslineopenLin_0; "RasLineOpen: Line for device 0x%x alrea"...
0x180087c17  mov     r9d, r12d
0x180087c1a  mov     [rsp+8E0h+var_8C0], eax
0x180087c1e  mov     r8d, esi
0x180087c21  call    cs:__imp_TracePrintfA
0x180087c27  cmp     dword ptr [r14+10h], 102h
0x180087c2f  jnz     loc_180088158
0x180087c35  inc     dword ptr [r14+14h]
0x180087c39  mov     rax, [rbp+7E0h+var_858]
0x180087c3d  mov     dword ptr [r14+10h], 102h
0x180087c45  mov     [rax], r12d
0x180087c48  mov     rcx, cs:g_hRasOpenLinesMutex; hMutex
0x180087c4f  call    cs:__imp_ReleaseMutex
0x180087c55  test    r13, r13
0x180087c58  jz      short loc_180087C6E
0x180087c5a  call    cs:__imp_GetProcessHeap
0x180087c60  mov     r8, r13; lpMem
0x180087c63  xor     edx, edx; dwFlags
0x180087c65  mov     rcx, rax; hHeap
0x180087c68  call    cs:__imp_HeapFree
0x180087c6e  test    ebx, ebx
0x180087c70  jz      short loc_180087C7F
0x180087c72  test    r12d, r12d
0x180087c75  jz      short loc_180087C7F
0x180087c77  mov     ecx, r12d
0x180087c7a  call    CloseObjHandle
0x180087c7f  mov     eax, ebx
0x180087c81  mov     rcx, [rbp+7E0h+var_50]
0x180087c88  xor     rcx, rsp; StackCookie
0x180087c8b  call    __security_check_cookie
0x180087c90  add     rsp, 8A8h
0x180087c97  pop     r15
0x180087c99  pop     r14
0x180087c9b  pop     r13
0x180087c9d  pop     r12
0x180087c9f  pop     rdi
0x180087ca0  pop     rsi
0x180087ca1  pop     rbx
0x180087ca2  pop     rbp
0x180087ca3  retn
0x180087ca4  mov     ecx, cs:dwTraceId; dwTraceID
0x180087caa  cmp     ecx, 0FFFFFFFFh
0x180087cad  jz      short loc_180087C48
0x180087caf  lea     rdx, aRaslineopenFai_0; "RasLineOpen: Failed to create line obj"
0x180087cb6  call    cs:__imp_TracePrintfA
0x180087cbc  jmp     short loc_180087C48
0x180087cbe  lea     r9, [rsp+8E0h+lpInBuffer]
0x180087cc3  mov     dword ptr [rax], 4B4C494Eh
0x180087cc9  mov     r8d, 2Ch ; ','
0x180087ccf  mov     [rax+4], esi
0x180087cd2  mov     edx, esi
0x180087cd4  mov     [rax+20h], r15
0x180087cd8  mov     ecx, 7030117h
0x180087cdd  call    PrepareSyncRequest
0x180087ce2  xor     r15d, r15d
0x180087ce5  mov     ebx, eax
0x180087ce7  test    eax, eax
0x180087ce9  jz      short loc_180087D5A
0x180087ceb  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087cf2  jz      short loc_180087D35
0x180087cf4  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087cfb  jz      short loc_180087D50
0x180087cfd  mov     r8d, eax
0x180087d00  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087d05  lea     rdx, aRaslineopenPre_0; "RasLineOpen: PrepareSyncRequest failed "...
0x180087d0c  lea     rcx, [rbp+7E0h+var_850]
0x180087d10  call    FormatRRASErrorString
0x180087d15  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087d1c  lea     r8, [rbp+7E0h+var_850]
0x180087d20  mov     rcx, cs:gNdpspEtwContext
0x180087d27  mov     rax, cs:gNdpspTemplateFunc
0x180087d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d33  jmp     short loc_180087D50
0x180087d35  mov     ecx, cs:dwTraceId; dwTraceID
0x180087d3b  cmp     ecx, 0FFFFFFFFh
0x180087d3e  jz      short loc_180087D50
0x180087d40  mov     r8d, eax
0x180087d43  lea     rdx, aRaslineopenPre; "RasLineOpen: PrepareSyncRequest failed "...
0x180087d4a  call    cs:__imp_TracePrintfA
0x180087d50  mov     r13, [rsp+8E0h+lpInBuffer]
0x180087d55  jmp     loc_180087C48
0x180087d5a  mov     r13, [rsp+8E0h+lpInBuffer]
0x180087d5f  lea     rdx, [rsp+8E0h+var_870]
0x180087d64  mov     rcx, rdi
0x180087d67  mov     [r13+34h], esi
0x180087d6b  call    OpenObjHandle
0x180087d70  mov     ebx, eax
0x180087d72  test    eax, eax
0x180087d74  jz      loc_180087DFD
0x180087d7a  call    cs:__imp_GetProcessHeap
0x180087d80  mov     r8, rdi; lpMem
0x180087d83  xor     edx, edx; dwFlags
0x180087d85  mov     rcx, rax; hHeap
0x180087d88  call    cs:__imp_HeapFree
0x180087d8e  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087d95  jz      short loc_180087DD8
0x180087d97  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087d9e  jz      short loc_180087DF3
0x180087da0  mov     r8, rdi
0x180087da3  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087da8  lea     rdx, aRaslineopenFai_3; "RasLineOpen: Failed to map line object "...
0x180087daf  lea     rcx, [rbp+7E0h+var_850]
0x180087db3  call    FormatRRASErrorString
0x180087db8  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087dbf  lea     r8, [rbp+7E0h+var_850]
0x180087dc3  mov     rcx, cs:gNdpspEtwContext
0x180087dca  mov     rax, cs:gNdpspTemplateFunc
0x180087dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087dd6  jmp     short loc_180087DF3
0x180087dd8  mov     ecx, cs:dwTraceId; dwTraceID
0x180087dde  cmp     ecx, 0FFFFFFFFh
0x180087de1  jz      short loc_180087DF3
0x180087de3  mov     r8, rdi
0x180087de6  lea     rdx, aRaslineopenFai_4; "RasLineOpen: Failed to map line object "...
0x180087ded  call    cs:__imp_TracePrintfA
0x180087df3  mov     r12d, [rsp+8E0h+var_870]
0x180087df8  jmp     loc_180087C48
0x180087dfd  mov     r12d, [rsp+8E0h+var_870]
0x180087e02  mov     rdx, r13; lpInBuffer
0x180087e05  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180087e0a  mov     [r13+38h], r12
0x180087e0e  call    SyncDriverRequest
0x180087e13  mov     ebx, eax
0x180087e15  test    eax, eax
0x180087e17  jz      short loc_180087E7B
0x180087e19  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087e20  jz      short loc_180087E57
0x180087e22  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087e29  jz      loc_180087C48
0x180087e2f  mov     r8d, eax
0x180087e32  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087e37  lea     rdx, aRaslineopenSyn_0; "RasLineOpen: SyncDriverRequest(OID_TAPI"...
0x180087e3e  lea     rcx, [rbp+7E0h+var_850]
0x180087e42  call    FormatRRASErrorString
0x180087e47  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087e4e  lea     r8, [rbp+7E0h+var_850]
0x180087e52  jmp     loc_180087B88
0x180087e57  mov     ecx, cs:dwTraceId; dwTraceID
0x180087e5d  cmp     ecx, 0FFFFFFFFh
0x180087e60  jz      loc_180087C48
0x180087e66  mov     r8d, eax
0x180087e69  lea     rdx, aRaslineopenSyn; "RasLineOpen: SyncDriverRequest(OID_TAPI"...
0x180087e70  call    cs:__imp_TracePrintfA
0x180087e76  jmp     loc_180087C48
0x180087e7b  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087e82  mov     r14, r15
0x180087e85  jz      loc_180087F1D
0x180087e8b  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087e92  jz      short loc_180087ECB
0x180087e94  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087e99  lea     rdx, aRaslineopenRas; "RasLineOpen: RasTapi Line handle (%p)"
0x180087ea0  mov     r8, [r13+38h]
0x180087ea4  lea     rcx, [rbp+7E0h+var_850]
0x180087ea8  call    FormatRRASErrorString
0x180087ead  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087eb4  lea     r8, [rbp+7E0h+var_850]
0x180087eb8  mov     rcx, cs:gNdpspEtwContext
0x180087ebf  mov     rax, cs:gNdpspTemplateFunc
0x180087ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ecb  or      ebx, 0FFFFFFFFh
0x180087ece  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180087ed5  jz      short loc_180087F45
0x180087ed7  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180087ede  jz      loc_180087F65
0x180087ee4  mov     word ptr [rbp+7E0h+var_850], r15w
0x180087ee9  lea     rdx, aRaslineopenNdp; "RasLineOpen: NDProxy Line handle (%p)"
0x180087ef0  mov     r8, [r13+40h]
0x180087ef4  lea     rcx, [rbp+7E0h+var_850]
0x180087ef8  call    FormatRRASErrorString
0x180087efd  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180087f04  lea     r8, [rbp+7E0h+var_850]
0x180087f08  mov     rcx, cs:gNdpspEtwContext
0x180087f0f  mov     rax, cs:gNdpspTemplateFunc
0x180087f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f1b  jmp     short loc_180087F65
0x180087f1d  mov     r15d, cs:dwTraceId
0x180087f24  or      ebx, 0FFFFFFFFh
0x180087f27  cmp     r15d, ebx
0x180087f2a  jz      short loc_180087F6C
0x180087f2c  mov     r8, [r13+38h]
0x180087f30  lea     rdx, aRaslineopenRas_2; "RasLineOpen: RasTapi Line handle (%p)"
0x180087f37  mov     ecx, r15d; dwTraceID
0x180087f3a  call    cs:__imp_TracePrintfA
0x180087f40  xor     r15d, r15d
0x180087f43  jmp     short loc_180087ECE
0x180087f45  mov     r15d, cs:dwTraceId
0x180087f4c  cmp     r15d, ebx
0x180087f4f  jz      short loc_180087F6C
0x180087f51  mov     r8, [r13+40h]
  ... truncated ...
```
