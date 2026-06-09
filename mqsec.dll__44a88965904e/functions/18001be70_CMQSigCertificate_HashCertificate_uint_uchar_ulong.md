# CMQSigCertificate::HashCertificate(uint,uchar *,ulong *)

- ea: `0x18001be70`
- end: `0x18001c33c`
- name: `?HashCertificate@CMQSigCertificate@@UEAAJIPEAEPEAK@Z`
- size: `1228`
- prototype: `__int64 __fastcall(CMQSigCertificate *__hidden this, ALG_ID Algid, BYTE *pbData, DWORD *pdwDataLen)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x180017430`
- `0x18001b6dc`
- `0x18001be70`
- `0x18001c6bc`

## import_xrefs

- `msvcrt!free` at `0x18001bfc5`
- `msvcrt!free` at `0x18001c05c`
- `msvcrt!free` at `0x18001c0e0`
- `msvcrt!free` at `0x18001c15b`
- `msvcrt!free` at `0x18001c1e7`
- `msvcrt!free` at `0x18001c245`
- `msvcrt!free` at `0x18001c2bb`
- `msvcrt!free` at `0x18001c2d4`
- `msvcrt!free` at `0x18001bfc5`
- `msvcrt!free` at `0x18001c05c`
- `msvcrt!free` at `0x18001c0e0`
- `msvcrt!free` at `0x18001c15b`
- `msvcrt!free` at `0x18001c1e7`
- `msvcrt!free` at `0x18001c245`
- `msvcrt!free` at `0x18001c2bb`
- `msvcrt!free` at `0x18001c2d4`
- `CRYPT32!CryptEncodeObject` at `0x18001bf35`
- `CRYPT32!CryptEncodeObject` at `0x18001bf74`
- `CRYPT32!CryptEncodeObject` at `0x18001bf35`
- `CRYPT32!CryptEncodeObject` at `0x18001bf74`
- `ADVAPI32!CryptGetHashParam` at `0x18001c18b`
- `ADVAPI32!CryptGetHashParam` at `0x18001c25f`
- `ADVAPI32!CryptGetHashParam` at `0x18001c18b`
- `ADVAPI32!CryptGetHashParam` at `0x18001c25f`
- `ADVAPI32!CryptCreateHash` at `0x18001c086`
- `ADVAPI32!CryptCreateHash` at `0x18001c086`
- `ADVAPI32!CryptHashData` at `0x18001c0ff`
- `ADVAPI32!CryptHashData` at `0x18001c0ff`
- `KERNEL32!GetLastError` at `0x18001bf9a`
- `KERNEL32!GetLastError` at `0x18001c0ac`
- `KERNEL32!GetLastError` at `0x18001c125`
- `KERNEL32!GetLastError` at `0x18001c1b1`
- `KERNEL32!GetLastError` at `0x18001c285`
- `KERNEL32!GetLastError` at `0x18001c2fb`
- `KERNEL32!GetLastError` at `0x18001bf9a`
- `KERNEL32!GetLastError` at `0x18001c0ac`
- `KERNEL32!GetLastError` at `0x18001c125`
- `KERNEL32!GetLastError` at `0x18001c1b1`
- `KERNEL32!GetLastError` at `0x18001c285`
- `KERNEL32!GetLastError` at `0x18001c2fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMQSigCertificate::HashCertificate(
        CMQSigCertificate *this,
        ALG_ID Algid,
        BYTE *pbData,
        DWORD *pdwDataLen)
{
  const void *v8; // r8
  unsigned int v9; // eax
  BOOL v11; // eax
  void *v12; // rbx
  DWORD v13; // eax
  int v14; // edi
  unsigned int v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD LastError; // eax
  DWORD v20; // eax
  DWORD dwDataLen; // [rsp+60h] [rbp-9h] BYREF
  BYTE pbDataa[4]; // [rsp+64h] [rbp-5h] BYREF
  int v23; // [rsp+68h] [rbp-1h] BYREF
  HCRYPTHASH phHash[10]; // [rsp+70h] [rbp+7h] BYREF
  __int16 v25; // [rsp+D0h] [rbp+67h] BYREF

  v8 = (const void *)*((_QWORD *)this + 6);
  if ( v8 )
  {
    dwDataLen = 0;
    v11 = CryptEncodeObject(0x10001u, (LPCSTR)2, v8, 0, &dwDataLen);
    if ( dwDataLen && v11 )
    {
      v12 = MmAllocate(dwDataLen);
      phHash[1] = (HCRYPTHASH)v12;
      if ( CryptEncodeObject(0x10001u, (LPCSTR)2, *((const void **)this + 6), (BYTE *)v12, &dwDataLen) )
      {
        v14 = CMQSigCertificate::_InitCryptProviderRead(this);
        if ( v14 >= 0 )
        {
          phHash[0] = 0;
          if ( CryptCreateHash(*((_QWORD *)this + 3), Algid, 0, 0, phHash) )
          {
            if ( CryptHashData(phHash[0], (const BYTE *)v12, dwDataLen, 0) )
            {
              *(_DWORD *)pbDataa = 0;
              dwDataLen = 4;
              if ( CryptGetHashParam(phHash[0], 4u, pbDataa, &dwDataLen, 0) )
              {
                if ( *(_DWORD *)pbDataa <= *pdwDataLen )
                {
                  if ( CryptGetHashParam(phHash[0], 2u, pbData, pdwDataLen, 0) )
                  {
                    CHashHandle::~CHashHandle((CHashHandle *)phHash);
                    free(v12);
                    return 0;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                  {
                    LastError = GetLastError();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 32),
                      19,
                      WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids,
                      LastError);
                  }
                }
                else
                {
                  *pdwDataLen = *(_DWORD *)pbDataa;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              {
                v18 = GetLastError();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids, v18);
              }
              CHashHandle::~CHashHandle((CHashHandle *)phHash);
              free(v12);
              return 3222146067LL;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            {
              v17 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids, v17);
            }
            CHashHandle::~CHashHandle((CHashHandle *)phHash);
            free(v12);
            return 3222146068LL;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            {
              v16 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 15, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids, v16);
            }
            CHashHandle::~CHashHandle((CHashHandle *)phHash);
            free(v12);
            return 3222146069LL;
          }
        }
        else
        {
          v25 = 120;
          v23 = v14;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v15 = mqwcslen(L"certifct/cmqcert");
            CMSMQTrace::MSMQTraceEvent(
              g_pMSMQErrorLoggingTrace,
              1,
              1,
              2LL * (v15 + 1),
              L"certifct/cmqcert",
              2,
              &v25,
              4,
              &v23,
              0,
              0);
          }
          free(v12);
          return (unsigned int)v14;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          v13 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids, v13);
        }
        free(v12);
        return 3222146071LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v20 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids, v20);
      }
      return 3222146070LL;
    }
  }
  else
  {
    v25 = 90;
    v23 = -1072821241;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v9 = mqwcslen(L"certifct/cmqcert");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v9 + 1),
        L"certifct/cmqcert",
        2,
        &v25,
        4,
        &v23,
        0,
        0);
    }
    return 3222146055LL;
  }
}

```

