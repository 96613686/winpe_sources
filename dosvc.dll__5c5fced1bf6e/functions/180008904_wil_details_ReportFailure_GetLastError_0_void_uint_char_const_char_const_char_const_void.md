# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008904`
- end: `0x18000897f`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `123`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000a090`

## callees

- `0x180002b90`
- `0x180004208`
- `0x1800088cc`
- `0x180008904`

## string_xrefs

- `0x180008916`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`
- `0x18000894a`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`

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
  int v8; // edx
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]
  _DWORD v13[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x173,
                    (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
                    a4,
                    v10,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v13[0] = LastErrorFail;
  v13[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    371,
    (int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
    v9,
    v11,
    (__int64)a6,
    (__int64)v13,
    0);
}

```

## disassembly

```asm
0x180008904  mov     [rsp+arg_0], rbx
0x180008909  push    rdi
0x18000890a  sub     rsp, 60h
0x18000890e  mov     rdi, [rsp+68h+arg_28]
0x180008916  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x18000891d  mov     edx, 173h; void *
0x180008922  mov     [rsp+68h+var_40], rdi; char *
0x180008927  mov     rbx, rcx
0x18000892a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000892f  test    eax, eax
0x180008931  jle     short loc_18000893B
0x180008933  movzx   eax, ax
0x180008936  or      eax, 80070000h
0x18000893b  mov     ecx, eax; this
0x18000893d  mov     [rsp+68h+var_18], eax
0x180008941  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008946  mov     [rsp+68h+var_14], eax
0x18000894a  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180008951  lea     rax, [rsp+68h+var_18]
0x180008956  mov     [rsp+68h+var_30], 0
0x18000895f  mov     [rsp+68h+var_38], rax
0x180008964  mov     edx, 173h
0x180008969  mov     rcx, rbx
0x18000896c  mov     [rsp+68h+var_40], rdi
0x180008971  mov     [rsp+68h+var_10], 0
0x180008979  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
