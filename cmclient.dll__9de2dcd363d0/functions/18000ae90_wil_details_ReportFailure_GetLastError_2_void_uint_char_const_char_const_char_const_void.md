# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000ae90`
- end: `0x18000af5c`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `204`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b31c`

## callees

- `0x180002f70`
- `0x180003154`
- `0x18000537c`
- `0x18000ae90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af44`

## string_xrefs

- `0x18000aecf`: `onecore\base\gendrv\silos\clem\client\dll\dllmain.cpp`
- `0x18000af2f`: `onecore\base\gendrv\silos\clem\client\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      75,
      (int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dllmain.cpp",
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
    75,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dllmain.cpp",
    0,
    0,
    a6,
    (__int64)v12);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000ae90  mov     [rsp+arg_0], rbx
0x18000ae95  mov     [rsp+arg_8], rsi
0x18000ae9a  push    rdi
0x18000ae9b  sub     rsp, 60h
0x18000ae9f  mov     rdi, rcx
0x18000aea2  call    cs:__imp_GetLastError
0x18000aea8  mov     ebx, eax
0x18000aeaa  mov     rsi, [rsp+68h+arg_28]
0x18000aeb2  test    eax, eax
0x18000aeb4  jnz     short loc_18000AEE6
0x18000aeb6  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x18000aebe  mov     [rsp+68h+var_40], rsi; __int64
0x18000aec3  mov     [rsp+68h+var_48], 0; __int64
0x18000aecc  xor     r9d, r9d; int
0x18000aecf  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000aed6  lea     edx, [rax+4Bh]; int
0x18000aed9  mov     rcx, rdi; int
0x18000aedc  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000aee1  mov     ebx, 29Ch
0x18000aee6  test    ebx, ebx
0x18000aee8  jg      short loc_18000AEEE
0x18000aeea  mov     ecx, ebx
0x18000aeec  jmp     short loc_18000AEF7
0x18000aeee  movzx   ecx, bx
0x18000aef1  or      ecx, 80070000h; this
0x18000aef7  mov     [rsp+68h+var_18], ecx
0x18000aefb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000af00  mov     [rsp+68h+var_14], eax
0x18000af04  mov     [rsp+68h+var_10], 0
0x18000af0c  mov     [rsp+68h+var_20], 0
0x18000af14  lea     rax, [rsp+68h+var_18]
0x18000af19  mov     [rsp+68h+var_38], rax
0x18000af1e  mov     [rsp+68h+var_40], rsi
0x18000af23  mov     [rsp+68h+var_48], 0
0x18000af2c  xor     r9d, r9d
0x18000af2f  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000af36  lea     edx, [r9+4Bh]
0x18000af3a  mov     rcx, rdi
0x18000af3d  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000af42  mov     ecx, ebx; dwErrCode
0x18000af44  call    cs:__imp_SetLastError
0x18000af4a  mov     eax, ebx
0x18000af4c  mov     rbx, [rsp+68h+arg_0]
0x18000af51  mov     rsi, [rsp+68h+arg_8]
0x18000af56  add     rsp, 60h
0x18000af5a  pop     rdi
0x18000af5b  retn
```
