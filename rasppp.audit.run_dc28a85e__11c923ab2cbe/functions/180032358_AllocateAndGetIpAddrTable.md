# AllocateAndGetIpAddrTable

- ea: `0x180032358`
- end: `0x180032731`
- name: `AllocateAndGetIpAddrTable`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180033304`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002dcfc`
- `0x18003230c`
- `0x180032358`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003268a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003268a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800324ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800324ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032659`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032472`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800326a0`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180032472`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800326a0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18003245c`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18003245c`
- `IPHLPAPI!GetIpAddrTable` at `0x180032497`
- `IPHLPAPI!GetIpAddrTable` at `0x18003259e`
- `IPHLPAPI!GetIpAddrTable` at `0x180032497`
- `IPHLPAPI!GetIpAddrTable` at `0x18003259e`

## string_xrefs

- `0x1800325c3`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180032615`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpAddrTable(LPVOID *a1, __int64 a2, void *a3)
{
  __int64 v5; // rcx
  __int64 result; // rax
  int v7; // esi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  DWORD IpAddrTable; // eax
  DWORD v10; // ebx
  const wchar_t *v11; // rdx
  const CHAR *v12; // rcx
  struct _MIB_IPADDRTABLE *v13; // rax
  _DWORD *v14; // rax
  ULONG pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+6Ch] [rbp-94h]
  __int128 v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwSize = 0;
  v21 = 0;
  memset(v16, 0, sizeof(v16));
  memset_0(v22, 0, sizeof(v22));
  v5 = qword_18004D658;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( qword_18004D648 || qword_18004D650 || qword_18004D658 )
  {
    result = NsiGetRoutingDomainIdForCompartment(qword_18004D658, v16);
    if ( (_DWORD)result )
      return result;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v5 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v5,
        L"AllocateAndGetIpAddrTable Begin",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable Begin");
  }
  *a1 = 0;
  v7 = 1;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpAddrTable = SetCurrentThreadCompartmentId(1u);
  v10 = IpAddrTable;
  if ( IpAddrTable )
  {
    v7 = 0;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D650 )
        goto LABEL_27;
      v11 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
      goto LABEL_24;
    }
    v12 = "AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_26;
  }
  pdwSize = 0;
  IpAddrTable = GetIpAddrTable(0, &pdwSize, 0);
  v10 = IpAddrTable;
  if ( IpAddrTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D650 )
        goto LABEL_27;
      v11 = L"AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_24:
      LOWORD(v17) = 0;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, v11, IpAddrTable);
      ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D650,
        &v21,
        v16,
        0,
        &v17);
      goto LABEL_27;
    }
    v12 = "AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_26:
    TraceHlp(v12);
    goto LABEL_27;
  }
  pdwSize += 120;
  v13 = (struct _MIB_IPADDRTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v13;
  if ( !v13 )
    goto LABEL_16;
  v10 = GetIpAddrTable(v13, &pdwSize, 0);
LABEL_27:
  if ( v10 != 232 )
  {
    if ( !v10 )
      goto LABEL_35;
LABEL_33:
    if ( *a1 )
    {
      HeapFree(a3, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_35;
  }
  if ( *a1 )
  {
    HeapFree(a3, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 36;
  v14 = HeapAlloc(a3, 0x40u, 0x24u);
  *a1 = v14;
  if ( !v14 )
  {
LABEL_16:
    v10 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D650 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v21, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D650,
          &v21,
          v16,
          0,
          &v17);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpAddrTable : error %d allocating %d bytes");
    }
    goto LABEL_33;
  }
  *v14 = 0;
  v10 = 0;
LABEL_35:
  if ( v7 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D658 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D658,
        L"AllocateAndGetIpAddrTable End",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable End");
  }
  return v10;
}

```

## disassembly

