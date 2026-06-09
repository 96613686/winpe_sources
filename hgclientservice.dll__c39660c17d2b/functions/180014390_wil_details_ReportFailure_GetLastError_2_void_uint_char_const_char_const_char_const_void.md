# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180014390`
- end: `0x180014465`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `213`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014f90`

## callees

- `0x180003270`
- `0x1800035f0`
- `0x1800057f4`
- `0x180014390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001444d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001444d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143a2`

## string_xrefs

- `0x1800143cf`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`
- `0x180014438`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  int LastError; // ebx
  unsigned __int64 v9; // rcx
  wil::details *v11; // [rsp+30h] [rbp-38h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      31,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
      0,
      0,
      a6,
      v11);
    LastError = 668;
  }
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  else
    v9 = (unsigned int)LastError;
  v12[0] = v9;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v9, v7);
  v12[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    31,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
    0,
    0,
    a6,
    (__int64)v12,
    0);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180014390  mov     [rsp+arg_0], rbx
0x180014395  mov     [rsp+arg_8], rsi
0x18001439a  push    rdi
0x18001439b  sub     rsp, 60h
0x18001439f  mov     rdi, rcx
0x1800143a2  call    cs:__imp_GetLastError
0x1800143a8  mov     ebx, eax
0x1800143aa  mov     rsi, [rsp+68h+arg_28]
0x1800143b2  test    eax, eax
0x1800143b4  jnz     short loc_1800143E6
0x1800143b6  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x1800143be  mov     [rsp+68h+var_40], rsi; __int64
0x1800143c3  mov     [rsp+68h+var_48], 0; __int64
0x1800143cc  xor     r9d, r9d; int
0x1800143cf  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x1800143d6  lea     edx, [rax+1Fh]; int
0x1800143d9  mov     rcx, rdi; int
0x1800143dc  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800143e1  mov     ebx, 29Ch
0x1800143e6  test    ebx, ebx
0x1800143e8  jg      short loc_1800143EE
0x1800143ea  mov     ecx, ebx
0x1800143ec  jmp     short loc_1800143F7
0x1800143ee  movzx   ecx, bx
0x1800143f1  or      ecx, 80070000h; this
0x1800143f7  mov     [rsp+68h+var_18], ecx
0x1800143fb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180014400  mov     [rsp+68h+var_14], eax
0x180014404  mov     [rsp+68h+var_10], 0
0x18001440c  mov     [rsp+68h+var_20], 0
0x180014414  mov     [rsp+68h+var_30], 0
0x18001441d  lea     rax, [rsp+68h+var_18]
0x180014422  mov     [rsp+68h+var_38], rax
0x180014427  mov     [rsp+68h+var_40], rsi
0x18001442c  mov     [rsp+68h+var_48], 0
0x180014435  xor     r9d, r9d
0x180014438  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x18001443f  lea     edx, [r9+1Fh]
0x180014443  mov     rcx, rdi
0x180014446  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001444b  mov     ecx, ebx; dwErrCode
0x18001444d  call    cs:__imp_SetLastError
0x180014453  mov     eax, ebx
0x180014455  mov     rbx, [rsp+68h+arg_0]
0x18001445a  mov     rsi, [rsp+68h+arg_8]
0x18001445f  add     rsp, 60h
0x180014463  pop     rdi
0x180014464  retn
```
