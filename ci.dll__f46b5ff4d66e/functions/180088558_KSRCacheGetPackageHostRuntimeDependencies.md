# KSRCacheGetPackageHostRuntimeDependencies

- ea: `0x180088558`
- end: `0x1800887eb`
- name: `KSRCacheGetPackageHostRuntimeDependencies`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007d8c8`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x180088558`
- `0x180088950`
- `0x180088adc`
- `0x180088ee8`
- `0x1800890c0`
- `0x180089194`
- `0x180089368`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800887b5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800887b5`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180088766`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180088766`
- `ntoskrnl!ZwClose` at `0x180088796`
- `ntoskrnl!ZwClose` at `0x180088796`
- `ntoskrnl!ZwEnumerateKey` at `0x1800886df`
- `ntoskrnl!ZwEnumerateKey` at `0x1800886df`

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
0x180088558  push    rbp
0x18008855a  push    rbx
0x18008855b  push    rsi
0x18008855c  push    rdi
0x18008855d  push    r12
0x18008855f  push    r14
0x180088561  push    r15
0x180088563  lea     rbp, [rsp-130h]
0x18008856b  sub     rsp, 230h
0x180088572  mov     rax, cs:__security_cookie
0x180088579  xor     rax, rsp
0x18008857c  mov     [rbp+160h+var_40], rax
0x180088583  xorps   xmm0, xmm0
0x180088586  mov     [rsp+260h+KeyHandle], 0
0x18008858f  xorps   xmm1, xmm1
0x180088592  mov     [rsp+260h+var_220], 220000h
0x18008859b  mov     r15, r8
0x18008859e  mov     rbx, rdx
0x1800885a1  mov     rsi, rcx
0x1800885a4  xor     edx, edx; Val
0x1800885a6  mov     r8d, 100h; Size
0x1800885ac  lea     rcx, [rbp+160h+var_140]; void *
0x1800885b0  movups  [rsp+260h+var_210], xmm0
0x1800885b5  mov     r12, r9
0x1800885b8  movups  [rsp+260h+var_200], xmm1
0x1800885bd  movups  [rbp+160h+var_1E0], xmm0
0x1800885c1  movups  xmmword ptr [rsp+260h+StringIn.Length], xmm1
0x1800885c6  call    memset
0x1800885cb  xor     eax, eax
0x1800885cd  lea     rdx, [rsp+260h+var_220]
0x1800885d2  xorps   xmm0, xmm0
0x1800885d5  mov     [rbp+160h+var_1B0], ax
0x1800885d9  mov     [rsp+260h+var_230], eax
0x1800885dd  mov     rcx, rbx
0x1800885e0  mov     [rsp+260h+var_22C], eax
0x1800885e4  xor     edi, edi
0x1800885e6  mov     [rbp+160h+var_188], ax
0x1800885ea  lea     rax, [rbp+160h+var_1D0]
0x1800885ee  mov     [rsp+260h+var_218], rax
0x1800885f3  movups  [rbp+160h+var_1D0], xmm0
0x1800885f7  movups  [rbp+160h+var_1C0], xmm0
0x1800885fb  movups  [rbp+160h+var_1A8], xmm0
0x1800885ff  movups  [rbp+160h+var_198], xmm0
0x180088603  call    KSRCachepGetUserDataId
0x180088608  mov     ebx, eax
0x18008860a  test    eax, eax
0x18008860c  js      loc_1800887A6
0x180088612  lea     rax, [rbp+160h+var_1A8]
0x180088616  mov     dword ptr [rsp+260h+var_210], 220000h
0x18008861e  lea     rdx, [rsp+260h+var_210]
0x180088623  mov     qword ptr [rsp+260h+var_210+8], rax
0x180088628  mov     rcx, rsi
0x18008862b  call    KSRCachepGetPackageDataId
0x180088630  mov     ebx, eax
0x180088632  test    eax, eax
0x180088634  js      loc_1800887A6
0x18008863a  lea     r8, [rsp+260h+KeyHandle]
0x18008863f  lea     rdx, [rsp+260h+var_220]
0x180088644  lea     rcx, [rsp+260h+var_210]
0x180088649  call    KSRCachepGetDependencyGraphIndexKey
0x18008864e  mov     r14, [rsp+260h+KeyHandle]
0x180088653  mov     ebx, eax
0x180088655  cmp     eax, 0C0000034h
0x18008865a  jnz     short loc_180088666
0x18008865c  xor     ebx, ebx
0x18008865e  mov     [r15], ebx
0x180088661  jmp     loc_18008878E
0x180088666  test    eax, eax
0x180088668  js      loc_18008878E
0x18008866e  lea     rdx, [rsp+260h+var_230]
0x180088673  mov     rcx, r14; KeyHandle
0x180088676  call    KSRCachepGetSubKeyCount
0x18008867b  mov     ebx, eax
0x18008867d  test    eax, eax
0x18008867f  js      loc_18008878E
0x180088685  mov     esi, [rsp+260h+var_230]
0x180088689  test    esi, esi
0x18008868b  jnz     short loc_180088694
0x18008868d  xor     ebx, ebx
0x18008868f  jmp     loc_18008878E
0x180088694  cmp     [r15], esi
0x180088697  jb      loc_180088786
0x18008869d  test    r12, r12
0x1800886a0  jz      loc_180088786
0x1800886a6  lea     rax, [rbp+160h+var_140]
0x1800886aa  mov     [rsp+260h+StringIn.Buffer], rax
0x1800886af  mov     eax, 100h
0x1800886b4  mov     [rsp+260h+StringIn.MaximumLength], ax
0x1800886b9  cmp     edi, esi
0x1800886bb  jnb     loc_180088781
0x1800886c1  lea     rax, [rsp+260h+var_22C]
0x1800886c6  xor     r8d, r8d; KeyInformationClass
0x1800886c9  mov     [rsp+260h+ResultLength], rax; ResultLength
0x1800886ce  lea     r9, [rbp+160h+KeyInformation]; KeyInformation
0x1800886d2  mov     edx, edi; Index
0x1800886d4  mov     [rsp+260h+Length], 3Ah ; ':'; Length
0x1800886dc  mov     rcx, r14; KeyHandle
0x1800886df  call    cs:__imp_ZwEnumerateKey
0x1800886e6  nop     dword ptr [rax+rax+00h]
0x1800886eb  mov     ebx, eax
0x1800886ed  cmp     eax, 8000001Ah
0x1800886f2  jz      loc_18008877F
0x1800886f8  test    eax, eax
0x1800886fa  js      loc_18008878E
0x180088700  lea     rax, [rbp+160h+var_170]
0x180088704  mov     dword ptr [rsp+260h+var_200], 220000h
0x18008870c  mov     qword ptr [rbp+160h+var_1E0+8], rax
0x180088710  lea     rdx, [rsp+260h+var_200]
0x180088715  movzx   eax, [rbp+160h+var_174]
0x180088719  lea     rcx, [rbp+160h+var_1E0]
0x18008871d  mov     word ptr [rbp+160h+var_1E0], ax
0x180088721  mov     word ptr [rbp+160h+var_1E0+2], ax
0x180088725  lea     rax, [rbp+160h+var_1D0]
0x180088729  mov     qword ptr [rsp+260h+var_200+8], rax
0x18008872e  call    KSRCachepGetSupplierPackageDataId
0x180088733  mov     ebx, eax
0x180088735  test    eax, eax
0x180088737  js      short loc_18008878E
0x180088739  xor     eax, eax
0x18008873b  lea     rdx, [rsp+260h+StringIn]
0x180088740  lea     rcx, [rsp+260h+var_200]
0x180088745  mov     [rsp+260h+StringIn.Length], ax
0x18008874a  call    KSRCachepGetPackageFullNameFromPackageDataId
0x18008874f  mov     ebx, eax
0x180088751  test    eax, eax
0x180088753  js      short loc_18008878E
0x180088755  mov     r8d, edi
0x180088758  lea     rdx, [rsp+260h+StringIn]; StringIn
0x18008875d  shl     r8, 4
0x180088761  xor     ecx, ecx; Flags
0x180088763  add     r8, r12; StringOut
0x180088766  call    cs:__imp_RtlDuplicateUnicodeString
0x18008876d  nop     dword ptr [rax+rax+00h]
0x180088772  mov     ebx, eax
0x180088774  test    eax, eax
0x180088776  js      short loc_18008878E
0x180088778  inc     edi
0x18008877a  jmp     loc_1800886B9
0x18008877f  xor     ebx, ebx
0x180088781  mov     [r15], edi
0x180088784  jmp     short loc_18008878E
0x180088786  mov     ebx, 0C0000023h
0x18008878b  mov     [r15], esi
0x18008878e  test    r14, r14
0x180088791  jz      short loc_1800887A2
0x180088793  mov     rcx, r14; Handle
0x180088796  call    cs:__imp_ZwClose
0x18008879d  nop     dword ptr [rax+rax+00h]
0x1800887a2  test    ebx, ebx
0x1800887a4  jns     short loc_1800887C7
0x1800887a6  xor     esi, esi
0x1800887a8  test    edi, edi
0x1800887aa  jz      short loc_1800887C7
0x1800887ac  mov     ecx, esi
0x1800887ae  shl     rcx, 4
0x1800887b2  add     rcx, r12; UnicodeString
0x1800887b5  call    cs:__imp_RtlFreeUnicodeString
0x1800887bc  nop     dword ptr [rax+rax+00h]
0x1800887c1  inc     esi
0x1800887c3  cmp     esi, edi
0x1800887c5  jb      short loc_1800887AC
0x1800887c7  mov     eax, ebx
0x1800887c9  mov     rcx, [rbp+160h+var_40]
0x1800887d0  xor     rcx, rsp; StackCookie
0x1800887d3  call    __security_check_cookie
0x1800887d8  add     rsp, 230h
0x1800887df  pop     r15
0x1800887e1  pop     r14
0x1800887e3  pop     r12
0x1800887e5  pop     rdi
0x1800887e6  pop     rsi
0x1800887e7  pop     rbx
0x1800887e8  pop     rbp
0x1800887e9  retn
```
