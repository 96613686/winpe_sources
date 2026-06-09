# HashpHashMemory

- ea: `0x1800a3544`
- end: `0x1800a3812`
- name: `HashpHashMemory`
- size: `718`
- prototype: `__int64 __fastcall(int, unsigned int, __int64, void *, int *)`
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
- `0x180021164`
- `0x18002c340`
- `0x1800a3544`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a375b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a375b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3801`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3801`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a3577`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800a3577`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a3662`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1800a3662`

## pseudocode

```c
__int64 __fastcall HashpHashMemory(int a1, unsigned int a2, __int64 a3, _QWORD *a4, int *a5)
{
  char v5; // r13
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  unsigned int *v12; // rbx
  int v13; // eax
  unsigned int v14; // r14d
  unsigned int i; // esi
  size_t v16; // r8
  char *v17; // rdx
  size_t v19; // rax
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx

  v5 = byte_180048F04;
  if ( byte_180048F04 )
    Pool2 = ExAllocateFromPagedLookasideList(&stru_180048900);
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
          v16 = *(unsigned int *)(a3 + 16LL * i);
          if ( (_DWORD)v16 )
          {
            v17 = *(char **)(a3 + 16LL * i + 8);
            switch ( *v11 )
            {
              case 0x8003:
                SymCryptMd5Append((__int64)v12, (__int64)v17, v16);
                break;
              case 0x8004:
                SymCryptSha1Append(v12, v17, v16);
                break;
              case 0x800C:
                SymCryptSha256Append(v12, v17, v16);
                break;
              case 0x800D:
                SymCryptSha384Append((__int64)v12, (__int64)v17, v16);
                break;
              case 0x800E:
                SymCryptSha512Append(v12, v17, v16);
                break;
            }
          }
        }
        switch ( *v11 )
        {
          case 0x8003:
            SymCryptMd5Result((__int64)v12, a4);
            break;
          case 0x8004:
            SymCryptSha1Result(v12, a4);
            break;
          case 0x800C:
            SymCryptSha256Result(v12, a4);
            break;
          case 0x800D:
            SymCryptSha384Result((__int64)v12, a4);
            break;
          case 0x800E:
            SymCryptSha512Result(v12, a4);
            break;
        }
LABEL_21:
        if ( v5 )
          ExFreeToPagedLookasideList(&stru_180048900, v11);
        else
          ExFreePoolWithTag(v11, 0x72634943u);
        return v14;
      case 32781:
        v12 = Pool2 + 4;
        SymCryptSha384Init((__int64)(Pool2 + 4));
        v13 = 48;
        goto LABEL_8;
      case 32782:
        v12 = Pool2 + 4;
        SymCryptSha512Init((__int64)(Pool2 + 4));
        v13 = 64;
        goto LABEL_8;
    }
    v14 = -1073740760;
  }
  else
  {
    v14 = -1073741801;
  }
  v19 = 0;
  v20 = a1 - 32771;
  if ( v20 )
  {
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 8;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 == 1 )
            v19 = 64;
        }
        else
        {
          v19 = 48;
        }
      }
      else
      {
        v19 = 32;
      }
    }
    else
    {
      v19 = 20;
    }
  }
  else
  {
    v19 = 16;
  }
  memset(a4, 0, v19);
  if ( v11 )
    goto LABEL_21;
  return v14;
}

```

## disassembly

