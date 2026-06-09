# KappxDeriveCatalogPathFromIdentity

- ea: `0x18007d6a4`
- end: `0x18007d8c2`
- name: `KappxDeriveCatalogPathFromIdentity`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007d8c8`
- `0x1800e1968`

## callees

- `0x18000ee20`
- `0x180010554`
- `0x18002c040`
- `0x18007d6a4`
- `0x1800887f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007d6f6`
- `ntoskrnl!ExAllocatePool2` at `0x18007d7a9`
- `ntoskrnl!ExAllocatePool2` at `0x18007d6f6`
- `ntoskrnl!ExAllocatePool2` at `0x18007d7a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d7d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d7d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007d8a2`

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
  v8 = RtlUnicodeStringCat((PUNICODE_STRING)pusResult, &stru_180030F38);
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
    v8 = RtlUnicodeStringCat(&v19, &stru_180030F48);
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
0x18007d6a4  push    rbp
0x18007d6a6  push    rbx
0x18007d6a7  push    rsi
0x18007d6a8  push    rdi
0x18007d6a9  push    r12
0x18007d6ab  push    r13
0x18007d6ad  push    r14
0x18007d6af  push    r15
0x18007d6b1  mov     rbp, rsp
0x18007d6b4  sub     rsp, 48h
0x18007d6b8  mov     ebx, 208h
0x18007d6bd  xorps   xmm0, xmm0
0x18007d6c0  xorps   xmm1, xmm1
0x18007d6c3  mov     [rbp+Size], rbx
0x18007d6c7  movups  xmmword ptr [rbp+pusResult], xmm0
0x18007d6cb  mov     r14, r8
0x18007d6ce  mov     r12, rdx
0x18007d6d1  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x18007d6d5  mov     r15, rcx
0x18007d6d8  mov     esi, 5
0x18007d6dd  mov     r13d, 58707041h
0x18007d6e3  test    esi, esi
0x18007d6e5  jz      loc_18007D7F9
0x18007d6eb  mov     r8d, r13d
0x18007d6ee  mov     rdx, rbx
0x18007d6f1  mov     ecx, 100h
0x18007d6f6  call    cs:__imp_ExAllocatePool2
0x18007d6fd  nop     dword ptr [rax+rax+00h]
0x18007d702  mov     qword ptr [rbp+pusResult+8], rax
0x18007d706  test    rax, rax
0x18007d709  jz      loc_18007D82D
0x18007d70f  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007d713  mov     rcx, rbx; uOperand
0x18007d716  call    RtlUIntPtrToUShort
0x18007d71b  mov     ebx, eax
0x18007d71d  test    eax, eax
0x18007d71f  js      loc_18007D893
0x18007d725  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007d729  lea     r8, [rbp+Size]
0x18007d72d  mov     rdx, rdi
0x18007d730  mov     rcx, r15
0x18007d733  call    KSRCacheGetPackageLocation
0x18007d738  mov     ebx, eax
0x18007d73a  test    eax, eax
0x18007d73c  jns     short loc_18007D776
0x18007d73e  cmp     eax, 0C0000023h
0x18007d743  jnz     loc_18007D893
0x18007d749  mov     rbx, [rbp+Size]
0x18007d74d  mov     edx, r13d; Tag
0x18007d750  add     rbx, 3Eh ; '>'
0x18007d754  mov     rcx, rdi; P
0x18007d757  mov     [rbp+Size], rbx
0x18007d75b  call    cs:__imp_ExFreePoolWithTag
0x18007d762  nop     dword ptr [rax+rax+00h]
0x18007d767  dec     esi
0x18007d769  mov     qword ptr [rbp+pusResult+8], 0
0x18007d771  jmp     loc_18007D6E3
0x18007d776  mov     rdi, [rbp+Size]
0x18007d77a  lea     rdx, [rbp+pusResult]; pusResult
0x18007d77e  lea     rcx, [rdi-2]; uOperand
0x18007d782  call    RtlUIntPtrToUShort
0x18007d787  mov     ebx, eax
0x18007d789  test    eax, eax
0x18007d78b  js      loc_18007D893
0x18007d791  movzx   eax, [rbp+pusResult+2]
0x18007d795  lea     rbx, [rdi+3Eh]
0x18007d799  cmp     rbx, rax
0x18007d79c  jbe     short loc_18007D7F9
0x18007d79e  mov     r8d, r13d
0x18007d7a1  mov     rdx, rbx
0x18007d7a4  mov     ecx, 100h
0x18007d7a9  call    cs:__imp_ExAllocatePool2
0x18007d7b0  nop     dword ptr [rax+rax+00h]
0x18007d7b5  mov     rsi, rax
0x18007d7b8  test    rax, rax
0x18007d7bb  jz      short loc_18007D82D
0x18007d7bd  mov     rdx, qword ptr [rbp+pusResult+8]; Src
0x18007d7c1  mov     r8, rdi; Size
0x18007d7c4  mov     rcx, rax; void *
0x18007d7c7  call    memmove
0x18007d7cc  mov     rcx, qword ptr [rbp+pusResult+8]; P
0x18007d7d0  mov     edx, r13d; Tag
0x18007d7d3  call    cs:__imp_ExFreePoolWithTag
0x18007d7da  nop     dword ptr [rax+rax+00h]
0x18007d7df  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007d7e3  mov     qword ptr [rbp+pusResult+8], rsi
0x18007d7e7  mov     rcx, rbx; uOperand
0x18007d7ea  call    RtlUIntPtrToUShort
0x18007d7ef  mov     ebx, eax
0x18007d7f1  test    eax, eax
0x18007d7f3  js      loc_18007D893
0x18007d7f9  lea     rdx, stru_180030F38; SourceString
0x18007d800  lea     rcx, [rbp+pusResult]; DestinationString
0x18007d804  call    RtlUnicodeStringCat
0x18007d809  mov     ebx, eax
0x18007d80b  test    eax, eax
0x18007d80d  js      loc_18007D893
0x18007d813  movzx   eax, [rbp+pusResult]
0x18007d817  mov     rcx, [r14]; uOperand
0x18007d81a  add     eax, 8
0x18007d81d  add     rax, 2
0x18007d821  cmp     rax, rcx
0x18007d824  jbe     short loc_18007D834
0x18007d826  mov     ebx, 0C0000023h
0x18007d82b  jmp     short loc_18007D890
0x18007d82d  mov     ebx, 0C0000017h
0x18007d832  jmp     short loc_18007D893
0x18007d834  xor     eax, eax
0x18007d836  mov     [rbp+var_18.Buffer], r12
0x18007d83a  lea     rdx, [rbp+var_18.MaximumLength]; pusResult
0x18007d83e  mov     [rbp+var_18.Length], ax
0x18007d842  call    RtlUIntPtrToUShort
0x18007d847  mov     ebx, eax
0x18007d849  test    eax, eax
0x18007d84b  js      short loc_18007D893
0x18007d84d  lea     rdx, stru_180030F48; SourceString
0x18007d854  lea     rcx, [rbp+var_18]; DestinationString
0x18007d858  call    RtlUnicodeStringCat
0x18007d85d  mov     ebx, eax
0x18007d85f  test    eax, eax
0x18007d861  js      short loc_18007D893
0x18007d863  lea     rdx, [rbp+pusResult]; SourceString
0x18007d867  lea     rcx, [rbp+var_18]; DestinationString
0x18007d86b  call    RtlUnicodeStringCat
0x18007d870  mov     ebx, eax
0x18007d872  test    eax, eax
0x18007d874  js      short loc_18007D893
0x18007d876  movzx   r9d, [rbp+var_18.Length]
0x18007d87b  mov     rax, [rbp+var_18.Buffer]
0x18007d87f  mov     r8d, r9d
0x18007d882  shr     r8, 1
0x18007d885  xor     ecx, ecx
0x18007d887  mov     [rax+r8*2], cx
0x18007d88c  lea     rax, [r9+2]
0x18007d890  mov     [r14], rax
0x18007d893  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007d897  test    rdi, rdi
0x18007d89a  jz      short loc_18007D8AE
0x18007d89c  mov     edx, r13d; Tag
0x18007d89f  mov     rcx, rdi; P
0x18007d8a2  call    cs:__imp_ExFreePoolWithTag
0x18007d8a9  nop     dword ptr [rax+rax+00h]
0x18007d8ae  mov     eax, ebx
0x18007d8b0  add     rsp, 48h
0x18007d8b4  pop     r15
0x18007d8b6  pop     r14
0x18007d8b8  pop     r13
0x18007d8ba  pop     r12
0x18007d8bc  pop     rdi
0x18007d8bd  pop     rsi
0x18007d8be  pop     rbx
0x18007d8bf  pop     rbp
0x18007d8c0  retn
```
