# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000fde0`
- end: `0x18000fe41`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010c44`

## callees

- `0x1800024dc`
- `0x180010be0`

## string_xrefs

- `0x18000fe22`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

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
  wil::details::ReportFailure_Base<1,0>(a1, a2, "onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp");
  return v10;
}

```

## disassembly

```asm
0x18000fde0  push    rbx
0x18000fde2  push    rbp
0x18000fde3  push    rsi
0x18000fde4  push    rdi
0x18000fde5  sub     rsp, 68h
0x18000fde9  mov     ebx, dword ptr [rsp+88h+arg_30]
0x18000fdf0  mov     rbp, rcx
0x18000fdf3  mov     ecx, ebx; this
0x18000fdf5  mov     esi, edx
0x18000fdf7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fdfc  mov     r8, [rsp+88h+arg_28]
0x18000fe04  mov     edi, eax
0x18000fe06  mov     [rsp+88h+var_38], eax
0x18000fe0a  mov     edx, esi
0x18000fe0c  lea     rax, [rsp+88h+var_38]
0x18000fe11  mov     [rsp+88h+var_34], ebx
0x18000fe15  mov     [rsp+88h+var_58], rax
0x18000fe1a  mov     rcx, rbp
0x18000fe1d  mov     [rsp+88h+var_60], r8
0x18000fe22  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18000fe29  mov     [rsp+88h+var_30], 1
0x18000fe31  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fe36  mov     eax, edi
0x18000fe38  add     rsp, 68h
0x18000fe3c  pop     rdi
0x18000fe3d  pop     rsi
0x18000fe3e  pop     rbp
0x18000fe3f  pop     rbx
0x18000fe40  retn
```
