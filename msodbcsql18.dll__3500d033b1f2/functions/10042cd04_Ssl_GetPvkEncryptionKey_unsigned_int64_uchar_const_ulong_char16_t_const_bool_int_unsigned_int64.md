# Ssl::GetPvkEncryptionKey(unsigned __int64,uchar const *,ulong,char16_t const *,bool,int,unsigned __int64 &)

- ea: `0x10042cd04`
- end: `0x10042cf07`
- name: `?GetPvkEncryptionKey@Ssl@@CAK_KPEBEKPEB_S_NHAEA_K@Z`
- size: `515`
- prototype: `unsigned int __fastcall(HCRYPTPROV hProv, BYTE *pbData, DWORD dwDataLen, LPCWCH lpWideCharStr, bool, ALG_ID Algid, HCRYPTKEY *phKey)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10042b324`

## callees

- `0x100425a50`
- `0x10042cd04`
- `0x100545d84`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042ce5c`
- `KERNEL32!GetLastError` at `0x10042ce5c`
- `ADVAPI32!CryptDestroyHash` at `0x10042ce6d`
- `ADVAPI32!CryptDestroyHash` at `0x10042ce6d`
- `ADVAPI32!CryptHashData` at `0x10042cdff`
- `ADVAPI32!CryptHashData` at `0x10042ce33`
- `ADVAPI32!CryptHashData` at `0x10042cdff`
- `ADVAPI32!CryptHashData` at `0x10042ce33`
- `ADVAPI32!CryptCreateHash` at `0x10042cde8`
- `ADVAPI32!CryptCreateHash` at `0x10042cde8`
- `ADVAPI32!CryptDeriveKey` at `0x10042ce52`
- `ADVAPI32!CryptDeriveKey` at `0x10042ce52`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10042ceab`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10042ceab`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Ssl::GetPvkEncryptionKey(
        HCRYPTPROV hProv,
        BYTE *pbData,
        DWORD dwDataLen,
        LPCWCH lpWideCharStr,
        bool a5,
        ALG_ID Algid,
        HCRYPTKEY *phKey)
{
  __int64 v11; // rbx
  DWORD LastError; // esi
  BYTE **v13; // rax
  const BYTE *v14; // rdx
  BYTE *v15; // rdx
  HCRYPTHASH hHash; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-39h] BYREF
  BYTE *pbDataa[2]; // [rsp+58h] [rbp-29h] BYREF
  __int64 v20; // [rsp+68h] [rbp-19h]
  unsigned __int64 v21; // [rsp+70h] [rbp-11h]

  v18[1] = -2;
  v11 = -1;
  v18[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7BB8[0] && bidID != -1 )
    off_1005D39F0(bidID);
  LastError = 0;
  hHash = 0;
  *phKey = 0;
  v20 = 0;
  v21 = 15;
  LOBYTE(pbDataa[0]) = 0;
  CryptoBase::FromUtf16(lpWideCharStr, pbDataa);
  if ( !CryptCreateHash(hProv, 0x8004u, 0, 0, &hHash) || !CryptHashData(hHash, pbData, dwDataLen, 0) )
    goto LABEL_14;
  v13 = pbDataa;
  if ( v21 >= 0x10 )
    v13 = (BYTE **)pbDataa[0];
  v14 = (const BYTE *)pbDataa;
  if ( v21 >= 0x10 )
    v14 = pbDataa[0];
  do
    ++v11;
  while ( *((_BYTE *)v13 + v11) );
  if ( !CryptHashData(hHash, v14, v11, 0) || !CryptDeriveKey(hProv, Algid, hHash, (a5 ? 40 : 128) << 16, phKey) )
LABEL_14:
    LastError = GetLastError();
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( v21 >= 0x10 )
  {
    v15 = pbDataa[0];
    if ( v21 + 1 >= 0x1000 )
    {
      if ( ((__int64)pbDataa[0] & 0x1F) != 0
        || (v15 = (BYTE *)*((_QWORD *)pbDataa[0] - 1), v15 >= pbDataa[0])
        || (unsigned __int64)(pbDataa[0] - v15 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    if ( v15 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v20 = 0;
  v21 = 15;
  LOBYTE(pbDataa[0]) = 0;
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v18);
  return LastError;
}

```

