# ScHelperCMSVerifyMessage(uchar *,ulong,int,char *,uchar * *,ulong *,_CERT_CONTEXT const * *,_CRYPT_ALGORITHM_IDENTIFIER * *)

- ea: `0x180032404`
- end: `0x180032665`
- name: `?ScHelperCMSVerifyMessage@@YAHPEAEKHPEADPEAPEAEPEAKPEAPEBU_CERT_CONTEXT@@PEAPEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z`
- size: `609`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, DWORD cbData@<edx>, int@<r8d>, char *@<r9>, unsigned __int8 **, unsigned int *, const struct _CERT_CONTEXT **, struct _CRYPT_ALGORITHM_IDENTIFIER **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180032334`

## callees

- `0x180032404`
- `0x180036820`
- `0x18006d0a8`
- `0x180070680`
- `0x18007108c`
- `0x1800f1ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800325fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032627`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800325fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032603`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003259c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003259c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032635`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032635`
- `CRYPT32!CryptMsgClose` at `0x180032616`
- `CRYPT32!CryptMsgClose` at `0x180032616`
- `CRYPT32!CryptMsgUpdate` at `0x1800324ad`
- `CRYPT32!CryptMsgUpdate` at `0x1800324ad`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180032489`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180032489`
- `CRYPT32!CryptMsgGetParam` at `0x1800324df`
- `CRYPT32!CryptMsgGetParam` at `0x180032538`
- `CRYPT32!CryptMsgGetParam` at `0x18003258a`
- `CRYPT32!CryptMsgGetParam` at `0x1800325c0`
- `CRYPT32!CryptMsgGetParam` at `0x1800324df`
- `CRYPT32!CryptMsgGetParam` at `0x180032538`
- `CRYPT32!CryptMsgGetParam` at `0x18003258a`
- `CRYPT32!CryptMsgGetParam` at `0x1800325c0`

## pseudocode

```c
__int64 __fastcall ScHelperCMSVerifyMessage(
        BYTE *pbData,
        DWORD cbData,
        __int64 a3,
        char *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        struct _CERT_CONTEXT **a7,
        struct _CRYPT_ALGORITHM_IDENTIFIER **a8)
{
  unsigned __int8 *v10; // rdi
  HCRYPTMSG v11; // rax
  void *v12; // rbx
  unsigned int v13; // r14d
  unsigned int v14; // ecx
  unsigned int v15; // r8d
  struct _CRYPT_ALGORITHM_IDENTIFIER *Param; // rax
  unsigned int *v17; // rcx
  DWORD LastError; // esi
  DWORD v19; // eax
  DWORD pcbData; // [rsp+30h] [rbp-A9h] BYREF
  DWORD v22; // [rsp+34h] [rbp-A5h] BYREF
  int pvData; // [rsp+38h] [rbp-A1h] BYREF
  struct _CERT_CONTEXT **v24; // [rsp+40h] [rbp-99h]
  unsigned int *v25; // [rsp+48h] [rbp-91h]
  char Str1[128]; // [rsp+50h] [rbp-89h] BYREF

  v25 = a6;
  v10 = 0;
  *a5 = 0;
  *a6 = 0;
  v24 = a7;
  pvData = 0;
  pcbData = 0;
  v22 = 0;
  if ( a8 )
    *a8 = 0;
  v11 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v12 = v11;
  if ( v11 )
  {
    v13 = 1;
    if ( CryptMsgUpdate(v11, pbData, cbData, 1) )
    {
      pcbData = 4;
      pvData = 0;
      if ( CryptMsgGetParam(v12, 1u, 0, &pvData, &pcbData) )
      {
        if ( pcbData != 4 || pvData != 2 )
          goto LABEL_17;
        memset_0(Str1, 0, sizeof(Str1));
        pcbData = 128;
        if ( !CryptMsgGetParam(v12, 4u, 0, Str1, &pcbData) )
          goto LABEL_18;
        if ( !strcmp_0(Str1, "1.3.6.1.5.2.3.2") )
        {
          if ( ScHelperGetSignerCertAndVerify(v14, v12, (const struct _CERT_CONTEXT **)v24) )
          {
            if ( CryptMsgGetParam(v12, 2u, 0, 0, &v22) )
            {
              v10 = (unsigned __int8 *)LocalAlloc(0x40u, v22);
              if ( v10 )
              {
                if ( CryptMsgGetParam(v12, 2u, 0, v10, &v22) )
                {
                  if ( !a8
                    || (Param = (struct _CRYPT_ALGORITHM_IDENTIFIER *)ScHelperAllocAndMsgGetParam(v12, 8u, v15),
                        (*a8 = Param) != 0) )
                  {
                    v17 = v25;
                    LastError = 0;
                    v19 = v22;
                    *a5 = v10;
                    v10 = 0;
                    *v17 = v19;
                    goto LABEL_19;
                  }
                }
              }
            }
          }
        }
        else
        {
LABEL_17:
          SetLastError(8u);
        }
      }
    }
  }
LABEL_18:
  v13 = 0;
  LastError = GetLastError();
  if ( v12 )
  {
LABEL_19:
    CryptMsgClose(v12);
    if ( v13 )
      goto LABEL_22;
  }
  if ( LastError )
    SetLastError(LastError);
LABEL_22:
  if ( v10 )
    LocalFree(v10);
  return v13;
}

```

