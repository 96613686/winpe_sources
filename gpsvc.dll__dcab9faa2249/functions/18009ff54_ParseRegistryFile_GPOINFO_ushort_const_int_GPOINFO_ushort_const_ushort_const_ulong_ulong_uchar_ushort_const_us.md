# ParseRegistryFile(_GPOINFO *,ushort const *,int (*)(_GPOINFO *,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *),void *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *,int,int,int)

- ea: `0x18009ff54`
- end: `0x1800a1e1a`
- name: `?ParseRegistryFile@@YAHPEAU_GPOINFO@@PEBGP6AH011KKPEAE11PEAU_REGHASHTABLE@@3@ZPEAX1133HHH@Z`
- size: `7878`
- prototype: `int(struct _GPOINFO *, const unsigned __int16 *, int (*)(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *), void *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *, int, int, int)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180065928`
- `0x180096f94`
- `0x1800a1e20`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001ae60`
- `0x18001eeb0`
- `0x1800246a8`
- `0x180030bcc`
- `0x180044720`
- `0x18004a960`
- `0x18005334c`
- `0x1800575fc`
- `0x180067d58`
- `0x180073720`
- `0x180073984`
- `0x1800746c8`
- `0x180074b04`
- `0x180075644`
- `0x180075ec0`
- `0x180076734`
- `0x18007d320`
- `0x18007de08`
- `0x18009ff54`
- `0x1800a4180`
- `0x1800ba464`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a091c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a091c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a1dee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a1dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ffe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a00a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a053e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a05ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a05ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a09d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a133a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a144b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a16ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a179c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a184d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a187b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a190f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a19eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ffe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a00a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a053e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a05ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a05ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a09d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a133a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a144b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a16ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a179c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a184d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a187b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a18e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a190f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a19eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a061c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0ae0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a126c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a061c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0ae0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a126c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a141c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a141c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1d8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a1c05`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a1c7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a1c05`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a1c7a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a03a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a03a0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a09f8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a09f8`

## string_xrefs

