# KsGetImageNameAndResourceId

- ea: `0x1800129e0`
- end: `0x180012c14`
- name: `KsGetImageNameAndResourceId`
- size: `564`
- prototype: `NTSTATUS __stdcall(HANDLE RegKey, PUNICODE_STRING ImageName, PULONG_PTR ResourceId, PULONG ValueType)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800395f0`

## callees

- `0x180006f80`
- `0x1800129e0`
- `0x18001a000`
- `0x18003979c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180012bed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180012bed`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012acc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012acc`
- `ntoskrnl!ExAllocatePool2` at `0x180012a68`
- `ntoskrnl!ExAllocatePool2` at `0x180012a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x180012adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180012bcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180012adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180012bcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180012b77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180012b77`

## string_xrefs

- `0x180012a7c`: `\SystemRoot\system32\drivers\`

## pseudocode

```c
NTSTATUS __stdcall KsGetImageNameAndResourceId(
        HANDLE RegKey,
        PUNICODE_STRING ImageName,
        PULONG_PTR ResourceId,
        PULONG ValueType)
{
  int Value; // ebx
  wchar_t *Pool2; // rax
  WCHAR *v10; // rdi
  __int64 v11; // r10
  __int64 v12; // rax
  PVOID PoolWithTag; // rdi
  __int64 v15[3]; // [rsp+30h] [rbp-18h] BYREF

  LODWORD(v15[0]) = 0;
  *ImageName = 0;
  *ResourceId = 0;
  Value = KspRegQueryValue(RegKey, (__int64)v15);
  if ( Value != -2147483643 )
    goto LABEL_11;
  if ( LODWORD(v15[0]) == 1 )
  {
    Pool2 = (wchar_t *)ExAllocatePool2(256, 60, 1953715019);
    v10 = Pool2;
    if ( Pool2 )
    {
      Value = RtlStringCbCopyW(Pool2, 0x3Cu, L"\\SystemRoot\\system32\\drivers\\");
      if ( Value >= 0 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)(v11 + 2 * v12) );
        Value = KspRegQueryValue(RegKey, 0);
        if ( Value >= 0 )
        {
          RtlInitUnicodeString(ImageName, v10);
LABEL_12:
          Value = KspRegQueryValue(RegKey, (__int64)ValueType);
          if ( Value >= 0 && *ValueType == 4 )
            return Value;
          Value = KspRegQueryValue(RegKey, (__int64)ValueType);
          if ( Value != -2147483643 )
          {
LABEL_21:
            if ( Value >= 0 )
              return Value;
            goto LABEL_22;
          }
          if ( *ValueType == 1 )
          {
            PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0, 0x7473534Bu);
            if ( PoolWithTag )
            {
              Value = KspRegQueryValue(RegKey, 0);
              if ( Value >= 0 )
              {
                *ResourceId = (unsigned __int64)PoolWithTag;
                return Value;
              }
              ExFreePoolWithTag(PoolWithTag, 0);
              goto LABEL_22;
            }
            Value = -1073741670;
            goto LABEL_21;
          }
          goto LABEL_25;
        }
      }
      ExFreePoolWithTag(v10, 0);
    }
    else
    {
      Value = -1073741670;
    }
LABEL_11:
    if ( Value < 0 )
      goto LABEL_22;
    goto LABEL_12;
  }
LABEL_25:
  Value = -1073741811;
LABEL_22:
  if ( ImageName->Buffer )
    RtlFreeUnicodeString(ImageName);
  return Value;
}

