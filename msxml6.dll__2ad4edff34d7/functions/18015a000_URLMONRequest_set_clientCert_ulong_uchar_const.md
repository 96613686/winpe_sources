# URLMONRequest::set_clientCert(ulong,uchar const *)

- ea: `0x18015a000`
- end: `0x18015a252`
- name: `?set_clientCert@URLMONRequest@@UEAAJKPEBE@Z`
- size: `594`
- prototype: `__int64 __fastcall(URLMONRequest *this, unsigned int cbClientCertHash, unsigned __int8 *pbClientCertHash)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cba94`
- `0x18015a000`
- `0x180185008`
- `0x180185bf0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015a19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015a19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015a14b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015a14b`
- `CRYPT32!CertFindCertificateInStore` at `0x18015a0d7`
- `CRYPT32!CertFindCertificateInStore` at `0x18015a0d7`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015a10f`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015a17d`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015a10f`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015a17d`
- `CRYPT32!CertFreeCertificateContext` at `0x18015a1ea`
- `CRYPT32!CertFreeCertificateContext` at `0x18015a1ea`
- `CRYPT32!CertCloseStore` at `0x18015a1f5`
- `CRYPT32!CertCloseStore` at `0x18015a1f5`
- `CRYPT32!CertOpenStore` at `0x18015a084`
- `CRYPT32!CertOpenStore` at `0x18015a084`

## pseudocode

