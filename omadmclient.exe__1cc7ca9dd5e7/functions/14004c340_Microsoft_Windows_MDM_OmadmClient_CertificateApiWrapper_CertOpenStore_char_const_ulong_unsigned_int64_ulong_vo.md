# Microsoft::Windows::MDM::OmadmClient::CertificateApiWrapper::CertOpenStore(char const *,ulong,unsigned __int64,ulong,void const *,void * *)

- ea: `0x14004c340`
- end: `0x14004c3a0`
- name: `?CertOpenStore@CertificateApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBDK_KKPEBXPEAPEAX@Z`
- size: `96`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::CertificateApiWrapper *__hidden this, const char *, unsigned int, unsigned __int64, unsigned int, const void *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14004c340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c37d`
- `CRYPT32!CertOpenStore` at `0x14004c364`
- `CRYPT32!CertOpenStore` at `0x14004c364`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateApiWrapper::CertOpenStore(
        Microsoft::Windows::MDM::OmadmClient::CertificateApiWrapper *this,
        const char *a2,
        DWORD a3,
        HCRYPTPROV_LEGACY a4,
        DWORD dwFlags,
        void *pvPara,
        void **a7)
{
  HCERTSTORE v7; // rax
  int result; // eax

  v7 = CertOpenStore(a2, a3, a4, dwFlags, pvPara);
  *a7 = v7;
  if ( v7 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004c340  push    rbx
0x14004c342  sub     rsp, 30h
0x14004c346  mov     rax, [rsp+38h+arg_28]
0x14004c34b  mov     r10, r9
0x14004c34e  mov     r9d, [rsp+38h+dwFlags]; dwFlags
0x14004c353  mov     r11d, r8d
0x14004c356  mov     rcx, rdx; lpszStoreProvider
0x14004c359  mov     [rsp+38h+pvPara], rax; pvPara
0x14004c35e  mov     r8, r10; hCryptProv
0x14004c361  mov     edx, r11d; dwEncodingType
0x14004c364  call    cs:__imp_CertOpenStore
0x14004c36b  nop     dword ptr [rax+rax+00h]
0x14004c370  mov     rcx, [rsp+38h+arg_30]
0x14004c375  mov     [rcx], rax
0x14004c378  test    rax, rax
0x14004c37b  jnz     short loc_14004C397
0x14004c37d  call    cs:__imp_GetLastError
0x14004c384  nop     dword ptr [rax+rax+00h]
0x14004c389  test    eax, eax
0x14004c38b  jle     short loc_14004C399
0x14004c38d  movzx   eax, ax
0x14004c390  or      eax, 80070000h
0x14004c395  jmp     short loc_14004C399
0x14004c397  xor     eax, eax
0x14004c399  add     rsp, 30h
0x14004c39d  pop     rbx
0x14004c39e  retn
```
