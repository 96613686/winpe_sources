# util_MarkKechainForClear(void)

- ea: `0x140039744`
- end: `0x140039855`
- name: `?util_MarkKechainForClear@@YAJXZ`
- size: `273`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140003160`
- `0x140039744`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140039845`
- `ADVAPI32!RegCloseKey` at `0x140039845`
- `ADVAPI32!RegOpenKeyExW` at `0x1400397b0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400397b0`
- `ADVAPI32!RegSetValueExW` at `0x1400397f2`
- `ADVAPI32!RegSetValueExW` at `0x1400397f2`

## string_xrefs

- `0x14003976d`: `Software\Microsoft\VsCommon\ConnectedUser`
- `0x140039781`: `ResetUserTokenStorage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 util_MarkKechainForClear(void)
{
  HKEY v0; // rbx
  LSTATUS v1; // eax
  unsigned int v2; // edi
  LPCWSTR v3; // rdx
  LPCWSTR v4; // rdx
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  LPCWSTR lpValueName; // [rsp+78h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp+30h] BYREF

  v0 = 0;
  lpSubKey = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpSubKey,
    L"Software\\Microsoft\\VsCommon\\ConnectedUser");
  lpValueName = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpValueName,
    L"ResetUserTokenStorage");
  phkResult = 0;
  v1 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 2u, &phkResult);
  if ( !v1 )
    v0 = phkResult;
  v2 = v1 != 0 ? v1 : 0;
  if ( !v2 )
  {
    LODWORD(phkResult) = 1;
    RegSetValueExW(v0, lpValueName, 0, 4u, (const BYTE *)&phkResult, 4u);
  }
  v3 = lpValueName - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpValueName - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  }
  v4 = lpSubKey - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  if ( v0 )
    RegCloseKey(v0);
  return v2;
}

```

## disassembly

```asm
0x140039744  push    rbp
0x140039746  push    rbx
0x140039747  push    rdi
0x140039748  mov     rbp, rsp
0x14003974b  sub     rsp, 50h
0x14003974f  xorps   xmm0, xmm0
0x140039752  xor     eax, eax
0x140039754  movups  [rbp+var_20], xmm0
0x140039758  mov     [rbp+var_10], rax
0x14003975c  xor     ebx, ebx
0x14003975e  mov     qword ptr [rbp+var_20], rbx
0x140039762  and     dword ptr [rbp+var_20+8], eax
0x140039765  and     [rbp+var_10], rax
0x140039769  and     [rbp+lpSubKey], rbx
0x14003976d  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\VsCommon\\Connecte"...
0x140039774  lea     rcx, [rbp+lpSubKey]
0x140039778  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14003977d  and     [rbp+lpValueName], rbx
0x140039781  lea     rdx, aResetusertoken; "ResetUserTokenStorage"
0x140039788  lea     rcx, [rbp+lpValueName]
0x14003978c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140039791  and     [rbp+arg_0], rbx
0x140039795  lea     rax, [rbp+arg_0]
0x140039799  mov     [rsp+50h+phkResult], rax; phkResult
0x14003979e  lea     r9d, [rbx+2]; samDesired
0x1400397a2  xor     r8d, r8d; ulOptions
0x1400397a5  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1400397a9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400397b0  call    cs:__imp_RegOpenKeyExW
0x1400397b6  test    eax, eax
0x1400397b8  jnz     short loc_1400397C5
0x1400397ba  mov     rbx, [rbp+arg_0]
0x1400397be  mov     qword ptr [rbp+var_20], rbx
0x1400397c2  and     dword ptr [rbp+var_20+8], eax
0x1400397c5  mov     ecx, eax
0x1400397c7  neg     ecx
0x1400397c9  sbb     edi, edi
0x1400397cb  and     edi, eax
0x1400397cd  jnz     short loc_1400397F8
0x1400397cf  mov     dword ptr [rbp+arg_0], 1
0x1400397d6  lea     r9d, [rdi+4]; dwType
0x1400397da  mov     [rsp+50h+cbData], r9d; cbData
0x1400397df  lea     rax, [rbp+arg_0]
0x1400397e3  mov     [rsp+50h+phkResult], rax; lpData
0x1400397e8  xor     r8d, r8d; Reserved
0x1400397eb  mov     rdx, [rbp+lpValueName]; lpValueName
0x1400397ef  mov     rcx, rbx; hKey
0x1400397f2  call    cs:__imp_RegSetValueExW
0x1400397f8  mov     rdx, [rbp+lpValueName]
0x1400397fc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140039800  or      eax, 0FFFFFFFFh
0x140039803  lock xadd [rdx+10h], eax
0x140039808  sub     eax, 1
0x14003980b  jg      short loc_14003981A
0x14003980d  lfence
0x140039810  mov     rcx, [rdx]
0x140039813  mov     rax, [rcx]
0x140039816  call    qword ptr [rax+8]
0x140039819  nop
0x14003981a  mov     rdx, [rbp+lpSubKey]
0x14003981e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140039822  or      eax, 0FFFFFFFFh
0x140039825  lock xadd [rdx+10h], eax
0x14003982a  sub     eax, 1
0x14003982d  jg      short loc_14003983D
0x14003982f  lfence
0x140039832  mov     rcx, [rdx]
0x140039835  mov     r8, [rcx]
0x140039838  call    qword ptr [r8+8]
0x14003983c  nop
0x14003983d  test    rbx, rbx
0x140039840  jz      short loc_14003984B
0x140039842  mov     rcx, rbx; hKey
0x140039845  call    cs:__imp_RegCloseKey
0x14003984b  mov     eax, edi
0x14003984d  add     rsp, 50h
0x140039851  pop     rdi
0x140039852  pop     rbx
0x140039853  pop     rbp
0x140039854  retn
```
