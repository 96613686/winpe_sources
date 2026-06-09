# HashpHashMemory

- ea: `0x1800a3754`
- end: `0x1800a3a22`
- name: `HashpHashMemory`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x18000ce18`
- `0x18000e430`

## callees

- `0x180001470`
- `0x180001590`
- `0x180002920`
- `0x180002ff0`
- `0x1800049f0`
- `0x180004b60`
- `0x18000a1c0`
- `0x18000ab20`
- `0x18000abb8`
- `0x18000abd0`
- `0x18000ad20`
- `0x18000c418`
- `0x18000d5a0`
- `0x18000f590`
- `0x180021264`
- `0x18002c500`
- `0x1800a3754`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a396b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a396b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3a11`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3a11`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a3787`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a3787`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a3872`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a3872`

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

  v5 = byte_180049F0C;
  if ( byte_180049F0C )
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
0x1800a3754  push    rbx
0x1800a3756  push    rbp
0x1800a3757  push    rsi
0x1800a3758  push    rdi
0x1800a3759  push    r12
0x1800a375b  push    r13
0x1800a375d  push    r14
0x1800a375f  push    r15
0x1800a3761  sub     rsp, 28h
0x1800a3765  mov     r13b, cs:byte_180049F0C
0x1800a376c  mov     rbp, r9
0x1800a376f  mov     r12, r8
0x1800a3772  mov     r15d, edx
0x1800a3775  mov     ebx, ecx
0x1800a3777  test    r13b, r13b
0x1800a377a  jz      loc_1800A395D
0x1800a3780  lea     rcx, stru_180049900; Lookaside
0x1800a3787  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800a378e  nop     dword ptr [rax+rax+00h]
0x1800a3793  mov     rdi, rax
0x1800a3796  mov     ecx, 8003h
0x1800a379b  test    rax, rax
0x1800a379e  jz      loc_1800A397C
0x1800a37a4  mov     [rax], ebx
0x1800a37a6  mov     eax, ebx
0x1800a37a8  sub     eax, ecx
0x1800a37aa  jz      loc_1800A39E6
0x1800a37b0  sub     eax, 1
0x1800a37b3  jz      loc_1800A38A9
0x1800a37b9  sub     eax, 8
0x1800a37bc  jnz     loc_1800A38D6
0x1800a37c2  lea     rbx, [rdi+10h]
0x1800a37c6  mov     rcx, rbx
0x1800a37c9  call    SymCryptSha256Init
0x1800a37ce  mov     eax, 20h ; ' '
0x1800a37d3  mov     rcx, [rsp+68h+arg_20]
0x1800a37db  mov     [rdi+4], eax
0x1800a37de  test    rcx, rcx
0x1800a37e1  jz      short loc_1800A37E5
0x1800a37e3  mov     [rcx], eax
0x1800a37e5  xor     r14d, r14d
0x1800a37e8  xor     esi, esi
0x1800a37ea  test    r15d, r15d
0x1800a37ed  jz      short loc_1800A3824
0x1800a37ef  mov     eax, esi
0x1800a37f1  add     rax, rax
0x1800a37f4  mov     r8d, [r12+rax*8]
0x1800a37f8  test    r8d, r8d
0x1800a37fb  jz      short loc_1800A381D
0x1800a37fd  mov     ecx, [rdi]
0x1800a37ff  mov     rdx, [r12+rax*8+8]
0x1800a3804  sub     ecx, 8003h
0x1800a380a  jz      loc_1800A39FC
0x1800a3810  sub     ecx, 1
0x1800a3813  jnz     short loc_1800A3893
0x1800a3815  mov     rcx, rbx
0x1800a3818  call    SymCryptSha1Append
0x1800a381d  inc     esi
0x1800a381f  cmp     esi, r15d
0x1800a3822  jb      short loc_1800A37EF
0x1800a3824  mov     edx, [rdi]
0x1800a3826  sub     edx, 8003h
0x1800a382c  jz      loc_1800A3937
0x1800a3832  sub     edx, 1
0x1800a3835  jz      loc_1800A38EF
0x1800a383b  sub     edx, 8
0x1800a383e  jnz     short loc_1800A38BF
0x1800a3840  mov     rdx, rbp
0x1800a3843  mov     rcx, rbx
0x1800a3846  call    SymCryptSha256Result
0x1800a384b  jmp     short loc_1800A385F
0x1800a384d  mov     r8, rax; Size
0x1800a3850  xor     edx, edx; Val
0x1800a3852  mov     rcx, rbp; void *
0x1800a3855  call    memset
0x1800a385a  test    rdi, rdi
0x1800a385d  jz      short loc_1800A387E
0x1800a385f  test    r13b, r13b
0x1800a3862  jz      loc_1800A3A09
0x1800a3868  mov     rdx, rdi; Entry
0x1800a386b  lea     rcx, stru_180049900; Lookaside
0x1800a3872  call    cs:__imp_ExFreeToPagedLookasideList
0x1800a3879  nop     dword ptr [rax+rax+00h]
0x1800a387e  mov     eax, r14d
0x1800a3881  add     rsp, 28h
0x1800a3885  pop     r15
0x1800a3887  pop     r14
0x1800a3889  pop     r13
0x1800a388b  pop     r12
0x1800a388d  pop     rdi
0x1800a388e  pop     rsi
0x1800a388f  pop     rbp
0x1800a3890  pop     rbx
0x1800a3891  retn
0x1800a3893  sub     ecx, 8
0x1800a3896  jnz     loc_1800A3925
0x1800a389c  mov     rcx, rbx
0x1800a389f  call    SymCryptSha256Append
0x1800a38a4  jmp     loc_1800A381D
0x1800a38a9  lea     rbx, [rdi+10h]
0x1800a38ad  mov     rcx, rbx
0x1800a38b0  call    SymCryptSha1Init
0x1800a38b5  mov     eax, 14h
0x1800a38ba  jmp     loc_1800A37D3
0x1800a38bf  sub     edx, 1
0x1800a38c2  jz      short loc_1800A3915
0x1800a38c4  cmp     edx, 1
0x1800a38c7  jnz     short loc_1800A385F
0x1800a38c9  mov     rdx, rbp
0x1800a38cc  mov     rcx, rbx
0x1800a38cf  call    SymCryptSha512Result
0x1800a38d4  jmp     short loc_1800A385F
0x1800a38d6  sub     eax, 1
0x1800a38d9  jz      short loc_1800A38FF
0x1800a38db  cmp     eax, 1
0x1800a38de  jz      loc_1800A39D0
0x1800a38e4  mov     r14d, 0C0000428h
0x1800a38ea  jmp     loc_1800A3982
0x1800a38ef  mov     rdx, rbp
0x1800a38f2  mov     rcx, rbx
0x1800a38f5  call    SymCryptSha1Result
0x1800a38fa  jmp     loc_1800A385F
0x1800a38ff  lea     rbx, [rdi+10h]
0x1800a3903  mov     rcx, rbx
0x1800a3906  call    SymCryptSha384Init
0x1800a390b  mov     eax, 30h ; '0'
0x1800a3910  jmp     loc_1800A37D3
0x1800a3915  mov     rdx, rbp
0x1800a3918  mov     rcx, rbx
0x1800a391b  call    SymCryptSha384Result
0x1800a3920  jmp     loc_1800A385F
0x1800a3925  sub     ecx, 1
0x1800a3928  jnz     short loc_1800A3947
0x1800a392a  mov     rcx, rbx
0x1800a392d  call    SymCryptSha384Append
0x1800a3932  jmp     loc_1800A381D
0x1800a3937  mov     rdx, rbp
0x1800a393a  mov     rcx, rbx
0x1800a393d  call    SymCryptMd5Result
0x1800a3942  jmp     loc_1800A385F
0x1800a3947  cmp     ecx, 1
0x1800a394a  jnz     loc_1800A381D
0x1800a3950  mov     rcx, rbx
0x1800a3953  call    SymCryptSha512Append
0x1800a3958  jmp     loc_1800A381D
0x1800a395d  mov     edx, 0F0h
0x1800a3962  mov     r8d, 72634943h
0x1800a3968  lea     ecx, [rdx+12h]
0x1800a396b  call    cs:__imp_ExAllocatePool2
0x1800a3972  nop     dword ptr [rax+rax+00h]
0x1800a3977  jmp     loc_1800A3793
0x1800a397c  mov     r14d, 0C0000017h
0x1800a3982  xor     eax, eax
0x1800a3984  sub     ebx, ecx
0x1800a3986  jz      short loc_1800A39C6
0x1800a3988  sub     ebx, 1
0x1800a398b  jz      short loc_1800A39BC
0x1800a398d  sub     ebx, 8
0x1800a3990  jz      short loc_1800A39B2
0x1800a3992  sub     ebx, 1
0x1800a3995  jz      short loc_1800A39A8
0x1800a3997  cmp     ebx, 1
0x1800a399a  jnz     loc_1800A384D
0x1800a39a0  lea     eax, [rbx+3Fh]
0x1800a39a3  jmp     loc_1800A384D
0x1800a39a8  mov     eax, 30h ; '0'
0x1800a39ad  jmp     loc_1800A384D
0x1800a39b2  mov     eax, 20h ; ' '
0x1800a39b7  jmp     loc_1800A384D
0x1800a39bc  mov     eax, 14h
0x1800a39c1  jmp     loc_1800A384D
0x1800a39c6  mov     eax, 10h
0x1800a39cb  jmp     loc_1800A384D
0x1800a39d0  lea     rbx, [rdi+10h]
0x1800a39d4  mov     rcx, rbx
0x1800a39d7  call    SymCryptSha512Init
0x1800a39dc  mov     eax, 40h ; '@'
0x1800a39e1  jmp     loc_1800A37D3
0x1800a39e6  lea     rbx, [rdi+10h]
0x1800a39ea  mov     rcx, rbx
0x1800a39ed  call    SymCryptMd5Init
0x1800a39f2  mov     eax, 10h
0x1800a39f7  jmp     loc_1800A37D3
0x1800a39fc  mov     rcx, rbx
0x1800a39ff  call    SymCryptMd5Append
0x1800a3a04  jmp     loc_1800A381D
0x1800a3a09  mov     edx, 72634943h; Tag
0x1800a3a0e  mov     rcx, rdi; P
0x1800a3a11  call    cs:__imp_ExFreePoolWithTag
0x1800a3a18  nop     dword ptr [rax+rax+00h]
0x1800a3a1d  jmp     loc_1800A387E
```
