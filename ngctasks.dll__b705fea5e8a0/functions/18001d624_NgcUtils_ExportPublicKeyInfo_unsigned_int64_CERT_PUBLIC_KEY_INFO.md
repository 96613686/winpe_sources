# NgcUtils::ExportPublicKeyInfo(unsigned __int64,_CERT_PUBLIC_KEY_INFO * *)

- ea: `0x18001d624`
- end: `0x18001d741`
- name: `?ExportPublicKeyInfo@NgcUtils@@YAJ_KPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey, PCERT_PUBLIC_KEY_INFO *, struct _CERT_PUBLIC_KEY_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cff4`

## callees

- `0x18000cc14`
- `0x18000cc34`
- `0x180017440`
- `0x18001d624`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d721`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d721`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d66b`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d6f7`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d66b`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001d6f7`

## string_xrefs

- `0x18001d67a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001d6b5`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001d706`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::ExportPublicKeyInfo(
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey,
        PCERT_PUBLIC_KEY_INFO *a2,
        struct _CERT_PUBLIC_KEY_INFO **a3)
{
  const char *v5; // r9
  PCERT_PUBLIC_KEY_INFO v7; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  DWORD dwFlags; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbInfo; // [rsp+60h] [rbp+18h] BYREF
  PCERT_PUBLIC_KEY_INFO pInfo; // [rsp+68h] [rbp+20h] BYREF

  pcbInfo = 0;
  if ( !CryptExportPublicKeyInfoEx(hCryptProvOrNCryptKey, 0, 1u, 0, 0, 0, 0, &pcbInfo) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x246,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             v5);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&pInfo, pcbInfo);
  v7 = pInfo;
  if ( pInfo )
  {
    if ( CryptExportPublicKeyInfoEx(hCryptProvOrNCryptKey, 0, 1u, 0, 0, 0, pInfo, &pcbInfo) )
    {
      *a2 = v7;
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x254,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
                    v8);
      if ( v7 )
        LocalFree(v7);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001d624  mov     r11, rsp
0x18001d627  mov     [r11+8], rbx
0x18001d62b  mov     [r11+10h], rsi
0x18001d62f  push    rdi
0x18001d630  sub     rsp, 40h
0x18001d634  mov     rdi, rdx
0x18001d637  mov     rsi, rcx
0x18001d63a  mov     [rsp+48h+arg_10], 0
0x18001d642  lea     rax, [r11+18h]
0x18001d646  mov     [r11-10h], rax
0x18001d64a  mov     qword ptr [r11-18h], 0
0x18001d652  mov     qword ptr [r11-20h], 0
0x18001d65a  mov     [rsp+48h+dwFlags], 0; int
0x18001d662  xor     r9d, r9d; pszPublicKeyObjId
0x18001d665  xor     edx, edx; dwKeySpec
0x18001d667  lea     r8d, [r9+1]; dwCertEncodingType
0x18001d66b  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001d671  test    eax, eax
0x18001d673  jnz     short loc_18001D690
0x18001d675  mov     rcx, [rsp+48h]; this
0x18001d67a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d681  mov     edx, 246h; void *
0x18001d686  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d68b  jmp     loc_18001D731
0x18001d690  mov     edx, [rsp+48h+arg_10]
0x18001d694  lea     rcx, [rsp+48h+arg_18]
0x18001d699  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001d69e  mov     rbx, [rsp+48h+arg_18]
0x18001d6a3  test    rbx, rbx
0x18001d6a6  jnz     short loc_18001D6CB
0x18001d6a8  mov     rcx, [rsp+48h]; this
0x18001d6ad  mov     ebx, 8007000Eh
0x18001d6b2  mov     r9d, ebx; char *
0x18001d6b5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d6bc  mov     edx, 249h; void *
0x18001d6c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6c6  nop
0x18001d6c7  mov     eax, ebx
0x18001d6c9  jmp     short loc_18001D731
0x18001d6cb  lea     rax, [rsp+48h+arg_10]
0x18001d6d0  mov     [rsp+48h+pcbInfo], rax; pcbInfo
0x18001d6d5  mov     [rsp+48h+pInfo], rbx; pInfo
0x18001d6da  mov     [rsp+48h+pvAuxInfo], 0; pvAuxInfo
0x18001d6e3  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18001d6eb  xor     r9d, r9d; pszPublicKeyObjId
0x18001d6ee  xor     edx, edx; dwKeySpec
0x18001d6f0  lea     r8d, [r9+1]; dwCertEncodingType
0x18001d6f4  mov     rcx, rsi; hCryptProvOrNCryptKey
0x18001d6f7  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001d6fd  test    eax, eax
0x18001d6ff  jnz     short loc_18001D72C
0x18001d701  mov     rcx, [rsp+48h]; this
0x18001d706  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d70d  mov     edx, 254h; void *
0x18001d712  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d717  mov     edi, eax
0x18001d719  test    rbx, rbx
0x18001d71c  jz      short loc_18001D728
0x18001d71e  mov     rcx, rbx; hMem
0x18001d721  call    cs:__imp_LocalFree
0x18001d727  nop
0x18001d728  mov     eax, edi
0x18001d72a  jmp     short loc_18001D731
0x18001d72c  mov     [rdi], rbx
0x18001d72f  xor     eax, eax
0x18001d731  mov     rbx, [rsp+48h+arg_0]
0x18001d736  mov     rsi, [rsp+48h+arg_8]
0x18001d73b  add     rsp, 40h
0x18001d73f  pop     rdi
0x18001d740  retn
```
