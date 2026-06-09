# KappxDeriveCatalogPathFromIdentity

- ea: `0x18007ecd0`
- end: `0x18007eeee`
- name: `KappxDeriveCatalogPathFromIdentity`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007eef4`
- `0x1800e2958`

## callees

- `0x18000ee20`
- `0x1800104a4`
- `0x18002c080`
- `0x18007ecd0`
- `0x180089e24`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007ed22`
- `ntoskrnl!ExAllocatePool2` at `0x18007edd5`
- `ntoskrnl!ExAllocatePool2` at `0x18007ed22`
- `ntoskrnl!ExAllocatePool2` at `0x18007edd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ed87`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007edff`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007eece`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ed87`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007edff`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007eece`

## pseudocode

```c
__int64 __fastcall KappxDeriveCatalogPathFromIdentity(struct _UNICODE_STRING *a1, WCHAR *a2, UINT_PTR *a3)
{
  UINT_PTR v3; // rbx
  int i; // esi
  NTSTATUS v8; // ebx
  void *v9; // rdi
  int PackageLocation; // eax
  size_t v11; // rdi
  void *Pool2; // rax
  void *v13; // rsi
  UINT_PTR v14; // rcx
  unsigned __int64 v15; // rax
  __int64 Length; // r9
  USHORT pusResult[8]; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v19; // [rsp+30h] [rbp-18h] BYREF
  size_t Size; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 520;
  Size = 520;
  *(_OWORD *)pusResult = 0;
  v19 = 0;
  for ( i = 5; i; --i )
  {
    *(_QWORD *)&pusResult[4] = ExAllocatePool2(256, v3, 1483763777);
    if ( !*(_QWORD *)&pusResult[4] )
      goto LABEL_15;
    v8 = RtlUIntPtrToUShort(v3, &pusResult[1]);
    if ( v8 < 0 )
      goto LABEL_21;
    v9 = *(void **)&pusResult[4];
    PackageLocation = KSRCacheGetPackageLocation(a1, *(void **)&pusResult[4], &Size);
    v8 = PackageLocation;
    if ( PackageLocation >= 0 )
    {
      v11 = Size;
      v8 = RtlUIntPtrToUShort(Size - 2, pusResult);
      if ( v8 < 0 )
        goto LABEL_21;
      if ( v11 + 62 > pusResult[1] )
      {
        Pool2 = (void *)ExAllocatePool2(256, v11 + 62, 1483763777);
        v13 = Pool2;
        if ( !Pool2 )
        {
LABEL_15:
          v8 = -1073741801;
          goto LABEL_21;
        }
        memmove(Pool2, *(const void **)&pusResult[4], v11);
        ExFreePoolWithTag(*(PVOID *)&pusResult[4], 0x58707041u);
        *(_QWORD *)&pusResult[4] = v13;
        v8 = RtlUIntPtrToUShort(v11 + 62, &pusResult[1]);
        if ( v8 < 0 )
          goto LABEL_21;
      }
      break;
    }
    if ( PackageLocation != -1073741789 )
      goto LABEL_21;
    v3 = Size + 62;
    Size += 62LL;
    ExFreePoolWithTag(v9, 0x58707041u);
    *(_QWORD *)&pusResult[4] = 0;
  }
  v8 = RtlUnicodeStringCat((PUNICODE_STRING)pusResult, &stru_180030FE8);
  if ( v8 < 0 )
    goto LABEL_21;
  v14 = *a3;
  v15 = (unsigned int)pusResult[0] + 8 + 2LL;
  if ( v15 > *a3 )
  {
    v8 = -1073741789;
LABEL_20:
    *a3 = v15;
    goto LABEL_21;
  }
  v19.Buffer = a2;
  v19.Length = 0;
  v8 = RtlUIntPtrToUShort(v14, &v19.MaximumLength);
  if ( v8 >= 0 )
  {
    v8 = RtlUnicodeStringCat(&v19, &stru_180030FF8);
    if ( v8 >= 0 )
    {
      v8 = RtlUnicodeStringCat(&v19, (PCUNICODE_STRING)pusResult);
      if ( v8 >= 0 )
      {
        Length = v19.Length;
        v19.Buffer[(unsigned __int64)v19.Length >> 1] = 0;
        v15 = Length + 2;
        goto LABEL_20;
      }
    }
  }
LABEL_21:
  if ( *(_QWORD *)&pusResult[4] )
    ExFreePoolWithTag(*(PVOID *)&pusResult[4], 0x58707041u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007ecd0  push    rbp
0x18007ecd2  push    rbx
0x18007ecd3  push    rsi
0x18007ecd4  push    rdi
0x18007ecd5  push    r12
0x18007ecd7  push    r13
0x18007ecd9  push    r14
0x18007ecdb  push    r15
0x18007ecdd  mov     rbp, rsp
0x18007ece0  sub     rsp, 48h
0x18007ece4  mov     ebx, 208h
0x18007ece9  xorps   xmm0, xmm0
0x18007ecec  xorps   xmm1, xmm1
0x18007ecef  mov     [rbp+Size], rbx
0x18007ecf3  movups  xmmword ptr [rbp+pusResult], xmm0
0x18007ecf7  mov     r14, r8
0x18007ecfa  mov     r12, rdx
0x18007ecfd  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x18007ed01  mov     r15, rcx
0x18007ed04  mov     esi, 5
0x18007ed09  mov     r13d, 58707041h
0x18007ed0f  test    esi, esi
0x18007ed11  jz      loc_18007EE25
0x18007ed17  mov     r8d, r13d
0x18007ed1a  mov     rdx, rbx
0x18007ed1d  mov     ecx, 100h
0x18007ed22  call    cs:__imp_ExAllocatePool2
0x18007ed29  nop     dword ptr [rax+rax+00h]
0x18007ed2e  mov     qword ptr [rbp+pusResult+8], rax
0x18007ed32  test    rax, rax
0x18007ed35  jz      loc_18007EE59
0x18007ed3b  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007ed3f  mov     rcx, rbx; uOperand
0x18007ed42  call    RtlUIntPtrToUShort
0x18007ed47  mov     ebx, eax
0x18007ed49  test    eax, eax
0x18007ed4b  js      loc_18007EEBF
0x18007ed51  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007ed55  lea     r8, [rbp+Size]
0x18007ed59  mov     rdx, rdi
0x18007ed5c  mov     rcx, r15
0x18007ed5f  call    KSRCacheGetPackageLocation
0x18007ed64  mov     ebx, eax
0x18007ed66  test    eax, eax
0x18007ed68  jns     short loc_18007EDA2
0x18007ed6a  cmp     eax, 0C0000023h
0x18007ed6f  jnz     loc_18007EEBF
0x18007ed75  mov     rbx, [rbp+Size]
0x18007ed79  mov     edx, r13d; Tag
0x18007ed7c  add     rbx, 3Eh ; '>'
0x18007ed80  mov     rcx, rdi; P
0x18007ed83  mov     [rbp+Size], rbx
0x18007ed87  call    cs:__imp_ExFreePoolWithTag
0x18007ed8e  nop     dword ptr [rax+rax+00h]
0x18007ed93  dec     esi
0x18007ed95  mov     qword ptr [rbp+pusResult+8], 0
0x18007ed9d  jmp     loc_18007ED0F
0x18007eda2  mov     rdi, [rbp+Size]
0x18007eda6  lea     rdx, [rbp+pusResult]; pusResult
0x18007edaa  lea     rcx, [rdi-2]; uOperand
0x18007edae  call    RtlUIntPtrToUShort
0x18007edb3  mov     ebx, eax
0x18007edb5  test    eax, eax
0x18007edb7  js      loc_18007EEBF
0x18007edbd  movzx   eax, [rbp+pusResult+2]
0x18007edc1  lea     rbx, [rdi+3Eh]
0x18007edc5  cmp     rbx, rax
0x18007edc8  jbe     short loc_18007EE25
0x18007edca  mov     r8d, r13d
0x18007edcd  mov     rdx, rbx
0x18007edd0  mov     ecx, 100h
0x18007edd5  call    cs:__imp_ExAllocatePool2
0x18007eddc  nop     dword ptr [rax+rax+00h]
0x18007ede1  mov     rsi, rax
0x18007ede4  test    rax, rax
0x18007ede7  jz      short loc_18007EE59
0x18007ede9  mov     rdx, qword ptr [rbp+pusResult+8]; Src
0x18007eded  mov     r8, rdi; Size
0x18007edf0  mov     rcx, rax; void *
0x18007edf3  call    memmove
0x18007edf8  mov     rcx, qword ptr [rbp+pusResult+8]; P
0x18007edfc  mov     edx, r13d; Tag
0x18007edff  call    cs:__imp_ExFreePoolWithTag
0x18007ee06  nop     dword ptr [rax+rax+00h]
0x18007ee0b  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007ee0f  mov     qword ptr [rbp+pusResult+8], rsi
0x18007ee13  mov     rcx, rbx; uOperand
0x18007ee16  call    RtlUIntPtrToUShort
0x18007ee1b  mov     ebx, eax
0x18007ee1d  test    eax, eax
0x18007ee1f  js      loc_18007EEBF
0x18007ee25  lea     rdx, stru_180030FE8; SourceString
0x18007ee2c  lea     rcx, [rbp+pusResult]; DestinationString
0x18007ee30  call    RtlUnicodeStringCat
0x18007ee35  mov     ebx, eax
0x18007ee37  test    eax, eax
0x18007ee39  js      loc_18007EEBF
0x18007ee3f  movzx   eax, [rbp+pusResult]
0x18007ee43  mov     rcx, [r14]; uOperand
0x18007ee46  add     eax, 8
0x18007ee49  add     rax, 2
0x18007ee4d  cmp     rax, rcx
0x18007ee50  jbe     short loc_18007EE60
0x18007ee52  mov     ebx, 0C0000023h
0x18007ee57  jmp     short loc_18007EEBC
0x18007ee59  mov     ebx, 0C0000017h
0x18007ee5e  jmp     short loc_18007EEBF
0x18007ee60  xor     eax, eax
0x18007ee62  mov     [rbp+var_18.Buffer], r12
0x18007ee66  lea     rdx, [rbp+var_18.MaximumLength]; pusResult
0x18007ee6a  mov     [rbp+var_18.Length], ax
0x18007ee6e  call    RtlUIntPtrToUShort
0x18007ee73  mov     ebx, eax
0x18007ee75  test    eax, eax
0x18007ee77  js      short loc_18007EEBF
0x18007ee79  lea     rdx, stru_180030FF8; SourceString
0x18007ee80  lea     rcx, [rbp+var_18]; DestinationString
0x18007ee84  call    RtlUnicodeStringCat
0x18007ee89  mov     ebx, eax
0x18007ee8b  test    eax, eax
0x18007ee8d  js      short loc_18007EEBF
0x18007ee8f  lea     rdx, [rbp+pusResult]; SourceString
0x18007ee93  lea     rcx, [rbp+var_18]; DestinationString
0x18007ee97  call    RtlUnicodeStringCat
0x18007ee9c  mov     ebx, eax
0x18007ee9e  test    eax, eax
0x18007eea0  js      short loc_18007EEBF
0x18007eea2  movzx   r9d, [rbp+var_18.Length]
0x18007eea7  mov     rax, [rbp+var_18.Buffer]
0x18007eeab  mov     r8d, r9d
0x18007eeae  shr     r8, 1
0x18007eeb1  xor     ecx, ecx
0x18007eeb3  mov     [rax+r8*2], cx
0x18007eeb8  lea     rax, [r9+2]
0x18007eebc  mov     [r14], rax
0x18007eebf  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007eec3  test    rdi, rdi
0x18007eec6  jz      short loc_18007EEDA
0x18007eec8  mov     edx, r13d; Tag
0x18007eecb  mov     rcx, rdi; P
0x18007eece  call    cs:__imp_ExFreePoolWithTag
0x18007eed5  nop     dword ptr [rax+rax+00h]
0x18007eeda  mov     eax, ebx
0x18007eedc  add     rsp, 48h
0x18007eee0  pop     r15
0x18007eee2  pop     r14
0x18007eee4  pop     r13
0x18007eee6  pop     r12
0x18007eee8  pop     rdi
0x18007eee9  pop     rsi
0x18007eeea  pop     rbx
0x18007eeeb  pop     rbp
0x18007eeec  retn
```
