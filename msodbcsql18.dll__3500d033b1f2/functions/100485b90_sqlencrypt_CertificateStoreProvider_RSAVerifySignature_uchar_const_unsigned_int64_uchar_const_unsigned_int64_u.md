# sqlencrypt::CertificateStoreProvider::RSAVerifySignature(uchar const *,unsigned __int64,uchar const *,unsigned __int64,unsigned __int64,CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...))

- ea: `0x100485b90`
- end: `0x100485df6`
- name: `?RSAVerifySignature@CertificateStoreProvider@sqlencrypt@@CA_NPEBE_K011PEAUCEKeystoreContext@@P6AX2PEBGZZ@Z`
- size: `614`
- prototype: `bool __usercall@<al>(BYTE *pbData@<rcx>, DWORD dwDataLen@<edx>, const unsigned __int8 *@<r8>, unsigned __int64@<r9>, HCRYPTKEY hPubKey, struct CEKeystoreContext *, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...))`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100484830`
- `0x100484ea0`

## callees

- `0x10040128c`
- `0x10042a7b4`
- `0x100485b90`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100485c82`
- `KERNEL32!GetLastError` at `0x100485c82`
- `ADVAPI32!CryptDestroyHash` at `0x100485d5b`
- `ADVAPI32!CryptDestroyHash` at `0x100485d5b`
- `ADVAPI32!CryptVerifySignatureW` at `0x100485d45`
- `ADVAPI32!CryptVerifySignatureW` at `0x100485d45`
- `ADVAPI32!CryptHashData` at `0x100485cb0`
- `ADVAPI32!CryptHashData` at `0x100485cb0`
- `ADVAPI32!CryptCreateHash` at `0x100485c30`
- `ADVAPI32!CryptCreateHash` at `0x100485c30`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485dc4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485dc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall sqlencrypt::CertificateStoreProvider::RSAVerifySignature(
        BYTE *pbData,
        DWORD dwDataLen,
        const unsigned __int8 *a3,
        unsigned __int64 a4,
        HCRYPTKEY hPubKey,
        struct CEKeystoreContext *a6,
        void (*a7)(struct CEKeystoreContext *, const unsigned __int16 *, ...))
{
  DWORD LastError; // eax
  unsigned __int64 v13; // rdx
  const unsigned __int8 *v14; // r8
  bool v15; // bl
  BYTE *v16; // rdx
  HCRYPTHASH hHash[2]; // [rsp+50h] [rbp-30h] BYREF
  BYTE *pbSignature[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h]

  hHash[1] = -2;
  if ( (bidGblFlags & 2) != 0 && off_1005E7068[0] )
    bidTraceW(0, 310272, off_1005E7068[0], pbData);
  if ( !CryptCreateHash(sqlencrypt::CertificateStoreProvider::_hProvider, 0x800Cu, 0, 0, hHash) )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E7070[0] || bidID == -1 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !CryptHashData(hHash[0], pbData, dwDataLen, 0) )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E7078[0] || bidID == -1 )
      goto LABEL_9;
LABEL_8:
    off_1005D39E0(bidID);
