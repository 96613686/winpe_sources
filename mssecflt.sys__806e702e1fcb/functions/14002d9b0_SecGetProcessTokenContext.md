# SecGetProcessTokenContext

- ea: `0x14002d9b0`
- end: `0x14002db5e`
- name: `SecGetProcessTokenContext`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c6b0`
- `0x140041e34`

## callees

- `0x140011650`
- `0x14002d86c`
- `0x14002d9b0`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14002da11`
- `ntoskrnl!SeQueryInformationToken` at `0x14002da3f`
- `ntoskrnl!SeQueryInformationToken` at `0x14002da69`
- `ntoskrnl!SeQueryInformationToken` at `0x14002daa4`
- `ntoskrnl!SeQueryInformationToken` at `0x14002da11`
- `ntoskrnl!SeQueryInformationToken` at `0x14002da3f`
- `ntoskrnl!SeQueryInformationToken` at `0x14002da69`
- `ntoskrnl!SeQueryInformationToken` at `0x14002daa4`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002db2c`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002db2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dacc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dafa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002db11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dacc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dafa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002db11`

## pseudocode

```c
__int64 __fastcall SecGetProcessTokenContext(__int64 a1, __int64 a2)
{
  NTSTATUS ProcessTokenAssertionContext; // edi
  int *v4; // rax
  __int64 v5; // rdx
  PVOID P; // [rsp+20h] [rbp-30h] BYREF
  PVOID TokenInformation; // [rsp+28h] [rbp-28h] BYREF
  PVOID v9; // [rsp+30h] [rbp-20h] BYREF
  PVOID v10; // [rsp+38h] [rbp-18h] BYREF

  TokenInformation = 0;
  P = 0;
  v9 = 0;
  v10 = 0;
  ProcessTokenAssertionContext = SecGetProcessTokenAssertionContext(a1, a2);
  if ( ProcessTokenAssertionContext >= 0 )
  {
    _mm_lfence();
    ProcessTokenAssertionContext = SeQueryInformationToken(*(PACCESS_TOKEN *)a2, TokenElevationType, &TokenInformation);
    if ( ProcessTokenAssertionContext >= 0 )
    {
      _mm_lfence();
      *(_DWORD *)(a2 + 44) = *(_DWORD *)TokenInformation;
      ProcessTokenAssertionContext = SeQueryInformationToken(*(PACCESS_TOKEN *)a2, TokenElevation, &P);
      if ( ProcessTokenAssertionContext >= 0 )
      {
        _mm_lfence();
        *(_DWORD *)(a2 + 48) = *(_DWORD *)P;
        ProcessTokenAssertionContext = SeQueryInformationToken(*(PACCESS_TOKEN *)a2, TokenStatistics, &v9);
        if ( ProcessTokenAssertionContext >= 0 )
        {
          _mm_lfence();
          v4 = (int *)v9;
          v5 = *((unsigned int *)v9 + 2);
          *(_QWORD *)(a2 + 56) = v5;
          *(_QWORD *)(a2 + 56) = v5 + ((__int64)v4[3] << 32);
          ProcessTokenAssertionContext = SeQueryInformationToken(*(PACCESS_TOKEN *)a2, TokenSource, &v10);
          if ( ProcessTokenAssertionContext >= 0 )
            *(_QWORD *)(a2 + 36) = *(_QWORD *)v10;
        }
      }
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( ProcessTokenAssertionContext < 0 )
  {
    _mm_lfence();
    if ( *(_QWORD *)a2 )
    {
      PsDereferencePrimaryToken(*(PACCESS_TOKEN *)a2);
      *(_QWORD *)a2 = 0;
    }
  }
  return (unsigned int)ProcessTokenAssertionContext;
}

```

## disassembly

