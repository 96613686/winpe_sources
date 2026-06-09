# IISCryptoImportSessionKeyBlob

- ea: `0x18002aea0`
- end: `0x18002b099`
- name: `IISCryptoImportSessionKeyBlob`
- size: `505`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a418`

## callees

- `0x18002937c`
- `0x180029bc8`
- `0x180029c24`
- `0x18002aea0`

## import_xrefs

- `ADVAPI32!CryptImportKey` at `0x18002b020`
- `ADVAPI32!CryptImportKey` at `0x18002b020`
- `ADVAPI32!CryptVerifySignatureA` at `0x18002afd1`
- `ADVAPI32!CryptVerifySignatureA` at `0x18002afd1`
- `ADVAPI32!CryptHashData` at `0x18002af6e`
- `ADVAPI32!CryptHashData` at `0x18002af6e`
- `IisRTL!PuDbgPrint` at `0x18002af44`
- `IisRTL!PuDbgPrint` at `0x18002b065`
- `IisRTL!PuDbgPrint` at `0x18002af44`
- `IisRTL!PuDbgPrint` at `0x18002b065`

## string_xrefs

- `0x18002af23`: `IISCryptoImportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoImportSessionKeyBlob(HCRYPTKEY *phKey, __int64 a2, HCRYPTPROV a3, HCRYPTKEY a4)
{
  int Hash; // eax
  int v10; // ebx
  int LastError; // eax
  int v12; // eax
  int v13; // eax
  DWORD dwFlags[2]; // [rsp+28h] [rbp-40h]
  HCRYPTHASH hHash[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !dword_180048964 )
  {
    if ( a3 != 1984918096 || a4 != 1799842131 || *(_DWORD *)a2 != 1648583497 )
      return 2147942487LL;
    *phKey = 1800627539;
    return 0;
  }
  hHash[0] = 0;
  Hash = IISCryptoCreateHash(hHash, a3);
  v10 = Hash;
  if ( Hash < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        728,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.IISCryptoCreateHash failed err=0x%x.\n",
        Hash);
LABEL_23:
    if ( hHash[0] )
      IISCryptoDestroyHash(hHash[0]);
    return (unsigned int)v10;
  }
  if ( !hHash[0] )
    return (unsigned int)-2147467259;
  if ( !CryptHashData(hHash[0], (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), 0) )
  {
    LastError = IcpGetLastError();
    v10 = LastError;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        750,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptHashData failed err=0x%x.\n",
        LastError);
    goto LABEL_23;
  }
  if ( !CryptVerifySignatureA(
          hHash[0],
          (const BYTE *)(a2 + ((*(_DWORD *)(a2 + 8) + 7) & 0xFFFFFFF8) + 16LL),
          *(_DWORD *)(a2 + 12),
          a4,
          0,
          0) )
  {
    v12 = IcpGetLastError();
    v10 = v12;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      dwFlags[0] = v12;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        765,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptVerifySignature failed err=0x%x.\n",
        *(_QWORD *)dwFlags);
    }
    goto LABEL_23;
  }
  if ( !CryptImportKey(a3, (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), 0, 0, phKey) )
  {
    v13 = IcpGetLastError();
    v10 = v13;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        784,
        "IISCryptoImportSessionKeyBlob",
        "IISCryptoImportSessionKeyBlob.CryptImportKey failed err=0x%x.\n",
        v13);
    if ( v10 < 0 )
      goto LABEL_23;
  }
  IISCryptoDestroyHash(hHash[0]);
  return 0;
}

