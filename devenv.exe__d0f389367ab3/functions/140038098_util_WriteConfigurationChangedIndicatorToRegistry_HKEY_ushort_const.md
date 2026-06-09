# util_WriteConfigurationChangedIndicatorToRegistry(HKEY__ *,ushort const *)

- ea: `0x140038098`
- end: `0x14003817c`
- name: `?util_WriteConfigurationChangedIndicatorToRegistry@@YAXPEAUHKEY__@@PEBG@Z`
- size: `228`
- prototype: `void __fastcall(HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000ccfc`

## callees

- `0x140003160`
- `0x140038098`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140038166`
- `ADVAPI32!RegCloseKey` at `0x140038166`
- `ADVAPI32!RegOpenKeyExW` at `0x1400380fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1400380fe`
- `ADVAPI32!RegSetValueExW` at `0x140038136`
- `ADVAPI32!RegSetValueExW` at `0x140038136`

## string_xrefs

- `0x1400380d0`: `NewConfigurationWritten`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall util_WriteConfigurationChangedIndicatorToRegistry(HKEY hKey, unsigned __int16 *a2)
{
  HKEY v3; // rdi
  LPCWSTR v4; // rdx
  HKEY v5; // [rsp+30h] [rbp-20h]
  HKEY hKeya; // [rsp+68h] [rbp+18h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp+20h] BYREF

  hKeya = (HKEY)a2;
  v3 = 0;
  lpValueName = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpValueName,
    L"NewConfigurationWritten");
  hKeya = 0;
  if ( !RegOpenKeyExW(hKey, &word_14009DC20, 0, 2u, &hKeya) )
  {
    v3 = hKeya;
    v5 = hKeya;
    LODWORD(hKeya) = 1;
    RegSetValueExW(v5, lpValueName, 0, 4u, (const BYTE *)&hKeya, 4u);
  }
  v4 = lpValueName - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpValueName - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x140038098  mov     [rsp-8+arg_0], rbx
0x14003809d  mov     [rsp-8+arg_18], rdi
0x1400380a2  mov     [rsp-8+hKey], rdx
0x1400380a7  push    rbp
0x1400380a8  mov     rbp, rsp
0x1400380ab  sub     rsp, 50h
0x1400380af  mov     rbx, rcx
0x1400380b2  xorps   xmm0, xmm0
0x1400380b5  xor     eax, eax
0x1400380b7  movups  [rbp+var_20], xmm0
0x1400380bb  mov     [rbp+var_10], rax
0x1400380bf  xor     edi, edi
0x1400380c1  mov     qword ptr [rbp+var_20], rdi
0x1400380c5  and     dword ptr [rbp+var_20+8], eax
0x1400380c8  and     [rbp+var_10], rax
0x1400380cc  and     [rbp+lpValueName], rdi
0x1400380d0  lea     rdx, aNewconfigurati; "NewConfigurationWritten"
0x1400380d7  lea     rcx, [rbp+lpValueName]
0x1400380db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400380e0  and     [rbp+hKey], rdi
0x1400380e4  lea     rax, [rbp+hKey]
0x1400380e8  mov     [rsp+50h+phkResult], rax; phkResult
0x1400380ed  lea     r9d, [rdi+2]; samDesired
0x1400380f1  xor     r8d, r8d; ulOptions
0x1400380f4  lea     rdx, word_14009DC20; lpSubKey
0x1400380fb  mov     rcx, rbx; hKey
0x1400380fe  call    cs:__imp_RegOpenKeyExW
0x140038104  test    eax, eax
0x140038106  jnz     short loc_14003813C
0x140038108  mov     rdi, [rbp+hKey]
0x14003810c  mov     qword ptr [rbp+var_20], rdi
0x140038110  and     dword ptr [rbp+var_20+8], eax
0x140038113  mov     dword ptr [rbp+hKey], 1
0x14003811a  lea     r9d, [rax+4]; dwType
0x14003811e  mov     [rsp+50h+cbData], r9d; cbData
0x140038123  lea     rax, [rbp+hKey]
0x140038127  mov     [rsp+50h+phkResult], rax; lpData
0x14003812c  xor     r8d, r8d; Reserved
0x14003812f  mov     rdx, [rbp+lpValueName]; lpValueName
0x140038133  mov     rcx, rdi; hKey
0x140038136  call    cs:__imp_RegSetValueExW
0x14003813c  mov     rdx, [rbp+lpValueName]
0x140038140  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140038144  or      eax, 0FFFFFFFFh
0x140038147  lock xadd [rdx+10h], eax
0x14003814c  sub     eax, 1
0x14003814f  jg      short loc_14003815E
0x140038151  lfence
0x140038154  mov     rcx, [rdx]
0x140038157  mov     rax, [rcx]
0x14003815a  call    qword ptr [rax+8]
0x14003815d  nop
0x14003815e  test    rdi, rdi
0x140038161  jz      short loc_14003816C
0x140038163  mov     rcx, rdi; hKey
0x140038166  call    cs:__imp_RegCloseKey
0x14003816c  mov     rbx, [rsp+50h+arg_0]
0x140038171  mov     rdi, [rsp+50h+arg_18]
0x140038176  add     rsp, 50h
0x14003817a  pop     rbp
0x14003817b  retn
```
