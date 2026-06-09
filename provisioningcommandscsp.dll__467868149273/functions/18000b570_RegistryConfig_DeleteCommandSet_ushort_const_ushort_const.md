# RegistryConfig::DeleteCommandSet(ushort const *,ushort const *)

- ea: `0x18000b570`
- end: `0x18000b69b`
- name: `?DeleteCommandSet@RegistryConfig@@QEAAXPEBG0@Z`
- size: `299`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800090e0`

## callees

- `0x180001134`
- `0x180008da4`
- `0x18000b254`
- `0x18000b570`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b65a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b65a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b63b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b63b`

## string_xrefs

- `0x18000b689`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryConfig::DeleteCommandSet(HKEY *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  _QWORD *v5; // rbx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  LPCWSTR *v9; // rax
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  const wchar_t *v12; // [rsp+20h] [rbp-60h]
  LPCWSTR *v13; // [rsp+40h] [rbp-40h] BYREF
  const unsigned __int16 *v14; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v15[2]; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = this + 1;
  v12 = L"\\";
  RegistryConfig::AppendStrings(this, lpSubKey, 5);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v9 = lpSubKey;
    if ( v17 >= 8 )
      v9 = (LPCWSTR *)lpSubKey[0];
    v13 = v9;
    v14 = a3;
    if ( v5[3] >= 8u )
      v5 = (_QWORD *)*v5;
    *(_QWORD *)v15 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v6,
      (unsigned int)byte_180010CF3,
      v7,
      v8,
      (__int64)v15,
      (__int64)&v14,
      (__int64)&v13);
  }
  v10 = (const WCHAR *)lpSubKey;
  if ( v17 >= 8 )
    v10 = lpSubKey[0];
  v11 = RegDeleteTreeW(*this, v10);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xB7,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v11,
      (unsigned int)v12);
  if ( v17 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18000b570  mov     [rsp-18h+arg_18], rbx
0x18000b575  push    rbp
0x18000b576  push    rsi
0x18000b577  push    rdi
0x18000b578  mov     rbp, rsp
0x18000b57b  sub     rsp, 80h
0x18000b582  mov     rax, cs:__security_cookie
0x18000b589  xor     rax, rsp
0x18000b58c  mov     [rbp+var_8], rax
0x18000b590  mov     rsi, r8
0x18000b593  mov     rdi, rcx
0x18000b596  lea     rbx, [rcx+8]
0x18000b59a  cmp     qword ptr [rbx+18h], 8
0x18000b59f  jb      short loc_18000B5A6
0x18000b5a1  mov     r9, [rbx]
0x18000b5a4  jmp     short loc_18000B5A9
0x18000b5a6  mov     r9, rbx
0x18000b5a9  mov     [rsp+80h+var_48], rsi
0x18000b5ae  lea     rax, asc_180010164; "\\"
0x18000b5b5  mov     [rsp+80h+var_50], rax
0x18000b5ba  mov     [rsp+80h+var_58], rdx
0x18000b5bf  mov     qword ptr [rsp+80h+var_60], rax
0x18000b5c4  mov     r8d, 5
0x18000b5ca  lea     rdx, [rbp+lpSubKey]
0x18000b5ce  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000b5d3  nop
0x18000b5d4  mov     eax, cs:dword_180014230
0x18000b5da  cmp     eax, 4
0x18000b5dd  jbe     short loc_18000B62A
0x18000b5df  lea     rax, [rbp+lpSubKey]
0x18000b5e3  cmp     [rbp+var_10], 8
0x18000b5e8  cmovnb  rax, [rbp+lpSubKey]
0x18000b5ed  mov     [rbp+var_40], rax
0x18000b5f1  mov     [rbp+var_38], rsi
0x18000b5f5  cmp     qword ptr [rbx+18h], 8
0x18000b5fa  jb      short loc_18000B5FF
0x18000b5fc  mov     rbx, [rbx]
0x18000b5ff  mov     qword ptr [rbp+var_30], rbx
0x18000b603  lea     rax, [rbp+var_40]
0x18000b607  mov     [rsp+80h+var_50], rax
0x18000b60c  lea     rax, [rbp+var_38]
0x18000b610  mov     [rsp+80h+var_58], rax
0x18000b615  lea     rax, [rbp+var_30]
0x18000b619  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x18000b61e  lea     rdx, byte_180010CF3
0x18000b625  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b62a  lea     rdx, [rbp+lpSubKey]
0x18000b62e  cmp     [rbp+var_10], 8
0x18000b633  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18000b638  mov     rcx, [rdi]; hKey
0x18000b63b  call    cs:__imp_RegDeleteTreeW
0x18000b642  nop     dword ptr [rax+rax+00h]
0x18000b647  mov     rcx, [rbp+18h]; this
0x18000b64b  test    eax, eax
0x18000b64d  jnz     short loc_18000B686
0x18000b64f  cmp     [rbp+var_10], 8
0x18000b654  jb      short loc_18000B666
0x18000b656  mov     rcx, [rbp+lpSubKey]
0x18000b65a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b661  nop     dword ptr [rax+rax+00h]
0x18000b666  mov     rcx, [rbp+var_8]
0x18000b66a  xor     rcx, rsp; StackCookie
0x18000b66d  call    __security_check_cookie
0x18000b672  mov     rbx, [rsp+80h+arg_18]
0x18000b67a  add     rsp, 80h
0x18000b681  pop     rdi
0x18000b682  pop     rsi
0x18000b683  pop     rbp
0x18000b684  retn
0x18000b686  mov     r9d, eax; char *
0x18000b689  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b690  mov     edx, 0B7h; void *
0x18000b695  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
