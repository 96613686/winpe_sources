# shaHmacKiInitializeEx

- ea: `0x180001b90`
- end: `0x180001e0b`
- name: `shaHmacKiInitializeEx`
- size: `635`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, size_t Size)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001b90`
- `0x180002240`
- `0x1800022c0`
- `0x180002750`
- `0x180004c40`
- `0x1800054be`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d74`
- `bcrypt!BCryptCreateHash` at `0x180001db1`
- `bcrypt!BCryptCreateHash` at `0x180001db1`
- `bcrypt!BCryptEncrypt` at `0x180001cfb`
- `bcrypt!BCryptEncrypt` at `0x180001cfb`
- `bcrypt!BCryptDestroyKey` at `0x180001d33`
- `bcrypt!BCryptDestroyKey` at `0x180001d33`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001c52`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001c52`

## pseudocode

```c
__int64 __fastcall shaHmacKiInitializeEx(PUCHAR pbSecret, size_t Size, int a3, UCHAR **a4)
{
  ULONG cbSecret; // esi
  UCHAR *v7; // rbx
  NTSTATUS v8; // edi
  UCHAR *v9; // rax
  UCHAR *v10; // r14
  int v11; // ebp
  __int128 v12; // xmm0
  BCRYPT_KEY_HANDLE v13; // rcx
  UCHAR *v14; // r15
  NTSTATUS Hash; // ebx
  UCHAR *v16; // rax
  UCHAR *v17; // rdi
  ULONG pcbResult; // [rsp+50h] [rbp-98h] BYREF
  char v20; // [rsp+54h] [rbp-94h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-90h] BYREF
  UCHAR v22[16]; // [rsp+60h] [rbp-88h] BYREF
  UCHAR pbIV[16]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-68h] BYREF

  cbSecret = Size;
  if ( a3 )
  {
    HIBYTE(pcbResult) = a3;
    LOBYTE(pcbResult) = HIBYTE(a3);
    v20 = 85;
    BYTE1(pcbResult) = BYTE2(a3);
    BYTE2(pcbResult) = BYTE1(a3);
    fold_40_to_128(&pcbResult, v22);
    phKey = 0;
    v7 = 0;
    v8 = CheckCNG();
    if ( v8 >= 0 )
    {
      v9 = (UCHAR *)LocalAlloc(0, (unsigned int)cshAesKeyObjectSize);
      v7 = v9;
      if ( v9 )
      {
        v8 = BCryptGenerateSymmetricKey(cshAesAlgHandle, &phKey, v9, cshAesKeyObjectSize, pbSecret, cbSecret, 0);
        if ( v8 >= 0 )
        {
          v10 = v22;
          memset_0(v24, 0, cbSecret);
          v11 = 0;
          if ( cbSecret )
          {
            do
            {
              v12 = *(_OWORD *)v10;
              v13 = phKey;
              v14 = &v24[16 * v11];
              pcbResult = 16;
              *(_OWORD *)v14 = v12;
              *(_OWORD *)pbIV = 0;
              v8 = BCryptEncrypt(v13, v14, 0x10u, 0, pbIV, 0x10u, v14, 0x10u, &pcbResult, 0);
              if ( v8 < 0 )
                break;
              ++v11;
              v10 = v14;
            }
            while ( 16 * v11 < cbSecret );
          }
        }
      }
      else
      {
        v8 = -1073741801;
      }
    }
    if ( phKey )
      BCryptDestroyKey(phKey);
    if ( v7 )
      LocalFree(v7);
    if ( v8 < 0 )
      return (unsigned int)v8;
    pbSecret = v24;
  }
  Hash = CheckCNG();
  if ( Hash >= 0 )
  {
    if ( (unsigned int)cshHmacShaObjectSize >= 0xFFFFFFF0 )
    {
      return (unsigned int)-1073741811;
    }
    else
    {
      v16 = (UCHAR *)LocalAlloc(0, (unsigned int)(cshHmacShaObjectSize + 16));
      phKey = v16;
      v17 = v16;
      if ( v16 )
      {
        *(_QWORD *)v16 = 0;
        *((_QWORD *)v16 + 1) = v16 + 16;
        Hash = BCryptCreateHash(
                 cshHmacShaAlgHandle,
                 (BCRYPT_HASH_HANDLE *)v16,
                 v16 + 16,
                 cshHmacShaObjectSize,
                 pbSecret,
                 cbSecret,
                 0);
        if ( Hash < 0 )
          shaHmacFinish(&phKey);
        else
          *a4 = v17;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x180001b90  push    rbx
0x180001b92  push    rbp
0x180001b93  push    rsi
0x180001b94  push    rdi
0x180001b95  push    r12
0x180001b97  push    r13
0x180001b99  sub     rsp, 0B8h
0x180001ba0  mov     rax, cs:__security_cookie
0x180001ba7  xor     rax, rsp
0x180001baa  mov     [rsp+0E8h+var_48], rax
0x180001bb2  xor     r13d, r13d
0x180001bb5  mov     esi, edx
0x180001bb7  mov     r12, r9
0x180001bba  mov     rbp, rcx
0x180001bbd  test    r8d, r8d
0x180001bc0  jz      loc_180001D57
0x180001bc6  mov     eax, r8d
0x180001bc9  mov     byte ptr [rsp+0E8h+var_98+3], r8b
0x180001bce  shr     eax, 18h
0x180001bd1  lea     rdx, [rsp+0E8h+var_88]
0x180001bd6  mov     byte ptr [rsp+0E8h+var_98], al
0x180001bda  lea     rcx, [rsp+0E8h+var_98]
0x180001bdf  mov     eax, r8d
0x180001be2  mov     [rsp+0E8h+var_94], 55h ; 'U'
0x180001be7  shr     eax, 10h
0x180001bea  mov     byte ptr [rsp+0E8h+var_98+1], al
0x180001bee  mov     eax, r8d
0x180001bf1  shr     eax, 8
0x180001bf4  mov     byte ptr [rsp+0E8h+var_98+2], al
0x180001bf8  call    fold_40_to_128
0x180001bfd  mov     [rsp+0E8h+phKey], r13
0x180001c02  mov     ebx, r13d
0x180001c05  call    CheckCNG
0x180001c0a  mov     edi, eax
0x180001c0c  test    eax, eax
0x180001c0e  js      loc_180001D29
0x180001c14  mov     edx, cs:cshAesKeyObjectSize; uBytes
0x180001c1a  xor     ecx, ecx; uFlags
0x180001c1c  call    cs:__imp_LocalAlloc
0x180001c22  mov     rbx, rax
0x180001c25  test    rax, rax
0x180001c28  jz      loc_180001DF6
0x180001c2e  mov     r9d, cs:cshAesKeyObjectSize; cbKeyObject
0x180001c35  lea     rdx, [rsp+0E8h+phKey]; phKey
0x180001c3a  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x180001c41  mov     r8, rax; pbKeyObject
0x180001c44  mov     [rsp+0E8h+dwFlags], r13d; dwFlags
0x180001c49  mov     [rsp+0E8h+cbSecret], esi; cbSecret
0x180001c4d  mov     [rsp+0E8h+pbSecret], rbp; pbSecret
0x180001c52  call    cs:__imp_BCryptGenerateSymmetricKey
0x180001c58  mov     edi, eax
0x180001c5a  test    eax, eax
0x180001c5c  js      loc_180001D29
0x180001c62  mov     [rsp+0E8h+arg_10], r14
0x180001c6a  lea     rcx, [rsp+0E8h+var_68]; void *
0x180001c72  mov     r8d, esi; Size
0x180001c75  lea     r14, [rsp+0E8h+var_88]
0x180001c7a  xor     edx, edx; Val
0x180001c7c  call    memset_0
0x180001c81  mov     ebp, r13d
0x180001c84  test    esi, esi
0x180001c86  jz      loc_180001D21
0x180001c8c  mov     [rsp+0E8h+var_38], r15
0x180001c94  movups  xmm0, xmmword ptr [r14]
0x180001c98  mov     rcx, [rsp+0E8h+phKey]; hKey
0x180001c9d  lea     r15, [rsp+0E8h+var_68]
0x180001ca5  mov     [rsp+0E8h+var_A0], r13d; dwFlags
0x180001caa  mov     eax, ebp
0x180001cac  shl     eax, 4
0x180001caf  xorps   xmm1, xmm1
0x180001cb2  add     r15, rax
0x180001cb5  mov     [rsp+0E8h+var_98], 10h
0x180001cbd  lea     rax, [rsp+0E8h+var_98]
0x180001cc2  xor     r9d, r9d; pPaddingInfo
0x180001cc5  mov     [rsp+0E8h+pcbResult], rax; pcbResult
0x180001cca  mov     r8d, 10h; cbInput
0x180001cd0  mov     [rsp+0E8h+cbOutput], 10h; cbOutput
0x180001cd8  lea     rax, [rsp+0E8h+pbIV]
0x180001cdd  mov     qword ptr [rsp+0E8h+dwFlags], r15; pbOutput
0x180001ce2  mov     rdx, r15; pbInput
0x180001ce5  mov     [rsp+0E8h+cbSecret], 10h; cbIV
0x180001ced  mov     [rsp+0E8h+pbSecret], rax; pbIV
0x180001cf2  movups  xmmword ptr [r15], xmm0
0x180001cf6  movups  xmmword ptr [rsp+0E8h+pbIV], xmm1
0x180001cfb  call    cs:__imp_BCryptEncrypt
0x180001d01  mov     edi, eax
0x180001d03  test    eax, eax
0x180001d05  js      short loc_180001D19
0x180001d07  inc     ebp
0x180001d09  mov     r14, r15
0x180001d0c  mov     eax, ebp
0x180001d0e  shl     eax, 4
0x180001d11  cmp     eax, esi
0x180001d13  jb      loc_180001C94
0x180001d19  mov     r15, [rsp+0E8h+var_38]
0x180001d21  mov     r14, [rsp+0E8h+arg_10]
0x180001d29  mov     rcx, [rsp+0E8h+phKey]; hKey
0x180001d2e  test    rcx, rcx
0x180001d31  jz      short loc_180001D39
0x180001d33  call    cs:__imp_BCryptDestroyKey
0x180001d39  test    rbx, rbx
0x180001d3c  jz      short loc_180001D47
0x180001d3e  mov     rcx, rbx; hMem
0x180001d41  call    cs:__imp_LocalFree
0x180001d47  test    edi, edi
0x180001d49  js      loc_180001E00
0x180001d4f  lea     rbp, [rsp+0E8h+var_68]
0x180001d57  call    CheckCNG
0x180001d5c  mov     ebx, eax
0x180001d5e  test    eax, eax
0x180001d60  js      short loc_180001DC1
0x180001d62  mov     eax, cs:cshHmacShaObjectSize
0x180001d68  add     eax, 10h
0x180001d6b  cmp     eax, 10h
0x180001d6e  jb      short loc_180001DE3
0x180001d70  mov     edx, eax; uBytes
0x180001d72  xor     ecx, ecx; uFlags
0x180001d74  call    cs:__imp_LocalAlloc
0x180001d7a  mov     [rsp+0E8h+phKey], rax
0x180001d7f  mov     rdi, rax
0x180001d82  test    rax, rax
0x180001d85  jz      short loc_180001E04
0x180001d87  mov     [rax], r13
0x180001d8a  lea     r8, [rax+10h]; pbHashObject
0x180001d8e  mov     [rax+8], r8
0x180001d92  mov     rdx, rax; phHash
0x180001d95  mov     r9d, cs:cshHmacShaObjectSize; cbHashObject
0x180001d9c  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x180001da3  mov     [rsp+0E8h+dwFlags], r13d; dwFlags
0x180001da8  mov     [rsp+0E8h+cbSecret], esi; cbSecret
0x180001dac  mov     [rsp+0E8h+pbSecret], rbp; pbSecret
0x180001db1  call    cs:__imp_BCryptCreateHash
0x180001db7  mov     ebx, eax
0x180001db9  test    eax, eax
0x180001dbb  js      short loc_180001DEA
0x180001dbd  mov     [r12], rdi
0x180001dc1  mov     eax, ebx
0x180001dc3  mov     rcx, [rsp+0E8h+var_48]
0x180001dcb  xor     rcx, rsp; StackCookie
0x180001dce  call    __security_check_cookie
0x180001dd3  add     rsp, 0B8h
0x180001dda  pop     r13
0x180001ddc  pop     r12
0x180001dde  pop     rdi
0x180001ddf  pop     rsi
0x180001de0  pop     rbp
0x180001de1  pop     rbx
0x180001de2  retn
0x180001de3  mov     ebx, 0C000000Dh
0x180001de8  jmp     short loc_180001DC1
0x180001dea  lea     rcx, [rsp+0E8h+phKey]
0x180001def  call    shaHmacFinish
0x180001df4  jmp     short loc_180001DC1
0x180001df6  mov     edi, 0C0000017h
0x180001dfb  jmp     loc_180001D29
0x180001e00  mov     eax, edi
0x180001e02  jmp     short loc_180001DC3
0x180001e04  mov     ebx, 0C000009Ah
0x180001e09  jmp     short loc_180001DC1
```
