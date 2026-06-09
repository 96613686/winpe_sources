# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008828`
- end: `0x1800088cb`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `163`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c2c8`

## callees

- `0x180003308`
- `0x180005960`
- `0x180005f3c`
- `0x180008828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088b3`

## string_xrefs

- `0x18000883f`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`
- `0x18000887a`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  DWORD v8; // ebx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  const char *v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x7C,
                    (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                    a4,
                    v12,
                    a6,
                    v13);
  v8 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v9 = (unsigned int)LastErrorFail;
  v14[0] = v9;
  v14[1] = wil::details::HrToNtStatus((wil::details *)v9, 0);
  v14[2] = v10;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    124,
    (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
    0,
    v10,
    (__int64)a6,
    (__int64)v14,
    v10);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x180008828  mov     [rsp+arg_0], rbx
0x18000882d  mov     [rsp+arg_8], rsi
0x180008832  push    rdi
0x180008833  sub     rsp, 60h
0x180008837  mov     rsi, [rsp+68h+arg_28]
0x18000883f  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180008846  mov     edx, 7Ch ; '|'; void *
0x18000884b  mov     [rsp+68h+var_40], rsi; char *
0x180008850  mov     rdi, rcx
0x180008853  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008858  xor     edx, edx; int
0x18000885a  mov     ebx, eax
0x18000885c  test    eax, eax
0x18000885e  jg      short loc_180008864
0x180008860  mov     ecx, eax
0x180008862  jmp     short loc_18000886D
0x180008864  movzx   ecx, bx
0x180008867  or      ecx, 80070000h; this
0x18000886d  mov     [rsp+68h+var_18], ecx
0x180008871  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008876  mov     [rsp+68h+var_20], edx
0x18000887a  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180008881  mov     [rsp+68h+var_30], rdx
0x180008886  xor     r9d, r9d
0x180008889  mov     [rsp+68h+var_14], eax
0x18000888d  mov     rcx, rdi
0x180008890  lea     rax, [rsp+68h+var_18]
0x180008895  mov     [rsp+68h+var_10], edx
0x180008899  mov     [rsp+68h+var_38], rax
0x18000889e  mov     [rsp+68h+var_40], rsi
0x1800088a3  mov     [rsp+68h+var_48], rdx
0x1800088a8  lea     edx, [r9+7Ch]
0x1800088ac  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800088b1  mov     ecx, ebx; dwErrCode
0x1800088b3  call    cs:__imp_SetLastError
0x1800088b9  mov     rsi, [rsp+68h+arg_8]
0x1800088be  mov     eax, ebx
0x1800088c0  mov     rbx, [rsp+68h+arg_0]
0x1800088c5  add     rsp, 60h
0x1800088c9  pop     rdi
0x1800088ca  retn
```