```asm
0x14002d9b0  mov     [rsp-8+arg_10], rbx
0x14002d9b5  mov     [rsp-8+arg_18], rdi
0x14002d9ba  push    rbp
0x14002d9bb  mov     rbp, rsp
0x14002d9be  sub     rsp, 50h
0x14002d9c2  mov     rax, cs:__security_cookie
0x14002d9c9  xor     rax, rsp
0x14002d9cc  mov     [rbp+var_10], rax
0x14002d9d0  mov     rbx, rdx
0x14002d9d3  mov     [rbp+TokenInformation], 0
0x14002d9db  mov     [rbp+P], 0
0x14002d9e3  mov     [rbp+var_20], 0
0x14002d9eb  mov     [rbp+var_18], 0
0x14002d9f3  call    SecGetProcessTokenAssertionContext
0x14002d9f8  mov     edi, eax
0x14002d9fa  test    eax, eax
0x14002d9fc  js      loc_14002DAC1
0x14002da02  lfence
0x14002da05  mov     rcx, [rbx]; Token
0x14002da08  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14002da0c  mov     edx, 12h; TokenInformationClass
0x14002da11  call    cs:__imp_SeQueryInformationToken
0x14002da18  nop     dword ptr [rax+rax+00h]
0x14002da1d  mov     edi, eax
0x14002da1f  test    eax, eax
0x14002da21  js      loc_14002DAC1
0x14002da27  lfence
0x14002da2a  mov     rax, [rbp+TokenInformation]
0x14002da2e  lea     r8, [rbp+P]; TokenInformation
0x14002da32  mov     edx, 14h; TokenInformationClass
0x14002da37  mov     ecx, [rax]
0x14002da39  mov     [rbx+2Ch], ecx
0x14002da3c  mov     rcx, [rbx]; Token
0x14002da3f  call    cs:__imp_SeQueryInformationToken
0x14002da46  nop     dword ptr [rax+rax+00h]
0x14002da4b  mov     edi, eax
0x14002da4d  test    eax, eax
0x14002da4f  js      short loc_14002DAC1
0x14002da51  lfence
0x14002da54  mov     rax, [rbp+P]
0x14002da58  lea     r8, [rbp+var_20]; TokenInformation
0x14002da5c  mov     edx, 0Ah; TokenInformationClass
0x14002da61  mov     ecx, [rax]
0x14002da63  mov     [rbx+30h], ecx
0x14002da66  mov     rcx, [rbx]; Token
0x14002da69  call    cs:__imp_SeQueryInformationToken
0x14002da70  nop     dword ptr [rax+rax+00h]
0x14002da75  mov     edi, eax
0x14002da77  test    eax, eax
0x14002da79  js      short loc_14002DAC1
0x14002da7b  lfence
0x14002da7e  mov     rax, [rbp+var_20]
0x14002da82  lea     r8, [rbp+var_18]; TokenInformation
0x14002da86  mov     edx, [rax+8]
0x14002da89  mov     [rbx+38h], rdx
0x14002da8d  movsxd  rcx, dword ptr [rax+0Ch]
0x14002da91  shl     rcx, 20h
0x14002da95  add     rcx, rdx
0x14002da98  mov     edx, 7; TokenInformationClass
0x14002da9d  mov     [rbx+38h], rcx
0x14002daa1  mov     rcx, [rbx]; Token
0x14002daa4  call    cs:__imp_SeQueryInformationToken
0x14002daab  nop     dword ptr [rax+rax+00h]
0x14002dab0  mov     edi, eax
0x14002dab2  test    eax, eax
0x14002dab4  js      short loc_14002DAC1
0x14002dab6  mov     rax, [rbp+var_18]
0x14002daba  mov     rcx, [rax]
0x14002dabd  mov     [rbx+24h], rcx
0x14002dac1  mov     rcx, [rbp+P]; P
0x14002dac5  test    rcx, rcx
0x14002dac8  jz      short loc_14002DAD8
0x14002daca  xor     edx, edx; Tag
0x14002dacc  call    cs:__imp_ExFreePoolWithTag
0x14002dad3  nop     dword ptr [rax+rax+00h]
0x14002dad8  mov     rcx, [rbp+TokenInformation]; P
0x14002dadc  test    rcx, rcx
0x14002dadf  jz      short loc_14002DAEF
0x14002dae1  xor     edx, edx; Tag
0x14002dae3  call    cs:__imp_ExFreePoolWithTag
0x14002daea  nop     dword ptr [rax+rax+00h]
0x14002daef  mov     rcx, [rbp+var_20]; P
0x14002daf3  test    rcx, rcx
0x14002daf6  jz      short loc_14002DB06
0x14002daf8  xor     edx, edx; Tag
0x14002dafa  call    cs:__imp_ExFreePoolWithTag
0x14002db01  nop     dword ptr [rax+rax+00h]
0x14002db06  mov     rcx, [rbp+var_18]; P
0x14002db0a  test    rcx, rcx
0x14002db0d  jz      short loc_14002DB1D
0x14002db0f  xor     edx, edx; Tag
0x14002db11  call    cs:__imp_ExFreePoolWithTag
0x14002db18  nop     dword ptr [rax+rax+00h]
0x14002db1d  test    edi, edi
0x14002db1f  jns     short loc_14002DB3F
0x14002db21  lfence
0x14002db24  mov     rcx, [rbx]; PrimaryToken
0x14002db27  test    rcx, rcx
0x14002db2a  jz      short loc_14002DB3F
0x14002db2c  call    cs:__imp_PsDereferencePrimaryToken
0x14002db33  nop     dword ptr [rax+rax+00h]
0x14002db38  mov     qword ptr [rbx], 0
0x14002db3f  mov     eax, edi
0x14002db41  mov     rcx, [rbp+var_10]
0x14002db45  xor     rcx, rsp; StackCookie
0x14002db48  call    __security_check_cookie
0x14002db4d  mov     rbx, [rsp+50h+arg_10]
0x14002db52  mov     rdi, [rsp+50h+arg_18]
0x14002db57  add     rsp, 50h
0x14002db5b  pop     rbp
0x14002db5c  retn
```