## disassembly

```asm
0x10042cd04  push    rbp
0x10042cd06  push    rbx
0x10042cd07  push    rsi
0x10042cd08  push    rdi
0x10042cd09  push    r12
0x10042cd0b  push    r13
0x10042cd0d  push    r14
0x10042cd0f  push    r15
0x10042cd11  lea     rbp, [rsp-7]
0x10042cd16  sub     rsp, 88h
0x10042cd1d  mov     [rbp+3Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x10042cd25  mov     rax, cs:__security_cookie
0x10042cd2c  xor     rax, rsp
0x10042cd2f  mov     [rbp+3Fh+var_48], rax
0x10042cd33  mov     rdi, r9
0x10042cd36  mov     r15d, r8d
0x10042cd39  mov     r14, rdx
0x10042cd3c  mov     r12, rcx
0x10042cd3f  mov     r13, [rbp+3Fh+phKey]
0x10042cd43  or      rbx, 0FFFFFFFFFFFFFFFFh
0x10042cd47  mov     [rbp+3Fh+var_78], rbx
0x10042cd4b  mov     eax, cs:_bidGblFlags
0x10042cd51  mov     ecx, 20004h
0x10042cd56  and     eax, ecx
0x10042cd58  xor     edx, edx
0x10042cd5a  cmp     eax, ecx
0x10042cd5c  jnz     short loc_10042CDA1
0x10042cd5e  mov     rax, cs:off_1005E7BB8; "<Ssl::GetPvkEncryptionKey|API|SNI> \n"
0x10042cd65  test    rax, rax
0x10042cd68  jz      short loc_10042CDA1
0x10042cd6a  cmp     cs:_bidID, rbx
0x10042cd71  jz      short loc_10042CDA1
0x10042cd73  mov     rax, cs:off_1005D39F0
0x10042cd7a  mov     [rsp+0C0h+var_98], rdx
0x10042cd7f  mov     rcx, cs:off_1005E7BB8; "<Ssl::GetPvkEncryptionKey|API|SNI> \n"
0x10042cd86  mov     [rsp+0C0h+phHash], rcx
0x10042cd8b  lea     r9, [rbp+3Fh+var_78]
0x10042cd8f  xor     r8d, r8d
0x10042cd92  mov     rcx, cs:_bidID
0x10042cd99  call    cs:__guard_dispatch_icall_fptr
0x10042cd9f  xor     edx, edx
0x10042cda1  mov     esi, edx
0x10042cda3  mov     [rbp+3Fh+hHash], rdx
0x10042cda7  mov     [r13+0], rdx
0x10042cdab  mov     [rbp+3Fh+var_58], rdx
0x10042cdaf  mov     [rbp+3Fh+var_50], 0Fh
0x10042cdb7  mov     byte ptr [rbp+3Fh+pbData], dl
0x10042cdba  lea     rdx, [rbp+3Fh+pbData]; void *
0x10042cdbe  mov     rcx, rdi; lpWideCharStr
0x10042cdc1  call    ?FromUtf16@CryptoBase@@SA_NPEB_SAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CryptoBase::FromUtf16(char16_t const *,std::string &)
0x10042cdc6  neg     [rbp+3Fh+arg_20]
0x10042cdc9  sbb     edi, edi
0x10042cdcb  and     edi, 0FFFFFFA8h
0x10042cdce  sub     edi, 0FFFFFF80h
0x10042cdd1  lea     rax, [rbp+3Fh+hHash]
0x10042cdd5  mov     [rsp+0C0h+phHash], rax; phHash
0x10042cdda  xor     r9d, r9d; dwFlags
0x10042cddd  xor     r8d, r8d; hKey
0x10042cde0  mov     edx, 8004h; Algid
0x10042cde5  mov     rcx, r12; hProv
0x10042cde8  call    cs:__imp_CryptCreateHash
0x10042cdee  test    eax, eax
0x10042cdf0  jz      short loc_10042CE5C
0x10042cdf2  xor     r9d, r9d; dwFlags
0x10042cdf5  mov     r8d, r15d; dwDataLen
0x10042cdf8  mov     rdx, r14; pbData
0x10042cdfb  mov     rcx, [rbp+3Fh+hHash]; hHash
0x10042cdff  call    cs:__imp_CryptHashData
0x10042ce05  test    eax, eax
0x10042ce07  jz      short loc_10042CE5C
0x10042ce09  lea     rax, [rbp+3Fh+pbData]
0x10042ce0d  cmp     [rbp+3Fh+var_50], 10h
0x10042ce12  cmovnb  rax, [rbp+3Fh+pbData]
0x10042ce17  lea     rdx, [rbp+3Fh+pbData]
0x10042ce1b  cmovnb  rdx, [rbp+3Fh+pbData]; pbData
0x10042ce20  inc     rbx
0x10042ce23  cmp     byte ptr [rax+rbx], 0
0x10042ce27  jnz     short loc_10042CE20
0x10042ce29  mov     r8, rbx; dwDataLen
0x10042ce2c  xor     r9d, r9d; dwFlags
0x10042ce2f  mov     rcx, [rbp+3Fh+hHash]; hHash
0x10042ce33  call    cs:__imp_CryptHashData
0x10042ce39  test    eax, eax
0x10042ce3b  jz      short loc_10042CE5C
0x10042ce3d  shl     edi, 10h
0x10042ce40  mov     [rsp+0C0h+phHash], r13; phKey
0x10042ce45  mov     r9d, edi; dwFlags
0x10042ce48  mov     r8, [rbp+3Fh+hHash]; hBaseData
0x10042ce4c  mov     edx, [rbp+3Fh+Algid]; Algid
0x10042ce4f  mov     rcx, r12; hProv
0x10042ce52  call    cs:__imp_CryptDeriveKey
0x10042ce58  test    eax, eax
0x10042ce5a  jnz     short loc_10042CE64
0x10042ce5c  call    cs:__imp_GetLastError
0x10042ce62  mov     esi, eax
0x10042ce64  mov     rcx, [rbp+3Fh+hHash]; hHash
0x10042ce68  test    rcx, rcx
0x10042ce6b  jz      short loc_10042CE74
0x10042ce6d  call    cs:__imp_CryptDestroyHash
0x10042ce73  nop
0x10042ce74  mov     rax, [rbp+3Fh+var_50]
0x10042ce78  cmp     rax, 10h
0x10042ce7c  jb      short loc_10042CECB
0x10042ce7e  inc     rax
0x10042ce81  mov     rdx, [rbp+3Fh+pbData]
0x10042ce85  mov     rcx, rdx
0x10042ce88  cmp     rax, 1000h
0x10042ce8e  jb      short loc_10042CEB2
0x10042ce90  test    cl, 1Fh
0x10042ce93  jnz     short loc_10042CEAB
0x10042ce95  mov     rdx, [rdx-8]
0x10042ce99  cmp     rdx, rcx
0x10042ce9c  jnb     short loc_10042CEAB
0x10042ce9e  sub     rcx, rdx
0x10042cea1  sub     rcx, 8
0x10042cea5  cmp     rcx, 1Fh
0x10042cea9  jbe     short loc_10042CEB2
0x10042ceab  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x10042ceb2  test    rdx, rdx
0x10042ceb5  jz      short loc_10042CECB
0x10042ceb7  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10042cebe  mov     rax, [rcx]
0x10042cec1  mov     rax, [rax+68h]
0x10042cec5  call    cs:__guard_dispatch_icall_fptr
0x10042cecb  and     [rbp+3Fh+var_58], 0
0x10042ced0  mov     [rbp+3Fh+var_50], 0Fh
0x10042ced8  mov     byte ptr [rbp+3Fh+pbData], 0
0x10042cedc  lea     rcx, [rbp+3Fh+var_78]; this
0x10042cee0  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042cee5  mov     eax, esi
0x10042cee7  mov     rcx, [rbp+3Fh+var_48]
0x10042ceeb  xor     rcx, rsp; StackCookie
0x10042ceee  call    __security_check_cookie
0x10042cef3  add     rsp, 88h
0x10042cefa  pop     r15
0x10042cefc  pop     r14
0x10042cefe  pop     r13
0x10042cf00  pop     r12
0x10042cf02  pop     rdi
0x10042cf03  pop     rsi
0x10042cf04  pop     rbx
0x10042cf05  pop     rbp
0x10042cf06  retn
```
