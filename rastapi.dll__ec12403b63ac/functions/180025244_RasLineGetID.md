# RasLineGetID

- ea: `0x180025244`
- end: `0x1800257dc`
- name: `RasLineGetID`
- size: `1432`
- prototype: `__int64 __fastcall(unsigned int, int, unsigned int, int, wchar_t *String1, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x18000f108`
- `0x1800131f0`

## callees

- `0x18002251c`
- `0x180025244`
- `0x180026c4c`
- `0x180027270`
- `0x180027a10`
- `0x180027d38`
- `0x180028b5c`
- `0x180029130`
- `0x180029266`
- `0x180029272`
- `0x18002927e`
- `0x18002928a`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002558c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002558c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002559a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002559a`
- `rtutils!TracePrintfA` at `0x180025359`
- `rtutils!TracePrintfA` at `0x1800253c6`
- `rtutils!TracePrintfA` at `0x18002549f`
- `rtutils!TracePrintfA` at `0x1800254eb`
- `rtutils!TracePrintfA` at `0x180025601`
- `rtutils!TracePrintfA` at `0x180025699`
- `rtutils!TracePrintfA` at `0x1800257d1`
- `rtutils!TracePrintfA` at `0x180025359`
- `rtutils!TracePrintfA` at `0x1800253c6`
- `rtutils!TracePrintfA` at `0x18002549f`
- `rtutils!TracePrintfA` at `0x1800254eb`
- `rtutils!TracePrintfA` at `0x180025601`
- `rtutils!TracePrintfA` at `0x180025699`
- `rtutils!TracePrintfA` at `0x1800257d1`

## string_xrefs

- `0x180025308`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180025352`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18002544d`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180025498`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetID(unsigned int a1, int a2, unsigned int a3, int a4, wchar_t *String1, unsigned int *a6)
{
  wchar_t *v7; // r15
  unsigned int v8; // r12d
  char *v10; // rbx
  __int64 v11; // rdi
  unsigned int v12; // r13d
  unsigned int LineObjWithReadLock; // eax
  unsigned int v14; // esi
  __int64 v15; // rdx
  const wchar_t *v16; // r8
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // r12d
  unsigned int v23; // eax
  HANDLE ProcessHeap; // rax
  __int64 v26; // rcx
  char *v27; // rdx
  unsigned int NDProxyHandle; // eax
  const wchar_t *v29; // rdx
  unsigned int v30; // ecx
  __int64 v31; // r8
  char *v32; // rdx
  char *v33; // rcx
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h] BYREF
  char v40[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v7 = String1;
  v8 = a3;
  v10 = 0;
  lpMem = 0;
  v38 = 0;
  v11 = -1;
  v37 = 0;
  do
    ++v11;
  while ( String1[v11] );
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( a4 != 1 )
  {
    if ( a4 != 4 )
    {
      v12 = a1;
LABEL_73:
      v14 = 87;
      if ( gIsndpspEtwTracingAvailable )
      {
        v15 = qword_18003EC48;
        if ( qword_18003EC48 )
        {
          v16 = L"RasLineGetID: Invalid input parameters";
          goto LABEL_8;
        }
        goto LABEL_45;
      }
      if ( dwTraceId == -1 )
        goto LABEL_45;
      TracePrintfA(dwTraceId, "RasLineGetID: Invalid input parameters");
      goto LABEL_41;
    }
    v18 = GetCallObjWithReadLock(v8, &v37);
    v14 = v18;
    if ( v18 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v18);
        goto LABEL_25;
      }
      if ( qword_18003EC40 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v18);
        v19 = qword_18003EC40;
        v20 = (const wchar_t *)&v39;
LABEL_24:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v19, v20);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
    v21 = *a6;
    a6[1] = 28;
    if ( v21 < 0x1C )
    {
      v14 = 122;
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
        goto LABEL_25;
      }
      v19 = qword_18003EC48;
      if ( qword_18003EC48 )
      {
        v20 = L"RasLineGetID: Insufficient buffer passed by caller";
        goto LABEL_24;
      }
