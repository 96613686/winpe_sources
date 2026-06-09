# SetCachedCredentials(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180022a70`
- end: `0x180022ba8`
- name: `?SetCachedCredentials@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `312`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bd14`

## callees

- `0x180002240`
- `0x180022a10`
- `0x180022a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022b5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022b5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b7d`
- `KERNEL32!lstrlenW` at `0x180022afc`
- `KERNEL32!lstrlenW` at `0x180022afc`
- `CRYPT32!CryptProtectData` at `0x180022b2f`
- `CRYPT32!CryptProtectData` at `0x180022b2f`

## pseudocode

```c
__int64 __fastcall SetCachedCredentials(HKEY hKey, const unsigned __int16 *a2, BYTE *a3)
{
  unsigned int inited; // ebx
  int v7; // edx
  __int64 v8; // rax
  int LastError; // eax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-40h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-30h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+60h] [rbp-20h] BYREF
  _DWORD v14[2]; // [rsp+70h] [rbp-10h] BYREF

  inited = InitCredentialPersist();
  if ( !inited )
  {
    *(_QWORD *)&pDataIn.cbData = 0;
    pOptionalEntropy.pbData = (BYTE *)v14;
    pOptionalEntropy.cbData = 4;
    v7 = 0;
    v14[0] = 0;
    pDataOut = 0;
    if ( *a2 )
    {
      do
      {
        v8 = v7++;
        *((_BYTE *)v14 + (v8 & 3)) += a2[v8] & 0x1F;
      }
      while ( a2[v7] );
    }
    pDataIn.pbData = a3;
    pDataIn.cbData = 2 * lstrlenW((LPCWSTR)a3) + 2;
    if ( CryptProtectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 1u, &pDataOut) )
      LastError = RegSetValueExW(hKey, L"Password", 0, 3u, pDataOut.pbData, pDataOut.cbData);
    else
      LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    LocalFree(pDataOut.pbData);
  }
  return inited;
}

```

## disassembly

```asm
0x180022a70  mov     [rsp-28h+arg_8], rbx
0x180022a75  push    rbp
0x180022a76  push    rsi
0x180022a77  push    rdi
0x180022a78  push    r14
0x180022a7a  push    r15
0x180022a7c  mov     rbp, rsp
0x180022a7f  sub     rsp, 80h
0x180022a86  mov     rax, cs:__security_cookie
0x180022a8d  xor     rax, rsp
0x180022a90  mov     [rbp+var_8], rax
0x180022a94  mov     rsi, r8
0x180022a97  mov     rdi, rdx
0x180022a9a  mov     r14, rcx
0x180022a9d  call    ?InitCredentialPersist@@YAJXZ; InitCredentialPersist(void)
0x180022aa2  xor     r15d, r15d
0x180022aa5  mov     ebx, eax
0x180022aa7  test    eax, eax
0x180022aa9  jnz     loc_180022B83
0x180022aaf  lea     rax, [rbp+var_10]
0x180022ab3  mov     qword ptr [rbp+pDataIn.cbData], r15
0x180022ab7  mov     [rbp+pOptionalEntropy.pbData], rax
0x180022abb  xorps   xmm0, xmm0
0x180022abe  xor     eax, eax
0x180022ac0  mov     [rbp+pOptionalEntropy.cbData], 4
0x180022ac7  mov     edx, r15d
0x180022aca  mov     [rbp+var_10], eax
0x180022acd  movups  xmmword ptr [rbp+var_40.cbData], xmm0
0x180022ad1  cmp     [rdi], r15w
0x180022ad5  jz      short loc_180022AF5
0x180022ad7  movsxd  rax, edx
0x180022ada  inc     edx
0x180022adc  mov     rcx, rax
0x180022adf  and     ecx, 3
0x180022ae2  mov     al, [rdi+rax*2]
0x180022ae5  and     al, 1Fh
0x180022ae7  add     byte ptr [rbp+rcx+var_10], al
0x180022aeb  movsxd  rax, edx
0x180022aee  cmp     [rdi+rax*2], r15w
0x180022af3  jnz     short loc_180022AD7
0x180022af5  mov     rcx, rsi; lpString
0x180022af8  mov     [rbp+pDataIn.pbData], rsi
0x180022afc  call    cs:__imp_lstrlenW
0x180022b02  xor     r9d, r9d; pvReserved
0x180022b05  lea     r8, [rbp+pOptionalEntropy]; pOptionalEntropy
0x180022b09  xor     edx, edx; szDataDescr
0x180022b0b  lea     rcx, [rbp+pDataIn]; pDataIn
0x180022b0f  lea     eax, ds:2[rax*2]
0x180022b16  mov     [rbp+pDataIn.cbData], eax
0x180022b19  lea     rax, [rbp+var_40]
0x180022b1d  mov     [rsp+80h+pDataOut], rax; pDataOut
0x180022b22  mov     [rsp+80h+dwFlags], 1; dwFlags
0x180022b2a  mov     [rsp+80h+pPromptStruct], r15; pPromptStruct
0x180022b2f  call    cs:__imp_CryptProtectData
0x180022b35  test    eax, eax
0x180022b37  jz      short loc_180022B64
0x180022b39  mov     eax, [rbp+var_40.cbData]
0x180022b3c  lea     rdx, ValueName; "Password"
0x180022b43  mov     [rsp+80h+dwFlags], eax; cbData
0x180022b47  mov     r9d, 3; dwType
0x180022b4d  mov     rax, [rbp+var_40.pbData]
0x180022b51  xor     r8d, r8d; Reserved
0x180022b54  mov     rcx, r14; hKey
0x180022b57  mov     [rsp+80h+pPromptStruct], rax; lpData
0x180022b5c  call    cs:__imp_RegSetValueExW
0x180022b62  jmp     short loc_180022B6A
0x180022b64  call    cs:__imp_GetLastError
0x180022b6a  mov     ebx, eax
0x180022b6c  test    eax, eax
0x180022b6e  jle     short loc_180022B79
0x180022b70  movzx   ebx, ax
0x180022b73  or      ebx, 80070000h
0x180022b79  mov     rcx, [rbp+var_40.pbData]; hMem
0x180022b7d  call    cs:__imp_LocalFree
0x180022b83  mov     eax, ebx
0x180022b85  mov     rcx, [rbp+var_8]
0x180022b89  xor     rcx, rsp; StackCookie
0x180022b8c  call    __security_check_cookie
0x180022b91  mov     rbx, [rsp+80h+arg_8]
0x180022b99  add     rsp, 80h
0x180022ba0  pop     r15
0x180022ba2  pop     r14
0x180022ba4  pop     rdi
0x180022ba5  pop     rsi
0x180022ba6  pop     rbp
0x180022ba7  retn
```
