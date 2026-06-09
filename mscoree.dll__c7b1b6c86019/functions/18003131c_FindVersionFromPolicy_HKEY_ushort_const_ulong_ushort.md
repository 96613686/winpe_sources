# FindVersionFromPolicy(HKEY__ *,ushort const *,ulong,ushort * *)

- ea: `0x18003131c`
- end: `0x1800313b5`
- name: `?FindVersionFromPolicy@@YAJPEAUHKEY__@@PEBGKPEAPEAG@Z`
- size: `153`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800313bc`

## callees

- `0x1800309d8`
- `0x180030c74`
- `0x180030db8`
- `0x18003131c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003135c`
- `ADVAPI32!RegOpenKeyExW` at `0x18003135c`
- `ADVAPI32!RegCloseKey` at `0x180031392`
- `ADVAPI32!RegCloseKey` at `0x180031392`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindVersionFromPolicy(HKEY a1, const unsigned __int16 *a2, REGSAM a3, unsigned __int16 **a4)
{
  int v6; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v9[2]; // [rsp+38h] [rbp-10h] BYREF

  v6 = -2147467259;
  hKey = 0;
  v9[0] = 0;
  if ( !RegOpenKeyExW(a1, L"Software\\Microsoft\\.NETFramework\\Policy\\Upgrades", 0, a3, &hKey) )
  {
    v6 = VersionPolicy::BuildPolicy((VersionPolicy *)v9, hKey);
    if ( v6 >= 0 )
      v6 = VersionPolicy::ApplyPolicy((VersionPolicy *)v9, a2, a4);
    RegCloseKey(hKey);
  }
  VersionPolicy::~VersionPolicy((VersionPolicy *)v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003131c  mov     r11, rsp
0x18003131f  mov     [r11+8], rbx
0x180031323  mov     [r11+10h], rsi
0x180031327  push    rdi
0x180031328  sub     rsp, 40h
0x18003132c  mov     rdi, r9
0x18003132f  mov     rsi, rdx
0x180031332  mov     ebx, 80004005h
0x180031337  mov     qword ptr [r11-18h], 0
0x18003133f  mov     qword ptr [r11-10h], 0
0x180031347  lea     rax, [r11-18h]
0x18003134b  mov     [r11-28h], rax
0x18003134f  mov     r9d, r8d; samDesired
0x180031352  xor     r8d, r8d; ulOptions
0x180031355  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\.NETFramework\\Pol"...
0x18003135c  call    cs:__imp_RegOpenKeyExW
0x180031362  test    eax, eax
0x180031364  jnz     short loc_180031399
0x180031366  mov     rdx, [rsp+48h+hKey]; hKey
0x18003136b  lea     rcx, [rsp+48h+var_10]; this
0x180031370  call    ?BuildPolicy@VersionPolicy@@QEAAJPEAUHKEY__@@@Z; VersionPolicy::BuildPolicy(HKEY__ *)
0x180031375  mov     ebx, eax
0x180031377  test    eax, eax
0x180031379  js      short loc_18003138D
0x18003137b  mov     r8, rdi; unsigned __int16 **
0x18003137e  mov     rdx, rsi; unsigned __int16 *
0x180031381  lea     rcx, [rsp+48h+var_10]; this
0x180031386  call    ?ApplyPolicy@VersionPolicy@@QEAAJPEBGPEAPEAG@Z; VersionPolicy::ApplyPolicy(ushort const *,ushort * *)
0x18003138b  mov     ebx, eax
0x18003138d  mov     rcx, [rsp+48h+hKey]; hKey
0x180031392  call    cs:__imp_RegCloseKey
0x180031398  nop
0x180031399  lea     rcx, [rsp+48h+var_10]; this
0x18003139e  call    ??1VersionPolicy@@QEAA@XZ; VersionPolicy::~VersionPolicy(void)
0x1800313a3  mov     eax, ebx
0x1800313a5  mov     rbx, [rsp+48h+arg_0]
0x1800313aa  mov     rsi, [rsp+48h+arg_8]
0x1800313af  add     rsp, 40h
0x1800313b3  pop     rdi
0x1800313b4  retn
```