LABEL_25:
      v12 = a1;
LABEL_43:
      if ( v37 )
        ReleaseObjReadLock(v8);
      goto LABEL_45;
    }
    if ( !v37 )
      return v14;
    v22 = v11 + 1;
    v23 = PrepareSyncRequest(0x7030113u, *(_DWORD *)(v37 + 4), v21 + 52 + 2 * (v11 + 1), &lpMem);
    v14 = v23;
    if ( v23 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v23);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v39);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v23);
      }
      v10 = (char *)lpMem;
      goto LABEL_40;
    }
    v10 = (char *)lpMem;
    v26 = v37;
    v27 = (char *)lpMem + 72;
    *((_DWORD *)lpMem + 16) = a2;
    NDProxyHandle = GetNDProxyHandle(v26, v27);
    v14 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_40;
      }
      if ( qword_18003EC40 )
      {
        v29 = L"RasLineGetID: GetNDProxyHandle failed with error (0x%x)";
LABEL_54:
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, v29, NDProxyHandle);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v39);
      }
    }
    else
    {
      *((_DWORD *)v10 + 20) = 4;
      *((_DWORD *)v10 + 21) = v22;
      v30 = *a6 + 48;
      v31 = v22;
      *((_DWORD *)v10 + 22) = v30;
      *((_DWORD *)v10 + 23) = *a6;
      *((_DWORD *)v10 + 25) = 24;
      *((_DWORD *)v10 + 24) = 24;
      *(_QWORD *)(v10 + 108) = 0;
      *((_DWORD *)v10 + 26) = 0;
      if ( (_DWORD)v11 != -1 )
      {
        v32 = &v10[v30 + 48];
        if ( v22 <= 0x7FFFFFFEuLL )
        {
          do
          {
            if ( !*v7 )
              break;
            *(_WORD *)v32 = *v7++;
            v32 += 2;
            --v31;
          }
          while ( v31 );
          v33 = v32 - 2;
          if ( v31 )
            v33 = v32;
          *(_WORD *)v33 = 0;
        }
        else
        {
          *(_WORD *)v32 = 0;
        }
      }
      NDProxyHandle = SyncDriverRequest(0x8FFF23C8, v10);
      v14 = NDProxyHandle;
      if ( !NDProxyHandle )
      {
        memcpy_0(a6, v10 + 92, *((unsigned int *)v10 + 25));
        goto LABEL_40;
      }
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)",
            NDProxyHandle);
        goto LABEL_40;
      }
      if ( qword_18003EC40 )
      {
        v29 = L"RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)";
        goto LABEL_54;
      }
    }
LABEL_40:
    v12 = a1;
    v8 = a3;
LABEL_41:
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    goto LABEL_43;
  }
  v12 = a1;
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v38);
  v14 = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      goto LABEL_45;
    }
    if ( qword_18003EC40 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      v15 = qword_18003EC40;
      v16 = (const wchar_t *)&v39;
LABEL_8:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v15, v16);
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  if ( wcscmp_0(String1, L"LineGuid") )
    goto LABEL_73;
  a6[1] = 48;
  if ( *a6 >= 0x30 )
  {
    v17 = v38;
    a6[2] = 48;
    a6[3] = 1;
    a6[4] = 24;
    a6[5] = 24;
    memmove_0(a6 + 6, (const void *)(v17 + 40), 0x10u);
    a6[10] = *(_DWORD *)(v17 + 56);
    *((_BYTE *)a6 + 44) = 0;
  }
  else
  {
    v14 = 122;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
      goto LABEL_45;
    }
    v15 = qword_18003EC48;
    if ( qword_18003EC48 )
    {
      v16 = L"RasLineGetID: Insufficient buffer passed by caller";
      goto LABEL_8;
    }
  }
LABEL_45:
  if ( v38 )
    ReleaseObjReadLock(v12);
  return v14;
}

