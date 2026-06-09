# UninstallTask::StoreUninstallResultInRegistry(long)

- ea: `0x18003c62c`
- end: `0x18003c6f2`
- name: `?StoreUninstallResultInRegistry@UninstallTask@@AEAAXJ@Z`
- size: `198`
- prototype: `void(UninstallTask *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180025890`

## callees

- `0x180025c5c`
- `0x18003b60c`
- `0x18003c388`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c6e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c6e1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c6c2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c6c2`
- `msvcp_win!_Xtime_get_ticks` at `0x18003c653`
- `msvcp_win!_Xtime_get_ticks` at `0x18003c653`

## string_xrefs

- `0x18003c6a9`: `LastRemediationAttemptTimestamp`
- `0x18003c665`: `UninstallResult`

## pseudocode

```c
void __fastcall UninstallTask::StoreUninstallResultInRegistry(UninstallTask *this, __int64 a2)
{
  unsigned int v2; // edi
  void *v3; // rdx
  unsigned int v4; // r8d
  __int64 ticks; // rax
  __int64 v6; // kr18_8
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = (__int64)this;
  hKey = 0;
  v2 = a2;
  if ( (int)wil::reg::create_unique_key_nothrow(this, a2, &hKey) < 0 )
  {
    wil::details::in1diag3::Log_Hr(retaddr, v3, v4, (const char *)v2, lpData);
  }
  else
  {
    ticks = _Xtime_get_ticks();
    LODWORD(Data) = v2;
    v6 = ticks;
    wil::reg::set_value_nothrow<unsigned int>(hKey, 0, L"UninstallResult", &Data);
    Data = v6 / 10000000;
    RegSetKeyValueW(hKey, 0, L"LastRemediationAttemptTimestamp", 0xBu, &Data, 8u);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18003c62c  mov     rax, rsp
0x18003c62f  mov     [rax+10h], rbx
0x18003c633  mov     [rax+8], rcx
0x18003c637  push    rdi
0x18003c638  sub     rsp, 30h
0x18003c63c  lea     r8, [rax+18h]
0x18003c640  mov     qword ptr [rax+18h], 0
0x18003c648  mov     edi, edx
0x18003c64a  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003c64f  test    eax, eax
0x18003c651  js      short loc_18003C6CA
0x18003c653  call    cs:__imp__Xtime_get_ticks
0x18003c659  lea     r9, [rsp+38h+Data]
0x18003c65e  mov     dword ptr [rsp+38h+Data], edi
0x18003c662  mov     rcx, rax
0x18003c665  lea     r8, aUninstallresul; "UninstallResult"
0x18003c66c  mov     rax, 0D6BF94D5E57A42BDh
0x18003c676  imul    rcx
0x18003c679  lea     rbx, [rcx+rdx]
0x18003c67d  mov     rcx, [rsp+38h+hKey]
0x18003c682  sar     rbx, 17h
0x18003c686  xor     edx, edx
0x18003c688  mov     rax, rbx
0x18003c68b  shr     rax, 3Fh
0x18003c68f  add     rbx, rax
0x18003c692  call    ??$set_value_nothrow@I@reg@wil@@YAJPEAUHKEY__@@PEBG1AEBI@Z; wil::reg::set_value_nothrow<uint>(HKEY__ *,ushort const *,ushort const *,uint const &)
0x18003c697  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c69c  lea     rax, [rsp+38h+Data]
0x18003c6a1  mov     [rsp+38h+cbData], 8; cbData
0x18003c6a9  lea     r8, aLastremediatio; "LastRemediationAttemptTimestamp"
0x18003c6b0  mov     r9d, 0Bh; dwType
0x18003c6b6  mov     [rsp+38h+lpData], rax; lpData
0x18003c6bb  xor     edx, edx; lpSubKey
0x18003c6bd  mov     [rsp+38h+Data], rbx
0x18003c6c2  call    cs:__imp_RegSetKeyValueW
0x18003c6c8  jmp     short loc_18003C6D7
0x18003c6ca  mov     rcx, [rsp+38h]; this
0x18003c6cf  mov     r9d, edi; char *
0x18003c6d2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003c6d7  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c6dc  test    rcx, rcx
0x18003c6df  jz      short loc_18003C6E7
0x18003c6e1  call    cs:__imp_RegCloseKey
0x18003c6e7  mov     rbx, [rsp+38h+arg_8]
0x18003c6ec  add     rsp, 30h
0x18003c6f0  pop     rdi
0x18003c6f1  retn
```
