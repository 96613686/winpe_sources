# OobeZdpElevatedManagerCore::StartUpdate(CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *)

- ea: `0x180010a10`
- end: `0x180010b7c`
- name: `?StartUpdate@OobeZdpElevatedManagerCore@@UEAAJPEAUIOobeZdpManagerCallBackCore@CloudExperienceHostAPI@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x18000b098`
- `0x18000f698`
- `0x180010160`
- `0x180010a10`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180010b64`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180010b64`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x180010a25`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x180010a25`

## string_xrefs

- `0x180010a79`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x180010adc`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x180010b15`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x180010b50`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OobeZdpElevatedManagerCore::StartUpdate(
        RTL_SRWLOCK *this,
        struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  PVOID Ptr; // rsi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CoAddRefServerProcess();
  if ( IsLowBattery() )
  {
    v4 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *, __int64))(*(_QWORD *)a2 + 48LL))(
           a2,
           4);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v4,
        (int)a2);
    v5 = -2147467260;
  }
  else
  {
    Ptr = this[5].Ptr;
    this[5].Ptr = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( Ptr )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    v7 = OobeZdpElevatedManagerCore::RunZDP(this);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *, __int64))(*(_QWORD *)a2 + 48LL))(
             a2,
             4);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
          (const char *)(unsigned int)v9,
          (int)a2);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v7,
        (int)a2);
      v8 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBackCore *, __int64))(*(_QWORD *)a2 + 48LL))(
             a2,
             4);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
          (const char *)(unsigned int)v8,
          v11);
    }
  }
  CoReleaseServerProcess();
  return v5;
}

```

## disassembly

```asm
0x180010a10  mov     [rsp+arg_0], rbx
0x180010a15  mov     [rsp+arg_18], rsi
0x180010a1a  push    rdi
0x180010a1b  sub     rsp, 40h
0x180010a1f  mov     rbx, rdx
0x180010a22  mov     rdi, rcx
0x180010a25  call    cs:__imp_CoAddRefServerProcess
0x180010a2b  mov     [rsp+48h+arg_11], 1
0x180010a30  mov     [rsp+48h+arg_8], 1
0x180010a35  mov     qword ptr [rsp+48h+var_28], rbx; int
0x180010a3a  lea     rax, [rsp+48h+arg_8]
0x180010a3f  mov     [rsp+48h+var_20], rax
0x180010a44  mov     [rsp+48h+var_18], 1
0x180010a49  call    ?IsLowBattery@@YA_NXZ; IsLowBattery(void)
0x180010a4e  test    al, al
0x180010a50  jz      short loc_180010A95
0x180010a52  cmp     [rsp+48h+arg_8], 0
0x180010a57  jz      short loc_180010A8B
0x180010a59  mov     rax, [rbx]
0x180010a5c  mov     edx, 4
0x180010a61  mov     rcx, rbx
0x180010a64  mov     rax, [rax+30h]
0x180010a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6d  mov     rcx, [rsp+48h]; this
0x180010a72  test    eax, eax
0x180010a74  jns     short loc_180010A8B
0x180010a76  mov     r9d, eax; char *
0x180010a79  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010a80  mov     edx, 34h ; '4'; void *
0x180010a85  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010a8a  nop
0x180010a8b  mov     edi, 80004004h
0x180010a90  jmp     loc_180010B64
0x180010a95  mov     rsi, [rdi+28h]
0x180010a99  mov     [rdi+28h], rbx
0x180010a9d  test    rbx, rbx
0x180010aa0  jz      short loc_180010AB1
0x180010aa2  mov     rax, [rbx]
0x180010aa5  mov     rcx, rbx
0x180010aa8  mov     rax, [rax+8]
0x180010aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab1  test    rsi, rsi
0x180010ab4  jz      short loc_180010AC6
0x180010ab6  mov     rax, [rsi]
0x180010ab9  mov     rcx, rsi
0x180010abc  mov     rax, [rax+10h]
0x180010ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac5  nop
0x180010ac6  mov     rcx, rdi; this
0x180010ac9  call    ?RunZDP@OobeZdpElevatedManagerCore@@AEAAJXZ; OobeZdpElevatedManagerCore::RunZDP(void)
0x180010ace  mov     edi, eax
0x180010ad0  test    eax, eax
0x180010ad2  jns     short loc_180010B29
0x180010ad4  mov     rcx, [rsp+48h]; this
0x180010ad9  mov     r9d, eax; char *
0x180010adc  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010ae3  mov     edx, 40h ; '@'; void *
0x180010ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010aed  nop
0x180010aee  cmp     [rsp+48h+arg_8], 0
0x180010af3  jz      short loc_180010B27
0x180010af5  mov     rax, [rbx]
0x180010af8  mov     edx, 4
0x180010afd  mov     rcx, rbx
0x180010b00  mov     rax, [rax+30h]
0x180010b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b09  mov     rcx, [rsp+48h]; this
0x180010b0e  test    eax, eax
0x180010b10  jns     short loc_180010B27
0x180010b12  mov     r9d, eax; char *
0x180010b15  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010b1c  mov     edx, 34h ; '4'; void *
0x180010b21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010b26  nop
0x180010b27  jmp     short loc_180010B64
0x180010b29  cmp     [rsp+48h+arg_8], 0
0x180010b2e  jz      short loc_180010B62
0x180010b30  mov     rax, [rbx]
0x180010b33  mov     edx, 4
0x180010b38  mov     rcx, rbx
0x180010b3b  mov     rax, [rax+30h]
0x180010b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b44  mov     rcx, [rsp+48h]; this
0x180010b49  test    eax, eax
0x180010b4b  jns     short loc_180010B62
0x180010b4d  mov     r9d, eax; char *
0x180010b50  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010b57  mov     edx, 34h ; '4'; void *
0x180010b5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010b61  nop
0x180010b62  xor     edi, edi
0x180010b64  call    cs:__imp_CoReleaseServerProcess
0x180010b6a  mov     eax, edi
0x180010b6c  mov     rbx, [rsp+48h+arg_0]
0x180010b71  mov     rsi, [rsp+48h+arg_18]
0x180010b76  add     rsp, 40h
0x180010b7a  pop     rdi
0x180010b7b  retn
```