- `0x1800a00ff`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a012a`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a029f`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a02cb`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a068f`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a06b5`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a07fc`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a0822`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a0b5e`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a0b93`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a0d5f`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a0d87`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a1a5d`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a1a82`: `ParseRegistryFile: String too large to format. The debug data will be truncated`
- `0x1800a002b`: `ParseRegistryFile: Entering with <%s>.`
- `0x1800a004e`: `ParseRegistryFile: Entering with <%s>.`
- `0x1800a00c3`: `Error during registry file parsing: Failed to get User SID`
- `0x1800a01bf`: `ParseRegistryFile: Failed to get User SID`
- `0x1800a01f2`: `ParseRegistryFile: Failed to get User SID`
- `0x1800a025b`: `Error during registry file parsing: Failed to impersonate user`
- `0x1800a0341`: `ParseRegistryFile: Failed to impersonate user`
- `0x1800a036c`: `ParseRegistryFile: Failed to impersonate user`
- `0x1800a04c8`: `ParseRegistryFile: (%s) not found.`
- `0x1800a04f1`: `ParseRegistryFile: (%s) not found.`
- `0x1800a054b`: `Error during registry file parsing: Could not get length of regsitry.pol file path (%s). Error: %d`
- `0x1800a05b9`: `ParseRegistryFile: Could not get length of regsitry.pol file path (%s). Error: %d`
- `0x1800a05f6`: `ParseRegistryFile: Could not get length of regsitry.pol file path (%s). Error: %d`
- `0x1800a0653`: `Error during registry file parsing: Failed to allocate memory`
- `0x1800a072f`: `ParseRegistryFile: Failed to allocate memory`
- `0x1800a0752`: `ParseRegistryFile: Failed to allocate memory`
- `0x1800a07c0`: `Error during registry file parsing: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d`
- `0x1800a08b3`: `ParseRegistryFile: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d`
- `0x1800a08e9`: `ParseRegistryFile: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d`
- `0x1800a095b`: `Error during registry file parsing: Failed to find %d last backslash character in registry.pol file path (%s), Error: %d`
- `0x1800a09a2`: `ParseRegistryFile: Failed to find %d last backslash character in registry.pol file path (%s), Error: %d`
- `0x1800a09e4`: `ParseRegistryFile: Failed to find %d last backslash character in registry.pol file path (%s), Error: %d`
- `0x1800a0a30`: `Error during registry file parsing: GetFileAttributes() failed to get attributes for gpo folder path (%s). Error: %d. Network connectivity to DC is lost.`
- `0x1800a0a72`: `ParseRegistryFile: GetFileAttributes() failed to get attributes for gpo folder path (%s). Error: %d. Network connectivity to DC is lost.`
- `0x1800a0aaf`: `ParseRegistryFile: GetFileAttributes() failed to get attributes for gpo folder path (%s). Error: %d. Network connectivity to DC is lost.`
- `0x1800a040e`: `Error during registry file parsing: CreateFile failed with %d`
- `0x1800a045f`: `ParseRegistryFile: CreateFile failed with %d`
- `0x1800a0499`: `ParseRegistryFile: CreateFile failed with %d`
- `0x1800a0b27`: `Error during registry file parsing: Failed to allocate memory with %d`
- `0x1800a0c33`: `ParseRegistryFile: Failed to allocate memory with %d`
- `0x1800a0c6f`: `ParseRegistryFile: Failed to allocate memory with %d`
- `0x1800a0d22`: `Error during registry file parsing: Failed to initialize Reader %d`
- `0x1800a0e14`: `ParseRegistryFile: Failed to initialize Reader %d`
- `0x1800a0e45`: `ParseRegistryFile: Failed to initialize Reader %d`
- `0x1800a0ea0`: `Error during registry file parsing: Failed to read signature with %d`
- `0x1800a0ec7`: `ParseRegistryFile: Failed to read signature with %d`
- `0x1800a0ef3`: `ParseRegistryFile: Failed to read signature with %d`
- `0x1800a0f29`: `Error during registry file parsing: Invalid file signature`
- `0x1800a0f5d`: `ParseRegistryFile: Invalid file signature`
- `0x1800a0f8d`: `ParseRegistryFile: Invalid file signature`
- `0x1800a0fdf`: `Error during registry file parsing: Failed to read version number with %d`
- `0x1800a100a`: `ParseRegistryFile: Failed to read version number with %d`
- `0x1800a1036`: `ParseRegistryFile: Failed to read version number with %d`
- `0x1800a1065`: `Error during registry file parsing: Invalid file version`
- `0x1800a108a`: `ParseRegistryFile: Invalid file version`
- `0x1800a10b0`: `ParseRegistryFile: Invalid file version`
- `0x1800a1915`: `Error during registry file parsing: Failed to read first character with %d`
- `0x1800a1a23`: `Error during registry file parsing: Failed to read first character with %d`
- `0x1800a1940`: `ParseRegistryFile: Failed to read first character with %d`
- `0x1800a196c`: `ParseRegistryFile: Failed to read first character with %d`
- `0x1800a1af3`: `ParseRegistryFile: Failed to read first character with %d`
- `0x1800a1b24`: `ParseRegistryFile: Failed to read first character with %d`
- `0x1800a1451`: `Error during registry file parsing: Failed to read keyname character with %d`
- `0x1800a147c`: `ParseRegistryFile: Failed to read keyname character with %d`
- `0x1800a14a8`: `ParseRegistryFile: Failed to read keyname character with %d`
- `0x1800a1b4e`: `Error during registry file parsing: Keyname exceeded max size`
- `0x1800a1b73`: `ParseRegistryFile: Keyname exceeded max size`
- `0x1800a1b99`: `ParseRegistryFile: Keyname exceeded max size`
- `0x1800a14d6`: `Error during registry file parsing: Failed to read valuename character with %d`
- `0x1800a1501`: `ParseRegistryFile: Failed to read valuename character with %d`
- `0x1800a152d`: `ParseRegistryFile: Failed to read valuename character with %d`
- `0x1800a1994`: `Error during registry file parsing: Valuename exceeded max size`
- `0x1800a19b9`: `ParseRegistryFile: Valuename exceeded max size`
- `0x1800a19df`: `ParseRegistryFile: Valuename exceeded max size`
- `0x1800a1881`: `Error during registry file parsing: Failed to read type with %d`
- `0x1800a18ac`: `ParseRegistryFile: Failed to read type with %d`
- `0x1800a18d8`: `ParseRegistryFile: Failed to read type with %d`
- `0x1800a1777`: `Error during registry file parsing: Failed to skip semicolon with %d`
- `0x1800a17a2`: `ParseRegistryFile: Failed to skip semicolon with %d`
- `0x1800a17ce`: `ParseRegistryFile: Failed to skip semicolon with %d`
- `0x1800a17fc`: `Error during registry file parsing: Failed to read data length with %d`
- `0x1800a1827`: `ParseRegistryFile: Failed to read data length with %d`
- `0x1800a1853`: `ParseRegistryFile: Failed to read data length with %d`
- `0x1800a15e3`: `Error during registry file parsing: Failed to allocate memory for data with %d`
- `0x1800a160e`: `ParseRegistryFile: Failed to allocate memory for data with %d`
- `0x1800a163a`: `ParseRegistryFile: Failed to allocate memory for data with %d`
- `0x1800a155b`: `Error during registry file parsing: Failed to read data with %d`
- `0x1800a1586`: `ParseRegistryFile: Failed to read data with %d`
- `0x1800a15b2`: `ParseRegistryFile: Failed to read data with %d`
- `0x1800a16f2`: `Error during registry file parsing: Failed to skip closing bracket with %d`
- `0x1800a171d`: `ParseRegistryFile: Failed to skip closing bracket with %d`
- `0x1800a1749`: `ParseRegistryFile: Failed to skip closing bracket with %d`
- `0x1800a1668`: `Error during registry file parsing: Expected to find ], but found %c`
- `0x1800a1693`: `ParseRegistryFile: Expected to find ], but found %c`
- `0x1800a16c4`: `ParseRegistryFile: Expected to find ], but found %c`
- `0x1800a1357`: `ParseRegistryFile: Callback function returned false.`
- `0x1800a137a`: `ParseRegistryFile: Callback function returned false.`
- `0x1800a13d0`: `ParseRegistryFile: ArchiveRegistryValue returned false.`
- `0x1800a13f5`: `ParseRegistryFile: ArchiveRegistryValue returned false.`
- `0x1800a1d0f`: `ParseRegistryFile: Leaving.`
- `0x1800a1d37`: `ParseRegistryFile: Leaving.`
- `0x1800a1dac`: `ParseRegistryFile: Failing callback because all registry values couldn't be set.`
- `0x1800a1dd4`: `ParseRegistryFile: Failing callback because all registry values couldn't be set.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ParseRegistryFile(
        struct _GPOINFO *a1,
        unsigned __int16 *a2,
        int (*a3)(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *),
        void *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct _REGHASHTABLE *a7,
        struct _REGHASHTABLE *a8,
        int a9,
        int a10,
        int a11)
{
  unsigned __int16 *v13; // r15
  int v15; // edi
  DWORD LastError; // ebx
  unsigned __int16 *SidString; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // rsi
  void (*v21)(unsigned int, const unsigned __int16 *, ...); // rsi
  const wchar_t *v22; // rdx
  __int64 v23; // rdx
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // rsi
  HANDLE FileW; // rsi
  __int64 v26; // rdx
  DWORD v27; // eax
  int v28; // eax
  void (*v29)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v30; // eax
  DWORD v31; // eax
  const unsigned __int16 *v32; // rcx
  int v33; // eax
  __int64 v34; // rdx
  void (*v35)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v36; // eax
  DWORD v37; // eax
  unsigned __int64 v38; // r14
  unsigned __int16 *v39; // rax
  const wchar_t *v40; // rdi
  __int64 v41; // rdx
  void (*v42)(unsigned int, const unsigned __int16 *, ...); // rax
  int v43; // eax
  __int64 v44; // rdx
  int v45; // eax
  void (*v46)(unsigned int, const unsigned __int16 *, ...); // rax
  void (*v47)(unsigned int, const unsigned __int16 *, ...); // rdi
  int i; // esi
  wchar_t *v49; // rax
  __int64 v50; // rdx
  void (*v51)(unsigned int, const unsigned __int16 *, ...); // rdi
  __int64 v52; // rdx
  void (*v53)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v54; // eax
  DWORD v55; // eax
  _WORD *v56; // rsi
  __int64 v57; // rdx
  DWORD v58; // eax
  void (*v59)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v60; // eax
  DWORD v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rdx
  DWORD v64; // eax
  int v65; // eax
  void (*v66)(unsigned int, const unsigned __int16 *, ...); // rax
  void (*v67)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v68; // eax
  const wchar_t *v69; // rdx
  __int64 v70; // r8
  void (*v71)(unsigned int, const unsigned __int16 *, ...); // rax
  DWORD v72; // eax
  __int64 v73; // rdx
  DWORD v74; // eax
  DWORD v75; // eax
  void (*v76)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v77; // rdx
  __int64 v78; // rdx
  DWORD v79; // eax
  DWORD v80; // eax
  unsigned int v81; // eax
  unsigned int j; // ecx
  _WORD *v83; // rsi
  unsigned int v84; // eax
  unsigned int k; // ecx
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx
  HLOCAL v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rdx
  struct _GPOINFO *v92; // rsi
  DWORD v93; // eax
  DWORD v94; // eax
  DWORD v95; // eax
  DWORD v96; // eax
  DWORD v97; // eax
  DWORD v98; // eax
  __int64 v99; // rdx
  DWORD v100; // eax
  DWORD v101; // eax
  DWORD v102; // eax
  DWORD v103; // eax
  DWORD v104; // eax
  DWORD v105; // eax
  DWORD v106; // eax
  DWORD v107; // eax
  DWORD v108; // eax
  DWORD v109; // eax
  __int64 v110; // rdx
  DWORD v111; // eax
  DWORD v112; // eax
  __int64 v113; // rdx
  DWORD v114; // eax
  __int64 v115; // r8
  struct _GPOINFO *v116; // r13
  char IsEnabled; // al
  unsigned __int16 *v118; // r14
  int v119; // edi
  int v120; // esi
  int v121; // edi
  unsigned int GPSourceFileId; // eax
  int *v123; // r8
  int v124; // esi
  int v125; // edi
  unsigned int v126; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  _WORD v130[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v131; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v132; // [rsp+68h] [rbp-98h]
  unsigned int v133; // [rsp+70h] [rbp-90h] BYREF
  DWORD uBytes[3]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v135; // [rsp+80h] [rbp-80h]
  unsigned int v136; // [rsp+84h] [rbp-7Ch] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  HLOCAL v138; // [rsp+90h] [rbp-70h]
  HLOCAL v139; // [rsp+98h] [rbp-68h]
  int v140; // [rsp+A0h] [rbp-60h]
  DWORD v141; // [rsp+A4h] [rbp-5Ch]
  int v142; // [rsp+A8h] [rbp-58h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  __int64 v144; // [rsp+C0h] [rbp-40h]
  __int64 v145; // [rsp+C8h] [rbp-38h]
  __int128 v146; // [rsp+D0h] [rbp-30h]
  struct _GPOINFO *v147; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v148; // [rsp+E8h] [rbp-18h]
  HANDLE hObject; // [rsp+F0h] [rbp-10h]
  void *TokenHandle; // [rsp+F8h] [rbp-8h] BYREF
  struct _REGHASHTABLE *v151; // [rsp+100h] [rbp+0h]
  _QWORD v152[14]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v153; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v154[2046]; // [rsp+182h] [rbp+82h] BYREF

  v13 = a2;
  v132 = a2;
  v147 = a1;
  v148 = a5;
  v151 = a7;
  *(_QWORD *)&uBytes[1] = a8;
  v15 = 0;
  v135 = 0;
  v133 = 0;
  v136 = 0;
  uBytes[0] = 0;
  v138 = 0;
  v139 = 0;
  hMem = 0;
  v130[0] = 0;
  TokenHandle = 0;
  LastError = GetLastError();
  v131 = LastError;
  v140 = 0;
  v141 = 0;
  v153 = 0;
  memset_0(v154, 0, sizeof(v154));
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ParseRegistryFile: Entering with <%s>.", v13);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ParseRegistryFile: Entering with <%s>.", v13);
    }
  }
  if ( a9 )
    goto LABEL_55;
  hObject = (HANDLE)-1LL;
  if ( !a1 || (*(_BYTE *)a1 & 1) != 0 )
  {
LABEL_35:
    v15 = 1;
    if ( !(unsigned int)ImpersonateUser(*((HANDLE *)a1 + 1), &TokenHandle) )
    {
      LastError = GetLastError();
      v131 = LastError;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                               `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                               v23) )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_413;
        v21 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to impersonate user");
          goto LABEL_413;
        }
        v22 = L"ParseRegistryFile: Failed to impersonate user";
        goto LABEL_29;
      }
      if ( (int)StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Failed to impersonate user") < 0 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_413;
        v24 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
          goto LABEL_40;
        if ( g_lpDebugMsgContextInstance )
        {
LABEL_42:
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"%s",
              L"ParseRegistryFile: String too large to format. The debug data will be truncated");
        }
      }
