# RasSrvrActivateIpv6DoDSpecificRoute

- ea: `0x1800556f0`
- end: `0x18005596b`
- name: `RasSrvrActivateIpv6DoDSpecificRoute`
- size: `635`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800556f0`
- `0x1800755b8`
- `0x1800792f8`
- `0x180079428`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180055941`
- `KERNEL32!LeaveCriticalSection` at `0x180055941`
- `KERNEL32!EnterCriticalSection` at `0x18005577c`
- `KERNEL32!EnterCriticalSection` at `0x18005577c`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180055761`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180055761`

## string_xrefs

- `0x1800557a8`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x`
- `0x1800558b1`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x`
- `0x18005590c`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x`

## pseudocode

```c
__int64 __fastcall RasSrvrActivateIpv6DoDSpecificRoute(
        __int128 *a1,
        __int128 *a2,
        const NET_LUID *a3,
        unsigned __int8 a4)
{
  __int128 v4; // xmm0
  __int128 v6; // xmm1
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  ULONG InterfaceIndex; // [rsp+40h] [rbp-C0h] BYREF
  NET_LUID v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v4 = *a1;
  v6 = *a2;
  v7 = a4;
  v20 = 33022;
  InterfaceIndex = 0;
  v22 = v4;
  v24 = 0;
  v23 = v6;
  memset_0(v25, 0, sizeof(v25));
  v19.Value = a3->Value;
  if ( !ConvertInterfaceLuidToIndex(a3, &InterfaceIndex) )
  {
    EnterCriticalSection(&RasSrvrCriticalSection);
    v8 = CreateOrSetOrDeleteIpv6NeighborEntry(&v19, &v19, v7, &v23);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v24);
    }
    v9 = CreateOrSetOrDeleteIpv6NeighborEntry(&v19, &v19, v7, &v22);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v9);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v24);
    }
    v21 = *((_QWORD *)&v23 + 1);
    v10 = CreateOrSetOrDeleteIpv6NeighborEntry(&v19, &v19, v7, &v20);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v10);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v24);
    }
    v13 = CreateOrSetOrDeleteIpv6ForwardEntry(&v22, v11, v12, InterfaceIndex);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x",
        v13);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v24);
    }
    v21 = *((_QWORD *)&v22 + 1);
    v16 = CreateOrSetOrDeleteIpv6ForwardEntry(&v20, v14, v15, InterfaceIndex);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x",
        v16);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v24);
    }
    LeaveCriticalSection(&RasSrvrCriticalSection);
  }
  return 0;
}

