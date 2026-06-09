# URLMONRequest::set_clientCert(ulong,uchar const *)

- ea: `0x1013a5a0`
- end: `0x1013a79c`
- name: `?set_clientCert@URLMONRequest@@UAEJKPBE@Z`
- size: `508`
- prototype: `HRESULT __thiscall(URLMONRequest *this, const void *cbClientCertHash, unsigned __int8 *pbClientCertHash)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x10067b20`
- `0x1006c2c4`
- `0x1013a5a0`
- `0x10180006`
- `0x101806b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013a706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013a706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013a6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013a6ba`
- `CRYPT32!CertFindCertificateInStore` at `0x1013a64a`
- `CRYPT32!CertFindCertificateInStore` at `0x1013a64a`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a680`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a6e6`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a680`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a6e6`
- `CRYPT32!CertFreeCertificateContext` at `0x1013a758`
- `CRYPT32!CertFreeCertificateContext` at `0x1013a758`
- `CRYPT32!CertCloseStore` at `0x1013a763`
- `CRYPT32!CertCloseStore` at `0x1013a763`
- `CRYPT32!CertOpenStore` at `0x1013a606`
- `CRYPT32!CertOpenStore` at `0x1013a606`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::set_clientCert(
        URLMONRequest *this,
        const void *cbClientCertHash,
        unsigned __int8 *pbClientCertHash)
{
  signed int v3; // edi
  HCERTSTORE v4; // eax
  signed int v5; // eax
  const _CERT_CONTEXT *CertificateInStore; // esi
  signed int v7; // eax
  signed int v8; // eax
  void *v9; // eax
  void *v10; // ebx
  signed int LastError; // eax
  int *v12; // ecx
  unsigned int v13; // eax
  int v14; // eax
  _CRYPTOAPI_BLOB HashBlob; // [esp+Ch] [ebp-18h] BYREF
  HCERTSTORE hCertStore; // [esp+14h] [ebp-10h]
  const _CERT_CONTEXT *v18; // [esp+18h] [ebp-Ch]
  URLMONRequest *v19; // [esp+1Ch] [ebp-8h]
  unsigned int cbCertSerial; // [esp+20h] [ebp-4h] BYREF

  v3 = 0;
  v19 = this;
  HashBlob = 0;
  cbCertSerial = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_qdq(0x403u, 0x73u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, cbClientCertHash, pbClientCertHash);
  if ( cbClientCertHash && pbClientCertHash )
  {
    v4 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x10000u, L"MY");
    hCertStore = v4;
    if ( v4 )
    {
      HashBlob.cbData = (unsigned int)cbClientCertHash;
      HashBlob.pbData = pbClientCertHash;
      CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x10000u, &HashBlob, 0);
      v18 = CertificateInStore;
      if ( CertificateInStore )
      {
        if ( CertSerializeCertificateStoreElement(CertificateInStore, 0, 0, &cbCertSerial) )
        {
          if ( cbCertSerial )
          {
            v9 = CoTaskMemAlloc(cbCertSerial);
            v10 = v9;
            if ( v9 )
            {
              memset(v9, 0, cbCertSerial);
              if ( CertSerializeCertificateStoreElement(CertificateInStore, 0, (BYTE *)v10, &cbCertSerial) )
              {
                v19->Lock(v19);
                v12 = (int *)v19;
                v13 = cbCertSerial;
                cbCertSerial = 0;
                v19->_cbClientCert = v13;
                v14 = *v12;
                v12[68] = (int)v10;
                (*(void (__thiscall **)(URLMONRequest *))(v14 + 128))(v19);
                CertificateInStore = v18;
              }
              else
              {
                LastError = GetLastError();
                v3 = LastError;
                if ( LastError > 0 )
                  v3 = (unsigned __int16)LastError | 0x80070000;
                CoTaskMemFree(v10);
                cbCertSerial = 0;
              }
            }
            else
            {
              v3 = -2147024882;
            }
          }
          else
          {
            v3 = -2147418113;
          }
        }
        else
        {
          v8 = GetLastError();
          v3 = v8;
          if ( v8 > 0 )
            v3 = (unsigned __int16)v8 | 0x80070000;
        }
        CertFreeCertificateContext(CertificateInStore);
      }
      else
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      CertCloseStore(hCertStore, 0);
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
    }
  }
  else
  {
    v3 = -2147024809;
  }
  if ( (byte_10185760[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0x74u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1013a5a0  mov     edi, edi
0x1013a5a2  push    ebp
0x1013a5a3  mov     ebp, esp
0x1013a5a5  sub     esp, 18h
0x1013a5a8  push    ebx
0x1013a5a9  push    esi
0x1013a5aa  push    edi
0x1013a5ab  mov     eax, this
0x1013a5ad  xor     edi, edi
0x1013a5af  xorps   xmm0, xmm0
0x1013a5b2  mov     [ebp+var_8], eax
0x1013a5b5  movlpd  qword ptr [ebp+HashBlob.cbData], xmm0
0x1013a5ba  mov     [ebp+cbCertSerial], edi
0x1013a5bd  test    byte_10185760, 8; __annotation("TMF:",
0x1013a5c4  mov     esi, [ebp+pbClientCertHash]
0x1013a5c7  mov     ebx, [ebp+cbClientCertHash]
0x1013a5ca  jz      short loc_1013A5E1
0x1013a5cc  push    esi; _a3
0x1013a5cd  push    ebx; _a2
0x1013a5ce  push    eax; _a1
0x1013a5cf  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a5d4  push    73h ; 's'
0x1013a5d6  pop     edx; id
0x1013a5d7  mov     this, 403h; LevelKeyword
0x1013a5dc  call    _WPP_SF_qdq@24; WPP_SF_qdq(x,x,x,x,x,x)
0x1013a5e1  test    ebx, ebx
0x1013a5e3  jnz     short loc_1013A5EF
0x1013a5e5  mov     edi, 80070057h
0x1013a5ea  jmp     loc_1013A769
0x1013a5ef  test    esi, esi
0x1013a5f1  jz      short loc_1013A5E5
0x1013a5f3  push    offset aMy; "MY"
0x1013a5f8  push    10000h; dwFlags
0x1013a5fd  push    0; hCryptProv
0x1013a5ff  push    10001h; dwEncodingType
0x1013a604  push    0Ah; lpszStoreProvider
0x1013a606  call    ds:__imp__CertOpenStore@20; CertOpenStore(x,x,x,x,x)
0x1013a60c  mov     [ebp+hCertStore], eax
0x1013a60f  test    eax, eax
0x1013a611  jnz     short loc_1013A631
0x1013a613  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a619  mov     edi, eax
0x1013a61b  test    edi, edi
0x1013a61d  jle     loc_1013A769
0x1013a623  movzx   edi, di
0x1013a626  or      edi, 80070000h
0x1013a62c  jmp     loc_1013A769
0x1013a631  push    0; pPrevCertContext
0x1013a633  lea     this, [ebp+HashBlob]
0x1013a636  mov     [ebp+HashBlob.cbData], ebx
0x1013a639  push    this; pvFindPara
0x1013a63a  push    10000h; dwFindType
0x1013a63f  push    0; dwFindFlags
0x1013a641  push    10001h; dwCertEncodingType
0x1013a646  push    eax; hCertStore
0x1013a647  mov     [ebp+HashBlob.pbData], esi
0x1013a64a  call    ds:__imp__CertFindCertificateInStore@24; CertFindCertificateInStore(x,x,x,x,x,x)
0x1013a650  mov     esi, eax
0x1013a652  mov     [ebp+var_C], esi
0x1013a655  test    esi, esi
0x1013a657  jnz     short loc_1013A677
0x1013a659  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a65f  mov     edi, eax
0x1013a661  test    edi, edi
0x1013a663  jle     loc_1013A75E
0x1013a669  movzx   edi, di
0x1013a66c  or      edi, 80070000h
0x1013a672  jmp     loc_1013A75E
0x1013a677  lea     eax, [ebp+cbCertSerial]
0x1013a67a  push    eax; pcbElement
0x1013a67b  push    0; pbElement
0x1013a67d  push    0; dwFlags
0x1013a67f  push    esi; pCertContext
0x1013a680  call    ds:__imp__CertSerializeCertificateStoreElement@16; CertSerializeCertificateStoreElement(x,x,x,x)
0x1013a686  test    eax, eax
0x1013a688  jnz     short loc_1013A6A8
0x1013a68a  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a690  mov     edi, eax
0x1013a692  test    edi, edi
0x1013a694  jle     loc_1013A757
0x1013a69a  movzx   edi, di
0x1013a69d  or      edi, 80070000h
0x1013a6a3  jmp     loc_1013A757
0x1013a6a8  cmp     [ebp+cbCertSerial], edi
0x1013a6ab  jnz     short loc_1013A6B7
0x1013a6ad  mov     edi, 8000FFFFh
0x1013a6b2  jmp     loc_1013A757
0x1013a6b7  push    [ebp+cbCertSerial]; cb
0x1013a6ba  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1013a6c0  mov     ebx, eax
0x1013a6c2  test    ebx, ebx
0x1013a6c4  jnz     short loc_1013A6D0
0x1013a6c6  mov     edi, 8007000Eh
0x1013a6cb  jmp     loc_1013A757
0x1013a6d0  push    [ebp+cbCertSerial]; Size
0x1013a6d3  push    0; Val
0x1013a6d5  push    ebx; void *
0x1013a6d6  call    _memset
0x1013a6db  add     esp, 0Ch
0x1013a6de  lea     eax, [ebp+cbCertSerial]
0x1013a6e1  push    eax; pcbElement
0x1013a6e2  push    ebx; pbElement
0x1013a6e3  push    0; dwFlags
0x1013a6e5  push    esi; pCertContext
0x1013a6e6  call    ds:__imp__CertSerializeCertificateStoreElement@16; CertSerializeCertificateStoreElement(x,x,x,x)
0x1013a6ec  test    eax, eax
0x1013a6ee  jnz     short loc_1013A715
0x1013a6f0  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a6f6  mov     edi, eax
0x1013a6f8  test    edi, edi
0x1013a6fa  jle     short loc_1013A705
0x1013a6fc  movzx   edi, di
0x1013a6ff  or      edi, 80070000h
0x1013a705  push    ebx; pv
0x1013a706  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1013a70c  mov     [ebp+cbCertSerial], 0
0x1013a713  jmp     short loc_1013A757
0x1013a715  mov     eax, [ebp+var_8]
0x1013a718  mov     eax, [eax]
0x1013a71a  mov     esi, [eax+7Ch]
0x1013a71d  mov     this, esi; this
0x1013a71f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a725  mov     this, [ebp+var_8]
0x1013a728  call    esi
0x1013a72a  mov     this, [ebp+var_8]
0x1013a72d  mov     eax, [ebp+cbCertSerial]
0x1013a730  mov     [ebp+cbCertSerial], edi
0x1013a733  mov     [this+10Ch], eax
0x1013a739  mov     eax, [this]
0x1013a73b  mov     [this+110h], ebx
0x1013a741  mov     esi, [eax+80h]
0x1013a747  mov     this, esi; this
0x1013a749  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a74f  mov     this, [ebp+var_8]
0x1013a752  call    esi
0x1013a754  mov     esi, [ebp+var_C]
0x1013a757  push    esi; pCertContext
0x1013a758  call    ds:__imp__CertFreeCertificateContext@4; CertFreeCertificateContext(x)
0x1013a75e  push    0; dwFlags
0x1013a760  push    [ebp+hCertStore]; hCertStore
0x1013a763  call    ds:__imp__CertCloseStore@8; CertCloseStore(x,x)
0x1013a769  mov     this, edi; __annotation("TMF:",
0x1013a76b  sar     this, 1Fh
0x1013a76e  mov     eax, this
0x1013a770  shl     eax, 4
0x1013a773  test    byte_10185760[eax], 8
0x1013a77a  jz      short loc_1013A793
0x1013a77c  push    edi; _a1
0x1013a77d  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a782  add     this, 2
0x1013a785  shl     this, 9
0x1013a788  push    74h ; 't'
0x1013a78a  or      this, 3; LevelKeyword
0x1013a78d  pop     edx; id
0x1013a78e  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a793  mov     eax, edi
0x1013a795  pop     edi
0x1013a796  pop     esi
0x1013a797  pop     ebx
0x1013a798  leave
0x1013a799  retn    8
```
