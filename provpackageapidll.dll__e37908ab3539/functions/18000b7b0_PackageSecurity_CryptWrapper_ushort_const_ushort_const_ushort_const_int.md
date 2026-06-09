# PackageSecurity::CryptWrapper(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000b7b0`
- end: `0x18000ce17`
- name: `?CryptWrapper@PackageSecurity@@AEAAJPEBG00H@Z`
- size: `5735`
- prototype: `__int64 __fastcall(PackageSecurity *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ce20`
- `0x18000ce90`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000b7b0`
- `0x180018440`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000b81b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000b81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c704`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c81b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c704`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c81b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd30`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000be68`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000be68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bd43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000be50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bd43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000be50`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c2ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c64d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000cbe8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c2ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c64d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000cbe8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c389`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c46d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000cc59`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c389`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c46d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000cc59`
- `bcrypt!BCryptDecrypt` at `0x18000c5e9`
- `bcrypt!BCryptDecrypt` at `0x18000c5e9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000b88a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ba0e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c1d0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000b88a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ba0e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c1d0`
- `bcrypt!BCryptGenRandom` at `0x18000c24d`
- `bcrypt!BCryptGenRandom` at `0x18000c24d`
- `bcrypt!BCryptFinishHash` at `0x18000c692`
- `bcrypt!BCryptFinishHash` at `0x18000c692`
- `bcrypt!BCryptGetProperty` at `0x18000baa6`
- `bcrypt!BCryptGetProperty` at `0x18000bfbf`
- `bcrypt!BCryptGetProperty` at `0x18000baa6`
- `bcrypt!BCryptGetProperty` at `0x18000bfbf`
- `bcrypt!BCryptDestroyHash` at `0x18000bc17`
- `bcrypt!BCryptDestroyHash` at `0x18000bc9c`
- `bcrypt!BCryptDestroyHash` at `0x18000bde0`
- `bcrypt!BCryptDestroyHash` at `0x18000bf39`
- `bcrypt!BCryptDestroyHash` at `0x18000c055`
- `bcrypt!BCryptDestroyHash` at `0x18000c14f`
- `bcrypt!BCryptDestroyHash` at `0x18000c72b`
- `bcrypt!BCryptDestroyHash` at `0x18000c851`
- `bcrypt!BCryptDestroyHash` at `0x18000c921`
- `bcrypt!BCryptDestroyHash` at `0x18000ca02`
- `bcrypt!BCryptDestroyHash` at `0x18000cb73`
- `bcrypt!BCryptDestroyHash` at `0x18000cd57`
- `bcrypt!BCryptDestroyHash` at `0x18000bc17`
- `bcrypt!BCryptDestroyHash` at `0x18000bc9c`
- `bcrypt!BCryptDestroyHash` at `0x18000bde0`
- `bcrypt!BCryptDestroyHash` at `0x18000bf39`
- `bcrypt!BCryptDestroyHash` at `0x18000c055`
- `bcrypt!BCryptDestroyHash` at `0x18000c14f`
- `bcrypt!BCryptDestroyHash` at `0x18000c72b`
- `bcrypt!BCryptDestroyHash` at `0x18000c851`
- `bcrypt!BCryptDestroyHash` at `0x18000c921`
- `bcrypt!BCryptDestroyHash` at `0x18000ca02`
- `bcrypt!BCryptDestroyHash` at `0x18000cb73`
- `bcrypt!BCryptDestroyHash` at `0x18000cd57`
- `bcrypt!BCryptHashData` at `0x18000c540`
- `bcrypt!BCryptHashData` at `0x18000c593`
- `bcrypt!BCryptHashData` at `0x18000c540`
- `bcrypt!BCryptHashData` at `0x18000c593`
- `bcrypt!BCryptSetProperty` at `0x18000b91e`
- `bcrypt!BCryptSetProperty` at `0x18000b91e`
- `bcrypt!BCryptCreateHash` at `0x18000bbb4`
- `bcrypt!BCryptCreateHash` at `0x18000bbb4`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b98b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b98b`
- `bcrypt!BCryptDestroyKey` at `0x18000b9ea`
- `bcrypt!BCryptDestroyKey` at `0x18000bb77`
- `bcrypt!BCryptDestroyKey` at `0x18000be13`
- `bcrypt!BCryptDestroyKey` at `0x18000bf6c`
- `bcrypt!BCryptDestroyKey` at `0x18000c088`
- `bcrypt!BCryptDestroyKey` at `0x18000c182`
- `bcrypt!BCryptDestroyKey` at `0x18000c75e`
- `bcrypt!BCryptDestroyKey` at `0x18000c884`
- `bcrypt!BCryptDestroyKey` at `0x18000c954`
- `bcrypt!BCryptDestroyKey` at `0x18000ca35`
- `bcrypt!BCryptDestroyKey` at `0x18000cba6`
- `bcrypt!BCryptDestroyKey` at `0x18000cd8a`
- `bcrypt!BCryptDestroyKey` at `0x18000b9ea`
- `bcrypt!BCryptDestroyKey` at `0x18000bb77`
- `bcrypt!BCryptDestroyKey` at `0x18000be13`
- `bcrypt!BCryptDestroyKey` at `0x18000bf6c`
- `bcrypt!BCryptDestroyKey` at `0x18000c088`
- `bcrypt!BCryptDestroyKey` at `0x18000c182`
- `bcrypt!BCryptDestroyKey` at `0x18000c75e`
- `bcrypt!BCryptDestroyKey` at `0x18000c884`
- `bcrypt!BCryptDestroyKey` at `0x18000c954`
- `bcrypt!BCryptDestroyKey` at `0x18000ca35`
- `bcrypt!BCryptDestroyKey` at `0x18000cba6`
- `bcrypt!BCryptDestroyKey` at `0x18000cd8a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b8f5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ba6f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bb63`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bdff`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bf58`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bf83`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c074`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c09f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c16e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c199`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c228`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c33f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c364`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c74a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c775`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c870`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c940`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c96b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ca21`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ca4c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000cb92`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000cbbd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000cd76`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000cda1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b8f5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ba6f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bb63`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bdff`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bf58`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000bf83`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c074`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c09f`

## string_xrefs

