# SIPolicyCopySIChainInfo

- ea: `0x18007d7ec`
- end: `0x18007da78`
- name: `SIPolicyCopySIChainInfo`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007af94`

## callees

- `0x18000cf48`
- `0x18002c200`
- `0x18007d7ec`
- `0x18009be98`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007d86e`
- `ntoskrnl!ExAllocatePool2` at `0x18007d8af`
- `ntoskrnl!ExAllocatePool2` at `0x18007d92d`
- `ntoskrnl!ExAllocatePool2` at `0x18007d99c`
- `ntoskrnl!ExAllocatePool2` at `0x18007d86e`
- `ntoskrnl!ExAllocatePool2` at `0x18007d8af`
- `ntoskrnl!ExAllocatePool2` at `0x18007d92d`
- `ntoskrnl!ExAllocatePool2` at `0x18007d99c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007d9f1`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007da1e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007da48`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007d9f1`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007da1e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007da48`

## pseudocode

```c
__int64 __fastcall SIPolicyCopySIChainInfo(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  NTSTATUS v5; // ebx
  __int64 Pool2; // rax
  unsigned int i; // ebp
  unsigned int v8; // ecx
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 j; // rbp
  __int64 v13; // r14
  unsigned int v14; // ecx
  void *v15; // rcx
  ULONG pulResult; // [rsp+40h] [rbp+8h] BYREF

  pulResult = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_OWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *(_DWORD *)(a2 + 36) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 + 32);
  v4 = *(_DWORD *)(a1 + 16);
  if ( v4 )
  {
    v5 = RtlULongLongToULong(16LL * v4, &pulResult);
    if ( v5 < 0 )
    {
LABEL_21:
      SIPolicyFreeSIChainInfo(a2);
      return (unsigned int)v5;
    }
    Pool2 = ExAllocatePool2(256, pulResult, 1769163075);
    *(_QWORD *)(a2 + 8) = Pool2;
    if ( !Pool2 )
    {
LABEL_4:
      v5 = -1073741801;
      goto LABEL_21;
    }
    for ( i = 0; i < *(_DWORD *)(a1 + 16); ++i )
    {
      v8 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL * i);
      if ( v8 )
      {
        *(_QWORD *)(*(_QWORD *)(a2 + 8) + 16LL * i + 8) = ExAllocatePool2(256, v8, 1769163075);
        v9 = *(void **)(*(_QWORD *)(a2 + 8) + 16LL * i + 8);
        if ( !v9 )
          goto LABEL_4;
        memmove(
          v9,
          *(const void **)(*(_QWORD *)(a1 + 8) + 16LL * i + 8),
          *(unsigned int *)(*(_QWORD *)(a1 + 8) + 16LL * i));
        *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL * i) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL * i);
      }
    }
  }
  v10 = *(unsigned int *)(a1 + 32);
  if ( (_DWORD)v10 )
  {
    v5 = RtlULongLongToULong(48 * v10, &pulResult);
    if ( v5 < 0 )
      goto LABEL_21;
    v11 = ExAllocatePool2(256, pulResult, 1769163075);
    *(_QWORD *)(a2 + 24) = v11;
    if ( !v11 )
      goto LABEL_4;
    for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 32); j = (unsigned int)(j + 1) )
    {
      v13 = 48 * j;
      *(_DWORD *)(v13 + *(_QWORD *)(a2 + 24)) = *(_DWORD *)(48 * j + *(_QWORD *)(a1 + 24));
      *(_DWORD *)(*(_QWORD *)(a2 + 24) + v13 + 4) = *(_DWORD *)(48 * j + *(_QWORD *)(a1 + 24) + 4);
      v14 = *(_DWORD *)(48 * j + *(_QWORD *)(a1 + 24) + 4);
      if ( v14 )
      {
        *(_QWORD *)(v13 + *(_QWORD *)(a2 + 24) + 8) = ExAllocatePool2(256, v14, 1769163075);
        v15 = *(void **)(v13 + *(_QWORD *)(a2 + 24) + 8);
        if ( !v15 )
          goto LABEL_4;
        memmove(
          v15,
          *(const void **)(v13 + *(_QWORD *)(a1 + 24) + 8),
          *(unsigned int *)(v13 + *(_QWORD *)(a1 + 24) + 4));
      }
      v5 = RtlDuplicateUnicodeString(
             1u,
             (PCUNICODE_STRING)(v13 + *(_QWORD *)(a1 + 24) + 16LL),
             (PUNICODE_STRING)(v13 + *(_QWORD *)(a2 + 24) + 16LL));
      if ( v5 < 0 )
        goto LABEL_21;
      v5 = RtlDuplicateUnicodeString(
             1u,
             (PCUNICODE_STRING)(v13 + *(_QWORD *)(a1 + 24) + 32LL),
             (PUNICODE_STRING)(v13 + *(_QWORD *)(a2 + 24) + 32LL));
      if ( v5 < 0 )
        goto LABEL_21;
    }
  }
  v5 = RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)(a1 + 40), (PUNICODE_STRING)(a2 + 40));
  if ( v5 < 0 )
    goto LABEL_21;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007d7ec  mov     [rsp+arg_8], rbx
