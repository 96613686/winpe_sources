# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x10039359`
- end: `0x10039378`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z`
- size: `31`
- prototype: `void __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10038410`

## callees

- `0x1000750b`

## string_xrefs

- `0x1003936e`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
void __thiscall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        void *ecx0,
        wil::details::in1diag3 *this,
        void *a3,
        unsigned int a4,
        const char *a5)
{
  void *retaddr; // [esp+4h] [ebp+4h]

  wil::details::ReportFailure_Hr<3>(
    "multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
    ecx0,
    ecx0,
    retaddr,
    -2147418113,
    ecx0);
}

```

## disassembly

```asm
0x10039359  mov     edi, edi
0x1003935b  push    ebp
0x1003935c  mov     ebp, esp
0x1003935e  push    ecx
0x1003935f  push    8000FFFFh
0x10039364  push    dword ptr [ebp+4]
0x10039367  mov     edx, 0F1h
0x1003936c  push    ecx
0x1003936d  push    ecx
0x1003936e  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10039373  call    ??$ReportFailure_Hr@$02@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
