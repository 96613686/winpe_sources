# NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)

- ea: `0x18001ce10`
- end: `0x18001ce5c`
- name: `?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `76`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800142d4`
- `0x180014c24`

## callees

- `0x18000cc58`
- `0x18001ce10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ce30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ce30`

## string_xrefs

- `0x18001ce3f`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

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
0x18001ce10  mov     r11, rsp
0x18001ce13  mov     [r11+18h], r8d
0x18001ce17  sub     rsp, 38h
0x18001ce1b  mov     r9d, 4; dwType
0x18001ce21  lea     rax, [r11+18h]
0x18001ce25  mov     [r11-10h], r9d
0x18001ce29  xor     r8d, r8d; Reserved
0x18001ce2c  mov     [r11-18h], rax
0x18001ce30  call    cs:__imp_RegSetValueExW
0x18001ce36  test    eax, eax
0x18001ce38  jz      short loc_18001CE55
0x18001ce3a  mov     rcx, [rsp+38h]; this
0x18001ce3f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ce46  mov     r9d, eax; char *
0x18001ce49  mov     edx, 86h; void *
0x18001ce4e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ce53  jmp     short loc_18001CE57
0x18001ce55  xor     eax, eax
0x18001ce57  add     rsp, 38h
0x18001ce5b  retn
```
