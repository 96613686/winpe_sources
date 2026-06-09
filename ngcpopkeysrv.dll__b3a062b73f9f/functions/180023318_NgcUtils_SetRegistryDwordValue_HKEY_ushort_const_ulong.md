# NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)

- ea: `0x180023318`
- end: `0x180023364`
- name: `?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `76`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019904`
- `0x18001c760`

## callees

- `0x1800136b0`
- `0x180023318`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023338`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023338`

## string_xrefs

- `0x180023347`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::SetRegistryDwordValue(NgcUtils *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // eax
  unsigned int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = (int)a3;
  v3 = RegSetValueExW((HKEY)this, a2, 0, 4u, (const BYTE *)&v7, 4u);
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x86,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
             (const char *)v3,
             v5);
  else
    return 0;
}

```

## disassembly

```asm
0x180023318  mov     r11, rsp
0x18002331b  mov     [r11+18h], r8d
0x18002331f  sub     rsp, 38h
0x180023323  mov     r9d, 4; dwType
0x180023329  lea     rax, [r11+18h]
0x18002332d  mov     [r11-10h], r9d
0x180023331  xor     r8d, r8d; Reserved
0x180023334  mov     [r11-18h], rax
0x180023338  call    cs:__imp_RegSetValueExW
0x18002333e  test    eax, eax
0x180023340  jz      short loc_18002335D
0x180023342  mov     rcx, [rsp+38h]; this
0x180023347  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002334e  mov     r9d, eax; char *
0x180023351  mov     edx, 86h; void *
0x180023356  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002335b  jmp     short loc_18002335F
0x18002335d  xor     eax, eax
0x18002335f  add     rsp, 38h
0x180023363  retn
```
