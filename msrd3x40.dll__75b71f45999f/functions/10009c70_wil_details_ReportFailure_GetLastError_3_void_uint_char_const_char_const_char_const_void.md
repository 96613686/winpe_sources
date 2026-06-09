# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x10009c70`
- end: `0x10009ccf`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YGKPAXIPBD110@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10009d80`

## callees

- `0x10008920`
- `0x10009100`
- `0x10009c00`
- `0x10009c70`

## string_xrefs

- `0x10009c84`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x10009cc5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __cdecl __noreturn wil::details::ReportFailure_GetLastError<3>(int a1, int a2, int a3, char *a4)
{
  signed int LastErrorFail; // eax
  int v5; // eax
  __int64 v6; // xmm0_8
  void *v7; // [esp-Ch] [ebp-34h]
  unsigned int v8; // [esp-8h] [ebp-30h]
  const char *v9; // [esp+0h] [ebp-28h]
  const char *v10; // [esp+4h] [ebp-24h]
  void *v11; // [esp+8h] [ebp-20h] BYREF
  __int64 v12; // [esp+1Ch] [ebp-Ch]
  int v13; // [esp+24h] [ebp-4h]

  LastErrorFail = wil::details::GetLastErrorFail(
                    (wil::details *)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    v7,
                    v8,
                    a4,
                    v9,
                    v10,
                    v11);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v5 = wil::details::ResultStatus::FromResult(LastErrorFail, &v11);
  v6 = *(_QWORD *)v5;
  v13 = *(_DWORD *)(v5 + 8);
  v12 = v6;
  wil::details::ReportFailure_Base<3,0>("onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
}

```

## disassembly

```asm
0x10009c70  mov     edi, edi
0x10009c72  push    ebp
0x10009c73  mov     ebp, esp
0x10009c75  sub     esp, 20h
0x10009c78  push    esi; char *
0x10009c79  push    edi; char *
0x10009c7a  push    [ebp+arg_C]; char *
0x10009c7d  mov     esi, edx
0x10009c7f  mov     edi, ecx
0x10009c81  sub     esp, 8
0x10009c84  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10009c89  call    ?GetLastErrorFail@details@wil@@YGKPAXIPBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x10009c8e  test    eax, eax
0x10009c90  jle     short loc_10009C9A
0x10009c92  movzx   eax, ax
0x10009c95  or      eax, 80070000h
0x10009c9a  lea     ecx, [ebp+var_20]
0x10009c9d  push    ecx
0x10009c9e  mov     ecx, eax
0x10009ca0  call    ?FromResult@ResultStatus@details@wil@@SG?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x10009ca5  sub     esp, 0Ch
0x10009ca8  mov     edx, esi
0x10009caa  mov     ecx, edi
0x10009cac  movq    xmm0, qword ptr [eax]
0x10009cb0  mov     eax, [eax+8]
0x10009cb3  mov     [ebp+var_4], eax
0x10009cb6  lea     eax, [ebp+var_C]
0x10009cb9  push    eax
0x10009cba  push    [ebp+arg_C]
0x10009cbd  movq    [ebp+var_C], xmm0
0x10009cc2  sub     esp, 8
0x10009cc5  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10009cca  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