```

## disassembly

```asm
0x18002aea0  push    rbx
0x18002aea2  push    rbp
0x18002aea3  push    rsi
0x18002aea4  push    rdi
0x18002aea5  push    r14
0x18002aea7  sub     rsp, 40h
0x18002aeab  cmp     cs:dword_180048964, 0
0x18002aeb2  mov     rbp, r9
0x18002aeb5  mov     rsi, r8
0x18002aeb8  mov     rdi, rdx
0x18002aebb  mov     r14, rcx
0x18002aebe  jnz     short loc_18002AEF0
0x18002aec0  cmp     r8, 764F7250h
0x18002aec7  jnz     short loc_18002AEE6
0x18002aec9  cmp     r9, 6B476953h
0x18002aed0  jnz     short loc_18002AEE6
0x18002aed2  cmp     dword ptr [rdx], 62436349h
0x18002aed8  jnz     short loc_18002AEE6
0x18002aeda  mov     qword ptr [rcx], 6B536553h
0x18002aee1  jmp     loc_18002B08C
0x18002aee6  mov     eax, 80070057h
0x18002aeeb  jmp     loc_18002B08E
0x18002aef0  mov     rdx, rsi; hProv
0x18002aef3  mov     [rsp+68h+hHash], 0
0x18002aefc  lea     rcx, [rsp+68h+hHash]; phHash
0x18002af01  call    IISCryptoCreateHash
0x18002af06  mov     ebx, eax
0x18002af08  test    eax, eax
0x18002af0a  jns     short loc_18002AF4F
0x18002af0c  test    byte ptr cs:g_dwDebugFlags, 3
0x18002af13  jz      loc_18002B06F
0x18002af19  mov     [rsp+68h+dwFlags], eax
0x18002af1d  mov     r8d, 2D8h
0x18002af23  lea     rax, aIiscryptoimpor_3; "IISCryptoImportSessionKeyBlob.IISCrypto"...
0x18002af2a  mov     rcx, cs:g_pDebug
0x18002af31  lea     r9, aIiscryptoimpor_7; "IISCryptoImportSessionKeyBlob"
0x18002af38  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002af3f  mov     [rsp+68h+szDescription], rax
0x18002af44  call    cs:__imp_PuDbgPrint
0x18002af4a  jmp     loc_18002B06F
0x18002af4f  mov     rcx, [rsp+68h+hHash]; hHash
0x18002af54  test    rcx, rcx
0x18002af57  jnz     short loc_18002AF63
0x18002af59  mov     ebx, 80004005h
0x18002af5e  jmp     loc_18002B07E
0x18002af63  mov     r8d, [rdi+8]; dwDataLen
0x18002af67  lea     rdx, [rdi+10h]; pbData
0x18002af6b  xor     r9d, r9d; dwFlags
0x18002af6e  call    cs:__imp_CryptHashData
0x18002af74  test    eax, eax
0x18002af76  jnz     short loc_18002AF9F
0x18002af78  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002af7d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002af84  mov     ebx, eax
0x18002af86  jz      loc_18002B06F
0x18002af8c  mov     [rsp+68h+dwFlags], eax
0x18002af90  mov     r8d, 2EEh
0x18002af96  lea     rax, aIiscryptoimpor_6; "IISCryptoImportSessionKeyBlob.CryptHash"...
0x18002af9d  jmp     short loc_18002AF2A
0x18002af9f  mov     edx, [rdi+8]
0x18002afa2  mov     ecx, 0FFFFFFF8h
0x18002afa7  mov     r8d, [rdi+0Ch]; dwSigLen
0x18002afab  add     edx, 7
0x18002afae  and     rdx, rcx
0x18002afb1  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18002afb9  mov     rcx, [rsp+68h+hHash]; hHash
0x18002afbe  add     rdx, 10h
0x18002afc2  add     rdx, rdi; pbSignature
0x18002afc5  mov     [rsp+68h+szDescription], 0; szDescription
0x18002afce  mov     r9, rbp; hPubKey
0x18002afd1  call    cs:__imp_CryptVerifySignatureA
0x18002afd7  test    eax, eax
0x18002afd9  jnz     short loc_18002B005
0x18002afdb  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002afe0  test    byte ptr cs:g_dwDebugFlags, 3
0x18002afe7  mov     ebx, eax
0x18002afe9  jz      loc_18002B06F
0x18002afef  mov     [rsp+68h+dwFlags], eax
0x18002aff3  mov     r8d, 2FDh
0x18002aff9  lea     rax, aIiscryptoimpor_1; "IISCryptoImportSessionKeyBlob.CryptVeri"...
0x18002b000  jmp     loc_18002AF2A
0x18002b005  mov     r8d, [rdi+8]; dwDataLen
0x18002b009  lea     rdx, [rdi+10h]; pbData
0x18002b00d  mov     qword ptr [rsp+68h+dwFlags], r14; phKey
0x18002b012  xor     r9d, r9d; hPubKey
0x18002b015  mov     rcx, rsi; hProv
0x18002b018  mov     dword ptr [rsp+68h+szDescription], 0; dwFlags
0x18002b020  call    cs:__imp_CryptImportKey
0x18002b026  test    eax, eax
0x18002b028  jnz     short loc_18002B082
0x18002b02a  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002b02f  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b036  mov     ebx, eax
0x18002b038  jz      short loc_18002B06B
0x18002b03a  mov     rcx, cs:g_pDebug
0x18002b041  lea     r9, aIiscryptoimpor_7; "IISCryptoImportSessionKeyBlob"
0x18002b048  mov     [rsp+68h+dwFlags], eax
0x18002b04c  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002b053  lea     rax, aIiscryptoimpor; "IISCryptoImportSessionKeyBlob.CryptImpo"...
0x18002b05a  mov     r8d, 310h
0x18002b060  mov     [rsp+68h+szDescription], rax
0x18002b065  call    cs:__imp_PuDbgPrint
0x18002b06b  test    ebx, ebx
0x18002b06d  jns     short loc_18002B082
0x18002b06f  mov     rcx, [rsp+68h+hHash]
0x18002b074  test    rcx, rcx
0x18002b077  jz      short loc_18002B07E
0x18002b079  call    IISCryptoDestroyHash
0x18002b07e  mov     eax, ebx
0x18002b080  jmp     short loc_18002B08E
0x18002b082  mov     rcx, [rsp+68h+hHash]
0x18002b087  call    IISCryptoDestroyHash
0x18002b08c  xor     eax, eax
0x18002b08e  add     rsp, 40h
0x18002b092  pop     r14
0x18002b094  pop     rdi
0x18002b095  pop     rsi
0x18002b096  pop     rbp
0x18002b097  pop     rbx
0x18002b098  retn
```
