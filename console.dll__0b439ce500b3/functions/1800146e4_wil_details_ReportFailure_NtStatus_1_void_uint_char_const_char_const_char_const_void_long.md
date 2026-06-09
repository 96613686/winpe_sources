# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x1800146e4`
- end: `0x18001474f`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `107`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800156a0`

## callees

- `0x180003148`
- `0x180006f5c`

## string_xrefs

- `0x18001472b`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`

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
    "onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp");
  return v10;
}

```

## disassembly

```asm
0x1800146e4  push    rbx
0x1800146e6  push    rbp
0x1800146e7  push    rsi
0x1800146e8  push    rdi
0x1800146e9  sub     rsp, 68h
0x1800146ed  mov     ebx, dword ptr [rsp+88h+arg_30]
0x1800146f4  mov     rbp, rcx
0x1800146f7  mov     ecx, ebx; this
0x1800146f9  mov     esi, edx
0x1800146fb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180014700  mov     r8, [rsp+88h+arg_28]
0x180014708  mov     edi, eax
0x18001470a  mov     [rsp+88h+var_38], eax
0x18001470e  mov     edx, esi
0x180014710  lea     rax, [rsp+88h+var_38]
0x180014715  mov     [rsp+88h+var_50], 0
0x18001471e  mov     [rsp+88h+var_58], rax
0x180014723  mov     rcx, rbp
0x180014726  mov     [rsp+88h+var_60], r8
0x18001472b  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180014732  mov     [rsp+88h+var_34], ebx
0x180014736  mov     [rsp+88h+var_30], 1
0x18001473e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180014743  mov     eax, edi
0x180014745  add     rsp, 68h
0x180014749  pop     rdi
0x18001474a  pop     rsi
0x18001474b  pop     rbp
0x18001474c  pop     rbx
0x18001474d  retn
```
