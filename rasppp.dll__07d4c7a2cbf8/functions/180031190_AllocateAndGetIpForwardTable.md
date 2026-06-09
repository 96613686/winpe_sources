# AllocateAndGetIpForwardTable

- ea: `0x180031190`
- end: `0x180031534`
- name: `AllocateAndGetIpForwardTable`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003153c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002cbb4`
- `0x180030da4`
- `0x180031190`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003149a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003149a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003146f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003146f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800312a4`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800314aa`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800312a4`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800314aa`
- `IPHLPAPI!GetIpForwardTable` at `0x1800312c3`
- `IPHLPAPI!GetIpForwardTable` at `0x1800313c0`
- `IPHLPAPI!GetIpForwardTable` at `0x1800312c3`
- `IPHLPAPI!GetIpForwardTable` at `0x1800313c0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180031294`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180031294`

## string_xrefs

- `0x1800313df`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180031431`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpForwardTable(LPVOID *a1, __int64 a2, void *a3)
{
  __int64 v5; // rcx
  __int64 result; // rax
  int v7; // esi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  DWORD IpForwardTable; // eax
  DWORD v10; // ebx
  const wchar_t *v11; // rdx
  const CHAR *v12; // rcx
  struct _MIB_IPFORWARDTABLE *v13; // rax
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
  v5 = qword_18004C658;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( qword_18004C648 || qword_18004C650 || qword_18004C658 )
  {
    result = NsiGetRoutingDomainIdForCompartment(qword_18004C658, v16);
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
        L"AllocateAndGetIpForwardTable Begin",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable Begin");
  }
  *a1 = 0;
  v7 = 1;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpForwardTable = SetCurrentThreadCompartmentId(1u);
  v10 = IpForwardTable;
  if ( IpForwardTable )
  {
    v7 = 0;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C650 )
        goto LABEL_27;
      v11 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
      goto LABEL_24;
    }
    v12 = "AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_26;
  }
  pdwSize = 0;
  IpForwardTable = GetIpForwardTable(0, &pdwSize, 0);
  v10 = IpForwardTable;
  if ( IpForwardTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C650 )
        goto LABEL_27;
      v11 = L"AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_24:
      LOWORD(v17) = 0;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, v11, IpForwardTable);
      ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C650,
        &v21,
        v16,
        0,
        &v17);
      goto LABEL_27;
    }
    v12 = "AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_26:
    TraceHlp(v12);
    goto LABEL_27;
  }
  pdwSize += 280;
  v13 = (struct _MIB_IPFORWARDTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v13;
  if ( !v13 )
    goto LABEL_16;
  v10 = GetIpForwardTable(v13, &pdwSize, 0);
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
  pdwSize = 68;
  v14 = HeapAlloc(a3, 0x40u, 0x44u);
  *a1 = v14;
  if ( !v14 )
  {
LABEL_16:
    v10 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v21, L"AllocateAndGetIpForwardTable : error %d allocating %d bytes", 14, pdwSize);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C650,
          &v21,
          v16,
          0,
          &v17);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpForwardTable : error %d allocating %d bytes");
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
    if ( qword_18004C658 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C658,
        L"AllocateAndGetIpForwardTable End",
        v16,
        0,
        &v17);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable End");
  }
  return v10;
}

```

## disassembly

