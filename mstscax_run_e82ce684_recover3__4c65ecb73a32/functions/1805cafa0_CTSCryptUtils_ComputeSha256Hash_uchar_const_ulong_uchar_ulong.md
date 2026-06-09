# CTSCryptUtils::ComputeSha256Hash(uchar * const,ulong,uchar * *,ulong *)

- ea: `0x1805cafa0`
- end: `0x1805cb4b8`
- name: `?ComputeSha256Hash@CTSCryptUtils@@SAJQEAEKPEAPEAEPEAK@Z`
- size: `1304`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, unsigned __int8 **, unsigned int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180390c44`
- `0x180392154`
- `0x1804e1408`
- `0x1804e1950`
- `0x1805e1390`

## callees

- `0x180001e8c`
- `0x18002a374`
- `0x1800dafe4`
- `0x18012962c`
- `0x18012966c`
- `0x1805cafa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1805cb0d8`
- `KERNEL32!GetLastError` at `0x1805cb19b`
- `KERNEL32!GetLastError` at `0x1805cb249`
- `KERNEL32!GetLastError` at `0x1805cb303`
- `KERNEL32!GetLastError` at `0x1805cb3d6`
- `KERNEL32!GetLastError` at `0x1805cb0d8`
- `KERNEL32!GetLastError` at `0x1805cb19b`
- `KERNEL32!GetLastError` at `0x1805cb249`
- `KERNEL32!GetLastError` at `0x1805cb303`
- `KERNEL32!GetLastError` at `0x1805cb3d6`
- `ADVAPI32!CryptAcquireContextW` at `0x1805cb0ca`
- `ADVAPI32!CryptAcquireContextW` at `0x1805cb0ca`
- `ADVAPI32!CryptCreateHash` at `0x1805cb18d`
- `ADVAPI32!CryptCreateHash` at `0x1805cb18d`
- `ADVAPI32!CryptReleaseContext` at `0x1805cb498`
- `ADVAPI32!CryptReleaseContext` at `0x1805cb498`
- `ADVAPI32!CryptHashData` at `0x1805cb23b`
- `ADVAPI32!CryptHashData` at `0x1805cb23b`
- `ADVAPI32!CryptGetHashParam` at `0x1805cb2f5`
- `ADVAPI32!CryptGetHashParam` at `0x1805cb3c8`
- `ADVAPI32!CryptGetHashParam` at `0x1805cb2f5`
- `ADVAPI32!CryptGetHashParam` at `0x1805cb3c8`
- `ADVAPI32!CryptDestroyHash` at `0x1805cb487`
- `ADVAPI32!CryptDestroyHash` at `0x1805cb487`

## string_xrefs

- `0x1805cb111`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1805cb1d4`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1805cb282`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1805cb33c`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1805cb40b`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1805cb0fc`: `ComputeSha256Hash`
- `0x1805cb1bf`: `ComputeSha256Hash`
- `0x1805cb26d`: `ComputeSha256Hash`
- `0x1805cb327`: `ComputeSha256Hash`
- `0x1805cb3f6`: `ComputeSha256Hash`
- `0x1805cb1e6`: `CryptCreateHash failed: 0x%X`

## pseudocode

