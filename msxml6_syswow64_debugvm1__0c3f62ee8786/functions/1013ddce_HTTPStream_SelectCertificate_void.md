# HTTPStream::SelectCertificate(void)

- ea: `0x1013ddce`
- end: `0x1013dee4`
- name: `?SelectCertificate@HTTPStream@@IAEJXZ`
- size: `278`
- prototype: `HRESULT __thiscall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1013df10`

## callees

- `0x1013ddce`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013deb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013de2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013deb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1013dea8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1013dea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013ddf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013ddf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013ddf8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013ddf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013decb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013decb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1013de02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1013de02`
- `WINHTTP!WinHttpSetOption` at `0x1013de77`
- `WINHTTP!WinHttpSetOption` at `0x1013de77`
- `CRYPT32!CertFindCertificateInStore` at `0x1013de60`
- `CRYPT32!CertFindCertificateInStore` at `0x1013de60`
- `CRYPT32!CertFreeCertificateContext` at `0x1013de81`
- `CRYPT32!CertFreeCertificateContext` at `0x1013de81`
- `CRYPT32!CertCloseStore` at `0x1013de91`
- `CRYPT32!CertCloseStore` at `0x1013de91`
- `CRYPT32!CertOpenStore` at `0x1013de48`
- `CRYPT32!CertOpenStore` at `0x1013de48`

## pseudocode

```c
HRESULT __thiscall HTTPStream::SelectCertificate(HTTPStream *this)
{
  BOOL v1; // ebx
  signed int v2; // esi
  HANDLE CurrentThread; // eax
  signed int LastError; // eax
  HCERTSTORE v5; // edi
  PCCERT_CONTEXT CertificateInStore; // ebx
  void *v7; // eax
  signed int v8; // eax
  BOOL v11; // [esp+8h] [ebp-Ch]
  void *hThreadToken; // [esp+Ch] [ebp-8h] BYREF
  char v13; // [esp+13h] [ebp-1h]

  v1 = 0;
  v13 = 0;
  v2 = 0;
  hThreadToken = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &hThreadToken) )
  {
    if ( !RevertToSelf() )
    {
      v13 = 1;
      goto LABEL_4;
    }
  }
  else
  {
    hThreadToken = 0;
    if ( GetLastError() != 1008 )
    {
LABEL_4:
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
  }
  v5 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x1C000u, L"MY");
  if ( v5 )
  {
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0, 0, 0);
    if ( CertificateInStore )
    {
      v11 = WinHttpSetOption(this->_hHTTP, 0x2Fu, (LPVOID)CertificateInStore, 0x14u);
      CertFreeCertificateContext(CertificateInStore);
      v1 = v11;
    }
    else
    {
      v1 = 0;
    }
    CertCloseStore(v5, 0);
  }
LABEL_12:
  v7 = hThreadToken;
  if ( hThreadToken )
  {
    if ( !v13 )
    {
      if ( !SetThreadToken(0, hThreadToken) )
      {
        v8 = GetLastError();
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
      }
      v7 = hThreadToken;
    }
    CloseHandle(v7);
  }
  if ( v2 >= 0 )
    return !v1;
  else
    return v2;
}

