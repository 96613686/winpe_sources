# Ssl::GetEncryptionKeyFromHash(unsigned __int64,uchar const *,ulong,char const *,ulong,ulong,ulong,ulong,unsigned __int64 &)

- ea: `0x10042c6ec`
- end: `0x10042c995`
- name: `?GetEncryptionKeyFromHash@Ssl@@CAK_KPEBEKPEBDKKKKAEA_K@Z`
- size: `681`
- prototype: `static unsigned int(unsigned __int64, const unsigned __int8 *, unsigned int, const char *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10042c488`

## callees

- `0x10042a8f8`
- `0x10042c6ec`
- `0x10043056c`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042c8bb`
- `KERNEL32!GetLastError` at `0x10042c8f3`
- `KERNEL32!GetLastError` at `0x10042c940`
- `KERNEL32!GetLastError` at `0x10042c8bb`
- `KERNEL32!GetLastError` at `0x10042c8f3`
- `KERNEL32!GetLastError` at `0x10042c940`
- `ADVAPI32!CryptDestroyHash` at `0x10042c7fa`
- `ADVAPI32!CryptDestroyHash` at `0x10042c951`
- `ADVAPI32!CryptDestroyHash` at `0x10042c7fa`
- `ADVAPI32!CryptDestroyHash` at `0x10042c951`
- `ADVAPI32!CryptHashData` at `0x10042c83c`
- `ADVAPI32!CryptHashData` at `0x10042c869`
- `ADVAPI32!CryptHashData` at `0x10042c881`
- `ADVAPI32!CryptHashData` at `0x10042c83c`
- `ADVAPI32!CryptHashData` at `0x10042c869`
- `ADVAPI32!CryptHashData` at `0x10042c881`
- `ADVAPI32!CryptCreateHash` at `0x10042c81c`
- `ADVAPI32!CryptCreateHash` at `0x10042c81c`
- `ADVAPI32!CryptImportKey` at `0x10042c8e9`
- `ADVAPI32!CryptImportKey` at `0x10042c8e9`
- `ADVAPI32!CryptGetHashParam` at `0x10042c8a3`
- `ADVAPI32!CryptGetHashParam` at `0x10042c8a3`
- `ADVAPI32!CryptSetKeyParam` at `0x10042c936`
- `ADVAPI32!CryptSetKeyParam` at `0x10042c936`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Ssl::GetEncryptionKeyFromHash(
        HCRYPTPROV a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        const BYTE *a4,
        ALG_ID Algid,
        DWORD a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int64 *a9)
{
  unsigned int v12; // r14d
  DWORD LastError; // ebx
  HCRYPTKEY *phKey; // r12
  DWORD v15; // edi
  BYTE *v16; // rcx
  DWORD v17; // esi
  __int64 v18; // rax
  DWORD pdwDataLen; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-38h] BYREF
  BYTE *pbData; // [rsp+50h] [rbp-30h]
  _QWORD v23[2]; // [rsp+58h] [rbp-28h] BYREF
  BYTE *v24[3]; // [rsp+68h] [rbp-18h] BYREF

  v23[1] = -2;
  v23[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7BF8[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      v23,
      off_1005E7BF8[0],
      0);
  v12 = a7;
  if ( a7 && a3 >= 8 )
  {
    LastError = 0;
    hHash = 0;
    phKey = a9;
    *a9 = 0;
    v15 = a6 + v12 - 1 - (v12 - 1) % a6;
    std::vector<unsigned char>::vector<unsigned char>(v24, v15 + 12LL, &a7);
    v16 = v24[0];
    pbData = v24[0] + 12;
    *(_DWORD *)v24[0] = 520;
    *((_DWORD *)v16 + 1) = a8;
    *((_DWORD *)v16 + 2) = v12;
    pdwDataLen = a6;
    v17 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        if ( hHash )
          CryptDestroyHash(hHash);
        pdwDataLen = a6;
        if ( !CryptCreateHash(a1, Algid, 0, 0, &hHash) || v17 && !CryptHashData(hHash, pbData, v17, 0) )
          break;
        if ( a4 )
        {
          v18 = -1;
          do
            ++v18;
          while ( a4[v18] );
        }
        else
        {
          LODWORD(v18) = 0;
        }
        if ( !CryptHashData(hHash, a4, v18, 0)
          || !CryptHashData(hHash, a2, 8u, 0)
          || !CryptGetHashParam(hHash, 2u, &pbData[v17], &pdwDataLen, 0) )
        {
          break;
        }
        v17 += pdwDataLen;
        v15 -= pdwDataLen;
        if ( !v15 )
          goto LABEL_24;
      }
      LastError = GetLastError();
LABEL_24:
      v16 = v24[0];
    }
    if ( v15 )
    {
      LastError = 13;
    }
    else if ( CryptImportKey(a1, v16, v12 + 12, 0, 0, phKey) )
    {
      if ( !CryptSetKeyParam(*phKey, 1u, a2, 0) )
        LastError = GetLastError();
    }
    else
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E5450[0] )
        bidTraceW(0, 1327104, off_1005E5450[0], LastError);
    }
    if ( hHash )
      CryptDestroyHash(hHash);
    std::vector<unsigned char>::_Tidy(v24);
  }
  else
  {
    LastError = 13;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v23);
  return LastError;
}

```

