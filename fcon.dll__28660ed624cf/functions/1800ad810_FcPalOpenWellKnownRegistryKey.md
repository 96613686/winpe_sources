# FcPalOpenWellKnownRegistryKey

- ea: `0x1800ad810`
- end: `0x1800ad913`
- name: `FcPalOpenWellKnownRegistryKey`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ab0bc`
- `0x1800aba30`

## callees

- `0x180003220`
- `0x1800ad810`

## import_xrefs

- `ntdll!ZwOpenKeyEx` at `0x1800ad8f1`
- `ntdll!ZwOpenKeyEx` at `0x1800ad8f1`

## string_xrefs

- `0x1800ad843`: `\Registry\Machine\INITIALMACHINECONFIG\SYSTEM\ControlSet001\Control`
- `0x1800ad838`: `\Registry\Machine\OSBOOT\ControlSetOverride`
- `0x1800ad86f`: `\Registry\Machine\SYSTEM\Software\Microsoft\BuildLayers`
- `0x1800ad864`: `\Registry\Machine\SYSTEM\CurrentControlSet\Policies\Microsoft`
- `0x1800ad859`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`
- `0x1800ad84e`: `\Registry\Machine\INITIALMACHINECONFIG\SYSTEM\ControlSet001\Policies\Microsoft`
- `0x1800ad87a`: `\Registry\Machine\SYSTEM\Software\Microsoft\ServicingLayers`

## pseudocode

```c
__int64 __fastcall FcPalOpenWellKnownRegistryKey(__int64 a1, __int64 a2, int a3)
{
  _DWORD v4[2]; // [rsp+20h] [rbp-59h] BYREF
  __int64 v5; // [rsp+28h] [rbp-51h]
  _DWORD *v6; // [rsp+30h] [rbp-49h]
  int v7; // [rsp+38h] [rbp-41h]
  int v8; // [rsp+3Ch] [rbp-3Dh]
  __int128 v9; // [rsp+40h] [rbp-39h]
  _DWORD v10[2]; // [rsp+50h] [rbp-29h] BYREF
  const wchar_t *v11; // [rsp+58h] [rbp-21h]
  int v12; // [rsp+60h] [rbp-19h]
  const wchar_t *v13; // [rsp+68h] [rbp-11h]
  int v14; // [rsp+70h] [rbp-9h]
  const wchar_t *v15; // [rsp+78h] [rbp-1h]
  int v16; // [rsp+80h] [rbp+7h]
  const wchar_t *v17; // [rsp+88h] [rbp+Fh]
  int v18; // [rsp+90h] [rbp+17h]
  const wchar_t *v19; // [rsp+98h] [rbp+1Fh]
  int v20; // [rsp+A0h] [rbp+27h]
  const wchar_t *v21; // [rsp+A8h] [rbp+2Fh]
  int v22; // [rsp+B0h] [rbp+37h]
  const wchar_t *v23; // [rsp+B8h] [rbp+3Fh]

  v10[0] = 5767254;
  v4[1] = 0;
  v11 = L"\\Registry\\Machine\\OSBOOT\\ControlSetOverride";
  v13 = L"\\Registry\\Machine\\INITIALMACHINECONFIG\\SYSTEM\\ControlSet001\\Control";
  v15 = L"\\Registry\\Machine\\INITIALMACHINECONFIG\\SYSTEM\\ControlSet001\\Policies\\Microsoft";
  v17 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control";
  v19 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Policies\\Microsoft";
  v21 = L"\\Registry\\Machine\\SYSTEM\\Software\\Microsoft\\BuildLayers";
  v23 = L"\\Registry\\Machine\\SYSTEM\\Software\\Microsoft\\ServicingLayers";
  v8 = 0;
  v12 = 8913030;
  v14 = 10354844;
  v16 = 6684772;
  v18 = 8126586;
  v20 = 7340142;
  v22 = 7864438;
  if ( a3 >= 7 )
    return 3221225485LL;
  v5 = 0;
  v6 = &v10[4 * a3];
  v4[0] = 48;
  v7 = 64;
  v9 = 0;
  return ((__int64 (__fastcall *)(__int64, __int64, _DWORD *, __int64))ZwOpenKeyEx)(a1, 131097, v4, 16);
}

```

