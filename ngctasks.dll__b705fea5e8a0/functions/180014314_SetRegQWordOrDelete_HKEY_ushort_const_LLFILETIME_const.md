# SetRegQWordOrDelete(HKEY__ *,ushort const *,_LLFILETIME const *)

- ea: `0x180014314`
- end: `0x180014370`
- name: `?SetRegQWordOrDelete@@YAXPEAUHKEY__@@PEBGPEBU_LLFILETIME@@@Z`
- size: `92`
- prototype: `void(HKEY, const unsigned __int16 *, const struct _LLFILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010b28`

## callees

- `0x18000ebc0`
- `0x180014314`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001431e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001431e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001433c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001433c`

## string_xrefs

- `0x180014357`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall SetRegQWordOrDelete(HKEY a1, const unsigned __int16 *a2, const BYTE *lpData)
{
  int v3; // eax
  bool v4; // sf
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_QWORD *)lpData )
  {
    v3 = RegSetValueExW(a1, a2, 0, 0xBu, lpData, 8u);
    v4 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = v3 < 0;
    }
    if ( v4 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x309,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v3);
  }
  else
  {
    RegDeleteValueW(a1, a2);
  }
}

```

## disassembly

```asm
0x180014314  sub     rsp, 38h
0x180014318  cmp     qword ptr [r8], 0
0x18001431c  jnz     short loc_180014326
0x18001431e  call    cs:__imp_RegDeleteValueW
0x180014324  jmp     short loc_18001436B
0x180014326  mov     [rsp+38h+cbData], 8; cbData
0x18001432e  mov     r9d, 0Bh; dwType
0x180014334  mov     [rsp+38h+lpData], r8; int
0x180014339  xor     r8d, r8d; Reserved
0x18001433c  call    cs:__imp_RegSetValueExW
0x180014342  test    eax, eax
0x180014344  jle     short loc_180014350
0x180014346  movzx   eax, ax
0x180014349  or      eax, 80070000h
0x18001434e  test    eax, eax
0x180014350  jns     short loc_18001436B
0x180014352  mov     rcx, [rsp+38h]; this
0x180014357  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001435e  mov     r9d, eax; char *
0x180014361  mov     edx, 309h; void *
0x180014366  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001436b  add     rsp, 38h
0x18001436f  retn
```
