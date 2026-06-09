# HashpHashMemory

- ea: `0x1800a4b74`
- end: `0x1800a4e42`
- name: `HashpHashMemory`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x18000ce08`
- `0x18000e420`

## callees

- `0x180001470`
- `0x180001590`
- `0x180002920`
- `0x180002ff0`
- `0x1800049f0`
- `0x180004b60`
- `0x18000a1b0`
- `0x18000ab10`
- `0x18000aba8`
- `0x18000abc0`
- `0x18000ad10`
- `0x18000c408`
- `0x18000d590`
- `0x18000f580`
- `0x180021194`
- `0x18002c380`
- `0x1800a4b74`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a4d8b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a4d8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4e31`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4e31`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a4ba7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a4ba7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a4c92`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a4c92`

## pseudocode

```c
__int64 __fastcall HashpHashMemory(int a1, unsigned int a2, __int64 a3, void *a4, int *a5)
{
  char v5; // r13
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  _DWORD *v12; // rbx
  int v13; // eax
  unsigned int v14; // r14d
  unsigned int i; // esi
  __int64 v16; // rdx
  size_t v18; // rax
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx

  v5 = byte_180049EF4;
  if ( byte_180049EF4 )
    Pool2 = ExAllocateFromPagedLookasideList(&stru_180049900);
  else
    Pool2 = (_DWORD *)ExAllocatePool2(258, 240, 1919109443);
  v11 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a1;
    switch ( a1 )
    {
      case 32771:
        v12 = Pool2 + 4;
        SymCryptMd5Init(Pool2 + 4);
        v13 = 16;
        goto LABEL_8;
      case 32772:
        v12 = Pool2 + 4;
        SymCryptSha1Init(Pool2 + 4);
        v13 = 20;
        goto LABEL_8;
      case 32780:
        v12 = Pool2 + 4;
        SymCryptSha256Init(Pool2 + 4);
        v13 = 32;
LABEL_8:
        v11[1] = v13;
        if ( a5 )
          *a5 = v13;
        v14 = 0;
        for ( i = 0; i < a2; ++i )
        {
          if ( *(_DWORD *)(a3 + 16LL * i) )
          {
            v16 = *(_QWORD *)(a3 + 16LL * i + 8);
            switch ( *v11 )
            {
              case 0x8003:
                SymCryptMd5Append(v12, v16);
                break;
              case 0x8004:
                SymCryptSha1Append(v12, v16);
                break;
              case 0x800C:
                SymCryptSha256Append(v12, v16);
                break;
              case 0x800D:
                SymCryptSha384Append(v12, v16);
                break;
              case 0x800E:
                SymCryptSha512Append(v12, v16);
                break;
            }
          }
        }
        switch ( *v11 )
        {
          case 0x8003:
            SymCryptMd5Result(v12, a4);
            break;
          case 0x8004:
            SymCryptSha1Result(v12, a4);
            break;
          case 0x800C:
            SymCryptSha256Result(v12, a4);
            break;
          case 0x800D:
            SymCryptSha384Result(v12, a4);
            break;
          case 0x800E:
            SymCryptSha512Result(v12, a4);
            break;
        }
LABEL_21:
        if ( v5 )
          ExFreeToPagedLookasideList(&stru_180049900, v11);
        else
          ExFreePoolWithTag(v11, 0x72634943u);
        return v14;
      case 32781:
        v12 = Pool2 + 4;
        SymCryptSha384Init(Pool2 + 4);
        v13 = 48;
        goto LABEL_8;
      case 32782:
        v12 = Pool2 + 4;
        SymCryptSha512Init(Pool2 + 4);
        v13 = 64;
        goto LABEL_8;
    }
    v14 = -1073740760;
  }
  else
  {
    v14 = -1073741801;
  }
  v18 = 0;
  v19 = a1 - 32771;
  if ( v19 )
  {
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 8;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 == 1 )
            v18 = 64;
        }
        else
        {
          v18 = 48;
        }
      }
      else
      {
        v18 = 32;
      }
    }
    else
    {
      v18 = 20;
    }
  }
  else
  {
    v18 = 16;
  }
  memset(a4, 0, v18);
  if ( v11 )
    goto LABEL_21;
  return v14;
}

