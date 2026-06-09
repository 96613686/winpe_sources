# CEditSessionObject::_GetTextAndAttribute(ulong,ITfRange *,CWCompString &,CWCompAttribute &,CWCompClause &,CWCompTfGuidAtom &,CWCompString &,CWCompClause &,CWCompString &,CWCompClause &,CWCompString &,CWCompClause &,int)

- ea: `0x180013a70`
- end: `0x180015318`
- name: `?_GetTextAndAttribute@CEditSessionObject@@IEAAJKPEAUITfRange@@AEAVCWCompString@@AEAVCWCompAttribute@@AEAVCWCompClause@@AEAVCWCompTfGuidAtom@@131313H@Z`
- size: `6312`
- prototype: `__int64 __fastcall(CEditSessionObject *__hidden this, unsigned int, struct ITfRange *, struct CWCompString *, struct CWCompAttribute *, struct CWCompClause *, struct CWCompTfGuidAtom *, struct CWCompString *, struct CWCompClause *, struct CWCompString *, struct CWCompClause *, struct CWCompString *, struct CWCompClause *, int)`
- caller_count: `4`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180012c64`
- `0x1800132a8`
- `0x180013700`
- `0x18006881c`

## callees

- `0x180013a70`
- `0x180015320`
- `0x180015850`
- `0x180018640`
- `0x18001a460`
- `0x18001cc80`
- `0x18001e2c0`
- `0x18003a518`
- `0x18003a564`
- `0x18003a5fc`
- `0x18003a930`
- `0x18003aa08`
- `0x18003aad8`
- `0x18003c7a8`
- `0x18003c9cc`
- `0x1800454c0`
- `0x180045d84`
- `0x180046748`
- `0x180073ca4`
- `0x18007e840`
- `0x18009eac6`
- `0x18009ead2`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001415e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001415e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015292`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014079`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014079`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180015140`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180015197`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180015140`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180015197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013e2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013eb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800140b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015170`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013e2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013eb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800140b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015170`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180014beb`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180014bff`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180014beb`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180014bff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001414c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800151ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001414c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800151ae`
- `USER32!SendMessageW` at `0x180013d7a`
- `USER32!SendMessageW` at `0x180014f51`
- `USER32!SendMessageW` at `0x180013d7a`
- `USER32!SendMessageW` at `0x180014f51`
- `USER32!IsWindow` at `0x180013d4a`
- `USER32!IsWindow` at `0x180013d4a`
- `OLEAUT32!__imp_SysStringLen` at `0x180014b72`
- `OLEAUT32!__imp_SysStringLen` at `0x180014b72`
- `OLEAUT32!__imp_VariantClear` at `0x180014d79`
- `OLEAUT32!__imp_VariantClear` at `0x180014d79`
- `IMM32!ImmGetDefaultIMEWnd` at `0x180013d3e`
- `IMM32!ImmGetDefaultIMEWnd` at `0x180013d3e`

## pseudocode

```c

```