```c
__int64 __fastcall URLMONRequest::set_clientCert(
        URLMONRequest *this,
        unsigned int cbClientCertHash,
        unsigned __int8 *pbClientCertHash)
{
  signed int v6; // ebx
  HCERTSTORE v7; // r15
  signed int v8; // eax
  const _CERT_CONTEXT *CertificateInStore; // rax
  const _CERT_CONTEXT *v10; // r14
  signed int v11; // eax
  signed int v12; // eax
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rdi
  signed int LastError; // eax
  URLMONRequest_vtbl *v16; // rax
  _CRYPTOAPI_BLOB HashBlob; // [rsp+30h] [rbp-18h] BYREF
  unsigned int cbCertSerial; // [rsp+88h] [rbp+40h] BYREF

  cbCertSerial = 0;
  HashBlob = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_qdq(0x403u, 0x73u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, cbClientCertHash, pbClientCertHash);
  if ( cbClientCertHash && pbClientCertHash )
  {
    v7 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x10000u, L"MY");
    if ( v7 )
    {
      HashBlob.cbData = cbClientCertHash;
      HashBlob.pbData = pbClientCertHash;
      CertificateInStore = CertFindCertificateInStore(v7, 0x10001u, 0, 0x10000u, &HashBlob, 0);
      v10 = CertificateInStore;
      if ( CertificateInStore )
      {
        if ( CertSerializeCertificateStoreElement(CertificateInStore, 0, 0, &cbCertSerial) )
        {
          if ( cbCertSerial )
          {
            v13 = (unsigned __int8 *)CoTaskMemAlloc(cbCertSerial);
            v14 = v13;
            if ( v13 )
            {
              memset_0(v13, 0, cbCertSerial);
              if ( CertSerializeCertificateStoreElement(v10, 0, v14, &cbCertSerial) )
              {
                v6 = 0;
                this->Lock(this);
                this->_cbClientCert = cbCertSerial;
                v16 = this->__vftable;
                this->_pbClientCert = v14;
                cbCertSerial = 0;
                v16->Unlock(this);
              }
              else
              {
                LastError = GetLastError();
                v6 = LastError;
                if ( LastError > 0 )
                  v6 = (unsigned __int16)LastError | 0x80070000;
                CoTaskMemFree(v14);
                cbCertSerial = 0;
              }
            }
            else
            {
              v6 = -2147024882;
            }
          }
          else
          {
            v6 = -2147418113;
          }
        }
        else
        {
          v12 = GetLastError();
          v6 = v12;
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
        }
        CertFreeCertificateContext(v10);
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
      }
      CertCloseStore(v7, 0);
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v6 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0x74u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18015a000  push    rbp
0x18015a002  push    rbx
0x18015a003  push    rsi
0x18015a004  push    rdi
0x18015a005  push    r14
0x18015a007  push    r15
0x18015a009  mov     rbp, rsp
0x18015a00c  sub     rsp, 48h
0x18015a010  xorps   xmm0, xmm0
0x18015a013  mov     [rbp+cbCertSerial], 0
0x18015a01a  movups  xmmword ptr [rbp+HashBlob.cbData], xmm0
0x18015a01e  mov     rbx, pbClientCertHash
0x18015a021  mov     edi, cbClientCertHash
0x18015a023  mov     rsi, this
0x18015a026  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x18015a02d  jz      short loc_18015A051
0x18015a02f  mov     cbClientCertHash, 73h ; 's'; id
0x18015a034  mov     [rsp+48h+_a3], rbx; _a3
0x18015a039  mov     ecx, 403h; LevelKeyword
0x18015a03e  mov     [rsp+48h+_a2], edi; _a2
0x18015a042  mov     r9, rsi; _a1
0x18015a045  lea     pbClientCertHash, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015a04c  call    WPP_SF_qdq
0x18015a051  test    edi, edi
0x18015a053  jnz     short loc_18015A05F
0x18015a055  mov     ebx, 80070057h
0x18015a05a  jmp     loc_18015A1FB
0x18015a05f  test    rbx, rbx
0x18015a062  jz      short loc_18015A055
0x18015a064  mov     r14d, 10000h
0x18015a06a  lea     rax, aMy; "MY"
0x18015a071  xor     r8d, r8d; hCryptProv
0x18015a074  mov     qword ptr [rsp+48h+_a2], rax; pvPara
0x18015a079  mov     r9d, r14d; dwFlags
0x18015a07c  lea     cbClientCertHash, [r14+1]; dwEncodingType
0x18015a080  lea     ecx, [pbClientCertHash+0Ah]; lpszStoreProvider
0x18015a084  call    cs:__imp_CertOpenStore
0x18015a08a  mov     r15, rax
0x18015a08d  test    rax, rax
0x18015a090  jnz     short loc_18015A0B0
0x18015a092  call    cs:__imp_GetLastError
0x18015a098  mov     ebx, eax
0x18015a09a  test    eax, eax
0x18015a09c  jle     loc_18015A1FB
0x18015a0a2  movzx   ebx, ax
0x18015a0a5  or      ebx, 80070000h
0x18015a0ab  jmp     loc_18015A1FB
0x18015a0b0  lea     rax, [rbp+HashBlob]
0x18015a0b4  mov     [rsp+48h+_a3], 0; pPrevCertContext
0x18015a0bd  mov     r9d, r14d; dwFindType
0x18015a0c0  mov     qword ptr [rsp+48h+_a2], rax; pvFindPara
0x18015a0c5  xor     r8d, r8d; dwFindFlags
0x18015a0c8  mov     [rbp+HashBlob.cbData], edi
0x18015a0cb  mov     cbClientCertHash, 10001h; dwCertEncodingType
0x18015a0d0  mov     [rbp+HashBlob.pbData], rbx
0x18015a0d4  mov     this, r15; hCertStore
0x18015a0d7  call    cs:__imp_CertFindCertificateInStore
0x18015a0dd  mov     r14, rax
0x18015a0e0  test    rax, rax
0x18015a0e3  jnz     short loc_18015A103
0x18015a0e5  call    cs:__imp_GetLastError
0x18015a0eb  mov     ebx, eax
0x18015a0ed  test    eax, eax
0x18015a0ef  jle     loc_18015A1F0
0x18015a0f5  movzx   ebx, ax
0x18015a0f8  or      ebx, 80070000h
0x18015a0fe  jmp     loc_18015A1F0
0x18015a103  lea     r9, [rbp+cbCertSerial]; pcbElement
0x18015a107  xor     r8d, r8d; pbElement
0x18015a10a  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015a10c  mov     this, r14; pCertContext
0x18015a10f  call    cs:__imp_CertSerializeCertificateStoreElement
0x18015a115  test    eax, eax
0x18015a117  jnz     short loc_18015A137
0x18015a119  call    cs:__imp_GetLastError
0x18015a11f  mov     ebx, eax
0x18015a121  test    eax, eax
0x18015a123  jle     loc_18015A1E7
0x18015a129  movzx   ebx, ax
0x18015a12c  or      ebx, 80070000h
0x18015a132  jmp     loc_18015A1E7
0x18015a137  mov     eax, [rbp+cbCertSerial]
0x18015a13a  test    eax, eax
0x18015a13c  jnz     short loc_18015A148
0x18015a13e  mov     ebx, 8000FFFFh
0x18015a143  jmp     loc_18015A1E7
0x18015a148  mov     this, rax; cb
0x18015a14b  call    cs:__imp_CoTaskMemAlloc
0x18015a151  mov     rdi, rax
0x18015a154  test    rax, rax
0x18015a157  jnz     short loc_18015A163
0x18015a159  mov     ebx, 8007000Eh
0x18015a15e  jmp     loc_18015A1E7
0x18015a163  mov     r8d, [rbp+cbCertSerial]; Size
0x18015a167  xor     cbClientCertHash, cbClientCertHash; Val
0x18015a169  mov     this, rdi; void *
0x18015a16c  call    memset_0
0x18015a171  lea     r9, [rbp+cbCertSerial]; pcbElement
0x18015a175  mov     pbClientCertHash, rdi; pbElement
0x18015a178  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015a17a  mov     this, r14; pCertContext
0x18015a17d  call    cs:__imp_CertSerializeCertificateStoreElement
0x18015a183  test    eax, eax
0x18015a185  jnz     short loc_18015A1AE
0x18015a187  call    cs:__imp_GetLastError
0x18015a18d  mov     ebx, eax
0x18015a18f  test    eax, eax
0x18015a191  jle     short loc_18015A19C
0x18015a193  movzx   ebx, ax
0x18015a196  or      ebx, 80070000h
0x18015a19c  mov     this, rdi; pv
0x18015a19f  call    cs:__imp_CoTaskMemFree
0x18015a1a5  mov     [rbp+cbCertSerial], 0
0x18015a1ac  jmp     short loc_18015A1E7
0x18015a1ae  mov     rax, [rsi]
0x18015a1b1  mov     this, rsi
0x18015a1b4  xor     ebx, ebx
0x18015a1b6  mov     rax, [rax+0F8h]
0x18015a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a1c2  mov     eax, [rbp+cbCertSerial]
0x18015a1c5  mov     this, rsi
0x18015a1c8  mov     [rsi+1D8h], eax
0x18015a1ce  mov     rax, [rsi]
0x18015a1d1  mov     [rsi+1E0h], rdi
0x18015a1d8  mov     [rbp+cbCertSerial], ebx
0x18015a1db  mov     rax, [rax+100h]
0x18015a1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a1e7  mov     this, r14; pCertContext
0x18015a1ea  call    cs:__imp_CertFreeCertificateContext
0x18015a1f0  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015a1f2  mov     this, r15; hCertStore
0x18015a1f5  call    cs:__imp_CertCloseStore
0x18015a1fb  mov     r10d, ebx; __annotation("TMF:",
0x18015a1fe  sar     r10d, 1Fh
0x18015a202  lea     eax, ds:4[r10*2]
0x18015a20a  movsxd  this, eax
0x18015a20d  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015a214  test    byte ptr [rax+this*8], 8
0x18015a218  jz      short loc_18015A243
0x18015a21a  add     r10w, 2
0x18015a21f  lea     pbClientCertHash, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015a226  movzx   ecx, r10w
0x18015a22a  mov     eax, 200h
0x18015a22f  imul    ecx, eax
0x18015a232  mov     cbClientCertHash, 74h ; 't'; id
0x18015a237  mov     r9d, ebx; _a1
0x18015a23a  or      cx, 3; LevelKeyword
0x18015a23e  call    WPP_SF_d
0x18015a243  mov     eax, ebx
0x18015a245  add     rsp, 48h
0x18015a249  pop     r15
0x18015a24b  pop     r14
0x18015a24d  pop     rdi
0x18015a24e  pop     rsi
0x18015a24f  pop     rbx
0x18015a250  pop     rbp
0x18015a251  retn
```