- `0x18000b844`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000b8a7`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000b936`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000b9a3`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000ba26`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000babe`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bb1f`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bbd0`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bc57`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bcd8`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bd7c`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000beb0`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000bfdf`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c0d9`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c1ec`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c269`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c2f0`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c3c3`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c560`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c6b2`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c79f`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c7d8`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c8a8`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000c989`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000ca78`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000caad`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000cafa`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000cc2a`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000cc93`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000cce2`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000cdbc`: `onecore\base\ntsetup\provpackageapi\lib\packagesecurity.cpp`
- `0x18000b84b`: `PackageSecurity::CryptWrapper`
- `0x18000b8ae`: `PackageSecurity::CryptWrapper`
- `0x18000b93d`: `PackageSecurity::CryptWrapper`
- `0x18000b9aa`: `PackageSecurity::CryptWrapper`
- `0x18000ba2d`: `PackageSecurity::CryptWrapper`
- `0x18000bac5`: `PackageSecurity::CryptWrapper`
- `0x18000bb26`: `PackageSecurity::CryptWrapper`
- `0x18000bbd7`: `PackageSecurity::CryptWrapper`
- `0x18000bc5e`: `PackageSecurity::CryptWrapper`
- `0x18000bcdf`: `PackageSecurity::CryptWrapper`
- `0x18000bd83`: `PackageSecurity::CryptWrapper`
- `0x18000beb7`: `PackageSecurity::CryptWrapper`
- `0x18000bfe6`: `PackageSecurity::CryptWrapper`
- `0x18000c0e0`: `PackageSecurity::CryptWrapper`
- `0x18000c1f3`: `PackageSecurity::CryptWrapper`
- `0x18000c270`: `PackageSecurity::CryptWrapper`
- `0x18000c2f7`: `PackageSecurity::CryptWrapper`
- `0x18000c3ca`: `PackageSecurity::CryptWrapper`
- `0x18000c567`: `PackageSecurity::CryptWrapper`
- `0x18000c6b9`: `PackageSecurity::CryptWrapper`
- `0x18000c7a6`: `PackageSecurity::CryptWrapper`
- `0x18000c7df`: `PackageSecurity::CryptWrapper`
- `0x18000c8af`: `PackageSecurity::CryptWrapper`
- `0x18000c990`: `PackageSecurity::CryptWrapper`
- `0x18000ca7f`: `PackageSecurity::CryptWrapper`
- `0x18000cab4`: `PackageSecurity::CryptWrapper`
- `0x18000cb01`: `PackageSecurity::CryptWrapper`
- `0x18000cc31`: `PackageSecurity::CryptWrapper`
- `0x18000cc9a`: `PackageSecurity::CryptWrapper`
- `0x18000cce9`: `PackageSecurity::CryptWrapper`
- `0x18000cdc3`: `PackageSecurity::CryptWrapper`
- `0x18000b8ca`: `    Failed to open AES algorithm provider`
- `0x18000ba49`: `    Failed to open SHA256 algorithm provider`
- `0x18000bbf3`: `    Failed to create hash`
- `0x18000bd99`: `    Failed to create input file`
- `0x18000c209`: `    Failed to open RNG algorithm provider`
- `0x18000c30d`: `    Failed to write IV`
- `0x18000c3e0`: `    Failed to read IV`
- `0x18000c7bc`: `    Failed to read chunk`
- `0x18000c57d`: `    Failed to compute chunk hash`
- `0x18000ca95`: `    Failed to write chunk`
- `0x18000cc47`: `    Failed to write hash`
- `0x18000ccb0`: `    Failed to read hash`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CryptWrapper(
        PackageSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  BCRYPT_ALG_HANDLE v13; // rcx
  bool v14; // cc
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS Property; // eax
  void *v19; // r15
  BCRYPT_ALG_HANDLE v20; // rcx
  bool v21; // cc
  NTSTATUS v22; // eax
  const struct std::nothrow_t *v23; // rdx
  void *v24; // r12
  const struct std::nothrow_t *v25; // rdx
  UCHAR *v26; // rdi
  const struct std::nothrow_t *v27; // rdx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int v30; // eax
  const struct std::nothrow_t *v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  char *v34; // rdi
  signed int v35; // eax
  bool v36; // sf
  signed int v37; // eax
  signed int v38; // eax
  const struct std::nothrow_t *v39; // rdx
  unsigned int v40; // r14d
  const struct std::nothrow_t *v41; // rdx
  const struct std::nothrow_t *v42; // rdx
  signed int v44; // eax
  const struct std::nothrow_t *v45; // rdx
  const struct std::nothrow_t *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  UCHAR *v48; // rax
  const struct std::nothrow_t *v49; // rdx
  const struct std::nothrow_t *v50; // rdx
  const struct std::nothrow_t *v51; // rdx
  signed int v52; // eax
  const struct std::nothrow_t *v53; // rdx
  signed int v54; // eax
  signed int v55; // eax
  bool v56; // sf
  signed int v57; // eax
  signed int v58; // eax
  const struct std::nothrow_t *v59; // rdx
  __int64 i; // rax
  signed int v61; // eax
  bool v62; // sf
  signed int v63; // eax
  signed int v64; // eax
  signed int v65; // eax
  bool v66; // sf
  size_t v67; // r8
  signed int v68; // eax
  signed int v69; // eax
  const struct std::nothrow_t *v70; // rdx
  signed int v71; // eax
  signed int v72; // eax
  size_t v73; // r8
  signed int v74; // eax
  bool v75; // sf
  int v76; // eax
  const struct std::nothrow_t *v77; // rdx
  const struct std::nothrow_t *v78; // rdx
  const struct std::nothrow_t *v79; // rdx
  const struct std::nothrow_t *v80; // rdx
  signed int v81; // eax
  const struct std::nothrow_t *v82; // rdx
  const struct std::nothrow_t *v83; // rdx
  const struct std::nothrow_t *v84; // rdx
  const struct std::nothrow_t *v85; // rdx
  BCRYPT_ALG_HANDLE v86; // rcx
  bool v87; // cc
  const struct std::nothrow_t *v88; // rdx
  const struct std::nothrow_t *v89; // rdx
  const struct std::nothrow_t *v90; // rdx
  const struct std::nothrow_t *v91; // rdx
  const struct std::nothrow_t *v92; // rdx
  const struct std::nothrow_t *v93; // rdx
  const struct std::nothrow_t *v94; // rdx
  signed int v95; // eax
  unsigned int v96; // r13d
  const struct std::nothrow_t *v97; // rdx
  const struct std::nothrow_t *v98; // rdx
  const struct std::nothrow_t *v99; // rdx
  const struct std::nothrow_t *v100; // rdx
  const struct std::nothrow_t *v101; // rdx
  signed int v102; // eax
  bool v103; // sf
  signed int v104; // eax
  signed int v105; // eax
  bool v106; // sf
  signed int v107; // eax
  const struct std::nothrow_t *v108; // rdx
  const struct std::nothrow_t *v109; // rdx
  const struct std::nothrow_t *v110; // rdx
  ULONG dwFlags[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsa[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsb[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsc[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsd[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagse[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsf[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsg[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsh[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsi[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsj[2]; // [rsp+20h] [rbp-B1h]
  ULONG dwFlagsk[2]; // [rsp+20h] [rbp-B1h]
  __int64 cbSecret; // [rsp+28h] [rbp-A9h]
  __int64 cbSecreta; // [rsp+28h] [rbp-A9h]
  __int64 cbSecretb; // [rsp+28h] [rbp-A9h]
  __int64 cbSecretc; // [rsp+28h] [rbp-A9h]
  __int64 cbSecretd; // [rsp+28h] [rbp-A9h]
  __int64 cbSecrete; // [rsp+28h] [rbp-A9h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-81h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-79h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+60h] [rbp-71h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-69h] BYREF
  PUCHAR pbInput; // [rsp+70h] [rbp-61h]
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-59h] BYREF
  UCHAR v135[4]; // [rsp+7Ch] [rbp-55h] BYREF
  PUCHAR pbBuffer; // [rsp+80h] [rbp-51h]
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+8Ch] [rbp-45h] BYREF
  BCRYPT_ALG_HANDLE v139; // [rsp+90h] [rbp-41h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp-39h] BYREF
  int v141; // [rsp+9Ch] [rbp-35h]
  LARGE_INTEGER v142; // [rsp+A0h] [rbp-31h]
  LARGE_INTEGER FileSize; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v144; // [rsp+B0h] [rbp-21h]
  void *v145; // [rsp+B8h] [rbp-19h]
  void *v146; // [rsp+C0h] [rbp-11h]
  HANDLE v147; // [rsp+C8h] [rbp-9h]
  char *v148; // [rsp+D0h] [rbp-1h]
  UCHAR pbSecret[16]; // [rsp+D8h] [rbp+7h] BYREF

  v8 = -1;
  do
    ++v8;
  while ( a4[v8] );
  if ( (unsigned __int64)(v8 - 1) > 0xF )
  {
    v11 = -2147024809;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      47,
      -2147024809);
    ProvPackageLog(3, L"    Invalid password length");
    return v11;
  }
  *(_OWORD *)pbSecret = 0;
  v9 = _o_wcstombs(pbSecret, a4, 16);
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  if ( v9 != v10 )
  {
    v11 = -2147024809;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      62,
      -2147024809);
    ProvPackageLog(3, L"    Invalid password byte length");
    return v11;
  }
  phAlgorithm = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  v11 = v12 | 0x10000000;
  if ( v12 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      73,
      v12 | 0x10000000);
    ProvPackageLog(3, L"    Failed to open AES algorithm provider");
LABEL_10:
    v13 = phAlgorithm;
    v14 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_11:
    if ( v14 )
      BCryptCloseAlgorithmProvider(v13, 0);
    return v11;
  }
  v15 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  v11 = v15 | 0x10000000;
  if ( v15 < 0 )
  {
    dwFlags[0] = 78;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlags,
      v15 | 0x10000000);
    ProvPackageLog(3, L"    Failed to set chaining property");
    goto LABEL_10;
  }
  phKey = 0;
  v16 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, 0x10u, 0);
  v11 = v16 | 0x10000000;
  if ( v16 < 0 )
  {
    LODWORD(cbSecret) = v16 | 0x10000000;
    dwFlagsa[0] = 83;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsa,
      cbSecret);
    ProvPackageLog(3, L"    Failed to generate key");
LABEL_17:
    if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyKey(phKey);
    goto LABEL_10;
  }
  hAlgorithm = 0;
  v17 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"SHA256", 0, 8u);
  v11 = v17 | 0x10000000;
  if ( v17 < 0 )
  {
    LODWORD(cbSecret) = v17 | 0x10000000;
    dwFlagsa[0] = 89;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsa,
      cbSecret);
    ProvPackageLog(3, L"    Failed to open SHA256 algorithm provider");
    goto LABEL_22;
  }
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  v11 = Property | 0x10000000;
  if ( Property < 0 )
  {
    LODWORD(cbSecreta) = Property | 0x10000000;
    dwFlagsb[0] = 97;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsb,
      cbSecreta);
    ProvPackageLog(3, L"    Failed to get hash length property");
LABEL_22:
    if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    goto LABEL_17;
  }
  v19 = operator new[](*(unsigned int *)pbOutput, (const struct std::nothrow_t *)&std::nothrow);
  v145 = v19;
  if ( !v19 )
  {
    LODWORD(cbSecreta) = -2147024882;
    dwFlagsb[0] = 101;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsb,
      cbSecreta);
    ProvPackageLog(3, L"    Failed to allocate spHmac.get()");
