# IISCryptoImportSessionKeyBlob2

- ea: `0x18002b0a0`
- end: `0x18002b29a`
- name: `IISCryptoImportSessionKeyBlob2`
- size: `506`
- prototype: `__int64 __usercall@<rax>(HCRYPTKEY *phKey@<rcx>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a35c`

## callees

- `0x180029bc8`
- `0x180029c24`
- `0x18002ae00`
- `0x18002b0a0`
- `0x1800309d0`

## import_xrefs

- `ADVAPI32!CryptImportKey` at `0x18002b21b`
- `ADVAPI32!CryptImportKey` at `0x18002b21b`
- `ADVAPI32!CryptHashData` at `0x18002b162`
- `ADVAPI32!CryptHashData` at `0x18002b1a3`
- `ADVAPI32!CryptHashData` at `0x18002b162`
- `ADVAPI32!CryptHashData` at `0x18002b1a3`
- `IisRTL!PuDbgPrint` at `0x18002b25e`
- `IisRTL!PuDbgPrint` at `0x18002b25e`

## string_xrefs

- `0x18002b141`: `IISCryptoImportSessionKeyBlobWithPasswd.IISCryptoCreateHash failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoImportSessionKeyBlob2(HCRYPTKEY *phKey, __int64 a2, HCRYPTPROV a3, const BYTE *a4)
{
  int v9; // eax
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r8
  int KeyDeriveKey2; // eax
  HCRYPTKEY *phKeya; // [rsp+28h] [rbp-40h]
  HCRYPTHASH hHash; // [rsp+30h] [rbp-38h] BYREF
  HCRYPTKEY hPubKey; // [rsp+38h] [rbp-30h] BYREF
  BYTE pbData[16]; // [rsp+40h] [rbp-28h] BYREF

  hPubKey = 0;
  if ( !dword_180048964 )
  {
    if ( a3 != 1984918096 || *(_DWORD *)a2 != 1648583497 )
      return 2147942487LL;
    *phKey = 1800627539;
    return 0;
  }
  v9 = *(_DWORD *)(a2 + 8) + 7;
  hHash = 0;
  *(_OWORD *)pbData = *(_OWORD *)((v9 & 0xFFFFFFF8) + a2 + 16);
  v10 = IISCryptoCreateHash(&hHash, a3);
  if ( v10 >= 0 )
  {
    if ( CryptHashData(hHash, pbData, 0x10u, 0) )
    {
      v13 = -1;
      do
        ++v13;
      while ( a4[v13] );
      if ( CryptHashData(hHash, a4, v13, 0) )
      {
        KeyDeriveKey2 = IISCryptoGetKeyDeriveKey2(&hPubKey, a3, hHash);
        v10 = KeyDeriveKey2;
        if ( KeyDeriveKey2 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              1175,
              "IISCryptoImportSessionKeyBlob2",
              "IISCryptoImportSessionKeyBlobWithPasswd.IISCryptoGetKeyDeriveKey2 failed err=0x%x.\n",
              KeyDeriveKey2);
          goto LABEL_24;
        }
        if ( CryptImportKey(a3, (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), hPubKey, 0, phKey) )
        {
          IISCryptoDestroyHash(hHash);
          return 0;
        }
        v10 = -2147023573;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v11 = "IISCryptoImportSessionKeyBlob.CryptImportKey failed err=0x%x.\n";
          v12 = 1195;
          goto LABEL_23;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        v11 = "IISCryptoImportSessionKeyBlobWithPasswd.CryptHashData failed err=0x%x.\n";
        v12 = 1161;
        goto LABEL_23;
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      v11 = "IISCryptoImportSessionKeyBlobWithPasswd.CryptHashData failed err=0x%x.\n";
      v12 = 1151;
      goto LABEL_23;
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v11 = "IISCryptoImportSessionKeyBlobWithPasswd.IISCryptoCreateHash failed err=0x%x.\n";
    v12 = 1142;
LABEL_23:
    LODWORD(phKeya) = v10;
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\crypto\\key.cxx", v12, "IISCryptoImportSessionKeyBlob2", v11, phKeya);
  }
LABEL_24:
  if ( hHash )
    IISCryptoDestroyHash(hHash);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b0a0  push    rbp
0x18002b0a2  push    rbx
0x18002b0a3  push    rsi
0x18002b0a4  push    rdi
0x18002b0a5  push    r14
0x18002b0a7  push    r15
0x18002b0a9  mov     rbp, rsp
0x18002b0ac  sub     rsp, 68h
0x18002b0b0  mov     rax, cs:__security_cookie
0x18002b0b7  xor     rax, rsp
0x18002b0ba  mov     [rbp+var_18], rax
0x18002b0be  cmp     cs:dword_180048964, 0
0x18002b0c5  mov     r15, r9
0x18002b0c8  mov     rsi, r8
0x18002b0cb  mov     [rbp+hPubKey], 0
0x18002b0d3  mov     rdi, rdx
0x18002b0d6  mov     r14, rcx
0x18002b0d9  jnz     short loc_18002B102
0x18002b0db  cmp     r8, 764F7250h
0x18002b0e2  jnz     short loc_18002B0F8
0x18002b0e4  cmp     dword ptr [rdx], 62436349h
0x18002b0ea  jnz     short loc_18002B0F8
0x18002b0ec  mov     qword ptr [rcx], 6B536553h
0x18002b0f3  jmp     loc_18002B27F
0x18002b0f8  mov     eax, 80070057h
0x18002b0fd  jmp     loc_18002B281
0x18002b102  mov     eax, [rdx+8]
0x18002b105  mov     ecx, 0FFFFFFF8h
0x18002b10a  add     eax, 7
0x18002b10d  mov     [rbp+hHash], 0
0x18002b115  and     rax, rcx
0x18002b118  lea     rcx, [rbp+hHash]; phHash
0x18002b11c  movups  xmm0, xmmword ptr [rax+rdx+10h]
0x18002b121  mov     rdx, rsi; hProv
0x18002b124  movdqu  xmmword ptr [rbp+pbData], xmm0
0x18002b129  call    IISCryptoCreateHash
0x18002b12e  mov     ebx, eax
0x18002b130  test    eax, eax
0x18002b132  jns     short loc_18002B153
0x18002b134  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b13b  jz      loc_18002B264
0x18002b141  lea     rax, aIiscryptoimpor_4; "IISCryptoImportSessionKeyBlobWithPasswd"...
0x18002b148  mov     r8d, 476h
0x18002b14e  jmp     loc_18002B240
0x18002b153  mov     rcx, [rbp+hHash]; hHash
0x18002b157  lea     rdx, [rbp+pbData]; pbData
0x18002b15b  xor     r9d, r9d; dwFlags
0x18002b15e  lea     r8d, [r9+10h]; dwDataLen
0x18002b162  call    cs:__imp_CryptHashData
0x18002b168  test    eax, eax
0x18002b16a  jnz     short loc_18002B18B
0x18002b16c  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b173  jz      loc_18002B264
0x18002b179  lea     rax, aIiscryptoimpor_0; "IISCryptoImportSessionKeyBlobWithPasswd"...
0x18002b180  mov     r8d, 47Fh
0x18002b186  jmp     loc_18002B240
0x18002b18b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b18f  inc     r8; dwDataLen
0x18002b192  cmp     byte ptr [r15+r8], 0
0x18002b197  jnz     short loc_18002B18F
0x18002b199  mov     rcx, [rbp+hHash]; hHash
0x18002b19d  xor     r9d, r9d; dwFlags
0x18002b1a0  mov     rdx, r15; pbData
0x18002b1a3  call    cs:__imp_CryptHashData
0x18002b1a9  test    eax, eax
0x18002b1ab  jnz     short loc_18002B1C9
0x18002b1ad  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b1b4  jz      loc_18002B264
0x18002b1ba  lea     rax, aIiscryptoimpor_0; "IISCryptoImportSessionKeyBlobWithPasswd"...
0x18002b1c1  mov     r8d, 489h
0x18002b1c7  jmp     short loc_18002B240
0x18002b1c9  mov     r9d, [rbp+arg_20]
0x18002b1cd  lea     rcx, [rbp+hPubKey]; phKey
0x18002b1d1  mov     r8, [rbp+hHash]; hBaseData
0x18002b1d5  mov     rdx, rsi; hProv
0x18002b1d8  call    IISCryptoGetKeyDeriveKey2
0x18002b1dd  mov     ebx, eax
0x18002b1df  test    eax, eax
0x18002b1e1  jns     short loc_18002B1FF
0x18002b1e3  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b1ea  jz      short loc_18002B264
0x18002b1ec  mov     dword ptr [rsp+68h+phKey], eax
0x18002b1f0  mov     r8d, 497h
0x18002b1f6  lea     rax, aIiscryptoimpor_2; "IISCryptoImportSessionKeyBlobWithPasswd"...
0x18002b1fd  jmp     short loc_18002B244
0x18002b1ff  mov     r9, [rbp+hPubKey]; hPubKey
0x18002b203  lea     rdx, [rdi+10h]; pbData
0x18002b207  mov     r8d, [rdi+8]; dwDataLen
0x18002b20b  mov     rcx, rsi; hProv
0x18002b20e  mov     [rsp+68h+phKey], r14; phKey
0x18002b213  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18002b21b  call    cs:__imp_CryptImportKey
0x18002b221  test    eax, eax
0x18002b223  jnz     short loc_18002B276
0x18002b225  test    byte ptr cs:g_dwDebugFlags, 3
0x18002b22c  mov     ebx, 8007052Bh
0x18002b231  jz      short loc_18002B264
0x18002b233  lea     rax, aIiscryptoimpor; "IISCryptoImportSessionKeyBlob.CryptImpo"...
0x18002b23a  mov     r8d, 4ABh
0x18002b240  mov     dword ptr [rsp+68h+phKey], ebx
0x18002b244  mov     rcx, cs:g_pDebug
0x18002b24b  lea     r9, aIiscryptoimpor_5; "IISCryptoImportSessionKeyBlob2"
0x18002b252  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002b259  mov     qword ptr [rsp+68h+dwFlags], rax
0x18002b25e  call    cs:__imp_PuDbgPrint
0x18002b264  mov     rcx, [rbp+hHash]
0x18002b268  test    rcx, rcx
0x18002b26b  jz      short loc_18002B272
0x18002b26d  call    IISCryptoDestroyHash
0x18002b272  mov     eax, ebx
0x18002b274  jmp     short loc_18002B281
0x18002b276  mov     rcx, [rbp+hHash]
0x18002b27a  call    IISCryptoDestroyHash
0x18002b27f  xor     eax, eax
0x18002b281  mov     rcx, [rbp+var_18]
0x18002b285  xor     rcx, rsp; StackCookie
0x18002b288  call    __security_check_cookie
0x18002b28d  add     rsp, 68h
0x18002b291  pop     r15
0x18002b293  pop     r14
0x18002b295  pop     rdi
0x18002b296  pop     rsi
0x18002b297  pop     rbx
0x18002b298  pop     rbp
0x18002b299  retn
```