LABEL_44:
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_413;
      v20 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
        goto LABEL_22;
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        goto LABEL_25;
      goto LABEL_413;
    }
LABEL_55:
    FileW = CreateFileW(v13, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
    hObject = FileW;
    if ( v15 )
      RevertToUser(&TokenHandle);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( GetLastError() != 2 && GetLastError() != 3 )
      {
        LastError = GetLastError();
        v131 = LastError;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                 `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                 v26) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v29 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v30 = GetLastError();
              v29(2u, L"ParseRegistryFile: CreateFile failed with %d", v30);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v31 = GetLastError();
              RedirectDebugMsg(2u, L"ParseRegistryFile: CreateFile failed with %d", v31);
            }
          }
          goto LABEL_413;
        }
        v27 = GetLastError();
        v28 = StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: CreateFile failed with %d", v27);
        goto LABEL_80;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ParseRegistryFile: (%s) not found.", v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ParseRegistryFile: (%s) not found.", v13);
        }
      }
      if ( (unsigned int)IsUNCPath(v13) )
      {
        *(_QWORD *)&uBytes[1] = 0;
        v33 = StringCchLengthW(v32, v19, (unsigned __int64 *)&uBytes[1]);
        if ( v33 < 0 )
        {
          LastError = (unsigned __int16)v33;
          v131 = (unsigned __int16)v33;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                   `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                   v34) )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v35 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v36 = GetLastError();
                v35(2u, L"ParseRegistryFile: Could not get length of regsitry.pol file path (%s). Error: %d", v13, v36);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v37 = GetLastError();
                RedirectDebugMsg(
                  2u,
                  L"ParseRegistryFile: Could not get length of regsitry.pol file path (%s). Error: %d",
                  v13,
                  v37);
              }
            }
            goto LABEL_413;
          }
          dwCreationDisposition[0] = GetLastError();
          v28 = StringCchPrintfW(
                  &v153,
                  0x400u,
                  L"Error during registry file parsing: Could not get length of regsitry.pol file path (%s). Error: %d",
                  v13,
                  *(_QWORD *)dwCreationDisposition);
LABEL_80:
          if ( v28 < 0 )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_413;
            v24 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
