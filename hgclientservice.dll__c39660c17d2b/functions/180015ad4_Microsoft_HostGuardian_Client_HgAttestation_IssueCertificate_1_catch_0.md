# _Microsoft::HostGuardian::Client::HgAttestation::IssueCertificate_::_1_::catch$0

- ea: `0x180015ad4`
- end: `0x180015b64`
- name: `_Microsoft::HostGuardian::Client::HgAttestation::IssueCertificate_::_1_::catch$0`
- size: `144`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`
- `0x180015ad4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b36`

## string_xrefs

- `0x180015ae6`: `servercommon\base\securehostingservice\common\service\lib\hgattestation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgAttestation::IssueCertificate_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rdx
  wil *v6; // rcx
  unsigned int v7; // r8d
  __int64 v8; // rbx
  __int64 v9; // rbx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x6C,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
    a4);
  v8 = *(_QWORD *)(a2 + 120);
  if ( *(_DWORD *)v8 && *(_QWORD *)(v8 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v8 + 8));
    *(_QWORD *)(v8 + 8) = 0;
    *(_DWORD *)v8 = 0;
  }
  v9 = *(_QWORD *)(a2 + 128);
  if ( *(_DWORD *)v9 && *(_QWORD *)(v9 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v9 + 8));
    *(_QWORD *)(v9 + 8) = 0;
    *(_DWORD *)v9 = 0;
  }
  *(_DWORD *)(a2 + 96) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015ad4  mov     [rsp+arg_8], rdx
0x180015ad9  push    rbx
0x180015ada  push    rbp
0x180015adb  sub     rsp, 48h
0x180015adf  mov     rbp, rdx
0x180015ae2  mov     rcx, [rbp+48h]; this
0x180015ae6  lea     r8, aServercommonBa_5; "servercommon\\base\\securehostingservic"...
0x180015aed  mov     edx, 6Ch ; 'l'; void *
0x180015af2  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015af7  mov     rbx, [rbp+78h]
0x180015afb  cmp     dword ptr [rbx], 0
0x180015afe  jbe     short loc_180015B1F
0x180015b00  cmp     qword ptr [rbx+8], 0
0x180015b05  jz      short loc_180015B1F
0x180015b07  mov     rcx, [rbx+8]; pv
0x180015b0b  call    cs:__imp_CoTaskMemFree
0x180015b11  mov     qword ptr [rbx+8], 0
0x180015b19  mov     dword ptr [rbx], 0
0x180015b1f  mov     rbx, [rbp+80h]
0x180015b26  cmp     dword ptr [rbx], 0
0x180015b29  jbe     short loc_180015B4A
0x180015b2b  cmp     qword ptr [rbx+8], 0
0x180015b30  jz      short loc_180015B4A
0x180015b32  mov     rcx, [rbx+8]; pv
0x180015b36  call    cs:__imp_CoTaskMemFree
0x180015b3c  mov     qword ptr [rbx+8], 0
0x180015b44  mov     dword ptr [rbx], 0
0x180015b4a  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015b4f  mov     [rbp+60h], eax
0x180015b52  mov     rax, 0
0x180015b5c  add     rsp, 48h
0x180015b60  pop     rbp
0x180015b61  pop     rbx
0x180015b62  retn
```
