# RasSrvrActivateIpv6DoDSpecificRoute

- ea: `0x180053b70`
- end: `0x180053dd8`
- name: `RasSrvrActivateIpv6DoDSpecificRoute`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180053b70`
- `0x180071cec`
- `0x180075534`
- `0x180075668`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180053db5`
- `KERNEL32!LeaveCriticalSection` at `0x180053db5`
- `KERNEL32!EnterCriticalSection` at `0x180053bf6`
- `KERNEL32!EnterCriticalSection` at `0x180053bf6`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180053be1`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180053be1`

## string_xrefs

- `0x180053c1c`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x`
- `0x180053d25`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x`
- `0x180053d80`: `RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x`

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
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    v9 = CreateOrSetOrDeleteIpv6NeighborEntry(&v19, &v19, v7, &v22);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v9);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    v21 = *((_QWORD *)&v23 + 1);
    v10 = CreateOrSetOrDeleteIpv6NeighborEntry(&v19, &v19, v7, &v20);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6NeighborEntry returned: 0x%x",
        v10);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    v13 = CreateOrSetOrDeleteIpv6ForwardEntry(&v22, v11, v12, InterfaceIndex);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x",
        v13);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    v21 = *((_QWORD *)&v22 + 1);
    v16 = CreateOrSetOrDeleteIpv6ForwardEntry(&v20, v14, v15, InterfaceIndex);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"RasSrvrActivateIpv6DoDSpecificRoute: CreateOrSetOrDeleteIpv6ForwardEntry returned: 0x%x",
        v16);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v24);
    }
    LeaveCriticalSection(&RasSrvrCriticalSection);
  }
  return 0;
}

