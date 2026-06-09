# GetRfc3161TimestampTime(_CRYPT_ATTRIBUTE const &,_FILETIME *)

- ea: `0x180019b58`
- end: `0x180019d17`
- name: `?GetRfc3161TimestampTime@@YAHAEBU_CRYPT_ATTRIBUTE@@PEAU_FILETIME@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(const struct _CRYPT_ATTRIBUTE *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001763c`

## callees

- `0x180016b88`
- `0x180019b58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019bfb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019c7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019bfb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cf0`
- `CRYPT32!CryptDecodeObjectEx` at `0x180019c6a`
- `CRYPT32!CryptDecodeObjectEx` at `0x180019cb7`
- `CRYPT32!CryptDecodeObjectEx` at `0x180019c6a`
- `CRYPT32!CryptDecodeObjectEx` at `0x180019cb7`
- `CRYPT32!CryptMsgGetParam` at `0x180019be7`
- `CRYPT32!CryptMsgGetParam` at `0x180019c26`
- `CRYPT32!CryptMsgGetParam` at `0x180019be7`
- `CRYPT32!CryptMsgGetParam` at `0x180019c26`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180019b91`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180019b91`
- `CRYPT32!CryptMsgUpdate` at `0x180019bbd`
- `CRYPT32!CryptMsgUpdate` at `0x180019bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetRfc3161TimestampTime(const struct _CRYPT_ATTRIBUTE *a1, struct _FILETIME *a2)
{
  HCRYPTMSG v4; // rax
  void *v5; // rdi
  unsigned int v6; // esi
  HLOCAL v7; // rax
  void *v8; // rbx
  struct _FILETIME *pvStructInfo; // rax
  struct _FILETIME *v10; // rdi
  _QWORD v12[4]; // [rsp+40h] [rbp-20h] BYREF
  DWORD cbEncoded; // [rsp+90h] [rbp+30h] BYREF
  DWORD pcbStructInfo; // [rsp+98h] [rbp+38h] BYREF

  v4 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v5 = v4;
  if ( !v4 )
    return 0;
  v12[0] = v4;
  v6 = 1;
  if ( !CryptMsgUpdate(v4, a1->rgValue->pbData, a1->rgValue->cbData, 1)
    || (cbEncoded = 0, !CryptMsgGetParam(v5, 2u, 0, 0, &cbEncoded))
    || (v7 = LocalAlloc(0x40u, cbEncoded), (v8 = v7) == 0) )
  {
LABEL_13:
    CryptMsgFreer::~CryptMsgFreer((CryptMsgFreer *)v12);
    return 0;
  }
  v12[1] = v7;
  if ( !CryptMsgGetParam(v5, 2u, 0, v7, &cbEncoded)
    || (pcbStructInfo = 0, !CryptDecodeObjectEx(1u, (LPCSTR)0x50, (const BYTE *)v8, cbEncoded, 0, 0, 0, &pcbStructInfo))
    || (pvStructInfo = (struct _FILETIME *)LocalAlloc(0x40u, pcbStructInfo), (v10 = pvStructInfo) == 0) )
  {
    LocalFree(v8);
    goto LABEL_13;
  }
  v12[2] = pvStructInfo;
  if ( CryptDecodeObjectEx(1u, (LPCSTR)0x50, (const BYTE *)v8, cbEncoded, 0, 0, pvStructInfo, &pcbStructInfo) )
    *a2 = v10[9];
  else
    v6 = 0;
  LocalFree(v10);
  LocalFree(v8);
  CryptMsgFreer::~CryptMsgFreer((CryptMsgFreer *)v12);
  return v6;
}

```

## disassembly

