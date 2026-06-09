# HTTPStream::SelectCertificate(void)

- ea: `0x1013dede`
- end: `0x1013dff4`
- name: `?SelectCertificate@HTTPStream@@IAEJXZ`
- size: `278`
- prototype: `HRESULT __thiscall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1013e020`

## callees

- `0x1013dede`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013df20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013df3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dfc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013df20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013df3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dfc2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1013dfb8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1013dfb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013df01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013df01`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013df08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013df08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013dfdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013dfdb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1013df12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1013df12`
- `WINHTTP!WinHttpSetOption` at `0x1013df87`
- `WINHTTP!WinHttpSetOption` at `0x1013df87`
- `CRYPT32!CertFindCertificateInStore` at `0x1013df70`
- `CRYPT32!CertFindCertificateInStore` at `0x1013df70`
- `CRYPT32!CertFreeCertificateContext` at `0x1013df91`
- `CRYPT32!CertFreeCertificateContext` at `0x1013df91`
- `CRYPT32!CertCloseStore` at `0x1013dfa1`
- `CRYPT32!CertCloseStore` at `0x1013dfa1`
- `CRYPT32!CertOpenStore` at `0x1013df58`
- `CRYPT32!CertOpenStore` at `0x1013df58`

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
0x1013dede  mov     edi, edi
0x1013dee0  push    ebp
0x1013dee1  mov     ebp, esp
0x1013dee3  sub     esp, 0Ch
0x1013dee6  push    ebx
0x1013dee7  push    esi
0x1013dee8  lea     eax, [ebp+hThreadToken]
0x1013deeb  mov     [ebp+var_C], this
0x1013deee  xor     this, this
0x1013def0  push    eax; TokenHandle
0x1013def1  push    this; OpenAsSelf
0x1013def2  push    2000Ch; DesiredAccess
0x1013def7  mov     ebx, this
0x1013def9  mov     [ebp+var_1], cl
0x1013defc  mov     esi, this
0x1013defe  mov     [ebp+hThreadToken], this
0x1013df01  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x1013df07  push    eax; ThreadHandle
0x1013df08  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x1013df0e  test    eax, eax
0x1013df10  jz      short loc_1013DF37
0x1013df12  call    ds:__imp__RevertToSelf@0; RevertToSelf()
0x1013df18  test    eax, eax
0x1013df1a  jnz     short loc_1013DF47
0x1013df1c  mov     [ebp+var_1], 1
0x1013df20  call    ds:__imp__GetLastError@0; GetLastError()
0x1013df26  mov     esi, eax
0x1013df28  test    esi, esi
0x1013df2a  jle     short loc_1013DFA8
0x1013df2c  movzx   esi, si
0x1013df2f  or      esi, 80070000h
0x1013df35  jmp     short loc_1013DFA8
0x1013df37  mov     [ebp+hThreadToken], ebx
0x1013df3a  call    ds:__imp__GetLastError@0; GetLastError()
0x1013df40  cmp     eax, 3F0h
0x1013df45  jnz     short loc_1013DF20
0x1013df47  push    edi
0x1013df48  push    offset aMy; "MY"
0x1013df4d  push    1C000h; dwFlags
0x1013df52  push    0; hCryptProv
0x1013df54  push    0; dwEncodingType
0x1013df56  push    0Ah; lpszStoreProvider
0x1013df58  call    ds:__imp__CertOpenStore@20; CertOpenStore(x,x,x,x,x)
0x1013df5e  mov     edi, eax
0x1013df60  test    edi, edi
0x1013df62  jz      short loc_1013DFA7
0x1013df64  xor     eax, eax
0x1013df66  push    eax; pPrevCertContext
0x1013df67  push    eax; pvFindPara
0x1013df68  push    eax; dwFindType
0x1013df69  push    eax; dwFindFlags
0x1013df6a  push    10001h; dwCertEncodingType
0x1013df6f  push    edi; hCertStore
0x1013df70  call    ds:__imp__CertFindCertificateInStore@24; CertFindCertificateInStore(x,x,x,x,x,x)
0x1013df76  mov     ebx, eax
0x1013df78  test    ebx, ebx
0x1013df7a  jz      short cleanup_1
0x1013df7c  mov     eax, [ebp+var_C]
0x1013df7f  push    14h; dwBufferLength
0x1013df81  push    ebx; lpBuffer
0x1013df82  push    2Fh ; '/'; dwOption
0x1013df84  push    dword ptr [eax+5Ch]; hInternet
0x1013df87  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013df8d  push    ebx; pCertContext
0x1013df8e  mov     [ebp+var_C], eax
0x1013df91  call    ds:__imp__CertFreeCertificateContext@4; CertFreeCertificateContext(x)
0x1013df97  mov     ebx, [ebp+var_C]
0x1013df9a  jmp     short loc_1013DF9E
0x1013df9c  xor     ebx, ebx
0x1013df9e  push    0; dwFlags
0x1013dfa0  push    edi; hCertStore
0x1013dfa1  call    ds:__imp__CertCloseStore@8; CertCloseStore(x,x)
0x1013dfa7  pop     edi
0x1013dfa8  mov     eax, [ebp+hThreadToken]
0x1013dfab  test    eax, eax
0x1013dfad  jz      short loc_1013DFE1
0x1013dfaf  cmp     [ebp+var_1], 0
0x1013dfb3  jnz     short loc_1013DFDA
0x1013dfb5  push    eax; Token
0x1013dfb6  push    0; Thread
0x1013dfb8  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x1013dfbe  test    eax, eax
0x1013dfc0  jnz     short loc_1013DFD7
0x1013dfc2  call    ds:__imp__GetLastError@0; GetLastError()
0x1013dfc8  mov     esi, eax
0x1013dfca  test    esi, esi
0x1013dfcc  jle     short loc_1013DFD7
0x1013dfce  movzx   esi, si
0x1013dfd1  or      esi, 80070000h
0x1013dfd7  mov     eax, [ebp+hThreadToken]
0x1013dfda  push    eax; hObject
0x1013dfdb  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1013dfe1  test    esi, esi
0x1013dfe3  jns     short loc_1013DFE9
0x1013dfe5  mov     eax, esi
0x1013dfe7  jmp     short loc_1013DFF0
0x1013dfe9  xor     eax, eax
0x1013dfeb  test    ebx, ebx
0x1013dfed  setz    al
0x1013dff0  pop     esi
0x1013dff1  pop     ebx
0x1013dff2  leave
0x1013dff3  retn
```
