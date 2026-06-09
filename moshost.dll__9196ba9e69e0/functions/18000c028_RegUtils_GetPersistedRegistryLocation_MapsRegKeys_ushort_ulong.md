# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x18000c028`
- end: `0x18000c081`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `89`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a6a4`
- `0x18000bef4`
- `0x18000bf98`

## callees

- `0x18000c028`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c073`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c04c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c04c`

## string_xrefs

- `0x18000c066`: `RegUtils::GetPersistedRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetPersistedRegistryLocation(__int64 a1, __int64 a2)
{
  signed int PersistedRegistryLocationW; // eax

  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"MapsBase", L"System\\Maps", a2, 520, 0);
  if ( !PersistedRegistryLocationW )
    return 0;
  if ( PersistedRegistryLocationW > 0 )
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  return ZTraceReportOriginationNoThis(PersistedRegistryLocationW, "RegUtils::GetPersistedRegistryLocation", 1043);
}

```

## disassembly

```asm
0x18000c028  sub     rsp, 38h
0x18000c02c  mov     r8, rdx
0x18000c02f  mov     [rsp+38h+var_18], 0
0x18000c038  lea     rdx, aSystemMaps; "System\\Maps"
0x18000c03f  mov     r9d, 208h
0x18000c045  lea     rcx, aMapsbase; "MapsBase"
0x18000c04c  call    cs:__imp_GetPersistedRegistryLocationW
0x18000c052  test    eax, eax
0x18000c054  jz      short loc_18000C07A
0x18000c056  jle     short loc_18000C060
0x18000c058  movzx   eax, ax
0x18000c05b  or      eax, 80070000h
0x18000c060  mov     r8d, 413h
0x18000c066  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x18000c06d  mov     ecx, eax
0x18000c06f  add     rsp, 38h
0x18000c073  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c07a  xor     eax, eax
0x18000c07c  add     rsp, 38h
0x18000c080  retn
```
