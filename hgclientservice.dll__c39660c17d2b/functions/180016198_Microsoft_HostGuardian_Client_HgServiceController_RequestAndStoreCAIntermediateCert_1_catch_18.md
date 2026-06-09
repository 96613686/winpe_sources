# _Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert_::_1_::catch$18

- ea: `0x180016198`
- end: `0x180016200`
- name: `_Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert_::_1_::catch$18`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x18000e008`
- `0x180014e74`
- `0x180016198`

## string_xrefs

- `0x1800161ce`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert_::_1_::catch_18(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  __int64 v5; // rcx

  v5 = *(_QWORD *)(a2 + 144);
  if ( *(_QWORD *)(v5 + 144)
    || (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(*(_QWORD *)(v5 + 144)) != 2 )
  {
    wil::details::in1diag3::Throw_CaughtException(*(wil::details::in1diag3 **)(a2 + 136), (void *)a2, a3, a4);
  }
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 136),
    (void *)0x270,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016198  mov     [rsp+arg_8], rdx
0x18001619d  push    rbp
0x18001619e  sub     rsp, 20h
0x1800161a2  mov     rbp, rdx
0x1800161a5  mov     rcx, [rbp+90h]
0x1800161ac  cmp     qword ptr [rcx+90h], 0
0x1800161b4  jnz     short loc_1800161EC
0x1800161b6  mov     rcx, [rcx+90h]
0x1800161bd  call    ?GetCertificateDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(_CERT_CONTEXT const *)
0x1800161c2  cmp     eax, 2
0x1800161c5  jnz     short loc_1800161EC
0x1800161c7  mov     rcx, [rbp+88h]; this
0x1800161ce  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x1800161d5  mov     edx, 270h; void *
0x1800161da  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800161df  nop
0x1800161e0  mov     rax, 0
0x1800161ea  jmp     short loc_1800161F9
0x1800161ec  mov     rcx, [rbp+88h]; this
0x1800161f3  call    ?Throw_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_CaughtException(void *,uint,char const *)
0x1800161f9  add     rsp, 20h
0x1800161fd  pop     rbp
0x1800161fe  retn
```
