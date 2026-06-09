# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000c92c`
- end: `0x18000c9b8`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `140`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d7ec`

## callees

- `0x1800039d8`
- `0x180004e60`
- `0x1800053cc`
- `0x18000c92c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9a7`

## string_xrefs

- `0x18000c93d`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000c975`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  DWORD v9; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  const char *v13; // [rsp+20h] [rbp-68h]
  void *v14; // [rsp+30h] [rbp-58h]
  _DWORD v15[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
                    a4,
                    v13,
                    a6,
                    v14);
  v9 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v10 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v10 = (unsigned int)LastErrorFail;
  v15[0] = v10;
  v15[1] = wil::details::HrToNtStatus((wil::details *)v10, 0);
  v15[2] = v11;
  wil::details::ReportFailure_Base<2,0>(
    v7,
    v6,
    (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x18000c92c  push    rbx
0x18000c92e  push    rbp
0x18000c92f  push    rsi
0x18000c930  push    rdi
0x18000c931  sub     rsp, 68h
0x18000c935  mov     rbp, [rsp+88h+arg_28]
0x18000c93d  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000c944  mov     [rsp+88h+var_60], rbp; char *
0x18000c949  mov     edi, edx
0x18000c94b  mov     rsi, rcx
0x18000c94e  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000c953  xor     edx, edx; int
0x18000c955  mov     ebx, eax
0x18000c957  test    eax, eax
0x18000c959  jg      short loc_18000C95F
0x18000c95b  mov     ecx, eax
0x18000c95d  jmp     short loc_18000C968
0x18000c95f  movzx   ecx, bx
0x18000c962  or      ecx, 80070000h; this
0x18000c968  mov     [rsp+88h+var_38], ecx
0x18000c96c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c971  mov     [rsp+88h+var_40], edx
0x18000c975  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000c97c  mov     [rsp+88h+var_34], eax
0x18000c980  xor     r9d, r9d
0x18000c983  lea     rax, [rsp+88h+var_38]
0x18000c988  mov     [rsp+88h+var_30], edx
0x18000c98c  mov     [rsp+88h+var_58], rax
0x18000c991  mov     rcx, rsi
0x18000c994  mov     [rsp+88h+var_60], rbp
0x18000c999  mov     [rsp+88h+var_68], rdx
0x18000c99e  mov     edx, edi
0x18000c9a0  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000c9a5  mov     ecx, ebx; dwErrCode
0x18000c9a7  call    cs:__imp_SetLastError
0x18000c9ad  mov     eax, ebx
0x18000c9af  add     rsp, 68h
0x18000c9b3  pop     rdi
0x18000c9b4  pop     rsi
0x18000c9b5  pop     rbp
0x18000c9b6  pop     rbx
0x18000c9b7  retn
```
