# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800223cc`
- end: `0x18002245d`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022d08`

## callees

- `0x180006898`
- `0x180008dd0`
- `0x180009380`
- `0x1800223cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002244c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002244c`

## string_xrefs

- `0x1800223dd`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180022415`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

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
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
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
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
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
0x1800223cc  push    rbx
0x1800223ce  push    rbp
0x1800223cf  push    rsi
0x1800223d0  push    rdi
0x1800223d1  sub     rsp, 68h
0x1800223d5  mov     rbp, [rsp+88h+arg_28]
0x1800223dd  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800223e4  mov     [rsp+88h+var_60], rbp; char *
0x1800223e9  mov     edi, edx
0x1800223eb  mov     rsi, rcx
0x1800223ee  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800223f3  xor     edx, edx; int
0x1800223f5  mov     ebx, eax
0x1800223f7  test    eax, eax
0x1800223f9  jg      short loc_1800223FF
0x1800223fb  mov     ecx, eax
0x1800223fd  jmp     short loc_180022408
0x1800223ff  movzx   ecx, bx
0x180022402  or      ecx, 80070000h; this
0x180022408  mov     [rsp+88h+var_38], ecx
0x18002240c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180022411  mov     [rsp+88h+var_40], edx
0x180022415  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18002241c  mov     [rsp+88h+var_50], rdx
0x180022421  xor     r9d, r9d
0x180022424  mov     [rsp+88h+var_34], eax
0x180022428  mov     rcx, rsi
0x18002242b  lea     rax, [rsp+88h+var_38]
0x180022430  mov     [rsp+88h+var_30], edx
0x180022434  mov     [rsp+88h+var_58], rax
0x180022439  mov     [rsp+88h+var_60], rbp
0x18002243e  mov     [rsp+88h+var_68], rdx
0x180022443  mov     edx, edi
0x180022445  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18002244a  mov     ecx, ebx; dwErrCode
0x18002244c  call    cs:__imp_SetLastError
0x180022452  mov     eax, ebx
0x180022454  add     rsp, 68h
0x180022458  pop     rdi
0x180022459  pop     rsi
0x18002245a  pop     rbp
0x18002245b  pop     rbx
0x18002245c  retn
```
