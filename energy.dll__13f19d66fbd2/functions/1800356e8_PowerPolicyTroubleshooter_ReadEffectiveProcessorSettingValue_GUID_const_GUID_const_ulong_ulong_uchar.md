# PowerPolicyTroubleshooter::ReadEffectiveProcessorSettingValue(_GUID const *,_GUID const *,ulong *,ulong *,uchar *)

- ea: `0x1800356e8`
- end: `0x180035762`
- name: `?ReadEffectiveProcessorSettingValue@PowerPolicyTroubleshooter@@AEAAXPEBU_GUID@@0PEAK1PEAE@Z`
- size: `122`
- prototype: `void(PowerPolicyTroubleshooter *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038238`

## callees

- `0x1800356e8`

## import_xrefs

- `POWRPROF!PowerReadDCValueIndex` at `0x180035744`
- `POWRPROF!PowerReadDCValueIndex` at `0x180035744`
- `POWRPROF!PowerReadACValueIndex` at `0x18003570b`
- `POWRPROF!PowerReadACValueIndex` at `0x18003570b`

## pseudocode

```c
void __fastcall PowerPolicyTroubleshooter::ReadEffectiveProcessorSettingValue(
        PowerPolicyTroubleshooter *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        unsigned int *AcValueIndex,
        unsigned int *DcValueIndex,
        unsigned __int8 *a6)
{
  if ( PowerReadACValueIndex(0, a2, &GUID_PROCESSOR_SETTINGS_SUBGROUP, a3, AcValueIndex) )
    *AcValueIndex = -1;
  else
    *a6 = 1;
  if ( PowerReadDCValueIndex(0, a2, &GUID_PROCESSOR_SETTINGS_SUBGROUP, a3, DcValueIndex) )
    *DcValueIndex = -1;
  else
    *a6 = 1;
}

```

## disassembly

```asm
0x1800356e8  push    rbx
0x1800356ea  push    rbp
0x1800356eb  push    rsi
0x1800356ec  push    rdi
0x1800356ed  sub     rsp, 38h
0x1800356f1  mov     rdi, r9
0x1800356f4  mov     [rsp+58h+AcValueIndex], r9; AcValueIndex
0x1800356f9  mov     r9, r8; PowerSettingGuid
0x1800356fc  mov     rsi, r8
0x1800356ff  lea     r8, GUID_PROCESSOR_SETTINGS_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180035706  xor     ecx, ecx; RootPowerKey
0x180035708  mov     rbp, rdx
0x18003570b  call    cs:__imp_PowerReadACValueIndex
0x180035711  mov     rbx, [rsp+58h+arg_28]
0x180035719  test    eax, eax
0x18003571b  jnz     short loc_180035722
0x18003571d  mov     byte ptr [rbx], 1
0x180035720  jmp     short loc_180035728
0x180035722  mov     dword ptr [rdi], 0FFFFFFFFh
0x180035728  mov     rdi, [rsp+58h+DcValueIndex]
0x180035730  lea     r8, GUID_PROCESSOR_SETTINGS_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180035737  mov     r9, rsi; PowerSettingGuid
0x18003573a  mov     [rsp+58h+AcValueIndex], rdi; DcValueIndex
0x18003573f  mov     rdx, rbp; SchemeGuid
0x180035742  xor     ecx, ecx; RootPowerKey
0x180035744  call    cs:__imp_PowerReadDCValueIndex
0x18003574a  test    eax, eax
0x18003574c  jnz     short loc_180035753
0x18003574e  mov     byte ptr [rbx], 1
0x180035751  jmp     short loc_180035759
0x180035753  mov     dword ptr [rdi], 0FFFFFFFFh
0x180035759  add     rsp, 38h
0x18003575d  pop     rdi
0x18003575e  pop     rsi
0x18003575f  pop     rbp
0x180035760  pop     rbx
0x180035761  retn
```
