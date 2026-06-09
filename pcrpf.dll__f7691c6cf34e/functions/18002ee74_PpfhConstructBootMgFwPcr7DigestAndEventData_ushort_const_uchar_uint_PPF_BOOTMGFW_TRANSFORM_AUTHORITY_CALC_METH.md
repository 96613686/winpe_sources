# PpfhConstructBootMgFwPcr7DigestAndEventData(ushort const *,uchar *,uint,PPF_BOOTMGFW_TRANSFORM_AUTHORITY_CALC_METHOD,bool *,uchar * *,ushort *,uchar * *,uint *)

- ea: `0x18002ee74`
- end: `0x180030399`
- name: `?PpfhConstructBootMgFwPcr7DigestAndEventData@@YAJPEBGPEAEIW4PPF_BOOTMGFW_TRANSFORM_AUTHORITY_CALC_METHOD@@PEA_NPEAPEAEPEAG4PEAI@Z`
- size: `5413`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned __int8 *, unsigned int, int, _BYTE *, _QWORD *, _WORD *, GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047b20`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c44`
- `0x180009c64`
- `0x18000b5c8`
- `0x18000dfa0`
- `0x18000f0c8`
- `0x1800181fc`
- `0x180028d5c`
- `0x180029f9c`
- `0x18002b774`
- `0x18002d0f8`
- `0x18002d5ec`
- `0x18002ee74`
- `0x18003068c`
- `0x1800324e0`
- `0x180032844`
- `0x180034ff8`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f4f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f4f9`
- `ntdll!RtlInitUnicodeString` at `0x18002fad7`
- `ntdll!RtlInitUnicodeString` at `0x18002fad7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fc2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030089`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fc2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f52d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f872`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fa6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fbbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fedd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ff0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ffd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030004`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800300d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003019a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f52d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f872`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fa6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fbbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fedd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ff0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ffd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030004`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800300d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003019a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f541`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f886`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f998`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ff21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ffe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800300e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030210`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f541`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f886`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f998`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ff21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ffe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800300e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030210`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f15d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f26a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fa8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fbe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fd74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800302c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f15d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f26a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fa8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fbe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fd74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800302c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f5ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f670`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f75a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f79a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f5ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f670`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f75a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f79a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f012`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f012`
- `CRYPT32!CryptDecodeObjectEx` at `0x18002f5b9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18002f5b9`
- `CRYPT32!CertGetNameStringW` at `0x18002f45d`
- `CRYPT32!CertGetNameStringW` at `0x18002f4b5`
- `CRYPT32!CertGetNameStringW` at `0x18002f45d`
- `CRYPT32!CertGetNameStringW` at `0x18002f4b5`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002f19f`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002f19f`
- `WINTRUST!WinVerifyTrust` at `0x18002f119`
- `WINTRUST!WinVerifyTrust` at `0x18002f119`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002f229`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002f229`

## string_xrefs

- `0x180030387`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PpfhConstructBootMgFwPcr7DigestAndEventData(
        const WCHAR *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        _BYTE *a5,
        _QWORD *a6,
        _WORD *a7,
        GUID **a8,
        unsigned int *a9)
{
  int DBAndBootMgFwAuthoritySignatureFromLog; // eax
  unsigned int v14; // ebx
  char *FileW; // rbx
  const char *v17; // r9
  unsigned int LastError; // edi
  LONG v19; // eax
  CRYPT_PROVIDER_DATA *v20; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  PCCERT_CHAIN_CONTEXT pChainContext; // rdi
  PCERT_SIMPLE_CHAIN v23; // rcx
  PCERT_CHAIN_ELEMENT *rgpElement; // rcx
  const CERT_CONTEXT *pCertContext; // rdi
  const CERT_CONTEXT *v26; // r15
  DWORD NameStringW; // eax
  const char *v28; // r9
  DWORD v29; // esi
  const char *v30; // r9
  LPWSTR v31; // rsi
  HANDLE ProcessHeap; // rax
  LPWSTR v33; // rcx
  LPWSTR v34; // rcx
  unsigned int cbCertEncoded; // edi
  LPWSTR v36; // rcx
  __int64 v37; // r8
  char *v38; // rax
  char *v39; // rdx
  int EfiVariable; // esi
  LPWSTR v41; // rcx
  unsigned __int8 *pbCertEncoded; // r15
  LPWSTR v43; // rcx
  void *v44; // r12
  HANDLE v45; // rax
  void *v46; // rdi
  HANDLE v47; // rax
  int v48; // eax
  void *v49; // rdi
  HANDLE v50; // rax
  int SignatureInDB; // eax
  void *v52; // rdi
  HANDLE v53; // rax
  unsigned int v54; // eax
  size_t v55; // rsi
  unsigned int v56; // r15d
  void *v57; // rdi
  HANDLE v58; // rax
  HANDLE v59; // rax
  GUID *v60; // rax
  GUID *v61; // rdi
  void *v62; // rdi
  HANDLE v63; // rax
  size_t v64; // r12
  GUID *v65; // rsi
  HANDLE v66; // rax
  void *v67; // rdi
  HANDLE v68; // rax
  char *v69; // rcx
  HANDLE v70; // rax
  void *v71; // rdi
  HANDLE v72; // rax
  int v73; // eax
  HANDLE v74; // rax
  void *v75; // rdi
  HANDLE v76; // rax
  int v77; // eax
  int v78; // eax
  HANDLE v79; // rax
  void *v80; // rdi
  HANDLE v81; // rax
  unsigned int v82; // r13d
  HANDLE v83; // rax
  void *v84; // rax
  void *v85; // rsi
  HANDLE v86; // rax
  void *v87; // rdi
  HANDLE v88; // rax
  int v89; // eax
  unsigned int v90; // r12d
  HANDLE v91; // rax
  HANDLE v92; // rax
  void *v93; // rdi
  HANDLE v94; // rax
  void *v95; // rdi
  HANDLE v96; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  bool v101[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  bool v103; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR pszNameString; // [rsp+58h] [rbp-A8h] BYREF
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v106; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbStructInfo; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v109; // [rsp+7Ch] [rbp-84h]
  unsigned __int8 *v110; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  GUID **v112; // [rsp+98h] [rbp-68h]
  unsigned int *v113; // [rsp+A0h] [rbp-60h]
  void *v114[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v115; // [rsp+B8h] [rbp-48h]
  __int64 v116; // [rsp+C8h] [rbp-38h]
  _BYTE *v117; // [rsp+D0h] [rbp-30h]
  _QWORD *v118; // [rsp+D8h] [rbp-28h]
  _WORD *v119; // [rsp+E0h] [rbp-20h]
  _QWORD v120[7]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD pWVTData[6]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v122; // [rsp+138h] [rbp+38h]
  int v123; // [rsp+140h] [rbp+40h]
  _QWORD *v124; // [rsp+148h] [rbp+48h]
  int v125; // [rsp+150h] [rbp+50h]
  HANDLE hStateData; // [rsp+158h] [rbp+58h]
  __int64 v127; // [rsp+168h] [rbp+68h]
  GUID pgActionID; // [rsp+180h] [rbp+80h] BYREF
  char v129[8]; // [rsp+190h] [rbp+90h] BYREF
  char v130[152]; // [rsp+198h] [rbp+98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v109 = a3;
  v117 = a5;
  v118 = a6;
  v119 = a7;
  v112 = a8;
  v113 = a9;
  HIDWORD(Size) = 0;
  v120[4] = "PpfhConstructBootMgFwPcr7DigestAndEventData";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfhConstructBootMgFwPcr7DigestAndEventData");
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *v112 = 0;
  *v113 = 0;
  v103 = 0;
  v101[0] = 0;
  v110 = 0;
  v106 = 0;
  LODWORD(Size) = 0;
  DBAndBootMgFwAuthoritySignatureFromLog = PpfhGetDBAndBootMgFwAuthoritySignatureFromLog(
                                             a2,
                                             a3,
                                             &v103,
                                             v101,
                                             &v110,
                                             &v106,
                                             (unsigned int *)&Size);
  v14 = DBAndBootMgFwAuthoritySignatureFromLog;
  if ( DBAndBootMgFwAuthoritySignatureFromLog < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x891,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)DBAndBootMgFwAuthoritySignatureFromLog,
      dwCreationDisposition);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return v14;
  }
  if ( !v103 || !v101[0] )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x896u,
      "PpfhConstructBootMgFwPcr7DigestAndEventData",
      "DB event or authority event not present");
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return 0;
  }
  FileW = (char *)CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  v120[5] = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x89C,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
                  v17);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  v120[0] = 32;
  v120[3] = 0;
  v120[1] = a1;
  v120[2] = FileW;
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  v122 = 2;
  v125 = 1;
  v127 = 1040;
  v123 = 1;
  v124 = v120;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  v19 = WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  if ( v19 )
  {
    LODWORD(dwFlagsAndAttributes) = v19;
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8B0,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"WinVerifyTrust failed: 0x%x",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  v20 = WTHelperProvDataFromStateData(hStateData);
  if ( !v20 )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8B3,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"WTHelperProvDataFromStateData",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v20, 0, 0, 0);
  if ( !ProvSignerFromChain )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8B5,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"WTHelperGetProvSignerFromChain",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  pChainContext = ProvSignerFromChain->pChainContext;
  if ( !pChainContext )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8BB,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"chainContext == nullptr",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  if ( !pChainContext->cChain )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8BC,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"chainContext->cChain == 0",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    0x8BDu,
    "PpfhConstructBootMgFwPcr7DigestAndEventData",
    "certChain->cChain = 0x%x",
    pChainContext->cChain);
  v23 = *pChainContext->rgpChain;
  if ( v23->cElement < 3 )
  {
    LODWORD(dwFlagsAndAttributes) = v23->cElement;
    LastError = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8BF,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)"chain->cElement < 3 (0x%x)",
      dwFlagsAndAttributes);
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return LastError;
  }
  rgpElement = v23->rgpElement;
  pCertContext = rgpElement[1]->pCertContext;
  v26 = rgpElement[2]->pCertContext;
  NameStringW = CertGetNameStringW(v26, 4u, 0, 0, 0, 0);
  v29 = NameStringW;
  if ( NameStringW )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszNameString,
      0,
      NameStringW,
      v28);
    HIDWORD(Size) = 2;
    if ( !pszNameString )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v30);
    if ( CertGetNameStringW(v26, 4u, 0, 0, pszNameString, v29) )
    {
      dwCreationDispositiona = (int)pszNameString;
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        0x8D3u,
        "PpfhConstructBootMgFwPcr7DigestAndEventData",
        "Root cert subject: %ws");
      if ( !(unsigned int)_o__wcsicmp(pszNameString, L"Microsoft Testing Root Certificate Authority 2010") )
      {
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
          0x8D6u,
          "PpfhConstructBootMgFwPcr7DigestAndEventData",
          "Predicting for test-signed bootmgfw");
        pCertContext = v26;
      }
    }
    v31 = pszNameString;
    if ( pszNameString )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v31);
    }
  }
  if ( (_DWORD)Size == 256 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x8E2u,
      "PpfhConstructBootMgFwPcr7DigestAndEventData",
      "logSignatureSize is EFI_CERT_RSA2048_MODULUS_LENGTH");
    pszNameString = 0;
    pcbStructInfo = 0;
    if ( !CryptDecodeObjectEx(
            pCertContext->dwCertEncodingType,
            (LPCSTR)0x48,
            pCertContext->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
            pCertContext->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
            0x8000u,
            0,
            &pszNameString,
            &pcbStructInfo) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8E8,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
                    v28);
      v33 = pszNameString;
      pszNameString = 0;
      if ( v33 )
        LocalFree(v33);
LABEL_33:
      CloseHandle(FileW);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfhConstructBootMgFwPcr7DigestAndEventData");
      return LastError;
    }
    v34 = pszNameString;
    cbCertEncoded = *((_DWORD *)pszNameString + 3);
    if ( cbCertEncoded != 256 )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E9,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDispositiona);
      v36 = pszNameString;
      pszNameString = 0;
      if ( v36 )
        LocalFree(v36);
      goto LABEL_33;
    }
    v37 = *((unsigned int *)pszNameString + 2);
    v38 = (char *)pszNameString + v37 + 24;
    v39 = v38 + 24;
    if ( v38 + 24 < v38 )
    {
      EfiVariable = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8ED,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)0x80070216LL,
        dwCreationDispositiona);
      v41 = pszNameString;
      pszNameString = 0;
      if ( v41 )
        LocalFree(v41);
LABEL_41:
      CloseHandle(FileW);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfhConstructBootMgFwPcr7DigestAndEventData");
      return (unsigned int)EfiVariable;
    }
    pbCertEncoded = (unsigned __int8 *)&v39[v37];
    if ( &v39[v37] < v39 )
    {
      EfiVariable = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8EF,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)0x80070216LL,
        dwCreationDispositiona);
      v43 = pszNameString;
      pszNameString = 0;
      if ( v43 )
        LocalFree(v43);
      goto LABEL_41;
    }
    pszNameString = 0;
    if ( v34 )
      LocalFree(v34);
  }
  else
  {
    pbCertEncoded = pCertContext->pbCertEncoded;
    cbCertEncoded = pCertContext->cbCertEncoded;
  }
  Src = 0;
  Size = 0;
  lpMem = 0;
  if ( a4 )
  {
    if ( a4 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x906,
        (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        v28);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x907u,
      "PpfhConstructBootMgFwPcr7DigestAndEventData",
      "Calculating authority hash based on PPF log");
    SignatureInDB = PpfhFindSignatureInDB(
                      v110,
                      v106,
                      pbCertEncoded,
                      cbCertEncoded,
                      (unsigned __int8 **)&Src,
                      (unsigned int *)&Size);
    EfiVariable = SignatureInDB;
    if ( SignatureInDB < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x909,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)SignatureInDB,
        dwCreationDispositionb);
      v52 = lpMem;
      lpMem = 0;
      if ( v52 )
      {
        v53 = GetProcessHeap();
        HeapFree(v53, 0, v52);
      }
      goto LABEL_41;
    }
  }
  else
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x8FEu,
      "PpfhConstructBootMgFwPcr7DigestAndEventData",
      "Calculating authority hash based on current DB");
    v114[0] = &lpMem;
    v114[1] = 0;
    LOBYTE(v115) = 1;
    EfiVariable = PpfhGetEfiVariable(&c_efiSecurityNamespace, L"db", &v114[1], (unsigned int *)&Size + 1);
    if ( (_BYTE)v115 )
    {
      v44 = *(void **)v114[0];
      *(_QWORD *)v114[0] = v114[1];
      if ( v44 )
      {
        v45 = GetProcessHeap();
        HeapFree(v45, 0, v44);
      }
    }
    if ( EfiVariable < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x900,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)EfiVariable,
        dwCreationDispositiona);
      v46 = lpMem;
      lpMem = 0;
      if ( v46 )
      {
        v47 = GetProcessHeap();
        HeapFree(v47, 0, v46);
      }
      goto LABEL_41;
    }
    v48 = PpfhFindSignatureInDB(
            (unsigned __int8 *)lpMem,
            HIDWORD(Size),
            pbCertEncoded,
            cbCertEncoded,
            (unsigned __int8 **)&Src,
            (unsigned int *)&Size);
    EfiVariable = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x902,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v48,
        dwCreationDispositionb);
      v49 = lpMem;
      lpMem = 0;
      if ( v49 )
      {
        v50 = GetProcessHeap();
        HeapFree(v50, 0, v49);
      }
      goto LABEL_41;
    }
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"db");
  v54 = DestinationString.Length + 32;
  v55 = (unsigned int)Size;
  v56 = v54 + Size;
  if ( v54 + (unsigned int)Size < v54 )
  {
    EfiVariable = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x919,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x80070216LL,
      dwCreationDispositionb);
    v57 = lpMem;
    lpMem = 0;
    if ( v57 )
    {
      v58 = GetProcessHeap();
      HeapFree(v58, 0, v57);
    }
    goto LABEL_41;
  }
  v59 = GetProcessHeap();
  v60 = (GUID *)HeapAlloc(v59, 0, v56);
  v61 = v60;
  v110 = (unsigned __int8 *)v60;
  if ( !v60 )
  {
    EfiVariable = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91C,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositionb);
    v62 = lpMem;
    lpMem = 0;
    if ( v62 )
    {
      v63 = GetProcessHeap();
      HeapFree(v63, 0, v62);
    }
    goto LABEL_41;
  }
  *v60 = c_efiSecurityNamespace;
  *(_QWORD *)&v60[1].Data1 = (unsigned __int64)DestinationString.Length >> 1;
  v64 = v55;
  *(_QWORD *)v60[1].Data4 = v55;
  v65 = v60 + 2;
  if ( &v60[2] < v60 )
  {
    EfiVariable = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x924,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x80070216LL,
      dwCreationDispositionb);
    v66 = GetProcessHeap();
    HeapFree(v66, 0, v61);
    v67 = lpMem;
    lpMem = 0;
    if ( v67 )
    {
      v68 = GetProcessHeap();
      HeapFree(v68, 0, v67);
    }
    goto LABEL_41;
  }
  memcpy_0(&v60[2], DestinationString.Buffer, DestinationString.Length);
  v69 = (char *)v65 + DestinationString.Length;
  if ( v69 < (char *)v65 )
  {
    EfiVariable = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x928,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x80070216LL,
      dwCreationDispositionb);
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v61);
    v71 = lpMem;
    lpMem = 0;
    if ( v71 )
    {
      v72 = GetProcessHeap();
      HeapFree(v72, 0, v71);
    }
    goto LABEL_41;
  }
  memcpy_0(v69, Src, v64);
  *(_OWORD *)v114 = 0;
  v115 = 0;
  v116 = 0;
  v73 = PpfEvtLogIteratorInitialize(a2, v109, v114, v101);
  if ( v73 < 0 )
  {
    EfiVariable = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x931,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
                    (const char *)(unsigned int)v73,
                    dwCreationDispositionb);
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v61);
    v75 = lpMem;
    lpMem = 0;
    if ( v75 )
    {
      v76 = GetProcessHeap();
      HeapFree(v76, 0, v75);
    }
    goto LABEL_41;
  }
  v129[0] = 0;
  v77 = PpfEvtLogSoftwarePcrInitialize((unsigned __int16)v116, v130);
  if ( v77 >= 0 )
  {
    v129[0] = 1;
  }
  else
  {
    v78 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x100,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
            (const char *)(unsigned int)v77,
            dwCreationDispositionb);
    EfiVariable = v78;
    if ( v78 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x934,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v78,
        dwCreationDispositionb);
      TpmSoftwarePcr::~TpmSoftwarePcr((TpmSoftwarePcr *)v129);
      v79 = GetProcessHeap();
      HeapFree(v79, 0, v61);
      v80 = lpMem;
      lpMem = 0;
      if ( v80 )
      {
        v81 = GetProcessHeap();
        HeapFree(v81, 0, v80);
      }
      goto LABEL_41;
    }
  }
  v82 = WORD1(v116);
  v83 = GetProcessHeap();
  v84 = HeapAlloc(v83, 8u, v82);
  v85 = v84;
  Src = v84;
  if ( !v84 )
  {
    EfiVariable = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x936,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositionb);
    TpmSoftwarePcr::~TpmSoftwarePcr((TpmSoftwarePcr *)v129);
    v86 = GetProcessHeap();
    HeapFree(v86, 0, v61);
    v87 = lpMem;
    lpMem = 0;
    if ( v87 )
    {
      v88 = GetProcessHeap();
      HeapFree(v88, 0, v87);
    }
    goto LABEL_41;
  }
  v89 = TpmSoftwarePcr::Hash((TpmSoftwarePcr *)v129, v61, v56, (unsigned __int8 *)v84);
  v90 = v89;
  if ( v89 >= 0 )
  {
    *v117 = 1;
    *v118 = v85;
    *v119 = v82;
    *v112 = v61;
    *v113 = v56;
    TpmSoftwarePcr::~TpmSoftwarePcr((TpmSoftwarePcr *)v129);
    v95 = lpMem;
    lpMem = 0;
    if ( v95 )
    {
      v96 = GetProcessHeap();
      HeapFree(v96, 0, v95);
    }
    CloseHandle(FileW);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfhConstructBootMgFwPcr7DigestAndEventData");
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x937,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    (const char *)(unsigned int)v89,
    dwCreationDispositionb);
  v91 = GetProcessHeap();
  HeapFree(v91, 0, v85);
  TpmSoftwarePcr::~TpmSoftwarePcr((TpmSoftwarePcr *)v129);
  v92 = GetProcessHeap();
  HeapFree(v92, 0, v61);
  v93 = lpMem;
  lpMem = 0;
  if ( v93 )
  {
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v93);
  }
  CloseHandle(FileW);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfhConstructBootMgFwPcr7DigestAndEventData");
  return v90;
}

```

