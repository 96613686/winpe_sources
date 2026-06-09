# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1800080ec`
- end: `0x180008153`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800087f4`

## callees

- `0x180002e40`
- `0x180004764`
- `0x1800080ec`

## string_xrefs

- `0x18000811c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v8, 3266, "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h");
  return v7;
}

```

## disassembly

```asm
0x1800080ec  push    rbx
0x1800080ee  sub     rsp, 60h
0x1800080f2  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1800080f9  mov     r9, rcx
0x1800080fc  test    ebx, ebx
0x1800080fe  jle     short loc_180008109
0x180008100  movzx   ebx, bx
0x180008103  or      ebx, 80070000h
0x180008109  mov     ecx, ebx; this
0x18000810b  mov     [rsp+68h+var_18], ebx
0x18000810f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008114  mov     rcx, [rsp+68h+arg_28]
0x18000811c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008123  mov     [rsp+68h+var_14], eax
0x180008127  mov     edx, 0CC2h
0x18000812c  lea     rax, [rsp+68h+var_18]
0x180008131  mov     [rsp+68h+var_10], 0
0x180008139  mov     [rsp+68h+var_38], rax
0x18000813e  mov     [rsp+68h+var_40], rcx
0x180008143  mov     rcx, r9
0x180008146  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000814b  mov     eax, ebx
0x18000814d  add     rsp, 60h
0x180008151  pop     rbx
0x180008152  retn
```
