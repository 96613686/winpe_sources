# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000d71c`
- end: `0x18000d7c1`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `165`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e92c`

## callees

- `0x180003154`
- `0x180004690`
- `0x180004c08`
- `0x18000d71c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d7a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d7a2`

## string_xrefs

- `0x18000d733`: `onecore\windows\core\console\open\src\types\inc\User32Utils.hpp`
- `0x18000d76e`: `onecore\windows\core\console\open\src\types\inc\User32Utils.hpp`

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
                    (void *)0x18,
                    (unsigned int)"onecore\\windows\\core\\console\\open\\src\\types\\inc\\User32Utils.hpp",
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
    24,
    (unsigned int)"onecore\\windows\\core\\console\\open\\src\\types\\inc\\User32Utils.hpp",
    0,
    v10,
    (__int64)a6,
    (__int64)v14);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x18000d71c  mov     [rsp+arg_0], rbx
0x18000d721  mov     [rsp+arg_8], rsi
0x18000d726  push    rdi
0x18000d727  sub     rsp, 60h
0x18000d72b  mov     rsi, [rsp+68h+arg_28]
0x18000d733  lea     r8, aOnecoreWindows_7; "onecore\\windows\\core\\console\\open\\"...
0x18000d73a  mov     edx, 18h; void *
0x18000d73f  mov     [rsp+68h+var_40], rsi; char *
0x18000d744  mov     rdi, rcx
0x18000d747  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000d74c  xor     edx, edx; int
0x18000d74e  mov     ebx, eax
0x18000d750  test    eax, eax
0x18000d752  jg      short loc_18000D758
0x18000d754  mov     ecx, eax
0x18000d756  jmp     short loc_18000D761
0x18000d758  movzx   ecx, bx
0x18000d75b  or      ecx, 80070000h; this
0x18000d761  mov     [rsp+68h+var_18], ecx
0x18000d765  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d76a  mov     [rsp+68h+var_20], edx
0x18000d76e  lea     r8, aOnecoreWindows_7; "onecore\\windows\\core\\console\\open\\"...
0x18000d775  mov     [rsp+68h+var_14], eax
0x18000d779  xor     r9d, r9d
0x18000d77c  lea     rax, [rsp+68h+var_18]
0x18000d781  mov     [rsp+68h+var_10], edx
0x18000d785  mov     [rsp+68h+var_38], rax
0x18000d78a  mov     rcx, rdi
0x18000d78d  mov     [rsp+68h+var_40], rsi
0x18000d792  mov     [rsp+68h+var_48], rdx
0x18000d797  lea     edx, [r9+18h]
0x18000d79b  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000d7a0  mov     ecx, ebx; dwErrCode
0x18000d7a2  call    cs:__imp_SetLastError
0x18000d7a9  nop     dword ptr [rax+rax+00h]
0x18000d7ae  mov     rsi, [rsp+68h+arg_8]
0x18000d7b3  mov     eax, ebx
0x18000d7b5  mov     rbx, [rsp+68h+arg_0]
0x18000d7ba  add     rsp, 60h
0x18000d7be  pop     rdi
0x18000d7bf  retn
```
