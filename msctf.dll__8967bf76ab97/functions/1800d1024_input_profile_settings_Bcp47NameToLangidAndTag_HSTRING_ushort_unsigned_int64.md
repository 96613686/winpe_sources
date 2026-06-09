# input_profile_settings::Bcp47NameToLangidAndTag(HSTRING__ *,ushort *,unsigned __int64 *)

- ea: `0x1800d1024`
- end: `0x1800d1123`
- name: `?Bcp47NameToLangidAndTag@input_profile_settings@@YAJPEAUHSTRING__@@PEAGPEA_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800859b4`

## callees

- `0x180011000`
- `0x1800b8440`
- `0x1800b847c`
- `0x1800d1024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d10c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d10c9`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800d10a0`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800d10a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1095`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x1800d10ec`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x1800d10ec`
- `Bcp47Langs!LcidFromBcp47` at `0x1800d1067`
- `Bcp47Langs!LcidFromBcp47` at `0x1800d1067`

## pseudocode

```c

```
