# RegistryConfig::DeleteCommandSet(ushort const *,ushort const *)

- ea: `0x18000af48`
- end: `0x18000b066`
- name: `?DeleteCommandSet@RegistryConfig@@QEAAXPEBG0@Z`
- size: `286`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008cc0`

## callees

- `0x18000112c`
- `0x18000899c`
- `0x18000ac58`
- `0x18000af48`
- `0x18000c600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b02c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b02c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b013`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b013`

## string_xrefs

- `0x18000b054`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
void __fastcall RegistryConfig::DeleteCommandSet(
        RegistryConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char *v5; // rbx
  char *v6; // r9
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  LPCWSTR *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // [rsp+20h] [rbp-60h]
  LPCWSTR *v14; // [rsp+40h] [rbp-40h] BYREF
  const unsigned __int16 *v15; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v16[2]; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) < 8u )
    v6 = (char *)this + 8;
  else
    v6 = *(char **)v5;
  RegistryConfig::AppendStrings((__int64)this, lpSubKey, 5, v6, L"\\", a2, L"\\", a3);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v10 = lpSubKey;
    if ( v18 >= 8 )
      v10 = (LPCWSTR *)lpSubKey[0];
    v14 = v10;
    v15 = a3;
    if ( *((_QWORD *)v5 + 3) >= 8u )
      v5 = *(char **)v5;
    *(_QWORD *)v16 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)byte_180010CF3,
      v8,
      v9,
      (__int64)v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  v11 = (const WCHAR *)lpSubKey;
  if ( v18 >= 8 )
    v11 = lpSubKey[0];
  v12 = RegDeleteTreeW(*(HKEY *)this, v11);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xB7,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v12,
      v13);
  if ( v18 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x18000af48  mov     [rsp-18h+arg_18], rbx
0x18000af4d  push    rbp
0x18000af4e  push    rsi
0x18000af4f  push    rdi
0x18000af50  mov     rbp, rsp
0x18000af53  sub     rsp, 80h
0x18000af5a  mov     rax, cs:__security_cookie
0x18000af61  xor     rax, rsp
0x18000af64  mov     [rbp+var_8], rax
0x18000af68  mov     rsi, r8
0x18000af6b  mov     rdi, rcx
0x18000af6e  lea     rbx, [rcx+8]
0x18000af72  cmp     qword ptr [rbx+18h], 8
0x18000af77  jb      short loc_18000AF7E
0x18000af79  mov     r9, [rbx]
0x18000af7c  jmp     short loc_18000AF81
0x18000af7e  mov     r9, rbx
0x18000af81  mov     [rsp+80h+var_48], rsi
0x18000af86  lea     rax, asc_180010164; "\\"
0x18000af8d  mov     [rsp+80h+var_50], rax
0x18000af92  mov     [rsp+80h+var_58], rdx
0x18000af97  mov     qword ptr [rsp+80h+var_60], rax
0x18000af9c  mov     r8d, 5
0x18000afa2  lea     rdx, [rbp+lpSubKey]
0x18000afa6  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000afab  nop
0x18000afac  mov     eax, cs:dword_180014230
0x18000afb2  cmp     eax, 4
0x18000afb5  jbe     short loc_18000B002
0x18000afb7  lea     rax, [rbp+lpSubKey]
0x18000afbb  cmp     [rbp+var_10], 8
0x18000afc0  cmovnb  rax, [rbp+lpSubKey]
0x18000afc5  mov     [rbp+var_40], rax
0x18000afc9  mov     [rbp+var_38], rsi
0x18000afcd  cmp     qword ptr [rbx+18h], 8
0x18000afd2  jb      short loc_18000AFD7
0x18000afd4  mov     rbx, [rbx]
0x18000afd7  mov     qword ptr [rbp+var_30], rbx
0x18000afdb  lea     rax, [rbp+var_40]
0x18000afdf  mov     [rsp+80h+var_50], rax
0x18000afe4  lea     rax, [rbp+var_38]
0x18000afe8  mov     [rsp+80h+var_58], rax
0x18000afed  lea     rax, [rbp+var_30]
0x18000aff1  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x18000aff6  lea     rdx, byte_180010CF3
0x18000affd  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b002  lea     rdx, [rbp+lpSubKey]
0x18000b006  cmp     [rbp+var_10], 8
0x18000b00b  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18000b010  mov     rcx, [rdi]; hKey
0x18000b013  call    cs:__imp_RegDeleteTreeW
0x18000b019  mov     rcx, [rbp+18h]; this
0x18000b01d  test    eax, eax
0x18000b01f  jnz     short loc_18000B051
0x18000b021  cmp     [rbp+var_10], 8
0x18000b026  jb      short loc_18000B032
0x18000b028  mov     rcx, [rbp+lpSubKey]
0x18000b02c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b032  mov     rcx, [rbp+var_8]
0x18000b036  xor     rcx, rsp; StackCookie
0x18000b039  call    __security_check_cookie
0x18000b03e  mov     rbx, [rsp+80h+arg_18]
0x18000b046  add     rsp, 80h
0x18000b04d  pop     rdi
0x18000b04e  pop     rsi
0x18000b04f  pop     rbp
0x18000b050  retn
0x18000b051  mov     r9d, eax; char *
0x18000b054  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b05b  mov     edx, 0B7h; void *
0x18000b060  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
