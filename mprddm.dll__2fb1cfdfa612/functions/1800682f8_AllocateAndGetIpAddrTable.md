# AllocateAndGetIpAddrTable

- ea: `0x1800682f8`
- end: `0x1800686b5`
- name: `AllocateAndGetIpAddrTable`
- size: `957`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800689f0`
- `0x1800692b4`

## callees

- `0x1800682f8`
- `0x180069984`
- `0x180071cec`
- `0x1800759b8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180068496`
- `KERNEL32!HeapAlloc` at `0x1800685ef`
- `KERNEL32!HeapAlloc` at `0x180068496`
- `KERNEL32!HeapAlloc` at `0x1800685ef`
- `KERNEL32!HeapFree` at `0x1800685d4`
- `KERNEL32!HeapFree` at `0x18006861a`
- `KERNEL32!HeapFree` at `0x1800685d4`
- `KERNEL32!HeapFree` at `0x18006861a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180068426`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006862b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180068426`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006862b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006841b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006841b`
- `IPHLPAPI!GetIpAddrTable` at `0x180068445`
- `IPHLPAPI!GetIpAddrTable` at `0x180068540`
- `IPHLPAPI!GetIpAddrTable` at `0x180068445`
- `IPHLPAPI!GetIpAddrTable` at `0x180068540`

## string_xrefs

- `0x18006855f`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x1800685b1`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpAddrTable(
        LPVOID *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        NET_IF_COMPARTMENT_ID CompartmentId)
{
  int v7; // r14d
  __int64 v8; // rdx
  __int64 result; // rax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  DWORD IpAddrTable; // eax
  DWORD v12; // ebx
  const wchar_t *v13; // rdx
  const CHAR *v14; // rcx
  struct _MIB_IPADDRTABLE *v15; // rax
  _DWORD *v16; // rax
  ULONG pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+6Ch] [rbp-94h]
  __int128 v21; // [rsp+7Ch] [rbp-84h]
  int v22; // [rsp+8Ch] [rbp-74h]
  int v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwSize = 0;
  v23 = 0;
  memset(v18, 0, sizeof(v18));
  memset_0(v24, 0, sizeof(v24));
  v7 = 1;
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  if ( CompartmentId != 1 && unk_1800CA080 || xmmword_1800CA088 != 0 || (v8 = unk_1800CA098) != 0 )
  {
    result = NsiGetRoutingDomainIdForCompartment(CompartmentId, v18);
    if ( (_DWORD)result )
      return result;
    v8 = unk_1800CA098;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v19) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v8,
        L"AllocateAndGetIpAddrTable Begin",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable Begin");
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpAddrTable = SetCurrentThreadCompartmentId(CompartmentId);
  v12 = IpAddrTable;
  if ( IpAddrTable )
  {
    v7 = 0;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800CA088 + 1) )
        goto LABEL_29;
      v13 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
      goto LABEL_26;
    }
    v14 = "AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_28;
  }
  pdwSize = 0;
  IpAddrTable = GetIpAddrTable(0, &pdwSize, 0);
  v12 = IpAddrTable;
  if ( IpAddrTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800CA088 + 1) )
        goto LABEL_29;
      v13 = L"AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_26:
      LOWORD(v19) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, v13, IpAddrTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800CA088 + 1),
        &v23,
        v18,
        0,
        &v19);
      goto LABEL_29;
    }
    v14 = "AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_28:
    TraceHlp(v14);
    goto LABEL_29;
  }
  pdwSize += 120;
  v15 = (struct _MIB_IPADDRTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v15;
  if ( !v15 )
    goto LABEL_18;
  v12 = GetIpAddrTable(v15, &pdwSize, 0);
LABEL_29:
  if ( v12 != 232 )
  {
    if ( !v12 )
      goto LABEL_37;
LABEL_35:
    if ( *a1 )
    {
      HeapFree(a3, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_37;
  }
  if ( *a1 )
  {
    HeapFree(a3, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 36;
  v16 = HeapAlloc(a3, 0x40u, 0x24u);
  *a1 = v16;
  if ( !v16 )
  {
LABEL_18:
    v12 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
      {
        LOWORD(v23) = 0;
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v23, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800CA088 + 1),
          &v23,
          v18,
          0,
          &v19);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpAddrTable : error %d allocating %d bytes");
    }
    goto LABEL_35;
  }
  *v16 = 0;
  v12 = 0;
LABEL_37:
  if ( v7 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( unk_1800CA098 )
    {
      LOWORD(v19) = 0;
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800CA098,
        L"AllocateAndGetIpAddrTable End",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable End");
  }
  return v12;
}

```

## disassembly

```asm
0x1800682f8  mov     [rsp-8+arg_8], rbx
0x1800682fd  mov     [rsp-8+arg_18], rsi
0x180068302  push    rbp
0x180068303  push    rdi
0x180068304  push    r12
0x180068306  push    r14
0x180068308  push    r15
0x18006830a  lea     rbp, [rsp-7A0h]
0x180068312  sub     rsp, 8A0h
0x180068319  mov     rax, cs:__security_cookie
0x180068320  xor     rax, rsp
0x180068323  mov     [rbp+7C0h+var_30], rax
0x18006832a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180068331  mov     rsi, r8
0x180068334  mov     rdi, rcx
0x180068337  xor     r12d, r12d
0x18006833a  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18006833e  xor     edx, edx; Val
0x180068340  mov     [rsp+8C0h+pdwSize], r12d
0x180068345  mov     r8d, 7FCh; Size
0x18006834b  mov     [rbp+7C0h+var_830], r12d
0x18006834f  movdqu  [rsp+8C0h+var_878], xmm0
0x180068355  call    memset_0
0x18006835a  mov     ebx, [rbp+7C0h+CompartmentId]
0x180068360  lea     r14d, [r12+1]
0x180068365  xorps   xmm0, xmm0
0x180068368  mov     [rsp+8C0h+var_858], r12d
0x18006836d  xor     eax, eax
0x18006836f  mov     [rbp+7C0h+var_834], eax
0x180068372  movups  [rsp+8C0h+var_854], xmm0
0x180068377  movups  [rsp+8C0h+var_844], xmm0
0x18006837c  movups  [rsp+8C0h+var_868], xmm0
0x180068381  cmp     ebx, r14d
0x180068384  jz      short loc_18006838F
0x180068386  cmp     qword ptr cs:unk_1800CA080, r12
0x18006838d  jnz     short loc_1800683AD
0x18006838f  cmp     qword ptr cs:xmmword_1800CA088, r12
0x180068396  jnz     short loc_1800683AD
0x180068398  cmp     qword ptr cs:xmmword_1800CA088+8, r12
0x18006839f  jnz     short loc_1800683AD
0x1800683a1  mov     rdx, qword ptr cs:unk_1800CA098
0x1800683a8  test    rdx, rdx
0x1800683ab  jz      short loc_1800683C8
0x1800683ad  lea     rdx, [rsp+8C0h+var_878]
0x1800683b2  mov     ecx, ebx
0x1800683b4  call    NsiGetRoutingDomainIdForCompartment
0x1800683b9  test    eax, eax
0x1800683bb  jnz     loc_18006868A
0x1800683c1  mov     rdx, qword ptr cs:unk_1800CA098
0x1800683c8  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800683cf  jz      short loc_18006840C
0x1800683d1  test    rdx, rdx
0x1800683d4  jz      short loc_180068418
0x1800683d6  mov     rcx, cs:gIphlpEtwContext
0x1800683dd  lea     rax, [rsp+8C0h+var_858]
0x1800683e2  mov     [rsp+8C0h+var_898], rax
0x1800683e7  lea     r9, [rsp+8C0h+var_878]
0x1800683ec  mov     rax, cs:gIphlpParamTemplateFunc
0x1800683f3  lea     r8, aAllocateandget_10; "AllocateAndGetIpAddrTable Begin"
0x1800683fa  mov     word ptr [rsp+8C0h+var_858], r12w
0x180068400  mov     [rsp+8C0h+var_8A0], r12
0x180068405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006840a  jmp     short loc_180068418
0x18006840c  lea     rcx, aAllocateandget_4; "AllocateAndGetIpAddrTable Begin"
0x180068413  call    TraceHlp
0x180068418  mov     [rdi], r12
0x18006841b  call    cs:__imp_GetCurrentThreadCompartmentId
0x180068421  mov     ecx, ebx; CompartmentId
0x180068423  mov     r15d, eax
0x180068426  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006842c  mov     ebx, eax
0x18006842e  test    eax, eax
0x180068430  jnz     loc_18006854A
0x180068436  xor     r8d, r8d; bOrder
0x180068439  mov     [rsp+8C0h+pdwSize], r12d
0x18006843e  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x180068443  xor     ecx, ecx; pIpAddrTable
0x180068445  call    cs:__imp_GetIpAddrTable
0x18006844b  mov     ebx, eax
0x18006844d  cmp     eax, 7Ah ; 'z'
0x180068450  jz      short loc_180068480
0x180068452  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180068459  jz      short loc_180068474
0x18006845b  cmp     qword ptr cs:xmmword_1800CA088+8, r12
0x180068462  jz      loc_1800685BF
0x180068468  lea     rdx, aAllocateandget_7; "AllocateAndGetIpNetTable : error %d get"...
0x18006846f  jmp     loc_180068566
0x180068474  lea     rcx, aAllocateandget_5; "AllocateAndGetIpNetTable : error %d get"...
0x18006847b  jmp     loc_1800685B8
0x180068480  mov     eax, [rsp+8C0h+pdwSize]
0x180068484  mov     edx, 40h ; '@'; dwFlags
0x180068489  add     eax, 78h ; 'x'
0x18006848c  mov     rcx, rsi; hHeap
0x18006848f  mov     r8d, eax; dwBytes
0x180068492  mov     [rsp+8C0h+pdwSize], eax
0x180068496  call    cs:__imp_HeapAlloc
0x18006849c  mov     [rdi], rax
0x18006849f  test    rax, rax
0x1800684a2  jnz     loc_180068535
0x1800684a8  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x1800684af  mov     ebx, 0Eh
0x1800684b4  jz      short loc_18006851D
0x1800684b6  cmp     qword ptr cs:xmmword_1800CA088+8, r12
0x1800684bd  jz      loc_18006860D
0x1800684c3  mov     r9d, [rsp+8C0h+pdwSize]
0x1800684c8  lea     rdx, aAllocateandget_3; "AllocateAndGetIpAddrTable : error %d al"...
0x1800684cf  mov     r8d, ebx
0x1800684d2  mov     word ptr [rbp+7C0h+var_830], r12w
0x1800684d7  lea     rcx, [rbp+7C0h+var_830]
0x1800684db  mov     word ptr [rsp+8C0h+var_858], r12w
0x1800684e1  call    FormatRRASErrorString
0x1800684e6  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x1800684ed  lea     rax, [rsp+8C0h+var_858]
0x1800684f2  mov     rcx, cs:gIphlpEtwContext
0x1800684f9  lea     r9, [rsp+8C0h+var_878]
0x1800684fe  mov     [rsp+8C0h+var_898], rax
0x180068503  lea     r8, [rbp+7C0h+var_830]
0x180068507  mov     rax, cs:gIphlpParamTemplateFunc
0x18006850e  mov     [rsp+8C0h+var_8A0], r12
0x180068513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068518  jmp     loc_18006860D
0x18006851d  mov     r8d, [rsp+8C0h+pdwSize]
0x180068522  lea     rcx, aAllocateandget_1; "AllocateAndGetIpAddrTable : error %d al"...
0x180068529  mov     edx, ebx
0x18006852b  call    TraceHlp
0x180068530  jmp     loc_18006860D
0x180068535  xor     r8d, r8d; bOrder
0x180068538  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006853d  mov     rcx, rax; pIpAddrTable
0x180068540  call    cs:__imp_GetIpAddrTable
0x180068546  mov     ebx, eax
0x180068548  jmp     short loc_1800685BF
0x18006854a  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180068551  mov     r14d, r12d
0x180068554  jz      short loc_1800685B1
0x180068556  cmp     qword ptr cs:xmmword_1800CA088+8, r12
0x18006855d  jz      short loc_1800685BF
0x18006855f  lea     rdx, aAllocateandget_0; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x180068566  mov     r8d, eax
0x180068569  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006856f  lea     rcx, [rbp+7C0h+var_830]
0x180068573  mov     word ptr [rbp+7C0h+var_830], r12w
0x180068578  call    FormatRRASErrorString
0x18006857d  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068584  lea     rax, [rsp+8C0h+var_858]
0x180068589  mov     rcx, cs:gIphlpEtwContext
0x180068590  lea     r9, [rsp+8C0h+var_878]
0x180068595  mov     [rsp+8C0h+var_898], rax
0x18006859a  lea     r8, [rbp+7C0h+var_830]
0x18006859e  mov     rax, cs:gIphlpParamTemplateFunc
0x1800685a5  mov     [rsp+8C0h+var_8A0], r12
0x1800685aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685af  jmp     short loc_1800685BF
0x1800685b1  lea     rcx, aAllocateandget_6; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x1800685b8  mov     edx, eax
0x1800685ba  call    TraceHlp
0x1800685bf  cmp     ebx, 0E8h
0x1800685c5  jnz     short loc_180068609
0x1800685c7  mov     r8, [rdi]; lpMem
0x1800685ca  test    r8, r8
0x1800685cd  jz      short loc_1800685DD
0x1800685cf  xor     edx, edx; dwFlags
0x1800685d1  mov     rcx, rsi; hHeap
0x1800685d4  call    cs:__imp_HeapFree
0x1800685da  mov     [rdi], r12
0x1800685dd  mov     r8d, 24h ; '$'; dwBytes
0x1800685e3  mov     rcx, rsi; hHeap
0x1800685e6  mov     [rsp+8C0h+pdwSize], r8d
0x1800685eb  lea     edx, [r8+1Ch]; dwFlags
0x1800685ef  call    cs:__imp_HeapAlloc
0x1800685f5  mov     [rdi], rax
0x1800685f8  test    rax, rax
0x1800685fb  jz      loc_1800684A8
0x180068601  mov     [rax], r12d
0x180068604  mov     ebx, r12d
0x180068607  jmp     short loc_180068623
0x180068609  test    ebx, ebx
0x18006860b  jz      short loc_180068623
0x18006860d  mov     r8, [rdi]; lpMem
0x180068610  test    r8, r8
0x180068613  jz      short loc_180068623
0x180068615  xor     edx, edx; dwFlags
0x180068617  mov     rcx, rsi; hHeap
0x18006861a  call    cs:__imp_HeapFree
0x180068620  mov     [rdi], r12
0x180068623  test    r14d, r14d
0x180068626  jz      short loc_180068631
0x180068628  mov     ecx, r15d; CompartmentId
0x18006862b  call    cs:__imp_SetCurrentThreadCompartmentId
0x180068631  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x180068638  jz      short loc_18006867C
0x18006863a  mov     rdx, qword ptr cs:unk_1800CA098
0x180068641  test    rdx, rdx
0x180068644  jz      short loc_180068688
0x180068646  mov     rcx, cs:gIphlpEtwContext
0x18006864d  lea     rax, [rsp+8C0h+var_858]
0x180068652  mov     [rsp+8C0h+var_898], rax
0x180068657  lea     r9, [rsp+8C0h+var_878]
0x18006865c  mov     rax, cs:gIphlpParamTemplateFunc
0x180068663  lea     r8, aAllocateandget_9; "AllocateAndGetIpAddrTable End"
0x18006866a  mov     word ptr [rsp+8C0h+var_858], r12w
0x180068670  mov     [rsp+8C0h+var_8A0], r12
0x180068675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006867a  jmp     short loc_180068688
0x18006867c  lea     rcx, aAllocateandget; "AllocateAndGetIpAddrTable End"
0x180068683  call    TraceHlp
0x180068688  mov     eax, ebx
0x18006868a  mov     rcx, [rbp+7C0h+var_30]
0x180068691  xor     rcx, rsp; StackCookie
0x180068694  call    __security_check_cookie
0x180068699  lea     r11, [rsp+8C0h+var_20]
0x1800686a1  mov     rbx, [r11+38h]
0x1800686a5  mov     rsi, [r11+48h]
0x1800686a9  mov     rsp, r11
0x1800686ac  pop     r15
0x1800686ae  pop     r14
0x1800686b0  pop     r12
0x1800686b2  pop     rdi
0x1800686b3  pop     rbp
0x1800686b4  retn
```
