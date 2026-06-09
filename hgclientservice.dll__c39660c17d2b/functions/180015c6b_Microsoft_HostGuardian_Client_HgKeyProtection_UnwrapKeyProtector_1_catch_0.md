# _Microsoft::HostGuardian::Client::HgKeyProtection::UnwrapKeyProtector_::_1_::catch$0

- ea: `0x180015c6b`
- end: `0x180015d57`
- name: `_Microsoft::HostGuardian::Client::HgKeyProtection::UnwrapKeyProtector_::_1_::catch$0`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`
- `0x180015c6b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015cfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d26`

## string_xrefs

- `0x180015c7d`: `servercommon\base\securehostingservice\common\service\lib\hgkeyprotection.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgKeyProtection::UnwrapKeyProtector_::_1_::catch_0(
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
  __int64 v10; // rbx
  __int64 v11; // rbx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x3C,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgkeyprotection.cpp",
    a4);
  v8 = *(_QWORD *)(a2 + 160);
  if ( *(_DWORD *)v8 && *(_QWORD *)(v8 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v8 + 8));
    *(_QWORD *)(v8 + 8) = 0;
    *(_DWORD *)v8 = 0;
  }
  v9 = *(_QWORD *)(a2 + 168);
  if ( *(_DWORD *)v9 && *(_QWORD *)(v9 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v9 + 8));
    *(_QWORD *)(v9 + 8) = 0;
    *(_DWORD *)v9 = 0;
  }
  v10 = *(_QWORD *)(a2 + 176);
  if ( *(_DWORD *)v10 && *(_QWORD *)(v10 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v10 + 8));
    *(_QWORD *)(v10 + 8) = 0;
    *(_DWORD *)v10 = 0;
  }
  v11 = *(_QWORD *)(a2 + 184);
  if ( *(_DWORD *)v11 && *(_QWORD *)(v11 + 8) )
  {
    CoTaskMemFree(*(LPVOID *)(v11 + 8));
    *(_QWORD *)(v11 + 8) = 0;
    *(_DWORD *)v11 = 0;
  }
  *(_DWORD *)(a2 + 144) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015c6b  mov     [rsp+arg_8], rdx
0x180015c70  push    rbx
0x180015c71  push    rbp
0x180015c72  sub     rsp, 58h
0x180015c76  mov     rbp, rdx
0x180015c79  mov     rcx, [rbp+78h]; this
0x180015c7d  lea     r8, aServercommonBa_6; "servercommon\\base\\securehostingservic"...
0x180015c84  mov     edx, 3Ch ; '<'; void *
0x180015c89  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015c8e  mov     rbx, [rbp+0A0h]
0x180015c95  cmp     dword ptr [rbx], 0
0x180015c98  jbe     short loc_180015CB9
0x180015c9a  cmp     qword ptr [rbx+8], 0
0x180015c9f  jz      short loc_180015CB9
0x180015ca1  mov     rcx, [rbx+8]; pv
0x180015ca5  call    cs:__imp_CoTaskMemFree
0x180015cab  mov     qword ptr [rbx+8], 0
0x180015cb3  mov     dword ptr [rbx], 0
0x180015cb9  mov     rbx, [rbp+0A8h]
0x180015cc0  cmp     dword ptr [rbx], 0
0x180015cc3  jbe     short loc_180015CE4
0x180015cc5  cmp     qword ptr [rbx+8], 0
0x180015cca  jz      short loc_180015CE4
0x180015ccc  mov     rcx, [rbx+8]; pv
0x180015cd0  call    cs:__imp_CoTaskMemFree
0x180015cd6  mov     qword ptr [rbx+8], 0
0x180015cde  mov     dword ptr [rbx], 0
0x180015ce4  mov     rbx, [rbp+0B0h]
0x180015ceb  cmp     dword ptr [rbx], 0
0x180015cee  jbe     short loc_180015D0F
0x180015cf0  cmp     qword ptr [rbx+8], 0
0x180015cf5  jz      short loc_180015D0F
0x180015cf7  mov     rcx, [rbx+8]; pv
0x180015cfb  call    cs:__imp_CoTaskMemFree
0x180015d01  mov     qword ptr [rbx+8], 0
0x180015d09  mov     dword ptr [rbx], 0
0x180015d0f  mov     rbx, [rbp+0B8h]
0x180015d16  cmp     dword ptr [rbx], 0
0x180015d19  jbe     short loc_180015D3A
0x180015d1b  cmp     qword ptr [rbx+8], 0
0x180015d20  jz      short loc_180015D3A
0x180015d22  mov     rcx, [rbx+8]; pv
0x180015d26  call    cs:__imp_CoTaskMemFree
0x180015d2c  mov     qword ptr [rbx+8], 0
0x180015d34  mov     dword ptr [rbx], 0
0x180015d3a  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015d3f  mov     [rbp+90h], eax
0x180015d45  mov     rax, 0
0x180015d4f  add     rsp, 58h
0x180015d53  pop     rbp
0x180015d54  pop     rbx
0x180015d55  retn
```
