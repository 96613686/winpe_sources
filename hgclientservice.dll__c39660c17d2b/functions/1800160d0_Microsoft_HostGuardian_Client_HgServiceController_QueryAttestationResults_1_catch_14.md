# _Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults_::_1_::catch$14

- ea: `0x1800160d0`
- end: `0x18001615c`
- name: `_Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults_::_1_::catch$14`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800077a0`
- `0x1800160d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016104`
- `OLEAUT32!__imp_SysFreeString` at `0x180016104`

## string_xrefs

- `0x1800160e4`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x180016113`: `Failed to retrieve new certificates, continue use cached certificates...`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults_::_1_::catch_14(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // r8
  BSTR *v6; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 328),
    (void *)0x67,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    a4);
  v6 = *(BSTR **)(a2 + 152);
  if ( v6 )
    SysFreeString(*v6);
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    *(_QWORD *)(a2 + 240) = L"Failed to retrieve new certificates, continue use cached certificates...";
    *(_QWORD *)(a2 + 248) = 146;
    McGenEventWrite_EventWriteTransfer(
      (__int64)v6,
      (const EVENT_DESCRIPTOR *)ServiceDebugInformational,
      v5,
      2u,
      (PEVENT_DATA_DESCRIPTOR)(a2 + 224));
  }
  return 0;
}

```

## disassembly

```asm
0x1800160d0  mov     [rsp+arg_8], rdx
0x1800160d5  push    rbp
0x1800160d6  sub     rsp, 40h
0x1800160da  mov     rbp, rdx
0x1800160dd  mov     rcx, [rbp+148h]; this
0x1800160e4  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x1800160eb  mov     edx, 67h ; 'g'; void *
0x1800160f0  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800160f5  mov     rcx, [rbp+98h]
0x1800160fc  test    rcx, rcx
0x1800160ff  jz      short loc_18001610A
0x180016101  mov     rcx, [rcx]; bstrString
0x180016104  call    cs:__imp_SysFreeString
0x18001610a  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180016111  jz      short loc_18001614B
0x180016113  lea     rax, aFailedToRetrie; "Failed to retrieve new certificates, co"...
0x18001611a  mov     [rbp+0F0h], rax
0x180016121  mov     qword ptr [rbp+0F8h], 92h
0x18001612c  lea     rax, [rbp+0E0h]
0x180016133  mov     [rsp+48h+var_28], rax
0x180016138  mov     r9d, 2
0x18001613e  lea     rdx, ServiceDebugInformational
0x180016145  call    McGenEventWrite_EventWriteTransfer
0x18001614a  nop
0x18001614b  mov     rax, 0
0x180016155  add     rsp, 40h
0x180016159  pop     rbp
0x18001615a  retn
```
