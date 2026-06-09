# CmsContainerRangeMap::InitializeMapIfRequired(void)

- ea: `0x14006e320`
- end: `0x14006e591`
- name: `?InitializeMapIfRequired@CmsContainerRangeMap@@AEAAJXZ`
- size: `625`
- prototype: `__int64 __fastcall(CmsContainerRangeMap *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400121f0`
- `0x14006d4c0`
- `0x14006f3f0`
- `0x1400c01a0`
- `0x14011d860`
- `0x140125fd8`
- `0x140136d9c`
- `0x14013c634`
- `0x14013ff9c`

## callees

- `0x14006e320`
- `0x1400c8574`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e569`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e569`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006e341`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006e341`
- `ntoskrnl!ExAllocatePool2` at `0x14006e440`
- `ntoskrnl!ExAllocatePool2` at `0x14006e440`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006e3fc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006e3fc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f69cc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f69cc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e583`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e583`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006e35d`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006e505`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006e35d`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006e505`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e36f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e36f`

## string_xrefs

- `0x1401f69de`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsContainerRangeMap::InitializeMapIfRequired(CmsContainerRangeMap *this)
{
  unsigned int *v2; // rdi
  unsigned int v3; // ebx
  unsigned int *v4; // rbp
  unsigned int v5; // ebx
  _QWORD *v6; // r9
  unsigned int i; // eax
  unsigned int v8; // edx
  __int64 v9; // rsi
  ULONG CurrentProcessorNumber; // eax
  __int64 v11; // rdx
  __int64 Pool2; // rax
  int v13; // ecx
  unsigned int j; // r8d
  __int64 v15; // rax
  struct _NPAGED_LOOKASIDE_LIST *v17; // rcx
  _QWORD *v18; // rax

  v2 = 0;
  v3 = 0;
  ExAcquirePushLockSharedEx((char *)this + 40, 4);
  if ( *((_BYTE *)this + 54) )
    goto LABEL_31;
  ExReleasePushLockEx((char *)this + 40, 0);
  ExAcquirePushLockExclusiveEx((char *)this + 40, 0);
  if ( *((_BYTE *)this + 54) )
    goto LABEL_31;
  v4 = (unsigned int *)((char *)this + 8);
  v5 = *((_DWORD *)this + 12) >> 2;
  v6 = 0;
  if ( v5 < 3 )
    v5 = 3;
  while ( !v6 )
  {
    for ( i = 0; i < 0x48; ++i )
    {
      v8 = *((_DWORD *)qword_140201FC0 + i);
      if ( v8 > v5 )
      {
        *((_DWORD *)this + 2) = v8;
        if ( v8 != -1 )
          goto LABEL_11;
LABEL_25:
        v5 >>= 2;
        goto LABEL_26;
      }
    }
    v8 = 7199369;
    *((_DWORD *)this + 2) = 7199369;
LABEL_11:
    v9 = 24LL * v8;
    if ( !is_mul_ok(v8, 0x18u) )
      v9 = -1;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( v9 != 7032 )
      goto LABEL_16;
    v2 = (unsigned int *)(qword_1402624C0 + 192LL * (CurrentProcessorNumber % NumProcessors));
    if ( *v2 < 0x1B78uLL )
    {
      v2 = 0;
LABEL_16:
      v11 = v9 + 16;
LABEL_17:
      Pool2 = ExAllocatePool2(66, v11, 1766871885);
      v6 = (_QWORD *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
        goto LABEL_36;
      goto LABEL_35;
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v17 = (struct _NPAGED_LOOKASIDE_LIST *)(v2 + 16);
      if ( *((_BYTE *)v2 + 9) )
        v18 = ExAllocateFromNPagedLookasideList(v17);
      else
        v18 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v17);
    }
    else
    {
      if ( (int)*((_QWORD *)v2 + 11) <= (int)HIDWORD(*((_QWORD *)v2 + 11)) )
        goto LABEL_24;
      v13 = _InterlockedDecrement((volatile signed __int32 *)v2 + 22);
      if ( v13 < (int)v2[23] || v13 < 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v2 + 22);
LABEL_24:
        v11 = v2[1];
        goto LABEL_17;
      }
      v18 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v2 + 4);
    }
    v6 = v18;
    if ( !v18 )
      goto LABEL_24;
LABEL_35:
    *v6 = v2;
    v6 += 2;
LABEL_36:
    if ( !v6 )
      goto LABEL_25;
LABEL_26:
    v2 = 0;
    if ( v5 <= 1 )
      break;
  }
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    memset(v6, 0, 24LL * *v4);
    for ( j = 0; j < *v4; *(_QWORD *)(*(_QWORD *)this + 24 * v15 + 16) = 0 )
      v15 = j++;
    v3 = 0;
    *((_BYTE *)this + 54) = 1;
  }
  else
  {
    v3 = -1073741670;
  }
LABEL_31:
  ExReleasePushLockEx((char *)this + 40, 0);
  return v3;
}

```

