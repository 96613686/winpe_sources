# StrToAttrib(char *,ushort *,_attcache *,uchar * *,ulong &)

- ea: `0x1801991a0`
- end: `0x180199857`
- name: `?StrToAttrib@@YAXPEADPEAGPEAU_attcache@@PEAPEAEAEAK@Z`
- size: `1719`
- prototype: `void __usercall(char *Src@<rcx>, unsigned __int16 *@<rdx>, struct _attcache *@<r8>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1801983c0`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x180088800`
- `0x180100768`
- `0x180102050`
- `0x180192394`
- `0x180197ef0`
- `0x1801991a0`
- `0x180199ed0`
- `0x180199fa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x180199541`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x18019954f`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x180199541`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x18019954f`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180199325`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180199325`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1801993be`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x1801993be`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180199520`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18019952f`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180199520`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18019952f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180199563`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180199563`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18019929d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18019929d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180199339`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180199339`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18019921a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180199263`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180199797`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801997c4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18019921a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180199263`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180199797`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801997c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199234`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801992b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199363`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801993a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019941b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199476`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199582`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801995f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019960f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801996e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199710`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199234`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801992b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199363`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801993a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019941b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199476`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801994ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199582`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801995f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019960f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801996e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180199710`
- `ntdll!RtlFreeHeap` at `0x180199669`
- `ntdll!RtlFreeHeap` at `0x18019980f`
- `ntdll!RtlFreeHeap` at `0x18019982a`
- `ntdll!RtlFreeHeap` at `0x180199669`
- `ntdll!RtlFreeHeap` at `0x18019980f`
- `ntdll!RtlFreeHeap` at `0x18019982a`

## pseudocode

```c

```