```

## disassembly

```asm
0x1800a4b74  push    rbx
0x1800a4b76  push    rbp
0x1800a4b77  push    rsi
0x1800a4b78  push    rdi
0x1800a4b79  push    r12
0x1800a4b7b  push    r13
0x1800a4b7d  push    r14
0x1800a4b7f  push    r15
0x1800a4b81  sub     rsp, 28h
0x1800a4b85  mov     r13b, cs:byte_180049EF4
0x1800a4b8c  mov     rbp, r9
0x1800a4b8f  mov     r12, r8
0x1800a4b92  mov     r15d, edx
0x1800a4b95  mov     ebx, ecx
0x1800a4b97  test    r13b, r13b
0x1800a4b9a  jz      loc_1800A4D7D
0x1800a4ba0  lea     rcx, stru_180049900; Lookaside
0x1800a4ba7  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800a4bae  nop     dword ptr [rax+rax+00h]
0x1800a4bb3  mov     rdi, rax
0x1800a4bb6  mov     ecx, 8003h
0x1800a4bbb  test    rax, rax
0x1800a4bbe  jz      loc_1800A4D9C
0x1800a4bc4  mov     [rax], ebx
0x1800a4bc6  mov     eax, ebx
0x1800a4bc8  sub     eax, ecx
0x1800a4bca  jz      loc_1800A4E06
0x1800a4bd0  sub     eax, 1
0x1800a4bd3  jz      loc_1800A4CC9
0x1800a4bd9  sub     eax, 8
0x1800a4bdc  jnz     loc_1800A4CF6
0x1800a4be2  lea     rbx, [rdi+10h]
0x1800a4be6  mov     rcx, rbx
0x1800a4be9  call    SymCryptSha256Init
0x1800a4bee  mov     eax, 20h ; ' '
0x1800a4bf3  mov     rcx, [rsp+68h+arg_20]
0x1800a4bfb  mov     [rdi+4], eax
0x1800a4bfe  test    rcx, rcx
0x1800a4c01  jz      short loc_1800A4C05
0x1800a4c03  mov     [rcx], eax
0x1800a4c05  xor     r14d, r14d
0x1800a4c08  xor     esi, esi
0x1800a4c0a  test    r15d, r15d
0x1800a4c0d  jz      short loc_1800A4C44
0x1800a4c0f  mov     eax, esi
0x1800a4c11  add     rax, rax
0x1800a4c14  mov     r8d, [r12+rax*8]
0x1800a4c18  test    r8d, r8d
0x1800a4c1b  jz      short loc_1800A4C3D
0x1800a4c1d  mov     ecx, [rdi]
0x1800a4c1f  mov     rdx, [r12+rax*8+8]
0x1800a4c24  sub     ecx, 8003h
0x1800a4c2a  jz      loc_1800A4E1C
0x1800a4c30  sub     ecx, 1
0x1800a4c33  jnz     short loc_1800A4CB3
0x1800a4c35  mov     rcx, rbx
0x1800a4c38  call    SymCryptSha1Append
0x1800a4c3d  inc     esi
0x1800a4c3f  cmp     esi, r15d
0x1800a4c42  jb      short loc_1800A4C0F
0x1800a4c44  mov     edx, [rdi]
0x1800a4c46  sub     edx, 8003h
0x1800a4c4c  jz      loc_1800A4D57
0x1800a4c52  sub     edx, 1
0x1800a4c55  jz      loc_1800A4D0F
0x1800a4c5b  sub     edx, 8
0x1800a4c5e  jnz     short loc_1800A4CDF
0x1800a4c60  mov     rdx, rbp
0x1800a4c63  mov     rcx, rbx
0x1800a4c66  call    SymCryptSha256Result
0x1800a4c6b  jmp     short loc_1800A4C7F
0x1800a4c6d  mov     r8, rax; Size
0x1800a4c70  xor     edx, edx; Val
0x1800a4c72  mov     rcx, rbp; void *
0x1800a4c75  call    memset
0x1800a4c7a  test    rdi, rdi
0x1800a4c7d  jz      short loc_1800A4C9E
0x1800a4c7f  test    r13b, r13b
0x1800a4c82  jz      loc_1800A4E29
0x1800a4c88  mov     rdx, rdi; Entry
0x1800a4c8b  lea     rcx, stru_180049900; Lookaside
0x1800a4c92  call    cs:__imp_ExFreeToPagedLookasideList
0x1800a4c99  nop     dword ptr [rax+rax+00h]
0x1800a4c9e  mov     eax, r14d
0x1800a4ca1  add     rsp, 28h
0x1800a4ca5  pop     r15
0x1800a4ca7  pop     r14
0x1800a4ca9  pop     r13
0x1800a4cab  pop     r12
0x1800a4cad  pop     rdi
0x1800a4cae  pop     rsi
0x1800a4caf  pop     rbp
0x1800a4cb0  pop     rbx
0x1800a4cb1  retn
0x1800a4cb3  sub     ecx, 8
0x1800a4cb6  jnz     loc_1800A4D45
0x1800a4cbc  mov     rcx, rbx
0x1800a4cbf  call    SymCryptSha256Append
0x1800a4cc4  jmp     loc_1800A4C3D
0x1800a4cc9  lea     rbx, [rdi+10h]
0x1800a4ccd  mov     rcx, rbx
0x1800a4cd0  call    SymCryptSha1Init
0x1800a4cd5  mov     eax, 14h
0x1800a4cda  jmp     loc_1800A4BF3
0x1800a4cdf  sub     edx, 1
0x1800a4ce2  jz      short loc_1800A4D35
0x1800a4ce4  cmp     edx, 1
0x1800a4ce7  jnz     short loc_1800A4C7F
0x1800a4ce9  mov     rdx, rbp
0x1800a4cec  mov     rcx, rbx
0x1800a4cef  call    SymCryptSha512Result
0x1800a4cf4  jmp     short loc_1800A4C7F
0x1800a4cf6  sub     eax, 1
0x1800a4cf9  jz      short loc_1800A4D1F
0x1800a4cfb  cmp     eax, 1
0x1800a4cfe  jz      loc_1800A4DF0
0x1800a4d04  mov     r14d, 0C0000428h
0x1800a4d0a  jmp     loc_1800A4DA2
0x1800a4d0f  mov     rdx, rbp
0x1800a4d12  mov     rcx, rbx
0x1800a4d15  call    SymCryptSha1Result
0x1800a4d1a  jmp     loc_1800A4C7F
0x1800a4d1f  lea     rbx, [rdi+10h]
0x1800a4d23  mov     rcx, rbx
0x1800a4d26  call    SymCryptSha384Init
0x1800a4d2b  mov     eax, 30h ; '0'
0x1800a4d30  jmp     loc_1800A4BF3
0x1800a4d35  mov     rdx, rbp
0x1800a4d38  mov     rcx, rbx
0x1800a4d3b  call    SymCryptSha384Result
0x1800a4d40  jmp     loc_1800A4C7F
0x1800a4d45  sub     ecx, 1
0x1800a4d48  jnz     short loc_1800A4D67
0x1800a4d4a  mov     rcx, rbx
0x1800a4d4d  call    SymCryptSha384Append
0x1800a4d52  jmp     loc_1800A4C3D
0x1800a4d57  mov     rdx, rbp
0x1800a4d5a  mov     rcx, rbx
0x1800a4d5d  call    SymCryptMd5Result
0x1800a4d62  jmp     loc_1800A4C7F
0x1800a4d67  cmp     ecx, 1
0x1800a4d6a  jnz     loc_1800A4C3D
0x1800a4d70  mov     rcx, rbx
0x1800a4d73  call    SymCryptSha512Append
0x1800a4d78  jmp     loc_1800A4C3D
0x1800a4d7d  mov     edx, 0F0h
0x1800a4d82  mov     r8d, 72634943h
0x1800a4d88  lea     ecx, [rdx+12h]
0x1800a4d8b  call    cs:__imp_ExAllocatePool2
0x1800a4d92  nop     dword ptr [rax+rax+00h]
0x1800a4d97  jmp     loc_1800A4BB3
0x1800a4d9c  mov     r14d, 0C0000017h
0x1800a4da2  xor     eax, eax
0x1800a4da4  sub     ebx, ecx
0x1800a4da6  jz      short loc_1800A4DE6
0x1800a4da8  sub     ebx, 1
0x1800a4dab  jz      short loc_1800A4DDC
0x1800a4dad  sub     ebx, 8
0x1800a4db0  jz      short loc_1800A4DD2
0x1800a4db2  sub     ebx, 1
0x1800a4db5  jz      short loc_1800A4DC8
0x1800a4db7  cmp     ebx, 1
0x1800a4dba  jnz     loc_1800A4C6D
0x1800a4dc0  lea     eax, [rbx+3Fh]
0x1800a4dc3  jmp     loc_1800A4C6D
0x1800a4dc8  mov     eax, 30h ; '0'
0x1800a4dcd  jmp     loc_1800A4C6D
0x1800a4dd2  mov     eax, 20h ; ' '
0x1800a4dd7  jmp     loc_1800A4C6D
0x1800a4ddc  mov     eax, 14h
0x1800a4de1  jmp     loc_1800A4C6D
0x1800a4de6  mov     eax, 10h
0x1800a4deb  jmp     loc_1800A4C6D
0x1800a4df0  lea     rbx, [rdi+10h]
0x1800a4df4  mov     rcx, rbx
0x1800a4df7  call    SymCryptSha512Init
0x1800a4dfc  mov     eax, 40h ; '@'
0x1800a4e01  jmp     loc_1800A4BF3
0x1800a4e06  lea     rbx, [rdi+10h]
0x1800a4e0a  mov     rcx, rbx
0x1800a4e0d  call    SymCryptMd5Init
0x1800a4e12  mov     eax, 10h
0x1800a4e17  jmp     loc_1800A4BF3
0x1800a4e1c  mov     rcx, rbx
0x1800a4e1f  call    SymCryptMd5Append
0x1800a4e24  jmp     loc_1800A4C3D
0x1800a4e29  mov     edx, 72634943h; Tag
0x1800a4e2e  mov     rcx, rdi; P
0x1800a4e31  call    cs:__imp_ExFreePoolWithTag
0x1800a4e38  nop     dword ptr [rax+rax+00h]
0x1800a4e3d  jmp     loc_1800A4C9E
```
