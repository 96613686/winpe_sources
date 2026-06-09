# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x10009dc0`
- end: `0x10009dfe`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z`
- size: `62`
- prototype: `void __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1000ebe0`
- `0x1000ed90`
- `0x1000eef0`
- `0x1000f090`

## callees

- `0x10009c20`
- `0x1005e3b0`
- `0x1005f064`

## string_xrefs

- `0x10009df4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __stdcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>("onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
}

```

## disassembly

```asm
0x10009dc0  mov     edi, edi
0x10009dc2  push    ebp
0x10009dc3  mov     ebp, esp
0x10009dc5  push    0FFFFFFFFh
0x10009dc7  push    offset ??1PageDescBlocks@@QAE@XZ_SEH
0x10009dcc  mov     eax, large fs:0
0x10009dd2  push    eax
0x10009dd3  mov     eax, ___security_cookie
0x10009dd8  push    ecx
0x10009dd9  xor     eax, ebp
0x10009ddb  push    eax
0x10009ddc  lea     eax, [ebp+var_C]
0x10009ddf  mov     large fs:0, eax
0x10009de5  mov     eax, [ebp+4]
0x10009de8  sub     esp, 8
0x10009deb  mov     edx, 0E01h
0x10009df0  push    eax
0x10009df1  sub     esp, 8
0x10009df4  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10009df9  call    ??$ReportFailure_Hr@$02@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1005f630  nop
0x1005f631  nop
0x1005f632  mov     edx, [esp-4+arg_4]
0x1005f636  lea     eax, [edx+0Ch]
0x1005f639  mov     ecx, [edx-8]
0x1005f63c  xor     ecx, eax; StackCookie
0x1005f63e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f643  mov     eax, offset stru_10062AB0
0x1005f648  jmp     ___CxxFrameHandler3
```
