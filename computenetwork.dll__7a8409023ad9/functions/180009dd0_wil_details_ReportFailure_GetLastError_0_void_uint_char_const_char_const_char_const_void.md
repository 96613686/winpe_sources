# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180009dd0`
- end: `0x180009e50`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b4c8`

## callees

- `0x1800030ac`
- `0x180004bb8`
- `0x180005100`
- `0x180009dd0`

## string_xrefs

- `0x180009de7`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`
- `0x180009e1e`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
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
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<0,0>(
    v7,
    v6,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180009dd0  mov     [rsp+arg_0], rbx
0x180009dd5  mov     [rsp+arg_8], rsi
0x180009dda  push    rdi
0x180009ddb  sub     rsp, 70h
0x180009ddf  mov     rsi, [rsp+78h+arg_28]
0x180009de7  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009dee  mov     [rsp+78h+var_50], rsi; char *
0x180009df3  mov     ebx, edx
0x180009df5  mov     rdi, rcx
0x180009df8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180009dfd  test    eax, eax
0x180009dff  jle     short loc_180009E09
0x180009e01  movzx   eax, ax
0x180009e04  or      eax, 80070000h
0x180009e09  mov     edx, eax
0x180009e0b  lea     rcx, [rsp+78h+var_18]
0x180009e10  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180009e15  mov     [rsp+78h+var_40], 0
0x180009e1e  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009e25  mov     edx, ebx
0x180009e27  mov     rcx, rdi
0x180009e2a  movsd   xmm0, qword ptr [rax]
0x180009e2e  mov     eax, [rax+8]
0x180009e31  mov     [rsp+78h+var_20], eax
0x180009e35  lea     rax, [rsp+78h+var_28]
0x180009e3a  mov     [rsp+78h+var_48], rax
0x180009e3f  mov     [rsp+78h+var_50], rsi
0x180009e44  movsd   [rsp+78h+var_28], xmm0
0x180009e4a  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
