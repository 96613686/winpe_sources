# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x1400141d0`
- end: `0x14001423a`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001528c`

## callees

- `0x1400041a0`
- `0x140009194`

## string_xrefs

- `0x140014217`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v10; // [rsp+50h] [rbp-38h]

  v10 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(
    a1,
    a2,
    "onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp");
  return v10;
}

```

## disassembly

```asm
0x1400141d0  push    rbx
0x1400141d2  push    rbp
0x1400141d3  push    rsi
0x1400141d4  push    rdi
0x1400141d5  sub     rsp, 68h
0x1400141d9  mov     ebx, dword ptr [rsp+88h+arg_30]
0x1400141e0  mov     rbp, rcx
0x1400141e3  mov     ecx, ebx; this
0x1400141e5  mov     esi, edx
0x1400141e7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1400141ec  mov     r8, [rsp+88h+arg_28]
0x1400141f4  mov     edi, eax
0x1400141f6  mov     [rsp+88h+var_38], eax
0x1400141fa  mov     edx, esi
0x1400141fc  lea     rax, [rsp+88h+var_38]
0x140014201  mov     [rsp+88h+var_50], 0
0x14001420a  mov     [rsp+88h+var_58], rax
0x14001420f  mov     rcx, rbp
0x140014212  mov     [rsp+88h+var_60], r8
0x140014217  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x14001421e  mov     [rsp+88h+var_34], ebx
0x140014222  mov     [rsp+88h+var_30], 1
0x14001422a  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14001422f  mov     eax, edi
0x140014231  add     rsp, 68h
0x140014235  pop     rdi
0x140014236  pop     rsi
0x140014237  pop     rbp
0x140014238  pop     rbx
0x140014239  retn
```