LABEL_29:
    if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyKey(phKey);
    v20 = phAlgorithm;
    v21 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_105:
    if ( v21 )
      BCryptCloseAlgorithmProvider(v20, 0);
    return 2147942414LL;
  }
  phHash = 0;
  v22 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, pbSecret, 0x10u, 0);
  v11 = v22 | 0x10000000;
  if ( v22 < 0 )
  {
    LODWORD(cbSecretb) = v22 | 0x10000000;
    dwFlagsc[0] = 107;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsc,
      cbSecretb);
    ProvPackageLog(3, L"    Failed to create hash");
    if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyHash(phHash);
    operator delete(v19, v23);
    goto LABEL_22;
  }
  v24 = operator new[](0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v146 = v24;
  if ( !v24 )
  {
    LODWORD(cbSecretb) = -2147024882;
    dwFlagsc[0] = 111;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsc,
      cbSecretb);
    ProvPackageLog(3, L"    Failed to allocate spInputChunk.get()");
LABEL_40:
    if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyHash(phHash);
    operator delete(v19, v25);
    goto LABEL_29;
  }
  v26 = (UCHAR *)operator new[](0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  pbInput = v26;
  if ( !v26 )
  {
    LODWORD(cbSecretb) = -2147024882;
    dwFlagsc[0] = 114;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsc,
      cbSecretb);
    ProvPackageLog(3, L"    Failed to allocate spOutputChunk.get()");
    operator delete(v24, v27);
    goto LABEL_40;
  }
  v141 = 1;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v147 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(cbSecretc) = LastError;
    dwFlagsd[0] = 119;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsd,
      cbSecretc);
    ProvPackageLog(3, L"    Failed to create input file");
    v30 = GetLastError();
    v11 = v30;
    if ( v30 > 0 )
      v11 = (unsigned __int16)v30 | 0x80070000;
    operator delete(v26, v31);
    operator delete(v24, v32);
    if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyHash(phHash);
    operator delete(v19, v33);
    if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyKey(phKey);
    v13 = phAlgorithm;
    v14 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_11;
  }
  v34 = (char *)CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v148 = v34;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v35 = GetLastError();
    v36 = v35 < 0;
    if ( v35 > 0 )
      v36 = 1;
    if ( v36 )
    {
      v37 = GetLastError();
      if ( v37 > 0 )
        v37 = (unsigned __int16)v37 | 0x80070000;
      LODWORD(cbSecretd) = v37;
      dwFlagse[0] = 129;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageSecurity::CryptWrapper",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
        *(_QWORD *)dwFlagse,
        cbSecretd);
      ProvPackageLog(3, L"    Failed to get input file size");
      v38 = GetLastError();
      v40 = v38;
      if ( v38 > 0 )
        v40 = (unsigned __int16)v38 | 0x80070000;
      goto LABEL_65;
    }
  }
  v142 = FileSize;
  *(_DWORD *)v135 = 0;
  v44 = BCryptGetProperty(phAlgorithm, L"BlockLength", v135, 4u, &pcbResult, 0) | 0x10000000;
  NumberOfBytesRead = v44;
  if ( v44 < 0 )
  {
    LODWORD(cbSecrete) = v44;
    dwFlagsf[0] = 137;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsf,
      cbSecrete);
    ProvPackageLog(3, L"    Failed to get block length property");
