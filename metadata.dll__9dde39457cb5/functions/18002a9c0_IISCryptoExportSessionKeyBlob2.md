# IISCryptoExportSessionKeyBlob2

- ea: `0x18002a9c0`
- end: `0x18002ad3d`
- name: `IISCryptoExportSessionKeyBlob2`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18002a1f8`

## callees

- `0x18002937c`
- `0x180029bc8`
- `0x180029c24`
- `0x180029e24`
- `0x18002a9c0`
- `0x18002ae00`
- `0x1800309d0`

## import_xrefs

- `ADVAPI32!CryptGenRandom` at `0x18002aa4e`
- `ADVAPI32!CryptGenRandom` at `0x18002aa4e`
- `ADVAPI32!CryptExportKey` at `0x18002abbc`
- `ADVAPI32!CryptExportKey` at `0x18002ac6c`
- `ADVAPI32!CryptExportKey` at `0x18002abbc`
- `ADVAPI32!CryptExportKey` at `0x18002ac6c`
- `ADVAPI32!CryptDestroyKey` at `0x18002aca0`
- `ADVAPI32!CryptDestroyKey` at `0x18002aca0`
- `ADVAPI32!CryptHashData` at `0x18002aaf2`
- `ADVAPI32!CryptHashData` at `0x18002ab36`
- `ADVAPI32!CryptHashData` at `0x18002aaf2`
- `ADVAPI32!CryptHashData` at `0x18002ab36`
- `ole32!CoTaskMemAlloc` at `0x18002ac27`
- `ole32!CoTaskMemAlloc` at `0x18002ac27`
- `ole32!CoTaskMemFree` at `0x18002ad1a`
- `ole32!CoTaskMemFree` at `0x18002ad1a`
- `KERNEL32!SetLastError` at `0x18002acf9`
- `KERNEL32!SetLastError` at `0x18002acf9`
- `IisRTL!PuDbgPrint` at `0x18002aa97`
- `IisRTL!PuDbgPrint` at `0x18002aa97`

## string_xrefs

- `0x18002aa76`: `IISCryptoExportSessionKeyBlobWithPasswd.CryptGenRandom (advapi32.dll) failed err=0x%x.\n`
- `0x18002aacb`: `IISCryptoExportSessionKeyBlobWithPasswd.IISCryptoCreateHash failed err=0x%x.\n`
- `0x18002abe4`: `IISCryptoExportSessionKeyBlobWithPasswd.CryptExportKey (advapi32.dll) failed err=0x%x.\n`
- `0x18002acc4`: `IISCryptoExportSessionKeyBlobWithPasswd.CryptDestroyKey (advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoExportSessionKeyBlob2(_QWORD *a1, HCRYPTPROV a2, HCRYPTKEY a3, const BYTE *a4)
{
  __int64 result; // rax
  _DWORD *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // r8
  int KeyDeriveKey2; // eax
  unsigned int v15; // eax
  DWORD v16; // esi
  DWORD v17; // eax
  DWORD v18; // ebx
  LPVOID v19; // rax
  unsigned int v20; // eax
  unsigned int LastError; // eax
  DWORD *pdwDataLen; // [rsp+28h] [rbp-38h]
  DWORD *pdwDataLena; // [rsp+28h] [rbp-38h]
  DWORD v24; // [rsp+30h] [rbp-30h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-28h] BYREF
  HCRYPTKEY hExpKey; // [rsp+40h] [rbp-20h] BYREF
  BYTE pbBuffer[16]; // [rsp+48h] [rbp-18h] BYREF

  *(_OWORD *)pbBuffer = 0;
  v24 = 0;
  hExpKey = 0;
  if ( dword_180048964 )
  {
    v9 = 0;
    hHash = 0;
    if ( CryptGenRandom(a2, 0x10u, pbBuffer) )
    {
      v12 = IISCryptoCreateHash(&hHash, a2);
      v11 = v12;
      if ( v12 >= 0 )
      {
        if ( !hHash )
          return (unsigned int)-2147467259;
        if ( CryptHashData(hHash, pbBuffer, 0x10u, 0) )
        {
          v13 = -1;
          do
            ++v13;
          while ( a4[v13] );
          if ( CryptHashData(hHash, a4, v13, 0) )
          {
            KeyDeriveKey2 = IISCryptoGetKeyDeriveKey2(&hExpKey, a2, hHash);
            v11 = KeyDeriveKey2;
            if ( KeyDeriveKey2 >= 0 )
            {
              if ( CryptExportKey(a3, hExpKey, 0xBu, 0, 0, &v24) )
              {
                v16 = v24;
                v17 = (v24 + 7) & 0xFFFFFFF8;
                if ( v17 < v24 || (v18 = v17 + 24, v17 + 24 < v17) || v17 == -24 || v17 + 32 < v17 + 24 )
                {
                  SetLastError(8u);
                }
                else
                {
                  v19 = CoTaskMemAlloc(v17 + 32);
                  v9 = v19;
                  if ( v19 )
                  {
                    *(_DWORD *)v19 = 1649632073;
                    *((_DWORD *)v19 + 1) = v18;
                    *((_DWORD *)v19 + 2) = v16;
                    *((_DWORD *)v19 + 3) = 16;
                    if ( CryptExportKey(a3, hExpKey, 0xBu, 0, (BYTE *)v19 + 16, &v24) )
                    {
                      if ( CryptDestroyKey(hExpKey) )
                      {
                        *(_OWORD *)((char *)v9 + ((v9[2] + 7) & 0xFFFFFFF8) + 16) = *(_OWORD *)pbBuffer;
                        IISCryptoDestroyHash(hHash);
                        result = 0;
                        *a1 = v9;
                        return result;
                      }
                      LastError = IcpGetLastError();
                      v11 = LastError;
                      if ( (g_dwDebugFlags & 3) != 0 )
                      {
                        LODWORD(pdwDataLena) = LastError;
                        PuDbgPrint(
                          g_pDebug,
                          "inetsrv\\iis\\mb\\crypto\\key.cxx",
                          1012,
                          "IISCryptoExportSessionKeyBlob2",
                          "IISCryptoExportSessionKeyBlobWithPasswd.CryptDestroyKey (advapi32.dll) failed err=0x%x.\n",
                          pdwDataLena);
                      }
                    }
                    else
                    {
                      v20 = IcpGetLastError();
                      v11 = v20;
                      if ( (g_dwDebugFlags & 3) != 0 )
                      {
                        LODWORD(pdwDataLena) = v20;
                        PuDbgPrint(
                          g_pDebug,
                          "inetsrv\\iis\\mb\\crypto\\key.cxx",
                          1004,
                          "IISCryptoExportSessionKeyBlob2",
                          "IISCryptoExportSessionKeyBlob.CryptExportKey failed err=0x%x.\n",
                          pdwDataLena);
                      }
                    }
                    goto LABEL_43;
                  }
                }
                v11 = -2147024888;
              }
              else
              {
                v15 = IcpGetLastError();
                v11 = v15;
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  LODWORD(pdwDataLen) = v15;
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\crypto\\key.cxx",
                    970,
                    "IISCryptoExportSessionKeyBlob2",
                    "IISCryptoExportSessionKeyBlobWithPasswd.CryptExportKey (advapi32.dll) failed err=0x%x.\n",
                    pdwDataLen);
                }
              }
            }
            else if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\crypto\\key.cxx",
                952,
                "IISCryptoExportSessionKeyBlob2",
                "IISCryptoExportSessionKeyBlobWithPasswd.IISCryptoGetKeyDeriveKey2 failed err=0x%x.\n",
                KeyDeriveKey2);
            }
          }
          else if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              938,
              "IISCryptoExportSessionKeyBlob2",
              "IISCryptoExportSessionKeyBlobWithPasswd.CryptHashData failed err=0x%x.\n",
              v11);
          }
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            928,
            "IISCryptoExportSessionKeyBlob2",
            "IISCryptoExportSessionKeyBlobWithPasswd.CryptHashData failed err=0x%x.\n",
            v11);
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          910,
          "IISCryptoExportSessionKeyBlob2",
          "IISCryptoExportSessionKeyBlobWithPasswd.IISCryptoCreateHash failed err=0x%x.\n",
          v12);
      }
    }
    else
    {
      v10 = IcpGetLastError();
      v11 = v10;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          899,
          "IISCryptoExportSessionKeyBlob2",
          "IISCryptoExportSessionKeyBlobWithPasswd.CryptGenRandom (advapi32.dll) failed err=0x%x.\n",
          v10);
    }
