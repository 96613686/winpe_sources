# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140011070`
- end: `0x1400110e1`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013684`

## callees

- `0x14000abcc`
- `0x14000f73c`
- `0x140011044`
- `0x140011070`

## string_xrefs

- `0x140011087`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400110b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]
  _DWORD v13[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v10,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v13[0] = LastErrorFail;
  v13[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail);
  v13[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v9,
    v11,
    (__int64)a6,
    (__int64)v13);
}

```

## disassembly

```asm
0x140011070  mov     [rsp+arg_0], rbx
0x140011075  mov     [rsp+arg_8], rsi
0x14001107a  push    rdi
0x14001107b  sub     rsp, 60h
0x14001107f  mov     rsi, [rsp+68h+arg_28]
0x140011087  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001108e  mov     [rsp+68h+var_40], rsi; char *
0x140011093  mov     ebx, edx
0x140011095  mov     rdi, rcx
0x140011098  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14001109d  test    eax, eax
0x14001109f  jle     short loc_1400110A9
0x1400110a1  movzx   eax, ax
0x1400110a4  or      eax, 80070000h
0x1400110a9  mov     ecx, eax; this
0x1400110ab  mov     [rsp+68h+var_18], eax
0x1400110af  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400110b4  mov     [rsp+68h+var_14], eax
0x1400110b8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400110bf  lea     rax, [rsp+68h+var_18]
0x1400110c4  mov     [rsp+68h+var_10], 0
0x1400110cc  mov     [rsp+68h+var_38], rax
0x1400110d1  mov     edx, ebx
0x1400110d3  mov     rcx, rdi
0x1400110d6  mov     [rsp+68h+var_40], rsi
0x1400110db  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
