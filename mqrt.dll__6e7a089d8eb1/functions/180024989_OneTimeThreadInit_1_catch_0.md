# _OneTimeThreadInit_::_1_::catch$0

- ea: `0x180024989`
- end: `0x1800249e9`
- name: `_OneTimeThreadInit_::_1_::catch$0`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800022d6`
- `0x18000a33c`
- `0x180013bdc`
- `0x180024989`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800249c8`
- `RPCRT4!RpcBindingFree` at `0x1800249c8`

## pseudocode

```c
void __fastcall __noreturn OneTimeThreadInit_::_1_::catch_0(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids);
  RpcBindingFree((RPC_BINDING_HANDLE *)(a2 + 80));
  LogIllegalPoint((wchar_t *)L"rt/rtmain", 0x4B2u);
  throw;
}

```

## disassembly

```asm
0x180024989  mov     [rsp+arg_8], rdx
0x18002498e  push    rbp
0x18002498f  sub     rsp, 20h
0x180024993  mov     rbp, rdx
0x180024996  lea     rax, WPP_GLOBAL_Control
0x18002499d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249a4  cmp     rcx, rax
0x1800249a7  jz      short loc_1800249C4
0x1800249a9  test    byte ptr [rcx+1Ch], 1
0x1800249ad  jz      short loc_1800249C4
0x1800249af  mov     edx, 0Bh
0x1800249b4  lea     r8, WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids
0x1800249bb  mov     rcx, [rcx+10h]
0x1800249bf  call    WPP_SF_
0x1800249c4  lea     rcx, [rbp+50h]; Binding
0x1800249c8  call    cs:__imp_RpcBindingFree
0x1800249ce  mov     edx, 4B2h; unsigned __int16
0x1800249d3  lea     rcx, aRtRtmain; "rt/rtmain"
0x1800249da  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x1800249df  xor     edx, edx; pThrowInfo
0x1800249e1  xor     ecx, ecx; pExceptionObject
0x1800249e3  call    _CxxThrowException_0
```
