# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x1003937f`
- end: `0x1003939c`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z`
- size: `29`
- prototype: `void __cdecl __noreturn(wil::details::in1diag3 *this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10038410`

## callees

- `0x1000750b`

## string_xrefs

- `0x10039392`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __cdecl __noreturn wil::details::in1diag3::_FailFast_Hr(wil::details::in1diag3 *this, void *a2)
{
  void *v2; // ecx
  int retaddr; // [esp+4h] [ebp+4h]

  wil::details::ReportFailure_Hr<3>(
    v2,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (int)v2,
    (int)v2,
    retaddr,
    (HRESULT)a2);
}

```

## disassembly

```asm
0x1003937f  mov     edi, edi
0x10039381  push    ebp
0x10039382  mov     ebp, esp
0x10039384  push    ecx
0x10039385  push    [ebp+arg_4]
0x10039388  mov     edx, 14CCh
0x1003938d  push    dword ptr [ebp+4]
0x10039390  push    ecx
0x10039391  push    ecx
0x10039392  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10039397  call    ??$ReportFailure_Hr@$02@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
