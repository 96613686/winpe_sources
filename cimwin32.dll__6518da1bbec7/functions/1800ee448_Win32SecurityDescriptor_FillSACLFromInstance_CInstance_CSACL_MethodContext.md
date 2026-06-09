# Win32SecurityDescriptor::FillSACLFromInstance(CInstance *,CSACL &,MethodContext *)

- ea: `0x1800ee448`
- end: `0x1800ee933`
- name: `?FillSACLFromInstance@Win32SecurityDescriptor@@QEAAKPEAVCInstance@@AEAVCSACL@@PEAVMethodContext@@@Z`
- size: `1259`
- prototype: `unsigned int(Win32SecurityDescriptor *__hidden this, struct CInstance *, struct CSACL *, struct MethodContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800eeb7c`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x180032fd8`
- `0x18003d7b0`
- `0x18005b394`
- `0x18007eefc`
- `0x1800ee448`
- `0x1800eeabc`
- `0x1800f7154`
- `0x1800f92c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ee7a7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ee81d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ee7a7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ee81d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ee6a1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ee6b0`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ee6a1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ee6b0`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ee74e`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ee7c4`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ee74e`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800ee7c4`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ee79b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ee811`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ee79b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800ee811`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800ee75c`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800ee7d2`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800ee75c`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800ee7d2`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ee604`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800ee604`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6cb`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6e5`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6ff`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6cb`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6e5`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800ee6ff`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ee4c6`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ee4c6`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ee5cf`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800ee5cf`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800ee633`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x1800ee633`
- `framedynos!?GetClassObjectInterface@CInstance@@QEAAPEAUIWbemClassObject@@XZ` at `0x1800ee474`
- `framedynos!?GetClassObjectInterface@CInstance@@QEAAPEAUIWbemClassObject@@XZ` at `0x1800ee474`
- `framedynos!??0CInstance@@QEAA@PEAUIWbemClassObject@@PEAVMethodContext@@@Z` at `0x1800ee59f`
- `framedynos!??0CInstance@@QEAA@PEAUIWbemClassObject@@PEAVMethodContext@@@Z` at `0x1800ee59f`
- `framedynos!??1CInstance@@UEAA@XZ` at `0x1800ee8e2`
- `framedynos!??1CInstance@@UEAA@XZ` at `0x1800ee8e2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee4ef`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee89f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee8ae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee4ef`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee89f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ee8ae`
- `OLEAUT32!__imp_VariantClear` at `0x1800ee906`
- `OLEAUT32!__imp_VariantClear` at `0x1800ee906`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800ee534`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800ee534`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800ee51a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800ee51a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800ee57b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800ee57b`

## string_xrefs

- `0x1800ee6f0`: `AccessMask`

## pseudocode

```c

```