```asm
0x180031190  mov     [rsp-8+arg_8], rbx
0x180031195  mov     [rsp-8+arg_18], rsi
0x18003119a  push    rbp
0x18003119b  push    rdi
0x18003119c  push    r12
0x18003119e  push    r14
0x1800311a0  push    r15
0x1800311a2  lea     rbp, [rsp-7A0h]
0x1800311aa  sub     rsp, 8A0h
0x1800311b1  mov     rax, cs:__security_cookie
0x1800311b8  xor     rax, rsp
0x1800311bb  mov     [rbp+7C0h+var_30], rax
0x1800311c2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800311c9  mov     r14, r8
0x1800311cc  mov     rdi, rcx
0x1800311cf  xor     r12d, r12d
0x1800311d2  lea     rcx, [rbp+7C0h+var_82C]; void *
0x1800311d6  xor     edx, edx; Val
0x1800311d8  mov     [rsp+8C0h+pdwSize], r12d
0x1800311dd  mov     r8d, 7FCh; Size
0x1800311e3  mov     [rbp+7C0h+var_830], r12d
0x1800311e7  movdqu  [rsp+8C0h+var_878], xmm0
0x1800311ed  call    memset_0
0x1800311f2  mov     rcx, cs:qword_18004C658
0x1800311f9  xorps   xmm0, xmm0
0x1800311fc  xor     eax, eax
0x1800311fe  mov     [rsp+8C0h+var_858], r12d
0x180031203  cmp     cs:qword_18004C648, r12
0x18003120a  movups  [rsp+8C0h+var_854], xmm0
0x18003120f  mov     [rbp+7C0h+var_834], eax
0x180031212  movups  [rsp+8C0h+var_844], xmm0
0x180031217  movups  [rsp+8C0h+var_868], xmm0
0x18003121c  jnz     short loc_18003122C
0x18003121e  cmp     cs:qword_18004C650, r12
0x180031225  jnz     short loc_18003122C
0x180031227  test    rcx, rcx
0x18003122a  jz      short loc_18003123E
0x18003122c  lea     rdx, [rsp+8C0h+var_878]
0x180031231  call    NsiGetRoutingDomainIdForCompartment
0x180031236  test    eax, eax
0x180031238  jnz     loc_180031509
0x18003123e  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180031245  jz      short loc_180031285
0x180031247  test    rcx, rcx
0x18003124a  jz      short loc_180031291
0x18003124c  lea     rax, [rsp+8C0h+var_858]
0x180031251  mov     word ptr [rsp+8C0h+var_858], r12w
0x180031257  mov     [rsp+8C0h+var_898], rax
0x18003125c  lea     r9, [rsp+8C0h+var_878]
0x180031261  mov     rax, cs:gIphlpParamTemplateFunc
0x180031268  lea     r8, aAllocateandget_20; "AllocateAndGetIpForwardTable Begin"
0x18003126f  mov     rdx, rcx
0x180031272  mov     [rsp+8C0h+var_8A0], r12
0x180031277  mov     rcx, cs:gIphlpEtwContext
0x18003127e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031283  jmp     short loc_180031291
0x180031285  lea     rcx, aAllocateandget_19; "AllocateAndGetIpForwardTable Begin"
0x18003128c  call    TraceHlp
0x180031291  mov     [rdi], r12
0x180031294  call    cs:__imp_GetCurrentThreadCompartmentId
0x18003129a  mov     esi, 1
0x18003129f  mov     r15d, eax
0x1800312a2  mov     ecx, esi; CompartmentId
0x1800312a4  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800312aa  mov     ebx, eax
0x1800312ac  test    eax, eax
0x1800312ae  jnz     loc_1800313CA
0x1800312b4  xor     r8d, r8d; bOrder
0x1800312b7  mov     [rsp+8C0h+pdwSize], r12d
0x1800312bc  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x1800312c1  xor     ecx, ecx; pIpForwardTable
0x1800312c3  call    cs:__imp_GetIpForwardTable
0x1800312c9  mov     ebx, eax
0x1800312cb  cmp     eax, 7Ah ; 'z'
0x1800312ce  jz      short loc_1800312FE
0x1800312d0  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800312d7  jz      short loc_1800312F2
0x1800312d9  cmp     cs:qword_18004C650, r12
0x1800312e0  jz      loc_18003143F
0x1800312e6  lea     rdx, aAllocateandget_14; "AllocateAndGetIpForwardTable : error %d"...
0x1800312ed  jmp     loc_1800313E6
0x1800312f2  lea     rcx, aAllocateandget_9; "AllocateAndGetIpForwardTable : error %d"...
0x1800312f9  jmp     loc_180031438
0x1800312fe  mov     eax, [rsp+8C0h+pdwSize]
0x180031302  mov     edx, 40h ; '@'; dwFlags
0x180031307  add     eax, 118h
0x18003130c  mov     rcx, r14; hHeap
0x18003130f  mov     r8d, eax; dwBytes
0x180031312  mov     [rsp+8C0h+pdwSize], eax
0x180031316  call    cs:__imp_HeapAlloc
0x18003131c  mov     [rdi], rax
0x18003131f  test    rax, rax
0x180031322  jnz     loc_1800313B5
0x180031328  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18003132f  mov     ebx, 0Eh
0x180031334  jz      short loc_18003139D
0x180031336  cmp     cs:qword_18004C650, r12
0x18003133d  jz      loc_18003148D
0x180031343  mov     r9d, [rsp+8C0h+pdwSize]
0x180031348  lea     rdx, aAllocateandget_3; "AllocateAndGetIpForwardTable : error %d"...
0x18003134f  mov     r8d, ebx
0x180031352  mov     word ptr [rbp+7C0h+var_830], r12w
0x180031357  lea     rcx, [rbp+7C0h+var_830]
0x18003135b  mov     word ptr [rsp+8C0h+var_858], r12w
0x180031361  call    FormatRRASErrorString
0x180031366  mov     rdx, cs:qword_18004C650
0x18003136d  lea     rax, [rsp+8C0h+var_858]
0x180031372  mov     rcx, cs:gIphlpEtwContext
0x180031379  lea     r9, [rsp+8C0h+var_878]
0x18003137e  mov     [rsp+8C0h+var_898], rax
0x180031383  lea     r8, [rbp+7C0h+var_830]
0x180031387  mov     rax, cs:gIphlpParamTemplateFunc
0x18003138e  mov     [rsp+8C0h+var_8A0], r12
0x180031393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031398  jmp     loc_18003148D
0x18003139d  mov     r8d, [rsp+8C0h+pdwSize]
0x1800313a2  lea     rcx, aAllocateandget_0; "AllocateAndGetIpForwardTable : error %d"...
0x1800313a9  mov     edx, ebx
0x1800313ab  call    TraceHlp
0x1800313b0  jmp     loc_18003148D
0x1800313b5  xor     r8d, r8d; bOrder
0x1800313b8  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x1800313bd  mov     rcx, rax; pIpForwardTable
0x1800313c0  call    cs:__imp_GetIpForwardTable
0x1800313c6  mov     ebx, eax
0x1800313c8  jmp     short loc_18003143F
0x1800313ca  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800313d1  mov     esi, r12d
0x1800313d4  jz      short loc_180031431
0x1800313d6  cmp     cs:qword_18004C650, r12
0x1800313dd  jz      short loc_18003143F
0x1800313df  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x1800313e6  mov     r8d, eax
0x1800313e9  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800313ef  lea     rcx, [rbp+7C0h+var_830]
0x1800313f3  mov     word ptr [rbp+7C0h+var_830], r12w
0x1800313f8  call    FormatRRASErrorString
0x1800313fd  mov     rdx, cs:qword_18004C650
0x180031404  lea     rax, [rsp+8C0h+var_858]
0x180031409  mov     rcx, cs:gIphlpEtwContext
0x180031410  lea     r9, [rsp+8C0h+var_878]
0x180031415  mov     [rsp+8C0h+var_898], rax
0x18003141a  lea     r8, [rbp+7C0h+var_830]
0x18003141e  mov     rax, cs:gIphlpParamTemplateFunc
0x180031425  mov     [rsp+8C0h+var_8A0], r12
0x18003142a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003142f  jmp     short loc_18003143F
0x180031431  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x180031438  mov     edx, eax
0x18003143a  call    TraceHlp
0x18003143f  cmp     ebx, 0E8h
0x180031445  jnz     short loc_180031489
0x180031447  mov     r8, [rdi]; lpMem
0x18003144a  test    r8, r8
0x18003144d  jz      short loc_18003145D
0x18003144f  xor     edx, edx; dwFlags
0x180031451  mov     rcx, r14; hHeap
0x180031454  call    cs:__imp_HeapFree
0x18003145a  mov     [rdi], r12
0x18003145d  mov     r8d, 44h ; 'D'; dwBytes
0x180031463  mov     rcx, r14; hHeap
0x180031466  mov     [rsp+8C0h+pdwSize], r8d
0x18003146b  lea     edx, [r8-4]; dwFlags
0x18003146f  call    cs:__imp_HeapAlloc
0x180031475  mov     [rdi], rax
0x180031478  test    rax, rax
0x18003147b  jz      loc_180031328
0x180031481  mov     [rax], r12d
0x180031484  mov     ebx, r12d
0x180031487  jmp     short loc_1800314A3
0x180031489  test    ebx, ebx
0x18003148b  jz      short loc_1800314A3
0x18003148d  mov     r8, [rdi]; lpMem
0x180031490  test    r8, r8
0x180031493  jz      short loc_1800314A3
0x180031495  xor     edx, edx; dwFlags
0x180031497  mov     rcx, r14; hHeap
0x18003149a  call    cs:__imp_HeapFree
0x1800314a0  mov     [rdi], r12
0x1800314a3  test    esi, esi
0x1800314a5  jz      short loc_1800314B0
0x1800314a7  mov     ecx, r15d; CompartmentId
0x1800314aa  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800314b0  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800314b7  jz      short loc_1800314FB
0x1800314b9  mov     rdx, cs:qword_18004C658
0x1800314c0  test    rdx, rdx
0x1800314c3  jz      short loc_180031507
0x1800314c5  mov     rcx, cs:gIphlpEtwContext
0x1800314cc  lea     rax, [rsp+8C0h+var_858]
0x1800314d1  mov     [rsp+8C0h+var_898], rax
0x1800314d6  lea     r9, [rsp+8C0h+var_878]
0x1800314db  mov     rax, cs:gIphlpParamTemplateFunc
0x1800314e2  lea     r8, aAllocateandget_8; "AllocateAndGetIpForwardTable End"
0x1800314e9  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800314ef  mov     [rsp+8C0h+var_8A0], r12
0x1800314f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314f9  jmp     short loc_180031507
0x1800314fb  lea     rcx, aAllocateandget_2; "AllocateAndGetIpForwardTable End"
0x180031502  call    TraceHlp
0x180031507  mov     eax, ebx
0x180031509  mov     rcx, [rbp+7C0h+var_30]
0x180031510  xor     rcx, rsp; StackCookie
0x180031513  call    __security_check_cookie
0x180031518  lea     r11, [rsp+8C0h+var_20]
0x180031520  mov     rbx, [r11+38h]
0x180031524  mov     rsi, [r11+48h]
0x180031528  mov     rsp, r11
0x18003152b  pop     r15
0x18003152d  pop     r14
0x18003152f  pop     r12
0x180031531  pop     rdi
0x180031532  pop     rbp
0x180031533  retn
```
