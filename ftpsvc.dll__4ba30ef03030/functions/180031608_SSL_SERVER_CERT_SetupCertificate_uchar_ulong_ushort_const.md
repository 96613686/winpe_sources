# SSL_SERVER_CERT::SetupCertificate(uchar *,ulong,ushort const *)

- ea: `0x180031608`
- end: `0x18003189b`
- name: `?SetupCertificate@SSL_SERVER_CERT@@QEAAJPEAEKPEBG@Z`
- size: `659`
- prototype: `__int64 __fastcall(SSL_SERVER_CERT *__hidden this, unsigned __int8 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180031238`

## callees

- `0x180030cc0`
- `0x180030f68`
- `0x180031608`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031723`
- `KERNEL32!GetLastError` at `0x180031723`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180031858`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180031873`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180031858`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180031873`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800316b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800316b5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180031686`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180031686`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180031786`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800317f3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180031786`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800317f3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800317c0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180031831`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800317c0`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180031831`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003184c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180031867`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003184c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180031867`
- `CRYPT32!CertFindCertificateInStore` at `0x180031714`
- `CRYPT32!CertFindCertificateInStore` at `0x180031714`
- `CRYPT32!CertNameToStrA` at `0x180031779`
- `CRYPT32!CertNameToStrA` at `0x1800317b1`
- `CRYPT32!CertNameToStrA` at `0x1800317e6`
- `CRYPT32!CertNameToStrA` at `0x180031822`
- `CRYPT32!CertNameToStrA` at `0x180031779`
- `CRYPT32!CertNameToStrA` at `0x1800317b1`
- `CRYPT32!CertNameToStrA` at `0x1800317e6`
- `CRYPT32!CertNameToStrA` at `0x180031822`
- `CRYPT32!CertGetPublicKeyLength` at `0x180031750`
- `CRYPT32!CertGetPublicKeyLength` at `0x180031750`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SSL_SERVER_CERT::SetupCertificate(
        SSL_SERVER_CERT *this,
        unsigned __int8 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  int v7; // ebx
  struct SSL_CERT_STORE *v8; // rcx
  PCCERT_CONTEXT CertificateInStore; // rax
  signed int LastError; // eax
  __int16 PublicKeyLength; // ax
  DWORD v12; // eax
  DWORD v13; // eax
  struct SSL_CERT_STORE *v15; // [rsp+30h] [rbp-D0h] BYREF
  __int128 pvFindPara; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPSTR psz; // [rsp+68h] [rbp-98h]
  DWORD csz; // [rsp+70h] [rbp-90h]
  __int16 v20; // [rsp+74h] [rbp-8Ch]
  _BYTE v21[56]; // [rsp+78h] [rbp-88h] BYREF
  char v22; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[127]; // [rsp+B1h] [rbp-4Fh] BYREF
  unsigned __int16 v24[256]; // [rsp+130h] [rbp+30h] BYREF

  memset_0(v23, 0, sizeof(v23));
  v22 = 0;
  psz = &v22;
  csz = 128;
  v20 = 256;
  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v21, v24, 0x100u);
  v15 = 0;
  pvFindPara = 0;
  if ( a4 && *a4 )
  {
    v7 = STRU::Copy((STRU *)v21, a4);
    if ( v7 < 0 )
      goto LABEL_14;
    v7 = SSL_CERT_STORE::OpenStore((struct STRU *)v21, &v15);
    if ( v7 < 0 )
      goto LABEL_14;
    v8 = v15;
    *((_QWORD *)this + 3) = v15;
    LODWORD(pvFindPara) = 20;
    *((_QWORD *)&pvFindPara + 1) = a2;
    CertificateInStore = CertFindCertificateInStore(*((HCERTSTORE *)v8 + 4), 1u, 0, 0x10000u, &pvFindPara, 0);
    *((_QWORD *)this + 2) = CertificateInStore;
    if ( CertificateInStore )
    {
      PublicKeyLength = CertGetPublicKeyLength(0x10001u, &CertificateInStore->pCertInfo->SubjectPublicKeyInfo);
      *((_WORD *)this + 20) = PublicKeyLength;
      if ( PublicKeyLength )
      {
        v12 = CertNameToStrA(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 48LL), 3u, 0, 0);
        if ( BUFFER::Resize((BUFFER *)v17, v12) )
        {
          CertNameToStrA(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 48LL), 3u, psz, csz);
          v7 = STRA::Copy((SSL_SERVER_CERT *)((char *)this + 48), psz);
          if ( v7 < 0 )
          {
LABEL_14:
            STRU::~STRU(v21);
            BUFFER::~BUFFER((BUFFER *)v17);
            return (unsigned int)v7;
          }
          v13 = CertNameToStrA(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 80LL), 3u, 0, 0);
          if ( BUFFER::Resize((BUFFER *)v17, v13) )
          {
            CertNameToStrA(0x10001u, (PCERT_NAME_BLOB)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 80LL), 3u, psz, csz);
            v7 = STRA::Copy((SSL_SERVER_CERT *)((char *)this + 104), psz);
            if ( v7 >= 0 )
              v7 = SSL_SERVER_CERT::AcquireCredentials(this);
            goto LABEL_14;
          }
        }
      }
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_14;
  }
  STRU::~STRU(v21);
  BUFFER::~BUFFER((BUFFER *)v17);
  return 2147942402LL;
}