```asm
0x180019b58  mov     rax, rsp
0x180019b5b  mov     [rax+8], rbx
0x180019b5f  mov     [rax+10h], rsi
0x180019b63  push    rbp
0x180019b64  push    rdi
0x180019b65  push    r14
0x180019b67  mov     rbp, rsp
0x180019b6a  sub     rsp, 60h
0x180019b6e  mov     r14, rdx
0x180019b71  mov     rbx, rcx
0x180019b74  mov     qword ptr [rax-50h], 0
0x180019b7c  mov     qword ptr [rax-58h], 0
0x180019b84  xor     r9d, r9d; hCryptProv
0x180019b87  xor     r8d, r8d; dwMsgType
0x180019b8a  xor     edx, edx; dwFlags
0x180019b8c  mov     ecx, 10001h; dwMsgEncodingType
0x180019b91  call    cs:__imp_CryptMsgOpenToDecode
0x180019b97  mov     rdi, rax
0x180019b9a  test    rax, rax
0x180019b9d  jz      loc_180019D00
0x180019ba3  mov     [rbp+var_20], rax
0x180019ba7  mov     rdx, [rbx+10h]
0x180019bab  mov     esi, 1
0x180019bb0  mov     r9d, esi; fFinal
0x180019bb3  mov     r8d, [rdx]; cbData
0x180019bb6  mov     rdx, [rdx+8]; pbData
0x180019bba  mov     rcx, rax; hCryptMsg
0x180019bbd  call    cs:__imp_CryptMsgUpdate
0x180019bc3  test    eax, eax
0x180019bc5  jz      loc_180019CF7
0x180019bcb  mov     [rbp+cbEncoded], 0
0x180019bd2  lea     rax, [rbp+cbEncoded]
0x180019bd6  mov     [rsp+60h+pcbData], rax; pcbData
0x180019bdb  xor     r9d, r9d; pvData
0x180019bde  xor     r8d, r8d; dwIndex
0x180019be1  lea     edx, [rsi+1]; dwParamType
0x180019be4  mov     rcx, rdi; hCryptMsg
0x180019be7  call    cs:__imp_CryptMsgGetParam
0x180019bed  test    eax, eax
0x180019bef  jz      loc_180019CF7
0x180019bf5  mov     edx, [rbp+cbEncoded]; uBytes
0x180019bf8  lea     ecx, [rsi+3Fh]; uFlags
0x180019bfb  call    cs:__imp_LocalAlloc
0x180019c01  mov     rbx, rax
0x180019c04  test    rax, rax
0x180019c07  jz      loc_180019CF7
0x180019c0d  mov     [rbp+var_18], rax
0x180019c11  lea     rax, [rbp+cbEncoded]
0x180019c15  mov     [rsp+60h+pcbData], rax; pcbData
0x180019c1a  mov     r9, rbx; pvData
0x180019c1d  xor     r8d, r8d; dwIndex
0x180019c20  lea     edx, [rsi+1]; dwParamType
0x180019c23  mov     rcx, rdi; hCryptMsg
0x180019c26  call    cs:__imp_CryptMsgGetParam
0x180019c2c  test    eax, eax
0x180019c2e  jz      loc_180019CED
0x180019c34  mov     [rbp+arg_18], 0
0x180019c3b  lea     rax, [rbp+arg_18]
0x180019c3f  mov     [rsp+60h+pcbStructInfo], rax; pcbStructInfo
0x180019c44  mov     [rsp+60h+pvStructInfo], 0; pvStructInfo
0x180019c4d  mov     [rsp+60h+pDecodePara], 0; pDecodePara
0x180019c56  mov     dword ptr [rsp+60h+pcbData], 0; dwFlags
0x180019c5e  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x180019c62  mov     r8, rbx; pbEncoded
0x180019c65  lea     edx, [rsi+4Fh]; lpszStructType
0x180019c68  mov     ecx, esi; dwCertEncodingType
0x180019c6a  call    cs:__imp_CryptDecodeObjectEx
0x180019c70  test    eax, eax
0x180019c72  jz      short loc_180019CED
0x180019c74  mov     edx, [rbp+arg_18]; uBytes
0x180019c77  lea     ecx, [rsi+3Fh]; uFlags
0x180019c7a  call    cs:__imp_LocalAlloc
0x180019c80  mov     rdi, rax
0x180019c83  test    rax, rax
0x180019c86  jz      short loc_180019CED
0x180019c88  mov     [rbp+var_10], rax
0x180019c8c  lea     rax, [rbp+arg_18]
0x180019c90  mov     [rsp+60h+pcbStructInfo], rax; pcbStructInfo
0x180019c95  mov     [rsp+60h+pvStructInfo], rdi; pvStructInfo
0x180019c9a  mov     [rsp+60h+pDecodePara], 0; pDecodePara
0x180019ca3  mov     dword ptr [rsp+60h+pcbData], 0; dwFlags
0x180019cab  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x180019caf  mov     r8, rbx; pbEncoded
0x180019cb2  lea     edx, [rsi+4Fh]; lpszStructType
0x180019cb5  mov     ecx, esi; dwCertEncodingType
0x180019cb7  call    cs:__imp_CryptDecodeObjectEx
0x180019cbd  test    eax, eax
0x180019cbf  jnz     short loc_180019CC5
0x180019cc1  xor     esi, esi
0x180019cc3  jmp     short loc_180019CCC
0x180019cc5  mov     rcx, [rdi+48h]
0x180019cc9  mov     [r14], rcx
0x180019ccc  mov     rcx, rdi; hMem
0x180019ccf  call    cs:__imp_LocalFree
0x180019cd5  nop
0x180019cd6  mov     rcx, rbx; hMem
0x180019cd9  call    cs:__imp_LocalFree
0x180019cdf  nop
0x180019ce0  lea     rcx, [rbp+var_20]; this
0x180019ce4  call    ??1CryptMsgFreer@@QEAA@XZ; CryptMsgFreer::~CryptMsgFreer(void)
0x180019ce9  mov     eax, esi
0x180019ceb  jmp     short loc_180019D02
0x180019ced  mov     rcx, rbx; hMem
0x180019cf0  call    cs:__imp_LocalFree
0x180019cf6  nop
0x180019cf7  lea     rcx, [rbp+var_20]; this
0x180019cfb  call    ??1CryptMsgFreer@@QEAA@XZ; CryptMsgFreer::~CryptMsgFreer(void)
0x180019d00  xor     eax, eax
0x180019d02  lea     r11, [rsp+60h+var_s0]
0x180019d07  mov     rbx, [r11+20h]
0x180019d0b  mov     rsi, [r11+28h]
0x180019d0f  mov     rsp, r11
0x180019d12  pop     r14
0x180019d14  pop     rdi
0x180019d15  pop     rbp
0x180019d16  retn
```
