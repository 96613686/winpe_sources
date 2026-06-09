# AllocateAndGetIpAddrTable

- ea: `0x180030de8`
- end: `0x18003118a`
- name: `AllocateAndGetIpAddrTable`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031d0c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002cbb4`
- `0x180030da4`
- `0x180030de8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030f6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800310c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030f6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800310c5`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180030efc`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180031100`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180030efc`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180031100`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180030eec`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180030eec`
- `IPHLPAPI!GetIpAddrTable` at `0x180030f1b`
- `IPHLPAPI!GetIpAddrTable` at `0x180031016`
- `IPHLPAPI!GetIpAddrTable` at `0x180030f1b`
- `IPHLPAPI!GetIpAddrTable` at `0x180031016`

## string_xrefs

- `0x180031035`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180031087`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

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
      if ( !qword_18004C650 )
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
      if ( !qword_18004C650 )
        goto LABEL_27;
      v11 = L"AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_24:
      LOWORD(v17) = 0;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, v11, IpAddrTable);
      ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C650,
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
      if ( qword_18004C650 )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v21, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize);
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
    if ( qword_18004C658 )
    {
      LOWORD(v17) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C658,
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
0x180030de8  mov     [rsp-8+arg_8], rbx
0x180030ded  mov     [rsp-8+arg_18], rsi
0x180030df2  push    rbp
0x180030df3  push    rdi
0x180030df4  push    r12
0x180030df6  push    r14
0x180030df8  push    r15
0x180030dfa  lea     rbp, [rsp-7A0h]
0x180030e02  sub     rsp, 8A0h
0x180030e09  mov     rax, cs:__security_cookie
0x180030e10  xor     rax, rsp
0x180030e13  mov     [rbp+7C0h+var_30], rax
0x180030e1a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180030e21  mov     r14, r8
0x180030e24  mov     rdi, rcx
0x180030e27  xor     r12d, r12d
0x180030e2a  lea     rcx, [rbp+7C0h+var_82C]; void *
0x180030e2e  xor     edx, edx; Val
0x180030e30  mov     [rsp+8C0h+pdwSize], r12d
0x180030e35  mov     r8d, 7FCh; Size
0x180030e3b  mov     [rbp+7C0h+var_830], r12d
0x180030e3f  movdqu  [rsp+8C0h+var_878], xmm0
0x180030e45  call    memset_0
0x180030e4a  mov     rcx, cs:qword_18004C658
0x180030e51  xorps   xmm0, xmm0
0x180030e54  xor     eax, eax
0x180030e56  mov     [rsp+8C0h+var_858], r12d
0x180030e5b  cmp     cs:qword_18004C648, r12
0x180030e62  movups  [rsp+8C0h+var_854], xmm0
0x180030e67  mov     [rbp+7C0h+var_834], eax
0x180030e6a  movups  [rsp+8C0h+var_844], xmm0
0x180030e6f  movups  [rsp+8C0h+var_868], xmm0
0x180030e74  jnz     short loc_180030E84
0x180030e76  cmp     cs:qword_18004C650, r12
0x180030e7d  jnz     short loc_180030E84
0x180030e7f  test    rcx, rcx
0x180030e82  jz      short loc_180030E96
0x180030e84  lea     rdx, [rsp+8C0h+var_878]
0x180030e89  call    NsiGetRoutingDomainIdForCompartment
0x180030e8e  test    eax, eax
0x180030e90  jnz     loc_18003115F
0x180030e96  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180030e9d  jz      short loc_180030EDD
0x180030e9f  test    rcx, rcx
0x180030ea2  jz      short loc_180030EE9
0x180030ea4  lea     rax, [rsp+8C0h+var_858]
0x180030ea9  mov     word ptr [rsp+8C0h+var_858], r12w
0x180030eaf  mov     [rsp+8C0h+var_898], rax
0x180030eb4  lea     r9, [rsp+8C0h+var_878]
0x180030eb9  mov     rax, cs:gIphlpParamTemplateFunc
0x180030ec0  lea     r8, aAllocateandget_18; "AllocateAndGetIpAddrTable Begin"
0x180030ec7  mov     rdx, rcx
0x180030eca  mov     [rsp+8C0h+var_8A0], r12
0x180030ecf  mov     rcx, cs:gIphlpEtwContext
0x180030ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030edb  jmp     short loc_180030EE9
0x180030edd  lea     rcx, aAllocateandget_11; "AllocateAndGetIpAddrTable Begin"
0x180030ee4  call    TraceHlp
0x180030ee9  mov     [rdi], r12
0x180030eec  call    cs:__imp_GetCurrentThreadCompartmentId
0x180030ef2  mov     esi, 1
0x180030ef7  mov     r15d, eax
0x180030efa  mov     ecx, esi; CompartmentId
0x180030efc  call    cs:__imp_SetCurrentThreadCompartmentId
0x180030f02  mov     ebx, eax
0x180030f04  test    eax, eax
0x180030f06  jnz     loc_180031020
0x180030f0c  xor     r8d, r8d; bOrder
0x180030f0f  mov     [rsp+8C0h+pdwSize], r12d
0x180030f14  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180030f19  xor     ecx, ecx; pIpAddrTable
0x180030f1b  call    cs:__imp_GetIpAddrTable
0x180030f21  mov     ebx, eax
0x180030f23  cmp     eax, 7Ah ; 'z'
0x180030f26  jz      short loc_180030F56
0x180030f28  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180030f2f  jz      short loc_180030F4A
0x180030f31  cmp     cs:qword_18004C650, r12
0x180030f38  jz      loc_180031095
0x180030f3e  lea     rdx, aAllocateandget_15; "AllocateAndGetIpNetTable : error %d get"...
0x180030f45  jmp     loc_18003103C
0x180030f4a  lea     rcx, aAllocateandget_12; "AllocateAndGetIpNetTable : error %d get"...
0x180030f51  jmp     loc_18003108E
0x180030f56  mov     eax, [rsp+8C0h+pdwSize]
0x180030f5a  mov     edx, 40h ; '@'; dwFlags
0x180030f5f  add     eax, 78h ; 'x'
0x180030f62  mov     rcx, r14; hHeap
0x180030f65  mov     r8d, eax; dwBytes
0x180030f68  mov     [rsp+8C0h+pdwSize], eax
0x180030f6c  call    cs:__imp_HeapAlloc
0x180030f72  mov     [rdi], rax
0x180030f75  test    rax, rax
0x180030f78  jnz     loc_18003100B
0x180030f7e  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180030f85  mov     ebx, 0Eh
0x180030f8a  jz      short loc_180030FF3
0x180030f8c  cmp     cs:qword_18004C650, r12
0x180030f93  jz      loc_1800310E3
0x180030f99  mov     r9d, [rsp+8C0h+pdwSize]
0x180030f9e  lea     rdx, aAllocateandget_10; "AllocateAndGetIpAddrTable : error %d al"...
0x180030fa5  mov     r8d, ebx
0x180030fa8  mov     word ptr [rbp+7C0h+var_830], r12w
0x180030fad  lea     rcx, [rbp+7C0h+var_830]
0x180030fb1  mov     word ptr [rsp+8C0h+var_858], r12w
0x180030fb7  call    FormatRRASErrorString
0x180030fbc  mov     rdx, cs:qword_18004C650
0x180030fc3  lea     rax, [rsp+8C0h+var_858]
0x180030fc8  mov     rcx, cs:gIphlpEtwContext
0x180030fcf  lea     r9, [rsp+8C0h+var_878]
0x180030fd4  mov     [rsp+8C0h+var_898], rax
0x180030fd9  lea     r8, [rbp+7C0h+var_830]
0x180030fdd  mov     rax, cs:gIphlpParamTemplateFunc
0x180030fe4  mov     [rsp+8C0h+var_8A0], r12
0x180030fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fee  jmp     loc_1800310E3
0x180030ff3  mov     r8d, [rsp+8C0h+pdwSize]
0x180030ff8  lea     rcx, aAllocateandget_5; "AllocateAndGetIpAddrTable : error %d al"...
0x180030fff  mov     edx, ebx
0x180031001  call    TraceHlp
0x180031006  jmp     loc_1800310E3
0x18003100b  xor     r8d, r8d; bOrder
0x18003100e  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180031013  mov     rcx, rax; pIpAddrTable
0x180031016  call    cs:__imp_GetIpAddrTable
0x18003101c  mov     ebx, eax
0x18003101e  jmp     short loc_180031095
0x180031020  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180031027  mov     esi, r12d
0x18003102a  jz      short loc_180031087
0x18003102c  cmp     cs:qword_18004C650, r12
0x180031033  jz      short loc_180031095
0x180031035  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18003103c  mov     r8d, eax
0x18003103f  mov     word ptr [rsp+8C0h+var_858], r12w
0x180031045  lea     rcx, [rbp+7C0h+var_830]
0x180031049  mov     word ptr [rbp+7C0h+var_830], r12w
0x18003104e  call    FormatRRASErrorString
0x180031053  mov     rdx, cs:qword_18004C650
0x18003105a  lea     rax, [rsp+8C0h+var_858]
0x18003105f  mov     rcx, cs:gIphlpEtwContext
0x180031066  lea     r9, [rsp+8C0h+var_878]
0x18003106b  mov     [rsp+8C0h+var_898], rax
0x180031070  lea     r8, [rbp+7C0h+var_830]
0x180031074  mov     rax, cs:gIphlpParamTemplateFunc
0x18003107b  mov     [rsp+8C0h+var_8A0], r12
0x180031080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031085  jmp     short loc_180031095
0x180031087  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18003108e  mov     edx, eax
0x180031090  call    TraceHlp
0x180031095  cmp     ebx, 0E8h
0x18003109b  jnz     short loc_1800310DF
0x18003109d  mov     r8, [rdi]; lpMem
0x1800310a0  test    r8, r8
0x1800310a3  jz      short loc_1800310B3
0x1800310a5  xor     edx, edx; dwFlags
0x1800310a7  mov     rcx, r14; hHeap
0x1800310aa  call    cs:__imp_HeapFree
0x1800310b0  mov     [rdi], r12
0x1800310b3  mov     r8d, 24h ; '$'; dwBytes
0x1800310b9  mov     rcx, r14; hHeap
0x1800310bc  mov     [rsp+8C0h+pdwSize], r8d
0x1800310c1  lea     edx, [r8+1Ch]; dwFlags
0x1800310c5  call    cs:__imp_HeapAlloc
0x1800310cb  mov     [rdi], rax
0x1800310ce  test    rax, rax
0x1800310d1  jz      loc_180030F7E
0x1800310d7  mov     [rax], r12d
0x1800310da  mov     ebx, r12d
0x1800310dd  jmp     short loc_1800310F9
0x1800310df  test    ebx, ebx
0x1800310e1  jz      short loc_1800310F9
0x1800310e3  mov     r8, [rdi]; lpMem
0x1800310e6  test    r8, r8
0x1800310e9  jz      short loc_1800310F9
0x1800310eb  xor     edx, edx; dwFlags
0x1800310ed  mov     rcx, r14; hHeap
0x1800310f0  call    cs:__imp_HeapFree
0x1800310f6  mov     [rdi], r12
0x1800310f9  test    esi, esi
0x1800310fb  jz      short loc_180031106
0x1800310fd  mov     ecx, r15d; CompartmentId
0x180031100  call    cs:__imp_SetCurrentThreadCompartmentId
0x180031106  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18003110d  jz      short loc_180031151
0x18003110f  mov     rdx, cs:qword_18004C658
0x180031116  test    rdx, rdx
0x180031119  jz      short loc_18003115D
0x18003111b  mov     rcx, cs:gIphlpEtwContext
0x180031122  lea     rax, [rsp+8C0h+var_858]
0x180031127  mov     [rsp+8C0h+var_898], rax
0x18003112c  lea     r9, [rsp+8C0h+var_878]
0x180031131  mov     rax, cs:gIphlpParamTemplateFunc
0x180031138  lea     r8, aAllocateandget_17; "AllocateAndGetIpAddrTable End"
0x18003113f  mov     word ptr [rsp+8C0h+var_858], r12w
0x180031145  mov     [rsp+8C0h+var_8A0], r12
0x18003114a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003114f  jmp     short loc_18003115D
0x180031151  lea     rcx, aAllocateandget; "AllocateAndGetIpAddrTable End"
0x180031158  call    TraceHlp
0x18003115d  mov     eax, ebx
0x18003115f  mov     rcx, [rbp+7C0h+var_30]
0x180031166  xor     rcx, rsp; StackCookie
0x180031169  call    __security_check_cookie
0x18003116e  lea     r11, [rsp+8C0h+var_20]
0x180031176  mov     rbx, [r11+38h]
0x18003117a  mov     rsi, [r11+48h]
0x18003117e  mov     rsp, r11
0x180031181  pop     r15
0x180031183  pop     r14
0x180031185  pop     r12
0x180031187  pop     rdi
0x180031188  pop     rbp
0x180031189  retn
```