LABEL_80:
    if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v34);
    if ( FileW )
      CloseHandle(FileW);
    operator delete(pbInput, v45);
    operator delete(v24, v46);
    if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyHash(phHash);
    operator delete(v19, v47);
    if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyKey(phKey);
    if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    return NumberOfBytesRead;
  }
  v48 = (UCHAR *)operator new[](*(unsigned int *)v135, (const struct std::nothrow_t *)&std::nothrow);
  pbBuffer = v48;
  if ( !v48 )
  {
    LODWORD(cbSecrete) = -2147024882;
    dwFlagsf[0] = 141;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsf,
      cbSecrete);
    ProvPackageLog(3, L"    Failed to allocate spIV.get()");
    if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v34);
    if ( FileW )
      CloseHandle(FileW);
    operator delete(pbInput, v49);
    operator delete(v24, v50);
    if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyHash(phHash);
    operator delete(v19, v51);
    if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptDestroyKey(phKey);
    v20 = phAlgorithm;
    v21 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_105;
  }
  if ( !a5 )
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(FileW, v48, *(DWORD *)v135, &NumberOfBytesRead, 0) )
      goto LABEL_139;
    v61 = GetLastError();
    v62 = v61 < 0;
    if ( v61 > 0 )
      v62 = 1;
    if ( !v62 )
    {
LABEL_139:
      i = v142.QuadPart - (*(unsigned int *)pbOutput + (unsigned __int64)*(unsigned int *)v135);
      goto LABEL_169;
    }
    v63 = GetLastError();
    if ( v63 > 0 )
      v63 = (unsigned __int16)v63 | 0x80070000;
    LODWORD(cbSecrete) = v63;
    dwFlagsg[0] = 175;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsg,
      cbSecrete);
    ProvPackageLog(3, L"    Failed to read IV");
LABEL_137:
    v64 = GetLastError();
    v40 = v64;
    if ( v64 > 0 )
      v40 = (unsigned __int16)v64 | 0x80070000;
    goto LABEL_126;
  }
  v139 = 0;
  v52 = BCryptOpenAlgorithmProvider(&v139, L"RNG", 0, 0) | 0x10000000;
  NumberOfBytesRead = v52;
  if ( v52 < 0 )
  {
    LODWORD(cbSecrete) = v52;
    dwFlagsf[0] = 151;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsf,
      cbSecrete);
    ProvPackageLog(3, L"    Failed to open RNG algorithm provider");