LABEL_9:
    LastError = GetLastError();
    a7(a6, (const unsigned __int16 *)41328, LastError);
    return 0;
  }
  *(_OWORD *)pbSignature = 0;
  v19 = 0;
  std::vector<unsigned char>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(pbSignature, a4, pbSignature);
  v13 = 0;
  if ( a4 )
  {
    v14 = &a3[a4 - 1];
    do
      pbSignature[0][v13++] = *v14--;
    while ( v13 < a4 );
  }
  v15 = CryptVerifySignatureW(hHash[0], pbSignature[0], a4, hPubKey, 0, 0);
  if ( hHash[0] )
    CryptDestroyHash(hHash[0]);
  if ( (bidGblFlags & 2) != 0 && off_1005E7080[0] )
    bidTraceW(0, 349184, off_1005E7080[0], v15);
  v16 = pbSignature[0];
  if ( pbSignature[0] )
  {
    if ( v19 - (unsigned __int64)pbSignature[0] >= 0x1000 )
    {
      if ( ((__int64)pbSignature[0] & 0x1F) != 0
        || (v16 = (BYTE *)*((_QWORD *)pbSignature[0] - 1), v16 >= pbSignature[0])
        || (unsigned __int64)(pbSignature[0] - v16 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x100485b90  mov     r11, rsp
0x100485b93  push    rbp
0x100485b94  push    r14
0x100485b96  push    r15
0x100485b98  mov     rbp, rsp
0x100485b9b  sub     rsp, 80h
0x100485ba2  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x100485baa  mov     [r11+8], rbx
0x100485bae  mov     [r11+10h], rsi
0x100485bb2  mov     [r11+18h], rdi
0x100485bb6  mov     [r11+20h], r12
0x100485bba  mov     rbx, r9
0x100485bbd  mov     r14, r8
0x100485bc0  mov     r15, rdx
0x100485bc3  mov     r12, rcx
0x100485bc6  mov     rdi, [rbp+arg_30]
0x100485bca  mov     rsi, [rbp+arg_28]
0x100485bce  test    byte ptr cs:_bidGblFlags, 2
0x100485bd5  jz      short loc_100485C15
0x100485bd7  mov     rax, cs:off_1005E7068; "<sqlencrypt::CertificateStoreProvider::"...
0x100485bde  test    rax, rax
0x100485be1  jz      short loc_100485C15
0x100485be3  mov     [r11-50h], rdi
0x100485be7  mov     [r11-58h], rsi
0x100485beb  lea     rax, [rbp+hPubKey]
0x100485bef  mov     [r11-60h], rax
0x100485bf3  mov     [r11-68h], rbx
0x100485bf7  mov     [r11-70h], r8
0x100485bfb  mov     [r11-78h], rdx
0x100485bff  mov     r9, rcx
0x100485c02  mov     r8, cs:off_1005E7068; "<sqlencrypt::CertificateStoreProvider::"...
0x100485c09  mov     edx, 4BC00h
0x100485c0e  xor     ecx, ecx
0x100485c10  call    _bidTraceW
0x100485c15  lea     rax, [rbp+hHash]
0x100485c19  mov     [rsp+80h+phHash], rax; szDescription
0x100485c1e  xor     r9d, r9d; dwFlags
0x100485c21  xor     r8d, r8d; hKey
0x100485c24  mov     edx, 800Ch; Algid
0x100485c29  mov     rcx, cs:?_hProvider@CertificateStoreProvider@sqlencrypt@@0_KA; hProv
0x100485c30  call    cs:__imp_CryptCreateHash
0x100485c36  test    eax, eax
0x100485c38  jnz     short loc_100485CA3
0x100485c3a  test    byte ptr cs:_bidGblFlags, 2
0x100485c41  jz      short loc_100485C82
0x100485c43  mov     rax, cs:off_1005E7070; "<sqlencrypt::CertificateStoreProvider::"...
0x100485c4a  test    rax, rax
0x100485c4d  jz      short loc_100485C82
0x100485c4f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100485c57  jz      short loc_100485C82
0x100485c59  mov     r9, cs:off_1005E7070; "<sqlencrypt::CertificateStoreProvider::"...
0x100485c60  mov     r8d, 4D800h
0x100485c66  and     [rsp+80h+phHash], 0
0x100485c6c  xor     edx, edx
0x100485c6e  mov     rax, cs:off_1005D39E0
0x100485c75  mov     rcx, cs:_bidID
0x100485c7c  call    cs:__guard_dispatch_icall_fptr
0x100485c82  call    cs:__imp_GetLastError
0x100485c88  mov     r8d, eax
0x100485c8b  mov     edx, 0A170h
0x100485c90  mov     rcx, rsi
0x100485c93  mov     rax, rdi
0x100485c96  call    cs:__guard_dispatch_icall_fptr
0x100485c9c  xor     al, al
0x100485c9e  jmp     loc_100485DD5
0x100485ca3  xor     r9d, r9d; dwFlags
0x100485ca6  mov     r8d, r15d; dwDataLen
0x100485ca9  mov     rdx, r12; pbData
0x100485cac  mov     rcx, [rbp+hHash]; hHash
0x100485cb0  call    cs:__imp_CryptHashData
0x100485cb6  test    eax, eax
0x100485cb8  jnz     short loc_100485CEB
0x100485cba  test    byte ptr cs:_bidGblFlags, 2
0x100485cc1  jz      short loc_100485C82
0x100485cc3  mov     rax, cs:off_1005E7078; "<sqlencrypt::CertificateStoreProvider::"...
0x100485cca  test    rax, rax
0x100485ccd  jz      short loc_100485C82
0x100485ccf  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100485cd7  jz      short loc_100485C82
0x100485cd9  mov     r9, cs:off_1005E7078; "<sqlencrypt::CertificateStoreProvider::"...
0x100485ce0  mov     r8d, 4F400h
0x100485ce6  jmp     loc_100485C66
0x100485ceb  xorps   xmm0, xmm0
0x100485cee  movdqu  xmmword ptr [rbp+pbSignature], xmm0
0x100485cf3  and     [rbp+var_10], 0
0x100485cf8  lea     r8, [rbp+pbSignature]
0x100485cfc  mov     rdx, rbx
0x100485cff  lea     rcx, [rbp+pbSignature]
0x100485d03  call    ??$_Resize@V_lambda_2b51424039c320f102fd798e073c89b2_@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KV_lambda_2b51424039c320f102fd798e073c89b2_@@@Z; std::vector<uchar>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(unsigned __int64,_lambda_2b51424039c320f102fd798e073c89b2_)
0x100485d08  xor     edx, edx
0x100485d0a  test    rbx, rbx
0x100485d0d  jz      short loc_100485D2B
0x100485d0f  lea     r8, [rbx-1]
0x100485d13  add     r8, r14
0x100485d16  mov     cl, [r8]
0x100485d19  mov     rax, [rbp+pbSignature]
0x100485d1d  mov     [rax+rdx], cl
0x100485d20  inc     rdx
0x100485d23  dec     r8
0x100485d26  cmp     rdx, rbx
0x100485d29  jb      short loc_100485D16
0x100485d2b  and     [rsp+80h+var_58], 0
0x100485d30  and     [rsp+80h+phHash], 0
0x100485d36  mov     r9, [rbp+hPubKey]; hPubKey
0x100485d3a  mov     r8d, ebx; dwSigLen
0x100485d3d  mov     rdx, [rbp+pbSignature]; pbSignature
0x100485d41  mov     rcx, [rbp+hHash]; hHash
0x100485d45  call    cs:__imp_CryptVerifySignatureW
0x100485d4b  neg     eax
0x100485d4d  sbb     bl, bl
0x100485d4f  and     bl, 1
0x100485d52  mov     rcx, [rbp+hHash]; hHash
0x100485d56  test    rcx, rcx
0x100485d59  jz      short loc_100485D61
0x100485d5b  call    cs:__imp_CryptDestroyHash
0x100485d61  test    byte ptr cs:_bidGblFlags, 2
0x100485d68  jz      short loc_100485D8E
0x100485d6a  mov     rax, cs:off_1005E7080; "<sqlencrypt::CertificateStoreProvider::"...
0x100485d71  test    rax, rax
0x100485d74  jz      short loc_100485D8E
0x100485d76  movzx   r9d, bl
0x100485d7a  mov     r8, cs:off_1005E7080; "<sqlencrypt::CertificateStoreProvider::"...
0x100485d81  mov     edx, 55400h
0x100485d86  xor     ecx, ecx
0x100485d88  call    _bidTraceW
0x100485d8d  nop
0x100485d8e  mov     rdx, [rbp+pbSignature]
0x100485d92  test    rdx, rdx
0x100485d95  jz      short loc_100485DD3
0x100485d97  mov     rcx, rdx
0x100485d9a  mov     rax, [rbp+var_10]
0x100485d9e  sub     rax, rdx
0x100485da1  cmp     rax, 1000h
0x100485da7  jb      short loc_100485DCB
0x100485da9  test    cl, 1Fh
0x100485dac  jnz     short loc_100485DC4
0x100485dae  mov     rdx, [rdx-8]
0x100485db2  cmp     rdx, rcx
0x100485db5  jnb     short loc_100485DC4
0x100485db7  sub     rcx, rdx
0x100485dba  sub     rcx, 8
0x100485dbe  cmp     rcx, 1Fh
0x100485dc2  jbe     short loc_100485DCB
0x100485dc4  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x100485dcb  mov     rcx, rdx; void *
0x100485dce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100485dd3  mov     al, bl
0x100485dd5  lea     r11, [rsp+80h+var_s0]
0x100485ddd  mov     rbx, [r11+20h]
0x100485de1  mov     rsi, [r11+28h]
0x100485de5  mov     rdi, [r11+30h]
0x100485de9  mov     r12, [r11+38h]
0x100485ded  mov     rsp, r11
0x100485df0  pop     r15
0x100485df2  pop     r14
0x100485df4  pop     rbp
0x100485df5  retn
```