```

## disassembly

```asm
0x180031608  push    rbp
0x18003160a  push    rbx
0x18003160b  push    rsi
0x18003160c  push    rdi
0x18003160d  push    r14
0x18003160f  lea     rbp, [rsp-240h]
0x180031617  sub     rsp, 340h
0x18003161e  mov     rax, cs:__security_cookie
0x180031625  xor     rax, rsp
0x180031628  mov     [rbp+260h+var_30], rax
0x18003162f  mov     rbx, r9
0x180031632  mov     rsi, rdx
0x180031635  mov     rdi, rcx
0x180031638  xor     edx, edx; Val
0x18003163a  lea     r8d, [rdx+7Fh]; Size
0x18003163e  lea     rcx, [rbp+260h+var_2AF]; void *
0x180031642  call    memset_0
0x180031647  xor     r14d, r14d
0x18003164a  mov     [rbp+260h+var_2B0], r14b
0x18003164e  lea     rax, [rbp+260h+var_2B0]
0x180031652  mov     [rsp+360h+psz], rax
0x180031657  mov     [rsp+360h+csz], 80h
0x18003165f  mov     [rsp+360h+var_2EC], 100h
0x180031666  xor     edx, edx; Val
0x180031668  mov     r8d, 200h; Size
0x18003166e  lea     rcx, [rbp+260h+var_230]; void *
0x180031672  call    memset_0
0x180031677  mov     r8d, 100h
0x18003167d  lea     rdx, [rbp+260h+var_230]
0x180031681  lea     rcx, [rsp+360h+var_2E8]
0x180031686  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003168c  nop
0x18003168d  mov     [rsp+360h+var_330], r14
0x180031692  xorps   xmm0, xmm0
0x180031695  movups  [rsp+360h+var_328], xmm0
0x18003169a  test    rbx, rbx
0x18003169d  jz      loc_180031862
0x1800316a3  cmp     [rbx], r14w
0x1800316a7  jz      loc_180031862
0x1800316ad  mov     rdx, rbx
0x1800316b0  lea     rcx, [rsp+360h+var_2E8]
0x1800316b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800316bb  mov     ebx, eax
0x1800316bd  test    eax, eax
0x1800316bf  js      loc_180031847
0x1800316c5  lea     rdx, [rsp+360h+var_330]; struct SSL_CERT_STORE **
0x1800316ca  lea     rcx, [rsp+360h+var_2E8]; struct STRU *
0x1800316cf  call    ?OpenStore@SSL_CERT_STORE@@SAJAEAVSTRU@@PEAPEAV1@@Z; SSL_CERT_STORE::OpenStore(STRU &,SSL_CERT_STORE * *)
0x1800316d4  mov     ebx, eax
0x1800316d6  test    eax, eax
0x1800316d8  js      loc_180031847
0x1800316de  mov     rcx, [rsp+360h+var_330]
0x1800316e3  mov     [rdi+18h], rcx
0x1800316e7  mov     dword ptr [rsp+360h+var_328], 14h
0x1800316ef  mov     qword ptr [rsp+360h+var_328+8], rsi
0x1800316f4  mov     [rsp+360h+pPrevCertContext], r14; pPrevCertContext
0x1800316f9  lea     rax, [rsp+360h+var_328]
0x1800316fe  mov     [rsp+360h+pvFindPara], rax; pvFindPara
0x180031703  mov     r9d, 10000h; dwFindType
0x180031709  xor     r8d, r8d; dwFindFlags
0x18003170c  lea     edx, [r14+1]; dwCertEncodingType
0x180031710  mov     rcx, [rcx+20h]; hCertStore
0x180031714  call    cs:__imp_CertFindCertificateInStore
0x18003171a  mov     [rdi+10h], rax
0x18003171e  test    rax, rax
0x180031721  jnz     short loc_180031741
0x180031723  call    cs:__imp_GetLastError
0x180031729  mov     ebx, eax
0x18003172b  test    eax, eax
0x18003172d  jle     loc_180031847
0x180031733  movzx   ebx, ax
0x180031736  or      ebx, 80070000h
0x18003173c  jmp     loc_180031847
0x180031741  mov     rdx, [rax+18h]
0x180031745  add     rdx, 60h ; '`'; pPublicKey
0x180031749  mov     esi, 10001h
0x18003174e  mov     ecx, esi; dwCertEncodingType
0x180031750  call    cs:__imp_CertGetPublicKeyLength
0x180031756  mov     [rdi+28h], ax
0x18003175a  test    ax, ax
0x18003175d  jz      short loc_180031723
0x18003175f  mov     rax, [rdi+10h]
0x180031763  mov     rdx, [rax+18h]
0x180031767  add     rdx, 30h ; '0'; pName
0x18003176b  mov     dword ptr [rsp+360h+pvFindPara], r14d; csz
0x180031770  xor     r9d, r9d; psz
0x180031773  lea     r8d, [r9+3]; dwStrType
0x180031777  mov     ecx, esi; dwCertEncodingType
0x180031779  call    cs:__imp_CertNameToStrA
0x18003177f  mov     edx, eax
0x180031781  lea     rcx, [rsp+360h+var_318]
0x180031786  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18003178c  test    al, al
0x18003178e  jz      short loc_180031723
0x180031790  mov     rax, [rdi+10h]
0x180031794  mov     rdx, [rax+18h]
0x180031798  add     rdx, 30h ; '0'; pName
0x18003179c  mov     eax, [rsp+360h+csz]
0x1800317a0  mov     dword ptr [rsp+360h+pvFindPara], eax; csz
0x1800317a4  mov     r9, [rsp+360h+psz]; psz
0x1800317a9  mov     r8d, 3; dwStrType
0x1800317af  mov     ecx, esi; dwCertEncodingType
0x1800317b1  call    cs:__imp_CertNameToStrA
0x1800317b7  lea     rcx, [rdi+30h]
0x1800317bb  mov     rdx, [rsp+360h+psz]
0x1800317c0  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800317c6  mov     ebx, eax
0x1800317c8  test    eax, eax
0x1800317ca  js      short loc_180031847
0x1800317cc  mov     rax, [rdi+10h]
0x1800317d0  mov     rdx, [rax+18h]
0x1800317d4  add     rdx, 50h ; 'P'; pName
0x1800317d8  mov     dword ptr [rsp+360h+pvFindPara], r14d; csz
0x1800317dd  xor     r9d, r9d; psz
0x1800317e0  lea     r8d, [r9+3]; dwStrType
0x1800317e4  mov     ecx, esi; dwCertEncodingType
0x1800317e6  call    cs:__imp_CertNameToStrA
0x1800317ec  mov     edx, eax
0x1800317ee  lea     rcx, [rsp+360h+var_318]
0x1800317f3  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800317f9  test    al, al
0x1800317fb  jz      loc_180031723
0x180031801  mov     rax, [rdi+10h]
0x180031805  mov     rdx, [rax+18h]
0x180031809  add     rdx, 50h ; 'P'; pName
0x18003180d  mov     eax, [rsp+360h+csz]
0x180031811  mov     dword ptr [rsp+360h+pvFindPara], eax; csz
0x180031815  mov     r9, [rsp+360h+psz]; psz
0x18003181a  mov     r8d, 3; dwStrType
0x180031820  mov     ecx, esi; dwCertEncodingType
0x180031822  call    cs:__imp_CertNameToStrA
0x180031828  lea     rcx, [rdi+68h]
0x18003182c  mov     rdx, [rsp+360h+psz]
0x180031831  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180031837  mov     ebx, eax
0x180031839  test    eax, eax
0x18003183b  js      short loc_180031847
0x18003183d  mov     rcx, rdi; this
0x180031840  call    ?AcquireCredentials@SSL_SERVER_CERT@@AEAAJXZ; SSL_SERVER_CERT::AcquireCredentials(void)
0x180031845  mov     ebx, eax
0x180031847  lea     rcx, [rsp+360h+var_2E8]
0x18003184c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180031852  nop
0x180031853  lea     rcx, [rsp+360h+var_318]
0x180031858  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003185e  mov     eax, ebx
0x180031860  jmp     short loc_18003187E
0x180031862  lea     rcx, [rsp+360h+var_2E8]
0x180031867  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003186d  nop
0x18003186e  lea     rcx, [rsp+360h+var_318]
0x180031873  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180031879  mov     eax, 80070002h
0x18003187e  mov     rcx, [rbp+260h+var_30]
0x180031885  xor     rcx, rsp; StackCookie
0x180031888  call    __security_check_cookie
0x18003188d  add     rsp, 340h
0x180031894  pop     r14
0x180031896  pop     rdi
0x180031897  pop     rsi
0x180031898  pop     rbx
0x180031899  pop     rbp
0x18003189a  retn
```