```

## disassembly

```asm
0x1800556f0  push    rbp
0x1800556f2  push    rbx
0x1800556f3  push    rsi
0x1800556f4  push    rdi
0x1800556f5  lea     rbp, [rsp-798h]
0x1800556fd  sub     rsp, 898h
0x180055704  mov     rax, cs:__security_cookie
0x18005570b  xor     rax, rsp
0x18005570e  mov     [rbp+7B0h+var_30], rax
0x180055715  movups  xmm0, xmmword ptr [rcx]
0x180055718  mov     rbx, r8
0x18005571b  xor     esi, esi
0x18005571d  movups  xmm1, xmmword ptr [rdx]
0x180055720  xor     edx, edx; Val
0x180055722  movzx   edi, r9b
0x180055726  mov     r8d, 7FCh; Size
0x18005572c  mov     [rsp+8B0h+var_860], 80FEh
0x180055735  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180055739  mov     [rsp+8B0h+InterfaceIndex], esi
0x18005573d  movdqu  [rsp+8B0h+var_850], xmm0
0x180055743  mov     [rbp+7B0h+var_830], esi
0x180055746  movdqu  [rsp+8B0h+var_840], xmm1
0x18005574c  call    memset_0
0x180055751  mov     rax, [rbx]
0x180055754  lea     rdx, [rsp+8B0h+InterfaceIndex]; InterfaceIndex
0x180055759  mov     rcx, rbx; InterfaceLuid
0x18005575c  mov     [rsp+8B0h+var_868], rax
0x180055761  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180055768  nop     dword ptr [rax+rax+00h]
0x18005576d  test    eax, eax
0x18005576f  jnz     loc_18005594D
0x180055775  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005577c  call    cs:__imp_EnterCriticalSection
0x180055783  nop     dword ptr [rax+rax+00h]
0x180055788  lea     r9, [rsp+8B0h+var_840]
0x18005578d  mov     r8d, edi
0x180055790  lea     rdx, [rsp+8B0h+var_868]
0x180055795  mov     ebx, edi
0x180055797  lea     rcx, [rsp+8B0h+var_868]
0x18005579c  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x1800557a1  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x1800557a8  lea     rdi, aRassrvractivat; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x1800557af  jz      short loc_1800557E2
0x1800557b1  mov     r8d, eax
0x1800557b4  mov     word ptr [rbp+7B0h+var_830], si
0x1800557b8  mov     rdx, rdi
0x1800557bb  lea     rcx, [rbp+7B0h+var_830]
0x1800557bf  call    FormatRRASErrorString
0x1800557c4  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800557cb  lea     r8, [rbp+7B0h+var_830]
0x1800557cf  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800557d6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800557dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557e2  lea     r9, [rsp+8B0h+var_850]
0x1800557e7  mov     r8d, ebx
0x1800557ea  lea     rdx, [rsp+8B0h+var_868]
0x1800557ef  lea     rcx, [rsp+8B0h+var_868]
0x1800557f4  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x1800557f9  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x180055800  jz      short loc_180055833
0x180055802  mov     r8d, eax
0x180055805  mov     word ptr [rbp+7B0h+var_830], si
0x180055809  mov     rdx, rdi
0x18005580c  lea     rcx, [rbp+7B0h+var_830]
0x180055810  call    FormatRRASErrorString
0x180055815  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005581c  lea     r8, [rbp+7B0h+var_830]
0x180055820  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055827  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005582e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055833  mov     rax, qword ptr [rsp+8B0h+var_840+8]
0x180055838  lea     r9, [rsp+8B0h+var_860]
0x18005583d  mov     r8d, ebx
0x180055840  mov     [rsp+8B0h+var_858], rax
0x180055845  lea     rdx, [rsp+8B0h+var_868]
0x18005584a  lea     rcx, [rsp+8B0h+var_868]
0x18005584f  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180055854  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18005585b  jz      short loc_18005588E
0x18005585d  mov     r8d, eax
0x180055860  mov     word ptr [rbp+7B0h+var_830], si
0x180055864  mov     rdx, rdi
0x180055867  lea     rcx, [rbp+7B0h+var_830]
0x18005586b  call    FormatRRASErrorString
0x180055870  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055877  lea     r8, [rbp+7B0h+var_830]
0x18005587b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055882  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005588e  mov     r9d, [rsp+8B0h+InterfaceIndex]
0x180055893  lea     rcx, [rsp+8B0h+var_850]
0x180055898  mov     [rsp+8B0h+var_888], ebx
0x18005589c  call    CreateOrSetOrDeleteIpv6ForwardEntry
0x1800558a1  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x1800558a8  jz      short loc_1800558DF
0x1800558aa  mov     r8d, eax
0x1800558ad  mov     word ptr [rbp+7B0h+var_830], si
0x1800558b1  lea     rdx, aRassrvractivat_5; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x1800558b8  lea     rcx, [rbp+7B0h+var_830]
0x1800558bc  call    FormatRRASErrorString
0x1800558c1  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800558c8  lea     r8, [rbp+7B0h+var_830]
0x1800558cc  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800558d3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800558da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558df  mov     rax, qword ptr [rsp+8B0h+var_850+8]
0x1800558e4  lea     rcx, [rsp+8B0h+var_860]
0x1800558e9  mov     r9d, [rsp+8B0h+InterfaceIndex]
0x1800558ee  mov     [rsp+8B0h+var_858], rax
0x1800558f3  mov     [rsp+8B0h+var_888], ebx
0x1800558f7  call    CreateOrSetOrDeleteIpv6ForwardEntry
0x1800558fc  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x180055903  jz      short loc_18005593A
0x180055905  mov     r8d, eax
0x180055908  mov     word ptr [rbp+7B0h+var_830], si
0x18005590c  lea     rdx, aRassrvractivat_5; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x180055913  lea     rcx, [rbp+7B0h+var_830]
0x180055917  call    FormatRRASErrorString
0x18005591c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055923  lea     r8, [rbp+7B0h+var_830]
0x180055927  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005592e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005593a  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180055941  call    cs:__imp_LeaveCriticalSection
0x180055948  nop     dword ptr [rax+rax+00h]
0x18005594d  xor     eax, eax
0x18005594f  mov     rcx, [rbp+7B0h+var_30]
0x180055956  xor     rcx, rsp; StackCookie
0x180055959  call    __security_check_cookie
0x18005595e  add     rsp, 898h
0x180055965  pop     rdi
0x180055966  pop     rsi
0x180055967  pop     rbx
0x180055968  pop     rbp
0x180055969  retn
```
