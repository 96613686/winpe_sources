# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180006098`
- end: `0x180006102`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `106`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000844c`

## callees

- `0x180002b90`
- `0x180004208`
- `0x18000606c`
- `0x180006098`

## string_xrefs

- `0x1800060af`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  void *v14; // [rsp+30h] [rbp-38h]
  _DWORD v15[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v15[0] = LastErrorFail;
  v15[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v15[2] = 0;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v10, v11, v13, (__int64)a6, (__int64)v15);
}

```

## disassembly

```asm
0x180006098  mov     [rsp+arg_0], rbx
0x18000609d  mov     [rsp+arg_8], rsi
0x1800060a2  push    rdi
0x1800060a3  sub     rsp, 60h
0x1800060a7  mov     rsi, [rsp+68h+arg_28]
0x1800060af  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800060b6  mov     [rsp+68h+var_40], rsi; char *
0x1800060bb  mov     ebx, edx
0x1800060bd  mov     rdi, rcx
0x1800060c0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800060c5  test    eax, eax
0x1800060c7  jle     short loc_1800060D1
0x1800060c9  movzx   eax, ax
0x1800060cc  or      eax, 80070000h
0x1800060d1  mov     ecx, eax; this
0x1800060d3  mov     [rsp+68h+var_18], eax
0x1800060d7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800060dc  mov     [rsp+68h+var_14], eax
0x1800060e0  mov     edx, ebx
0x1800060e2  lea     rax, [rsp+68h+var_18]
0x1800060e7  mov     [rsp+68h+var_10], 0
0x1800060ef  mov     [rsp+68h+var_38], rax
0x1800060f4  mov     rcx, rdi
0x1800060f7  mov     [rsp+68h+var_40], rsi
0x1800060fc  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