0x18007d7f1  mov     [rsp+arg_10], rbp
0x18007d7f6  push    rsi
0x18007d7f7  push    rdi
0x18007d7f8  push    r14
0x18007d7fa  sub     rsp, 20h
0x18007d7fe  xor     eax, eax
0x18007d800  mov     [rsp+38h+pulResult], 0
0x18007d808  xorps   xmm0, xmm0
0x18007d80b  mov     rsi, rdx
0x18007d80e  movups  xmmword ptr [rdx], xmm0
0x18007d811  mov     rdi, rcx
0x18007d814  mov     r14d, 100h
0x18007d81a  movups  xmmword ptr [rdx+10h], xmm0
0x18007d81e  movups  xmmword ptr [rdx+20h], xmm0
0x18007d822  mov     [rdx+30h], rax
0x18007d826  mov     eax, [rcx]
0x18007d828  mov     [rdx], eax
0x18007d82a  mov     eax, [rcx+24h]
0x18007d82d  mov     [rdx+24h], eax
0x18007d830  mov     eax, [rcx+10h]
0x18007d833  mov     [rdx+10h], eax
0x18007d836  mov     eax, [rcx+20h]
0x18007d839  mov     [rdx+20h], eax
0x18007d83c  mov     eax, [rcx+10h]
0x18007d83f  test    eax, eax
0x18007d841  jz      loc_18007D8F9
0x18007d847  mov     ecx, eax
0x18007d849  lea     rdx, [rsp+38h+pulResult]; pulResult
0x18007d84e  shl     rcx, 4; ullOperand
0x18007d852  call    RtlULongLongToULong
0x18007d857  mov     ebx, eax
0x18007d859  test    eax, eax
0x18007d85b  js      loc_18007DA5A
0x18007d861  mov     edx, [rsp+38h+pulResult]
0x18007d865  mov     r8d, 69734943h
0x18007d86b  mov     ecx, r14d
0x18007d86e  call    cs:__imp_ExAllocatePool2
0x18007d875  nop     dword ptr [rax+rax+00h]
0x18007d87a  mov     [rsi+8], rax
0x18007d87e  test    rax, rax
0x18007d881  jnz     short loc_18007D88D
0x18007d883  mov     ebx, 0C0000017h
0x18007d888  jmp     loc_18007DA5A
0x18007d88d  xor     ebp, ebp
0x18007d88f  cmp     [rdi+10h], ebp
0x18007d892  jbe     short loc_18007D8F9
0x18007d894  mov     rax, [rdi+8]
0x18007d898  mov     ebx, ebp
0x18007d89a  add     rbx, rbx
0x18007d89d  mov     ecx, [rax+rbx*8]
0x18007d8a0  test    ecx, ecx
0x18007d8a2  jz      short loc_18007D8F2
0x18007d8a4  mov     edx, ecx
0x18007d8a6  mov     r8d, 69734943h
0x18007d8ac  mov     rcx, r14
0x18007d8af  call    cs:__imp_ExAllocatePool2
0x18007d8b6  nop     dword ptr [rax+rax+00h]
0x18007d8bb  mov     rcx, [rsi+8]
0x18007d8bf  mov     [rcx+rbx*8+8], rax
0x18007d8c4  mov     rax, [rsi+8]
0x18007d8c8  mov     rcx, [rax+rbx*8+8]; void *
0x18007d8cd  test    rcx, rcx
0x18007d8d0  jz      short loc_18007D883
0x18007d8d2  mov     rdx, [rdi+8]
0x18007d8d6  mov     r8d, [rdx+rbx*8]; Size
0x18007d8da  mov     rdx, [rdx+rbx*8+8]; Src
0x18007d8df  call    memmove
0x18007d8e4  mov     rax, [rdi+8]
0x18007d8e8  mov     rcx, [rsi+8]
0x18007d8ec  mov     eax, [rax+rbx*8]
0x18007d8ef  mov     [rcx+rbx*8], eax
0x18007d8f2  inc     ebp
0x18007d8f4  cmp     ebp, [rdi+10h]
0x18007d8f7  jb      short loc_18007D894
0x18007d8f9  mov     eax, [rdi+20h]
0x18007d8fc  test    eax, eax
0x18007d8fe  jz      loc_18007DA3B
0x18007d904  lea     rcx, [rax+rax*2]
0x18007d908  shl     rcx, 4; ullOperand
0x18007d90c  lea     rdx, [rsp+38h+pulResult]; pulResult
0x18007d911  call    RtlULongLongToULong
0x18007d916  mov     ebx, eax
0x18007d918  test    eax, eax
0x18007d91a  js      loc_18007DA5A
0x18007d920  mov     edx, [rsp+38h+pulResult]
0x18007d924  mov     r8d, 69734943h
0x18007d92a  mov     rcx, r14
0x18007d92d  call    cs:__imp_ExAllocatePool2
0x18007d934  nop     dword ptr [rax+rax+00h]
0x18007d939  mov     [rsi+18h], rax
0x18007d93d  test    rax, rax
0x18007d940  jz      loc_18007D883
0x18007d946  xor     ebp, ebp
0x18007d948  cmp     [rdi+20h], ebp
0x18007d94b  jbe     loc_18007DA3B
0x18007d951  mov     rax, [rdi+18h]
0x18007d955  lea     r14, ds:0[rbp*2]
0x18007d95d  mov     rcx, [rsi+18h]
0x18007d961  add     r14, rbp
0x18007d964  shl     r14, 4
0x18007d968  mov     eax, [r14+rax]
0x18007d96c  mov     [r14+rcx], eax
0x18007d970  mov     rax, [rdi+18h]
0x18007d974  mov     rcx, [rsi+18h]
0x18007d978  mov     eax, [r14+rax+4]
0x18007d97d  mov     [rcx+r14+4], eax
0x18007d982  mov     rax, [rdi+18h]
0x18007d986  mov     ecx, [r14+rax+4]
0x18007d98b  test    ecx, ecx
0x18007d98d  jz      short loc_18007D9D6
0x18007d98f  mov     edx, ecx
0x18007d991  mov     r8d, 69734943h
0x18007d997  mov     ecx, 100h
0x18007d99c  call    cs:__imp_ExAllocatePool2
0x18007d9a3  nop     dword ptr [rax+rax+00h]
0x18007d9a8  mov     rcx, [rsi+18h]
0x18007d9ac  mov     [r14+rcx+8], rax
0x18007d9b1  mov     rax, [rsi+18h]
0x18007d9b5  mov     rcx, [r14+rax+8]; void *
0x18007d9ba  test    rcx, rcx
0x18007d9bd  jz      loc_18007D883
0x18007d9c3  mov     rdx, [rdi+18h]
0x18007d9c7  mov     r8d, [r14+rdx+4]; Size
0x18007d9cc  mov     rdx, [r14+rdx+8]; Src
0x18007d9d1  call    memmove
0x18007d9d6  mov     r8, [rsi+18h]
0x18007d9da  mov     ecx, 1; Flags
0x18007d9df  mov     rdx, [rdi+18h]
0x18007d9e3  add     r8, 10h
0x18007d9e7  add     rdx, 10h
0x18007d9eb  add     r8, r14; StringOut
0x18007d9ee  add     rdx, r14; StringIn
0x18007d9f1  call    cs:__imp_RtlDuplicateUnicodeString
0x18007d9f8  nop     dword ptr [rax+rax+00h]
0x18007d9fd  mov     ebx, eax
0x18007d9ff  test    eax, eax
0x18007da01  js      short loc_18007DA5A
0x18007da03  mov     r8, [rsi+18h]
0x18007da07  mov     ecx, 1; Flags
0x18007da0c  mov     rdx, [rdi+18h]
0x18007da10  add     r8, 20h ; ' '
0x18007da14  add     rdx, 20h ; ' '
0x18007da18  add     r8, r14; StringOut
0x18007da1b  add     rdx, r14; StringIn
0x18007da1e  call    cs:__imp_RtlDuplicateUnicodeString
0x18007da25  nop     dword ptr [rax+rax+00h]
0x18007da2a  mov     ebx, eax
0x18007da2c  test    eax, eax
0x18007da2e  js      short loc_18007DA5A
0x18007da30  inc     ebp
0x18007da32  cmp     ebp, [rdi+20h]
0x18007da35  jb      loc_18007D951
0x18007da3b  lea     r8, [rsi+28h]; StringOut
0x18007da3f  mov     ecx, 1; Flags
0x18007da44  lea     rdx, [rdi+28h]; StringIn
0x18007da48  call    cs:__imp_RtlDuplicateUnicodeString
0x18007da4f  nop     dword ptr [rax+rax+00h]
0x18007da54  mov     ebx, eax
0x18007da56  test    eax, eax
0x18007da58  jns     short loc_18007DA62
0x18007da5a  mov     rcx, rsi
0x18007da5d  call    SIPolicyFreeSIChainInfo
0x18007da62  mov     rbp, [rsp+38h+arg_10]
0x18007da67  mov     eax, ebx
0x18007da69  mov     rbx, [rsp+38h+arg_8]
0x18007da6e  add     rsp, 20h
0x18007da72  pop     r14
0x18007da74  pop     rdi
0x18007da75  pop     rsi
0x18007da76  retn
```
