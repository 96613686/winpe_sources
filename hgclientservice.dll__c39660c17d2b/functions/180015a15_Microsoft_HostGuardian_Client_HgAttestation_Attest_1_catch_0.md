# _Microsoft::HostGuardian::Client::HgAttestation::Attest_::_1_::catch$0

- ea: `0x180015a15`
- end: `0x180015ace`
- name: `_Microsoft::HostGuardian::Client::HgAttestation::Attest_::_1_::catch$0`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`
- `0x1800062c4`
- `0x180015a15`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015aa5`

## string_xrefs

- `0x180015a29`: `servercommon\base\securehostingservice\common\service\lib\hgattestation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgAttestation::Attest_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rdx
  wil *v6; // rcx
  unsigned int v7; // r8d
  LPVOID *v8; // rbx
  __int64 v9; // rdi
  _DWORD *v10; // rsi
  _QWORD *v11; // rax

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x37,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
    a4);
  v8 = *(LPVOID **)(a2 + 160);
  if ( *v8 )
  {
    v9 = 0;
    v10 = *(_DWORD **)(a2 + 152);
    if ( *v10 )
    {
      do
      {
        v11 = *v8;
        if ( !*((_DWORD *)*v8 + 6 * v9 + 2) )
          break;
        if ( !v11[3 * v9 + 2] )
          break;
        CoTaskMemFree((LPVOID)v11[3 * v9 + 2]);
        *((_QWORD *)*v8 + 3 * v9 + 2) = 0;
        *((_DWORD *)*v8 + 6 * v9 + 2) = 0;
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 < *v10 );
    }
    CoTaskMemFree(*v8);
    *v8 = 0;
  }
  *(_DWORD *)(a2 + 112) = wil::ResultFromCaughtException(v6, v5, v7);
  return 0;
}

```

## disassembly

```asm
0x180015a15  mov     [rsp+arg_8], rdx
0x180015a1a  push    rbx
0x180015a1b  push    rbp
0x180015a1c  push    rsi
0x180015a1d  push    rdi
0x180015a1e  sub     rsp, 58h
0x180015a22  mov     rbp, rdx
0x180015a25  mov     rcx, [rbp+58h]; this
0x180015a29  lea     r8, aServercommonBa_5; "servercommon\\base\\securehostingservic"...
0x180015a30  mov     edx, 37h ; '7'; void *
0x180015a35  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015a3a  mov     rbx, [rbp+0A0h]
0x180015a41  cmp     qword ptr [rbx], 0
0x180015a45  jz      short loc_180015AB2
0x180015a47  xor     edi, edi
0x180015a49  mov     rsi, [rbp+98h]
0x180015a50  cmp     [rsi], edi
0x180015a52  jbe     short loc_180015AA2
0x180015a54  lea     rcx, [rdi+rdi*2]
0x180015a58  mov     rax, [rbx]
0x180015a5b  cmp     dword ptr [rax+rcx*8+8], 0
0x180015a60  jbe     short loc_180015AA2
0x180015a62  lea     rcx, [rdi+rdi*2]
0x180015a66  cmp     qword ptr [rax+rcx*8+10h], 0
0x180015a6c  jz      short loc_180015AA2
0x180015a6e  lea     rdx, [rdi+rdi*2]
0x180015a72  mov     rcx, [rax+rdx*8+10h]; pv
0x180015a77  call    cs:__imp_CoTaskMemFree
0x180015a7d  lea     rcx, [rdi+rdi*2]
0x180015a81  mov     rax, [rbx]
0x180015a84  mov     qword ptr [rax+rcx*8+10h], 0
0x180015a8d  lea     rcx, [rdi+rdi*2]
0x180015a91  mov     rax, [rbx]
0x180015a94  mov     dword ptr [rax+rcx*8+8], 0
0x180015a9c  inc     edi
0x180015a9e  cmp     edi, [rsi]
0x180015aa0  jb      short loc_180015A54
0x180015aa2  mov     rcx, [rbx]; pv
0x180015aa5  call    cs:__imp_CoTaskMemFree
0x180015aab  mov     qword ptr [rbx], 0
0x180015ab2  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015ab7  mov     [rbp+70h], eax
0x180015aba  mov     rax, 0
0x180015ac4  add     rsp, 58h
0x180015ac8  pop     rdi
0x180015ac9  pop     rsi
0x180015aca  pop     rbp
0x180015acb  pop     rbx
0x180015acc  retn
```
