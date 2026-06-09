# IPHelper::GetAdapterAddressesByCompartment(uint)

- ea: `0x18008a170`
- end: `0x18008a2c9`
- name: `?GetAdapterAddressesByCompartment@IPHelper@@SA?AV?$unique_ptr@U_IP_ADAPTER_ADDRESSES_LH@@UAutoFree@@@std@@I@Z`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180157738`
- `0x180161e38`
- `0x1802449d8`

## callees

- `0x1800759d8`
- `0x180075aac`
- `0x18007cbc8`
- `0x18008a170`
- `0x18008b50c`
- `0x18008c69c`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1e7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008a1d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008a1d4`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18008a231`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18008a231`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008a27c`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008a27c`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008a218`

## string_xrefs

- `0x18008a293`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008a2a5`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008a2b7`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008a191`: `IPHelper::GetAdapterAddressesByCompartment`
- `0x18008a266`: `IPHelper::GetAdapterAddressesByCompartment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IPHelper::GetAdapterAddressesByCompartment(__int64 a1, unsigned int a2)
{
  void *v4; // rax
  const char *v5; // r9
  void *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v12; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+20h] BYREF

  HNSTraceProvider::TraceEnter("IPHelper::GetAdapterAddressesByCompartment", 0xB2u);
  IPHelper::SetCurrentThreadCompartmentId(&v12, a2);
  *(_QWORD *)(a1 + 8) = 0;
  HNSTraceProvider::TraceEnter("IPHelper::ExecuteIpHelperFunction", 0x78u);
  v13 = 15360;
  v4 = malloc(0x3C00u);
  v6 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v4;
  if ( v6 )
    free(v6);
  v7 = *(_QWORD *)(a1 + 8);
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
      v5);
  while ( 1 )
  {
    v8 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))GetAdaptersAddresses)(2, 134, 0, v7);
    if ( v8 != 111 )
      break;
    v7 = _o_realloc(*(_QWORD *)(a1 + 8), v13);
    if ( !v7 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        v9);
    *(_QWORD *)(a1 + 8) = v7;
  }
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
      (const char *)v8,
      (unsigned int)&v13);
  HNSTraceProvider::TraceSuccess("IPHelper::ExecuteIpHelperFunction", 0x90u);
  HNSTraceProvider::TraceSuccess("IPHelper::GetAdapterAddressesByCompartment", 0xBEu);
  if ( v12 )
    SetCurrentThreadCompartmentId(0);
  return a1;
}

```

## disassembly

```asm
0x18008a170  mov     [rsp+arg_8], rbx
0x18008a175  mov     [rsp+arg_0], rcx
0x18008a17a  push    rdi
0x18008a17b  sub     rsp, 40h
0x18008a17f  mov     ebx, edx
0x18008a181  mov     rdi, rcx
0x18008a184  mov     [rsp+48h+var_18], 0
0x18008a18c  mov     edx, 0B2h; unsigned int
0x18008a191  lea     rcx, aIphelperGetada_0; "IPHelper::GetAdapterAddressesByCompartm"...
0x18008a198  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18008a19d  mov     edx, ebx
0x18008a19f  lea     rcx, [rsp+48h+arg_10]
0x18008a1a4  call    ?SetCurrentThreadCompartmentId@IPHelper@@SA?AV?$unique_call@P6AXXZ$1?ClearCompartment@IPHelper@@SAXXZ$00@wil@@I@Z; IPHelper::SetCurrentThreadCompartmentId(uint)
0x18008a1a9  nop
0x18008a1aa  mov     qword ptr [rdi+8], 0
0x18008a1b2  mov     [rsp+48h+var_18], 1
0x18008a1ba  mov     edx, 78h ; 'x'; unsigned int
0x18008a1bf  lea     rcx, aIphelperExecut; "IPHelper::ExecuteIpHelperFunction"
0x18008a1c6  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18008a1cb  mov     ecx, 3C00h; Size
0x18008a1d0  mov     [rsp+48h+arg_18], ecx
0x18008a1d4  call    cs:__imp_malloc
0x18008a1da  mov     rcx, [rdi+8]; Block
0x18008a1de  mov     [rdi+8], rax
0x18008a1e2  test    rcx, rcx
0x18008a1e5  jz      short loc_18008A1ED
0x18008a1e7  call    cs:__imp_free
0x18008a1ed  mov     rax, [rdi+8]
0x18008a1f1  mov     rcx, [rsp+48h]; this
0x18008a1f6  test    rax, rax
0x18008a1f9  jz      loc_18008A2A5
0x18008a1ff  lea     rcx, [rsp+48h+arg_18]
0x18008a204  mov     qword ptr [rsp+48h+var_28], rcx; unsigned int
0x18008a209  mov     r9, rax
0x18008a20c  xor     r8d, r8d
0x18008a20f  mov     edx, 86h
0x18008a214  lea     ecx, [r8+2]
0x18008a218  mov     rax, cs:__imp_GetAdaptersAddresses
0x18008a21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a224  cmp     eax, 6Fh ; 'o'
0x18008a227  jnz     short loc_18008A247
0x18008a229  mov     edx, [rsp+48h+arg_18]
0x18008a22d  mov     rcx, [rdi+8]
0x18008a231  call    cs:__imp__o_realloc
0x18008a237  mov     rcx, [rsp+48h]; this
0x18008a23c  test    rax, rax
0x18008a23f  jz      short loc_18008A2B7
0x18008a241  mov     [rdi+8], rax
0x18008a245  jmp     short loc_18008A1FF
0x18008a247  mov     rcx, [rsp+48h]; this
0x18008a24c  test    eax, eax
0x18008a24e  jnz     short loc_18008A290
0x18008a250  mov     edx, 90h; unsigned int
0x18008a255  lea     rcx, aIphelperExecut; "IPHelper::ExecuteIpHelperFunction"
0x18008a25c  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x18008a261  mov     edx, 0BEh; unsigned int
0x18008a266  lea     rcx, aIphelperGetada_0; "IPHelper::GetAdapterAddressesByCompartm"...
0x18008a26d  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x18008a272  nop
0x18008a273  cmp     [rsp+48h+arg_10], 0
0x18008a278  jz      short loc_18008A282
0x18008a27a  xor     ecx, ecx; CompartmentId
0x18008a27c  call    cs:__imp_SetCurrentThreadCompartmentId
0x18008a282  mov     rax, rdi
0x18008a285  mov     rbx, [rsp+48h+arg_8]
0x18008a28a  add     rsp, 40h
0x18008a28e  pop     rdi
0x18008a28f  retn
0x18008a290  mov     r9d, eax; char *
0x18008a293  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18008a29a  mov     edx, 8Eh; void *
0x18008a29f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008a2a5  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18008a2ac  mov     edx, 7Bh ; '{'; void *
0x18008a2b1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18008a2b7  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18008a2be  mov     edx, 88h; void *
0x18008a2c3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
