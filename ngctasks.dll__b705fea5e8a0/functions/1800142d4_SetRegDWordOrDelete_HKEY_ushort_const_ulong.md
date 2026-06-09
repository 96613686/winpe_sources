# SetRegDWordOrDelete(HKEY__ *,ushort const *,ulong)

- ea: `0x1800142d4`
- end: `0x18001430c`
- name: `?SetRegDWordOrDelete@@YAXPEAUHKEY__@@PEBGK@Z`
- size: `56`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010b28`

## callees

- `0x18000ebc0`
- `0x1800142d4`
- `0x18001ce10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800142dd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800142dd`

## string_xrefs

- `0x1800142f3`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall SetRegDWordOrDelete(NgcUtils *a1, WCHAR *a2, const unsigned __int16 *a3, unsigned int a4)
{
  int v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (_DWORD)a3 )
  {
    v4 = NgcUtils::SetRegistryDwordValue(a1, (HKEY)a2, a3, a4);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2EB,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v4);
  }
  else
  {
    RegDeleteValueW((HKEY)a1, a2);
  }
}

```

## disassembly

```asm
0x1800142d4  sub     rsp, 28h
0x1800142d8  test    r8d, r8d
0x1800142db  jnz     short loc_1800142E5
0x1800142dd  call    cs:__imp_RegDeleteValueW
0x1800142e3  jmp     short loc_180014307
0x1800142e5  call    ?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z; NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)
0x1800142ea  test    eax, eax
0x1800142ec  jns     short loc_180014307
0x1800142ee  mov     rcx, [rsp+28h]; this
0x1800142f3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800142fa  mov     r9d, eax; char *
0x1800142fd  mov     edx, 2EBh; void *
0x180014302  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014307  add     rsp, 28h
0x18001430b  retn
```
