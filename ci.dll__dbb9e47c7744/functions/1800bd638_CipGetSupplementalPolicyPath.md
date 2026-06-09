# CipGetSupplementalPolicyPath

- ea: `0x1800bd638`
- end: `0x1800bd68f`
- name: `CipGetSupplementalPolicyPath`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075e84`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800bd676`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800bd676`

## string_xrefs

- `0x1800bd63f`: `\EFI\Microsoft\Boot\Policies\UnlockToken.pol`

## pseudocode

```c
NTSTATUS __fastcall CipGetSupplementalPolicyPath(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  _QWORD v4[3]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v5; // [rsp+48h] [rbp-10h]

  v4[1] = a2;
  v4[2] = a3;
  v4[0] = L"\\EFI\\Microsoft\\Boot\\Policies\\UnlockToken.pol";
  v5 = 0;
  result = KeExpandKernelStackAndCalloutEx(CipGetSupplementalPolicyPathOnExpandedStackCallout, v4, 0x11800u, 0, 0);
  if ( result >= 0 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x1800bd638  mov     r11, rsp
0x1800bd63b  sub     rsp, 58h
0x1800bd63f  lea     rax, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\Policies\\Unloc"...
0x1800bd646  mov     [r11-20h], rdx
0x1800bd64a  mov     [r11-18h], r8
0x1800bd64e  lea     rdx, [r11-28h]; Parameter
0x1800bd652  mov     r8d, 11800h; Size
0x1800bd658  mov     [r11-28h], rax
0x1800bd65c  xor     r9d, r9d; Wait
0x1800bd65f  mov     qword ptr [r11-10h], 0
0x1800bd667  lea     rcx, CipGetSupplementalPolicyPathOnExpandedStackCallout; Callout
0x1800bd66e  mov     qword ptr [r11-38h], 0
0x1800bd676  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1800bd67d  nop     dword ptr [rax+rax+00h]
0x1800bd682  test    eax, eax
0x1800bd684  cmovns  eax, dword ptr [rsp+58h+var_10]
0x1800bd689  add     rsp, 58h
0x1800bd68d  retn
```
