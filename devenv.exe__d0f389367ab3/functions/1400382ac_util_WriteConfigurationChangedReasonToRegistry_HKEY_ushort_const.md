# util_WriteConfigurationChangedReasonToRegistry(HKEY__ *,ushort const *)

- ea: `0x1400382ac`
- end: `0x1400383a2`
- name: `?util_WriteConfigurationChangedReasonToRegistry@@YAXPEAUHKEY__@@PEBG@Z`
- size: `246`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000ccfc`

## callees

- `0x140002c10`
- `0x140007740`
- `0x140033ab0`
- `0x1400382ac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003838b`
- `ADVAPI32!RegCloseKey` at `0x14003838b`
- `ADVAPI32!RegOpenKeyExW` at `0x1400382ee`
- `ADVAPI32!RegOpenKeyExW` at `0x1400382ee`
- `ADVAPI32!RegSetValueExW` at `0x140038324`
- `ADVAPI32!RegSetValueExW` at `0x140038324`

## string_xrefs

- `0x14003831a`: `ConfigurationChangedReason`
- `0x140038348`: `ConfigurationChangedReason`
- `0x14003834f`: `Cannot find a place to write out the '%s', values!`
- `0x140038305`: `DevenvUpdateConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall util_WriteConfigurationChangedReasonToRegistry(HKEY a1, const unsigned __int16 *a2)
{
  HKEY v2; // rbx
  struct ATL::IAtlStringMgr *Instance; // rax
  HKEY v4; // rdx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(a1, &word_14009DC20, 0, 2u, &hKey) )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    hKey = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &hKey,
      L"Cannot find a place to write out the '%s', values!",
      L"ConfigurationChangedReason");
    v4 = hKey - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)hKey - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
    }
  }
  else
  {
    v2 = hKey;
    RegSetValueExW(hKey, L"ConfigurationChangedReason", 0, 1u, L"DevenvUpdateConfiguration", 0x34u);
  }
  if ( v2 )
    RegCloseKey(v2);
}

```

## disassembly

```asm
0x1400382ac  mov     r11, rsp
0x1400382af  mov     [r11+10h], rdx
0x1400382b3  push    rbx
0x1400382b4  sub     rsp, 50h
0x1400382b8  xorps   xmm0, xmm0
0x1400382bb  xor     eax, eax
0x1400382bd  movups  [rsp+58h+var_28], xmm0
0x1400382c2  mov     [r11-18h], rax
0x1400382c6  xor     ebx, ebx
0x1400382c8  mov     [r11-28h], rbx
0x1400382cc  and     dword ptr [rsp+58h+var_28+8], eax
0x1400382d0  and     [r11-18h], rax
0x1400382d4  and     [r11+10h], rbx
0x1400382d8  lea     rax, [r11+10h]
0x1400382dc  mov     [r11-38h], rax
0x1400382e0  lea     r9d, [rbx+2]; samDesired
0x1400382e4  xor     r8d, r8d; ulOptions
0x1400382e7  lea     rdx, word_14009DC20; lpSubKey
0x1400382ee  call    cs:__imp_RegOpenKeyExW
0x1400382f4  test    eax, eax
0x1400382f6  jnz     short loc_14003832C
0x1400382f8  mov     rbx, [rsp+58h+hKey]
0x1400382fd  mov     [rsp+58h+cbData], 34h ; '4'; cbData
0x140038305  lea     rax, Data; "DevenvUpdateConfiguration"
0x14003830c  mov     [rsp+58h+lpData], rax; lpData
0x140038311  mov     r9d, 1; dwType
0x140038317  xor     r8d, r8d; Reserved
0x14003831a  lea     rdx, aConfigurationc_1; "ConfigurationChangedReason"
0x140038321  mov     rcx, rbx; hKey
0x140038324  call    cs:__imp_RegSetValueExW
0x14003832a  jmp     short loc_140038383
0x14003832c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140038331  mov     rcx, rax
0x140038334  test    rax, rax
0x140038337  jz      short loc_140038397
0x140038339  mov     rax, [rax]
0x14003833c  call    qword ptr [rax+18h]
0x14003833f  add     rax, 18h
0x140038343  mov     [rsp+58h+hKey], rax
0x140038348  lea     r8, aConfigurationc_1; "ConfigurationChangedReason"
0x14003834f  lea     rdx, aCannotFindAPla; "Cannot find a place to write out the '%"...
0x140038356  lea     rcx, [rsp+58h+hKey]
0x14003835b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140038360  mov     rdx, [rsp+58h+hKey]
0x140038365  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140038369  or      eax, 0FFFFFFFFh
0x14003836c  lock xadd [rdx+10h], eax
0x140038371  sub     eax, 1
0x140038374  jg      short loc_140038383
0x140038376  lfence
0x140038379  mov     rcx, [rdx]
0x14003837c  mov     rax, [rcx]
0x14003837f  call    qword ptr [rax+8]
0x140038382  nop
0x140038383  test    rbx, rbx
0x140038386  jz      short loc_140038391
0x140038388  mov     rcx, rbx; hKey
0x14003838b  call    cs:__imp_RegCloseKey
0x140038391  add     rsp, 50h
0x140038395  pop     rbx
0x140038396  retn
0x140038397  mov     ecx, 80004005h; int
0x14003839c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