```asm
0x180032358  mov     [rsp-8+arg_8], rbx
0x18003235d  mov     [rsp-8+arg_18], rsi
0x180032362  push    rbp
0x180032363  push    rdi
0x180032364  push    r12
0x180032366  push    r14
0x180032368  push    r15
0x18003236a  lea     rbp, [rsp-7A0h]
0x180032372  sub     rsp, 8A0h
0x180032379  mov     rax, cs:__security_cookie
0x180032380  xor     rax, rsp
0x180032383  mov     [rbp+7C0h+var_30], rax
0x18003238a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032391  mov     r14, r8
0x180032394  mov     rdi, rcx
0x180032397  xor     r12d, r12d
0x18003239a  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18003239e  xor     edx, edx; Val
0x1800323a0  mov     [rsp+8C0h+pdwSize], r12d
0x1800323a5  mov     r8d, 7FCh; Size
0x1800323ab  mov     [rbp+7C0h+var_830], r12d
0x1800323af  movdqu  [rsp+8C0h+var_878], xmm0
0x1800323b5  call    memset_0
0x1800323ba  mov     rcx, cs:qword_18004D658
0x1800323c1  xorps   xmm0, xmm0
0x1800323c4  xor     eax, eax
0x1800323c6  mov     [rsp+8C0h+var_858], r12d
0x1800323cb  cmp     cs:qword_18004D648, r12
0x1800323d2  movups  [rsp+8C0h+var_854], xmm0
0x1800323d7  mov     [rbp+7C0h+var_834], eax
0x1800323da  movups  [rsp+8C0h+var_844], xmm0
0x1800323df  movups  [rsp+8C0h+var_868], xmm0
0x1800323e4  jnz     short loc_1800323F4
0x1800323e6  cmp     cs:qword_18004D650, r12
0x1800323ed  jnz     short loc_1800323F4
0x1800323ef  test    rcx, rcx
0x1800323f2  jz      short loc_180032406
0x1800323f4  lea     rdx, [rsp+8C0h+var_878]
0x1800323f9  call    NsiGetRoutingDomainIdForCompartment
0x1800323fe  test    eax, eax
0x180032400  jnz     loc_180032705
0x180032406  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18003240d  jz      short loc_18003244D
0x18003240f  test    rcx, rcx
0x180032412  jz      short loc_180032459
0x180032414  lea     rax, [rsp+8C0h+var_858]
0x180032419  mov     word ptr [rsp+8C0h+var_858], r12w
0x18003241f  mov     [rsp+8C0h+var_898], rax
0x180032424  lea     r9, [rsp+8C0h+var_878]
0x180032429  mov     rax, cs:gIphlpParamTemplateFunc
0x180032430  lea     r8, aAllocateandget_18; "AllocateAndGetIpAddrTable Begin"
0x180032437  mov     rdx, rcx
0x18003243a  mov     [rsp+8C0h+var_8A0], r12
0x18003243f  mov     rcx, cs:gIphlpEtwContext
0x180032446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003244b  jmp     short loc_180032459
0x18003244d  lea     rcx, aAllocateandget_11; "AllocateAndGetIpAddrTable Begin"
0x180032454  call    TraceHlp
0x180032459  mov     [rdi], r12
0x18003245c  call    cs:__imp_GetCurrentThreadCompartmentId
0x180032463  nop     dword ptr [rax+rax+00h]
0x180032468  mov     esi, 1
0x18003246d  mov     r15d, eax
0x180032470  mov     ecx, esi; CompartmentId
0x180032472  call    cs:__imp_SetCurrentThreadCompartmentId
0x180032479  nop     dword ptr [rax+rax+00h]
0x18003247e  mov     ebx, eax
0x180032480  test    eax, eax
0x180032482  jnz     loc_1800325AE
0x180032488  xor     r8d, r8d; bOrder
0x18003248b  mov     [rsp+8C0h+pdwSize], r12d
0x180032490  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180032495  xor     ecx, ecx; pIpAddrTable
0x180032497  call    cs:__imp_GetIpAddrTable
0x18003249e  nop     dword ptr [rax+rax+00h]
0x1800324a3  mov     ebx, eax
0x1800324a5  cmp     eax, 7Ah ; 'z'
0x1800324a8  jz      short loc_1800324D8
0x1800324aa  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800324b1  jz      short loc_1800324CC
0x1800324b3  cmp     cs:qword_18004D650, r12
0x1800324ba  jz      loc_180032623
0x1800324c0  lea     rdx, aAllocateandget_15; "AllocateAndGetIpNetTable : error %d get"...
0x1800324c7  jmp     loc_1800325CA
0x1800324cc  lea     rcx, aAllocateandget_12; "AllocateAndGetIpNetTable : error %d get"...
0x1800324d3  jmp     loc_18003261C
0x1800324d8  mov     eax, [rsp+8C0h+pdwSize]
0x1800324dc  mov     edx, 40h ; '@'; dwFlags
0x1800324e1  add     eax, 78h ; 'x'
0x1800324e4  mov     rcx, r14; hHeap
0x1800324e7  mov     r8d, eax; dwBytes
0x1800324ea  mov     [rsp+8C0h+pdwSize], eax
0x1800324ee  call    cs:__imp_HeapAlloc
0x1800324f5  nop     dword ptr [rax+rax+00h]
0x1800324fa  mov     [rdi], rax
0x1800324fd  test    rax, rax
0x180032500  jnz     loc_180032593
0x180032506  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18003250d  mov     ebx, 0Eh
0x180032512  jz      short loc_18003257B
0x180032514  cmp     cs:qword_18004D650, r12
0x18003251b  jz      loc_18003267D
0x180032521  mov     r9d, [rsp+8C0h+pdwSize]
0x180032526  lea     rdx, aAllocateandget_10; "AllocateAndGetIpAddrTable : error %d al"...
0x18003252d  mov     r8d, ebx
0x180032530  mov     word ptr [rbp+7C0h+var_830], r12w
0x180032535  lea     rcx, [rbp+7C0h+var_830]
0x180032539  mov     word ptr [rsp+8C0h+var_858], r12w
0x18003253f  call    FormatRRASErrorString
0x180032544  mov     rdx, cs:qword_18004D650
0x18003254b  lea     rax, [rsp+8C0h+var_858]
0x180032550  mov     rcx, cs:gIphlpEtwContext
0x180032557  lea     r9, [rsp+8C0h+var_878]
0x18003255c  mov     [rsp+8C0h+var_898], rax
0x180032561  lea     r8, [rbp+7C0h+var_830]
0x180032565  mov     rax, cs:gIphlpParamTemplateFunc
0x18003256c  mov     [rsp+8C0h+var_8A0], r12
0x180032571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032576  jmp     loc_18003267D
0x18003257b  mov     r8d, [rsp+8C0h+pdwSize]
0x180032580  lea     rcx, aAllocateandget_5; "AllocateAndGetIpAddrTable : error %d al"...
0x180032587  mov     edx, ebx
0x180032589  call    TraceHlp
0x18003258e  jmp     loc_18003267D
0x180032593  xor     r8d, r8d; bOrder
0x180032596  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18003259b  mov     rcx, rax; pIpAddrTable
0x18003259e  call    cs:__imp_GetIpAddrTable
0x1800325a5  nop     dword ptr [rax+rax+00h]
0x1800325aa  mov     ebx, eax
0x1800325ac  jmp     short loc_180032623
0x1800325ae  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800325b5  mov     esi, r12d
0x1800325b8  jz      short loc_180032615
0x1800325ba  cmp     cs:qword_18004D650, r12
0x1800325c1  jz      short loc_180032623
0x1800325c3  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x1800325ca  mov     r8d, eax
0x1800325cd  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800325d3  lea     rcx, [rbp+7C0h+var_830]
0x1800325d7  mov     word ptr [rbp+7C0h+var_830], r12w
0x1800325dc  call    FormatRRASErrorString
0x1800325e1  mov     rdx, cs:qword_18004D650
0x1800325e8  lea     rax, [rsp+8C0h+var_858]
0x1800325ed  mov     rcx, cs:gIphlpEtwContext
0x1800325f4  lea     r9, [rsp+8C0h+var_878]
0x1800325f9  mov     [rsp+8C0h+var_898], rax
0x1800325fe  lea     r8, [rbp+7C0h+var_830]
0x180032602  mov     rax, cs:gIphlpParamTemplateFunc
0x180032609  mov     [rsp+8C0h+var_8A0], r12
0x18003260e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032613  jmp     short loc_180032623
0x180032615  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18003261c  mov     edx, eax
0x18003261e  call    TraceHlp
0x180032623  cmp     ebx, 0E8h
0x180032629  jnz     short loc_180032679
0x18003262b  mov     r8, [rdi]; lpMem
0x18003262e  test    r8, r8
0x180032631  jz      short loc_180032647
0x180032633  xor     edx, edx; dwFlags
0x180032635  mov     rcx, r14; hHeap
0x180032638  call    cs:__imp_HeapFree
0x18003263f  nop     dword ptr [rax+rax+00h]
0x180032644  mov     [rdi], r12
0x180032647  mov     r8d, 24h ; '$'; dwBytes
0x18003264d  mov     rcx, r14; hHeap
0x180032650  mov     [rsp+8C0h+pdwSize], r8d
0x180032655  lea     edx, [r8+1Ch]; dwFlags
0x180032659  call    cs:__imp_HeapAlloc
0x180032660  nop     dword ptr [rax+rax+00h]
0x180032665  mov     [rdi], rax
0x180032668  test    rax, rax
0x18003266b  jz      loc_180032506
0x180032671  mov     [rax], r12d
0x180032674  mov     ebx, r12d
0x180032677  jmp     short loc_180032699
0x180032679  test    ebx, ebx
0x18003267b  jz      short loc_180032699
0x18003267d  mov     r8, [rdi]; lpMem
0x180032680  test    r8, r8
0x180032683  jz      short loc_180032699
0x180032685  xor     edx, edx; dwFlags
0x180032687  mov     rcx, r14; hHeap
0x18003268a  call    cs:__imp_HeapFree
0x180032691  nop     dword ptr [rax+rax+00h]
0x180032696  mov     [rdi], r12
0x180032699  test    esi, esi
0x18003269b  jz      short loc_1800326AC
0x18003269d  mov     ecx, r15d; CompartmentId
0x1800326a0  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800326a7  nop     dword ptr [rax+rax+00h]
0x1800326ac  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800326b3  jz      short loc_1800326F7
0x1800326b5  mov     rdx, cs:qword_18004D658
0x1800326bc  test    rdx, rdx
0x1800326bf  jz      short loc_180032703
0x1800326c1  mov     rcx, cs:gIphlpEtwContext
0x1800326c8  lea     rax, [rsp+8C0h+var_858]
0x1800326cd  mov     [rsp+8C0h+var_898], rax
0x1800326d2  lea     r9, [rsp+8C0h+var_878]
0x1800326d7  mov     rax, cs:gIphlpParamTemplateFunc
0x1800326de  lea     r8, aAllocateandget_17; "AllocateAndGetIpAddrTable End"
0x1800326e5  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800326eb  mov     [rsp+8C0h+var_8A0], r12
0x1800326f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326f5  jmp     short loc_180032703
0x1800326f7  lea     rcx, aAllocateandget; "AllocateAndGetIpAddrTable End"
0x1800326fe  call    TraceHlp
0x180032703  mov     eax, ebx
0x180032705  mov     rcx, [rbp+7C0h+var_30]
0x18003270c  xor     rcx, rsp; StackCookie
0x18003270f  call    __security_check_cookie
0x180032714  lea     r11, [rsp+8C0h+var_20]
0x18003271c  mov     rbx, [r11+38h]
0x180032720  mov     rsi, [r11+48h]
0x180032724  mov     rsp, r11
0x180032727  pop     r15
0x180032729  pop     r14
0x18003272b  pop     r12
0x18003272d  pop     rdi
0x18003272e  pop     rbp
0x18003272f  retn
```
