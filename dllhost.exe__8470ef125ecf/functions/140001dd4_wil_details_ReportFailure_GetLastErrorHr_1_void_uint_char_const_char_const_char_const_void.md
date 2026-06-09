# wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140001dd4`
- end: `0x140001e6d`
- name: `??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002f5c`

## callees

- `0x140001d78`
- `0x140001dd4`
- `0x140001e74`
- `0x14000275c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001de2`

## string_xrefs

- `0x140001dfe`: `onecore\com\combase\dllhost\surrogat.cxx`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastErrorHr<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  signed int LastError; // eax
  int v9; // edx
  unsigned int v10; // ebx
  wil::details *v12; // [rsp+30h] [rbp-58h]

  LastError = GetLastError();
  v10 = LastError;
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, (int)"onecore\\com\\combase\\dllhost\\surrogat.cxx", 0, 0, a6, v12);
    LOWORD(v10) = 668;
LABEL_4:
    v10 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_5;
  }
  if ( LastError > 0 )
    goto LABEL_4;
LABEL_5:
  wil::details::HrToNtStatus((wil::details *)v10, v9);
  wil::details::ReportFailure_Base<1,0>(a1, a2);
  return v10;
}

```

## disassembly

```asm
0x140001dd4  push    rbx
0x140001dd6  push    rbp
0x140001dd7  push    rsi
0x140001dd8  push    rdi
0x140001dd9  sub     rsp, 68h
0x140001ddd  mov     edi, edx
0x140001ddf  mov     rsi, rcx
0x140001de2  call    cs:__imp_GetLastError
0x140001de8  mov     rbp, [rsp+88h+arg_28]
0x140001df0  mov     ebx, eax
0x140001df2  test    eax, eax
0x140001df4  jnz     short loc_140001E27
0x140001df6  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x140001dfe  lea     r8, aOnecoreComComb; "onecore\\com\\combase\\dllhost\\surroga"...
0x140001e05  mov     [rsp+88h+var_60], rbp; __int64
0x140001e0a  xor     r9d, r9d; int
0x140001e0d  mov     edx, edi; int
0x140001e0f  mov     [rsp+88h+var_68], 0; __int64
0x140001e18  mov     rcx, rsi; int
0x140001e1b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140001e20  mov     ebx, 29Ch
0x140001e25  jmp     short loc_140001E29
0x140001e27  jle     short loc_140001E32
0x140001e29  movzx   ebx, bx
0x140001e2c  or      ebx, 80070000h
0x140001e32  mov     ecx, ebx; this
0x140001e34  mov     [rsp+88h+var_38], ebx
0x140001e38  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140001e3d  mov     [rsp+88h+var_34], eax
0x140001e41  mov     edx, edi
0x140001e43  lea     rax, [rsp+88h+var_38]
0x140001e48  mov     [rsp+88h+var_30], 0
0x140001e50  mov     [rsp+88h+var_58], rax
0x140001e55  mov     rcx, rsi
0x140001e58  mov     [rsp+88h+var_60], rbp
0x140001e5d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140001e62  mov     eax, ebx
0x140001e64  add     rsp, 68h
0x140001e68  pop     rdi
0x140001e69  pop     rsi
0x140001e6a  pop     rbp
0x140001e6b  pop     rbx
0x140001e6c  retn
```