```c
__int64 __fastcall CTSCryptUtils::ComputeSha256Hash(
        BYTE *pbData,
        __int64 dwDataLen,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  DWORD v6; // r14d
  int ActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // ebx
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  signed int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  signed int v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  signed int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  BYTE *v28; // rax
  unsigned __int8 *v29; // rdi
  signed int LastError; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned int v34; // eax
  int v36; // [rsp+50h] [rbp+7h] BYREF
  int v37; // [rsp+54h] [rbp+Bh] BYREF
  int v38; // [rsp+58h] [rbp+Fh] BYREF
  const char *v39; // [rsp+60h] [rbp+17h] BYREF
  const char *v40; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v41; // [rsp+70h] [rbp+27h] BYREF
  HCRYPTHASH phHash; // [rsp+78h] [rbp+2Fh] BYREF
  DWORD pdwDataLen; // [rsp+80h] [rbp+37h] BYREF
  HCRYPTPROV phProv; // [rsp+88h] [rbp+3Fh] BYREF
  DWORD pbDataa; // [rsp+B0h] [rbp+67h] BYREF

  phProv = 0;
  phHash = 0;
  v6 = dwDataLen;
  pbDataa = 0;
  pdwDataLen = 4;
  if ( !pbData )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, dwDataLen, a3, a4);
    v9 = 170;
    v10 = "pIn";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids,
      ActivityIdPrefix,
      (__int64)v10);
LABEL_7:
    v11 = -2147024809;
    goto LABEL_48;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, dwDataLen, 0, a4);
    v9 = 171;
    v10 = "ppOut";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, dwDataLen, a3, 0);
    v9 = 172;
    v10 = "pcbOut";
    goto LABEL_6;
  }
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      if ( CryptHashData(phHash, pbData, v6, 0) )
      {
        if ( CryptGetHashParam(phHash, 4u, (BYTE *)&pbDataa, &pdwDataLen, 0) )
        {
          v28 = (BYTE *)operator new(pbDataa);
          v29 = v28;
          if ( v28 )
          {
            if ( CryptGetHashParam(phHash, 2u, v28, &pbDataa, 0) )
            {
              v34 = pbDataa;
              *a3 = v29;
              *a4 = v34;
              v11 = 0;
            }
            else
            {
              LastError = GetLastError();
              v11 = LastError;
              if ( LastError > 0 )
                v11 = (unsigned __int16)LastError | 0x80070000;
              if ( (unsigned int)dword_1808B5850 > 2 )
              {
                v38 = v11;
                v41 = "ComputeSha256Hash";
                v37 = 2894;
                v40 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
                v39 = "CryptGetHashParam(HP_HASHVAL) failed: 0x%X";
                v36 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v31,
                  (unsigned int)&word_180888F36,
                  v32,
                  v33,
                  (__int64)&v39,
                  (__int64)&v36,
                  (__int64)&v40,
                  (__int64)&v37,
                  (__int64)&v41,
                  (__int64)&v38);
              }
              operator delete(v29);
            }
          }
          else
          {
            v11 = -2147024882;
          }
        }
        else
        {
          v24 = GetLastError();
          v11 = v24;
          if ( v24 > 0 )
            v11 = (unsigned __int16)v24 | 0x80070000;
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v38 = v11;
            v41 = "ComputeSha256Hash";
            v37 = 2880;
            v40 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
            v39 = "CryptGetHashParam(HP_HASHSIZE) failed: 0x%X";
            v36 = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v25,
              (unsigned int)&byte_180888F7F,
              v26,
              v27,
              (__int64)&v39,
              (__int64)&v36,
              (__int64)&v40,
              (__int64)&v37,
              (__int64)&v41,
              (__int64)&v38);
          }
        }
      }
      else
      {
        v20 = GetLastError();
        v11 = v20;
        if ( v20 > 0 )
          v11 = (unsigned __int16)v20 | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v38 = v11;
          v41 = "ComputeSha256Hash";
          v37 = 2872;
          v40 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
          v39 = "CryptHashData failed: 0x%X";
          v36 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v21,
            (unsigned int)qword_180888FC8,
            v22,
            v23,
            (__int64)&v39,
            (__int64)&v36,
            (__int64)&v40,
            (__int64)&v37,
            (__int64)&v41,
            (__int64)&v38);
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v38 = v11;
        v41 = "ComputeSha256Hash";
        v37 = 2864;
        v40 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
        v39 = "CryptCreateHash failed: 0x%X";
        v36 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_180889011,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v36,
          (__int64)&v40,
          (__int64)&v37,
          (__int64)&v41,
          (__int64)&v38);
      }
    }
  }
  else
  {
    v12 = GetLastError();
    v11 = v12;
    if ( v12 > 0 )
      v11 = (unsigned __int16)v12 | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v36 = v11;
      v39 = "ComputeSha256Hash";
      v37 = 2857;
      v40 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
      v41 = "CryptAcquireContext failed: 0x%X";
      v38 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&byte_180888D37,
        v14,
        v15,
        (__int64)&v41,
        (__int64)&v38,
        (__int64)&v40,
        (__int64)&v37,
        (__int64)&v39,
        (__int64)&v36);
    }
  }
LABEL_48:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v11;
}

```

## disassembly