## disassembly

```asm
0x14006e320  push    rbx
0x14006e322  push    rbp
0x14006e323  push    rsi
0x14006e324  push    rdi
0x14006e325  push    r12
0x14006e327  push    r13
0x14006e329  push    r14
0x14006e32b  push    r15
0x14006e32d  sub     rsp, 28h
0x14006e331  mov     r14, rcx
0x14006e334  xor     edi, edi
0x14006e336  add     rcx, 28h ; '('
0x14006e33a  mov     edx, 4
0x14006e33f  mov     ebx, edi
0x14006e341  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006e348  nop     dword ptr [rax+rax+00h]
0x14006e34d  cmp     [r14+36h], dil
0x14006e351  jnz     loc_14006E4FF
0x14006e357  xor     edx, edx
0x14006e359  lea     rcx, [r14+28h]
0x14006e35d  call    cs:__imp_ExReleasePushLockEx
0x14006e364  nop     dword ptr [rax+rax+00h]
0x14006e369  xor     edx, edx
0x14006e36b  lea     rcx, [r14+28h]
0x14006e36f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006e376  nop     dword ptr [rax+rax+00h]
0x14006e37b  cmp     [r14+36h], bl
0x14006e37f  jnz     loc_14006E4FF
0x14006e385  mov     ebx, [r14+30h]
0x14006e389  lea     rbp, [r14+8]
0x14006e38d  shr     ebx, 2
0x14006e390  lea     r15, [r14+8]
0x14006e394  mov     r9d, edi
0x14006e397  cmp     ebx, 3
0x14006e39a  jnb     short loc_14006E3A1
0x14006e39c  mov     ebx, 3
0x14006e3a1  lea     rdx, qword_140201FC0
0x14006e3a8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14006e3af  test    r9, r9
0x14006e3b2  jnz     loc_14006E4B0
0x14006e3b8  mov     eax, edi
0x14006e3ba  nop     word ptr [rax+rax+00h]
0x14006e3c0  cmp     eax, 48h ; 'H'
0x14006e3c3  jnb     loc_14006E52C
0x14006e3c9  mov     ecx, eax
0x14006e3cb  mov     edx, [rdx+rcx*4]
0x14006e3ce  cmp     edx, ebx
0x14006e3d0  ja      short loc_14006E3DD
0x14006e3d2  inc     eax
0x14006e3d4  lea     rdx, qword_140201FC0
0x14006e3db  jmp     short loc_14006E3C0
0x14006e3dd  mov     [r15], edx
0x14006e3e0  cmp     edx, 0FFFFFFFFh
0x14006e3e3  jnb     loc_14006E4A2
0x14006e3e9  mov     ecx, edx
0x14006e3eb  mov     eax, 18h
0x14006e3f0  mul     rcx
0x14006e3f3  mov     rsi, rax
0x14006e3f6  cmovb   rsi, r8
0x14006e3fa  xor     ecx, ecx; ProcNumber
0x14006e3fc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006e403  nop     dword ptr [rax+rax+00h]
0x14006e408  cmp     rsi, 1B78h
0x14006e40f  jnz     short loc_14006E431
0x14006e411  xor     edx, edx
0x14006e413  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14006e419  lea     rdi, [rdx+rdx*2]
0x14006e41d  shl     rdi, 6
0x14006e421  add     rdi, cs:qword_1402624C0
0x14006e428  mov     eax, [rdi]
0x14006e42a  cmp     rsi, rax
0x14006e42d  jbe     short loc_14006E465
0x14006e42f  xor     edi, edi
0x14006e431  lea     rdx, [rsi+10h]
0x14006e435  mov     ecx, 42h ; 'B'
0x14006e43a  mov     r8d, 6950534Dh
0x14006e440  call    cs:__imp_ExAllocatePool2
0x14006e447  nop     dword ptr [rax+rax+00h]
0x14006e44c  mov     r9, rax
0x14006e44f  test    al, 0Fh
0x14006e451  jnz     loc_1401F69DE
0x14006e457  test    rax, rax
0x14006e45a  jz      loc_14006E54D
0x14006e460  jmp     loc_14006E546
0x14006e465  cmp     byte ptr [rdi+8], 0
0x14006e469  jnz     loc_14006E55B
0x14006e46f  mov     rcx, [rdi+58h]
0x14006e473  mov     rax, rcx
0x14006e476  shr     rax, 20h
0x14006e47a  cmp     ecx, eax
0x14006e47c  jle     short loc_14006E49D
0x14006e47e  nop
0x14006e47f  mov     ecx, 0FFFFFFFFh
0x14006e484  lock xadd [rdi+58h], ecx
0x14006e489  nop
0x14006e48a  dec     ecx
0x14006e48c  mov     eax, [rdi+5Ch]
0x14006e48f  cmp     ecx, eax
0x14006e491  jge     loc_14006E577
0x14006e497  nop
0x14006e498  lock inc dword ptr [rdi+58h]
0x14006e49c  nop
0x14006e49d  mov     edx, [rdi+4]
0x14006e4a0  jmp     short loc_14006E435
0x14006e4a2  shr     ebx, 2
0x14006e4a5  xor     edi, edi
0x14006e4a7  cmp     ebx, 1
0x14006e4aa  ja      loc_14006E3A1
0x14006e4b0  mov     [r14], r9
0x14006e4b3  test    r9, r9
0x14006e4b6  jz      short loc_14006E525
0x14006e4b8  mov     eax, [rbp+0]
0x14006e4bb  xor     edx, edx; Val
0x14006e4bd  mov     rcx, r9; void *
0x14006e4c0  lea     r8, [rax+rax*2]
0x14006e4c4  shl     r8, 3; Size
0x14006e4c8  call    memset
0x14006e4cd  cmp     dword ptr [rbp+0], 0
0x14006e4d1  mov     r8d, edi
0x14006e4d4  jbe     short loc_14006E4F8
0x14006e4d6  nop     word ptr [rax+rax+00000000h]
0x14006e4e0  mov     eax, r8d
0x14006e4e3  inc     r8d
0x14006e4e6  lea     rdx, [rax+rax*2]
0x14006e4ea  mov     rax, [r14]
0x14006e4ed  mov     [rax+rdx*8+10h], rdi
0x14006e4f2  cmp     r8d, [rbp+0]
0x14006e4f6  jb      short loc_14006E4E0
0x14006e4f8  mov     ebx, edi
0x14006e4fa  mov     byte ptr [r14+36h], 1
0x14006e4ff  xor     edx, edx
0x14006e501  lea     rcx, [r14+28h]
0x14006e505  call    cs:__imp_ExReleasePushLockEx
0x14006e50c  nop     dword ptr [rax+rax+00h]
0x14006e511  mov     eax, ebx
0x14006e513  add     rsp, 28h
0x14006e517  pop     r15
0x14006e519  pop     r14
0x14006e51b  pop     r13
0x14006e51d  pop     r12
0x14006e51f  pop     rdi
0x14006e520  pop     rsi
0x14006e521  pop     rbp
0x14006e522  pop     rbx
0x14006e523  retn
0x14006e525  mov     ebx, 0C000009Ah
0x14006e52a  jmp     short loc_14006E4FF
0x14006e52c  mov     edx, 6DDA89h
0x14006e531  mov     [r14+8], edx
0x14006e535  jmp     loc_14006E3E9
0x14006e53a  mov     r9, rax
0x14006e53d  test    rax, rax
0x14006e540  jz      loc_14006E49D
0x14006e546  mov     [r9], rdi
0x14006e549  add     r9, 10h
0x14006e54d  test    r9, r9
0x14006e550  jnz     loc_14006E4A5
0x14006e556  jmp     loc_14006E4A2
0x14006e55b  cmp     byte ptr [rdi+9], 0
0x14006e55f  lea     rcx, [rdi+40h]; Lookaside
0x14006e563  jz      loc_1401F69CC
0x14006e569  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006e570  nop     dword ptr [rax+rax+00h]
0x14006e575  jmp     short loc_14006E53A
0x14006e577  test    ecx, ecx
0x14006e579  js      loc_14006E497
0x14006e57f  lea     rcx, [rdi+40h]; ListHead
0x14006e583  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006e58a  nop     dword ptr [rax+rax+00h]
0x14006e58f  jmp     short loc_14006E53A
0x1401f69cc  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f69d3  nop     dword ptr [rax+rax+00h]
0x1401f69d8  nop
0x1401f69d9  jmp     loc_14006E53A
0x1401f69de  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f69e5  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
