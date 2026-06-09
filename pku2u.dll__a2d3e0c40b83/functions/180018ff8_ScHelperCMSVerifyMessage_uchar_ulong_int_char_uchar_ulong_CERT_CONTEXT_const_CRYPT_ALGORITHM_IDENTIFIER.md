# ScHelperCMSVerifyMessage(uchar *,ulong,int,char *,uchar * *,ulong *,_CERT_CONTEXT const * *,_CRYPT_ALGORITHM_IDENTIFIER * *)

- ea: `0x180018ff8`
- end: `0x1800192ae`
- name: `?ScHelperCMSVerifyMessage@@YAHPEAEKHPEADPEAPEAEPEAKPEAPEBU_CERT_CONTEXT@@PEAPEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD cbData, __int64, char *, unsigned __int8 **, unsigned int *, struct _CERT_CONTEXT **, struct _CRYPT_ALGORITHM_IDENTIFIER **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018f50`

## callees

- `0x180018ff8`
- `0x1800210f0`
- `0x180021a54`
- `0x18003b160`
- `0x18003b2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001923f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001927e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001923f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001927e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001924f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001924f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800191d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800191d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001925f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001925f`
- `CRYPT32!CryptMsgUpdate` at `0x1800190a2`
- `CRYPT32!CryptMsgUpdate` at `0x1800190a2`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180019081`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180019081`
- `CRYPT32!CryptMsgClose` at `0x1800190d3`
- `CRYPT32!CryptMsgClose` at `0x18001926d`
- `CRYPT32!CryptMsgClose` at `0x1800190d3`
- `CRYPT32!CryptMsgClose` at `0x18001926d`
- `CRYPT32!CryptMsgGetParam` at `0x18001910a`
- `CRYPT32!CryptMsgGetParam` at `0x180019163`
- `CRYPT32!CryptMsgGetParam` at `0x1800191bf`
- `CRYPT32!CryptMsgGetParam` at `0x1800191fb`
- `CRYPT32!CryptMsgGetParam` at `0x18001910a`
- `CRYPT32!CryptMsgGetParam` at `0x180019163`
- `CRYPT32!CryptMsgGetParam` at `0x1800191bf`
- `CRYPT32!CryptMsgGetParam` at `0x1800191fb`

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
  unsigned int v11; // r15d
  DWORD v12; // r8d
  unsigned __int8 *v13; // rsi
  HCRYPTMSG v14; // rax
  void *v15; // rdi
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  struct _CRYPT_ALGORITHM_IDENTIFIER *Param; // rax
  DWORD LastError; // ebx
  unsigned int *v20; // rcx
  int pvData; // [rsp+30h] [rbp-B9h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-B5h] BYREF
  DWORD v24; // [rsp+38h] [rbp-B1h] BYREF
  struct _CERT_CONTEXT **v25; // [rsp+40h] [rbp-A9h]
  unsigned __int8 **v26; // [rsp+48h] [rbp-A1h]
  unsigned int *v27; // [rsp+50h] [rbp-99h]
  char v28[128]; // [rsp+60h] [rbp-89h] BYREF

  v25 = a7;
  *a5 = 0;
  v11 = 0;
  *a6 = 0;
  v12 = 0;
  v26 = a5;
  v13 = 0;
  v27 = a6;
  pvData = 0;
  pcbData = 0;
  v24 = 0;
  if ( a8 )
    *a8 = 0;
  while ( 1 )
  {
    v14 = CryptMsgOpenToDecode(0x10001u, 0, v12, 0, 0, 0);
    v15 = v14;
    if ( !v14 )
      goto LABEL_22;
    if ( CryptMsgUpdate(v14, pbData, cbData, 1) )
      break;
    if ( pvData == 2 || GetLastError() != -2146881269 )
      goto LABEL_22;
    pvData = 2;
    CryptMsgClose(v15);
    v12 = 2;
  }
  pvData = 0;
  pcbData = 4;
  if ( CryptMsgGetParam(v15, 1u, 0, &pvData, &pcbData) )
  {
    if ( pcbData != 4 || pvData != 2 )
      goto LABEL_21;
    if ( !a4 )
    {
LABEL_14:
      if ( ScHelperGetSignerCertAndVerify(v16, v15, (const struct _CERT_CONTEXT **)v25) )
      {
        if ( CryptMsgGetParam(v15, 2u, 0, 0, &v24) )
        {
          v13 = (unsigned __int8 *)LocalAlloc(0x40u, v24);
          if ( v13 )
          {
            if ( CryptMsgGetParam(v15, 2u, 0, v13, &v24) )
            {
              if ( !a8
                || (Param = (struct _CRYPT_ALGORITHM_IDENTIFIER *)ScHelperAllocAndMsgGetParam(v15, 8u, v17),
                    (*a8 = Param) != 0) )
              {
                LastError = 0;
                v20 = v27;
                *v26 = v13;
                v11 = 1;
                *v20 = v24;
                goto LABEL_25;
              }
            }
          }
        }
      }
      goto LABEL_22;
    }
    memset_0(v28, 0, sizeof(v28));
    pcbData = 128;
    if ( CryptMsgGetParam(v15, 4u, 0, v28, &pcbData) )
    {
      v16 = strcmp(v28, a4);
      if ( !v16 )
        goto LABEL_14;
LABEL_21:
      SetLastError(0xC000009A);
      LastError = GetLastError();
      goto LABEL_25;
    }
  }
