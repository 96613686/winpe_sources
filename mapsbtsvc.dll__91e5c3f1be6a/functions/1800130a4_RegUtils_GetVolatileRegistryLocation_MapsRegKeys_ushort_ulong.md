# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x1800130a4`
- end: `0x1800130e1`
- name: `?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `61`
- prototype: `int __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180012e84`

## callees

- `0x180008cf8`
- `0x1800130a4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800130d3`

## string_xrefs

- `0x1800130c6`: `RegUtils::GetVolatileRegistryLocation`
- `0x1800130ab`: `System\Maps\BackgroundTransferService\Volatile`

## pseudocode

```c
int __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, unsigned __int16 *a2)
{
  int v2; // eax

  v2 = StringCchCopyW(a2, 0x104u, L"System\\Maps\\BackgroundTransferService\\Volatile");
  if ( v2 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v2, "RegUtils::GetVolatileRegistryLocation", 1082);
}

```

## disassembly

```asm
0x1800130a4  sub     rsp, 28h
0x1800130a8  mov     rcx, rdx; unsigned __int16 *
0x1800130ab  lea     r8, aSystemMapsBack_0; "System\\Maps\\BackgroundTransferService"...
0x1800130b2  mov     edx, 104h; unsigned __int64
0x1800130b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800130bc  test    eax, eax
0x1800130be  jns     short loc_1800130DA
0x1800130c0  mov     r8d, 43Ah
0x1800130c6  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x1800130cd  mov     ecx, eax
0x1800130cf  add     rsp, 28h
0x1800130d3  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800130da  xor     eax, eax
0x1800130dc  add     rsp, 28h
0x1800130e0  retn
```
