# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008fb4`
- end: `0x180009024`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bd6c`

## callees

- `0x180008f88`
- `0x180008fb4`
- `0x180009df4`
- `0x18000a308`

## string_xrefs

- `0x180008fcb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v13,
                    a6,
                    v15);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v18, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v17 = *(_DWORD *)(v9 + 8);
  v16 = v10;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v11, v12, v14, (__int64)a6, (__int64)&v16);
}

```

## disassembly

```asm
0x180008fb4  mov     [rsp+arg_0], rbx
0x180008fb9  mov     [rsp+arg_8], rsi
0x180008fbe  push    rdi
0x180008fbf  sub     rsp, 70h
0x180008fc3  mov     rsi, [rsp+78h+arg_28]
0x180008fcb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008fd2  mov     [rsp+78h+var_50], rsi; char *
0x180008fd7  mov     ebx, edx
0x180008fd9  mov     rdi, rcx
0x180008fdc  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008fe1  test    eax, eax
0x180008fe3  jle     short loc_180008FED
0x180008fe5  movzx   eax, ax
0x180008fe8  or      eax, 80070000h
0x180008fed  mov     edx, eax
0x180008fef  lea     rcx, [rsp+78h+var_18]
0x180008ff4  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180008ff9  mov     edx, ebx
0x180008ffb  mov     rcx, rdi
0x180008ffe  movsd   xmm0, qword ptr [rax]
0x180009002  mov     eax, [rax+8]
0x180009005  mov     [rsp+78h+var_20], eax
0x180009009  lea     rax, [rsp+78h+var_28]
0x18000900e  mov     [rsp+78h+var_48], rax
0x180009013  mov     [rsp+78h+var_50], rsi
0x180009018  movsd   [rsp+78h+var_28], xmm0
0x18000901e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