## disassembly

```asm
0x18001be70  push    rbp
0x18001be72  push    rbx
0x18001be73  push    rsi
0x18001be74  push    rdi
0x18001be75  push    r12
0x18001be77  push    r13
0x18001be79  push    r14
0x18001be7b  push    r15
0x18001be7d  lea     rbp, [rsp-1Fh]
0x18001be82  sub     rsp, 88h
0x18001be89  mov     r14, r9
0x18001be8c  mov     r13, r8
0x18001be8f  mov     r12d, edx
0x18001be92  mov     rsi, rcx
0x18001be95  mov     r8, [rcx+30h]; pvStructInfo
0x18001be99  xor     edi, edi
0x18001be9b  test    r8, r8
0x18001be9e  jnz     short loc_18001BF1A
0x18001bea0  lea     eax, [rdi+5Ah]
0x18001bea3  mov     [rbp+57h+arg_0], ax
0x18001bea7  mov     ebx, 0C00E0C07h
0x18001beac  mov     [rbp+57h+var_58], ebx
0x18001beaf  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001beb6  jz      short loc_18001BF13
0x18001beb8  lea     rsi, aCertifctCmqcer; "certifct/cmqcert"
0x18001bebf  mov     rcx, rsi; wchar_t *
0x18001bec2  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001bec7  lea     r9d, [rax+1]
0x18001becb  add     r9, r9
0x18001bece  mov     [rsp+0C0h+var_70], rdi
0x18001bed3  mov     [rsp+0C0h+var_78], rdi
0x18001bed8  lea     rax, [rbp+57h+var_58]
0x18001bedc  mov     [rsp+0C0h+var_80], rax
0x18001bee1  mov     [rsp+0C0h+var_88], 4
0x18001beea  lea     rcx, [rbp+57h+arg_0]
0x18001beee  mov     [rsp+0C0h+var_90], rcx
0x18001bef3  lea     r15d, [rdi+2]
0x18001bef7  mov     [rsp+0C0h+var_98], r15
0x18001befc  mov     [rsp+0C0h+pcbEncoded], rsi
0x18001bf01  lea     edx, [rdi+1]
0x18001bf04  mov     r8d, edx
0x18001bf07  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001bf0e  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001bf13  mov     eax, ebx
0x18001bf15  jmp     loc_18001C328
0x18001bf1a  mov     [rbp+57h+dwDataLen], edi
0x18001bf1d  lea     rax, [rbp+57h+dwDataLen]
0x18001bf21  mov     [rsp+0C0h+pcbEncoded], rax; pcbEncoded
0x18001bf26  xor     r9d, r9d; pbEncoded
0x18001bf29  lea     r15d, [r9+2]
0x18001bf2d  mov     edx, r15d; lpszStructType
0x18001bf30  mov     ecx, 10001h; dwCertEncodingType
0x18001bf35  call    cs:__imp_CryptEncodeObject
0x18001bf3b  mov     edx, [rbp+57h+dwDataLen]
0x18001bf3e  test    edx, edx
0x18001bf40  jz      loc_18001C2DF
0x18001bf46  test    eax, eax
0x18001bf48  jz      loc_18001C2DF
0x18001bf4e  mov     ecx, edx; unsigned __int64
0x18001bf50  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001bf55  mov     rbx, rax
0x18001bf58  mov     [rbp+57h+var_48], rax
0x18001bf5c  lea     rax, [rbp+57h+dwDataLen]
0x18001bf60  mov     [rsp+0C0h+pcbEncoded], rax; pcbEncoded
0x18001bf65  mov     r9, rbx; pbEncoded
0x18001bf68  mov     r8, [rsi+30h]; pvStructInfo
0x18001bf6c  mov     edx, r15d; lpszStructType
0x18001bf6f  mov     ecx, 10001h; dwCertEncodingType
0x18001bf74  call    cs:__imp_CryptEncodeObject
0x18001bf7a  test    eax, eax
0x18001bf7c  jnz     short loc_18001BFD6
0x18001bf7e  lea     rax, WPP_GLOBAL_Control
0x18001bf85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf8c  cmp     rcx, rax
0x18001bf8f  jz      short loc_18001BFC2
0x18001bf91  test    byte ptr [rcx+10Ch], 1
0x18001bf98  jz      short loc_18001BFC2
0x18001bf9a  call    cs:__imp_GetLastError
0x18001bfa0  lea     edx, [r15+0Ch]
0x18001bfa4  mov     r9d, eax
0x18001bfa7  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001bfae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfb5  mov     rcx, [rcx+100h]
0x18001bfbc  call    WPP_SF_d
0x18001bfc1  nop
0x18001bfc2  mov     rcx, rbx; Block
0x18001bfc5  call    cs:__imp_free
0x18001bfcb  nop
0x18001bfcc  mov     eax, 0C00E0C17h
0x18001bfd1  jmp     loc_18001C328
0x18001bfd6  mov     rcx, rsi; this
0x18001bfd9  call    ?_InitCryptProviderRead@CMQSigCertificate@@AEAAJXZ; CMQSigCertificate::_InitCryptProviderRead(void)
0x18001bfde  mov     edi, eax
0x18001bfe0  test    eax, eax
0x18001bfe2  jns     loc_18001C06A
0x18001bfe8  mov     eax, 78h ; 'x'
0x18001bfed  mov     [rbp+57h+arg_0], ax
0x18001bff1  mov     [rbp+57h+var_58], edi
0x18001bff4  xor     r14d, r14d
0x18001bff7  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r14; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001bffe  jz      short loc_18001C059
0x18001c000  lea     rsi, aCertifctCmqcer; "certifct/cmqcert"
0x18001c007  mov     rcx, rsi; wchar_t *
0x18001c00a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001c00f  lea     r9d, [rax+1]
0x18001c013  add     r9, r9
0x18001c016  mov     [rsp+0C0h+var_70], r14
0x18001c01b  mov     [rsp+0C0h+var_78], r14
0x18001c020  lea     rax, [rbp+57h+var_58]
0x18001c024  mov     [rsp+0C0h+var_80], rax
0x18001c029  mov     [rsp+0C0h+var_88], 4
0x18001c032  lea     rax, [rbp+57h+arg_0]
0x18001c036  mov     [rsp+0C0h+var_90], rax
0x18001c03b  mov     [rsp+0C0h+var_98], r15
0x18001c040  mov     [rsp+0C0h+pcbEncoded], rsi
0x18001c045  lea     edx, [r14+1]
0x18001c049  mov     r8d, edx
0x18001c04c  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001c053  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001c058  nop
0x18001c059  mov     rcx, rbx; Block
0x18001c05c  call    cs:__imp_free
0x18001c062  nop
0x18001c063  mov     eax, edi
0x18001c065  jmp     loc_18001C328
0x18001c06a  xor     edi, edi
0x18001c06c  mov     [rbp+57h+phHash], rdi
0x18001c070  lea     rax, [rbp+57h+phHash]
0x18001c074  mov     [rsp+0C0h+pcbEncoded], rax; phHash
0x18001c079  xor     r9d, r9d; dwFlags
0x18001c07c  xor     r8d, r8d; hKey
0x18001c07f  mov     edx, r12d; Algid
0x18001c082  mov     rcx, [rsi+18h]; hProv
0x18001c086  call    cs:__imp_CryptCreateHash
0x18001c08c  test    eax, eax
0x18001c08e  jnz     short loc_18001C0F1
0x18001c090  lea     rax, WPP_GLOBAL_Control
0x18001c097  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c09e  cmp     rcx, rax
0x18001c0a1  jz      short loc_18001C0D3
0x18001c0a3  test    byte ptr [rcx+10Ch], 1
0x18001c0aa  jz      short loc_18001C0D3
0x18001c0ac  call    cs:__imp_GetLastError
0x18001c0b2  lea     edx, [rdi+0Fh]
0x18001c0b5  mov     r9d, eax
0x18001c0b8  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0c6  mov     rcx, [rcx+100h]
0x18001c0cd  call    WPP_SF_d
0x18001c0d2  nop
0x18001c0d3  lea     rcx, [rbp+57h+phHash]; this
0x18001c0d7  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c0dc  nop
0x18001c0dd  mov     rcx, rbx; Block
0x18001c0e0  call    cs:__imp_free
0x18001c0e6  nop
0x18001c0e7  mov     eax, 0C00E0C15h
0x18001c0ec  jmp     loc_18001C328
0x18001c0f1  xor     r9d, r9d; dwFlags
0x18001c0f4  mov     r8d, [rbp+57h+dwDataLen]; dwDataLen
0x18001c0f8  mov     rdx, rbx; pbData
0x18001c0fb  mov     rcx, [rbp+57h+phHash]; hHash
0x18001c0ff  call    cs:__imp_CryptHashData
0x18001c105  test    eax, eax
0x18001c107  jnz     short loc_18001C16C
0x18001c109  lea     rax, WPP_GLOBAL_Control
0x18001c110  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c117  cmp     rcx, rax
0x18001c11a  jz      short loc_18001C14E
0x18001c11c  test    byte ptr [rcx+10Ch], 1
0x18001c123  jz      short loc_18001C14E
0x18001c125  call    cs:__imp_GetLastError
0x18001c12b  mov     edx, 10h
0x18001c130  mov     r9d, eax
0x18001c133  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c13a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c141  mov     rcx, [rcx+100h]
0x18001c148  call    WPP_SF_d
0x18001c14d  nop
0x18001c14e  lea     rcx, [rbp+57h+phHash]; this
0x18001c152  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c157  nop
0x18001c158  mov     rcx, rbx; Block
0x18001c15b  call    cs:__imp_free
0x18001c161  nop
0x18001c162  mov     eax, 0C00E0C14h
0x18001c167  jmp     loc_18001C328
0x18001c16c  mov     dword ptr [rbp+57h+pbData], edi
0x18001c16f  mov     [rbp+57h+dwDataLen], 4
0x18001c176  mov     dword ptr [rsp+0C0h+pcbEncoded], edi; dwFlags
0x18001c17a  lea     r9, [rbp+57h+dwDataLen]; pdwDataLen
0x18001c17e  lea     r8, [rbp+57h+pbData]; pbData
0x18001c182  mov     edx, 4; dwParam
0x18001c187  mov     rcx, [rbp+57h+phHash]; hHash
0x18001c18b  call    cs:__imp_CryptGetHashParam
0x18001c191  test    eax, eax
0x18001c193  jnz     short loc_18001C1F8
0x18001c195  lea     rax, WPP_GLOBAL_Control
0x18001c19c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1a3  cmp     rcx, rax
0x18001c1a6  jz      short loc_18001C1DA
0x18001c1a8  test    byte ptr [rcx+10Ch], 1
0x18001c1af  jz      short loc_18001C1DA
0x18001c1b1  call    cs:__imp_GetLastError
0x18001c1b7  mov     edx, 11h
0x18001c1bc  mov     r9d, eax
0x18001c1bf  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1cd  mov     rcx, [rcx+100h]
0x18001c1d4  call    WPP_SF_d
0x18001c1d9  nop
0x18001c1da  lea     rcx, [rbp+57h+phHash]; this
0x18001c1de  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c1e3  nop
0x18001c1e4  mov     rcx, rbx; Block
0x18001c1e7  call    cs:__imp_free
0x18001c1ed  nop
0x18001c1ee  mov     eax, 0C00E0C13h
0x18001c1f3  jmp     loc_18001C328
0x18001c1f8  mov     eax, dword ptr [rbp+57h+pbData]
0x18001c1fb  cmp     eax, [r14]
0x18001c1fe  jbe     short loc_18001C24E
0x18001c200  mov     [r14], eax
0x18001c203  lea     rax, WPP_GLOBAL_Control
0x18001c20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c211  cmp     rcx, rax
0x18001c214  jz      short loc_18001C238
0x18001c216  test    byte ptr [rcx+10Ch], 1
0x18001c21d  jz      short loc_18001C238
0x18001c21f  mov     edx, 12h
0x18001c224  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c22b  mov     rcx, [rcx+100h]
0x18001c232  call    WPP_SF_
0x18001c237  nop
0x18001c238  lea     rcx, [rbp+57h+phHash]; this
0x18001c23c  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c241  nop
0x18001c242  mov     rcx, rbx; Block
0x18001c245  call    cs:__imp_free
0x18001c24b  nop
0x18001c24c  jmp     short loc_18001C1EE
0x18001c24e  mov     dword ptr [rsp+0C0h+pcbEncoded], edi; dwFlags
0x18001c252  mov     r9, r14; pdwDataLen
0x18001c255  mov     r8, r13; pbData
0x18001c258  mov     edx, r15d; dwParam
0x18001c25b  mov     rcx, [rbp+57h+phHash]; hHash
0x18001c25f  call    cs:__imp_CryptGetHashParam
0x18001c265  test    eax, eax
0x18001c267  jnz     short loc_18001C2C7
0x18001c269  lea     rax, WPP_GLOBAL_Control
0x18001c270  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c277  cmp     rcx, rax
0x18001c27a  jz      short loc_18001C2AE
0x18001c27c  test    byte ptr [rcx+10Ch], 1
0x18001c283  jz      short loc_18001C2AE
0x18001c285  call    cs:__imp_GetLastError
0x18001c28b  mov     edx, 13h
0x18001c290  mov     r9d, eax
0x18001c293  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2a1  mov     rcx, [rcx+100h]
0x18001c2a8  call    WPP_SF_d
0x18001c2ad  nop
0x18001c2ae  lea     rcx, [rbp+57h+phHash]; this
0x18001c2b2  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c2b7  nop
0x18001c2b8  mov     rcx, rbx; Block
0x18001c2bb  call    cs:__imp_free
0x18001c2c1  nop
0x18001c2c2  jmp     loc_18001C1EE
0x18001c2c7  lea     rcx, [rbp+57h+phHash]; this
0x18001c2cb  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18001c2d0  nop
0x18001c2d1  mov     rcx, rbx; Block
0x18001c2d4  call    cs:__imp_free
0x18001c2da  nop
0x18001c2db  xor     eax, eax
0x18001c2dd  jmp     short loc_18001C328
0x18001c2df  lea     rax, WPP_GLOBAL_Control
0x18001c2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2ed  cmp     rcx, rax
0x18001c2f0  jz      short loc_18001C323
0x18001c2f2  test    byte ptr [rcx+10Ch], 1
0x18001c2f9  jz      short loc_18001C323
0x18001c2fb  call    cs:__imp_GetLastError
0x18001c301  mov     edx, 0Dh
0x18001c306  mov     r9d, eax
0x18001c309  lea     r8, WPP_de86a6b65feb37dba35c0ab41bce2d15_Traceguids
0x18001c310  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c317  mov     rcx, [rcx+100h]
0x18001c31e  call    WPP_SF_d
0x18001c323  mov     eax, 0C00E0C16h
0x18001c328  add     rsp, 88h
0x18001c32f  pop     r15
0x18001c331  pop     r14
0x18001c333  pop     r13
0x18001c335  pop     r12
0x18001c337  pop     rdi
0x18001c338  pop     rsi
0x18001c339  pop     rbx
  ... truncated ...
```
