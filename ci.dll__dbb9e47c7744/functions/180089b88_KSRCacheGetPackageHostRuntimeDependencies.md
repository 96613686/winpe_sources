# KSRCacheGetPackageHostRuntimeDependencies

- ea: `0x180089b88`
- end: `0x180089e1b`
- name: `KSRCacheGetPackageHostRuntimeDependencies`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007eef4`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x180089b88`
- `0x180089f80`
- `0x18008a10c`
- `0x18008a518`
- `0x18008a6f0`
- `0x18008a7c4`
- `0x18008a998`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180089de5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180089de5`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180089d96`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180089d96`
- `ntoskrnl!ZwClose` at `0x180089dc6`
- `ntoskrnl!ZwClose` at `0x180089dc6`
- `ntoskrnl!ZwEnumerateKey` at `0x180089d0f`
- `ntoskrnl!ZwEnumerateKey` at `0x180089d0f`

## pseudocode

```c
__int64 __fastcall KSRCacheGetPackageHostRuntimeDependencies(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        _DWORD *a3)
{
  int UserDataId; // ebx
  int DependencyGraphIndexKey; // eax
  HANDLE v8; // r14
  ULONG v10; // [rsp+34h] [rbp-CCh]
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING v13[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v14[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v15; // [rsp+B0h] [rbp-50h]
  _OWORD v16[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v17; // [rsp+D8h] [rbp-28h]
  _BYTE v18[256]; // [rsp+120h] [rbp+20h] BYREF

  KeyHandle = 0;
  v12[0] = 2228224;
  memset(v13, 0, sizeof(v13));
  memset(v18, 0, sizeof(v18));
  v15 = 0;
  v10 = 0;
  v17 = 0;
  v12[1] = v14;
  memset(v14, 0, sizeof(v14));
  memset(v16, 0, sizeof(v16));
  UserDataId = KSRCachepGetUserDataId(a2, (__int64)v12);
  if ( UserDataId >= 0 )
  {
    *(_DWORD *)&v13[0].Length = 2228224;
    v13[0].Buffer = (PWSTR)v16;
    UserDataId = KSRCachepGetPackageDataId(a1, (__int64)v13);
    if ( UserDataId >= 0 )
    {
      DependencyGraphIndexKey = KSRCachepGetDependencyGraphIndexKey(v13, v12, &KeyHandle);
      v8 = KeyHandle;
      UserDataId = DependencyGraphIndexKey;
      if ( DependencyGraphIndexKey == -1073741772 )
      {
        UserDataId = 0;
        *a3 = 0;
      }
      else if ( DependencyGraphIndexKey >= 0 )
      {
        UserDataId = KSRCachepGetSubKeyCount(KeyHandle);
        if ( UserDataId >= 0 )
          UserDataId = 0;
      }
      if ( v8 )
        ZwClose(v8);
    }
  }
  return (unsigned int)UserDataId;
}

```

## disassembly

```asm
0x180089b88  push    rbp
0x180089b8a  push    rbx
0x180089b8b  push    rsi
0x180089b8c  push    rdi
0x180089b8d  push    r12
0x180089b8f  push    r14
0x180089b91  push    r15
0x180089b93  lea     rbp, [rsp-130h]
0x180089b9b  sub     rsp, 230h
0x180089ba2  mov     rax, cs:__security_cookie
0x180089ba9  xor     rax, rsp
0x180089bac  mov     [rbp+160h+var_40], rax
0x180089bb3  xorps   xmm0, xmm0
0x180089bb6  mov     [rsp+260h+KeyHandle], 0
0x180089bbf  xorps   xmm1, xmm1
0x180089bc2  mov     [rsp+260h+var_220], 220000h
0x180089bcb  mov     r15, r8
0x180089bce  mov     rbx, rdx
0x180089bd1  mov     rsi, rcx
0x180089bd4  xor     edx, edx; Val
0x180089bd6  mov     r8d, 100h; Size
0x180089bdc  lea     rcx, [rbp+160h+var_140]; void *
0x180089be0  movups  [rsp+260h+var_210], xmm0
0x180089be5  mov     r12, r9
0x180089be8  movups  [rsp+260h+var_200], xmm1
0x180089bed  movups  [rbp+160h+var_1E0], xmm0
0x180089bf1  movups  xmmword ptr [rsp+260h+StringIn.Length], xmm1
0x180089bf6  call    memset
0x180089bfb  xor     eax, eax
0x180089bfd  lea     rdx, [rsp+260h+var_220]
0x180089c02  xorps   xmm0, xmm0
0x180089c05  mov     [rbp+160h+var_1B0], ax
0x180089c09  mov     [rsp+260h+var_230], eax
0x180089c0d  mov     rcx, rbx
0x180089c10  mov     [rsp+260h+var_22C], eax
0x180089c14  xor     edi, edi
0x180089c16  mov     [rbp+160h+var_188], ax
0x180089c1a  lea     rax, [rbp+160h+var_1D0]
0x180089c1e  mov     [rsp+260h+var_218], rax
0x180089c23  movups  [rbp+160h+var_1D0], xmm0
0x180089c27  movups  [rbp+160h+var_1C0], xmm0
0x180089c2b  movups  [rbp+160h+var_1A8], xmm0
0x180089c2f  movups  [rbp+160h+var_198], xmm0
0x180089c33  call    KSRCachepGetUserDataId
0x180089c38  mov     ebx, eax
0x180089c3a  test    eax, eax
0x180089c3c  js      loc_180089DD6
0x180089c42  lea     rax, [rbp+160h+var_1A8]
0x180089c46  mov     dword ptr [rsp+260h+var_210], 220000h
0x180089c4e  lea     rdx, [rsp+260h+var_210]
0x180089c53  mov     qword ptr [rsp+260h+var_210+8], rax
0x180089c58  mov     rcx, rsi
0x180089c5b  call    KSRCachepGetPackageDataId
0x180089c60  mov     ebx, eax
0x180089c62  test    eax, eax
0x180089c64  js      loc_180089DD6
0x180089c6a  lea     r8, [rsp+260h+KeyHandle]
0x180089c6f  lea     rdx, [rsp+260h+var_220]
0x180089c74  lea     rcx, [rsp+260h+var_210]
0x180089c79  call    KSRCachepGetDependencyGraphIndexKey
0x180089c7e  mov     r14, [rsp+260h+KeyHandle]
0x180089c83  mov     ebx, eax
0x180089c85  cmp     eax, 0C0000034h
0x180089c8a  jnz     short loc_180089C96
0x180089c8c  xor     ebx, ebx
0x180089c8e  mov     [r15], ebx
0x180089c91  jmp     loc_180089DBE
0x180089c96  test    eax, eax
0x180089c98  js      loc_180089DBE
0x180089c9e  lea     rdx, [rsp+260h+var_230]
0x180089ca3  mov     rcx, r14; KeyHandle
0x180089ca6  call    KSRCachepGetSubKeyCount
0x180089cab  mov     ebx, eax
0x180089cad  test    eax, eax
0x180089caf  js      loc_180089DBE
0x180089cb5  mov     esi, [rsp+260h+var_230]
0x180089cb9  test    esi, esi
0x180089cbb  jnz     short loc_180089CC4
0x180089cbd  xor     ebx, ebx
0x180089cbf  jmp     loc_180089DBE
0x180089cc4  cmp     [r15], esi
0x180089cc7  jb      loc_180089DB6
0x180089ccd  test    r12, r12
0x180089cd0  jz      loc_180089DB6
0x180089cd6  lea     rax, [rbp+160h+var_140]
0x180089cda  mov     [rsp+260h+StringIn.Buffer], rax
0x180089cdf  mov     eax, 100h
0x180089ce4  mov     [rsp+260h+StringIn.MaximumLength], ax
0x180089ce9  cmp     edi, esi
0x180089ceb  jnb     loc_180089DB1
0x180089cf1  lea     rax, [rsp+260h+var_22C]
0x180089cf6  xor     r8d, r8d; KeyInformationClass
0x180089cf9  mov     [rsp+260h+ResultLength], rax; ResultLength
0x180089cfe  lea     r9, [rbp+160h+KeyInformation]; KeyInformation
0x180089d02  mov     edx, edi; Index
0x180089d04  mov     [rsp+260h+Length], 3Ah ; ':'; Length
0x180089d0c  mov     rcx, r14; KeyHandle
0x180089d0f  call    cs:__imp_ZwEnumerateKey
0x180089d16  nop     dword ptr [rax+rax+00h]
0x180089d1b  mov     ebx, eax
0x180089d1d  cmp     eax, 8000001Ah
0x180089d22  jz      loc_180089DAF
0x180089d28  test    eax, eax
0x180089d2a  js      loc_180089DBE
0x180089d30  lea     rax, [rbp+160h+var_170]
0x180089d34  mov     dword ptr [rsp+260h+var_200], 220000h
0x180089d3c  mov     qword ptr [rbp+160h+var_1E0+8], rax
0x180089d40  lea     rdx, [rsp+260h+var_200]
0x180089d45  movzx   eax, [rbp+160h+var_174]
0x180089d49  lea     rcx, [rbp+160h+var_1E0]
0x180089d4d  mov     word ptr [rbp+160h+var_1E0], ax
0x180089d51  mov     word ptr [rbp+160h+var_1E0+2], ax
0x180089d55  lea     rax, [rbp+160h+var_1D0]
0x180089d59  mov     qword ptr [rsp+260h+var_200+8], rax
0x180089d5e  call    KSRCachepGetSupplierPackageDataId
0x180089d63  mov     ebx, eax
0x180089d65  test    eax, eax
0x180089d67  js      short loc_180089DBE
0x180089d69  xor     eax, eax
0x180089d6b  lea     rdx, [rsp+260h+StringIn]
0x180089d70  lea     rcx, [rsp+260h+var_200]
0x180089d75  mov     [rsp+260h+StringIn.Length], ax
0x180089d7a  call    KSRCachepGetPackageFullNameFromPackageDataId
0x180089d7f  mov     ebx, eax
0x180089d81  test    eax, eax
0x180089d83  js      short loc_180089DBE
0x180089d85  mov     r8d, edi
0x180089d88  lea     rdx, [rsp+260h+StringIn]; StringIn
0x180089d8d  shl     r8, 4
0x180089d91  xor     ecx, ecx; Flags
0x180089d93  add     r8, r12; StringOut
0x180089d96  call    cs:__imp_RtlDuplicateUnicodeString
0x180089d9d  nop     dword ptr [rax+rax+00h]
0x180089da2  mov     ebx, eax
0x180089da4  test    eax, eax
0x180089da6  js      short loc_180089DBE
0x180089da8  inc     edi
0x180089daa  jmp     loc_180089CE9
0x180089daf  xor     ebx, ebx
0x180089db1  mov     [r15], edi
0x180089db4  jmp     short loc_180089DBE
0x180089db6  mov     ebx, 0C0000023h
0x180089dbb  mov     [r15], esi
0x180089dbe  test    r14, r14
0x180089dc1  jz      short loc_180089DD2
0x180089dc3  mov     rcx, r14; Handle
0x180089dc6  call    cs:__imp_ZwClose
0x180089dcd  nop     dword ptr [rax+rax+00h]
0x180089dd2  test    ebx, ebx
0x180089dd4  jns     short loc_180089DF7
0x180089dd6  xor     esi, esi
0x180089dd8  test    edi, edi
0x180089dda  jz      short loc_180089DF7
0x180089ddc  mov     ecx, esi
0x180089dde  shl     rcx, 4
0x180089de2  add     rcx, r12; UnicodeString
0x180089de5  call    cs:__imp_RtlFreeUnicodeString
0x180089dec  nop     dword ptr [rax+rax+00h]
0x180089df1  inc     esi
0x180089df3  cmp     esi, edi
0x180089df5  jb      short loc_180089DDC
0x180089df7  mov     eax, ebx
0x180089df9  mov     rcx, [rbp+160h+var_40]
0x180089e00  xor     rcx, rsp; StackCookie
0x180089e03  call    __security_check_cookie
0x180089e08  add     rsp, 230h
0x180089e0f  pop     r15
0x180089e11  pop     r14
0x180089e13  pop     r12
0x180089e15  pop     rdi
0x180089e16  pop     rsi
0x180089e17  pop     rbx
0x180089e18  pop     rbp
0x180089e19  retn
```