```

## disassembly

```asm
0x180053b70  push    rbp
0x180053b72  push    rbx
0x180053b73  push    rsi
0x180053b74  push    rdi
0x180053b75  lea     rbp, [rsp-798h]
0x180053b7d  sub     rsp, 898h
0x180053b84  mov     rax, cs:__security_cookie
0x180053b8b  xor     rax, rsp
0x180053b8e  mov     [rbp+7B0h+var_30], rax
0x180053b95  movups  xmm0, xmmword ptr [rcx]
0x180053b98  mov     rbx, r8
0x180053b9b  xor     esi, esi
0x180053b9d  movups  xmm1, xmmword ptr [rdx]
0x180053ba0  xor     edx, edx; Val
0x180053ba2  movzx   edi, r9b
0x180053ba6  mov     r8d, 7FCh; Size
0x180053bac  mov     [rsp+8B0h+var_860], 80FEh
0x180053bb5  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180053bb9  mov     [rsp+8B0h+InterfaceIndex], esi
0x180053bbd  movdqu  [rsp+8B0h+var_850], xmm0
0x180053bc3  mov     [rbp+7B0h+var_830], esi
0x180053bc6  movdqu  [rsp+8B0h+var_840], xmm1
0x180053bcc  call    memset_0
0x180053bd1  mov     rax, [rbx]
0x180053bd4  lea     rdx, [rsp+8B0h+InterfaceIndex]; InterfaceIndex
0x180053bd9  mov     rcx, rbx; InterfaceLuid
0x180053bdc  mov     [rsp+8B0h+var_868], rax
0x180053be1  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180053be7  test    eax, eax
0x180053be9  jnz     loc_180053DBB
0x180053bef  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053bf6  call    cs:__imp_EnterCriticalSection
0x180053bfc  lea     r9, [rsp+8B0h+var_840]
0x180053c01  mov     r8d, edi
0x180053c04  lea     rdx, [rsp+8B0h+var_868]
0x180053c09  mov     ebx, edi
0x180053c0b  lea     rcx, [rsp+8B0h+var_868]
0x180053c10  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180053c15  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180053c1c  lea     rdi, aRassrvractivat; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x180053c23  jz      short loc_180053C56
0x180053c25  mov     r8d, eax
0x180053c28  mov     word ptr [rbp+7B0h+var_830], si
0x180053c2c  mov     rdx, rdi
0x180053c2f  lea     rcx, [rbp+7B0h+var_830]
0x180053c33  call    FormatRRASErrorString
0x180053c38  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053c3f  lea     r8, [rbp+7B0h+var_830]
0x180053c43  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053c4a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c56  lea     r9, [rsp+8B0h+var_850]
0x180053c5b  mov     r8d, ebx
0x180053c5e  lea     rdx, [rsp+8B0h+var_868]
0x180053c63  lea     rcx, [rsp+8B0h+var_868]
0x180053c68  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180053c6d  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180053c74  jz      short loc_180053CA7
0x180053c76  mov     r8d, eax
0x180053c79  mov     word ptr [rbp+7B0h+var_830], si
0x180053c7d  mov     rdx, rdi
0x180053c80  lea     rcx, [rbp+7B0h+var_830]
0x180053c84  call    FormatRRASErrorString
0x180053c89  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053c90  lea     r8, [rbp+7B0h+var_830]
0x180053c94  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053c9b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ca7  mov     rax, qword ptr [rsp+8B0h+var_840+8]
0x180053cac  lea     r9, [rsp+8B0h+var_860]
0x180053cb1  mov     r8d, ebx
0x180053cb4  mov     [rsp+8B0h+var_858], rax
0x180053cb9  lea     rdx, [rsp+8B0h+var_868]
0x180053cbe  lea     rcx, [rsp+8B0h+var_868]
0x180053cc3  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180053cc8  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180053ccf  jz      short loc_180053D02
0x180053cd1  mov     r8d, eax
0x180053cd4  mov     word ptr [rbp+7B0h+var_830], si
0x180053cd8  mov     rdx, rdi
0x180053cdb  lea     rcx, [rbp+7B0h+var_830]
0x180053cdf  call    FormatRRASErrorString
0x180053ce4  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053ceb  lea     r8, [rbp+7B0h+var_830]
0x180053cef  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053cf6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d02  mov     r9d, [rsp+8B0h+InterfaceIndex]
0x180053d07  lea     rcx, [rsp+8B0h+var_850]
0x180053d0c  mov     [rsp+8B0h+var_888], ebx
0x180053d10  call    CreateOrSetOrDeleteIpv6ForwardEntry
0x180053d15  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180053d1c  jz      short loc_180053D53
0x180053d1e  mov     r8d, eax
0x180053d21  mov     word ptr [rbp+7B0h+var_830], si
0x180053d25  lea     rdx, aRassrvractivat_5; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x180053d2c  lea     rcx, [rbp+7B0h+var_830]
0x180053d30  call    FormatRRASErrorString
0x180053d35  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053d3c  lea     r8, [rbp+7B0h+var_830]
0x180053d40  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053d47  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d53  mov     rax, qword ptr [rsp+8B0h+var_850+8]
0x180053d58  lea     rcx, [rsp+8B0h+var_860]
0x180053d5d  mov     r9d, [rsp+8B0h+InterfaceIndex]
0x180053d62  mov     [rsp+8B0h+var_858], rax
0x180053d67  mov     [rsp+8B0h+var_888], ebx
0x180053d6b  call    CreateOrSetOrDeleteIpv6ForwardEntry
0x180053d70  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180053d77  jz      short loc_180053DAE
0x180053d79  mov     r8d, eax
0x180053d7c  mov     word ptr [rbp+7B0h+var_830], si
0x180053d80  lea     rdx, aRassrvractivat_5; "RasSrvrActivateIpv6DoDSpecificRoute: Cr"...
0x180053d87  lea     rcx, [rbp+7B0h+var_830]
0x180053d8b  call    FormatRRASErrorString
0x180053d90  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053d97  lea     r8, [rbp+7B0h+var_830]
0x180053d9b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053da2  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053dae  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053db5  call    cs:__imp_LeaveCriticalSection
0x180053dbb  xor     eax, eax
0x180053dbd  mov     rcx, [rbp+7B0h+var_30]
0x180053dc4  xor     rcx, rsp; StackCookie
0x180053dc7  call    __security_check_cookie
0x180053dcc  add     rsp, 898h
0x180053dd3  pop     rdi
0x180053dd4  pop     rsi
0x180053dd5  pop     rbx
0x180053dd6  pop     rbp
0x180053dd7  retn
```