```asm
0x1800a3544  push    rbx
0x1800a3546  push    rbp
0x1800a3547  push    rsi
0x1800a3548  push    rdi
0x1800a3549  push    r12
0x1800a354b  push    r13
0x1800a354d  push    r14
0x1800a354f  push    r15
0x1800a3551  sub     rsp, 28h
0x1800a3555  mov     r13b, cs:byte_180048F04
0x1800a355c  mov     rbp, r9
0x1800a355f  mov     r12, r8
0x1800a3562  mov     r15d, edx
0x1800a3565  mov     ebx, ecx
0x1800a3567  test    r13b, r13b
0x1800a356a  jz      loc_1800A374D
0x1800a3570  lea     rcx, stru_180048900; Lookaside
0x1800a3577  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800a357e  nop     dword ptr [rax+rax+00h]
0x1800a3583  mov     rdi, rax
0x1800a3586  mov     ecx, 8003h
0x1800a358b  test    rax, rax
0x1800a358e  jz      loc_1800A376C
0x1800a3594  mov     [rax], ebx
0x1800a3596  mov     eax, ebx
0x1800a3598  sub     eax, ecx
0x1800a359a  jz      loc_1800A37D6
0x1800a35a0  sub     eax, 1
0x1800a35a3  jz      loc_1800A3699
0x1800a35a9  sub     eax, 8
0x1800a35ac  jnz     loc_1800A36C6
0x1800a35b2  lea     rbx, [rdi+10h]
0x1800a35b6  mov     rcx, rbx
0x1800a35b9  call    SymCryptSha256Init
0x1800a35be  mov     eax, 20h ; ' '
0x1800a35c3  mov     rcx, [rsp+68h+arg_20]
0x1800a35cb  mov     [rdi+4], eax
0x1800a35ce  test    rcx, rcx
0x1800a35d1  jz      short loc_1800A35D5
0x1800a35d3  mov     [rcx], eax
0x1800a35d5  xor     r14d, r14d
0x1800a35d8  xor     esi, esi
0x1800a35da  test    r15d, r15d
0x1800a35dd  jz      short loc_1800A3614
0x1800a35df  mov     eax, esi
0x1800a35e1  add     rax, rax
0x1800a35e4  mov     r8d, [r12+rax*8]
0x1800a35e8  test    r8d, r8d
0x1800a35eb  jz      short loc_1800A360D
0x1800a35ed  mov     ecx, [rdi]
0x1800a35ef  mov     rdx, [r12+rax*8+8]
0x1800a35f4  sub     ecx, 8003h
0x1800a35fa  jz      loc_1800A37EC
0x1800a3600  sub     ecx, 1
0x1800a3603  jnz     short loc_1800A3683
0x1800a3605  mov     rcx, rbx
0x1800a3608  call    SymCryptSha1Append
0x1800a360d  inc     esi
0x1800a360f  cmp     esi, r15d
0x1800a3612  jb      short loc_1800A35DF
0x1800a3614  mov     edx, [rdi]
0x1800a3616  sub     edx, 8003h
0x1800a361c  jz      loc_1800A3727
0x1800a3622  sub     edx, 1
0x1800a3625  jz      loc_1800A36DF
0x1800a362b  sub     edx, 8
0x1800a362e  jnz     short loc_1800A36AF
0x1800a3630  mov     rdx, rbp
0x1800a3633  mov     rcx, rbx
0x1800a3636  call    SymCryptSha256Result
0x1800a363b  jmp     short loc_1800A364F
0x1800a363d  mov     r8, rax; Size
0x1800a3640  xor     edx, edx; Val
0x1800a3642  mov     rcx, rbp; void *
0x1800a3645  call    memset
0x1800a364a  test    rdi, rdi
0x1800a364d  jz      short loc_1800A366E
0x1800a364f  test    r13b, r13b
0x1800a3652  jz      loc_1800A37F9
0x1800a3658  mov     rdx, rdi; Entry
0x1800a365b  lea     rcx, stru_180048900; Lookaside
0x1800a3662  call    cs:__imp_ExFreeToPagedLookasideList
0x1800a3669  nop     dword ptr [rax+rax+00h]
0x1800a366e  mov     eax, r14d
0x1800a3671  add     rsp, 28h
0x1800a3675  pop     r15
0x1800a3677  pop     r14
0x1800a3679  pop     r13
0x1800a367b  pop     r12
0x1800a367d  pop     rdi
0x1800a367e  pop     rsi
0x1800a367f  pop     rbp
0x1800a3680  pop     rbx
0x1800a3681  retn
0x1800a3683  sub     ecx, 8
0x1800a3686  jnz     loc_1800A3715
0x1800a368c  mov     rcx, rbx
0x1800a368f  call    SymCryptSha256Append
0x1800a3694  jmp     loc_1800A360D
0x1800a3699  lea     rbx, [rdi+10h]
0x1800a369d  mov     rcx, rbx
0x1800a36a0  call    SymCryptSha1Init
0x1800a36a5  mov     eax, 14h
0x1800a36aa  jmp     loc_1800A35C3
0x1800a36af  sub     edx, 1
0x1800a36b2  jz      short loc_1800A3705
0x1800a36b4  cmp     edx, 1
0x1800a36b7  jnz     short loc_1800A364F
0x1800a36b9  mov     rdx, rbp
0x1800a36bc  mov     rcx, rbx
0x1800a36bf  call    SymCryptSha512Result
0x1800a36c4  jmp     short loc_1800A364F
0x1800a36c6  sub     eax, 1
0x1800a36c9  jz      short loc_1800A36EF
0x1800a36cb  cmp     eax, 1
0x1800a36ce  jz      loc_1800A37C0
0x1800a36d4  mov     r14d, 0C0000428h
0x1800a36da  jmp     loc_1800A3772
0x1800a36df  mov     rdx, rbp
0x1800a36e2  mov     rcx, rbx
0x1800a36e5  call    SymCryptSha1Result
0x1800a36ea  jmp     loc_1800A364F
0x1800a36ef  lea     rbx, [rdi+10h]
0x1800a36f3  mov     rcx, rbx
0x1800a36f6  call    SymCryptSha384Init
0x1800a36fb  mov     eax, 30h ; '0'
0x1800a3700  jmp     loc_1800A35C3
0x1800a3705  mov     rdx, rbp
0x1800a3708  mov     rcx, rbx
0x1800a370b  call    SymCryptSha384Result
0x1800a3710  jmp     loc_1800A364F
0x1800a3715  sub     ecx, 1
0x1800a3718  jnz     short loc_1800A3737
0x1800a371a  mov     rcx, rbx
0x1800a371d  call    SymCryptSha384Append
0x1800a3722  jmp     loc_1800A360D
0x1800a3727  mov     rdx, rbp
0x1800a372a  mov     rcx, rbx
0x1800a372d  call    SymCryptMd5Result
0x1800a3732  jmp     loc_1800A364F
0x1800a3737  cmp     ecx, 1
0x1800a373a  jnz     loc_1800A360D
0x1800a3740  mov     rcx, rbx
0x1800a3743  call    SymCryptSha512Append
0x1800a3748  jmp     loc_1800A360D
0x1800a374d  mov     edx, 0F0h
0x1800a3752  mov     r8d, 72634943h
0x1800a3758  lea     ecx, [rdx+12h]
0x1800a375b  call    cs:__imp_ExAllocatePool2
0x1800a3762  nop     dword ptr [rax+rax+00h]
0x1800a3767  jmp     loc_1800A3583
0x1800a376c  mov     r14d, 0C0000017h
0x1800a3772  xor     eax, eax
0x1800a3774  sub     ebx, ecx
0x1800a3776  jz      short loc_1800A37B6
0x1800a3778  sub     ebx, 1
0x1800a377b  jz      short loc_1800A37AC
0x1800a377d  sub     ebx, 8
0x1800a3780  jz      short loc_1800A37A2
0x1800a3782  sub     ebx, 1
0x1800a3785  jz      short loc_1800A3798
0x1800a3787  cmp     ebx, 1
0x1800a378a  jnz     loc_1800A363D
0x1800a3790  lea     eax, [rbx+3Fh]
0x1800a3793  jmp     loc_1800A363D
0x1800a3798  mov     eax, 30h ; '0'
0x1800a379d  jmp     loc_1800A363D
0x1800a37a2  mov     eax, 20h ; ' '
0x1800a37a7  jmp     loc_1800A363D
0x1800a37ac  mov     eax, 14h
0x1800a37b1  jmp     loc_1800A363D
0x1800a37b6  mov     eax, 10h
0x1800a37bb  jmp     loc_1800A363D
0x1800a37c0  lea     rbx, [rdi+10h]
0x1800a37c4  mov     rcx, rbx
0x1800a37c7  call    SymCryptSha512Init
0x1800a37cc  mov     eax, 40h ; '@'
0x1800a37d1  jmp     loc_1800A35C3
0x1800a37d6  lea     rbx, [rdi+10h]
0x1800a37da  mov     rcx, rbx
0x1800a37dd  call    SymCryptMd5Init
0x1800a37e2  mov     eax, 10h
0x1800a37e7  jmp     loc_1800A35C3
0x1800a37ec  mov     rcx, rbx
0x1800a37ef  call    SymCryptMd5Append
0x1800a37f4  jmp     loc_1800A360D
0x1800a37f9  mov     edx, 72634943h; Tag
0x1800a37fe  mov     rcx, rdi; P
0x1800a3801  call    cs:__imp_ExFreePoolWithTag
0x1800a3808  nop     dword ptr [rax+rax+00h]
0x1800a380d  jmp     loc_1800A366E
```