LABEL_111:
    if ( (char *)v139 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      BCryptCloseAlgorithmProvider(v139, 0);
    operator delete(pbBuffer, v53);
    goto LABEL_80;
  }
  v54 = BCryptGenRandom(v139, pbBuffer, *(ULONG *)v135, 0) | 0x10000000;
  NumberOfBytesRead = v54;
  if ( v54 < 0 )
  {
    LODWORD(cbSecrete) = v54;
    dwFlagsf[0] = 156;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageSecurity::CryptWrapper",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
      *(_QWORD *)dwFlagsf,
      cbSecrete);
    ProvPackageLog(3, L"    Failed to generate IV");
    goto LABEL_111;
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v34, pbBuffer, *(DWORD *)v135, &NumberOfBytesWritten, 0) )
  {
    v55 = GetLastError();
    v56 = v55 < 0;
    if ( v55 > 0 )
      v56 = 1;
    if ( v56 )
    {
      v57 = GetLastError();
      if ( v57 > 0 )
        v57 = (unsigned __int16)v57 | 0x80070000;
      LODWORD(cbSecrete) = v57;
      dwFlagsg[0] = 163;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageSecurity::CryptWrapper",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
        *(_QWORD *)dwFlagsg,
        cbSecrete);
      ProvPackageLog(3, L"    Failed to write IV");
      v58 = GetLastError();
      v40 = v58;
      if ( v58 > 0 )
        v40 = (unsigned __int16)v58 | 0x80070000;
      if ( (char *)v139 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptCloseAlgorithmProvider(v139, 0);
LABEL_126:
      operator delete(pbBuffer, v59);
LABEL_65:
      if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v34);
      if ( FileW )
        CloseHandle(FileW);
      operator delete(pbInput, v39);
      operator delete(v24, v41);
      if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptDestroyHash(phHash);
      operator delete(v19, v42);
      if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptCloseAlgorithmProvider(hAlgorithm, 0);
      if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptDestroyKey(phKey);
      if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      return v40;
    }
  }
  if ( (char *)v139 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    BCryptCloseAlgorithmProvider(v139, 0);
  for ( i = v142.QuadPart; ; v142.QuadPart = i )
  {
    if ( i <= 0 )
    {
      v76 = BCryptFinishHash(phHash, (PUCHAR)v19, *(ULONG *)pbOutput, 0) | 0x10000000;
      LODWORD(v139) = v76;
      if ( v76 < 0 )
      {
        LODWORD(cbSecrete) = v76;
        dwFlagsg[0] = 263;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsg,
          cbSecrete);
        ProvPackageLog(3, L"    Failed to finish hash");
        operator delete(pbBuffer, v77);
        if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v34);
        if ( FileW )
          CloseHandle(FileW);
        operator delete(pbInput, v78);
        operator delete(v24, v79);
        if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptDestroyHash(phHash);
        operator delete(v19, v80);
        if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptCloseAlgorithmProvider(hAlgorithm, 0);
        if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptDestroyKey(phKey);
        if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        return (unsigned int)v139;
      }
      LODWORD(v139) = 0;
      if ( a5 )
      {
        if ( !WriteFile(v34, v19, *(DWORD *)pbOutput, (LPDWORD)&v139, 0) )
        {
          v102 = GetLastError();
          v103 = v102 < 0;
          if ( v102 > 0 )
            v103 = 1;
          if ( v103 )
          {
            v104 = GetLastError();
            if ( v104 > 0 )
              v104 = (unsigned __int16)v104 | 0x80070000;
            LODWORD(cbSecrete) = v104;
            dwFlagsj[0] = 273;
            ProvPackageLog(
              3,
              L"%hs (%hs:%d) - 0x%08x:",
              "PackageSecurity::CryptWrapper",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
              *(_QWORD *)dwFlagsj,
              cbSecrete);
            ProvPackageLog(3, L"    Failed to write hash");
            goto LABEL_137;
          }
        }
      }
      else
      {
        if ( !ReadFile(FileW, v24, *(DWORD *)pbOutput, (LPDWORD)&v139, 0) )
        {
          v105 = GetLastError();
          v106 = v105 < 0;
          if ( v105 > 0 )
            v106 = 1;
          if ( v106 )
          {
            v107 = GetLastError();
            if ( v107 > 0 )
              v107 = (unsigned __int16)v107 | 0x80070000;
            LODWORD(cbSecrete) = v107;
            dwFlagsk[0] = 282;
            ProvPackageLog(
              3,
              L"%hs (%hs:%d) - 0x%08x:",
              "PackageSecurity::CryptWrapper",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
              *(_QWORD *)dwFlagsk,
              cbSecrete);
            ProvPackageLog(3, L"    Failed to read hash");
            goto LABEL_137;
          }
        }
        if ( memcmp_0(v24, v19, *(unsigned int *)pbOutput) )
        {
          v96 = -2147023504;
          LODWORD(cbSecrete) = -2147023504;
          dwFlagsk[0] = 287;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "PackageSecurity::CryptWrapper",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
            *(_QWORD *)dwFlagsk,
            cbSecrete);
          ProvPackageLog(3, L"    Failed to validate hash");
LABEL_233:
          operator delete(pbBuffer, v97);
          if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v34);
          if ( FileW )
            CloseHandle(FileW);
          operator delete(pbInput, v98);
          operator delete(v24, v99);
          if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptDestroyHash(phHash);
          operator delete(v19, v100);
          if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptCloseAlgorithmProvider(hAlgorithm, 0);
          if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptDestroyKey(phKey);
          if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptCloseAlgorithmProvider(phAlgorithm, 0);
          return v96;
        }
      }
      operator delete(pbBuffer, v101);
      if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v34);
      if ( FileW )
        CloseHandle(FileW);
      operator delete(pbInput, v108);
      operator delete(v24, v109);
      if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptDestroyHash(phHash);
      operator delete(v19, v110);
      if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptCloseAlgorithmProvider(hAlgorithm, 0);
      if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptDestroyKey(phKey);
      if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      return 0;
    }
    NumberOfBytesRead = 0;
    NumberOfBytesWritten = i;
    if ( (unsigned __int64)i >= 0xA0 )
      NumberOfBytesWritten = 160;
    memset_0(v24, 0, 0xA0u);
    memset_0(pbInput, 0, 0xA0u);
    if ( !ReadFile(FileW, v24, NumberOfBytesWritten, &NumberOfBytesRead, 0) )
    {
      v65 = GetLastError();
      v66 = v65 < 0;
      if ( v65 > 0 )
        v66 = 1;
      if ( v66 )
      {
        v81 = GetLastError();
        if ( v81 > 0 )
          v81 = (unsigned __int16)v81 | 0x80070000;
        LODWORD(cbSecrete) = v81;
        dwFlagsh[0] = 194;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsh,
          cbSecrete);
        ProvPackageLog(3, L"    Failed to read chunk");
        goto LABEL_137;
      }
    }
    if ( !NumberOfBytesRead )
    {
      v96 = 1006;
      LODWORD(cbSecrete) = 1006;
      dwFlagsh[0] = 199;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PackageSecurity::CryptWrapper",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
        *(_QWORD *)dwFlagsh,
        cbSecrete);
      ProvPackageLog(3, L"    Early file termination");
      goto LABEL_233;
    }
    v144 = NumberOfBytesRead;
    if ( a5 )
    {
      if ( v141 )
      {
        v67 = *(unsigned int *)v135;
        if ( *(_DWORD *)v135 >= 8u )
          v67 = 8;
        if ( memcmp_0(v24, "MSWIM", v67) )
        {
          LODWORD(cbSecrete) = -2147024883;
          dwFlagsh[0] = 212;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "PackageSecurity::CryptWrapper",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
            *(_QWORD *)dwFlagsh,
            cbSecrete);
          ProvPackageLog(3, L"    Invalid first chunk");
          operator delete(pbBuffer, v82);
          if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v34);
          if ( FileW )
            CloseHandle(FileW);
          operator delete(pbInput, v83);
          operator delete(v24, v84);
          if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptDestroyHash(phHash);
          operator delete(v19, v85);
          if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptCloseAlgorithmProvider(hAlgorithm, 0);
          if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            BCryptDestroyKey(phKey);
          v86 = phAlgorithm;
          v87 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
          goto LABEL_224;
        }
        v141 = 0;
      }
      v68 = BCryptEncrypt(phKey, (PUCHAR)v24, 0xA0u, 0, pbBuffer, *(ULONG *)v135, pbInput, 0xA0u, &pcbResult, 0)
          | 0x10000000;
      NumberOfBytesWritten = v68;
      if ( v68 < 0 )
      {
        LODWORD(cbSecrete) = v68;
        dwFlagsh[0] = 221;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsh,
          cbSecrete);
        ProvPackageLog(3, L"    Failed to encrypt chunk");
        goto LABEL_200;
      }
      v69 = BCryptHashData(phHash, pbInput, pcbResult, 0) | 0x10000000;
      NumberOfBytesWritten = v69;
      if ( v69 < 0 )
      {
        LODWORD(cbSecrete) = v69;
        dwFlagsh[0] = 226;
LABEL_156:
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsh,
          cbSecrete);
        ProvPackageLog(3, L"    Failed to compute chunk hash");
        goto LABEL_200;
      }
      goto LABEL_164;
    }
    v71 = BCryptHashData(phHash, (PUCHAR)v24, NumberOfBytesRead, 0) | 0x10000000;
    NumberOfBytesWritten = v71;
    if ( v71 < 0 )
    {
      LODWORD(cbSecrete) = v71;
      dwFlagsh[0] = 233;
      goto LABEL_156;
    }
    v72 = BCryptDecrypt(phKey, (PUCHAR)v24, 0xA0u, 0, pbBuffer, *(ULONG *)v135, pbInput, 0xA0u, &pcbResult, 0)
        | 0x10000000;
    NumberOfBytesWritten = v72;
    if ( v72 < 0 )
      break;
    if ( v141 )
    {
      v73 = *(unsigned int *)v135;
      if ( *(_DWORD *)v135 >= 8u )
        v73 = 8;
      if ( memcmp_0(pbInput, "MSWIM", v73) )
      {
        LODWORD(cbSecrete) = -2147024883;
        dwFlagsi[0] = 247;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsi,
          cbSecrete);
        ProvPackageLog(3, L"    Invalid first chunk");
        operator delete(pbBuffer, v91);
        if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v34);
        if ( FileW )
          CloseHandle(FileW);
        operator delete(pbInput, v92);
        operator delete(v24, v93);
        if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptDestroyHash(phHash);
        operator delete(v19, v94);
        if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptCloseAlgorithmProvider(hAlgorithm, 0);
        if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          BCryptDestroyKey(phKey);
        v86 = phAlgorithm;
        v87 = (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_224:
        if ( v87 )
          BCryptCloseAlgorithmProvider(v86, 0);
        return 2147942413LL;
      }
      v141 = 0;
    }
