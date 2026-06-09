# PerformHash

- ea: `0x1801f93e4`
- end: `0x1801f9663`
- name: `PerformHash`
- size: `639`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801fad90`

## callees

- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800b550c`
- `0x1800eb920`
- `0x1801f93e4`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1801f95f3`
- `bcrypt!BCryptFinishHash` at `0x1801f95f3`
- `bcrypt!BCryptHashData` at `0x1801f95ad`
- `bcrypt!BCryptHashData` at `0x1801f95ad`
- `bcrypt!BCryptCreateHash` at `0x1801f953f`
- `bcrypt!BCryptCreateHash` at `0x1801f953f`
- `bcrypt!BCryptGetProperty` at `0x1801f9444`
- `bcrypt!BCryptGetProperty` at `0x1801f9444`

## string_xrefs

- `0x1801f956d`: `::BCryptCreateHash( Alg, Hash.GetInitPointer(), nullptr, 0, nullptr, 0, 0)`

## pseudocode

```c

```
