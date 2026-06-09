# Microsoft::Windows::MDM::OmadmClient::Utilities::GetRevisionNumber(ushort const *,ulong *)

- ea: `0x1400535a0`
- end: `0x140053651`
- name: `?GetRevisionNumber@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGPEAK@Z`
- size: `177`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400535a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053632`
- `DMCmnUtils!BigStrcat` at `0x1400535ed`
- `DMCmnUtils!BigStrcat` at `0x1400535ed`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140053621`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140053621`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400535be`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400535be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::GetRevisionNumber(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int DWORD; // ebx

  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(this);
  v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v6 = L"Software\\Microsoft\\Provisioning\\OMADM";
  v7 = BigStrcat(3u, v6, L"\\Accounts\\", a2);
  v8 = (unsigned __int16 *)v7;
  if ( !v7 )
    return 2147942414LL;
  DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, v7, L"revision_number", a3);
  LocalFree(v8);
  return DWORD;
}

```

## disassembly

```asm
0x1400535a0  mov     [rsp+arg_0], rbx
0x1400535a5  mov     [rsp+arg_8], rsi
0x1400535aa  push    rdi
0x1400535ab  sub     rsp, 20h
0x1400535af  mov     rsi, r8
0x1400535b2  mov     rbx, rdx
0x1400535b5  mov     [rsp+28h+arg_18], 0
0x1400535be  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400535c5  nop     dword ptr [rax+rax+00h]
0x1400535ca  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x1400535d1  lea     rdx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Provisioni"...
0x1400535d8  test    al, al
0x1400535da  cmovz   rdx, rcx
0x1400535de  mov     r9, rbx
0x1400535e1  lea     r8, aAccounts; "\\Accounts\\"
0x1400535e8  mov     ecx, 3
0x1400535ed  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400535f4  nop     dword ptr [rax+rax+00h]
0x1400535f9  mov     rdi, rax
0x1400535fc  mov     [rsp+28h+arg_18], rax
0x140053601  test    rax, rax
0x140053604  jnz     short loc_14005360D
0x140053606  mov     eax, 8007000Eh
0x14005360b  jmp     short loc_140053640
0x14005360d  mov     r9, rsi
0x140053610  lea     r8, ?gc_szRevisionNumberValueName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "revision_number"
0x140053617  mov     rdx, rdi
0x14005361a  mov     rcx, 0FFFFFFFF80000002h
0x140053621  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140053628  nop     dword ptr [rax+rax+00h]
0x14005362d  mov     ebx, eax
0x14005362f  mov     rcx, rdi; hMem
0x140053632  call    cs:__imp_LocalFree
0x140053639  nop     dword ptr [rax+rax+00h]
0x14005363e  mov     eax, ebx
0x140053640  mov     rbx, [rsp+28h+arg_0]
0x140053645  mov     rsi, [rsp+28h+arg_8]
0x14005364a  add     rsp, 20h
0x14005364e  pop     rdi
0x14005364f  retn
```
