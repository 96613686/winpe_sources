# Microsoft::Windows::MDM::OmadmClient::Utilities::SetRevisionNumber(ushort const *,ulong)

- ea: `0x140054160`
- end: `0x140054211`
- name: `?SetRevisionNumber@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGK@Z`
- size: `177`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140054160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400541f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400541f2`
- `DMCmnUtils!BigStrcat` at `0x1400541ad`
- `DMCmnUtils!BigStrcat` at `0x1400541ad`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1400541e1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1400541e1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14005417e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14005417e`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::SetRevisionNumber(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int v10; // ebx

  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(this);
  v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v6 = L"Software\\Microsoft\\Provisioning\\OMADM";
  v7 = BigStrcat(3u, v6, L"\\Accounts\\", a2);
  v8 = (unsigned __int16 *)v7;
  if ( !v7 )
    return 2147942414LL;
  v10 = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, v7, L"revision_number", a3);
  LocalFree(v8);
  return v10;
}

```

## disassembly

```asm
0x140054160  mov     [rsp+arg_0], rbx
0x140054165  mov     [rsp+arg_8], rsi
0x14005416a  push    rdi
0x14005416b  sub     rsp, 20h
0x14005416f  mov     esi, r8d
0x140054172  mov     rbx, rdx
0x140054175  mov     [rsp+28h+arg_18], 0
0x14005417e  call    cs:__imp_RtlIsStateSeparationEnabled
0x140054185  nop     dword ptr [rax+rax+00h]
0x14005418a  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140054191  lea     rdx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Provisioni"...
0x140054198  test    al, al
0x14005419a  cmovz   rdx, rcx
0x14005419e  mov     r9, rbx
0x1400541a1  lea     r8, aAccounts; "\\Accounts\\"
0x1400541a8  mov     ecx, 3
0x1400541ad  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400541b4  nop     dword ptr [rax+rax+00h]
0x1400541b9  mov     rdi, rax
0x1400541bc  mov     [rsp+28h+arg_18], rax
0x1400541c1  test    rax, rax
0x1400541c4  jnz     short loc_1400541CD
0x1400541c6  mov     eax, 8007000Eh
0x1400541cb  jmp     short loc_140054200
0x1400541cd  mov     r9d, esi
0x1400541d0  lea     r8, ?gc_szRevisionNumberValueName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "revision_number"
0x1400541d7  mov     rdx, rdi
0x1400541da  mov     rcx, 0FFFFFFFF80000002h
0x1400541e1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400541e8  nop     dword ptr [rax+rax+00h]
0x1400541ed  mov     ebx, eax
0x1400541ef  mov     rcx, rdi; hMem
0x1400541f2  call    cs:__imp_LocalFree
0x1400541f9  nop     dword ptr [rax+rax+00h]
0x1400541fe  mov     eax, ebx
0x140054200  mov     rbx, [rsp+28h+arg_0]
0x140054205  mov     rsi, [rsp+28h+arg_8]
0x14005420a  add     rsp, 20h
0x14005420e  pop     rdi
0x14005420f  retn
```