LABEL_40:
              v24(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
              goto LABEL_44;
            }
            if ( g_lpDebugMsgContextInstance )
              goto LABEL_42;
          }
          goto LABEL_44;
        }
        v38 = *(_QWORD *)&uBytes[1];
        v39 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * *(_QWORD *)&uBytes[1] + 2);
        v40 = v39;
        *(_QWORD *)&uBytes[1] = v39;
        if ( !v39 )
        {
          LastError = GetLastError();
          v131 = LastError;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                   `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                   v41) )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"ParseRegistryFile: Failed to allocate memory");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to allocate memory");
              }
            }
            goto LABEL_112;
          }
          if ( (int)StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Failed to allocate memory") < 0 )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
            {
LABEL_112:
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&uBytes[1]);
LABEL_412:
              v13 = v132;
              goto LABEL_413;
            }
            v42 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                2u,
                L"%s",
                L"ParseRegistryFile: String too large to format. The debug data will be truncated");
            }
            else
            {
              if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              {
LABEL_100:
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( v42 )
                  {
                    v42(2u, L"%s", &v153);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"%s", &v153);
                  }
                }
                goto LABEL_112;
              }
              RedirectDebugMsg(
                2u,
                L"%s",
                L"ParseRegistryFile: String too large to format. The debug data will be truncated");
            }
          }
          v42 = g_lpDebugMsg;
          goto LABEL_100;
        }
        v13 = v132;
        v43 = StringCchCopyNW(v39, v38 + 1, v132, v38);
        if ( v43 >= 0 )
        {
          for ( i = 0; i < 2; ++i )
          {
            v49 = wcsrchr(v40, 0x5Cu);
            if ( !v49 )
            {
              LastError = 53;
              v131 = 53;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                      `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                      v50) )
              {
                dwFlagsAndAttributes[0] = GetLastError();
                v45 = StringCchPrintfW(
                        &v153,
                        0x400u,
                        L"Error during registry file parsing: Failed to find %d last backslash character in registry.pol f"
                         "ile path (%s), Error: %d",
                        (unsigned int)(i + 1),
                        v13,
                        *(_QWORD *)dwFlagsAndAttributes);
                goto LABEL_116;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v51 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  dwCreationDisposition[0] = GetLastError();
                  v51(
                    2u,
                    L"ParseRegistryFile: Failed to find %d last backslash character in registry.pol file path (%s), Error: %d",
                    (unsigned int)(i + 1),
                    v13,
                    *(_QWORD *)dwCreationDisposition);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  dwCreationDisposition[0] = GetLastError();
                  RedirectDebugMsg(
                    2u,
                    L"ParseRegistryFile: Failed to find %d last backslash character in registry.pol file path (%s), Error: %d",
                    (unsigned int)(i + 1),
                    v13,
                    *(_QWORD *)dwCreationDisposition);
                }
              }
              goto LABEL_136;
            }
            *v49 = 0;
          }
          if ( GetFileAttributesW(v40) != -1 )
          {
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&uBytes[1]);
            goto LABEL_411;
          }
          LastError = GetLastError();
          v131 = LastError;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                  v52) )
          {
            dwCreationDisposition[0] = GetLastError();
            v45 = StringCchPrintfW(
                    &v153,
                    0x400u,
                    L"Error during registry file parsing: GetFileAttributes() failed to get attributes for gpo folder path"
                     " (%s). Error: %d. Network connectivity to DC is lost.",
                    v40,
                    *(_QWORD *)dwCreationDisposition);
            goto LABEL_116;
          }
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v53 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v54 = GetLastError();
              v53(
                2u,
                L"ParseRegistryFile: GetFileAttributes() failed to get attributes for gpo folder path (%s). Error: %d. Net"
                 "work connectivity to DC is lost.",
                v40,
                v54);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v55 = GetLastError();
              RedirectDebugMsg(
                2u,
                L"ParseRegistryFile: GetFileAttributes() failed to get attributes for gpo folder path (%s). Error: %d. Net"
                 "work connectivity to DC is lost.",
                v40,
                v55);
            }
          }
          goto LABEL_136;
        }
        LastError = (unsigned __int16)v43;
        v131 = (unsigned __int16)v43;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                 `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                 v44) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v47 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              dwCreationDisposition[0] = GetLastError();
              v47(
                2u,
                L"ParseRegistryFile: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d",
                v132,
                v38 + 1,
                *(_QWORD *)dwCreationDisposition);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              dwCreationDisposition[0] = GetLastError();
              RedirectDebugMsg(
                2u,
                L"ParseRegistryFile: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d",
                v132,
                v38 + 1,
                *(_QWORD *)dwCreationDisposition);
            }
          }
          goto LABEL_136;
        }
        dwFlagsAndAttributes[0] = GetLastError();
        v45 = StringCchPrintfW(
                &v153,
                0x400u,
                L"Error during registry file parsing: Failed to copy registry.pol file (%s) over to buffer of size: %Iu, Error: %d",
                v132,
                v38 + 1,
                *(_QWORD *)dwFlagsAndAttributes);
LABEL_116:
        if ( v45 < 0 )
        {
          if ( !*(_DWORD *)&g_dwDebugLevel )
          {
LABEL_136:
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&uBytes[1]);
            goto LABEL_413;
          }
          v46 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
          }
          else
          {
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            {
LABEL_124:
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( v46 )
                {
                  v46(2u, L"%s", &v153);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"%s", &v153);
                }
              }
              goto LABEL_136;
            }
            RedirectDebugMsg(
              2u,
              L"%s",
              L"ParseRegistryFile: String too large to format. The debug data will be truncated");
          }
        }
        v46 = g_lpDebugMsg;
        goto LABEL_124;
      }
LABEL_411:
      v135 = 1;
      if ( (*(_DWORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x200000) == 0 )
        goto LABEL_419;
      goto LABEL_412;
    }
    v56 = LocalAlloc(0x40u, 0x1000u);
    v138 = v56;
    if ( !v56 )
    {
      LastError = GetLastError();
      v131 = LastError;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                              v57) )
        goto LABEL_161;
      goto LABEL_174;
    }
    v139 = LocalAlloc(0x40u, 0x400u);
    if ( !v139 )
    {
      LastError = GetLastError();
      v131 = LastError;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                              v62) )
      {
LABEL_161:
        v58 = GetLastError();
        if ( (int)StringCchPrintfW(
                    &v153,
                    0x400u,
                    L"Error during registry file parsing: Failed to allocate memory with %d",
                    v58) < 0 )
        {
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_412;
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"%s",
              L"ParseRegistryFile: String too large to format. The debug data will be truncated");
          }
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"%s", &v153);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"%s", &v153);
          }
        }
        goto LABEL_412;
      }
LABEL_174:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v59 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v60 = GetLastError();
          v59(2u, L"ParseRegistryFile: Failed to allocate memory with %d", v60);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v61 = GetLastError();
          RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to allocate memory with %d", v61);
        }
      }
      goto LABEL_412;
    }
    v142 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v144 = 0;
    v146 = 0;
    v145 = 0;
    if ( !CFileReader::Initialize((CFileReader *)&v142, hObject) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                              v63) )
      {
        v64 = GetLastError();
        v65 = StringCchPrintfW(
                &v153,
                0x400u,
                L"Error during registry file parsing: Failed to initialize Reader %d",
                v64);
        goto LABEL_186;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_208;
      v67 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v72 = GetLastError();
          RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to initialize Reader %d", v72);
        }
        goto LABEL_208;
      }
      v68 = GetLastError();
      v69 = L"ParseRegistryFile: Failed to initialize Reader %d";
LABEL_203:
      v70 = v68;
      v71 = v67;
LABEL_204:
      v71(2u, v69, v70);
      goto LABEL_208;
    }
    if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, &v133, 4u) )
    {
      LastError = 13;
      v131 = 13;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                               `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                               v73) )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_208;
        v67 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v75 = GetLastError();
            RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read signature with %d", v75);
          }
          goto LABEL_208;
        }
        v68 = GetLastError();
        v69 = L"ParseRegistryFile: Failed to read signature with %d";
        goto LABEL_203;
      }
      v74 = GetLastError();
      v65 = StringCchPrintfW(
              &v153,
              0x400u,
              L"Error during registry file parsing: Failed to read signature with %d",
              v74);
LABEL_186:
      if ( v65 < 0 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_208;
        v66 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
        }
        else
        {
          if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            goto LABEL_194;
          RedirectDebugMsg(
            2u,
            L"%s",
            L"ParseRegistryFile: String too large to format. The debug data will be truncated");
        }
      }
      v66 = g_lpDebugMsg;
LABEL_194:
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_208;
      if ( v66 )
        goto LABEL_196;
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_208;
      goto LABEL_199;
    }
    if ( v133 != 1734693456 )
    {
      LastError = 13;
      v131 = 13;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                              v73) )
      {
        v65 = StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Invalid file signature");
        goto LABEL_186;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_208;
      v76 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ParseRegistryFile: Invalid file signature");
        goto LABEL_208;
      }
      v77 = L"ParseRegistryFile: Invalid file signature";
      goto LABEL_224;
    }
    if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, &v133, 4u) )
    {
      LastError = 13;
      v131 = 13;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                               `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                               v78) )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_208;
        v67 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v80 = GetLastError();
            RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read version number with %d", v80);
          }
          goto LABEL_208;
        }
        v68 = GetLastError();
        v69 = L"ParseRegistryFile: Failed to read version number with %d";
        goto LABEL_203;
      }
      v79 = GetLastError();
      v65 = StringCchPrintfW(
              &v153,
              0x400u,
              L"Error during registry file parsing: Failed to read version number with %d",
              v79);
      goto LABEL_186;
    }
    if ( v133 != 1 )
    {
      LastError = 13;
      v131 = 13;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                              v78) )
      {
        v65 = StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Invalid file version");
        goto LABEL_186;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_208;
      v76 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ParseRegistryFile: Invalid file version");
        goto LABEL_208;
      }
      v77 = L"ParseRegistryFile: Invalid file version";
LABEL_224:
      v76(2u, v77);
      goto LABEL_208;
    }
    while ( 2 )
    {
      if ( (unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
      {
        if ( v130[0] == 91 )
        {
          v81 = 0;
          v133 = 0;
          for ( j = 0; j < 0x800; j = v81 )
          {
            if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
            {
              LastError = 13;
              v131 = 13;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                      `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                      0) )
              {
                v93 = GetLastError();
                v65 = StringCchPrintfW(
                        &v153,
                        0x400u,
                        L"Error during registry file parsing: Failed to read keyname character with %d",
                        v93);
                goto LABEL_186;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v67 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v68 = GetLastError();
                  v69 = L"ParseRegistryFile: Failed to read keyname character with %d";
                  goto LABEL_203;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  v94 = GetLastError();
                  RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read keyname character with %d", v94);
                }
              }
              goto LABEL_208;
            }
            *v56 = v130[0];
            v81 = v133;
            if ( !v130[0] )
              break;
            ++v56;
            v81 = v133 + 1;
            v133 = v81;
          }
          if ( v81 >= 0x800 )
          {
            LastError = 13;
            v131 = 13;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                    0) )
            {
              v65 = StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Keyname exceeded max size");
              goto LABEL_186;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v76 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v77 = L"ParseRegistryFile: Keyname exceeded max size";
                goto LABEL_224;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"ParseRegistryFile: Keyname exceeded max size");
            }
