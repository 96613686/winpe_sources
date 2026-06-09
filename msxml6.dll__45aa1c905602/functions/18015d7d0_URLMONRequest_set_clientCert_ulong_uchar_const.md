# URLMONRequest::set_clientCert(ulong,uchar const *)

- ea: `0x18015d7d0`
- end: `0x18015da6b`
- name: `?set_clientCert@URLMONRequest@@UEAAJKPEBE@Z`
- size: `667`
- prototype: `HRESULT __fastcall(URLMONRequest *this, unsigned int cbClientCertHash, const unsigned __int8 *pbClientCertHash)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cd3e4`
- `0x18015d7d0`
- `0x180189008`
- `0x180189bfc`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d8c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d8c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015d9a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015d9a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015d93f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18015d93f`
- `CRYPT32!CertFindCertificateInStore` at `0x18015d8b3`
- `CRYPT32!CertFindCertificateInStore` at `0x18015d8b3`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015d8f7`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015d977`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015d8f7`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x18015d977`
- `CRYPT32!CertFreeCertificateContext` at `0x18015d9f6`
- `CRYPT32!CertFreeCertificateContext` at `0x18015d9f6`
- `CRYPT32!CertCloseStore` at `0x18015da07`
- `CRYPT32!CertCloseStore` at `0x18015da07`
- `CRYPT32!CertOpenStore` at `0x18015d854`
- `CRYPT32!CertOpenStore` at `0x18015d854`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
0x18015d7d0  push    rbp
0x18015d7d2  push    rbx
0x18015d7d3  push    rsi
0x18015d7d4  push    rdi
0x18015d7d5  push    r14
0x18015d7d7  push    r15
0x18015d7d9  mov     rbp, rsp
0x18015d7dc  sub     rsp, 48h
0x18015d7e0  xorps   xmm0, xmm0
0x18015d7e3  mov     [rbp+cbCertSerial], 0
0x18015d7ea  movups  xmmword ptr [rbp+HashBlob.cbData], xmm0
0x18015d7ee  mov     rbx, pbClientCertHash
0x18015d7f1  mov     edi, cbClientCertHash
0x18015d7f3  mov     rsi, this
0x18015d7f6  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015d7fd  jz      short loc_18015D821
0x18015d7ff  mov     cbClientCertHash, 73h ; 's'; id
0x18015d804  mov     [rsp+48h+_a3], rbx; _a3
0x18015d809  mov     ecx, 403h; LevelKeyword
0x18015d80e  mov     [rsp+48h+_a2], edi; _a2
0x18015d812  mov     r9, rsi; _a1
0x18015d815  lea     pbClientCertHash, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d81c  call    WPP_SF_qdq
0x18015d821  test    edi, edi
0x18015d823  jnz     short loc_18015D82F
0x18015d825  mov     ebx, 80070057h
0x18015d82a  jmp     loc_18015DA13
0x18015d82f  test    rbx, rbx
0x18015d832  jz      short loc_18015D825
0x18015d834  mov     r14d, 10000h
0x18015d83a  lea     rax, aMy; "MY"
0x18015d841  xor     r8d, r8d; hCryptProv
0x18015d844  mov     qword ptr [rsp+48h+_a2], rax; pvPara
0x18015d849  mov     r9d, r14d; dwFlags
0x18015d84c  lea     cbClientCertHash, [r14+1]; dwEncodingType
0x18015d850  lea     ecx, [pbClientCertHash+0Ah]; lpszStoreProvider
0x18015d854  call    cs:__imp_CertOpenStore
0x18015d85b  nop     dword ptr [rax+rax+00h]
0x18015d860  mov     r15, rax
0x18015d863  test    rax, rax
0x18015d866  jnz     short loc_18015D88C
0x18015d868  call    cs:__imp_GetLastError
0x18015d86f  nop     dword ptr [rax+rax+00h]
0x18015d874  mov     ebx, eax
0x18015d876  test    eax, eax
0x18015d878  jle     loc_18015DA13
0x18015d87e  movzx   ebx, ax
0x18015d881  or      ebx, 80070000h
0x18015d887  jmp     loc_18015DA13
0x18015d88c  lea     rax, [rbp+HashBlob]
0x18015d890  mov     [rsp+48h+_a3], 0; pPrevCertContext
0x18015d899  mov     r9d, r14d; dwFindType
0x18015d89c  mov     qword ptr [rsp+48h+_a2], rax; pvFindPara
0x18015d8a1  xor     r8d, r8d; dwFindFlags
0x18015d8a4  mov     [rbp+HashBlob.cbData], edi
0x18015d8a7  mov     cbClientCertHash, 10001h; dwCertEncodingType
0x18015d8ac  mov     [rbp+HashBlob.pbData], rbx
0x18015d8b0  mov     this, r15; hCertStore
0x18015d8b3  call    cs:__imp_CertFindCertificateInStore
0x18015d8ba  nop     dword ptr [rax+rax+00h]
0x18015d8bf  mov     r14, rax
0x18015d8c2  test    rax, rax
0x18015d8c5  jnz     short loc_18015D8EB
0x18015d8c7  call    cs:__imp_GetLastError
0x18015d8ce  nop     dword ptr [rax+rax+00h]
0x18015d8d3  mov     ebx, eax
0x18015d8d5  test    eax, eax
0x18015d8d7  jle     loc_18015DA02
0x18015d8dd  movzx   ebx, ax
0x18015d8e0  or      ebx, 80070000h
0x18015d8e6  jmp     loc_18015DA02
0x18015d8eb  lea     r9, [rbp+cbCertSerial]; pcbElement
0x18015d8ef  xor     r8d, r8d; pbElement
0x18015d8f2  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015d8f4  mov     this, r14; pCertContext
0x18015d8f7  call    cs:__imp_CertSerializeCertificateStoreElement
0x18015d8fe  nop     dword ptr [rax+rax+00h]
0x18015d903  test    eax, eax
0x18015d905  jnz     short loc_18015D92B
0x18015d907  call    cs:__imp_GetLastError
0x18015d90e  nop     dword ptr [rax+rax+00h]
0x18015d913  mov     ebx, eax
0x18015d915  test    eax, eax
0x18015d917  jle     loc_18015D9F3
0x18015d91d  movzx   ebx, ax
0x18015d920  or      ebx, 80070000h
0x18015d926  jmp     loc_18015D9F3
0x18015d92b  mov     eax, [rbp+cbCertSerial]
0x18015d92e  test    eax, eax
0x18015d930  jnz     short loc_18015D93C
0x18015d932  mov     ebx, 8000FFFFh
0x18015d937  jmp     loc_18015D9F3
0x18015d93c  mov     this, rax; cb
0x18015d93f  call    cs:__imp_CoTaskMemAlloc
0x18015d946  nop     dword ptr [rax+rax+00h]
0x18015d94b  mov     rdi, rax
0x18015d94e  test    rax, rax
0x18015d951  jnz     short loc_18015D95D
0x18015d953  mov     ebx, 8007000Eh
0x18015d958  jmp     loc_18015D9F3
0x18015d95d  mov     r8d, [rbp+cbCertSerial]; Size
0x18015d961  xor     cbClientCertHash, cbClientCertHash; Val
0x18015d963  mov     this, rdi; void *
0x18015d966  call    memset_0
0x18015d96b  lea     r9, [rbp+cbCertSerial]; pcbElement
0x18015d96f  mov     pbClientCertHash, rdi; pbElement
0x18015d972  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015d974  mov     this, r14; pCertContext
0x18015d977  call    cs:__imp_CertSerializeCertificateStoreElement
0x18015d97e  nop     dword ptr [rax+rax+00h]
0x18015d983  test    eax, eax
0x18015d985  jnz     short loc_18015D9BA
0x18015d987  call    cs:__imp_GetLastError
0x18015d98e  nop     dword ptr [rax+rax+00h]
0x18015d993  mov     ebx, eax
0x18015d995  test    eax, eax
0x18015d997  jle     short loc_18015D9A2
0x18015d999  movzx   ebx, ax
0x18015d99c  or      ebx, 80070000h
0x18015d9a2  mov     this, rdi; pv
0x18015d9a5  call    cs:__imp_CoTaskMemFree
0x18015d9ac  nop     dword ptr [rax+rax+00h]
0x18015d9b1  mov     [rbp+cbCertSerial], 0
0x18015d9b8  jmp     short loc_18015D9F3
0x18015d9ba  mov     rax, [rsi]
0x18015d9bd  mov     this, rsi
0x18015d9c0  xor     ebx, ebx
0x18015d9c2  mov     rax, [rax+0F8h]
0x18015d9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d9ce  mov     eax, [rbp+cbCertSerial]
0x18015d9d1  mov     this, rsi
0x18015d9d4  mov     [rsi+1D8h], eax
0x18015d9da  mov     rax, [rsi]
0x18015d9dd  mov     [rsi+1E0h], rdi
0x18015d9e4  mov     [rbp+cbCertSerial], ebx
0x18015d9e7  mov     rax, [rax+100h]
0x18015d9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d9f3  mov     this, r14; pCertContext
0x18015d9f6  call    cs:__imp_CertFreeCertificateContext
0x18015d9fd  nop     dword ptr [rax+rax+00h]
0x18015da02  xor     cbClientCertHash, cbClientCertHash; dwFlags
0x18015da04  mov     this, r15; hCertStore
0x18015da07  call    cs:__imp_CertCloseStore
0x18015da0e  nop     dword ptr [rax+rax+00h]
0x18015da13  mov     r10d, ebx; __annotation("TMF:",
0x18015da16  sar     r10d, 1Fh
0x18015da1a  lea     eax, ds:4[r10*2]
0x18015da22  movsxd  this, eax
0x18015da25  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015da2c  test    byte ptr [rax+this*8], 8
0x18015da30  jz      short loc_18015DA5B
0x18015da32  add     r10w, 2
0x18015da37  lea     pbClientCertHash, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015da3e  movzx   ecx, r10w
0x18015da42  mov     eax, 200h
0x18015da47  imul    ecx, eax
0x18015da4a  mov     cbClientCertHash, 74h ; 't'; id
0x18015da4f  mov     r9d, ebx; _a1
0x18015da52  or      cx, 3; LevelKeyword
0x18015da56  call    WPP_SF_d
0x18015da5b  mov     eax, ebx
0x18015da5d  add     rsp, 48h
0x18015da61  pop     r15
0x18015da63  pop     r14
0x18015da65  pop     rdi
0x18015da66  pop     rsi
0x18015da67  pop     rbx
0x18015da68  pop     rbp
0x18015da69  retn
```