```

## disassembly

```asm
0x1013ddce  mov     edi, edi
0x1013ddd0  push    ebp
0x1013ddd1  mov     ebp, esp
0x1013ddd3  sub     esp, 0Ch
0x1013ddd6  push    ebx
0x1013ddd7  push    esi
0x1013ddd8  lea     eax, [ebp+hThreadToken]
0x1013dddb  mov     [ebp+var_C], this
0x1013ddde  xor     this, this
0x1013dde0  push    eax; TokenHandle
0x1013dde1  push    this; OpenAsSelf
0x1013dde2  push    2000Ch; DesiredAccess
0x1013dde7  mov     ebx, this
0x1013dde9  mov     [ebp+var_1], cl
0x1013ddec  mov     esi, this
0x1013ddee  mov     [ebp+hThreadToken], this
0x1013ddf1  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x1013ddf7  push    eax; ThreadHandle
0x1013ddf8  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x1013ddfe  test    eax, eax
0x1013de00  jz      short loc_1013DE27
0x1013de02  call    ds:__imp__RevertToSelf@0; RevertToSelf()
0x1013de08  test    eax, eax
0x1013de0a  jnz     short loc_1013DE37
0x1013de0c  mov     [ebp+var_1], 1
0x1013de10  call    ds:__imp__GetLastError@0; GetLastError()
0x1013de16  mov     esi, eax
0x1013de18  test    esi, esi
0x1013de1a  jle     short loc_1013DE98
0x1013de1c  movzx   esi, si
0x1013de1f  or      esi, 80070000h
0x1013de25  jmp     short loc_1013DE98
0x1013de27  mov     [ebp+hThreadToken], ebx
0x1013de2a  call    ds:__imp__GetLastError@0; GetLastError()
0x1013de30  cmp     eax, 3F0h
0x1013de35  jnz     short loc_1013DE10
0x1013de37  push    edi
0x1013de38  push    offset aMy; "MY"
0x1013de3d  push    1C000h; dwFlags
0x1013de42  push    0; hCryptProv
0x1013de44  push    0; dwEncodingType
0x1013de46  push    0Ah; lpszStoreProvider
0x1013de48  call    ds:__imp__CertOpenStore@20; CertOpenStore(x,x,x,x,x)
0x1013de4e  mov     edi, eax
0x1013de50  test    edi, edi
0x1013de52  jz      short loc_1013DE97
0x1013de54  xor     eax, eax
0x1013de56  push    eax; pPrevCertContext
0x1013de57  push    eax; pvFindPara
0x1013de58  push    eax; dwFindType
0x1013de59  push    eax; dwFindFlags
0x1013de5a  push    10001h; dwCertEncodingType
0x1013de5f  push    edi; hCertStore
0x1013de60  call    ds:__imp__CertFindCertificateInStore@24; CertFindCertificateInStore(x,x,x,x,x,x)
0x1013de66  mov     ebx, eax
0x1013de68  test    ebx, ebx
0x1013de6a  jz      short cleanup_1
0x1013de6c  mov     eax, [ebp+var_C]
0x1013de6f  push    14h; dwBufferLength
0x1013de71  push    ebx; lpBuffer
0x1013de72  push    2Fh ; '/'; dwOption
0x1013de74  push    dword ptr [eax+5Ch]; hInternet
0x1013de77  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013de7d  push    ebx; pCertContext
0x1013de7e  mov     [ebp+var_C], eax
0x1013de81  call    ds:__imp__CertFreeCertificateContext@4; CertFreeCertificateContext(x)
0x1013de87  mov     ebx, [ebp+var_C]
0x1013de8a  jmp     short loc_1013DE8E
0x1013de8c  xor     ebx, ebx
0x1013de8e  push    0; dwFlags
0x1013de90  push    edi; hCertStore
0x1013de91  call    ds:__imp__CertCloseStore@8; CertCloseStore(x,x)
0x1013de97  pop     edi
0x1013de98  mov     eax, [ebp+hThreadToken]
0x1013de9b  test    eax, eax
0x1013de9d  jz      short loc_1013DED1
0x1013de9f  cmp     [ebp+var_1], 0
0x1013dea3  jnz     short loc_1013DECA
0x1013dea5  push    eax; Token
0x1013dea6  push    0; Thread
0x1013dea8  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x1013deae  test    eax, eax
0x1013deb0  jnz     short loc_1013DEC7
0x1013deb2  call    ds:__imp__GetLastError@0; GetLastError()
0x1013deb8  mov     esi, eax
0x1013deba  test    esi, esi
0x1013debc  jle     short loc_1013DEC7
0x1013debe  movzx   esi, si
0x1013dec1  or      esi, 80070000h
0x1013dec7  mov     eax, [ebp+hThreadToken]
0x1013deca  push    eax; hObject
0x1013decb  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1013ded1  test    esi, esi
0x1013ded3  jns     short loc_1013DED9
0x1013ded5  mov     eax, esi
0x1013ded7  jmp     short loc_1013DEE0
0x1013ded9  xor     eax, eax
0x1013dedb  test    ebx, ebx
0x1013dedd  setz    al
0x1013dee0  pop     esi
0x1013dee1  pop     ebx
0x1013dee2  leave
0x1013dee3  retn
```
