# std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>(void)

- ea: `0x18001f4b0`
- end: `0x18001f5a4`
- name: `??$?0$$V@?$_Ref_count_obj2@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@std@@QEAA@XZ`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f798`

## callees

- `0x180001bcc`
- `0x18000270c`
- `0x180009ce8`
- `0x18001f1cc`
- `0x18001f4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001f516`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001f516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f52a`

## string_xrefs

- `0x18001f592`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>(
        __int64 a1)
{
  _QWORD *v2; // rdi
  HANDLE Event; // rbp
  const char *v4; // r9
  _QWORD *v5; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>::`vftable';
  v2 = (_QWORD *)(a1 + 16);
  memset_0((void *)(a1 + 24), 0, 0x98u);
  *v2 = &Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::`vftable';
  v2[1] = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C6A,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v2 + 1,
    Event);
  v2[2] = 0;
  v2[3] = 0;
  v2[4] = 0;
  v5 = operator new(0x28u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  v2[3] = v5;
  v2[19] = 0;
  return a1;
}

```

## disassembly

```asm
0x18001f4b0  mov     [rsp+arg_10], rbx
0x18001f4b5  push    rbp
0x18001f4b6  push    rsi
0x18001f4b7  push    rdi
0x18001f4b8  sub     rsp, 20h
0x18001f4bc  mov     rsi, rcx
0x18001f4bf  mov     dword ptr [rcx+8], 1
0x18001f4c6  mov     dword ptr [rcx+0Ch], 1
0x18001f4cd  lea     rax, ??_7?$_Ref_count_obj2@VAsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar>::`vftable'
0x18001f4d4  mov     [rcx], rax
0x18001f4d7  lea     rdi, [rcx+10h]
0x18001f4db  mov     [rsp+38h+arg_0], rdi
0x18001f4e0  add     rcx, 18h; void *
0x18001f4e4  xor     edx, edx; Val
0x18001f4e6  mov     r8d, 98h; Size
0x18001f4ec  call    memset_0
0x18001f4f1  lea     rax, ??_7AsyncObjectRegistrar@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::AsyncObjectRegistrar::`vftable'
0x18001f4f8  mov     [rdi], rax
0x18001f4fb  lea     rbx, [rdi+8]
0x18001f4ff  mov     [rsp+38h+arg_8], rbx
0x18001f504  and     qword ptr [rbx], 0
0x18001f508  xor     edx, edx; lpName
0x18001f50a  xor     ecx, ecx; lpEventAttributes
0x18001f50c  mov     r9d, 1F0003h; dwDesiredAccess
0x18001f512  lea     r8d, [rdx+1]; dwFlags
0x18001f516  call    cs:__imp_CreateEventExW
0x18001f51d  nop     dword ptr [rax+rax+00h]
0x18001f522  mov     rbp, rax
0x18001f525  test    rax, rax
0x18001f528  jz      short loc_18001F58D
0x18001f52a  call    cs:__imp_GetLastError
0x18001f531  nop     dword ptr [rax+rax+00h]
0x18001f536  mov     rdx, rbp
0x18001f539  mov     rcx, rbx
0x18001f53c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f541  nop
0x18001f542  xor     eax, eax
0x18001f544  mov     [rdi+10h], rax
0x18001f548  lea     rbx, [rdi+18h]
0x18001f54c  mov     [rsp+38h+arg_8], rbx
0x18001f551  and     [rbx], rax
0x18001f554  and     [rbx+8], rax
0x18001f558  lea     ecx, [rax+28h]; Size
0x18001f55b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f560  mov     [rax], rax
0x18001f563  mov     [rax+8], rax
0x18001f567  mov     [rax+10h], rax
0x18001f56b  mov     word ptr [rax+18h], 101h
0x18001f571  mov     [rbx], rax
0x18001f574  and     qword ptr [rdi+98h], 0
0x18001f57c  mov     rax, rsi
0x18001f57f  mov     rbx, [rsp+38h+arg_10]
0x18001f584  add     rsp, 20h
0x18001f588  pop     rdi
0x18001f589  pop     rsi
0x18001f58a  pop     rbp
0x18001f58b  retn
0x18001f58d  mov     rcx, [rsp+38h]; this
0x18001f592  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f599  mov     edx, 1C6Ah; void *
0x18001f59e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