```asm
0x1805cafa0  mov     [rsp-8+arg_8], rbx
0x1805cafa5  mov     [rsp-8+arg_10], rsi
0x1805cafaa  push    rbp
0x1805cafab  push    rdi
0x1805cafac  push    r14
0x1805cafae  lea     rbp, [rsp-47h]
0x1805cafb3  sub     rsp, 90h
0x1805cafba  mov     rbx, r9
0x1805cafbd  mov     [rbp+57h+phProv], 0
0x1805cafc5  mov     rsi, r8
0x1805cafc8  mov     [rbp+57h+phHash], 0
0x1805cafd0  mov     r14d, edx
0x1805cafd3  mov     [rbp+57h+pbData], 0
0x1805cafda  mov     rdi, rcx
0x1805cafdd  mov     [rbp+57h+pdwDataLen], 4
0x1805cafe4  test    rcx, rcx
0x1805cafe7  jnz     short loc_1805CB042
0x1805cafe9  mov     rcx, cs:WPP_GLOBAL_Control
0x1805caff0  lea     rax, WPP_GLOBAL_Control
0x1805caff7  cmp     rcx, rax
0x1805caffa  jz      short loc_1805CB038
0x1805caffc  test    byte ptr [rcx+1Ch], 8
0x1805cb000  jz      short loc_1805CB038
0x1805cb002  cmp     byte ptr [rcx+19h], 2
0x1805cb006  jb      short loc_1805CB038
0x1805cb008  call    RdpX_GetActivityIdPrefix
0x1805cb00d  mov     edx, 0AAh
0x1805cb012  lea     rcx, aPin; "pIn"
0x1805cb019  mov     qword ptr [rsp+0A0h+dwFlags], rcx
0x1805cb01e  lea     r8, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids
0x1805cb025  mov     rcx, cs:WPP_GLOBAL_Control
0x1805cb02c  mov     r9d, eax
0x1805cb02f  mov     rcx, [rcx+10h]
0x1805cb033  call    WPP_SF_Ds
0x1805cb038  mov     ebx, 80070057h
0x1805cb03d  jmp     loc_1805CB47E
0x1805cb042  test    rsi, rsi
0x1805cb045  jnz     short loc_1805CB079
0x1805cb047  mov     rcx, cs:WPP_GLOBAL_Control
0x1805cb04e  lea     rax, WPP_GLOBAL_Control
0x1805cb055  cmp     rcx, rax
0x1805cb058  jz      short loc_1805CB038
0x1805cb05a  test    byte ptr [rcx+1Ch], 8
0x1805cb05e  jz      short loc_1805CB038
0x1805cb060  cmp     byte ptr [rcx+19h], 2
0x1805cb064  jb      short loc_1805CB038
0x1805cb066  call    RdpX_GetActivityIdPrefix
0x1805cb06b  mov     edx, 0ABh
0x1805cb070  lea     rcx, pbBinary; "ppOut"
0x1805cb077  jmp     short loc_1805CB019
0x1805cb079  test    rbx, rbx
0x1805cb07c  jnz     short loc_1805CB0B3
0x1805cb07e  mov     rcx, cs:WPP_GLOBAL_Control
0x1805cb085  lea     rax, WPP_GLOBAL_Control
0x1805cb08c  cmp     rcx, rax
0x1805cb08f  jz      short loc_1805CB038
0x1805cb091  test    byte ptr [rcx+1Ch], 8
0x1805cb095  jz      short loc_1805CB038
0x1805cb097  cmp     byte ptr [rcx+19h], 2
0x1805cb09b  jb      short loc_1805CB038
0x1805cb09d  call    RdpX_GetActivityIdPrefix
0x1805cb0a2  mov     edx, 0ACh
0x1805cb0a7  lea     rcx, pszString; "pcbOut"
0x1805cb0ae  jmp     loc_1805CB019
0x1805cb0b3  mov     r9d, 18h; dwProvType
0x1805cb0b9  mov     [rsp+0A0h+dwFlags], 0F0000000h; dwFlags
0x1805cb0c1  xor     r8d, r8d; szProvider
0x1805cb0c4  lea     rcx, [rbp+57h+phProv]; phProv
0x1805cb0c8  xor     edx, edx; szContainer
0x1805cb0ca  call    cs:__imp_CryptAcquireContextW
0x1805cb0d0  test    eax, eax
0x1805cb0d2  jnz     loc_1805CB175
0x1805cb0d8  call    cs:__imp_GetLastError
0x1805cb0de  mov     ebx, eax
0x1805cb0e0  test    eax, eax
0x1805cb0e2  jle     short loc_1805CB0ED
0x1805cb0e4  movzx   ebx, ax
0x1805cb0e7  or      ebx, 80070000h
0x1805cb0ed  mov     eax, cs:dword_1808B5850
0x1805cb0f3  cmp     eax, 2
0x1805cb0f6  jbe     loc_1805CB47E
0x1805cb0fc  lea     rax, aComputesha256h; "ComputeSha256Hash"
0x1805cb103  mov     [rbp+57h+var_50], ebx
0x1805cb106  mov     [rbp+57h+var_40], rax
0x1805cb10a  lea     rdx, byte_180888D37
0x1805cb111  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1805cb118  mov     [rbp+57h+var_4C], 0B29h
0x1805cb11f  mov     [rbp+57h+var_38], rax
0x1805cb123  lea     rax, aCryptacquireco_0; "CryptAcquireContext failed: 0x%X"
0x1805cb12a  mov     [rbp+57h+var_30], rax
0x1805cb12e  lea     rax, [rbp+57h+var_50]
0x1805cb132  mov     [rsp+0A0h+var_58], rax
0x1805cb137  lea     rax, [rbp+57h+var_40]
0x1805cb13b  mov     [rsp+0A0h+var_60], rax
0x1805cb140  lea     rax, [rbp+57h+var_4C]
0x1805cb144  mov     [rsp+0A0h+var_68], rax
0x1805cb149  lea     rax, [rbp+57h+var_38]
0x1805cb14d  mov     [rsp+0A0h+var_70], rax
0x1805cb152  lea     rax, [rbp+57h+var_48]
0x1805cb156  mov     [rsp+0A0h+var_78], rax
0x1805cb15b  lea     rax, [rbp+57h+var_30]
0x1805cb15f  mov     [rbp+57h+var_48], 80004005h
0x1805cb166  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x1805cb16b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805cb170  jmp     loc_1805CB47E
0x1805cb175  mov     rcx, [rbp+57h+phProv]; hProv
0x1805cb179  lea     rax, [rbp+57h+phHash]
0x1805cb17d  xor     r9d, r9d; dwFlags
0x1805cb180  mov     qword ptr [rsp+0A0h+dwFlags], rax; phHash
0x1805cb185  xor     r8d, r8d; hKey
0x1805cb188  mov     edx, 800Ch; Algid
0x1805cb18d  call    cs:__imp_CryptCreateHash
0x1805cb193  test    eax, eax
0x1805cb195  jnz     loc_1805CB22E
0x1805cb19b  call    cs:__imp_GetLastError
0x1805cb1a1  mov     ebx, eax
0x1805cb1a3  test    eax, eax
0x1805cb1a5  jle     short loc_1805CB1B0
0x1805cb1a7  movzx   ebx, ax
0x1805cb1aa  or      ebx, 80070000h
0x1805cb1b0  mov     eax, cs:dword_1808B5850
0x1805cb1b6  cmp     eax, 2
0x1805cb1b9  jbe     loc_1805CB47E
0x1805cb1bf  lea     rax, aComputesha256h; "ComputeSha256Hash"
0x1805cb1c6  mov     [rbp+57h+var_48], ebx
0x1805cb1c9  mov     [rbp+57h+var_30], rax
0x1805cb1cd  lea     rdx, byte_180889011
0x1805cb1d4  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1805cb1db  mov     [rbp+57h+var_4C], 0B30h
0x1805cb1e2  mov     [rbp+57h+var_38], rax
0x1805cb1e6  lea     rax, aCryptcreatehas_1; "CryptCreateHash failed: 0x%X"
0x1805cb1ed  mov     [rbp+57h+var_40], rax
0x1805cb1f1  lea     rax, [rbp+57h+var_48]
0x1805cb1f5  mov     [rsp+0A0h+var_58], rax
0x1805cb1fa  lea     rax, [rbp+57h+var_30]
0x1805cb1fe  mov     [rsp+0A0h+var_60], rax
0x1805cb203  lea     rax, [rbp+57h+var_4C]
0x1805cb207  mov     [rsp+0A0h+var_68], rax
0x1805cb20c  lea     rax, [rbp+57h+var_38]
0x1805cb210  mov     [rsp+0A0h+var_70], rax
0x1805cb215  lea     rax, [rbp+57h+var_50]
0x1805cb219  mov     [rsp+0A0h+var_78], rax
0x1805cb21e  lea     rax, [rbp+57h+var_40]
0x1805cb222  mov     [rbp+57h+var_50], 80004005h
0x1805cb229  jmp     loc_1805CB166
0x1805cb22e  mov     rcx, [rbp+57h+phHash]; hHash
0x1805cb232  xor     r9d, r9d; dwFlags
0x1805cb235  mov     r8d, r14d; dwDataLen
0x1805cb238  mov     rdx, rdi; pbData
0x1805cb23b  call    cs:__imp_CryptHashData
0x1805cb241  test    eax, eax
0x1805cb243  jnz     loc_1805CB2DC
0x1805cb249  call    cs:__imp_GetLastError
0x1805cb24f  mov     ebx, eax
0x1805cb251  test    eax, eax
0x1805cb253  jle     short loc_1805CB25E
0x1805cb255  movzx   ebx, ax
0x1805cb258  or      ebx, 80070000h
0x1805cb25e  mov     eax, cs:dword_1808B5850
0x1805cb264  cmp     eax, 2
0x1805cb267  jbe     loc_1805CB47E
0x1805cb26d  lea     rax, aComputesha256h; "ComputeSha256Hash"
0x1805cb274  mov     [rbp+57h+var_48], ebx
0x1805cb277  mov     [rbp+57h+var_30], rax
0x1805cb27b  lea     rdx, qword_180888FC8
0x1805cb282  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1805cb289  mov     [rbp+57h+var_4C], 0B38h
0x1805cb290  mov     [rbp+57h+var_38], rax
0x1805cb294  lea     rax, aCrypthashdataF; "CryptHashData failed: 0x%X"
0x1805cb29b  mov     [rbp+57h+var_40], rax
0x1805cb29f  lea     rax, [rbp+57h+var_48]
0x1805cb2a3  mov     [rsp+0A0h+var_58], rax
0x1805cb2a8  lea     rax, [rbp+57h+var_30]
0x1805cb2ac  mov     [rsp+0A0h+var_60], rax
0x1805cb2b1  lea     rax, [rbp+57h+var_4C]
0x1805cb2b5  mov     [rsp+0A0h+var_68], rax
0x1805cb2ba  lea     rax, [rbp+57h+var_38]
0x1805cb2be  mov     [rsp+0A0h+var_70], rax
0x1805cb2c3  lea     rax, [rbp+57h+var_50]
0x1805cb2c7  mov     [rsp+0A0h+var_78], rax
0x1805cb2cc  lea     rax, [rbp+57h+var_40]
0x1805cb2d0  mov     [rbp+57h+var_50], 80004005h
0x1805cb2d7  jmp     loc_1805CB166
0x1805cb2dc  mov     rcx, [rbp+57h+phHash]; hHash
0x1805cb2e0  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1805cb2e4  lea     r8, [rbp+57h+pbData]; pbData
0x1805cb2e8  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x1805cb2f0  mov     edx, 4; dwParam
0x1805cb2f5  call    cs:__imp_CryptGetHashParam
0x1805cb2fb  test    eax, eax
0x1805cb2fd  jnz     loc_1805CB396
0x1805cb303  call    cs:__imp_GetLastError
0x1805cb309  mov     ebx, eax
0x1805cb30b  test    eax, eax
0x1805cb30d  jle     short loc_1805CB318
0x1805cb30f  movzx   ebx, ax
0x1805cb312  or      ebx, 80070000h
0x1805cb318  mov     eax, cs:dword_1808B5850
0x1805cb31e  cmp     eax, 2
0x1805cb321  jbe     loc_1805CB47E
0x1805cb327  lea     rax, aComputesha256h; "ComputeSha256Hash"
0x1805cb32e  mov     [rbp+57h+var_48], ebx
0x1805cb331  mov     [rbp+57h+var_30], rax
0x1805cb335  lea     rdx, byte_180888F7F
0x1805cb33c  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1805cb343  mov     [rbp+57h+var_4C], 0B40h
0x1805cb34a  mov     [rbp+57h+var_38], rax
0x1805cb34e  lea     rax, aCryptgethashpa_2; "CryptGetHashParam(HP_HASHSIZE) failed: "...
0x1805cb355  mov     [rbp+57h+var_40], rax
0x1805cb359  lea     rax, [rbp+57h+var_48]
0x1805cb35d  mov     [rsp+0A0h+var_58], rax
0x1805cb362  lea     rax, [rbp+57h+var_30]
0x1805cb366  mov     [rsp+0A0h+var_60], rax
0x1805cb36b  lea     rax, [rbp+57h+var_4C]
0x1805cb36f  mov     [rsp+0A0h+var_68], rax
0x1805cb374  lea     rax, [rbp+57h+var_38]
0x1805cb378  mov     [rsp+0A0h+var_70], rax
0x1805cb37d  lea     rax, [rbp+57h+var_50]
0x1805cb381  mov     [rsp+0A0h+var_78], rax
0x1805cb386  lea     rax, [rbp+57h+var_40]
0x1805cb38a  mov     [rbp+57h+var_50], 80004005h
0x1805cb391  jmp     loc_1805CB166
0x1805cb396  mov     ecx, [rbp+57h+pbData]; Size
0x1805cb399  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805cb39e  mov     rdi, rax
0x1805cb3a1  test    rax, rax
0x1805cb3a4  jnz     short loc_1805CB3B0
0x1805cb3a6  mov     ebx, 8007000Eh
0x1805cb3ab  jmp     loc_1805CB47E
0x1805cb3b0  mov     rcx, [rbp+57h+phHash]; hHash
0x1805cb3b4  lea     r9, [rbp+57h+pbData]; pdwDataLen
0x1805cb3b8  mov     r8, rdi; pbData
0x1805cb3bb  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x1805cb3c3  mov     edx, 2; dwParam
0x1805cb3c8  call    cs:__imp_CryptGetHashParam
0x1805cb3ce  test    eax, eax
0x1805cb3d0  jnz     loc_1805CB474
0x1805cb3d6  call    cs:__imp_GetLastError
0x1805cb3dc  mov     ebx, eax
0x1805cb3de  test    eax, eax
0x1805cb3e0  jle     short loc_1805CB3EB
0x1805cb3e2  movzx   ebx, ax
0x1805cb3e5  or      ebx, 80070000h
0x1805cb3eb  mov     eax, cs:dword_1808B5850
0x1805cb3f1  cmp     eax, 2
0x1805cb3f4  jbe     short loc_1805CB46A
0x1805cb3f6  lea     rax, aComputesha256h; "ComputeSha256Hash"
0x1805cb3fd  mov     [rbp+57h+var_48], ebx
0x1805cb400  mov     [rbp+57h+var_30], rax
0x1805cb404  lea     rdx, word_180888F36
0x1805cb40b  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1805cb412  mov     [rbp+57h+var_4C], 0B4Eh
0x1805cb419  mov     [rbp+57h+var_38], rax
0x1805cb41d  lea     rax, aCryptgethashpa_0; "CryptGetHashParam(HP_HASHVAL) failed: 0"...
0x1805cb424  mov     [rbp+57h+var_40], rax
0x1805cb428  lea     rax, [rbp+57h+var_48]
0x1805cb42c  mov     [rsp+0A0h+var_58], rax
0x1805cb431  lea     rax, [rbp+57h+var_30]
0x1805cb435  mov     [rsp+0A0h+var_60], rax
0x1805cb43a  lea     rax, [rbp+57h+var_4C]
0x1805cb43e  mov     [rsp+0A0h+var_68], rax
0x1805cb443  lea     rax, [rbp+57h+var_38]
0x1805cb447  mov     [rsp+0A0h+var_70], rax
0x1805cb44c  lea     rax, [rbp+57h+var_50]
0x1805cb450  mov     [rsp+0A0h+var_78], rax
0x1805cb455  lea     rax, [rbp+57h+var_40]
0x1805cb459  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x1805cb45e  mov     [rbp+57h+var_50], 80004005h
0x1805cb465  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805cb46a  mov     rcx, rdi; Block
0x1805cb46d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1805cb472  jmp     short loc_1805CB47E
0x1805cb474  mov     eax, [rbp+57h+pbData]
0x1805cb477  mov     [rsi], rdi
0x1805cb47a  mov     [rbx], eax
0x1805cb47c  xor     ebx, ebx
0x1805cb47e  mov     rcx, [rbp+57h+phHash]; hHash
0x1805cb482  test    rcx, rcx
0x1805cb485  jz      short loc_1805CB48D
0x1805cb487  call    cs:__imp_CryptDestroyHash
0x1805cb48d  mov     rcx, [rbp+57h+phProv]; hProv
0x1805cb491  test    rcx, rcx
0x1805cb494  jz      short loc_1805CB49E
0x1805cb496  xor     edx, edx; dwFlags
0x1805cb498  call    cs:__imp_CryptReleaseContext
0x1805cb49e  lea     r11, [rsp+0A0h+var_10]
0x1805cb4a6  mov     eax, ebx
0x1805cb4a8  mov     rbx, [r11+28h]
0x1805cb4ac  mov     rsi, [r11+30h]
0x1805cb4b0  mov     rsp, r11
0x1805cb4b3  pop     r14
0x1805cb4b5  pop     rdi
0x1805cb4b6  pop     rbp
0x1805cb4b7  retn
```
