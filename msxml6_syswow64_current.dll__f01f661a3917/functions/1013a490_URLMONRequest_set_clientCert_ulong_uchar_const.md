# URLMONRequest::set_clientCert(ulong,uchar const *)

- ea: `0x1013a490`
- end: `0x1013a68c`
- name: `?set_clientCert@URLMONRequest@@UAEJKPBE@Z`
- size: `508`
- prototype: `HRESULT __thiscall(URLMONRequest *this, const void *cbClientCertHash, unsigned __int8 *pbClientCertHash)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x10067bc0`
- `0x1006c354`
- `0x1013a490`
- `0x10180006`
- `0x101806b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013a5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1013a5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013a5aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013a5aa`
- `CRYPT32!CertFindCertificateInStore` at `0x1013a53a`
- `CRYPT32!CertFindCertificateInStore` at `0x1013a53a`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a570`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a5d6`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a570`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1013a5d6`
- `CRYPT32!CertFreeCertificateContext` at `0x1013a648`
- `CRYPT32!CertFreeCertificateContext` at `0x1013a648`
- `CRYPT32!CertCloseStore` at `0x1013a653`
- `CRYPT32!CertCloseStore` at `0x1013a653`
- `CRYPT32!CertOpenStore` at `0x1013a4f6`
- `CRYPT32!CertOpenStore` at `0x1013a4f6`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0x74u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1013a490  mov     edi, edi
0x1013a492  push    ebp
0x1013a493  mov     ebp, esp
0x1013a495  sub     esp, 18h
0x1013a498  push    ebx
0x1013a499  push    esi
0x1013a49a  push    edi
0x1013a49b  mov     eax, this
0x1013a49d  xor     edi, edi
0x1013a49f  xorps   xmm0, xmm0
0x1013a4a2  mov     [ebp+var_8], eax
0x1013a4a5  movlpd  qword ptr [ebp+HashBlob.cbData], xmm0
0x1013a4aa  mov     [ebp+cbCertSerial], edi
0x1013a4ad  test    byte_101857A0, 8; __annotation("TMF:",
0x1013a4b4  mov     esi, [ebp+pbClientCertHash]
0x1013a4b7  mov     ebx, [ebp+cbClientCertHash]
0x1013a4ba  jz      short loc_1013A4D1
0x1013a4bc  push    esi; _a3
0x1013a4bd  push    ebx; _a2
0x1013a4be  push    eax; _a1
0x1013a4bf  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a4c4  push    73h ; 's'
0x1013a4c6  pop     edx; id
0x1013a4c7  mov     this, 403h; LevelKeyword
0x1013a4cc  call    _WPP_SF_qdq@24; WPP_SF_qdq(x,x,x,x,x,x)
0x1013a4d1  test    ebx, ebx
0x1013a4d3  jnz     short loc_1013A4DF
0x1013a4d5  mov     edi, 80070057h
0x1013a4da  jmp     loc_1013A659
0x1013a4df  test    esi, esi
0x1013a4e1  jz      short loc_1013A4D5
0x1013a4e3  push    offset aMy; "MY"
0x1013a4e8  push    10000h; dwFlags
0x1013a4ed  push    0; hCryptProv
0x1013a4ef  push    10001h; dwEncodingType
0x1013a4f4  push    0Ah; lpszStoreProvider
0x1013a4f6  call    ds:__imp__CertOpenStore@20; CertOpenStore(x,x,x,x,x)
0x1013a4fc  mov     [ebp+hCertStore], eax
0x1013a4ff  test    eax, eax
0x1013a501  jnz     short loc_1013A521
0x1013a503  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a509  mov     edi, eax
0x1013a50b  test    edi, edi
0x1013a50d  jle     loc_1013A659
0x1013a513  movzx   edi, di
0x1013a516  or      edi, 80070000h
0x1013a51c  jmp     loc_1013A659
0x1013a521  push    0; pPrevCertContext
0x1013a523  lea     this, [ebp+HashBlob]
0x1013a526  mov     [ebp+HashBlob.cbData], ebx
0x1013a529  push    this; pvFindPara
0x1013a52a  push    10000h; dwFindType
0x1013a52f  push    0; dwFindFlags
0x1013a531  push    10001h; dwCertEncodingType
0x1013a536  push    eax; hCertStore
0x1013a537  mov     [ebp+HashBlob.pbData], esi
0x1013a53a  call    ds:__imp__CertFindCertificateInStore@24; CertFindCertificateInStore(x,x,x,x,x,x)
0x1013a540  mov     esi, eax
0x1013a542  mov     [ebp+var_C], esi
0x1013a545  test    esi, esi
0x1013a547  jnz     short loc_1013A567
0x1013a549  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a54f  mov     edi, eax
0x1013a551  test    edi, edi
0x1013a553  jle     loc_1013A64E
0x1013a559  movzx   edi, di
0x1013a55c  or      edi, 80070000h
0x1013a562  jmp     loc_1013A64E
0x1013a567  lea     eax, [ebp+cbCertSerial]
0x1013a56a  push    eax; pcbElement
0x1013a56b  push    0; pbElement
0x1013a56d  push    0; dwFlags
0x1013a56f  push    esi; pCertContext
0x1013a570  call    ds:__imp__CertSerializeCertificateStoreElement@16; CertSerializeCertificateStoreElement(x,x,x,x)
0x1013a576  test    eax, eax
0x1013a578  jnz     short loc_1013A598
0x1013a57a  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a580  mov     edi, eax
0x1013a582  test    edi, edi
0x1013a584  jle     loc_1013A647
0x1013a58a  movzx   edi, di
0x1013a58d  or      edi, 80070000h
0x1013a593  jmp     loc_1013A647
0x1013a598  cmp     [ebp+cbCertSerial], edi
0x1013a59b  jnz     short loc_1013A5A7
0x1013a59d  mov     edi, 8000FFFFh
0x1013a5a2  jmp     loc_1013A647
0x1013a5a7  push    [ebp+cbCertSerial]; cb
0x1013a5aa  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1013a5b0  mov     ebx, eax
0x1013a5b2  test    ebx, ebx
0x1013a5b4  jnz     short loc_1013A5C0
0x1013a5b6  mov     edi, 8007000Eh
0x1013a5bb  jmp     loc_1013A647
0x1013a5c0  push    [ebp+cbCertSerial]; Size
0x1013a5c3  push    0; Val
0x1013a5c5  push    ebx; void *
0x1013a5c6  call    _memset
0x1013a5cb  add     esp, 0Ch
0x1013a5ce  lea     eax, [ebp+cbCertSerial]
0x1013a5d1  push    eax; pcbElement
0x1013a5d2  push    ebx; pbElement
0x1013a5d3  push    0; dwFlags
0x1013a5d5  push    esi; pCertContext
0x1013a5d6  call    ds:__imp__CertSerializeCertificateStoreElement@16; CertSerializeCertificateStoreElement(x,x,x,x)
0x1013a5dc  test    eax, eax
0x1013a5de  jnz     short loc_1013A605
0x1013a5e0  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a5e6  mov     edi, eax
0x1013a5e8  test    edi, edi
0x1013a5ea  jle     short loc_1013A5F5
0x1013a5ec  movzx   edi, di
0x1013a5ef  or      edi, 80070000h
0x1013a5f5  push    ebx; pv
0x1013a5f6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1013a5fc  mov     [ebp+cbCertSerial], 0
0x1013a603  jmp     short loc_1013A647
0x1013a605  mov     eax, [ebp+var_8]
0x1013a608  mov     eax, [eax]
0x1013a60a  mov     esi, [eax+7Ch]
0x1013a60d  mov     this, esi; this
0x1013a60f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a615  mov     this, [ebp+var_8]
0x1013a618  call    esi
0x1013a61a  mov     this, [ebp+var_8]
0x1013a61d  mov     eax, [ebp+cbCertSerial]
0x1013a620  mov     [ebp+cbCertSerial], edi
0x1013a623  mov     [this+10Ch], eax
0x1013a629  mov     eax, [this]
0x1013a62b  mov     [this+110h], ebx
0x1013a631  mov     esi, [eax+80h]
0x1013a637  mov     this, esi; this
0x1013a639  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a63f  mov     this, [ebp+var_8]
0x1013a642  call    esi
0x1013a644  mov     esi, [ebp+var_C]
0x1013a647  push    esi; pCertContext
0x1013a648  call    ds:__imp__CertFreeCertificateContext@4; CertFreeCertificateContext(x)
0x1013a64e  push    0; dwFlags
0x1013a650  push    [ebp+hCertStore]; hCertStore
0x1013a653  call    ds:__imp__CertCloseStore@8; CertCloseStore(x,x)
0x1013a659  mov     this, edi; __annotation("TMF:",
0x1013a65b  sar     this, 1Fh
0x1013a65e  mov     eax, this
0x1013a660  shl     eax, 4
0x1013a663  test    byte_101857A0[eax], 8
0x1013a66a  jz      short loc_1013A683
0x1013a66c  push    edi; _a1
0x1013a66d  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a672  add     this, 2
0x1013a675  shl     this, 9
0x1013a678  push    74h ; 't'
0x1013a67a  or      this, 3; LevelKeyword
0x1013a67d  pop     edx; id
0x1013a67e  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a683  mov     eax, edi
0x1013a685  pop     edi
0x1013a686  pop     esi
0x1013a687  pop     ebx
0x1013a688  leave
0x1013a689  retn    8
```