```

## disassembly

```asm
0x1800129e0  push    rbp
0x1800129e2  push    rbx
0x1800129e3  push    rsi
0x1800129e4  push    rdi
0x1800129e5  push    r12
0x1800129e7  push    r13
0x1800129e9  push    r14
0x1800129eb  push    r15
0x1800129ed  mov     rbp, rsp
0x1800129f0  sub     rsp, 48h
0x1800129f4  xor     r13d, r13d
0x1800129f7  lea     rax, [rbp+var_18]
0x1800129fb  xorps   xmm0, xmm0
0x1800129fe  mov     dword ptr [rbp+var_18], r13d
0x180012a02  movups  xmmword ptr [rdx], xmm0
0x180012a05  mov     [r8], r13
0x180012a08  mov     rsi, r9
0x180012a0b  mov     r12, r8
0x180012a0e  mov     dword ptr [rbp+NumberOfBytes], r13d
0x180012a12  mov     r14, rdx
0x180012a15  mov     [rsp+48h+var_28], rax; __int64
0x180012a1a  xor     r8d, r8d
0x180012a1d  lea     r9, [rbp+NumberOfBytes]
0x180012a21  lea     rdx, aImage; "Image"
0x180012a28  mov     r15, rcx
0x180012a2b  call    KspRegQueryValue
0x180012a30  mov     ebx, eax
0x180012a32  cmp     eax, 80000005h
0x180012a37  jnz     loc_180012AF9
0x180012a3d  cmp     dword ptr [rbp+var_18], 1
0x180012a41  jnz     loc_180012C0D
0x180012a47  mov     eax, dword ptr [rbp+NumberOfBytes]
0x180012a4a  add     eax, 3Ch ; '<'
0x180012a4d  cmp     eax, 3Ch ; '<'
0x180012a50  jb      loc_180012AF4
0x180012a56  mov     r8d, 7473534Bh
0x180012a5c  mov     edx, eax
0x180012a5e  mov     ecx, 100h
0x180012a63  mov     dword ptr [rbp+NumberOfBytes], eax
0x180012a66  mov     ebx, eax
0x180012a68  call    cs:__imp_ExAllocatePool2
0x180012a6f  nop     dword ptr [rax+rax+00h]
0x180012a74  mov     rdi, rax
0x180012a77  test    rax, rax
0x180012a7a  jz      short loc_180012AED
0x180012a7c  lea     r10, aSystemrootSyst; "\\SystemRoot\\system32\\drivers\\"
0x180012a83  mov     edx, ebx; cbDest
0x180012a85  mov     r8, r10; pszSrc
0x180012a88  mov     rcx, rax; pszDest
0x180012a8b  call    RtlStringCbCopyW
0x180012a90  mov     ebx, eax
0x180012a92  test    eax, eax
0x180012a94  js      short loc_180012ADA
0x180012a96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a9a  inc     rax
0x180012a9d  cmp     [r10+rax*2], r13w
0x180012aa2  jnz     short loc_180012A9A
0x180012aa4  lea     r8, [rdi+rax*2]
0x180012aa8  mov     [rsp+48h+var_28], r13; __int64
0x180012aad  lea     r9, [rbp+NumberOfBytes]
0x180012ab1  mov     rcx, r15; KeyHandle
0x180012ab4  lea     rdx, aImage; "Image"
0x180012abb  call    KspRegQueryValue
0x180012ac0  mov     ebx, eax
0x180012ac2  test    eax, eax
0x180012ac4  js      short loc_180012ADA
0x180012ac6  mov     rdx, rdi; SourceString
0x180012ac9  mov     rcx, r14; DestinationString
0x180012acc  call    cs:__imp_RtlInitUnicodeString
0x180012ad3  nop     dword ptr [rax+rax+00h]
0x180012ad8  jmp     short loc_180012B01
0x180012ada  xor     edx, edx; Tag
0x180012adc  mov     rcx, rdi; P
0x180012adf  call    cs:__imp_ExFreePoolWithTag
0x180012ae6  nop     dword ptr [rax+rax+00h]
0x180012aeb  jmp     short loc_180012AF9
0x180012aed  mov     ebx, 0C000009Ah
0x180012af2  jmp     short loc_180012AF9
0x180012af4  mov     ebx, 0C0000095h
0x180012af9  test    ebx, ebx
0x180012afb  js      loc_180012BE4
0x180012b01  lea     r9, [rbp+NumberOfBytes]
0x180012b05  mov     dword ptr [rbp+NumberOfBytes], 4
0x180012b0c  mov     r8, r12
0x180012b0f  mov     [rsp+48h+var_28], rsi; __int64
0x180012b14  lea     rdx, aResourceid; "ResourceId"
0x180012b1b  mov     rcx, r15; KeyHandle
0x180012b1e  call    KspRegQueryValue
0x180012b23  mov     ebx, eax
0x180012b25  test    eax, eax
0x180012b27  js      short loc_180012B32
0x180012b29  cmp     dword ptr [rsi], 4
0x180012b2c  jz      loc_180012BF9
0x180012b32  lea     r9, [rbp+NumberOfBytes]
0x180012b36  mov     dword ptr [rbp+NumberOfBytes], r13d
0x180012b3a  xor     r8d, r8d
0x180012b3d  mov     [rsp+48h+var_28], rsi; __int64
0x180012b42  lea     rdx, aResourceid; "ResourceId"
0x180012b49  mov     rcx, r15; KeyHandle
0x180012b4c  call    KspRegQueryValue
0x180012b51  mov     ebx, eax
0x180012b53  cmp     eax, 80000005h
0x180012b58  jnz     loc_180012BE0
0x180012b5e  cmp     dword ptr [rsi], 1
0x180012b61  jnz     loc_180012C0D
0x180012b67  mov     ebx, dword ptr [rbp+NumberOfBytes]
0x180012b6a  mov     r8d, 7473534Bh; Tag
0x180012b70  mov     edx, ebx; NumberOfBytes
0x180012b72  mov     ecx, 401h; PoolType
0x180012b77  call    cs:__imp_ExAllocatePoolWithTag
0x180012b7e  nop     dword ptr [rax+rax+00h]
0x180012b83  mov     rdi, rax
0x180012b86  test    rax, rax
0x180012b89  jz      short loc_180012BDB
0x180012b8b  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x180012b92  jnz     short loc_180012BA1
0x180012b94  mov     r8d, ebx; Size
0x180012b97  xor     edx, edx; Val
0x180012b99  mov     rcx, rax; void *
0x180012b9c  call    memset
0x180012ba1  lea     r9, [rbp+NumberOfBytes]
0x180012ba5  mov     [rsp+48h+var_28], r13; __int64
0x180012baa  mov     r8, rdi
0x180012bad  lea     rdx, aResourceid; "ResourceId"
0x180012bb4  mov     rcx, r15; KeyHandle
0x180012bb7  call    KspRegQueryValue
0x180012bbc  mov     ebx, eax
0x180012bbe  test    eax, eax
0x180012bc0  js      short loc_180012BC8
0x180012bc2  mov     [r12], rdi
0x180012bc6  jmp     short loc_180012BF9
0x180012bc8  xor     edx, edx; Tag
0x180012bca  mov     rcx, rdi; P
0x180012bcd  call    cs:__imp_ExFreePoolWithTag
0x180012bd4  nop     dword ptr [rax+rax+00h]
0x180012bd9  jmp     short loc_180012BE4
0x180012bdb  mov     ebx, 0C000009Ah
0x180012be0  test    ebx, ebx
0x180012be2  jns     short loc_180012BF9
0x180012be4  cmp     [r14+8], r13
0x180012be8  jz      short loc_180012BF9
0x180012bea  mov     rcx, r14; UnicodeString
0x180012bed  call    cs:__imp_RtlFreeUnicodeString
0x180012bf4  nop     dword ptr [rax+rax+00h]
0x180012bf9  mov     eax, ebx
0x180012bfb  add     rsp, 48h
0x180012bff  pop     r15
0x180012c01  pop     r14
0x180012c03  pop     r13
0x180012c05  pop     r12
0x180012c07  pop     rdi
0x180012c08  pop     rsi
0x180012c09  pop     rbx
0x180012c0a  pop     rbp
0x180012c0b  retn
0x180012c0d  mov     ebx, 0C000000Dh
0x180012c12  jmp     short loc_180012BE4
```
