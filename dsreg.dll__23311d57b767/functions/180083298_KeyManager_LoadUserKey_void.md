# KeyManager::LoadUserKey(void)

- ea: `0x180083298`
- end: `0x1800834ec`
- name: `?LoadUserKey@KeyManager@@QEAAJXZ`
- size: `596`
- prototype: `__int64 __fastcall(KeyManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180080bc4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180017bb0`
- `0x180034cd0`
- `0x18003a7a0`
- `0x180082c18`
- `0x180083004`
- `0x180083298`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800834d9`
- `cryptngc!NgcFreeEnumState` at `0x1800834c6`
- `cryptngc!NgcFreeEnumState` at `0x1800834c6`
- `cryptngc!NgcEnumUserIdKeys` at `0x180083335`
- `cryptngc!NgcEnumUserIdKeys` at `0x180083335`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800833fc`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800833fc`

## string_xrefs

- `0x18008334a`: `%s: User ID key is not found. Return success. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x1800832f4`: `KeyManager::GetUserSid`
- `0x1800833e1`: `%s: NgcEnumUserIdKeys returns NULL pKeyInfo. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, HRESULT: 0x%08x.`
- `0x1800833ad`: `%s: Cannot find user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`

## pseudocode

```c

```