LABEL_208:
            CFileReader::~CFileReader((CFileReader *)&v142);
            goto LABEL_412;
          }
          if ( (unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
          {
            if ( v130[0] != 59 )
              break;
            v83 = v139;
            v84 = 0;
            v133 = 0;
            for ( k = 0; k < 0x200; k = v84 )
            {
              if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
              {
                LastError = 13;
                v131 = 13;
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                        `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                        0) )
                {
                  v95 = GetLastError();
                  v65 = StringCchPrintfW(
                          &v153,
                          0x400u,
                          L"Error during registry file parsing: Failed to read valuename character with %d",
                          v95);
                  goto LABEL_186;
                }
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  v67 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v68 = GetLastError();
                    v69 = L"ParseRegistryFile: Failed to read valuename character with %d";
                    goto LABEL_203;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    v96 = GetLastError();
                    RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read valuename character with %d", v96);
                  }
                }
                goto LABEL_208;
              }
              *v83 = v130[0];
              v84 = v133;
              if ( !v130[0] )
                break;
              ++v83;
              v84 = v133 + 1;
              v133 = v84;
            }
            if ( v84 >= 0x200 )
            {
              LastError = 13;
              v131 = 13;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                      `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                      0) )
              {
                v65 = StringCchPrintfW(
                        &v153,
                        0x400u,
                        L"Error during registry file parsing: Valuename exceeded max size");
                goto LABEL_186;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v76 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v77 = L"ParseRegistryFile: Valuename exceeded max size";
                  goto LABEL_224;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"ParseRegistryFile: Valuename exceeded max size");
              }
            }
            else
            {
              if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
                goto LABEL_365;
              if ( v130[0] != 59 )
                break;
              if ( (unsigned int)CFileReader::ReadFile((CFileReader *)&v142, &v136, 4u) )
              {
                if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, &v133, 2u) )
                  goto LABEL_341;
                if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, uBytes, 4u) )
                {
                  LastError = 13;
                  v131 = 13;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                          v88) )
                  {
                    v106 = GetLastError();
                    v65 = StringCchPrintfW(
                            &v153,
                            0x400u,
                            L"Error during registry file parsing: Failed to read data length with %d",
                            v106);
                    goto LABEL_186;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v67 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v68 = GetLastError();
                      v69 = L"ParseRegistryFile: Failed to read data length with %d";
                      goto LABEL_203;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      v107 = GetLastError();
                      RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read data length with %d", v107);
                    }
                  }
                  goto LABEL_208;
                }
                if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, &v133, 2u) )
                {
LABEL_341:
                  LastError = 13;
                  v131 = 13;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                          v87) )
                  {
                    v104 = GetLastError();
                    v65 = StringCchPrintfW(
                            &v153,
                            0x400u,
                            L"Error during registry file parsing: Failed to skip semicolon with %d",
                            v104);
                    goto LABEL_186;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v67 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v68 = GetLastError();
                      v69 = L"ParseRegistryFile: Failed to skip semicolon with %d";
                      goto LABEL_203;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      v105 = GetLastError();
                      RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to skip semicolon with %d", v105);
                    }
                  }
                  goto LABEL_208;
                }
                hMem = 0;
                if ( uBytes[0] )
                {
                  v89 = LocalAlloc(0x40u, uBytes[0]);
                  hMem = v89;
                  if ( !v89 )
                  {
                    LastError = GetLastError();
                    v131 = LastError;
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                            v99) )
                    {
                      v100 = GetLastError();
                      v65 = StringCchPrintfW(
                              &v153,
                              0x400u,
                              L"Error during registry file parsing: Failed to allocate memory for data with %d",
                              v100);
                      goto LABEL_186;
                    }
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      v67 = g_lpDebugMsg;
                      if ( g_lpDebugMsg )
                      {
                        v68 = GetLastError();
                        v69 = L"ParseRegistryFile: Failed to allocate memory for data with %d";
                        goto LABEL_203;
                      }
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        v101 = GetLastError();
                        RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to allocate memory for data with %d", v101);
                      }
                    }
                    goto LABEL_208;
                  }
                  if ( !(unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v89, uBytes[0]) )
                  {
                    LastError = 13;
                    v131 = 13;
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                            v90) )
                    {
                      v97 = GetLastError();
                      v65 = StringCchPrintfW(
                              &v153,
                              0x400u,
                              L"Error during registry file parsing: Failed to read data with %d",
                              v97);
                      goto LABEL_186;
                    }
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      v67 = g_lpDebugMsg;
                      if ( g_lpDebugMsg )
                      {
                        v68 = GetLastError();
                        v69 = L"ParseRegistryFile: Failed to read data with %d";
                        goto LABEL_203;
                      }
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        v98 = GetLastError();
                        RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read data with %d", v98);
                      }
                    }
                    goto LABEL_208;
                  }
                }
                if ( (unsigned int)CFileReader::ReadFile((CFileReader *)&v142, v130, 2u) )
                {
                  if ( v130[0] == 93 )
                  {
                    v92 = v147;
                    if ( a11
                      && !(unsigned int)CheckAllowedRegistryPoliciesOnDomainIncapableSystems(
                                          v147,
                                          (unsigned __int16 *)v138,
                                          (unsigned __int16 *)v139) )
                    {
                      v56 = v138;
                    }
                    else
                    {
                      if ( !((unsigned int (__fastcall *)(struct _GPOINFO *, HLOCAL, HLOCAL, _QWORD, DWORD, HLOCAL, unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, _QWORD))a3)(
                              v92,
                              v138,
                              v139,
                              v136,
                              uBytes[0],
                              hMem,
                              v148,
                              a6,
                              v151,
                              *(_QWORD *)&uBytes[1]) )
                      {
                        v140 = 1;
                        v141 = GetLastError();
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(2u, L"ParseRegistryFile: Callback function returned false.");
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(2u, L"ParseRegistryFile: Callback function returned false.");
                          }
                        }
                      }
                      v56 = v138;
                      if ( a4
                        && !(unsigned int)ArchiveRegistryValue(
                                            a4,
                                            (const wchar_t *)v138,
                                            (const wchar_t *)v139,
                                            v136,
                                            uBytes[0],
                                            (unsigned __int8 *)hMem)
                        && *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(2u, L"ParseRegistryFile: ArchiveRegistryValue returned false.");
                        }
                        else if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
                        {
                          RedirectDebugMsg(2u, L"ParseRegistryFile: ArchiveRegistryValue returned false.");
                        }
                      }
                    }
                    if ( hMem )
                    {
                      LocalFree(hMem);
                      hMem = 0;
                    }
                    continue;
                  }
                  LastError = 13;
                  v131 = 13;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                          v91) )
                  {
                    v65 = StringCchPrintfW(
                            &v153,
                            0x400u,
                            L"Error during registry file parsing: Expected to find ], but found %c",
                            v130[0]);
                    goto LABEL_186;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v71 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v70 = v130[0];
                      v69 = L"ParseRegistryFile: Expected to find ], but found %c";
                      goto LABEL_204;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      RedirectDebugMsg(2u, L"ParseRegistryFile: Expected to find ], but found %c", v130[0]);
                  }
                }
                else
                {
                  LastError = 13;
                  v131 = 13;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                          v91) )
                  {
                    v102 = GetLastError();
                    v65 = StringCchPrintfW(
                            &v153,
                            0x400u,
                            L"Error during registry file parsing: Failed to skip closing bracket with %d",
                            v102);
                    goto LABEL_186;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v67 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v68 = GetLastError();
                      v69 = L"ParseRegistryFile: Failed to skip closing bracket with %d";
                      goto LABEL_203;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      v103 = GetLastError();
                      RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to skip closing bracket with %d", v103);
                    }
                  }
                }
              }
              else
              {
                LastError = 13;
                v131 = 13;
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                        `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                        v86) )
                {
                  v108 = GetLastError();
                  v65 = StringCchPrintfW(
                          &v153,
                          0x400u,
                          L"Error during registry file parsing: Failed to read type with %d",
                          v108);
                  goto LABEL_186;
                }
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  v67 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v68 = GetLastError();
                    v69 = L"ParseRegistryFile: Failed to read type with %d";
                    goto LABEL_203;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    v109 = GetLastError();
                    RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read type with %d", v109);
                  }
                }
              }
            }
            goto LABEL_208;
          }
          if ( GetLastError() == 38 )
            break;
          LastError = 13;
          v131 = 13;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                  v113) )
          {
            v114 = GetLastError();
            if ( (int)StringCchPrintfW(
                        &v153,
                        0x400u,
                        L"Error during registry file parsing: Failed to read first character with %d",
                        v114) < 0 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_208;
              v66 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  2u,
                  L"%s",
                  L"ParseRegistryFile: String too large to format. The debug data will be truncated");
              }
              else
              {
                if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                  goto LABEL_391;
                RedirectDebugMsg(
                  2u,
                  L"%s",
                  L"ParseRegistryFile: String too large to format. The debug data will be truncated");
              }
            }
            v66 = g_lpDebugMsg;
LABEL_391:
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_208;
            if ( v66 )
            {
LABEL_196:
              v66(2u, L"%s", &v153);
              goto LABEL_208;
            }
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              goto LABEL_208;
LABEL_199:
            RedirectDebugMsg(2u, L"%s", &v153);
            goto LABEL_208;
          }
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_208;
          v67 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v115 = GetLastError();
              RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read first character with %d", v115);
            }
            goto LABEL_208;
          }
LABEL_398:
          v68 = GetLastError();
          v69 = L"ParseRegistryFile: Failed to read first character with %d";
          goto LABEL_203;
        }
      }
      else
      {
LABEL_365:
        if ( GetLastError() != 38 )
        {
          LastError = 13;
          v131 = 13;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                                  v110) )
          {
            v111 = GetLastError();
            v65 = StringCchPrintfW(
                    &v153,
                    0x400u,
                    L"Error during registry file parsing: Failed to read first character with %d",
                    v111);
            goto LABEL_186;
          }
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_208;
          v67 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v112 = GetLastError();
              RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to read first character with %d", v112);
            }
            goto LABEL_208;
          }
          goto LABEL_398;
        }
      }
      break;
    }
    CFileReader::~CFileReader((CFileReader *)&v142);
    goto LABEL_411;
  }
  if ( *((_QWORD *)a1 + 9) || (SidString = GetSidString(*((void **)a1 + 1)), (*((_QWORD *)a1 + 9) = SidString) != 0) )
  {
    if ( (*(_BYTE *)a1 & 1) == 0 && !(unsigned int)ShouldUserImpersonated(*((const unsigned __int16 **)a1 + 9)) )
      goto LABEL_55;
    goto LABEL_35;
  }
  LastError = GetLastError();
  v131 = LastError;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                           v18) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_413;
    v21 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ParseRegistryFile: Failed to get User SID");
      goto LABEL_413;
    }
    v22 = L"ParseRegistryFile: Failed to get User SID";
LABEL_29:
    v21(2u, v22);
    goto LABEL_413;
  }
  if ( (int)StringCchPrintfW(&v153, 0x400u, L"Error during registry file parsing: Failed to get User SID") < 0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_413;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"%s", L"ParseRegistryFile: String too large to format. The debug data will be truncated");
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v20 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
LABEL_22:
      v20(2u, L"%s", &v153);
      goto LABEL_413;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
LABEL_25:
      RedirectDebugMsg(2u, L"%s", &v153);
  }
LABEL_413:
  if ( a10 )
  {
    v116 = v147;
    if ( v147 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(
                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl'::`2'::impl,
                    v19);
      v118 = (unsigned __int16 *)*((_QWORD *)v116 + 33);
      v119 = *((_DWORD *)v116 + 64);
      if ( IsEnabled )
      {
        v120 = GetTickCount() - v119;
        v121 = *((_DWORD *)v116 + 70);
        GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpreg.cpp");
        CGPAdminEventGPOFileFailure::CGPAdminEventGPOFileFailure(
          (CGPAdminEventGenericFailure *)v152,
          (__int64)gpEvent_REGISTRY_TEMPLATE_ERROR,
          GPSourceFileId,
          1732,
          v121,
          v120,
          LastError,
          v118,
          v148,
          v13);
      }
      else
      {
        v124 = GetTickCount() - v119;
        v125 = *((_DWORD *)v116 + 70);
        v126 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpreg.cpp");
        CGPAdminEventGPOFileFailure::CGPAdminEventGPOFileFailure(
          (CGPAdminEventGenericFailure *)v152,
          (__int64)gpEvent_REGISTRY_TEMPLATE_ERROR,
          v126,
          1746,
          v125,
          v124,
          LastError,
          v118,
          v148,
          v13);
      }
      CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v116 + 34), (struct CGPEventInfo *)v152, v123);
      v152[0] = &CGPAdminEventLdapFailure::`vftable';
      CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v152);
    }
  }
LABEL_419:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ParseRegistryFile: Leaving.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ParseRegistryFile: Leaving.");
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v138 )
    LocalFree(v138);
  if ( v139 )
    LocalFree(v139);
  if ( v140 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ParseRegistryFile: Failing callback because all registry values couldn't be set.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ParseRegistryFile: Failing callback because all registry values couldn't be set.");
      }
    }
    LastError = v141;
    v135 = 0;
  }
  SetLastError(LastError);
  return v135;
}

```

