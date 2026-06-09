# _Microsoft::HostGuardian::Client::HgKeyProtection::EncryptWithKeyProtector_::_1_::catch$0

- ea: `0x180015bd5`
- end: `0x180015c65`
- name: `_Microsoft::HostGuardian::Client::HgKeyProtection::EncryptWithKeyProtector_::_1_::catch$0`
- size: `144`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`
- `0x180015bd5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015c37`

## string_xrefs

- `0x180015be7`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::EncryptWithKeyProtector_::_1_::catch_0(
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
    (void *)0x80,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
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
  *(_DWORD *)(a2 + 88) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015bd5  mov     [rsp+arg_8], rdx
0x180015bda  push    rbx
0x180015bdb  push    rbp
0x180015bdc  sub     rsp, 48h
0x180015be0  mov     rbp, rdx
0x180015be3  mov     rcx, [rbp+48h]; this
0x180015be7  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x180015bee  mov     edx, 80h; void *
0x180015bf3  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015bf8  mov     rbx, [rbp+78h]
0x180015bfc  cmp     dword ptr [rbx], 0
0x180015bff  jbe     short loc_180015C20
0x180015c01  cmp     qword ptr [rbx+8], 0
0x180015c06  jz      short loc_180015C20
0x180015c08  mov     rcx, [rbx+8]; pv
0x180015c0c  call    cs:__imp_CoTaskMemFree
0x180015c12  mov     qword ptr [rbx+8], 0
0x180015c1a  mov     dword ptr [rbx], 0
0x180015c20  mov     rbx, [rbp+80h]
0x180015c27  cmp     dword ptr [rbx], 0
0x180015c2a  jbe     short loc_180015C4B
0x180015c2c  cmp     qword ptr [rbx+8], 0
0x180015c31  jz      short loc_180015C4B
0x180015c33  mov     rcx, [rbx+8]; pv
0x180015c37  call    cs:__imp_CoTaskMemFree
0x180015c3d  mov     qword ptr [rbx+8], 0
0x180015c45  mov     dword ptr [rbx], 0
0x180015c4b  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015c50  mov     [rbp+58h], eax
0x180015c53  mov     rax, 0
0x180015c5d  add     rsp, 48h
0x180015c61  pop     rbp
0x180015c62  pop     rbx
0x180015c63  retn
```