## disassembly

```asm
0x18002ee74  mov     [rsp-8+arg_18], rbx
0x18002ee79  push    rbp
0x18002ee7a  push    rsi
0x18002ee7b  push    rdi
0x18002ee7c  push    r12
0x18002ee7e  push    r13
0x18002ee80  push    r14
0x18002ee82  push    r15
0x18002ee84  lea     rbp, [rsp-140h]
0x18002ee8c  sub     rsp, 240h
0x18002ee93  mov     rax, cs:__security_cookie
0x18002ee9a  xor     rax, rsp
0x18002ee9d  mov     [rbp+170h+var_40], rax
0x18002eea4  mov     r12d, r9d
0x18002eea7  mov     ebx, r8d
0x18002eeaa  mov     [rsp+270h+var_1F4], ebx
0x18002eeae  mov     r13, rdx
0x18002eeb1  mov     rdi, rcx
0x18002eeb4  mov     rsi, [rbp+170h+arg_20]
0x18002eebb  mov     [rbp+170h+var_1A0], rsi
0x18002eebf  mov     r14, [rbp+170h+arg_28]
0x18002eec6  mov     [rbp+170h+var_198], r14
0x18002eeca  mov     r15, [rbp+170h+arg_30]
0x18002eed1  mov     [rbp+170h+var_190], r15
0x18002eed5  mov     rax, [rbp+170h+arg_38]
0x18002eedc  mov     [rbp+170h+var_1D8], rax
0x18002eee0  mov     rax, [rbp+170h+arg_40]
0x18002eee7  mov     [rbp+170h+var_1D0], rax
0x18002eeeb  mov     dword ptr [rsp+270h+Size+4], 0
0x18002eef3  lea     rax, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002eefa  mov     [rbp+170h+var_168], rax
0x18002eefe  mov     qword ptr [rsp+270h+dwCreationDisposition], rax
0x18002ef03  lea     r9, aEnteringHs; "Entering %hs"
0x18002ef0a  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18002ef11  mov     edx, 84h; unsigned int
0x18002ef16  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002ef1d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002ef22  nop
0x18002ef23  mov     byte ptr [rsi], 0
0x18002ef26  xor     esi, esi
0x18002ef28  mov     [r14], rsi
0x18002ef2b  mov     [r15], si
0x18002ef2f  mov     rax, [rbp+170h+var_1D8]
0x18002ef33  mov     [rax], rsi
0x18002ef36  mov     rax, [rbp+170h+var_1D0]
0x18002ef3a  mov     [rax], esi
0x18002ef3c  mov     [rsp+270h+var_220], sil
0x18002ef41  mov     [rsp+270h+var_230], sil
0x18002ef46  mov     [rbp+170h+var_1F0], rsi
0x18002ef4a  mov     [rsp+270h+var_208], esi
0x18002ef4e  mov     dword ptr [rsp+270h+Size], esi
0x18002ef52  lea     rax, [rsp+270h+Size]
0x18002ef57  mov     [rsp+270h+hTemplateFile], rax; unsigned int *
0x18002ef5c  lea     rax, [rsp+270h+var_208]
0x18002ef61  mov     qword ptr [rsp+270h+dwFlagsAndAttributes], rax; unsigned int *
0x18002ef66  lea     rax, [rbp+170h+var_1F0]
0x18002ef6a  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002ef6f  lea     r9, [rsp+270h+var_230]; bool *
0x18002ef74  lea     r8, [rsp+270h+var_220]; bool *
0x18002ef79  mov     edx, ebx; unsigned int
0x18002ef7b  mov     rcx, r13; unsigned __int8 *
0x18002ef7e  call    ?PpfhGetDBAndBootMgFwAuthoritySignatureFromLog@@YAJPEAEIPEA_N1PEAPEAEPEAI3@Z; PpfhGetDBAndBootMgFwAuthoritySignatureFromLog(uchar *,uint,bool *,bool *,uchar * *,uint *,uint *)
0x18002ef83  mov     ebx, eax
0x18002ef85  test    eax, eax
0x18002ef87  jns     short loc_18002EFD8
0x18002ef89  mov     rcx, [rbp+178h]; this
0x18002ef90  mov     r9d, eax; char *
0x18002ef93  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002ef9a  mov     edx, 891h; void *
0x18002ef9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002efa4  nop
0x18002efa5  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002efac  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002efb1  lea     r9, aLeavingHs; "Leaving %hs"
0x18002efb8  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002efbf  mov     edx, 89h; unsigned int
0x18002efc4  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002efcb  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002efd0  nop
0x18002efd1  mov     eax, ebx
0x18002efd3  jmp     loc_18003034E
0x18002efd8  cmp     [rsp+270h+var_220], sil
0x18002efdd  jz      loc_180030304
0x18002efe3  cmp     [rsp+270h+var_230], sil
0x18002efe8  jz      loc_180030304
0x18002efee  mov     [rsp+270h+hTemplateFile], rsi; hTemplateFile
0x18002eff3  mov     [rsp+270h+dwFlagsAndAttributes], 80h; char *
0x18002effb  mov     [rsp+270h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f003  xor     r9d, r9d; lpSecurityAttributes
0x18002f006  mov     edx, 80000000h; dwDesiredAccess
0x18002f00b  lea     r8d, [r9+5]; dwShareMode
0x18002f00f  mov     rcx, rdi; lpFileName
0x18002f012  call    cs:__imp_CreateFileW
0x18002f019  nop     dword ptr [rax+rax+00h]
0x18002f01e  mov     rbx, rax
0x18002f021  mov     [rbp+170h+var_160], rax
0x18002f025  inc     rax
0x18002f028  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f02e  jnz     short loc_18002F097
0x18002f030  mov     rcx, [rbp+178h]; this
0x18002f037  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f03e  mov     edx, 89Ch; void *
0x18002f043  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f048  mov     edi, eax
0x18002f04a  lea     rcx, [rbx-1]
0x18002f04e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002f052  ja      short loc_18002F064
0x18002f054  mov     rcx, rbx; hObject
0x18002f057  call    cs:__imp_CloseHandle
0x18002f05e  nop     dword ptr [rax+rax+00h]
0x18002f063  nop
0x18002f064  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f06b  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f070  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f077  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f07e  mov     edx, 89h; unsigned int
0x18002f083  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f08a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f08f  nop
0x18002f090  mov     eax, edi
0x18002f092  jmp     loc_18003034E
0x18002f097  mov     [rbp+170h+var_188], 20h ; ' '
0x18002f09f  mov     [rbp+170h+var_170], rsi
0x18002f0a3  mov     [rbp+170h+var_180], rdi
0x18002f0a7  mov     [rbp+170h+var_178], rbx
0x18002f0ab  mov     edi, 58h ; 'X'
0x18002f0b0  mov     r8d, edi; Size
0x18002f0b3  xor     edx, edx; Val
0x18002f0b5  lea     rcx, [rbp+170h+pWVTData]; void *
0x18002f0b9  call    memset_0
0x18002f0be  mov     [rbp+170h+pWVTData], edi
0x18002f0c1  mov     [rbp+170h+var_138], 2
0x18002f0c9  lea     eax, [rdi-57h]
0x18002f0cc  mov     [rbp+170h+var_120], eax
0x18002f0cf  mov     [rbp+170h+var_108], 410h
0x18002f0d7  mov     [rbp+170h+var_130], eax
0x18002f0da  lea     rax, [rbp+170h+var_188]
0x18002f0de  mov     [rbp+170h+var_128], rax
0x18002f0e2  mov     [rbp+170h+pgActionID.Data1], 0AAC56Bh
0x18002f0ec  mov     dword ptr [rbp+170h+pgActionID.Data2], 11D0CD44h
0x18002f0f6  mov     dword ptr [rbp+170h+pgActionID.Data4], 0C000C28Ch
0x18002f100  mov     dword ptr [rbp+170h+pgActionID.Data4+4], 0EE95C24Fh
0x18002f10a  lea     r8, [rbp+170h+pWVTData]; pWVTData
0x18002f10e  lea     rdx, [rbp+170h+pgActionID]; pgActionID
0x18002f115  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18002f119  call    cs:__imp_WinVerifyTrust
0x18002f120  nop     dword ptr [rax+rax+00h]
0x18002f125  test    eax, eax
0x18002f127  jz      short loc_18002F19B
0x18002f129  mov     rcx, [rbp+178h]; this
0x18002f130  mov     [rsp+270h+dwFlagsAndAttributes], eax; char *
0x18002f134  lea     rax, aWinverifytrust_0; "WinVerifyTrust failed: 0x%x"
0x18002f13b  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f140  mov     edi, 8000FFFFh
0x18002f145  mov     r9d, edi; char *
0x18002f148  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f14f  mov     edx, 8B0h; void *
0x18002f154  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f159  nop
0x18002f15a  mov     rcx, rbx; hObject
0x18002f15d  call    cs:__imp_CloseHandle
0x18002f164  nop     dword ptr [rax+rax+00h]
0x18002f169  nop
0x18002f16a  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f171  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f176  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f17d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f184  mov     edx, 89h; unsigned int
0x18002f189  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f190  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f195  nop
0x18002f196  jmp     loc_18002F090
0x18002f19b  mov     rcx, [rbp+170h+hStateData]; hStateData
0x18002f19f  call    cs:__imp_WTHelperProvDataFromStateData
0x18002f1a6  nop     dword ptr [rax+rax+00h]
0x18002f1ab  test    rax, rax
0x18002f1ae  jnz     short loc_18002F21E
0x18002f1b0  mov     rcx, [rbp+178h]; this
0x18002f1b7  lea     rax, aWthelperprovda_0; "WTHelperProvDataFromStateData"
0x18002f1be  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f1c3  mov     edi, 8000FFFFh
0x18002f1c8  mov     r9d, edi; char *
0x18002f1cb  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f1d2  mov     edx, 8B3h; void *
0x18002f1d7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f1dc  nop
0x18002f1dd  mov     rcx, rbx; hObject
0x18002f1e0  call    cs:__imp_CloseHandle
0x18002f1e7  nop     dword ptr [rax+rax+00h]
0x18002f1ec  nop
0x18002f1ed  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f1f4  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f1f9  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f200  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f207  mov     edx, 89h; unsigned int
0x18002f20c  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f213  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f218  nop
0x18002f219  jmp     loc_18002F090
0x18002f21e  xor     r9d, r9d; idxCounterSigner
0x18002f221  xor     r8d, r8d; fCounterSigner
0x18002f224  xor     edx, edx; idxSigner
0x18002f226  mov     rcx, rax; pProvData
0x18002f229  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18002f230  nop     dword ptr [rax+rax+00h]
0x18002f235  test    rax, rax
0x18002f238  jnz     short loc_18002F2A8
0x18002f23a  mov     rcx, [rbp+178h]; this
0x18002f241  lea     rax, aWthelpergetpro_0; "WTHelperGetProvSignerFromChain"
0x18002f248  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f24d  mov     edi, 8000FFFFh
0x18002f252  mov     r9d, edi; char *
0x18002f255  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f25c  mov     edx, 8B5h; void *
0x18002f261  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f266  nop
0x18002f267  mov     rcx, rbx; hObject
0x18002f26a  call    cs:__imp_CloseHandle
0x18002f271  nop     dword ptr [rax+rax+00h]
0x18002f276  nop
0x18002f277  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f27e  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f283  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f28a  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f291  mov     edx, 89h; unsigned int
0x18002f296  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f29d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f2a2  nop
0x18002f2a3  jmp     loc_18002F090
0x18002f2a8  mov     rdi, [rax+38h]
0x18002f2ac  test    rdi, rdi
0x18002f2af  jnz     short loc_18002F31F
0x18002f2b1  mov     rcx, [rbp+178h]; this
0x18002f2b8  lea     rax, aChaincontextNu; "chainContext == nullptr"
0x18002f2bf  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f2c4  mov     edi, 8000FFFFh
0x18002f2c9  mov     r9d, edi; char *
0x18002f2cc  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f2d3  mov     edx, 8BBh; void *
0x18002f2d8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f2dd  nop
0x18002f2de  mov     rcx, rbx; hObject
0x18002f2e1  call    cs:__imp_CloseHandle
0x18002f2e8  nop     dword ptr [rax+rax+00h]
0x18002f2ed  nop
0x18002f2ee  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f2f5  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f2fa  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f301  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f308  mov     edx, 89h; unsigned int
0x18002f30d  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f314  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f319  nop
0x18002f31a  jmp     loc_18002F090
0x18002f31f  mov     eax, [rdi+0Ch]
0x18002f322  test    eax, eax
0x18002f324  jnz     short loc_18002F394
0x18002f326  mov     rcx, [rbp+178h]; this
0x18002f32d  lea     rax, aChaincontextCc; "chainContext->cChain == 0"
0x18002f334  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f339  mov     edi, 8000FFFFh
0x18002f33e  mov     r9d, edi; char *
0x18002f341  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f348  mov     edx, 8BCh; void *
0x18002f34d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f352  nop
0x18002f353  mov     rcx, rbx; hObject
0x18002f356  call    cs:__imp_CloseHandle
0x18002f35d  nop     dword ptr [rax+rax+00h]
0x18002f362  nop
0x18002f363  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f36a  mov     qword ptr [rsp+270h+dwCreationDisposition], r15
0x18002f36f  lea     r9, aLeavingHs; "Leaving %hs"
0x18002f376  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18002f37d  mov     edx, 89h; unsigned int
0x18002f382  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f389  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f38e  nop
0x18002f38f  jmp     loc_18002F090
0x18002f394  mov     [rsp+270h+dwCreationDisposition], eax
0x18002f398  lea     r9, aCertchainCchai; "certChain->cChain = 0x%x"
0x18002f39f  lea     r15, aPpfhconstructb_0; "PpfhConstructBootMgFwPcr7DigestAndEvent"...
0x18002f3a6  mov     r8, r15; char *
0x18002f3a9  mov     edx, 8BDh; unsigned int
0x18002f3ae  lea     r14, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002f3b5  mov     rcx, r14; char *
0x18002f3b8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18002f3bd  mov     rax, [rdi+10h]
0x18002f3c1  mov     rcx, [rax]
0x18002f3c4  mov     eax, [rcx+0Ch]
0x18002f3c7  cmp     eax, 3
0x18002f3ca  jnb     short loc_18002F433
0x18002f3cc  mov     rcx, [rbp+178h]; this
0x18002f3d3  mov     [rsp+270h+dwFlagsAndAttributes], eax; char *
0x18002f3d7  lea     rax, aChainCelement3; "chain->cElement < 3 (0x%x)"
0x18002f3de  mov     qword ptr [rsp+270h+dwCreationDisposition], rax; int
0x18002f3e3  mov     edi, 8000FFFFh
0x18002f3e8  mov     r9d, edi; char *
0x18002f3eb  mov     r8, r14; unsigned int
0x18002f3ee  mov     edx, 8BFh; void *
  ... truncated ...
```