LABEL_22:
  LastError = GetLastError();
  if ( v13 )
    LocalFree(v13);
  if ( !v15 )
    goto LABEL_26;
LABEL_25:
  CryptMsgClose(v15);
  if ( v11 )
    return v11;
LABEL_26:
  if ( LastError )
    SetLastError(LastError);
  return v11;
}

```

## disassembly

```asm
0x180018ff8  mov     [rsp-8+arg_10], rbx
0x180018ffd  push    rbp
0x180018ffe  push    rsi
0x180018fff  push    rdi
0x180019000  push    r12
0x180019002  push    r13
0x180019004  push    r14
0x180019006  push    r15
0x180019008  lea     rbp, [rsp-7]
0x18001900d  sub     rsp, 0F0h
0x180019014  mov     rax, cs:__security_cookie
0x18001901b  xor     rax, rsp
0x18001901e  mov     [rbp+37h+var_40], rax
0x180019022  mov     rax, [rbp+37h+arg_20]
0x180019026  mov     r13d, edx
0x180019029  mov     rdx, [rbp+37h+arg_30]
0x18001902d  mov     r12, rcx
0x180019030  mov     rcx, [rbp+37h+arg_28]
0x180019034  mov     rbx, r9
0x180019037  mov     r14, [rbp+37h+arg_38]
0x18001903b  mov     [rsp+120h+var_E0], rdx
0x180019040  xor     edx, edx
0x180019042  mov     [rax], rdx
0x180019045  mov     r15d, edx
0x180019048  mov     [rcx], edx
0x18001904a  mov     r8d, edx; dwMsgType
0x18001904d  mov     [rsp+120h+var_D8], rax
0x180019052  mov     esi, edx
0x180019054  mov     [rsp+120h+var_D0], rcx
0x180019059  mov     [rsp+120h+pvData], edx
0x18001905d  mov     [rsp+120h+pcbData], edx
0x180019061  mov     [rsp+120h+var_E8], edx
0x180019065  test    r14, r14
0x180019068  jz      short loc_18001906D
0x18001906a  mov     [r14], rdx
0x18001906d  mov     [rsp+120h+pStreamInfo], rdx; pStreamInfo
0x180019072  xor     r9d, r9d; hCryptProv
0x180019075  mov     [rsp+120h+pRecipientInfo], rdx; pRecipientInfo
0x18001907a  mov     ecx, 10001h; dwMsgEncodingType
0x18001907f  xor     edx, edx; dwFlags
0x180019081  call    cs:__imp_CryptMsgOpenToDecode
0x180019087  mov     rdi, rax
0x18001908a  test    rax, rax
0x18001908d  jz      loc_18001924F
0x180019093  mov     r9d, 1; fFinal
0x180019099  mov     r8d, r13d; cbData
0x18001909c  mov     rdx, r12; pbData
0x18001909f  mov     rcx, rax; hCryptMsg
0x1800190a2  call    cs:__imp_CryptMsgUpdate
0x1800190a8  test    eax, eax
0x1800190aa  jnz     short loc_1800190E2
0x1800190ac  cmp     [rsp+120h+pvData], 2
0x1800190b1  jz      loc_18001924F
0x1800190b7  call    cs:__imp_GetLastError
0x1800190bd  cmp     eax, 8009310Bh
0x1800190c2  jnz     loc_18001924F
0x1800190c8  mov     rcx, rdi; hCryptMsg
0x1800190cb  mov     [rsp+120h+pvData], 2
0x1800190d3  call    cs:__imp_CryptMsgClose
0x1800190d9  mov     r8d, [rsp+120h+pvData]
0x1800190de  xor     edx, edx
0x1800190e0  jmp     short loc_18001906D
0x1800190e2  mov     r13d, 4
0x1800190e8  mov     [rsp+120h+pvData], esi
0x1800190ec  lea     rax, [rsp+120h+pcbData]
0x1800190f1  mov     [rsp+120h+pcbData], r13d
0x1800190f6  lea     r9, [rsp+120h+pvData]; pvData
0x1800190fb  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x180019100  xor     r8d, r8d; dwIndex
0x180019103  mov     rcx, rdi; hCryptMsg
0x180019106  lea     edx, [r13-3]; dwParamType
0x18001910a  call    cs:__imp_CryptMsgGetParam
0x180019110  test    eax, eax
0x180019112  jz      loc_18001924F
0x180019118  cmp     [rsp+120h+pcbData], r13d
0x18001911d  jnz     loc_18001923A
0x180019123  cmp     [rsp+120h+pvData], 2
0x180019128  jnz     loc_18001923A
0x18001912e  test    rbx, rbx
0x180019131  jz      short loc_180019193
0x180019133  lea     r12d, [r13+7Ch]
0x180019137  xor     edx, edx; Val
0x180019139  mov     r8d, r12d; Size
0x18001913c  lea     rcx, [rsp+120h+var_C0]; void *
0x180019141  call    memset_0
0x180019146  lea     rax, [rsp+120h+pcbData]
0x18001914b  mov     [rsp+120h+pcbData], r12d
0x180019150  lea     r9, [rsp+120h+var_C0]; pvData
0x180019155  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x18001915a  xor     r8d, r8d; dwIndex
0x18001915d  mov     edx, r13d; dwParamType
0x180019160  mov     rcx, rdi; hCryptMsg
0x180019163  call    cs:__imp_CryptMsgGetParam
0x180019169  test    eax, eax
0x18001916b  jz      loc_18001924F
0x180019171  lea     rax, [rsp+120h+var_C0]
0x180019176  sub     rbx, rax
0x180019179  movzx   ecx, byte ptr [rax]
0x18001917c  movzx   edx, byte ptr [rax+rbx]
0x180019180  sub     ecx, edx; unsigned int
0x180019182  jnz     short loc_18001918B
0x180019184  inc     rax
0x180019187  test    edx, edx
0x180019189  jnz     short loc_180019179
0x18001918b  test    ecx, ecx
0x18001918d  jnz     loc_18001923A
0x180019193  mov     r8, [rsp+120h+var_E0]; struct _CERT_CONTEXT **
0x180019198  mov     rdx, rdi; void *
0x18001919b  call    ?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z; ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)
0x1800191a0  test    eax, eax
0x1800191a2  jz      loc_18001924F
0x1800191a8  xor     r9d, r9d; pvData
0x1800191ab  lea     rax, [rsp+120h+var_E8]
0x1800191b0  xor     r8d, r8d; dwIndex
0x1800191b3  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x1800191b8  mov     rcx, rdi; hCryptMsg
0x1800191bb  lea     edx, [r9+2]; dwParamType
0x1800191bf  call    cs:__imp_CryptMsgGetParam
0x1800191c5  test    eax, eax
0x1800191c7  jz      loc_18001924F
0x1800191cd  mov     edx, [rsp+120h+var_E8]; uBytes
0x1800191d1  mov     ecx, 40h ; '@'; uFlags
0x1800191d6  call    cs:__imp_LocalAlloc
0x1800191dc  mov     rsi, rax
0x1800191df  test    rax, rax
0x1800191e2  jz      short loc_18001924F
0x1800191e4  xor     r8d, r8d; dwIndex
0x1800191e7  lea     rax, [rsp+120h+var_E8]
0x1800191ec  mov     r9, rsi; pvData
0x1800191ef  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x1800191f4  mov     rcx, rdi; hCryptMsg
0x1800191f7  lea     edx, [r8+2]; dwParamType
0x1800191fb  call    cs:__imp_CryptMsgGetParam
0x180019201  test    eax, eax
0x180019203  jz      short loc_18001924F
0x180019205  test    r14, r14
0x180019208  jz      short loc_18001921F
0x18001920a  mov     edx, 8; dwParamType
0x18001920f  mov     rcx, rdi; hCryptMsg
0x180019212  call    ?ScHelperAllocAndMsgGetParam@@YAPEAXPEAXKK@Z; ScHelperAllocAndMsgGetParam(void *,ulong,ulong)
0x180019217  mov     [r14], rax
0x18001921a  test    rax, rax
0x18001921d  jz      short loc_18001924F
0x18001921f  mov     rax, [rsp+120h+var_D8]
0x180019224  xor     ebx, ebx
0x180019226  mov     rcx, [rsp+120h+var_D0]
0x18001922b  mov     [rax], rsi
0x18001922e  lea     r15d, [rbx+1]
0x180019232  mov     eax, [rsp+120h+var_E8]
0x180019236  mov     [rcx], eax
0x180019238  jmp     short loc_18001926A
0x18001923a  mov     ecx, 0C000009Ah; dwErrCode
0x18001923f  call    cs:__imp_SetLastError
0x180019245  call    cs:__imp_GetLastError
0x18001924b  mov     ebx, eax
0x18001924d  jmp     short loc_18001926A
0x18001924f  call    cs:__imp_GetLastError
0x180019255  mov     ebx, eax
0x180019257  test    rsi, rsi
0x18001925a  jz      short loc_180019265
0x18001925c  mov     rcx, rsi; hMem
0x18001925f  call    cs:__imp_LocalFree
0x180019265  test    rdi, rdi
0x180019268  jz      short loc_180019278
0x18001926a  mov     rcx, rdi; hCryptMsg
0x18001926d  call    cs:__imp_CryptMsgClose
0x180019273  test    r15d, r15d
0x180019276  jnz     short loc_180019284
0x180019278  test    ebx, ebx
0x18001927a  jz      short loc_180019284
0x18001927c  mov     ecx, ebx; dwErrCode
0x18001927e  call    cs:__imp_SetLastError
0x180019284  mov     eax, r15d
0x180019287  mov     rcx, [rbp+37h+var_40]
0x18001928b  xor     rcx, rsp; StackCookie
0x18001928e  call    __security_check_cookie
0x180019293  mov     rbx, [rsp+120h+arg_10]
0x18001929b  add     rsp, 0F0h
0x1800192a2  pop     r15
0x1800192a4  pop     r14
0x1800192a6  pop     r13
0x1800192a8  pop     r12
0x1800192aa  pop     rdi
0x1800192ab  pop     rsi
0x1800192ac  pop     rbp
0x1800192ad  retn
```
