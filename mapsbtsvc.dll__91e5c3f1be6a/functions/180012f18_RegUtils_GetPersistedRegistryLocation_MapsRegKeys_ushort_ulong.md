# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x180012f18`
- end: `0x180012f71`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `89`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180012f78`

## callees

- `0x180012f18`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180012f63`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180012f3c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180012f3c`

## string_xrefs

- `0x180012f56`: `RegUtils::GetPersistedRegistryLocation`
- `0x180012f28`: `System\Maps\BackgroundTransferService`

## pseudocode

```c
int __fastcall RegUtils::GetPersistedRegistryLocation(__int64 a1, __int64 a2)
{
  signed int PersistedRegistryLocationW; // eax

  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"MapsBackgroundTransfer",
                                 L"System\\Maps\\BackgroundTransferService",
                                 a2,
                                 520,
                                 0);
  if ( !PersistedRegistryLocationW )
    return 0;
  if ( PersistedRegistryLocationW > 0 )
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  return ZTraceReportOriginationNoThis(PersistedRegistryLocationW, "RegUtils::GetPersistedRegistryLocation", 1043);
}

```

## disassembly

```asm
0x180012f18  sub     rsp, 38h
0x180012f1c  mov     r8, rdx
0x180012f1f  mov     [rsp+38h+var_18], 0
0x180012f28  lea     rdx, aSystemMapsBack; "System\\Maps\\BackgroundTransferService"
0x180012f2f  mov     r9d, 208h
0x180012f35  lea     rcx, aMapsbackground_43; "MapsBackgroundTransfer"
0x180012f3c  call    cs:__imp_GetPersistedRegistryLocationW
0x180012f42  test    eax, eax
0x180012f44  jz      short loc_180012F6A
0x180012f46  jle     short loc_180012F50
0x180012f48  movzx   eax, ax
0x180012f4b  or      eax, 80070000h
0x180012f50  mov     r8d, 413h
0x180012f56  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x180012f5d  mov     ecx, eax
0x180012f5f  add     rsp, 38h
0x180012f63  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180012f6a  xor     eax, eax
0x180012f6c  add     rsp, 38h
0x180012f70  retn
```