LABEL_43:
    if ( hHash )
      IISCryptoDestroyHash(hHash);
    if ( v9 )
      CoTaskMemFree(v9);
    return v11;
  }
  if ( a2 == 1984918096 && a3 == 1800627539 )
    return IISCryptoCreateCleartextBlob(a1, Locale, 1);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18002a9c0  push    rbp
0x18002a9c2  push    rbx
0x18002a9c3  push    rsi
0x18002a9c4  push    rdi
0x18002a9c5  push    r12
0x18002a9c7  push    r14
0x18002a9c9  push    r15
0x18002a9cb  mov     rbp, rsp
0x18002a9ce  sub     rsp, 60h
0x18002a9d2  mov     rax, cs:__security_cookie
0x18002a9d9  xor     rax, rsp
0x18002a9dc  mov     [rbp+var_8], rax
0x18002a9e0  cmp     cs:dword_180048964, 0
0x18002a9e7  xorps   xmm0, xmm0
0x18002a9ea  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x18002a9ee  mov     r15, r9
0x18002a9f1  mov     [rbp+var_30], 0
0x18002a9f8  mov     r14, r8
0x18002a9fb  mov     [rbp+hExpKey], 0
0x18002aa03  mov     rsi, rdx
0x18002aa06  mov     r12, rcx
0x18002aa09  jnz     short loc_18002AA3E
0x18002aa0b  cmp     rdx, 764F7250h
0x18002aa12  jnz     short loc_18002AA34
0x18002aa14  cmp     r8, 6B536553h
0x18002aa1b  jnz     short loc_18002AA34
0x18002aa1d  mov     r8d, 1
0x18002aa23  lea     rdx, Locale
0x18002aa2a  call    IISCryptoCreateCleartextBlob
0x18002aa2f  jmp     loc_18002AD22
0x18002aa34  mov     eax, 80070057h
0x18002aa39  jmp     loc_18002AD22
0x18002aa3e  xor     edi, edi
0x18002aa40  lea     r8, [rbp+pbBuffer]; pbBuffer
0x18002aa44  mov     rcx, rsi; hProv
0x18002aa47  mov     [rbp+hHash], rdi
0x18002aa4b  lea     edx, [rdi+10h]; dwLen
0x18002aa4e  call    cs:__imp_CryptGenRandom
0x18002aa54  test    eax, eax
0x18002aa56  jnz     short loc_18002AAA2
0x18002aa58  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002aa5d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002aa64  mov     ebx, eax
0x18002aa66  jz      loc_18002AD04
0x18002aa6c  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002aa70  mov     r8d, 383h
0x18002aa76  lea     rax, aIiscryptoexpor_0; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002aa7d  mov     rcx, cs:g_pDebug
0x18002aa84  lea     r9, aIiscryptoexpor_7; "IISCryptoExportSessionKeyBlob2"
0x18002aa8b  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002aa92  mov     [rsp+60h+pbData], rax
0x18002aa97  call    cs:__imp_PuDbgPrint
0x18002aa9d  jmp     loc_18002AD04
0x18002aaa2  mov     rdx, rsi; hProv
0x18002aaa5  lea     rcx, [rbp+hHash]; phHash
0x18002aaa9  call    IISCryptoCreateHash
0x18002aaae  mov     ebx, eax
0x18002aab0  test    eax, eax
0x18002aab2  jns     short loc_18002AAD4
0x18002aab4  test    byte ptr cs:g_dwDebugFlags, 3
0x18002aabb  jz      loc_18002AD04
0x18002aac1  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002aac5  mov     r8d, 38Eh
0x18002aacb  lea     rax, aIiscryptoexpor_12; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002aad2  jmp     short loc_18002AA7D
0x18002aad4  mov     rcx, [rbp+hHash]; hHash
0x18002aad8  test    rcx, rcx
0x18002aadb  jnz     short loc_18002AAE7
0x18002aadd  mov     ebx, 80004005h
0x18002aae2  jmp     loc_18002AD20
0x18002aae7  xor     r9d, r9d; dwFlags
0x18002aaea  lea     rdx, [rbp+pbBuffer]; pbData
0x18002aaee  lea     r8d, [r9+10h]; dwDataLen
0x18002aaf2  call    cs:__imp_CryptHashData
0x18002aaf8  test    eax, eax
0x18002aafa  jnz     short loc_18002AB1F
0x18002aafc  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ab03  jz      loc_18002AD04
0x18002ab09  mov     dword ptr [rsp+60h+pdwDataLen], ebx
0x18002ab0d  lea     rax, aIiscryptoexpor_4; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002ab14  mov     r8d, 3A0h
0x18002ab1a  jmp     loc_18002AA7D
0x18002ab1f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ab23  inc     r8; dwDataLen
0x18002ab26  cmp     [r15+r8], dil
0x18002ab2a  jnz     short loc_18002AB23
0x18002ab2c  mov     rcx, [rbp+hHash]; hHash
0x18002ab30  xor     r9d, r9d; dwFlags
0x18002ab33  mov     rdx, r15; pbData
0x18002ab36  call    cs:__imp_CryptHashData
0x18002ab3c  test    eax, eax
0x18002ab3e  jnz     short loc_18002AB63
0x18002ab40  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ab47  jz      loc_18002AD04
0x18002ab4d  mov     dword ptr [rsp+60h+pdwDataLen], ebx
0x18002ab51  lea     rax, aIiscryptoexpor_4; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002ab58  mov     r8d, 3AAh
0x18002ab5e  jmp     loc_18002AA7D
0x18002ab63  mov     r9d, [rbp+arg_20]
0x18002ab67  lea     rcx, [rbp+hExpKey]; phKey
0x18002ab6b  mov     r8, [rbp+hHash]; hBaseData
0x18002ab6f  mov     rdx, rsi; hProv
0x18002ab72  call    IISCryptoGetKeyDeriveKey2
0x18002ab77  mov     ebx, eax
0x18002ab79  test    eax, eax
0x18002ab7b  jns     short loc_18002ABA0
0x18002ab7d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ab84  jz      loc_18002AD04
0x18002ab8a  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002ab8e  mov     r8d, 3B8h
0x18002ab94  lea     rax, aIiscryptoexpor_2; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002ab9b  jmp     loc_18002AA7D
0x18002aba0  mov     rdx, [rbp+hExpKey]; hExpKey
0x18002aba4  lea     rax, [rbp+var_30]
0x18002aba8  xor     r9d, r9d; dwFlags
0x18002abab  mov     [rsp+60h+pdwDataLen], rax; pdwDataLen
0x18002abb0  mov     rcx, r14; hKey
0x18002abb3  mov     [rsp+60h+pbData], rdi; pbData
0x18002abb8  lea     r8d, [r9+0Bh]; dwBlobType
0x18002abbc  call    cs:__imp_CryptExportKey
0x18002abc2  test    eax, eax
0x18002abc4  jnz     short loc_18002ABF0
0x18002abc6  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002abcb  test    byte ptr cs:g_dwDebugFlags, 3
0x18002abd2  mov     ebx, eax
0x18002abd4  jz      loc_18002AD04
0x18002abda  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002abde  mov     r8d, 3CAh
0x18002abe4  lea     rax, aIiscryptoexpor_10; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002abeb  jmp     loc_18002AA7D
0x18002abf0  mov     esi, [rbp+var_30]
0x18002abf3  mov     r15d, 0FFFFFFF8h
0x18002abf9  lea     eax, [rsi+7]
0x18002abfc  and     eax, r15d
0x18002abff  cmp     eax, esi
0x18002ac01  jb      loc_18002ACF4
0x18002ac07  lea     ebx, [rax+18h]
0x18002ac0a  cmp     ebx, eax
0x18002ac0c  jb      loc_18002ACF4
0x18002ac12  test    ebx, ebx
0x18002ac14  jz      loc_18002ACF4
0x18002ac1a  lea     eax, [rbx+8]
0x18002ac1d  cmp     eax, ebx
0x18002ac1f  jb      loc_18002ACF4
0x18002ac25  mov     ecx, eax; cb
0x18002ac27  call    cs:__imp_CoTaskMemAlloc
0x18002ac2d  mov     rdi, rax
0x18002ac30  test    rax, rax
0x18002ac33  jz      loc_18002ACFF
0x18002ac39  mov     dword ptr [rax], 62536349h
0x18002ac3f  lea     rcx, [rbp+var_30]
0x18002ac43  mov     [rax+4], ebx
0x18002ac46  xor     r9d, r9d; dwFlags
0x18002ac49  mov     [rax+8], esi
0x18002ac4c  mov     dword ptr [rax+0Ch], 10h
0x18002ac53  add     rax, 10h
0x18002ac57  mov     rdx, [rbp+hExpKey]; hExpKey
0x18002ac5b  mov     [rsp+60h+pdwDataLen], rcx; pdwDataLen
0x18002ac60  lea     r8d, [r9+0Bh]; dwBlobType
0x18002ac64  mov     rcx, r14; hKey
0x18002ac67  mov     [rsp+60h+pbData], rax; pbData
0x18002ac6c  call    cs:__imp_CryptExportKey
0x18002ac72  test    eax, eax
0x18002ac74  jnz     short loc_18002AC9C
0x18002ac76  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002ac7b  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ac82  mov     ebx, eax
0x18002ac84  jz      short loc_18002AD04
0x18002ac86  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002ac8a  mov     r8d, 3ECh
0x18002ac90  lea     rax, aIiscryptoexpor; "IISCryptoExportSessionKeyBlob.CryptExpo"...
0x18002ac97  jmp     loc_18002AA7D
0x18002ac9c  mov     rcx, [rbp+hExpKey]; hKey
0x18002aca0  call    cs:__imp_CryptDestroyKey
0x18002aca6  test    eax, eax
0x18002aca8  jnz     short loc_18002ACD0
0x18002acaa  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002acaf  test    byte ptr cs:g_dwDebugFlags, 3
0x18002acb6  mov     ebx, eax
0x18002acb8  jz      short loc_18002AD04
0x18002acba  mov     dword ptr [rsp+60h+pdwDataLen], eax
0x18002acbe  mov     r8d, 3F4h
0x18002acc4  lea     rax, aIiscryptoexpor_5; "IISCryptoExportSessionKeyBlobWithPasswd"...
0x18002accb  jmp     loc_18002AA7D
0x18002acd0  mov     eax, [rdi+8]
0x18002acd3  movups  xmm0, xmmword ptr [rbp+pbBuffer]
0x18002acd7  add     eax, 7
0x18002acda  and     rax, r15
0x18002acdd  movdqu  xmmword ptr [rax+rdi+10h], xmm0
0x18002ace3  mov     rcx, [rbp+hHash]
0x18002ace7  call    IISCryptoDestroyHash
0x18002acec  xor     eax, eax
0x18002acee  mov     [r12], rdi
0x18002acf2  jmp     short loc_18002AD22
0x18002acf4  mov     ecx, 8; dwErrCode
0x18002acf9  call    cs:__imp_SetLastError
0x18002acff  mov     ebx, 80070008h
0x18002ad04  mov     rcx, [rbp+hHash]
0x18002ad08  test    rcx, rcx
0x18002ad0b  jz      short loc_18002AD12
0x18002ad0d  call    IISCryptoDestroyHash
0x18002ad12  test    rdi, rdi
0x18002ad15  jz      short loc_18002AD20
0x18002ad17  mov     rcx, rdi; pv
0x18002ad1a  call    cs:__imp_CoTaskMemFree
0x18002ad20  mov     eax, ebx
0x18002ad22  mov     rcx, [rbp+var_8]
0x18002ad26  xor     rcx, rsp; StackCookie
0x18002ad29  call    __security_check_cookie
0x18002ad2e  add     rsp, 60h
0x18002ad32  pop     r15
0x18002ad34  pop     r14
0x18002ad36  pop     r12
0x18002ad38  pop     rdi
0x18002ad39  pop     rsi
0x18002ad3a  pop     rbx
0x18002ad3b  pop     rbp
0x18002ad3c  retn
```