```

## disassembly

```asm
0x180025244  mov     [rsp-8+arg_8], rbx
0x180025249  push    rbp
0x18002524a  push    rsi
0x18002524b  push    rdi
0x18002524c  push    r12
0x18002524e  push    r13
0x180025250  push    r14
0x180025252  push    r15
0x180025254  lea     rbp, [rsp-750h]
0x18002525c  sub     rsp, 850h
0x180025263  mov     rax, cs:__security_cookie
0x18002526a  xor     rax, rsp
0x18002526d  mov     [rbp+780h+var_40], rax
0x180025274  mov     r14, [rbp+780h+arg_28]
0x18002527b  mov     esi, r9d
0x18002527e  mov     r15, [rbp+780h+String1]
0x180025285  mov     r12d, r8d
0x180025288  mov     [rsp+880h+var_860], ecx
0x18002528c  mov     r13d, edx
0x18002528f  xor     ecx, ecx
0x180025291  mov     [rsp+880h+var_85C], r8d
0x180025296  mov     ebx, ecx
0x180025298  mov     [rsp+880h+lpMem], rcx
0x18002529d  mov     [rsp+880h+var_848], rcx
0x1800252a2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800252a6  mov     [rsp+880h+var_850], rcx
0x1800252ab  inc     rdi
0x1800252ae  cmp     [r15+rdi*2], cx
0x1800252b3  jnz     short loc_1800252AB
0x1800252b5  mov     [rsp+880h+var_840], ecx
0x1800252b9  xor     edx, edx; Val
0x1800252bb  lea     rcx, [rsp+880h+var_83C]; void *
0x1800252c0  mov     r8d, 7FCh; Size
0x1800252c6  call    memset_0
0x1800252cb  cmp     esi, 1
0x1800252ce  jnz     loc_180025419
0x1800252d4  mov     r13d, [rsp+880h+var_860]
0x1800252d9  lea     rdx, [rsp+880h+var_848]
0x1800252de  mov     ecx, r13d
0x1800252e1  call    GetLineObjWithReadLock
0x1800252e6  xor     ecx, ecx
0x1800252e8  mov     esi, eax
0x1800252ea  test    eax, eax
0x1800252ec  jz      short loc_180025364
0x1800252ee  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x1800252f4  jz      short loc_180025340
0x1800252f6  cmp     cs:qword_18003EC40, rcx
0x1800252fd  jz      loc_1800255B0
0x180025303  mov     word ptr [rsp+880h+var_840], cx
0x180025308  lea     rdx, aRaslinegetidGe; "RasLineGetID: GetLineObjWithReadLock fa"...
0x18002530f  lea     rcx, [rsp+880h+var_840]
0x180025314  mov     r8d, eax
0x180025317  call    FormatRRASErrorString
0x18002531c  mov     rdx, cs:qword_18003EC40
0x180025323  lea     r8, [rsp+880h+var_840]
0x180025328  mov     rcx, cs:gNdpspEtwContext
0x18002532f  mov     rax, cs:gNdpspTemplateFunc
0x180025336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002533b  jmp     loc_1800255B0
0x180025340  mov     ecx, cs:dwTraceId; dwTraceID
0x180025346  cmp     ecx, 0FFFFFFFFh
0x180025349  jz      loc_1800255B0
0x18002534f  mov     r8d, eax
0x180025352  lea     rdx, aRaslinegetidGe_3; "RasLineGetID: GetLineObjWithReadLock fa"...
0x180025359  call    cs:__imp_TracePrintfA
0x18002535f  jmp     loc_1800255B0
0x180025364  lea     rdx, aLineguid; "LineGuid"
0x18002536b  mov     rcx, r15; String1
0x18002536e  call    wcscmp_0
0x180025373  xor     ecx, ecx
0x180025375  test    eax, eax
0x180025377  jnz     loc_180025792
0x18002537d  lea     eax, [rcx+30h]
0x180025380  mov     [r14+4], eax
0x180025384  cmp     [r14], eax
0x180025387  jnb     short loc_1800253D1
0x180025389  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18002538f  lea     esi, [rcx+7Ah]
0x180025392  jz      short loc_1800253B0
0x180025394  mov     rdx, cs:qword_18003EC48
0x18002539b  test    rdx, rdx
0x18002539e  jz      loc_1800255B0
0x1800253a4  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x1800253ab  jmp     loc_180025328
0x1800253b0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800253b6  cmp     ecx, 0FFFFFFFFh
0x1800253b9  jz      loc_1800255B0
0x1800253bf  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x1800253c6  call    cs:__imp_TracePrintfA
0x1800253cc  jmp     loc_1800255B0
0x1800253d1  mov     rbx, [rsp+880h+var_848]
0x1800253d6  lea     rcx, [r14+18h]; void *
0x1800253da  mov     [r14+8], eax
0x1800253de  mov     r8d, 10h; Size
0x1800253e4  lea     eax, [r14+18h]
0x1800253e8  mov     dword ptr [r14+0Ch], 1
0x1800253f0  sub     eax, r14d
0x1800253f3  mov     dword ptr [r14+10h], 18h
0x1800253fb  lea     rdx, [rbx+28h]; Src
0x1800253ff  mov     [r14+14h], eax
0x180025403  call    memmove_0
0x180025408  mov     eax, [rbx+38h]
0x18002540b  mov     [r14+28h], eax
0x18002540f  mov     byte ptr [r14+2Ch], 0
0x180025414  jmp     loc_1800255B0
0x180025419  cmp     esi, 4
0x18002541c  jnz     loc_18002578B
0x180025422  lea     rdx, [rsp+880h+var_850]
0x180025427  mov     ecx, r12d
0x18002542a  call    GetCallObjWithReadLock
0x18002542f  xor     ecx, ecx
0x180025431  mov     esi, eax
0x180025433  test    eax, eax
0x180025435  jz      short loc_1800254A7
0x180025437  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x18002543d  jz      short loc_18002548A
0x18002543f  cmp     cs:qword_18003EC40, rcx
0x180025446  jz      short loc_180025480
0x180025448  mov     word ptr [rsp+880h+var_840], cx
0x18002544d  lea     rdx, aRaslinegetidGe_0; "RasLineGetID: GetCallObjWithReadLock fa"...
0x180025454  lea     rcx, [rsp+880h+var_840]
0x180025459  mov     r8d, eax
0x18002545c  call    FormatRRASErrorString
0x180025461  mov     rdx, cs:qword_18003EC40
0x180025468  lea     r8, [rsp+880h+var_840]
0x18002546d  mov     rcx, cs:gNdpspEtwContext
0x180025474  mov     rax, cs:gNdpspTemplateFunc
0x18002547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025480  mov     r13d, [rsp+880h+var_860]
0x180025485  jmp     loc_1800255A0
0x18002548a  mov     ecx, cs:dwTraceId; dwTraceID
0x180025490  cmp     ecx, 0FFFFFFFFh
0x180025493  jz      short loc_180025480
0x180025495  mov     r8d, eax
0x180025498  lea     rdx, aRaslinegetidGe_2; "RasLineGetID: GetCallObjWithReadLock fa"...
0x18002549f  call    cs:__imp_TracePrintfA
0x1800254a5  jmp     short loc_180025480
0x1800254a7  mov     eax, [r14]
0x1800254aa  mov     dword ptr [r14+4], 1Ch
0x1800254b2  cmp     eax, 1Ch
0x1800254b5  jnb     short loc_1800254F3
0x1800254b7  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x1800254bd  mov     esi, 7Ah ; 'z'
0x1800254c2  jz      short loc_1800254D9
0x1800254c4  mov     rdx, cs:qword_18003EC48
0x1800254cb  test    rdx, rdx
0x1800254ce  jz      short loc_180025480
0x1800254d0  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x1800254d7  jmp     short loc_18002546D
0x1800254d9  mov     ecx, cs:dwTraceId; dwTraceID
0x1800254df  cmp     ecx, 0FFFFFFFFh
0x1800254e2  jz      short loc_180025480
0x1800254e4  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x1800254eb  call    cs:__imp_TracePrintfA
0x1800254f1  jmp     short loc_180025480
0x1800254f3  mov     rdx, [rsp+880h+var_850]
0x1800254f8  test    rdx, rdx
0x1800254fb  jz      loc_1800255C0
0x180025501  mov     edx, [rdx+4]
0x180025504  lea     r8d, [rax+34h]
0x180025508  lea     r12d, [rdi+1]
0x18002550c  mov     ecx, 7030113h
0x180025511  lea     r8d, [r8+r12*2]
0x180025515  lea     r9, [rsp+880h+lpMem]
0x18002551a  call    PrepareSyncRequest
0x18002551f  xor     ecx, ecx
0x180025521  mov     esi, eax
0x180025523  test    eax, eax
0x180025525  jz      loc_18002560C
0x18002552b  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180025531  jz      loc_1800255EC
0x180025537  cmp     cs:qword_18003EC40, rcx
0x18002553e  jz      short loc_180025578
0x180025540  mov     word ptr [rsp+880h+var_840], cx
0x180025545  lea     rdx, aRaslinegetidPr_0; "RasLineGetID: PrepareSyncRequest failed"...
0x18002554c  lea     rcx, [rsp+880h+var_840]
0x180025551  mov     r8d, eax
0x180025554  call    FormatRRASErrorString
0x180025559  mov     rdx, cs:qword_18003EC40
0x180025560  lea     r8, [rsp+880h+var_840]
0x180025565  mov     rcx, cs:gNdpspEtwContext
0x18002556c  mov     rax, cs:gNdpspTemplateFunc
0x180025573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025578  mov     rbx, [rsp+880h+lpMem]
0x18002557d  mov     r13d, [rsp+880h+var_860]
0x180025582  mov     r12d, [rsp+880h+var_85C]
0x180025587  test    rbx, rbx
0x18002558a  jz      short loc_1800255A0
0x18002558c  call    cs:__imp_GetProcessHeap
0x180025592  mov     r8, rbx; lpMem
0x180025595  xor     edx, edx; dwFlags
0x180025597  mov     rcx, rax; hHeap
0x18002559a  call    cs:__imp_HeapFree
0x1800255a0  cmp     [rsp+880h+var_850], 0
0x1800255a6  jz      short loc_1800255B0
0x1800255a8  mov     ecx, r12d
0x1800255ab  call    ReleaseObjReadLock
0x1800255b0  cmp     [rsp+880h+var_848], 0
0x1800255b6  jz      short loc_1800255C0
0x1800255b8  mov     ecx, r13d
0x1800255bb  call    ReleaseObjReadLock
0x1800255c0  mov     eax, esi
0x1800255c2  mov     rcx, [rbp+780h+var_40]
0x1800255c9  xor     rcx, rsp; StackCookie
0x1800255cc  call    __security_check_cookie
0x1800255d1  mov     rbx, [rsp+880h+arg_8]
0x1800255d9  add     rsp, 850h
0x1800255e0  pop     r15
0x1800255e2  pop     r14
0x1800255e4  pop     r13
0x1800255e6  pop     r12
0x1800255e8  pop     rdi
0x1800255e9  pop     rsi
0x1800255ea  pop     rbp
0x1800255eb  retn
0x1800255ec  mov     ecx, cs:dwTraceId; dwTraceID
0x1800255f2  cmp     ecx, 0FFFFFFFFh
0x1800255f5  jz      short loc_180025578
0x1800255f7  mov     r8d, eax
0x1800255fa  lea     rdx, aRaslinegetidPr; "RasLineGetID: PrepareSyncRequest failed"...
0x180025601  call    cs:__imp_TracePrintfA
0x180025607  jmp     loc_180025578
0x18002560c  mov     rbx, [rsp+880h+lpMem]
0x180025611  mov     rcx, [rsp+880h+var_850]
0x180025616  lea     rdx, [rbx+48h]
0x18002561a  mov     [rbx+40h], r13d
0x18002561e  call    GetNDProxyHandle
0x180025623  xor     r13d, r13d
0x180025626  mov     esi, eax
0x180025628  test    eax, eax
0x18002562a  jz      short loc_1800256A4
0x18002562c  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025633  jz      short loc_180025680
0x180025635  cmp     cs:qword_18003EC40, r13
0x18002563c  jz      loc_18002557D
0x180025642  lea     rdx, aRaslinegetidGe_1; "RasLineGetID: GetNDProxyHandle failed w"...
0x180025649  mov     r8d, eax
0x18002564c  mov     word ptr [rsp+880h+var_840], r13w
0x180025652  lea     rcx, [rsp+880h+var_840]
0x180025657  call    FormatRRASErrorString
0x18002565c  mov     rdx, cs:qword_18003EC40
0x180025663  lea     r8, [rsp+880h+var_840]
0x180025668  mov     rcx, cs:gNdpspEtwContext
0x18002566f  mov     rax, cs:gNdpspTemplateFunc
0x180025676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002567b  jmp     loc_18002557D
0x180025680  mov     ecx, cs:dwTraceId; dwTraceID
0x180025686  cmp     ecx, 0FFFFFFFFh
0x180025689  jz      loc_18002557D
0x18002568f  lea     rdx, aRaslinegetidGe_4; "RasLineGetID: GetNDProxyHandle failed w"...
0x180025696  mov     r8d, eax
0x180025699  call    cs:__imp_TracePrintfA
0x18002569f  jmp     loc_18002557D
0x1800256a4  mov     dword ptr [rbx+50h], 4
0x1800256ab  mov     [rbx+54h], r12d
0x1800256af  mov     ecx, [r14]
0x1800256b2  add     ecx, 30h ; '0'
0x1800256b5  mov     r8d, r12d
0x1800256b8  mov     [rbx+58h], ecx
0x1800256bb  mov     eax, [r14]
0x1800256be  mov     [rbx+5Ch], eax
0x1800256c1  mov     dword ptr [rbx+64h], 18h
0x1800256c8  mov     dword ptr [rbx+60h], 18h
0x1800256cf  mov     [rbx+6Ch], r13
0x1800256d3  mov     [rbx+68h], r13d
0x1800256d7  test    r12d, r12d
0x1800256da  jz      short loc_180025726
0x1800256dc  mov     edx, ecx
0x1800256de  add     rdx, 30h ; '0'
0x1800256e2  add     rdx, rbx
0x1800256e5  cmp     r8, 7FFFFFFFh
0x1800256ec  ja      short loc_1800256F7
0x1800256ee  cmp     r8, 7FFFFFFEh
0x1800256f5  jbe     short loc_1800256FD
0x1800256f7  mov     [rdx], r13w
0x1800256fb  jmp     short loc_180025726
0x1800256fd  movzx   eax, word ptr [r15]
0x180025701  test    ax, ax
0x180025704  jz      short loc_180025717
0x180025706  mov     [rdx], ax
0x180025709  add     r15, 2
0x18002570d  add     rdx, 2
0x180025711  sub     r8, 1
0x180025715  jnz     short loc_1800256FD
0x180025717  test    r8, r8
0x18002571a  lea     rcx, [rdx-2]
0x18002571e  cmovnz  rcx, rdx
0x180025722  mov     [rcx], r13w
0x180025726  mov     rdx, rbx; lpInBuffer
0x180025729  mov     ecx, 8FFF23C8h; dwIoControlCode
0x18002572e  call    SyncDriverRequest
0x180025733  mov     esi, eax
0x180025735  test    eax, eax
0x180025737  jz      short loc_180025776
0x180025739  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025740  jz      short loc_18002575B
0x180025742  cmp     cs:qword_18003EC40, r13
0x180025749  jz      loc_18002557D
0x18002574f  lea     rdx, aRaslinegetidSy; "RasLineGetID: SyncDriverRequest(OID_TAP"...
0x180025756  jmp     loc_180025649
  ... truncated ...
```
