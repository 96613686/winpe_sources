# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000f28c`
- end: `0x18000f2f6`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800146c8`

## callees

- `0x18000f260`
- `0x18000f28c`
- `0x180010510`
- `0x180010a28`

## string_xrefs

- `0x18000f2a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000f28c  mov     [rsp+arg_0], rbx
0x18000f291  mov     [rsp+arg_8], rsi
0x18000f296  push    rdi
0x18000f297  sub     rsp, 60h
0x18000f29b  mov     rsi, [rsp+68h+arg_28]
0x18000f2a3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f2aa  mov     [rsp+68h+var_40], rsi; char *
0x18000f2af  mov     ebx, edx
0x18000f2b1  mov     rdi, rcx
0x18000f2b4  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000f2b9  test    eax, eax
0x18000f2bb  jle     short loc_18000F2C5
0x18000f2bd  movzx   eax, ax
0x18000f2c0  or      eax, 80070000h
0x18000f2c5  mov     ecx, eax; this
0x18000f2c7  mov     [rsp+68h+var_18], eax
0x18000f2cb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f2d0  mov     [rsp+68h+var_14], eax
0x18000f2d4  mov     edx, ebx
0x18000f2d6  lea     rax, [rsp+68h+var_18]
0x18000f2db  mov     [rsp+68h+var_10], 0
0x18000f2e3  mov     [rsp+68h+var_38], rax
0x18000f2e8  mov     rcx, rdi
0x18000f2eb  mov     [rsp+68h+var_40], rsi
0x18000f2f0  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