## disassembly

```asm
0x18009ff54  push    rbp
0x18009ff56  push    rbx
0x18009ff57  push    rsi
0x18009ff58  push    rdi
0x18009ff59  push    r12
0x18009ff5b  push    r13
0x18009ff5d  push    r14
0x18009ff5f  push    r15
0x18009ff61  lea     rbp, [rsp-898h]
0x18009ff69  sub     rsp, 998h
0x18009ff70  mov     rax, cs:__security_cookie
0x18009ff77  xor     rax, rsp
0x18009ff7a  mov     [rbp+8D0h+var_50], rax
0x18009ff81  mov     r14, r9
0x18009ff84  mov     r12, r8
0x18009ff87  mov     r15, rdx
0x18009ff8a  mov     [rsp+9D0h+var_968], rdx
0x18009ff8f  mov     rsi, rcx
0x18009ff92  mov     [rbp+8D0h+var_8F0], rcx
0x18009ff96  mov     rax, [rbp+8D0h+arg_20]
0x18009ff9d  mov     [rbp+8D0h+var_8E8], rax
0x18009ffa1  mov     r13, [rbp+8D0h+arg_28]
0x18009ffa8  mov     rax, [rbp+8D0h+arg_30]
0x18009ffaf  mov     [rbp+8D0h+var_8D0], rax
0x18009ffb3  mov     rax, [rbp+8D0h+arg_38]
0x18009ffba  mov     qword ptr [rsp+9D0h+uBytes+4], rax
0x18009ffbf  xor     edi, edi
0x18009ffc1  mov     [rbp+8D0h+var_950], edi
0x18009ffc4  mov     [rsp+9D0h+var_960], edi
0x18009ffc8  mov     [rbp+8D0h+var_94C], edi
0x18009ffcb  mov     dword ptr [rsp+9D0h+uBytes], edi
0x18009ffcf  mov     [rbp+8D0h+var_940], rdi
0x18009ffd3  mov     [rbp+8D0h+var_938], rdi
0x18009ffd7  mov     [rbp+8D0h+hMem], rdi
0x18009ffdb  mov     [rsp+9D0h+var_970], di
0x18009ffe0  mov     [rbp+8D0h+TokenHandle], rdi
0x18009ffe4  call    cs:__imp_GetLastError
0x18009ffea  mov     ebx, eax
0x18009ffec  mov     [rsp+9D0h+var_96C], eax
0x18009fff0  mov     [rbp+8D0h+var_930], edi
0x18009fff3  mov     [rbp+8D0h+var_92C], edi
0x18009fff6  mov     [rbp+8D0h+var_850], di
0x18009fffd  xor     edx, edx; Val
0x18009ffff  mov     r8d, 7FEh; Size
0x1800a0005  lea     rcx, [rbp+8D0h+var_84E]; void *
0x1800a000c  call    memset_0
0x1800a0011  lea     ecx, [rdi+4]; unsigned int
0x1800a0014  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x1800a001a  jz      short loc_1800A005A
0x1800a001c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a0023  test    rax, rax
0x1800a0026  jz      short loc_1800A0039
0x1800a0028  mov     r8, r15
0x1800a002b  lea     rdx, aParseregistryf_0; "ParseRegistryFile: Entering with <%s>."
0x1800a0032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0037  jmp     short loc_1800A005A
0x1800a0039  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdi; void * g_lpDebugMsgContextInstance
0x1800a0040  jz      short loc_1800A005A
0x1800a0042  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a0049  jz      short loc_1800A005A
0x1800a004b  mov     r8, r15
0x1800a004e  lea     rdx, aParseregistryf_0; "ParseRegistryFile: Entering with <%s>."
0x1800a0055  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a005a  cmp     [rbp+8D0h+arg_40], edi
0x1800a0060  jnz     loc_1800A0378
0x1800a0066  mov     [rbp+8D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800a006e  test    rsi, rsi
0x1800a0071  jz      loc_1800A021E
0x1800a0077  test    byte ptr [rsi], 1
0x1800a007a  jnz     loc_1800A021E
0x1800a0080  cmp     [rsi+48h], rdi
0x1800a0084  jnz     loc_1800A0208
0x1800a008a  mov     rcx, [rsi+8]; void *
0x1800a008e  call    ?GetSidString@@YAPEAGPEAX@Z; GetSidString(void *)
0x1800a0093  mov     [rsi+48h], rax
0x1800a0097  test    rax, rax
0x1800a009a  jnz     loc_1800A0208
0x1800a00a0  call    cs:__imp_GetLastError
0x1800a00a6  mov     ebx, eax
0x1800a00a8  mov     [rsp+9D0h+var_96C], eax
0x1800a00ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl(void)'::`2'::impl
0x1800a00b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(void)
0x1800a00b8  xor     r12d, r12d
0x1800a00bb  test    al, al
0x1800a00bd  jz      loc_1800A01A6
0x1800a00c3  lea     r8, aErrorDuringReg_13; "Error during registry file parsing: Fai"...
0x1800a00ca  mov     edx, 400h; unsigned __int64
0x1800a00cf  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x1800a00d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a00db  lea     rdi, aS_1; "%s"
0x1800a00e2  test    eax, eax
0x1800a00e4  jns     short loc_1800A013E
0x1800a00e6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a00ed  jz      loc_1800A1BCD
0x1800a00f3  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a00fa  test    rsi, rsi
0x1800a00fd  jz      short loc_1800A0118
0x1800a00ff  lea     r8, aParseregistryf_11; "ParseRegistryFile: String too large to "...
0x1800a0106  mov     rdx, rdi
0x1800a0109  lea     ecx, [r12+2]
0x1800a010e  mov     rax, rsi
0x1800a0111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0116  jmp     short loc_1800A013E
0x1800a0118  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a011f  jz      short loc_1800A013E
0x1800a0121  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a0128  jz      short loc_1800A013E
0x1800a012a  lea     r8, aParseregistryf_11; "ParseRegistryFile: String too large to "...
0x1800a0131  mov     rdx, rdi; unsigned __int16 *
0x1800a0134  mov     ecx, 2; unsigned int
0x1800a0139  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a013e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a0145  jz      loc_1800A1BCD
0x1800a014b  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a0152  test    rsi, rsi
0x1800a0155  jz      short loc_1800A0173
0x1800a0157  mov     ecx, 2
0x1800a015c  mov     rdx, rdi
0x1800a015f  lea     r8, [rbp+8D0h+var_850]
0x1800a0166  mov     rax, rsi
0x1800a0169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a016e  jmp     loc_1800A1BCD
0x1800a0173  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a017a  jz      loc_1800A1BCD
0x1800a0180  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a0187  jz      loc_1800A1BCD
0x1800a018d  mov     ecx, 2; unsigned int
0x1800a0192  mov     rdx, rdi; unsigned __int16 *
0x1800a0195  lea     r8, [rbp+8D0h+var_850]
0x1800a019c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a01a1  jmp     loc_1800A1BCD
0x1800a01a6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a01ad  jz      loc_1800A1BCD
0x1800a01b3  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a01ba  test    rsi, rsi
0x1800a01bd  jz      short loc_1800A01D8
0x1800a01bf  lea     rdx, aParseregistryf_31; "ParseRegistryFile: Failed to get User S"...
0x1800a01c6  mov     ecx, 2
0x1800a01cb  mov     rax, rsi
0x1800a01ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01d3  jmp     loc_1800A1BCD
0x1800a01d8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a01df  jz      loc_1800A1BCD
0x1800a01e5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a01ec  jz      loc_1800A1BCD
0x1800a01f2  lea     rdx, aParseregistryf_31; "ParseRegistryFile: Failed to get User S"...
0x1800a01f9  mov     ecx, 2; unsigned int
0x1800a01fe  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a0203  jmp     loc_1800A1BCD
0x1800a0208  test    byte ptr [rsi], 1
0x1800a020b  jnz     short loc_1800A021E
0x1800a020d  mov     rcx, [rsi+48h]; unsigned __int16 *
0x1800a0211  call    ?ShouldUserImpersonated@@YAHPEBG@Z; ShouldUserImpersonated(ushort const *)
0x1800a0216  test    eax, eax
0x1800a0218  jz      loc_1800A0378
0x1800a021e  mov     edi, 1
0x1800a0223  lea     rdx, [rbp+8D0h+TokenHandle]; TokenHandle
0x1800a0227  mov     rcx, [rsi+8]; hToken
0x1800a022b  call    ?ImpersonateUser@@YAHPEAXPEAPEAX@Z; ImpersonateUser(void *,void * *)
0x1800a0230  test    eax, eax
0x1800a0232  jnz     loc_1800A0378
0x1800a0238  call    cs:__imp_GetLastError
0x1800a023e  mov     ebx, eax
0x1800a0240  mov     [rsp+9D0h+var_96C], eax
0x1800a0244  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl(void)'::`2'::impl
0x1800a024b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(void)
0x1800a0250  xor     r12d, r12d
0x1800a0253  test    al, al
0x1800a0255  jz      loc_1800A0328
0x1800a025b  lea     r8, aErrorDuringReg_20; "Error during registry file parsing: Fai"...
0x1800a0262  mov     edx, 400h; unsigned __int64
0x1800a0267  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x1800a026e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0273  lea     rdi, aS_1; "%s"
0x1800a027a  test    eax, eax
0x1800a027c  jns     short loc_1800A02DF
0x1800a027e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a0285  jz      loc_1800A1BCD
0x1800a028b  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a0292  test    rsi, rsi
0x1800a0295  jz      short loc_1800A02B3
0x1800a0297  lea     r13d, [r12+2]
0x1800a029c  mov     rdx, rdi
0x1800a029f  lea     r8, aParseregistryf_11; "ParseRegistryFile: String too large to "...
0x1800a02a6  mov     ecx, r13d
0x1800a02a9  mov     rax, rsi
0x1800a02ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a02b1  jmp     short loc_1800A02E5
0x1800a02b3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a02ba  jz      short loc_1800A02DF
0x1800a02bc  mov     r13d, 2
0x1800a02c2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a02c9  jz      short loc_1800A02E5
0x1800a02cb  lea     r8, aParseregistryf_11; "ParseRegistryFile: String too large to "...
0x1800a02d2  mov     rdx, rdi; unsigned __int16 *
0x1800a02d5  mov     ecx, r13d; unsigned int
0x1800a02d8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a02dd  jmp     short loc_1800A02E5
0x1800a02df  mov     r13d, 2
0x1800a02e5  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a02ec  jz      loc_1800A1BCD
0x1800a02f2  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a02f9  test    rsi, rsi
0x1800a02fc  jz      short loc_1800A0306
0x1800a02fe  mov     ecx, r13d
0x1800a0301  jmp     loc_1800A015C
0x1800a0306  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a030d  jz      loc_1800A1BCD
0x1800a0313  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a031a  jz      loc_1800A1BCD
0x1800a0320  mov     ecx, r13d
0x1800a0323  jmp     loc_1800A0192
0x1800a0328  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a032f  jz      loc_1800A1BCD
0x1800a0335  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a033c  test    rsi, rsi
0x1800a033f  jz      short loc_1800A0352
0x1800a0341  lea     rdx, aParseregistryf_24; "ParseRegistryFile: Failed to impersonat"...
0x1800a0348  mov     ecx, 2
0x1800a034d  jmp     loc_1800A01CB
0x1800a0352  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a0359  jz      loc_1800A1BCD
0x1800a035f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a0366  jz      loc_1800A1BCD
0x1800a036c  lea     rdx, aParseregistryf_24; "ParseRegistryFile: Failed to impersonat"...
0x1800a0373  jmp     loc_1800A01F9
0x1800a0378  mov     [rsp+9D0h+hTemplateFile], 0; hTemplateFile
0x1800a0381  mov     [rsp+9D0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800a0389  mov     [rsp+9D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a0391  xor     r9d, r9d; lpSecurityAttributes
0x1800a0394  mov     edx, 80000000h; dwDesiredAccess
0x1800a0399  lea     r8d, [r9+1]; dwShareMode
0x1800a039d  mov     rcx, r15; lpFileName
0x1800a03a0  call    cs:__imp_CreateFileW
0x1800a03a6  mov     rsi, rax
0x1800a03a9  mov     [rbp+8D0h+hObject], rax
0x1800a03ad  test    edi, edi
0x1800a03af  jz      short loc_1800A03BA
0x1800a03b1  lea     rcx, [rbp+8D0h+TokenHandle]; void **
0x1800a03b5  call    ?RevertToUser@@YAHPEAPEAX@Z; RevertToUser(void * *)
0x1800a03ba  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800a03be  jnz     loc_1800A0AD2
0x1800a03c4  call    cs:__imp_GetLastError
0x1800a03ca  lea     r13d, [rsi+3]
0x1800a03ce  cmp     eax, r13d
0x1800a03d1  jz      loc_1800A04AD
0x1800a03d7  call    cs:__imp_GetLastError
0x1800a03dd  cmp     eax, 3
0x1800a03e0  jz      loc_1800A04AD
0x1800a03e6  call    cs:__imp_GetLastError
0x1800a03ec  mov     ebx, eax
0x1800a03ee  mov     [rsp+9D0h+var_96C], eax
0x1800a03f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::GetImpl(void)'::`2'::impl
0x1800a03f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegPolEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegPolEvent>::__private_IsEnabled(void)
0x1800a03fe  xor     r12d, r12d
0x1800a0401  test    al, al
0x1800a0403  jz      short loc_1800A043D
0x1800a0405  call    cs:__imp_GetLastError
0x1800a040b  mov     r9d, eax
0x1800a040e  lea     r8, aErrorDuringReg; "Error during registry file parsing: Cre"...
0x1800a0415  mov     edx, 400h; unsigned __int64
0x1800a041a  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x1800a0421  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0426  jmp     loc_1800A0563
0x1800a042b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a0432  jz      loc_1800A02E5
0x1800a0438  jmp     loc_1800A02C2
0x1800a043d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a0444  jz      loc_1800A1BCD
0x1800a044a  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a0451  test    rsi, rsi
0x1800a0454  jz      short loc_1800A0476
0x1800a0456  call    cs:__imp_GetLastError
0x1800a045c  mov     r8d, eax
0x1800a045f  lea     rdx, aParseregistryf_13; "ParseRegistryFile: CreateFile failed wi"...
0x1800a0466  mov     ecx, r13d
0x1800a0469  mov     rax, rsi
0x1800a046c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0471  jmp     loc_1800A1BCD
0x1800a0476  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a047d  jz      loc_1800A1BCD
0x1800a0483  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a048a  jz      loc_1800A1BCD
0x1800a0490  call    cs:__imp_GetLastError
0x1800a0496  mov     r8d, eax
0x1800a0499  lea     rdx, aParseregistryf_13; "ParseRegistryFile: CreateFile failed wi"...
0x1800a04a0  mov     ecx, r13d; unsigned int
0x1800a04a3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a04a8  jmp     loc_1800A1BCD
0x1800a04ad  xor     r12d, r12d
0x1800a04b0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a04b7  jz      short loc_1800A0500
0x1800a04b9  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a04c0  test    rsi, rsi
0x1800a04c3  jz      short loc_1800A04DC
0x1800a04c5  mov     r8, r15
0x1800a04c8  lea     rdx, aParseregistryf_8; "ParseRegistryFile: (%s) not found."
0x1800a04cf  mov     ecx, r13d
0x1800a04d2  mov     rax, rsi
0x1800a04d5  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
