# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180018254`
- end: `0x1800182c6`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `114`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a3bc`

## callees

- `0x180004e68`
- `0x1800059d0`
- `0x18001809c`
- `0x180018254`

## string_xrefs

- `0x180018266`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18001829a`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

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
                    (void *)0x25,
                    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
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
    37,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    v9,
    v11,
    (__int64)a6,
    (__int64)v13);
}

```

## disassembly

```asm
0x180018254  mov     [rsp+arg_0], rbx
0x180018259  push    rdi
0x18001825a  sub     rsp, 60h
0x18001825e  mov     rdi, [rsp+68h+arg_28]
0x180018266  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001826d  mov     edx, 25h ; '%'; void *
0x180018272  mov     [rsp+68h+var_40], rdi; char *
0x180018277  mov     rbx, rcx
0x18001827a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18001827f  test    eax, eax
0x180018281  jle     short loc_18001828B
0x180018283  movzx   eax, ax
0x180018286  or      eax, 80070000h
0x18001828b  mov     ecx, eax; this
0x18001828d  mov     [rsp+68h+var_18], eax
0x180018291  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180018296  mov     [rsp+68h+var_14], eax
0x18001829a  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800182a1  lea     rax, [rsp+68h+var_18]
0x1800182a6  mov     [rsp+68h+var_10], 0
0x1800182ae  mov     [rsp+68h+var_38], rax
0x1800182b3  mov     edx, 25h ; '%'
0x1800182b8  mov     rcx, rbx
0x1800182bb  mov     [rsp+68h+var_40], rdi
0x1800182c0  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
