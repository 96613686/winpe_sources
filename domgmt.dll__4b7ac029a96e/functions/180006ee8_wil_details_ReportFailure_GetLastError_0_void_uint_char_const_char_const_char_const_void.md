# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180006ee8`
- end: `0x180006f69`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `129`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000a8d0`

## callees

- `0x180004468`
- `0x1800049b0`
- `0x180006eb0`
- `0x180006ee8`

## string_xrefs

- `0x180006efa`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`
- `0x180006f34`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  _BYTE v16[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x173,
                    (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v16, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v15 = *(_DWORD *)(v8 + 8);
  v14 = v9;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    371,
    (int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
    v10,
    v12,
    (__int64)a6,
    (__int64)&v14,
    0);
}

```

## disassembly

```asm
0x180006ee8  mov     [rsp+arg_0], rbx
0x180006eed  push    rdi
0x180006eee  sub     rsp, 70h
0x180006ef2  mov     rdi, [rsp+78h+arg_28]
0x180006efa  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180006f01  mov     edx, 173h; void *
0x180006f06  mov     [rsp+78h+var_50], rdi; char *
0x180006f0b  mov     rbx, rcx
0x180006f0e  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180006f13  test    eax, eax
0x180006f15  jle     short loc_180006F1F
0x180006f17  movzx   eax, ax
0x180006f1a  or      eax, 80070000h
0x180006f1f  mov     edx, eax
0x180006f21  lea     rcx, [rsp+78h+var_18]
0x180006f26  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180006f2b  mov     [rsp+78h+var_40], 0
0x180006f34  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180006f3b  mov     edx, 173h
0x180006f40  mov     rcx, rbx
0x180006f43  movsd   xmm0, qword ptr [rax]
0x180006f47  mov     eax, [rax+8]
0x180006f4a  mov     [rsp+78h+var_20], eax
0x180006f4e  lea     rax, [rsp+78h+var_28]
0x180006f53  mov     [rsp+78h+var_48], rax
0x180006f58  mov     [rsp+78h+var_50], rdi
0x180006f5d  movsd   [rsp+78h+var_28], xmm0
0x180006f63  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
