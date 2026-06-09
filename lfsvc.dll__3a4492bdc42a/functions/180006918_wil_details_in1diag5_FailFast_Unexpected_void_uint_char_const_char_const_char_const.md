# wil::details::in1diag5::FailFast_Unexpected(void *,uint,char const *,char const *,char const *)

- ea: `0x180006918`
- end: `0x18000694b`
- name: `?FailFast_Unexpected@in1diag5@details@wil@@YAXPEAXIPEBD11@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(wil::details::in1diag5 *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f04`

## callees

- `0x1800050fc`

## string_xrefs

- `0x180006939`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006926`: `(status == WAIT_TIMEOUT) || (status == WAIT_OBJECT_0) || (status == WAIT_ABANDONED) || (bAlertable && (status == WAIT_IO_COMPLETION))`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag5::FailFast_Unexpected(
        wil::details::in1diag5 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (unsigned int)"wil::mutex_t<class wil::details::unique_storage<struct wil::details::resource_policy<void *,void (__cd"
                  "ecl*)(void *) noexcept,&void __cdecl wil::details::CloseHandle(void *),struct wistd::integral_constant"
                  "<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,struct wil::err_returncode_policy>::acquire",
    (__int64)"(status == WAIT_TIMEOUT) || (status == WAIT_OBJECT_0) || (status == WAIT_ABANDONED) || (bAlertable && (stat"
             "us == WAIT_IO_COMPLETION))",
    retaddr);
}

```

## disassembly

```asm
0x180006918  sub     rsp, 48h
0x18000691c  mov     rax, [rsp+48h]
0x180006921  mov     [rsp+48h+var_20], rax
0x180006926  lea     rax, aStatusWaitTime; "(status == WAIT_TIMEOUT) || (status == "...
0x18000692d  mov     [rsp+48h+var_28], rax
0x180006932  lea     r9, aWilMutexTClass; "wil::mutex_t<class wil::details::unique"...
0x180006939  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006940  mov     edx, 0E01h
0x180006945  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
