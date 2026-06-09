# UtilsDeleteCert(HKEY__ *,ushort const *,bool,bool)

- ea: `0x180081dec`
- end: `0x180082032`
- name: `?UtilsDeleteCert@@YAJPEAUHKEY__@@PEBG_N2@Z`
- size: `582`
- prototype: `int(HKEY, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180082038`

## callees

- `0x180002714`
- `0x180081dec`
- `0x180082188`
- `0x1800cec40`
- `0x1800d1fa8`
- `0x1800d26c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081eae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081eae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081fd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081fbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f90`
- `CRYPT32!CertCloseStore` at `0x180081ffe`
- `CRYPT32!CertCloseStore` at `0x180081ffe`
- `CRYPT32!CertOpenStore` at `0x180081e35`
- `CRYPT32!CertOpenStore` at `0x180081e35`
- `CRYPT32!CertFreeCertificateContext` at `0x180081fe8`
- `CRYPT32!CertFreeCertificateContext` at `0x180081fe8`
- `CRYPT32!CertFindCertificateInStore` at `0x180081f16`
- `CRYPT32!CertFindCertificateInStore` at `0x180081f16`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180081f76`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180081f76`
- `DMCmnUtils!HexStringToBinary` at `0x180081e7d`
- `DMCmnUtils!HexStringToBinary` at `0x180081ee1`
- `DMCmnUtils!HexStringToBinary` at `0x180081e7d`
- `DMCmnUtils!HexStringToBinary` at `0x180081ee1`

## pseudocode

