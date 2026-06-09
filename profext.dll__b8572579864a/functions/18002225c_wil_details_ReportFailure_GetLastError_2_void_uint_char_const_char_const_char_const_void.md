# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002225c`
- end: `0x1800222f4`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `152`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002257c`

## callees

- `0x180005314`
- `0x18000f148`
- `0x180012910`
- `0x18002225c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800222dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800222dc`

## string_xrefs

- `0x18002226d`: `onecore\ds\security\gina\profile\profext\setup.cpp`
- `0x1800222a5`: `onecore\ds\security\gina\profile\profext\setup.cpp`

## pseudocode

```c
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
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
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
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
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
0x18002225c  push    rbx
0x18002225e  push    rbp
0x18002225f  push    rsi
0x180022260  push    rdi
0x180022261  sub     rsp, 68h
0x180022265  mov     rbp, [rsp+88h+arg_28]
0x18002226d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180022274  mov     [rsp+88h+var_60], rbp; char *
0x180022279  mov     edi, edx
0x18002227b  mov     rsi, rcx
0x18002227e  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180022283  xor     edx, edx; int
0x180022285  mov     ebx, eax
0x180022287  test    eax, eax
0x180022289  jg      short loc_18002228F
0x18002228b  mov     ecx, eax
0x18002228d  jmp     short loc_180022298
0x18002228f  movzx   ecx, bx
0x180022292  or      ecx, 80070000h; this
0x180022298  mov     [rsp+88h+var_38], ecx
0x18002229c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800222a1  mov     [rsp+88h+var_40], edx
0x1800222a5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800222ac  mov     [rsp+88h+var_50], rdx
0x1800222b1  xor     r9d, r9d
0x1800222b4  mov     [rsp+88h+var_34], eax
0x1800222b8  mov     rcx, rsi
0x1800222bb  lea     rax, [rsp+88h+var_38]
0x1800222c0  mov     [rsp+88h+var_30], edx
0x1800222c4  mov     [rsp+88h+var_58], rax
0x1800222c9  mov     [rsp+88h+var_60], rbp
0x1800222ce  mov     [rsp+88h+var_68], rdx
0x1800222d3  mov     edx, edi
0x1800222d5  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800222da  mov     ecx, ebx; dwErrCode
0x1800222dc  call    cs:__imp_SetLastError
0x1800222e3  nop     dword ptr [rax+rax+00h]
0x1800222e8  mov     eax, ebx
0x1800222ea  add     rsp, 68h
0x1800222ee  pop     rdi
0x1800222ef  pop     rsi
0x1800222f0  pop     rbp
0x1800222f1  pop     rbx
0x1800222f2  retn
```
