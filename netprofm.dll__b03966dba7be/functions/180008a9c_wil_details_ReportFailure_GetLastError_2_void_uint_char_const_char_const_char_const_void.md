# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008a9c`
- end: `0x180008b2d`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180008a7c`

## callees

- `0x180008a9c`
- `0x180008bf8`
- `0x180008dcc`
- `0x180014244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b11`

## string_xrefs

- `0x180008aad`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`
- `0x180008ada`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
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
                    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
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
    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15,
    v11);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x180008a9c  push    rbx
0x180008a9e  push    rbp
0x180008a9f  push    rsi
0x180008aa0  push    rdi
0x180008aa1  sub     rsp, 68h
0x180008aa5  mov     rbp, [rsp+88h+arg_28]
0x180008aad  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180008ab4  mov     [rsp+88h+var_60], rbp; char *
0x180008ab9  mov     edi, edx
0x180008abb  mov     rsi, rcx
0x180008abe  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008ac3  xor     edx, edx; int
0x180008ac5  mov     ebx, eax
0x180008ac7  test    eax, eax
0x180008ac9  jg      short loc_180008B22
0x180008acb  mov     ecx, eax; this
0x180008acd  mov     [rsp+88h+var_38], ecx
0x180008ad1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008ad6  mov     [rsp+88h+var_40], edx
0x180008ada  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180008ae1  mov     [rsp+88h+var_50], rdx
0x180008ae6  xor     r9d, r9d
0x180008ae9  mov     [rsp+88h+var_34], eax
0x180008aed  mov     rcx, rsi
0x180008af0  lea     rax, [rsp+88h+var_38]
0x180008af5  mov     [rsp+88h+var_30], edx
0x180008af9  mov     [rsp+88h+var_58], rax
0x180008afe  mov     [rsp+88h+var_60], rbp
0x180008b03  mov     [rsp+88h+var_68], rdx
0x180008b08  mov     edx, edi
0x180008b0a  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180008b0f  mov     ecx, ebx; dwErrCode
0x180008b11  call    cs:__imp_SetLastError
0x180008b17  mov     eax, ebx
0x180008b19  add     rsp, 68h
0x180008b1d  pop     rdi
0x180008b1e  pop     rsi
0x180008b1f  pop     rbp
0x180008b20  pop     rbx
0x180008b21  retn
0x180008b22  movzx   ecx, bx
0x180008b25  or      ecx, 80070000h
0x180008b2b  jmp     short loc_180008ACD
```