```c
__int64 __fastcall UtilsDeleteCert(HKEY a1, const unsigned __int16 *a2, char a3, unsigned __int8 a4)
{
  const CERT_CONTEXT *v6; // rdi
  HCERTSTORE v7; // rsi
  signed int LastError; // eax
  signed int v9; // ebx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  PCCERT_CONTEXT CertificateInStore; // rax
  CommonNGCUtils *v13; // rcx
  int v14; // eax
  int v15; // r8d
  int v16; // r9d
  signed int v17; // eax
  HANDLE v18; // rax
  CClientCertScepLogger *Logger; // rax
  const char *v20; // r9
  SIZE_T dwBytes[2]; // [rsp+30h] [rbp-28h] BYREF
  int v23; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  *(_OWORD *)dwBytes = 0;
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, ((a4 ^ 1u) << 16) + 65537, L"MY");
  if ( !v7 )
  {
LABEL_2:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  v9 = HexStringToBinary(a2, 0, dwBytes, 1);
  if ( v9 < 0 )
    goto LABEL_21;
  v10 = dwBytes[0];
  ProcessHeap = GetProcessHeap();
  dwBytes[1] = (SIZE_T)HeapAlloc(ProcessHeap, 8u, v10);
  if ( !dwBytes[1] )
  {
    v9 = -2147024882;
    goto LABEL_21;
  }
  v9 = HexStringToBinary(a2, dwBytes[1], dwBytes, 1);
  if ( v9 >= 0 )
  {
    CertificateInStore = CertFindCertificateInStore(v7, 1u, 0, 0x10000u, dwBytes, 0);
    v6 = CertificateInStore;
    if ( CertificateInStore )
    {
      if ( a3 )
        v14 = CommonNGCUtils::DeleteCertificatePrivateKey(v13, CertificateInStore);
      else
        v14 = UtilsDeleteCertPrivateKey(v7, CertificateInStore);
      if ( v14 < 0 && (unsigned int)dword_180155C20 > 3 )
      {
        v23 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180155C20,
          (unsigned int)byte_180134AC9,
          v15,
          v16,
          (__int64)&v23);
      }
      if ( CertDeleteCertificateFromStore(v6) )
      {
        v9 = 0;
        v6 = 0;
        goto LABEL_21;
      }
      goto LABEL_2;
    }
    v17 = GetLastError();
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    if ( v9 == -2146885628 )
      v9 = 0;
  }
LABEL_21:
  if ( dwBytes[1] )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, (LPVOID)dwBytes[1]);
  }
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( v7 )
    CertCloseStore(v7, 0);
  Logger = CClientCertScepLogger::GetLogger();
  CClientCertScepLogger::LogSCEPUtilsDeleteCert(Logger, v9, a2, v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180081dec  mov     [rsp+arg_0], rbx
0x180081df1  mov     [rsp+arg_8], rbp
0x180081df6  push    rsi
0x180081df7  push    rdi
0x180081df8  push    r14
0x180081dfa  sub     rsp, 40h
0x180081dfe  movzx   r9d, r9b
0x180081e02  lea     rax, aMy_0; "MY"
0x180081e09  xor     r9d, 1
0x180081e0d  mov     [rsp+58h+pvPara], rax; pvPara
0x180081e12  shl     r9d, 10h
0x180081e16  mov     r14b, r8b
0x180081e19  mov     rbp, rdx
0x180081e1c  xorps   xmm0, xmm0
0x180081e1f  xor     edi, edi
0x180081e21  add     r9d, 10001h; dwFlags
0x180081e28  xor     r8d, r8d; hCryptProv
0x180081e2b  xor     edx, edx; dwEncodingType
0x180081e2d  movups  xmmword ptr [rsp+58h+dwBytes], xmm0
0x180081e32  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x180081e35  call    cs:__imp_CertOpenStore
0x180081e3c  nop     dword ptr [rax+rax+00h]
0x180081e41  mov     rsi, rax
0x180081e44  test    rax, rax
0x180081e47  jnz     short loc_180081E6D
0x180081e49  call    cs:__imp_GetLastError
0x180081e50  nop     dword ptr [rax+rax+00h]
0x180081e55  mov     ebx, eax
0x180081e57  test    eax, eax
0x180081e59  jle     loc_180081FB6
0x180081e5f  movzx   ebx, ax
0x180081e62  or      ebx, 80070000h
0x180081e68  jmp     loc_180081FB6
0x180081e6d  mov     r9d, 1
0x180081e73  lea     r8, [rsp+58h+dwBytes]
0x180081e78  xor     edx, edx
0x180081e7a  mov     rcx, rbp
0x180081e7d  call    cs:__imp_HexStringToBinary
0x180081e84  nop     dword ptr [rax+rax+00h]
0x180081e89  mov     ebx, eax
0x180081e8b  test    eax, eax
0x180081e8d  js      loc_180081FB6
0x180081e93  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x180081e97  call    cs:__imp_GetProcessHeap
0x180081e9e  nop     dword ptr [rax+rax+00h]
0x180081ea3  mov     r8d, ebx; dwBytes
0x180081ea6  mov     edx, 8; dwFlags
0x180081eab  mov     rcx, rax; hHeap
0x180081eae  call    cs:__imp_HeapAlloc
0x180081eb5  nop     dword ptr [rax+rax+00h]
0x180081eba  mov     [rsp+58h+dwBytes+8], rax
0x180081ebf  test    rax, rax
0x180081ec2  jnz     short loc_180081ECE
0x180081ec4  mov     ebx, 8007000Eh
0x180081ec9  jmp     loc_180081FB6
0x180081ece  mov     rdx, [rsp+58h+dwBytes+8]
0x180081ed3  lea     r8, [rsp+58h+dwBytes]
0x180081ed8  mov     r9d, 1
0x180081ede  mov     rcx, rbp
0x180081ee1  call    cs:__imp_HexStringToBinary
0x180081ee8  nop     dword ptr [rax+rax+00h]
0x180081eed  mov     ebx, eax
0x180081eef  test    eax, eax
0x180081ef1  js      loc_180081FB6
0x180081ef7  xor     r8d, r8d; dwFindFlags
0x180081efa  mov     [rsp+58h+pPrevCertContext], rdi; pPrevCertContext
0x180081eff  lea     rax, [rsp+58h+dwBytes]
0x180081f04  mov     r9d, 10000h; dwFindType
0x180081f0a  mov     rcx, rsi; hCertStore
0x180081f0d  mov     [rsp+58h+pvPara], rax; pvFindPara
0x180081f12  lea     edx, [r8+1]; dwCertEncodingType
0x180081f16  call    cs:__imp_CertFindCertificateInStore
0x180081f1d  nop     dword ptr [rax+rax+00h]
0x180081f22  mov     rdi, rax
0x180081f25  test    rax, rax
0x180081f28  jz      short loc_180081F90
0x180081f2a  mov     rdx, rax; pCertContext
0x180081f2d  test    r14b, r14b
0x180081f30  jz      short loc_180081F39
0x180081f32  call    ?DeleteCertificatePrivateKey@CommonNGCUtils@@QEAAJPEBU_CERT_CONTEXT@@@Z; CommonNGCUtils::DeleteCertificatePrivateKey(_CERT_CONTEXT const *)
0x180081f37  jmp     short loc_180081F41
0x180081f39  mov     rcx, rsi; hCertStore
0x180081f3c  call    ?UtilsDeleteCertPrivateKey@@YAJPEAXPEBU_CERT_CONTEXT@@@Z; UtilsDeleteCertPrivateKey(void *,_CERT_CONTEXT const *)
0x180081f41  mov     ecx, eax
0x180081f43  test    eax, eax
0x180081f45  jns     short loc_180081F73
0x180081f47  mov     eax, cs:dword_180155C20
0x180081f4d  cmp     eax, 3
0x180081f50  jbe     short loc_180081F73
0x180081f52  mov     [rsp+58h+arg_18], ecx
0x180081f56  lea     rax, [rsp+58h+arg_18]
0x180081f5b  lea     rcx, dword_180155C20
0x180081f62  mov     [rsp+58h+pvPara], rax
0x180081f67  lea     rdx, byte_180134AC9
0x180081f6e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180081f73  mov     rcx, rdi; pCertContext
0x180081f76  call    cs:__imp_CertDeleteCertificateFromStore
0x180081f7d  nop     dword ptr [rax+rax+00h]
0x180081f82  test    eax, eax
0x180081f84  jz      loc_180081E49
0x180081f8a  xor     ebx, ebx
0x180081f8c  xor     edi, edi
0x180081f8e  jmp     short loc_180081FB6
0x180081f90  call    cs:__imp_GetLastError
0x180081f97  nop     dword ptr [rax+rax+00h]
0x180081f9c  mov     ebx, eax
0x180081f9e  test    eax, eax
0x180081fa0  jle     short loc_180081FAB
0x180081fa2  movzx   ebx, ax
0x180081fa5  or      ebx, 80070000h
0x180081fab  xor     eax, eax
0x180081fad  cmp     ebx, 80092004h
0x180081fb3  cmovz   ebx, eax
0x180081fb6  cmp     [rsp+58h+dwBytes+8], 0
0x180081fbc  jz      short loc_180081FE0
0x180081fbe  call    cs:__imp_GetProcessHeap
0x180081fc5  nop     dword ptr [rax+rax+00h]
0x180081fca  mov     r8, [rsp+58h+dwBytes+8]; lpMem
0x180081fcf  xor     edx, edx; dwFlags
0x180081fd1  mov     rcx, rax; hHeap
0x180081fd4  call    cs:__imp_HeapFree
0x180081fdb  nop     dword ptr [rax+rax+00h]
0x180081fe0  test    rdi, rdi
0x180081fe3  jz      short loc_180081FF4
0x180081fe5  mov     rcx, rdi; pCertContext
0x180081fe8  call    cs:__imp_CertFreeCertificateContext
0x180081fef  nop     dword ptr [rax+rax+00h]
0x180081ff4  test    rsi, rsi
0x180081ff7  jz      short loc_18008200A
0x180081ff9  xor     edx, edx; dwFlags
0x180081ffb  mov     rcx, rsi; hCertStore
0x180081ffe  call    cs:__imp_CertCloseStore
0x180082005  nop     dword ptr [rax+rax+00h]
0x18008200a  call    ?GetLogger@CClientCertScepLogger@@SAPEAV1@XZ; CClientCertScepLogger::GetLogger(void)
0x18008200f  mov     r8, rbp; unsigned __int16 *
0x180082012  mov     edx, ebx; int
0x180082014  mov     rcx, rax; this
0x180082017  call    ?LogSCEPUtilsDeleteCert@CClientCertScepLogger@@QEAAXJPEBGPEBD@Z; CClientCertScepLogger::LogSCEPUtilsDeleteCert(long,ushort const *,char const *)
0x18008201c  mov     rbp, [rsp+58h+arg_8]
0x180082021  mov     eax, ebx
0x180082023  mov     rbx, [rsp+58h+arg_0]
0x180082028  add     rsp, 40h
0x18008202c  pop     r14
0x18008202e  pop     rdi
0x18008202f  pop     rsi
0x180082030  retn
```
