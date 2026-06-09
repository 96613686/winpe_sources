# KappxDeriveCatalogPathFromIdentity

- ea: `0x18007f6e4`
- end: `0x18007f902`
- name: `KappxDeriveCatalogPathFromIdentity`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007f908`
- `0x1800e2868`

## callees

- `0x18000ee30`
- `0x1800104b4`
- `0x18002c200`
- `0x18007f6e4`
- `0x18008a840`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007f736`
- `ntoskrnl!ExAllocatePool2` at `0x18007f7e9`
- `ntoskrnl!ExAllocatePool2` at `0x18007f736`
- `ntoskrnl!ExAllocatePool2` at `0x18007f7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f79b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f813`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f8e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f79b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f813`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007f8e2`

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
  v8 = RtlUnicodeStringCat((PUNICODE_STRING)pusResult, &stru_180030FF0);
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
    v8 = RtlUnicodeStringCat(&v19, &stru_180031000);
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
0x18007f6e4  push    rbp
0x18007f6e6  push    rbx
0x18007f6e7  push    rsi
0x18007f6e8  push    rdi
0x18007f6e9  push    r12
0x18007f6eb  push    r13
0x18007f6ed  push    r14
0x18007f6ef  push    r15
0x18007f6f1  mov     rbp, rsp
0x18007f6f4  sub     rsp, 48h
0x18007f6f8  mov     ebx, 208h
0x18007f6fd  xorps   xmm0, xmm0
0x18007f700  xorps   xmm1, xmm1
0x18007f703  mov     [rbp+Size], rbx
0x18007f707  movups  xmmword ptr [rbp+pusResult], xmm0
0x18007f70b  mov     r14, r8
0x18007f70e  mov     r12, rdx
0x18007f711  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x18007f715  mov     r15, rcx
0x18007f718  mov     esi, 5
0x18007f71d  mov     r13d, 58707041h
0x18007f723  test    esi, esi
0x18007f725  jz      loc_18007F839
0x18007f72b  mov     r8d, r13d
0x18007f72e  mov     rdx, rbx
0x18007f731  mov     ecx, 100h
0x18007f736  call    cs:__imp_ExAllocatePool2
0x18007f73d  nop     dword ptr [rax+rax+00h]
0x18007f742  mov     qword ptr [rbp+pusResult+8], rax
0x18007f746  test    rax, rax
0x18007f749  jz      loc_18007F86D
0x18007f74f  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007f753  mov     rcx, rbx; uOperand
0x18007f756  call    RtlUIntPtrToUShort
0x18007f75b  mov     ebx, eax
0x18007f75d  test    eax, eax
0x18007f75f  js      loc_18007F8D3
0x18007f765  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007f769  lea     r8, [rbp+Size]
0x18007f76d  mov     rdx, rdi
0x18007f770  mov     rcx, r15
0x18007f773  call    KSRCacheGetPackageLocation
0x18007f778  mov     ebx, eax
0x18007f77a  test    eax, eax
0x18007f77c  jns     short loc_18007F7B6
0x18007f77e  cmp     eax, 0C0000023h
0x18007f783  jnz     loc_18007F8D3
0x18007f789  mov     rbx, [rbp+Size]
0x18007f78d  mov     edx, r13d; Tag
0x18007f790  add     rbx, 3Eh ; '>'
0x18007f794  mov     rcx, rdi; P
0x18007f797  mov     [rbp+Size], rbx
0x18007f79b  call    cs:__imp_ExFreePoolWithTag
0x18007f7a2  nop     dword ptr [rax+rax+00h]
0x18007f7a7  dec     esi
0x18007f7a9  mov     qword ptr [rbp+pusResult+8], 0
0x18007f7b1  jmp     loc_18007F723
0x18007f7b6  mov     rdi, [rbp+Size]
0x18007f7ba  lea     rdx, [rbp+pusResult]; pusResult
0x18007f7be  lea     rcx, [rdi-2]; uOperand
0x18007f7c2  call    RtlUIntPtrToUShort
0x18007f7c7  mov     ebx, eax
0x18007f7c9  test    eax, eax
0x18007f7cb  js      loc_18007F8D3
0x18007f7d1  movzx   eax, [rbp+pusResult+2]
0x18007f7d5  lea     rbx, [rdi+3Eh]
0x18007f7d9  cmp     rbx, rax
0x18007f7dc  jbe     short loc_18007F839
0x18007f7de  mov     r8d, r13d
0x18007f7e1  mov     rdx, rbx
0x18007f7e4  mov     ecx, 100h
0x18007f7e9  call    cs:__imp_ExAllocatePool2
0x18007f7f0  nop     dword ptr [rax+rax+00h]
0x18007f7f5  mov     rsi, rax
0x18007f7f8  test    rax, rax
0x18007f7fb  jz      short loc_18007F86D
0x18007f7fd  mov     rdx, qword ptr [rbp+pusResult+8]; Src
0x18007f801  mov     r8, rdi; Size
0x18007f804  mov     rcx, rax; void *
0x18007f807  call    memmove
0x18007f80c  mov     rcx, qword ptr [rbp+pusResult+8]; P
0x18007f810  mov     edx, r13d; Tag
0x18007f813  call    cs:__imp_ExFreePoolWithTag
0x18007f81a  nop     dword ptr [rax+rax+00h]
0x18007f81f  lea     rdx, [rbp+pusResult+2]; pusResult
0x18007f823  mov     qword ptr [rbp+pusResult+8], rsi
0x18007f827  mov     rcx, rbx; uOperand
0x18007f82a  call    RtlUIntPtrToUShort
0x18007f82f  mov     ebx, eax
0x18007f831  test    eax, eax
0x18007f833  js      loc_18007F8D3
0x18007f839  lea     rdx, stru_180030FF0; SourceString
0x18007f840  lea     rcx, [rbp+pusResult]; DestinationString
0x18007f844  call    RtlUnicodeStringCat
0x18007f849  mov     ebx, eax
0x18007f84b  test    eax, eax
0x18007f84d  js      loc_18007F8D3
0x18007f853  movzx   eax, [rbp+pusResult]
0x18007f857  mov     rcx, [r14]; uOperand
0x18007f85a  add     eax, 8
0x18007f85d  add     rax, 2
0x18007f861  cmp     rax, rcx
0x18007f864  jbe     short loc_18007F874
0x18007f866  mov     ebx, 0C0000023h
0x18007f86b  jmp     short loc_18007F8D0
0x18007f86d  mov     ebx, 0C0000017h
0x18007f872  jmp     short loc_18007F8D3
0x18007f874  xor     eax, eax
0x18007f876  mov     [rbp+var_18.Buffer], r12
0x18007f87a  lea     rdx, [rbp+var_18.MaximumLength]; pusResult
0x18007f87e  mov     [rbp+var_18.Length], ax
0x18007f882  call    RtlUIntPtrToUShort
0x18007f887  mov     ebx, eax
0x18007f889  test    eax, eax
0x18007f88b  js      short loc_18007F8D3
0x18007f88d  lea     rdx, stru_180031000; SourceString
0x18007f894  lea     rcx, [rbp+var_18]; DestinationString
0x18007f898  call    RtlUnicodeStringCat
0x18007f89d  mov     ebx, eax
0x18007f89f  test    eax, eax
0x18007f8a1  js      short loc_18007F8D3
0x18007f8a3  lea     rdx, [rbp+pusResult]; SourceString
0x18007f8a7  lea     rcx, [rbp+var_18]; DestinationString
0x18007f8ab  call    RtlUnicodeStringCat
0x18007f8b0  mov     ebx, eax
0x18007f8b2  test    eax, eax
0x18007f8b4  js      short loc_18007F8D3
0x18007f8b6  movzx   r9d, [rbp+var_18.Length]
0x18007f8bb  mov     rax, [rbp+var_18.Buffer]
0x18007f8bf  mov     r8d, r9d
0x18007f8c2  shr     r8, 1
0x18007f8c5  xor     ecx, ecx
0x18007f8c7  mov     [rax+r8*2], cx
0x18007f8cc  lea     rax, [r9+2]
0x18007f8d0  mov     [r14], rax
0x18007f8d3  mov     rdi, qword ptr [rbp+pusResult+8]
0x18007f8d7  test    rdi, rdi
0x18007f8da  jz      short loc_18007F8EE
0x18007f8dc  mov     edx, r13d; Tag
0x18007f8df  mov     rcx, rdi; P
0x18007f8e2  call    cs:__imp_ExFreePoolWithTag
0x18007f8e9  nop     dword ptr [rax+rax+00h]
0x18007f8ee  mov     eax, ebx
0x18007f8f0  add     rsp, 48h
0x18007f8f4  pop     r15
0x18007f8f6  pop     r14
0x18007f8f8  pop     r13
0x18007f8fa  pop     r12
0x18007f8fc  pop     rdi
0x18007f8fd  pop     rsi
0x18007f8fe  pop     rbx
0x18007f8ff  pop     rbp
0x18007f900  retn
```
