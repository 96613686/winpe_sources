# _Microsoft::HostGuardian::Client::HgKeyProtection::DecryptWithKeyProtector_::_1_::catch$0

- ea: `0x180015b6a`
- end: `0x180015bcf`
- name: `_Microsoft::HostGuardian::Client::HgKeyProtection::DecryptWithKeyProtector_::_1_::catch$0`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`
- `0x180015b6a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ba1`

## string_xrefs

- `0x180015b7c`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::DecryptWithKeyProtector_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rdx
  wil *v6; // rcx
  unsigned int v7; // r8d
  __int64 v8; // rbx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xAE,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
    a4);
  v8 = *(_QWORD *)(a2 + 72);
  if ( *(_DWORD *)v8 && *(_QWORD *)(v8 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v8 + 8));
    *(_QWORD *)(v8 + 8) = 0;
    *(_DWORD *)v8 = 0;
  }
  *(_DWORD *)(a2 + 56) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015b6a  mov     [rsp+arg_8], rdx
0x180015b6f  push    rbx
0x180015b70  push    rbp
0x180015b71  sub     rsp, 28h
0x180015b75  mov     rbp, rdx
0x180015b78  mov     rcx, [rbp+28h]; this
0x180015b7c  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x180015b83  mov     edx, 0AEh; void *
0x180015b88  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015b8d  mov     rbx, [rbp+48h]
0x180015b91  cmp     dword ptr [rbx], 0
0x180015b94  jbe     short loc_180015BB5
0x180015b96  cmp     qword ptr [rbx+8], 0
0x180015b9b  jz      short loc_180015BB5
0x180015b9d  mov     rcx, [rbx+8]; pv
0x180015ba1  call    cs:__imp_CoTaskMemFree
0x180015ba7  mov     qword ptr [rbx+8], 0
0x180015baf  mov     dword ptr [rbx], 0
0x180015bb5  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015bba  mov     [rbp+38h], eax
0x180015bbd  mov     rax, 0
0x180015bc7  add     rsp, 28h
0x180015bcb  pop     rbp
0x180015bcc  pop     rbx
0x180015bcd  retn
```