## disassembly

```asm
0x1800ad810  push    rbp
0x1800ad812  lea     rbp, [rsp-57h]
0x1800ad817  sub     rsp, 0D0h
0x1800ad81e  mov     rax, cs:__security_cookie
0x1800ad825  xor     rax, rsp
0x1800ad828  mov     [rbp+57h+var_10], rax
0x1800ad82c  xor     edx, edx
0x1800ad82e  mov     [rbp+57h+var_80], 580056h
0x1800ad835  mov     [rbp+57h+var_AC], edx
0x1800ad838  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\OSBOOT\\ControlSet"...
0x1800ad83f  mov     [rbp+57h+var_78], rax
0x1800ad843  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\INITIALMACHINECONF"...
0x1800ad84a  mov     [rbp+57h+var_68], rax
0x1800ad84e  lea     rax, aRegistryMachin; "\\Registry\\Machine\\INITIALMACHINECONF"...
0x1800ad855  mov     [rbp+57h+var_58], rax
0x1800ad859  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1800ad860  mov     [rbp+57h+var_48], rax
0x1800ad864  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1800ad86b  mov     [rbp+57h+var_38], rax
0x1800ad86f  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\Software\\"...
0x1800ad876  mov     [rbp+57h+var_28], rax
0x1800ad87a  lea     rax, aRegistryMachin_5; "\\Registry\\Machine\\SYSTEM\\Software\\"...
0x1800ad881  mov     [rbp+57h+var_18], rax
0x1800ad885  mov     [rbp+57h+var_94], edx
0x1800ad888  mov     [rbp+57h+var_70], 880086h
0x1800ad88f  mov     [rbp+57h+var_60], 9E009Ch
0x1800ad896  mov     [rbp+57h+var_50], 660064h
0x1800ad89d  mov     [rbp+57h+var_40], 7C007Ah
0x1800ad8a4  mov     [rbp+57h+var_30], 70006Eh
0x1800ad8ab  mov     [rbp+57h+var_20], 780076h
0x1800ad8b2  cmp     r8d, 7
0x1800ad8b6  jge     short loc_1800AD8F9
0x1800ad8b8  movsxd  rax, r8d
0x1800ad8bb  lea     r9d, [rdx+10h]
0x1800ad8bf  shl     rax, 4
0x1800ad8c3  lea     r8, [rbp+57h+var_80]
0x1800ad8c7  add     rax, r8
0x1800ad8ca  mov     [rbp+57h+var_A8], rdx
0x1800ad8ce  xorps   xmm0, xmm0
0x1800ad8d1  mov     [rbp+57h+var_A0], rax
0x1800ad8d5  lea     r8, [rbp+57h+var_B0]
0x1800ad8d9  mov     [rbp+57h+var_B0], 30h ; '0'
0x1800ad8e0  mov     edx, 20019h
0x1800ad8e5  mov     [rbp+57h+var_98], 40h ; '@'
0x1800ad8ec  movdqu  [rbp+57h+var_90], xmm0
0x1800ad8f1  call    cs:__imp_ZwOpenKeyEx
0x1800ad8f7  jmp     short loc_1800AD8FE
0x1800ad8f9  mov     eax, 0C000000Dh
0x1800ad8fe  mov     rcx, [rbp+57h+var_10]
0x1800ad902  xor     rcx, rsp; StackCookie
0x1800ad905  call    __security_check_cookie
0x1800ad90a  add     rsp, 0D0h
0x1800ad911  pop     rbp
0x1800ad912  retn
```
