# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000a4e8`
- end: `0x18000a5a6`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `190`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000be00`

## callees

- `0x180002d78`
- `0x180002f64`
- `0x180005f50`
- `0x18000a4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4f6`

## string_xrefs

- `0x18000a523`: `onecoreuap\net\eaphost\build\hostservice\hostservice.cpp`
- `0x18000a582`: `onecoreuap\net\eaphost\build\hostservice\hostservice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  int LastError; // ebx
  unsigned __int64 v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-58h]
  _DWORD v13[14]; // [rsp+50h] [rbp-38h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      a2,
      (int)"onecoreuap\\net\\eaphost\\build\\hostservice\\hostservice.cpp",
      0,
      0,
      a6,
      v12);
    LastError = 668;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = (unsigned int)LastError;
  v13[0] = v10;
  v13[1] = wil::details::HrToNtStatus((wil::details *)v10, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"onecoreuap\\net\\eaphost\\build\\hostservice\\hostservice.cpp",
    0,
    0,
    a6,
    (__int64)v13);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000a4e8  push    rbx
0x18000a4ea  push    rbp
0x18000a4eb  push    rsi
0x18000a4ec  push    rdi
0x18000a4ed  sub     rsp, 68h
0x18000a4f1  mov     edi, edx
0x18000a4f3  mov     rsi, rcx
0x18000a4f6  call    cs:__imp_GetLastError
0x18000a4fc  mov     ebx, eax
0x18000a4fe  mov     rbp, [rsp+88h+arg_28]
0x18000a506  test    eax, eax
0x18000a508  jnz     short loc_18000A539
0x18000a50a  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x18000a512  mov     [rsp+88h+var_60], rbp; __int64
0x18000a517  mov     [rsp+88h+var_68], 0; __int64
0x18000a520  xor     r9d, r9d; int
0x18000a523  lea     r8, aOnecoreuapNetE; "onecoreuap\\net\\eaphost\\build\\hostse"...
0x18000a52a  mov     edx, edi; int
0x18000a52c  mov     rcx, rsi; int
0x18000a52f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a534  mov     ebx, 29Ch
0x18000a539  test    ebx, ebx
0x18000a53b  jg      short loc_18000A541
0x18000a53d  mov     ecx, ebx
0x18000a53f  jmp     short loc_18000A54A
0x18000a541  movzx   ecx, bx
0x18000a544  or      ecx, 80070000h; this
0x18000a54a  mov     [rsp+88h+var_38], ecx
0x18000a54e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a553  mov     [rsp+88h+var_34], eax
0x18000a557  mov     [rsp+88h+var_30], 0
0x18000a55f  mov     [rsp+88h+var_40], 0
0x18000a567  lea     rax, [rsp+88h+var_38]
0x18000a56c  mov     [rsp+88h+var_58], rax
0x18000a571  mov     [rsp+88h+var_60], rbp
0x18000a576  mov     [rsp+88h+var_68], 0
0x18000a57f  xor     r9d, r9d
0x18000a582  lea     r8, aOnecoreuapNetE; "onecoreuap\\net\\eaphost\\build\\hostse"...
0x18000a589  mov     edx, edi
0x18000a58b  mov     rcx, rsi
0x18000a58e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000a593  mov     ecx, ebx; dwErrCode
0x18000a595  call    cs:__imp_SetLastError
0x18000a59b  mov     eax, ebx
0x18000a59d  add     rsp, 68h
0x18000a5a1  pop     rdi
0x18000a5a2  pop     rsi
0x18000a5a3  pop     rbp
0x18000a5a4  pop     rbx
0x18000a5a5  retn
```
