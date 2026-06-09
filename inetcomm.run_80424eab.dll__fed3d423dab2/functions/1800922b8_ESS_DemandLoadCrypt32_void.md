# ESS_DemandLoadCrypt32(void)

- ea: `0x1800922b8`
- end: `0x1800923f5`
- name: `?ESS_DemandLoadCrypt32@@YAHXZ`
- size: `317`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180093d60`
- `0x180093dc0`
- `0x180093e00`
- `0x180093e40`
- `0x180093ea0`

## callees

- `0x1800922b8`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x1800922e5`
- `KERNEL32!LoadLibraryA` at `0x1800922e5`
- `KERNEL32!GetProcAddress` at `0x180092308`
- `KERNEL32!GetProcAddress` at `0x180092336`
- `KERNEL32!GetProcAddress` at `0x180092364`
- `KERNEL32!GetProcAddress` at `0x180092392`
- `KERNEL32!GetProcAddress` at `0x1800923c0`
- `KERNEL32!GetProcAddress` at `0x180092308`
- `KERNEL32!GetProcAddress` at `0x180092336`
- `KERNEL32!GetProcAddress` at `0x180092364`
- `KERNEL32!GetProcAddress` at `0x180092392`
- `KERNEL32!GetProcAddress` at `0x1800923c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800923e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800923e7`
- `KERNEL32!EnterCriticalSection` at `0x1800922ca`
- `KERNEL32!EnterCriticalSection` at `0x1800922ca`

## string_xrefs

- `0x1800922de`: `CRYPT32.DLL`
- `0x18009232f`: `I_CryptUninstallAsn1Module`
- `0x18009235d`: `I_CryptInstallAsn1Module`

## pseudocode

```c
__int64 ESS_DemandLoadCrypt32(void)
{
  unsigned int v0; // ebx
  HMODULE LibraryA; // rax

  v0 = 1;
  EnterCriticalSection(&stru_1800F33B8);
  if ( !hModule )
  {
    LibraryA = LoadLibraryA("CRYPT32.DLL");
    hModule = LibraryA;
    if ( LibraryA )
    {
      VAR_CryptRegisterOIDFunction = (int (*)(unsigned int, const char *, const char *, const unsigned __int16 *, const char *))GetProcAddress(LibraryA, "CryptRegisterOIDFunction");
      if ( !VAR_CryptRegisterOIDFunction )
        VAR_CryptRegisterOIDFunction = (int (*)(unsigned int, const char *, const char *, const unsigned __int16 *, const char *))LOADER_CryptRegisterOIDFunction;
      VAR_I_CryptUninstallAsn1Module = (int (*)(unsigned int))GetProcAddress(hModule, "I_CryptUninstallAsn1Module");
      if ( !VAR_I_CryptUninstallAsn1Module )
        VAR_I_CryptUninstallAsn1Module = (int (*)(unsigned int))LOADER_I_CryptUninstallAsn1Module;
      VAR_I_CryptInstallAsn1Module = (int (*)(struct tagASN1module_t *, unsigned int, void *))GetProcAddress(
                                                                                                hModule,
                                                                                                "I_CryptInstallAsn1Module");
      if ( !VAR_I_CryptInstallAsn1Module )
        VAR_I_CryptInstallAsn1Module = (int (*)(struct tagASN1module_t *, unsigned int, void *))LOADER_I_CryptInstallAsn1Module;
      VAR_I_CryptGetAsn1Encoder = (struct ASN1encoding_s *(*)(unsigned int))GetProcAddress(
                                                                              hModule,
                                                                              "I_CryptGetAsn1Encoder");
      if ( !VAR_I_CryptGetAsn1Encoder )
        VAR_I_CryptGetAsn1Encoder = (struct ASN1encoding_s *(*)(unsigned int))LOADER_I_CryptGetAsn1Encoder;
      VAR_I_CryptGetAsn1Decoder = (struct ASN1decoding_s *(*)(unsigned int))GetProcAddress(
                                                                              hModule,
                                                                              "I_CryptGetAsn1Decoder");
      if ( !VAR_I_CryptGetAsn1Decoder )
        VAR_I_CryptGetAsn1Decoder = (struct ASN1decoding_s *(*)(unsigned int))LOADER_I_CryptGetAsn1Decoder;
    }
    else
    {
      v0 = 0;
    }
  }
  LeaveCriticalSection(&stru_1800F33B8);
  return v0;
}

```

## disassembly

