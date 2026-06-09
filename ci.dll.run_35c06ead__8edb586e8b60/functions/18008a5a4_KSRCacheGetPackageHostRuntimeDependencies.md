# KSRCacheGetPackageHostRuntimeDependencies

- ea: `0x18008a5a4`
- end: `0x18008a837`
- name: `KSRCacheGetPackageHostRuntimeDependencies`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007f908`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18008a5a4`
- `0x18008a99c`
- `0x18008ab28`
- `0x18008af34`
- `0x18008b10c`
- `0x18008b1e0`
- `0x18008b3b4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18008a801`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18008a801`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18008a7b2`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18008a7b2`
- `ntoskrnl!ZwClose` at `0x18008a7e2`
- `ntoskrnl!ZwClose` at `0x18008a7e2`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a72b`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a72b`

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
0x18008a5a4  push    rbp
0x18008a5a6  push    rbx
0x18008a5a7  push    rsi
0x18008a5a8  push    rdi
0x18008a5a9  push    r12
0x18008a5ab  push    r14
0x18008a5ad  push    r15
0x18008a5af  lea     rbp, [rsp-130h]
0x18008a5b7  sub     rsp, 230h
0x18008a5be  mov     rax, cs:__security_cookie
0x18008a5c5  xor     rax, rsp
0x18008a5c8  mov     [rbp+160h+var_40], rax
0x18008a5cf  xorps   xmm0, xmm0
0x18008a5d2  mov     [rsp+260h+KeyHandle], 0
0x18008a5db  xorps   xmm1, xmm1
0x18008a5de  mov     [rsp+260h+var_220], 220000h
0x18008a5e7  mov     r15, r8
0x18008a5ea  mov     rbx, rdx
0x18008a5ed  mov     rsi, rcx
0x18008a5f0  xor     edx, edx; Val
0x18008a5f2  mov     r8d, 100h; Size
0x18008a5f8  lea     rcx, [rbp+160h+var_140]; void *
0x18008a5fc  movups  [rsp+260h+var_210], xmm0
0x18008a601  mov     r12, r9
0x18008a604  movups  [rsp+260h+var_200], xmm1
0x18008a609  movups  [rbp+160h+var_1E0], xmm0
0x18008a60d  movups  xmmword ptr [rsp+260h+StringIn.Length], xmm1
0x18008a612  call    memset
0x18008a617  xor     eax, eax
0x18008a619  lea     rdx, [rsp+260h+var_220]
0x18008a61e  xorps   xmm0, xmm0
0x18008a621  mov     [rbp+160h+var_1B0], ax
0x18008a625  mov     [rsp+260h+var_230], eax
0x18008a629  mov     rcx, rbx
0x18008a62c  mov     [rsp+260h+var_22C], eax
0x18008a630  xor     edi, edi
0x18008a632  mov     [rbp+160h+var_188], ax
0x18008a636  lea     rax, [rbp+160h+var_1D0]
0x18008a63a  mov     [rsp+260h+var_218], rax
0x18008a63f  movups  [rbp+160h+var_1D0], xmm0
0x18008a643  movups  [rbp+160h+var_1C0], xmm0
0x18008a647  movups  [rbp+160h+var_1A8], xmm0
0x18008a64b  movups  [rbp+160h+var_198], xmm0
0x18008a64f  call    KSRCachepGetUserDataId
0x18008a654  mov     ebx, eax
0x18008a656  test    eax, eax
0x18008a658  js      loc_18008A7F2
0x18008a65e  lea     rax, [rbp+160h+var_1A8]
0x18008a662  mov     dword ptr [rsp+260h+var_210], 220000h
0x18008a66a  lea     rdx, [rsp+260h+var_210]
0x18008a66f  mov     qword ptr [rsp+260h+var_210+8], rax
0x18008a674  mov     rcx, rsi
0x18008a677  call    KSRCachepGetPackageDataId
0x18008a67c  mov     ebx, eax
0x18008a67e  test    eax, eax
0x18008a680  js      loc_18008A7F2
0x18008a686  lea     r8, [rsp+260h+KeyHandle]
0x18008a68b  lea     rdx, [rsp+260h+var_220]
0x18008a690  lea     rcx, [rsp+260h+var_210]
0x18008a695  call    KSRCachepGetDependencyGraphIndexKey
0x18008a69a  mov     r14, [rsp+260h+KeyHandle]
0x18008a69f  mov     ebx, eax
0x18008a6a1  cmp     eax, 0C0000034h
0x18008a6a6  jnz     short loc_18008A6B2
0x18008a6a8  xor     ebx, ebx
0x18008a6aa  mov     [r15], ebx
0x18008a6ad  jmp     loc_18008A7DA
0x18008a6b2  test    eax, eax
0x18008a6b4  js      loc_18008A7DA
0x18008a6ba  lea     rdx, [rsp+260h+var_230]
0x18008a6bf  mov     rcx, r14; KeyHandle
0x18008a6c2  call    KSRCachepGetSubKeyCount
0x18008a6c7  mov     ebx, eax
0x18008a6c9  test    eax, eax
0x18008a6cb  js      loc_18008A7DA
0x18008a6d1  mov     esi, [rsp+260h+var_230]
0x18008a6d5  test    esi, esi
0x18008a6d7  jnz     short loc_18008A6E0
0x18008a6d9  xor     ebx, ebx
0x18008a6db  jmp     loc_18008A7DA
0x18008a6e0  cmp     [r15], esi
0x18008a6e3  jb      loc_18008A7D2
0x18008a6e9  test    r12, r12
0x18008a6ec  jz      loc_18008A7D2
0x18008a6f2  lea     rax, [rbp+160h+var_140]
0x18008a6f6  mov     [rsp+260h+StringIn.Buffer], rax
0x18008a6fb  mov     eax, 100h
0x18008a700  mov     [rsp+260h+StringIn.MaximumLength], ax
0x18008a705  cmp     edi, esi
0x18008a707  jnb     loc_18008A7CD
0x18008a70d  lea     rax, [rsp+260h+var_22C]
0x18008a712  xor     r8d, r8d; KeyInformationClass
0x18008a715  mov     [rsp+260h+ResultLength], rax; ResultLength
0x18008a71a  lea     r9, [rbp+160h+KeyInformation]; KeyInformation
0x18008a71e  mov     edx, edi; Index
0x18008a720  mov     [rsp+260h+Length], 3Ah ; ':'; Length
0x18008a728  mov     rcx, r14; KeyHandle
0x18008a72b  call    cs:__imp_ZwEnumerateKey
0x18008a732  nop     dword ptr [rax+rax+00h]
0x18008a737  mov     ebx, eax
0x18008a739  cmp     eax, 8000001Ah
0x18008a73e  jz      loc_18008A7CB
0x18008a744  test    eax, eax
0x18008a746  js      loc_18008A7DA
0x18008a74c  lea     rax, [rbp+160h+var_170]
0x18008a750  mov     dword ptr [rsp+260h+var_200], 220000h
0x18008a758  mov     qword ptr [rbp+160h+var_1E0+8], rax
0x18008a75c  lea     rdx, [rsp+260h+var_200]
0x18008a761  movzx   eax, [rbp+160h+var_174]
0x18008a765  lea     rcx, [rbp+160h+var_1E0]
0x18008a769  mov     word ptr [rbp+160h+var_1E0], ax
0x18008a76d  mov     word ptr [rbp+160h+var_1E0+2], ax
0x18008a771  lea     rax, [rbp+160h+var_1D0]
0x18008a775  mov     qword ptr [rsp+260h+var_200+8], rax
0x18008a77a  call    KSRCachepGetSupplierPackageDataId
0x18008a77f  mov     ebx, eax
0x18008a781  test    eax, eax
0x18008a783  js      short loc_18008A7DA
0x18008a785  xor     eax, eax
0x18008a787  lea     rdx, [rsp+260h+StringIn]
0x18008a78c  lea     rcx, [rsp+260h+var_200]
0x18008a791  mov     [rsp+260h+StringIn.Length], ax
0x18008a796  call    KSRCachepGetPackageFullNameFromPackageDataId
0x18008a79b  mov     ebx, eax
0x18008a79d  test    eax, eax
0x18008a79f  js      short loc_18008A7DA
0x18008a7a1  mov     r8d, edi
0x18008a7a4  lea     rdx, [rsp+260h+StringIn]; StringIn
0x18008a7a9  shl     r8, 4
0x18008a7ad  xor     ecx, ecx; Flags
0x18008a7af  add     r8, r12; StringOut
0x18008a7b2  call    cs:__imp_RtlDuplicateUnicodeString
0x18008a7b9  nop     dword ptr [rax+rax+00h]
0x18008a7be  mov     ebx, eax
0x18008a7c0  test    eax, eax
0x18008a7c2  js      short loc_18008A7DA
0x18008a7c4  inc     edi
0x18008a7c6  jmp     loc_18008A705
0x18008a7cb  xor     ebx, ebx
0x18008a7cd  mov     [r15], edi
0x18008a7d0  jmp     short loc_18008A7DA
0x18008a7d2  mov     ebx, 0C0000023h
0x18008a7d7  mov     [r15], esi
0x18008a7da  test    r14, r14
0x18008a7dd  jz      short loc_18008A7EE
0x18008a7df  mov     rcx, r14; Handle
0x18008a7e2  call    cs:__imp_ZwClose
0x18008a7e9  nop     dword ptr [rax+rax+00h]
0x18008a7ee  test    ebx, ebx
0x18008a7f0  jns     short loc_18008A813
0x18008a7f2  xor     esi, esi
0x18008a7f4  test    edi, edi
0x18008a7f6  jz      short loc_18008A813
0x18008a7f8  mov     ecx, esi
0x18008a7fa  shl     rcx, 4
0x18008a7fe  add     rcx, r12; UnicodeString
0x18008a801  call    cs:__imp_RtlFreeUnicodeString
0x18008a808  nop     dword ptr [rax+rax+00h]
0x18008a80d  inc     esi
0x18008a80f  cmp     esi, edi
0x18008a811  jb      short loc_18008A7F8
0x18008a813  mov     eax, ebx
0x18008a815  mov     rcx, [rbp+160h+var_40]
0x18008a81c  xor     rcx, rsp; StackCookie
0x18008a81f  call    __security_check_cookie
0x18008a824  add     rsp, 230h
0x18008a82b  pop     r15
0x18008a82d  pop     r14
0x18008a82f  pop     r12
0x18008a831  pop     rdi
0x18008a832  pop     rsi
0x18008a833  pop     rbx
0x18008a834  pop     rbp
0x18008a835  retn
```
