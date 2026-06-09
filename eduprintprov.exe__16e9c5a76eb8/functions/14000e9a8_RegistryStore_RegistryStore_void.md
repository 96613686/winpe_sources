# RegistryStore::~RegistryStore(void)

- ea: `0x14000e9a8`
- end: `0x14000ea52`
- name: `??1RegistryStore@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(RegistryStore *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d2a4`
- `0x1400133d9`
- `0x1400133eb`

## callees

- `0x1400034f8`
- `0x14000c540`
- `0x14000e9a8`
- `0x14000f0cc`
- `0x14000f0f0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000ea20`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000ea20`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000ea30`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000ea30`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000ea0f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e9ea`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e9ea`

## string_xrefs

- `0x14000ea08`: `Error writing retry count to registry: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryStore::~RegistryStore(RegistryStore *this)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_BYTE *)this + 32) )
  {
    RegistryStore::_SaveInstalledPrinters(this);
    v2 = RegSetKeyValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Print\\EDU",
           L"RetryCount",
           4u,
           (char *)this + 36,
           4u);
    v4 = v2;
    if ( v2 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x106, v3, (const char *)v2, lpData);
      v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             std::wcout,
             L"Error writing retry count to registry: ");
      v6 = std::basic_ostream<unsigned short>::operator<<(v5, v4);
      std::basic_ostream<unsigned short>::operator<<(v6, std::endl<unsigned short,std::char_traits<unsigned short>>);
    }
  }
  std::list<std::wstring>::~list<std::wstring>((char *)this + 16);
  std::list<std::wstring>::~list<std::wstring>(this);
}

```

## disassembly

```asm
0x14000e9a8  mov     [rsp+arg_0], rbx
0x14000e9ad  push    rdi
0x14000e9ae  sub     rsp, 30h
0x14000e9b2  mov     rbx, rcx
0x14000e9b5  cmp     byte ptr [rcx+20h], 0
0x14000e9b9  jz      short loc_14000EA37
0x14000e9bb  call    ?_SaveInstalledPrinters@RegistryStore@@AEBAXXZ; RegistryStore::_SaveInstalledPrinters(void)
0x14000e9c0  nop
0x14000e9c1  lea     rax, [rbx+24h]
0x14000e9c5  mov     r9d, 4; dwType
0x14000e9cb  mov     [rsp+38h+cbData], r9d; cbData
0x14000e9d0  mov     [rsp+38h+lpData], rax; unsigned int
0x14000e9d5  lea     r8, aRetrycount; "RetryCount"
0x14000e9dc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000e9e3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000e9ea  call    cs:__imp_RegSetKeyValueW
0x14000e9f0  mov     edi, eax
0x14000e9f2  mov     rcx, [rsp+38h]; this
0x14000e9f7  test    eax, eax
0x14000e9f9  jz      short loc_14000EA37
0x14000e9fb  mov     r9d, eax; char *
0x14000e9fe  mov     edx, 106h; void *
0x14000ea03  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14000ea08  lea     rdx, aErrorWritingRe; "Error writing retry count to registry: "
0x14000ea0f  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000ea16  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000ea1b  mov     edx, edi
0x14000ea1d  mov     rcx, rax
0x14000ea20  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14000ea26  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000ea2d  mov     rcx, rax
0x14000ea30  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000ea36  nop
0x14000ea37  lea     rcx, [rbx+10h]
0x14000ea3b  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x14000ea40  mov     rcx, rbx
0x14000ea43  mov     rbx, [rsp+38h+arg_0]
0x14000ea48  add     rsp, 30h
0x14000ea4c  pop     rdi
0x14000ea4d  jmp     ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
```