```asm
0x1800922b8  push    rbx
0x1800922ba  sub     rsp, 20h
0x1800922be  lea     rcx, stru_1800F33B8; lpCriticalSection
0x1800922c5  mov     ebx, 1
0x1800922ca  call    cs:__imp_EnterCriticalSection
0x1800922d0  cmp     cs:hModule, 0
0x1800922d8  jnz     loc_1800923E0
0x1800922de  lea     rcx, aCrypt32Dll_0; "CRYPT32.DLL"
0x1800922e5  call    cs:__imp_LoadLibraryA
0x1800922eb  mov     cs:hModule, rax
0x1800922f2  test    rax, rax
0x1800922f5  jnz     short loc_1800922FE
0x1800922f7  xor     ebx, ebx
0x1800922f9  jmp     loc_1800923E0
0x1800922fe  lea     rdx, aCryptregistero; "CryptRegisterOIDFunction"
0x180092305  mov     rcx, rax; hModule
0x180092308  call    cs:__imp_GetProcAddress
0x18009230e  mov     cs:?VAR_CryptRegisterOIDFunction@@3P6AHKPEBD0PEBG0@ZEA, rax; int (*VAR_CryptRegisterOIDFunction)(ulong,char const *,char const *,ushort const *,char const *)
0x180092315  test    rax, rax
0x180092318  jnz     short loc_180092328
0x18009231a  lea     rax, ?LOADER_CryptRegisterOIDFunction@@YAHKPEBD0PEBG0@Z; LOADER_CryptRegisterOIDFunction(ulong,char const *,char const *,ushort const *,char const *)
0x180092321  mov     cs:?VAR_CryptRegisterOIDFunction@@3P6AHKPEBD0PEBG0@ZEA, rax; int (*VAR_CryptRegisterOIDFunction)(ulong,char const *,char const *,ushort const *,char const *)
0x180092328  mov     rcx, cs:hModule; hModule
0x18009232f  lea     rdx, aICryptuninstal; "I_CryptUninstallAsn1Module"
0x180092336  call    cs:__imp_GetProcAddress
0x18009233c  mov     cs:?VAR_I_CryptUninstallAsn1Module@@3P6AHK@ZEA, rax; int (*VAR_I_CryptUninstallAsn1Module)(ulong)
0x180092343  test    rax, rax
0x180092346  jnz     short loc_180092356
0x180092348  lea     rax, ?LOADER_I_CryptUninstallAsn1Module@@YAHK@Z; LOADER_I_CryptUninstallAsn1Module(ulong)
0x18009234f  mov     cs:?VAR_I_CryptUninstallAsn1Module@@3P6AHK@ZEA, rax; int (*VAR_I_CryptUninstallAsn1Module)(ulong)
0x180092356  mov     rcx, cs:hModule; hModule
0x18009235d  lea     rdx, aICryptinstalla; "I_CryptInstallAsn1Module"
0x180092364  call    cs:__imp_GetProcAddress
0x18009236a  mov     cs:?VAR_I_CryptInstallAsn1Module@@3P6AHPEAUtagASN1module_t@@KPEAX@ZEA, rax; int (*VAR_I_CryptInstallAsn1Module)(tagASN1module_t *,ulong,void *)
0x180092371  test    rax, rax
0x180092374  jnz     short loc_180092384
0x180092376  lea     rax, ?LOADER_I_CryptInstallAsn1Module@@YAHPEAUtagASN1module_t@@KPEAX@Z; LOADER_I_CryptInstallAsn1Module(tagASN1module_t *,ulong,void *)
0x18009237d  mov     cs:?VAR_I_CryptInstallAsn1Module@@3P6AHPEAUtagASN1module_t@@KPEAX@ZEA, rax; int (*VAR_I_CryptInstallAsn1Module)(tagASN1module_t *,ulong,void *)
0x180092384  mov     rcx, cs:hModule; hModule
0x18009238b  lea     rdx, aICryptgetasn1e; "I_CryptGetAsn1Encoder"
0x180092392  call    cs:__imp_GetProcAddress
0x180092398  mov     cs:?VAR_I_CryptGetAsn1Encoder@@3P6APEAUASN1encoding_s@@K@ZEA, rax; ASN1encoding_s * (*VAR_I_CryptGetAsn1Encoder)(ulong)
0x18009239f  test    rax, rax
0x1800923a2  jnz     short loc_1800923B2
0x1800923a4  lea     rax, ?LOADER_I_CryptGetAsn1Encoder@@YAPEAUASN1encoding_s@@K@Z; LOADER_I_CryptGetAsn1Encoder(ulong)
0x1800923ab  mov     cs:?VAR_I_CryptGetAsn1Encoder@@3P6APEAUASN1encoding_s@@K@ZEA, rax; ASN1encoding_s * (*VAR_I_CryptGetAsn1Encoder)(ulong)
0x1800923b2  mov     rcx, cs:hModule; hModule
0x1800923b9  lea     rdx, aICryptgetasn1d; "I_CryptGetAsn1Decoder"
0x1800923c0  call    cs:__imp_GetProcAddress
0x1800923c6  mov     cs:?VAR_I_CryptGetAsn1Decoder@@3P6APEAUASN1decoding_s@@K@ZEA, rax; ASN1decoding_s * (*VAR_I_CryptGetAsn1Decoder)(ulong)
0x1800923cd  test    rax, rax
0x1800923d0  jnz     short loc_1800923E0
0x1800923d2  lea     rax, ?LOADER_I_CryptGetAsn1Decoder@@YAPEAUASN1decoding_s@@K@Z; LOADER_I_CryptGetAsn1Decoder(ulong)
0x1800923d9  mov     cs:?VAR_I_CryptGetAsn1Decoder@@3P6APEAUASN1decoding_s@@K@ZEA, rax; ASN1decoding_s * (*VAR_I_CryptGetAsn1Decoder)(ulong)
0x1800923e0  lea     rcx, stru_1800F33B8; lpCriticalSection
0x1800923e7  call    cs:__imp_LeaveCriticalSection
0x1800923ed  mov     eax, ebx
0x1800923ef  add     rsp, 20h
0x1800923f3  pop     rbx
0x1800923f4  retn
```