LABEL_164:
    LODWORD(v139) = 0;
    if ( !WriteFile(v34, pbInput, pcbResult, (LPDWORD)&v139, 0) )
    {
      v74 = GetLastError();
      v75 = v74 < 0;
      if ( v74 > 0 )
        v75 = 1;
      if ( v75 )
      {
        v95 = GetLastError();
        if ( v95 > 0 )
          v95 = (unsigned __int16)v95 | 0x80070000;
        LODWORD(cbSecrete) = v95;
        dwFlagsg[0] = 258;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PackageSecurity::CryptWrapper",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
          *(_QWORD *)dwFlagsg,
          cbSecrete);
        ProvPackageLog(3, L"    Failed to write chunk");
        goto LABEL_137;
      }
    }
    i = v142.QuadPart - v144;
LABEL_169:
    ;
  }
  LODWORD(cbSecrete) = v72;
  dwFlagsi[0] = 239;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "PackageSecurity::CryptWrapper",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagesecurity.cpp",
    *(_QWORD *)dwFlagsi,
    cbSecrete);
  ProvPackageLog(3, L"    Failed to decrypt block");
LABEL_200:
  operator delete(pbBuffer, v70);
  if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v34);
  if ( FileW )
    CloseHandle(FileW);
  operator delete(pbInput, v88);
  operator delete(v24, v89);
  if ( (char *)phHash - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    BCryptDestroyHash(phHash);
  operator delete(v19, v90);
  if ( (char *)hAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( (char *)phKey - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    BCryptDestroyKey(phKey);
  if ( (char *)phAlgorithm - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return NumberOfBytesWritten;
}

```

## disassembly

```asm
0x18000b7b0  mov     [rsp-8+arg_0], rbx
0x18000b7b5  push    rbp
0x18000b7b6  push    rsi
0x18000b7b7  push    rdi
0x18000b7b8  push    r12
0x18000b7ba  push    r13
0x18000b7bc  push    r14
0x18000b7be  push    r15
0x18000b7c0  lea     rbp, [rsp-1Fh]
0x18000b7c5  sub     rsp, 0F0h
0x18000b7cc  mov     rax, cs:__security_cookie
0x18000b7d3  xor     rax, rsp
0x18000b7d6  mov     [rbp+4Fh+var_38], rax
0x18000b7da  mov     rbx, r9
0x18000b7dd  mov     r13, r8
0x18000b7e0  mov     rsi, rdx
0x18000b7e3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b7e7  mov     rax, rdi
0x18000b7ea  xor     r14d, r14d
0x18000b7ed  inc     rax
0x18000b7f0  cmp     [r9+rax*2], r14w
0x18000b7f5  jnz     short loc_18000B7ED
0x18000b7f7  dec     rax
0x18000b7fa  cmp     rax, 0Fh
0x18000b7fe  ja      loc_18000CDAB
0x18000b804  xorps   xmm0, xmm0
0x18000b807  movups  xmmword ptr [rbp+4Fh+pbSecret], xmm0
0x18000b80b  mov     r12d, 10h
0x18000b811  mov     r8d, r12d
0x18000b814  mov     rdx, rbx
0x18000b817  lea     rcx, [rbp+4Fh+pbSecret]
0x18000b81b  call    cs:__imp__o_wcstombs
0x18000b821  mov     rcx, rdi
0x18000b824  inc     rcx
0x18000b827  cmp     [rbx+rcx*2], r14w
0x18000b82c  jnz     short loc_18000B824
0x18000b82e  cmp     rax, rcx
0x18000b831  jz      short loc_18000B873
0x18000b833  mov     ebx, 80070057h
0x18000b838  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000b83c  mov     [rsp+120h+dwFlags], 3Eh ; '>'
0x18000b844  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000b84b  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000b852  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000b859  mov     r14d, 3
0x18000b85f  mov     ecx, r14d
0x18000b862  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b867  lea     rdx, aInvalidPasswor_0; "    Invalid password byte length"
0x18000b86e  jmp     loc_18000CDE6
0x18000b873  mov     [rsp+120h+phAlgorithm], r14
0x18000b878  xor     r9d, r9d; dwFlags
0x18000b87b  xor     r8d, r8d; pszImplementation
0x18000b87e  lea     rdx, pszAlgId; "AES"
0x18000b885  lea     rcx, [rsp+120h+phAlgorithm]; phAlgorithm
0x18000b88a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000b890  mov     ebx, eax
0x18000b892  mov     edi, 10000000h
0x18000b897  or      ebx, edi
0x18000b899  jge     short loc_18000B900
0x18000b89b  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000b89f  mov     [rsp+120h+dwFlags], 49h ; 'I'
0x18000b8a7  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000b8ae  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000b8b5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000b8bc  mov     r14d, 3
0x18000b8c2  mov     ecx, r14d
0x18000b8c5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b8ca  lea     rdx, aFailedToOpenAe; "    Failed to open AES algorithm provid"...
0x18000b8d1  mov     ecx, r14d
0x18000b8d4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b8d9  nop
0x18000b8da  mov     rsi, 0FFFFFFFFFFFFFFFDh
0x18000b8e1  mov     rcx, [rsp+120h+phAlgorithm]; hAlgorithm
0x18000b8e6  lea     rax, [rcx-1]
0x18000b8ea  cmp     rax, rsi
0x18000b8ed  ja      loc_18000CDEE
0x18000b8f3  xor     edx, edx; dwFlags
0x18000b8f5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000b8fb  jmp     loc_18000CDEE
0x18000b900  mov     [rsp+120h+dwFlags], r14d; dwFlags
0x18000b905  mov     r9d, 20h ; ' '; cbInput
0x18000b90b  lea     r8, pbInput; "ChainingModeCBC"
0x18000b912  lea     rdx, pszProperty; "ChainingMode"
0x18000b919  mov     rcx, [rsp+120h+phAlgorithm]; hObject
0x18000b91e  call    cs:__imp_BCryptSetProperty
0x18000b924  mov     ebx, eax
0x18000b926  or      ebx, edi
0x18000b928  jge     short loc_18000B965
0x18000b92a  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000b92e  mov     [rsp+120h+dwFlags], 4Eh ; 'N'
0x18000b936  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000b93d  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000b944  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000b94b  mov     r14d, 3
0x18000b951  mov     ecx, r14d
0x18000b954  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b959  lea     rdx, aFailedToSetCha; "    Failed to set chaining property"
0x18000b960  jmp     loc_18000B8D1
0x18000b965  mov     [rbp+4Fh+phKey], r14
0x18000b969  mov     [rsp+120h+var_F0], r14d; dwFlags
0x18000b96e  mov     dword ptr [rsp+120h+cbSecret], r12d; cbSecret
0x18000b973  lea     rax, [rbp+4Fh+pbSecret]
0x18000b977  mov     qword ptr [rsp+120h+dwFlags], rax; pbSecret
0x18000b97c  xor     r9d, r9d; cbKeyObject
0x18000b97f  xor     r8d, r8d; pbKeyObject
0x18000b982  lea     rdx, [rbp+4Fh+phKey]; phKey
0x18000b986  mov     rcx, [rsp+120h+phAlgorithm]; hAlgorithm
0x18000b98b  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000b991  mov     ebx, eax
0x18000b993  or      ebx, edi
0x18000b995  jge     short loc_18000B9F6
0x18000b997  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000b99b  mov     [rsp+120h+dwFlags], 53h ; 'S'
0x18000b9a3  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000b9aa  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000b9b1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000b9b8  mov     r14d, 3
0x18000b9be  mov     ecx, r14d
0x18000b9c1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b9c6  lea     rdx, aFailedToGenera_0; "    Failed to generate key"
0x18000b9cd  mov     ecx, r14d
0x18000b9d0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000b9d5  nop
0x18000b9d6  mov     rsi, 0FFFFFFFFFFFFFFFDh
0x18000b9dd  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18000b9e1  lea     rax, [rcx-1]
0x18000b9e5  cmp     rax, rsi
0x18000b9e8  ja      short loc_18000B9F1
0x18000b9ea  call    cs:__imp_BCryptDestroyKey
0x18000b9f0  nop
0x18000b9f1  jmp     loc_18000B8E1
0x18000b9f6  mov     [rbp+4Fh+hAlgorithm], r14
0x18000b9fa  mov     r9d, 8; dwFlags
0x18000ba00  xor     r8d, r8d; pszImplementation
0x18000ba03  lea     rdx, aSha256; "SHA256"
0x18000ba0a  lea     rcx, [rbp+4Fh+hAlgorithm]; phAlgorithm
0x18000ba0e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ba14  mov     ebx, eax
0x18000ba16  or      ebx, edi
0x18000ba18  jge     short loc_18000BA7B
0x18000ba1a  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000ba1e  mov     [rsp+120h+dwFlags], 59h ; 'Y'
0x18000ba26  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000ba2d  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000ba34  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000ba3b  mov     r14d, 3
0x18000ba41  mov     ecx, r14d
0x18000ba44  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000ba49  lea     rdx, aFailedToOpenSh; "    Failed to open SHA256 algorithm pro"...
0x18000ba50  mov     ecx, r14d
0x18000ba53  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000ba58  nop
0x18000ba59  mov     rsi, 0FFFFFFFFFFFFFFFDh
0x18000ba60  mov     rcx, [rbp+4Fh+hAlgorithm]; hAlgorithm
0x18000ba64  lea     rax, [rcx-1]
0x18000ba68  cmp     rax, rsi
0x18000ba6b  ja      short loc_18000BA76
0x18000ba6d  xor     edx, edx; dwFlags
0x18000ba6f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000ba75  nop
0x18000ba76  jmp     loc_18000B9DD
0x18000ba7b  mov     dword ptr [rbp+4Fh+pbOutput], r14d
0x18000ba7f  mov     [rbp+4Fh+pcbResult], r14d
0x18000ba83  mov     dword ptr [rsp+120h+cbSecret], r14d; dwFlags
0x18000ba88  lea     rax, [rbp+4Fh+pcbResult]
0x18000ba8c  mov     qword ptr [rsp+120h+dwFlags], rax; pcbResult
0x18000ba91  mov     r9d, 4; cbOutput
0x18000ba97  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x18000ba9b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000baa2  mov     rcx, [rbp+4Fh+hAlgorithm]; hObject
0x18000baa6  call    cs:__imp_BCryptGetProperty
0x18000baac  mov     ebx, eax
0x18000baae  or      ebx, edi
0x18000bab0  jge     short loc_18000BAED
0x18000bab2  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000bab6  mov     [rsp+120h+dwFlags], 61h ; 'a'
0x18000babe  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000bac5  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000bacc  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000bad3  mov     r14d, 3
0x18000bad9  mov     ecx, r14d
0x18000badc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bae1  lea     rdx, aFailedToGetHas; "    Failed to get hash length property"
0x18000bae8  jmp     loc_18000BA50
0x18000baed  mov     ecx, dword ptr [rbp+4Fh+pbOutput]; unsigned __int64
0x18000baf0  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000baf7  mov     rdx, rdi; struct std::nothrow_t *
0x18000bafa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000baff  mov     r15, rax
0x18000bb02  mov     [rbp+4Fh+var_68], rax
0x18000bb06  test    rax, rax
0x18000bb09  jnz     loc_18000BB8F
0x18000bb0f  mov     dword ptr [rsp+120h+cbSecret], 8007000Eh
0x18000bb17  mov     [rsp+120h+dwFlags], 65h ; 'e'
0x18000bb1f  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000bb26  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000bb2d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000bb34  lea     r14d, [rax+3]
0x18000bb38  mov     ecx, r14d
0x18000bb3b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bb40  lea     rdx, aFailedToAlloca_21; "    Failed to allocate spHmac.get()"
0x18000bb47  mov     ecx, r14d
0x18000bb4a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bb4f  nop
0x18000bb50  lea     rsi, [r15-3]
0x18000bb54  mov     rcx, [rbp+4Fh+hAlgorithm]; hAlgorithm
0x18000bb58  lea     rax, [rcx-1]
0x18000bb5c  cmp     rax, rsi
0x18000bb5f  ja      short loc_18000BB6A
0x18000bb61  xor     edx, edx; dwFlags
0x18000bb63  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000bb69  nop
0x18000bb6a  mov     rcx, [rbp+4Fh+phKey]; hKey
0x18000bb6e  lea     rax, [rcx-1]
0x18000bb72  cmp     rax, rsi
0x18000bb75  ja      short loc_18000BB7E
0x18000bb77  call    cs:__imp_BCryptDestroyKey
0x18000bb7d  nop
0x18000bb7e  mov     rcx, [rsp+120h+phAlgorithm]
0x18000bb83  lea     rax, [rcx-1]
0x18000bb87  cmp     rax, rsi
0x18000bb8a  jmp     loc_18000C195
0x18000bb8f  mov     [rbp+4Fh+phHash], r14
0x18000bb93  mov     [rsp+120h+var_F0], r14d; dwFlags
0x18000bb98  mov     dword ptr [rsp+120h+cbSecret], r12d; cbSecret
0x18000bb9d  lea     rax, [rbp+4Fh+pbSecret]
0x18000bba1  mov     qword ptr [rsp+120h+dwFlags], rax; pbSecret
0x18000bba6  xor     r9d, r9d; cbHashObject
0x18000bba9  xor     r8d, r8d; pbHashObject
0x18000bbac  lea     rdx, [rbp+4Fh+phHash]; phHash
0x18000bbb0  mov     rcx, [rbp+4Fh+hAlgorithm]; hAlgorithm
0x18000bbb4  call    cs:__imp_BCryptCreateHash
0x18000bbba  mov     ebx, eax
0x18000bbbc  or      ebx, 10000000h
0x18000bbc2  jge     short loc_18000BC2C
0x18000bbc4  mov     dword ptr [rsp+120h+cbSecret], ebx
0x18000bbc8  mov     [rsp+120h+dwFlags], 6Bh ; 'k'
0x18000bbd0  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000bbd7  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000bbde  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000bbe5  mov     r14d, 3
0x18000bbeb  mov     ecx, r14d
0x18000bbee  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bbf3  lea     rdx, aFailedToCreate_17; "    Failed to create hash"
0x18000bbfa  mov     ecx, r14d
0x18000bbfd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bc02  nop
0x18000bc03  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18000bc07  lea     rax, [rcx-1]
0x18000bc0b  mov     rsi, 0FFFFFFFFFFFFFFFDh
0x18000bc12  cmp     rax, rsi
0x18000bc15  ja      short loc_18000BC1E
0x18000bc17  call    cs:__imp_BCryptDestroyHash
0x18000bc1d  nop
0x18000bc1e  mov     rcx, r15; void *
0x18000bc21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bc26  nop
0x18000bc27  jmp     loc_18000BA60
0x18000bc2c  mov     rdx, rdi; struct std::nothrow_t *
0x18000bc2f  mov     ebx, 0A0h
0x18000bc34  mov     ecx, ebx; unsigned __int64
0x18000bc36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bc3b  mov     r12, rax
0x18000bc3e  mov     [rbp+4Fh+var_60], rax
0x18000bc42  test    rax, rax
0x18000bc45  jnz     short loc_18000BCB1
0x18000bc47  mov     dword ptr [rsp+120h+cbSecret], 8007000Eh
0x18000bc4f  mov     [rsp+120h+dwFlags], 6Fh ; 'o'
0x18000bc57  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000bc5e  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
0x18000bc65  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000bc6c  lea     r14d, [rax+3]
0x18000bc70  mov     ecx, r14d
0x18000bc73  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bc78  lea     rdx, aFailedToAlloca_35; "    Failed to allocate spInputChunk.get"...
0x18000bc7f  mov     ecx, r14d
0x18000bc82  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000bc87  nop
0x18000bc88  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18000bc8c  mov     rsi, 0FFFFFFFFFFFFFFFDh
0x18000bc93  lea     rax, [rcx-1]
0x18000bc97  cmp     rax, rsi
0x18000bc9a  ja      short loc_18000BCA3
0x18000bc9c  call    cs:__imp_BCryptDestroyHash
0x18000bca2  nop
0x18000bca3  mov     rcx, r15; void *
0x18000bca6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bcab  nop
0x18000bcac  jmp     loc_18000BB54
0x18000bcb1  mov     rdx, rdi; struct std::nothrow_t *
0x18000bcb4  mov     rcx, rbx; unsigned __int64
0x18000bcb7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bcbc  mov     rdi, rax
0x18000bcbf  mov     [rbp+4Fh+pbInput], rax
0x18000bcc3  test    rax, rax
0x18000bcc6  jnz     short loc_18000BD16
0x18000bcc8  mov     dword ptr [rsp+120h+cbSecret], 8007000Eh
0x18000bcd0  mov     [rsp+120h+dwFlags], 72h ; 'r'
0x18000bcd8  lea     r9, aOnecoreBaseNts_2; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000bcdf  lea     r8, aPackagesecurit; "PackageSecurity::CryptWrapper"
  ... truncated ...
```
