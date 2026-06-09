# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004fb0`
- end: `0x180005035`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `133`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009e20`

## callees

- `0x180003bc0`
- `0x180003d84`
- `0x180004f78`
- `0x180004fb0`

## string_xrefs

- `0x180004fc3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005004`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        char *a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  int v8; // esi
  signed int LastErrorFail; // eax
  int v10; // edx
  void *v11; // [rsp+30h] [rbp-58h]
  _DWORD v12[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = (int)a4;
  v7 = (int)a2;
  v8 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    a5,
                    a6,
                    v11);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v12[0] = LastErrorFail;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v10);
  v12[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v8,
    v7,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6,
    (__int64)a5,
    (__int64)a6,
    (__int64)v12);
}

```

## disassembly

```asm
0x180004fb0  push    rbx
0x180004fb2  push    rbp
0x180004fb3  push    rsi
0x180004fb4  push    rdi
0x180004fb5  push    r14
0x180004fb7  sub     rsp, 60h
0x180004fbb  mov     rbp, [rsp+88h+arg_28]
0x180004fc3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004fca  mov     r14, [rsp+88h+arg_20]
0x180004fd2  mov     rbx, r9
0x180004fd5  mov     [rsp+88h+var_60], rbp; char *
0x180004fda  mov     edi, edx
0x180004fdc  mov     [rsp+88h+var_68], r14; char *
0x180004fe1  mov     rsi, rcx
0x180004fe4  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180004fe9  test    eax, eax
0x180004feb  jle     short loc_180004FF5
0x180004fed  movzx   eax, ax
0x180004ff0  or      eax, 80070000h
0x180004ff5  mov     ecx, eax; this
0x180004ff7  mov     [rsp+88h+var_38], eax
0x180004ffb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005000  mov     [rsp+88h+var_34], eax
0x180005004  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000500b  lea     rax, [rsp+88h+var_38]
0x180005010  mov     [rsp+88h+var_30], 0
0x180005018  mov     [rsp+88h+var_58], rax
0x18000501d  mov     r9, rbx
0x180005020  mov     [rsp+88h+var_60], rbp
0x180005025  mov     edx, edi
0x180005027  mov     rcx, rsi
0x18000502a  mov     [rsp+88h+var_68], r14
0x18000502f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