## disassembly

```asm
0x180032404  mov     [rsp-8+arg_10], rbx
0x180032409  push    rbp
0x18003240a  push    rsi
0x18003240b  push    rdi
0x18003240c  push    r12
0x18003240e  push    r13
0x180032410  push    r14
0x180032412  push    r15
0x180032414  lea     rbp, [rsp-7]
0x180032419  sub     rsp, 0E0h
0x180032420  mov     rax, cs:__security_cookie
0x180032427  xor     rax, rsp
0x18003242a  mov     [rbp+37h+var_40], rax
0x18003242e  mov     rax, [rbp+37h+arg_28]
0x180032432  xor     r14d, r14d
0x180032435  mov     r13, [rbp+37h+arg_20]
0x180032439  mov     r15, rcx
0x18003243c  mov     rsi, [rbp+37h+arg_38]
0x180032440  mov     r12d, edx
0x180032443  mov     rcx, [rbp+37h+arg_30]
0x180032447  mov     r8d, r14d; dwMsgType
0x18003244a  mov     [rsp+110h+var_C8], rax
0x18003244f  mov     edi, r14d
0x180032452  mov     [r13+0], r14
0x180032456  mov     [rax], r14d
0x180032459  mov     [rsp+110h+var_D0], rcx
0x18003245e  mov     [rsp+110h+pvData], r14d
0x180032463  mov     [rsp+110h+pcbData], r14d
0x180032468  mov     [rsp+110h+var_DC], r14d
0x18003246d  test    rsi, rsi
0x180032470  jz      short loc_180032475
0x180032472  mov     [rsi], r14
0x180032475  mov     [rsp+110h+pStreamInfo], r14; pStreamInfo
0x18003247a  xor     r9d, r9d; hCryptProv
0x18003247d  xor     edx, edx; dwFlags
0x18003247f  mov     [rsp+110h+pRecipientInfo], r14; pRecipientInfo
0x180032484  mov     ecx, 10001h; dwMsgEncodingType
0x180032489  call    cs:__imp_CryptMsgOpenToDecode
0x18003248f  mov     rbx, rax
0x180032492  test    rax, rax
0x180032495  jz      loc_180032603
0x18003249b  mov     r14d, 1
0x1800324a1  mov     r8d, r12d; cbData
0x1800324a4  mov     r9d, r14d; fFinal
0x1800324a7  mov     rdx, r15; pbData
0x1800324aa  mov     rcx, rax; hCryptMsg
0x1800324ad  call    cs:__imp_CryptMsgUpdate
0x1800324b3  test    eax, eax
0x1800324b5  jz      loc_180032603
0x1800324bb  lea     rax, [rsp+110h+pcbData]
0x1800324c0  mov     [rsp+110h+pcbData], 4
0x1800324c8  lea     r9, [rsp+110h+pvData]; pvData
0x1800324cd  mov     [rsp+110h+pRecipientInfo], rax; pcbData
0x1800324d2  xor     r8d, r8d; dwIndex
0x1800324d5  mov     [rsp+110h+pvData], edi
0x1800324d9  mov     edx, r14d; dwParamType
0x1800324dc  mov     rcx, rbx; hCryptMsg
0x1800324df  call    cs:__imp_CryptMsgGetParam
0x1800324e5  test    eax, eax
0x1800324e7  jz      loc_180032603
0x1800324ed  cmp     [rsp+110h+pcbData], 4
0x1800324f2  jnz     loc_1800325F8
0x1800324f8  lea     r12d, [r14+1]
0x1800324fc  cmp     [rsp+110h+pvData], r12d
0x180032501  jnz     loc_1800325F8
0x180032507  lea     r15d, [r14+7Fh]
0x18003250b  xor     edx, edx; Val
0x18003250d  mov     r8d, r15d; Size
0x180032510  lea     rcx, [rsp+110h+Str1]; void *
0x180032515  call    memset_0
0x18003251a  lea     rax, [rsp+110h+pcbData]
0x18003251f  mov     [rsp+110h+pcbData], r15d
0x180032524  lea     r9, [rsp+110h+Str1]; pvData
0x180032529  mov     [rsp+110h+pRecipientInfo], rax; pcbData
0x18003252e  xor     r8d, r8d; dwIndex
0x180032531  lea     edx, [r14+3]; dwParamType
0x180032535  mov     rcx, rbx; hCryptMsg
0x180032538  call    cs:__imp_CryptMsgGetParam
0x18003253e  test    eax, eax
0x180032540  jz      loc_180032603
0x180032546  lea     rdx, a13615232; "1.3.6.1.5.2.3.2"
0x18003254d  lea     rcx, [rsp+110h+Str1]; Str1
0x180032552  call    strcmp_0
0x180032557  test    eax, eax
0x180032559  jnz     loc_1800325F8
0x18003255f  mov     r8, [rsp+110h+var_D0]; struct _CERT_CONTEXT **
0x180032564  mov     rdx, rbx; void *
0x180032567  call    ?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z; ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)
0x18003256c  test    eax, eax
0x18003256e  jz      loc_180032603
0x180032574  lea     rax, [rsp+110h+var_DC]
0x180032579  xor     r9d, r9d; pvData
0x18003257c  xor     r8d, r8d; dwIndex
0x18003257f  mov     [rsp+110h+pRecipientInfo], rax; pcbData
0x180032584  mov     edx, r12d; dwParamType
0x180032587  mov     rcx, rbx; hCryptMsg
0x18003258a  call    cs:__imp_CryptMsgGetParam
0x180032590  test    eax, eax
0x180032592  jz      short loc_180032603
0x180032594  mov     edx, [rsp+110h+var_DC]; uBytes
0x180032598  lea     ecx, [r14+3Fh]; uFlags
0x18003259c  call    cs:__imp_LocalAlloc
0x1800325a2  mov     rdi, rax
0x1800325a5  test    rax, rax
0x1800325a8  jz      short loc_180032603
0x1800325aa  lea     rax, [rsp+110h+var_DC]
0x1800325af  mov     r9, rdi; pvData
0x1800325b2  xor     r8d, r8d; dwIndex
0x1800325b5  mov     [rsp+110h+pRecipientInfo], rax; pcbData
0x1800325ba  mov     edx, r12d; dwParamType
0x1800325bd  mov     rcx, rbx; hCryptMsg
0x1800325c0  call    cs:__imp_CryptMsgGetParam
0x1800325c6  test    eax, eax
0x1800325c8  jz      short loc_180032603
0x1800325ca  test    rsi, rsi
0x1800325cd  jz      short loc_1800325E3
0x1800325cf  lea     edx, [r14+7]; dwParamType
0x1800325d3  mov     rcx, rbx; hCryptMsg
0x1800325d6  call    ?ScHelperAllocAndMsgGetParam@@YAPEAXPEAXKK@Z; ScHelperAllocAndMsgGetParam(void *,ulong,ulong)
0x1800325db  mov     [rsi], rax
0x1800325de  test    rax, rax
0x1800325e1  jz      short loc_180032603
0x1800325e3  mov     rcx, [rsp+110h+var_C8]
0x1800325e8  xor     esi, esi
0x1800325ea  mov     eax, [rsp+110h+var_DC]
0x1800325ee  mov     [r13+0], rdi
0x1800325f2  xor     edi, edi
0x1800325f4  mov     [rcx], eax
0x1800325f6  jmp     short loc_180032613
0x1800325f8  mov     ecx, 8; dwErrCode
0x1800325fd  call    cs:__imp_SetLastError
0x180032603  call    cs:__imp_GetLastError
0x180032609  xor     r14d, r14d
0x18003260c  mov     esi, eax
0x18003260e  test    rbx, rbx
0x180032611  jz      short loc_180032621
0x180032613  mov     rcx, rbx; hCryptMsg
0x180032616  call    cs:__imp_CryptMsgClose
0x18003261c  test    r14d, r14d
0x18003261f  jnz     short loc_18003262D
0x180032621  test    esi, esi
0x180032623  jz      short loc_18003262D
0x180032625  mov     ecx, esi; dwErrCode
0x180032627  call    cs:__imp_SetLastError
0x18003262d  test    rdi, rdi
0x180032630  jz      short loc_18003263B
0x180032632  mov     rcx, rdi; hMem
0x180032635  call    cs:__imp_LocalFree
0x18003263b  mov     eax, r14d
0x18003263e  mov     rcx, [rbp+37h+var_40]
0x180032642  xor     rcx, rsp; StackCookie
0x180032645  call    __security_check_cookie
0x18003264a  mov     rbx, [rsp+110h+arg_10]
0x180032652  add     rsp, 0E0h
0x180032659  pop     r15
0x18003265b  pop     r14
0x18003265d  pop     r13
0x18003265f  pop     r12
0x180032661  pop     rdi
0x180032662  pop     rsi
0x180032663  pop     rbp
0x180032664  retn
```