## disassembly

```asm
0x10042c6ec  mov     r11, rsp
0x10042c6ef  mov     [r11+8], rcx
0x10042c6f3  push    rbp
0x10042c6f4  push    r12
0x10042c6f6  push    r13
0x10042c6f8  push    r14
0x10042c6fa  push    r15
0x10042c6fc  mov     rbp, rsp
0x10042c6ff  sub     rsp, 80h
0x10042c706  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x10042c70e  mov     [r11+10h], rbx
0x10042c712  mov     [r11+18h], rsi
0x10042c716  mov     [r11+20h], rdi
0x10042c71a  mov     r15, r9
0x10042c71d  mov     ebx, r8d
0x10042c720  mov     r13, rdx
0x10042c723  or      [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x10042c728  mov     eax, cs:_bidGblFlags
0x10042c72e  mov     ecx, 20004h
0x10042c733  and     eax, ecx
0x10042c735  xor     edi, edi
0x10042c737  cmp     eax, ecx
0x10042c739  jnz     short loc_10042C77E
0x10042c73b  mov     rax, cs:off_1005E7BF8; "<Ssl::GetEncryptionKeyFromHash|API|SNI>"...
0x10042c742  test    rax, rax
0x10042c745  jz      short loc_10042C77E
0x10042c747  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10042c74f  jz      short loc_10042C77E
0x10042c751  mov     rax, cs:off_1005D39F0
0x10042c758  mov     [r11-80h], rdi
0x10042c75c  mov     rcx, cs:off_1005E7BF8; "<Ssl::GetEncryptionKeyFromHash|API|SNI>"...
0x10042c763  mov     [rsp+80h+phHash], rcx
0x10042c768  lea     r9, [rbp+var_28]
0x10042c76c  xor     r8d, r8d
0x10042c76f  xor     edx, edx
0x10042c771  mov     rcx, cs:_bidID
0x10042c778  call    cs:__guard_dispatch_icall_fptr
0x10042c77e  mov     r14d, [rbp+arg_30]
0x10042c782  test    r14d, r14d
0x10042c785  jz      loc_10042C964
0x10042c78b  cmp     ebx, 8
0x10042c78e  jb      loc_10042C964
0x10042c794  mov     ebx, edi
0x10042c796  mov     [rbp+hHash], rdi
0x10042c79a  mov     r12, [rbp+arg_40]
0x10042c79e  mov     [r12], rdi
0x10042c7a2  lea     edi, [r14-1]
0x10042c7a6  xor     edx, edx
0x10042c7a8  mov     eax, edi
0x10042c7aa  mov     esi, [rbp+arg_28]
0x10042c7ad  div     esi
0x10042c7af  sub     edi, edx
0x10042c7b1  add     edi, esi
0x10042c7b3  mov     edx, edi
0x10042c7b5  add     rdx, 0Ch
0x10042c7b9  lea     r8, [rbp+arg_30]
0x10042c7bd  lea     rcx, [rbp+var_18]
0x10042c7c1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x10042c7c6  mov     rcx, [rbp+var_18]
0x10042c7ca  lea     rax, [rcx+0Ch]
0x10042c7ce  mov     [rbp+pbData], rax
0x10042c7d2  mov     dword ptr [rcx], 208h
0x10042c7d8  mov     eax, [rbp+arg_38]
0x10042c7db  mov     [rcx+4], eax
0x10042c7de  xor     eax, eax
0x10042c7e0  mov     [rcx+8], r14d
0x10042c7e4  mov     [rbp+pdwDataLen], esi
0x10042c7e7  mov     esi, eax
0x10042c7e9  test    edi, edi
0x10042c7eb  jz      loc_10042C8C7
0x10042c7f1  mov     rcx, [rbp+hHash]; hHash
0x10042c7f5  test    rcx, rcx
0x10042c7f8  jz      short loc_10042C800
0x10042c7fa  call    cs:__imp_CryptDestroyHash
0x10042c800  mov     eax, [rbp+arg_28]
0x10042c803  mov     [rbp+pdwDataLen], eax
0x10042c806  lea     rax, [rbp+hHash]
0x10042c80a  mov     [rsp+80h+phHash], rax; dwFlags
0x10042c80f  xor     r9d, r9d; dwFlags
0x10042c812  xor     r8d, r8d; hKey
0x10042c815  mov     edx, [rbp+Algid]; Algid
0x10042c818  mov     rcx, [rbp+hProv]; hProv
0x10042c81c  call    cs:__imp_CryptCreateHash
0x10042c822  test    eax, eax
0x10042c824  jz      loc_10042C8BB
0x10042c82a  test    esi, esi
0x10042c82c  jz      short loc_10042C846
0x10042c82e  xor     r9d, r9d; dwFlags
0x10042c831  mov     r8d, esi; dwDataLen
0x10042c834  mov     rdx, [rbp+pbData]; pbData
0x10042c838  mov     rcx, [rbp+hHash]; hHash
0x10042c83c  call    cs:__imp_CryptHashData
0x10042c842  test    eax, eax
0x10042c844  jz      short loc_10042C8BB
0x10042c846  test    r15, r15
0x10042c849  jz      short loc_10042C85A
0x10042c84b  or      rax, 0FFFFFFFFFFFFFFFFh
0x10042c84f  inc     rax
0x10042c852  cmp     [r15+rax], bl
0x10042c856  jnz     short loc_10042C84F
0x10042c858  jmp     short loc_10042C85C
0x10042c85a  xor     eax, eax
0x10042c85c  xor     r9d, r9d; dwFlags
0x10042c85f  mov     r8d, eax; dwDataLen
0x10042c862  mov     rdx, r15; pbData
0x10042c865  mov     rcx, [rbp+hHash]; hHash
0x10042c869  call    cs:__imp_CryptHashData
0x10042c86f  test    eax, eax
0x10042c871  jz      short loc_10042C8BB
0x10042c873  xor     r9d, r9d; dwFlags
0x10042c876  lea     r8d, [r9+8]; dwDataLen
0x10042c87a  mov     rdx, r13; pbData
0x10042c87d  mov     rcx, [rbp+hHash]; hHash
0x10042c881  call    cs:__imp_CryptHashData
0x10042c887  test    eax, eax
0x10042c889  jz      short loc_10042C8BB
0x10042c88b  mov     r8d, esi
0x10042c88e  add     r8, [rbp+pbData]; pbData
0x10042c892  and     dword ptr [rsp+80h+phHash], ebx
0x10042c896  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x10042c89a  mov     edx, 2; dwParam
0x10042c89f  mov     rcx, [rbp+hHash]; hHash
0x10042c8a3  call    cs:__imp_CryptGetHashParam
0x10042c8a9  test    eax, eax
0x10042c8ab  jz      short loc_10042C8BB
0x10042c8ad  add     esi, [rbp+pdwDataLen]
0x10042c8b0  sub     edi, [rbp+pdwDataLen]
0x10042c8b3  jnz     loc_10042C7F1
0x10042c8b9  jmp     short loc_10042C8C3
0x10042c8bb  call    cs:__imp_GetLastError
0x10042c8c1  mov     ebx, eax
0x10042c8c3  mov     rcx, [rbp+var_18]
0x10042c8c7  xor     esi, esi
0x10042c8c9  test    edi, edi
0x10042c8cb  jz      short loc_10042C8D2
0x10042c8cd  lea     ebx, [rsi+0Dh]
0x10042c8d0  jmp     short loc_10042C948
0x10042c8d2  lea     r8d, [r14+0Ch]; dwDataLen
0x10042c8d6  mov     [rsp+80h+phKey], r12; phKey
0x10042c8db  mov     dword ptr [rsp+80h+phHash], esi; dwFlags
0x10042c8df  xor     r9d, r9d; hPubKey
0x10042c8e2  mov     rdx, rcx; pbData
0x10042c8e5  mov     rcx, [rbp+hProv]; hProv
0x10042c8e9  call    cs:__imp_CryptImportKey
0x10042c8ef  test    eax, eax
0x10042c8f1  jnz     short loc_10042C928
0x10042c8f3  call    cs:__imp_GetLastError
0x10042c8f9  mov     ebx, eax
0x10042c8fb  test    byte ptr cs:_bidGblFlags, 2
0x10042c902  jz      short loc_10042C948
0x10042c904  mov     rax, cs:off_1005E5450; "<Ssl::GetEncryptionKeyFromHash|ERR|SNI>"...
0x10042c90b  test    rax, rax
0x10042c90e  jz      short loc_10042C948
0x10042c910  mov     r9d, ebx
0x10042c913  mov     r8, cs:off_1005E5450; "<Ssl::GetEncryptionKeyFromHash|ERR|SNI>"...
0x10042c91a  mov     edx, 144000h
0x10042c91f  xor     ecx, ecx
0x10042c921  call    _bidTraceW
0x10042c926  jmp     short loc_10042C948
0x10042c928  xor     r9d, r9d; dwFlags
0x10042c92b  mov     r8, r13; pbData
0x10042c92e  lea     edx, [r9+1]; dwParam
0x10042c932  mov     rcx, [r12]; hKey
0x10042c936  call    cs:__imp_CryptSetKeyParam
0x10042c93c  test    eax, eax
0x10042c93e  jnz     short loc_10042C948
0x10042c940  call    cs:__imp_GetLastError
0x10042c946  mov     ebx, eax
0x10042c948  mov     rcx, [rbp+hHash]; hHash
0x10042c94c  test    rcx, rcx
0x10042c94f  jz      short loc_10042C958
0x10042c951  call    cs:__imp_CryptDestroyHash
0x10042c957  nop
0x10042c958  lea     rcx, [rbp+var_18]
0x10042c95c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x10042c961  nop
0x10042c962  jmp     short loc_10042C969
0x10042c964  mov     ebx, 0Dh
0x10042c969  lea     rcx, [rbp+var_28]; this
0x10042c96d  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042c972  mov     eax, ebx
0x10042c974  lea     r11, [rsp+80h+var_s0]
0x10042c97c  mov     rbx, [r11+38h]
0x10042c980  mov     rsi, [r11+40h]
0x10042c984  mov     rdi, [r11+48h]
0x10042c988  mov     rsp, r11
0x10042c98b  pop     r15
0x10042c98d  pop     r14
0x10042c98f  pop     r13
0x10042c991  pop     r12
0x10042c993  pop     rbp
0x10042c994  retn
```
