# CdNonCachedRead

- ea: `0x14000f27c`
- end: `0x14000f60f`
- name: `CdNonCachedRead`
- size: `915`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, ULONG)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140017ab8`

## callees

- `0x140001114`
- `0x140002df0`
- `0x140003300`
- `0x14000e978`
- `0x14000ea54`
- `0x14000edcc`
- `0x14000f27c`
- `0x14000fe14`
- `0x1400104e0`
- `0x140010d70`
- `0x140010e90`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000f3d0`
- `ntoskrnl!KeInitializeEvent` at `0x14000f3d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f31a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f31a`
- `ntoskrnl!KeFlushIoBuffers` at `0x14000f586`
- `ntoskrnl!KeFlushIoBuffers` at `0x14000f586`

## pseudocode

```c
__int64 __fastcall CdNonCachedRead(__int64 a1, __int64 a2, __int64 a3, ULONG a4)
{
  unsigned int v4; // r13d
  __int64 v5; // rdi
  __int64 v8; // r15
  __int64 v9; // rcx
  char *v10; // r15
  __int64 v11; // rcx
  int v13; // esi
  char v14; // al
  unsigned int v15; // esi
  int v16; // r9d
  int v17; // eax
  int v18; // edi
  int v19; // eax
  char v20; // al
  __int64 v21; // rdx
  char v22; // [rsp+88h] [rbp-1D8h]
  char v23; // [rsp+89h] [rbp-1D7h]
  unsigned int v24; // [rsp+8Ch] [rbp-1D4h] BYREF
  char v25; // [rsp+90h] [rbp-1D0h]
  unsigned int v26; // [rsp+94h] [rbp-1CCh]
  unsigned int v27; // [rsp+98h] [rbp-1C8h] BYREF
  int v28; // [rsp+9Ch] [rbp-1C4h]
  int v29; // [rsp+A0h] [rbp-1C0h]
  __int64 v30; // [rsp+A8h] [rbp-1B8h]
  unsigned int v31; // [rsp+B0h] [rbp-1B0h]
  int v32; // [rsp+B4h] [rbp-1ACh]
  __int64 v33; // [rsp+B8h] [rbp-1A8h]
  __int64 v34; // [rsp+C0h] [rbp-1A0h]
  char *v35; // [rsp+C8h] [rbp-198h]
  _BYTE v36[320]; // [rsp+D8h] [rbp-188h] BYREF

  v4 = a4;
  v5 = a3;
  v30 = a3;
  v33 = a1;
  v24 = 0;
  v27 = 0;
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) )
    CdCreateUserMdl(a1, a4);
  v8 = *(_QWORD *)(a1 + 8);
  v9 = *(_QWORD *)(v8 + 8);
  if ( v9 )
  {
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
      v10 = *(char **)(v9 + 24);
    else
      v10 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v10 = *(char **)(v8 + 112);
  }
  if ( !v10 )
    CdRaiseStatusEx(a1, 3221225626LL, 0, 655360, 377);
  v11 = *(_QWORD *)(a2 + 120);
  if ( (*(_DWORD *)(v11 + 48) & 0x80u) != 0 && (unsigned __int16)(*(_WORD *)a2 - 771) <= 1u )
  {
    CdReadAudioSystemFile(a1, a2, v5, v4, v10);
    return 0;
  }
  v13 = 0;
  v28 = 0;
  LOBYTE(v26) = 0;
  v22 = 1;
  if ( *(_WORD *)a2 == 772
    && *(_QWORD *)(v11 + 568)
    && *(_DWORD *)(*(_QWORD *)(a1 + 16) + 52LL) == 2
    && (*(_DWORD *)(a1 + 32) & 4) == 0 )
  {
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 48) + 24LL), NotificationEvent, 0);
    *(_DWORD *)(a1 + 32) |= 4u;
  }
  while ( 1 )
  {
    memset(v36, 0, sizeof(v36));
    v14 = CdPrepareBuffers(
            a1,
            *(_QWORD *)(a1 + 8),
            a2,
            (_DWORD)v10,
            v13,
            v5,
            v4,
            (__int64)v36,
            (__int64)&v24,
            (__int64)&v27);
    v23 = v14;
    if ( v27 < v4 && (*(_DWORD *)(a1 + 32) & 4) == 0 )
      CdRaiseStatusEx(a1, 3221225688LL, 0, 655360, 458);
    v15 = v24;
    if ( v24 == 1 && !v14 && v22 )
    {
      CdSingleAsync(a1, v36, a2);
      v15 = 0;
      v24 = 0;
      v17 = *(_DWORD *)(a1 + 32);
      if ( (v17 & 4) != 0 )
      {
        CdWaitSync(a1);
        v18 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
LABEL_39:
        v29 = v18;
        goto LABEL_40;
      }
      *(_DWORD *)(a1 + 32) = v17 & 0xFFFFFEFF;
LABEL_38:
      v18 = 259;
      goto LABEL_39;
    }
    CdMultipleAsync(a1, a2, v24, v36);
    v19 = *(_DWORD *)(a1 + 32);
    if ( (v19 & 4) == 0 )
    {
      *(_DWORD *)(a1 + 32) = v19 & 0xFFFFFEFF;
      v15 = 0;
      v24 = 0;
      goto LABEL_38;
    }
    CdWaitSync(a1);
    v18 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
    v29 = v18;
    if ( v18 < 0 )
      goto LABEL_40;
    if ( v23 )
    {
      v20 = CdFinishBuffers(a1, (unsigned int)v36, v15, 0, 0);
      v21 = (unsigned __int8)v26;
      if ( v20 )
        v21 = 1;
      v26 = v21;
      v25 = v21;
    }
    else
    {
      v21 = v26;
    }
    v15 = 0;
    v24 = 0;
    v4 -= v27;
    v31 = v4;
    v30 += v27;
    v34 = v30;
    v10 += v27;
    v35 = v10;
    v28 += v27;
    v32 = v28;
    v22 = 0;
    if ( !v4 )
      break;
    v5 = v30;
    v13 = v28;
  }
  if ( (_BYTE)v21 )
  {
    LOBYTE(v21) = 1;
    KeFlushIoBuffers(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL), v21, 0);
  }
LABEL_40:
  if ( v15 )
  {
    LOBYTE(v16) = 1;
    CdFinishBuffers(a1, (unsigned int)v36, v15, v16, 0);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14000f27c  push    rbx
0x14000f27e  push    rsi
0x14000f27f  push    rdi
0x14000f280  push    r12
0x14000f282  push    r13
0x14000f284  push    r14
0x14000f286  push    r15
0x14000f288  sub     rsp, 1F0h
0x14000f28f  mov     rax, cs:__security_cookie
0x14000f296  xor     rax, rsp
0x14000f299  mov     [rsp+228h+var_48], rax
0x14000f2a1  mov     r13d, r9d
0x14000f2a4  mov     rdi, r8
0x14000f2a7  mov     [rsp+228h+var_1B8], r8
0x14000f2ac  mov     r12, rdx
0x14000f2af  mov     rbx, rcx
0x14000f2b2  mov     [rsp+228h+var_1A8], rcx
0x14000f2ba  mov     [rsp+228h+var_1D4], 0
0x14000f2c2  mov     [rsp+228h+var_1C8], 0
0x14000f2ca  mov     rax, [rcx+8]
0x14000f2ce  cmp     qword ptr [rax+8], 0
0x14000f2d3  jnz     short loc_14000F2DD
0x14000f2d5  mov     edx, r9d
0x14000f2d8  call    CdCreateUserMdl
0x14000f2dd  mov     r15, [rbx+8]
0x14000f2e1  mov     rcx, [r15+8]; MemoryDescriptorList
0x14000f2e5  mov     r14d, 1
0x14000f2eb  test    rcx, rcx
0x14000f2ee  jnz     short loc_14000F2F6
0x14000f2f0  mov     r15, [r15+70h]
0x14000f2f4  jmp     short loc_14000F329
0x14000f2f6  test    byte ptr [rcx+0Ah], 5
0x14000f2fa  jz      short loc_14000F302
0x14000f2fc  mov     r15, [rcx+18h]
0x14000f300  jmp     short loc_14000F329
0x14000f302  mov     [rsp+228h+Priority], 40000010h; Priority
0x14000f30a  mov     [rsp+228h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000f312  xor     r9d, r9d; RequestedAddress
0x14000f315  mov     r8d, r14d; CacheType
0x14000f318  xor     edx, edx; AccessMode
0x14000f31a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000f321  nop     dword ptr [rax+rax+00h]
0x14000f326  mov     r15, rax
0x14000f329  test    r15, r15
0x14000f32c  jz      loc_14000F5D0
0x14000f332  mov     rcx, [r12+78h]
0x14000f337  mov     eax, [rcx+30h]
0x14000f33a  test    al, al
0x14000f33c  jns     short loc_14000F38D
0x14000f33e  mov     edx, 303h
0x14000f343  movzx   eax, word ptr [r12]
0x14000f348  sub     ax, dx
0x14000f34b  cmp     ax, r14w
0x14000f34f  ja      short loc_14000F38D
0x14000f351  mov     qword ptr [rsp+228h+BugCheckOnFailure], r15; void *
0x14000f356  mov     r9d, r13d; int
0x14000f359  mov     r8, rdi; int
0x14000f35c  mov     rdx, r12; int
0x14000f35f  mov     rcx, rbx; int
0x14000f362  call    CdReadAudioSystemFile
0x14000f367  xor     eax, eax
0x14000f369  mov     rcx, [rsp+228h+var_48]
0x14000f371  xor     rcx, rsp; StackCookie
0x14000f374  call    __security_check_cookie
0x14000f379  add     rsp, 1F0h
0x14000f380  pop     r15
0x14000f382  pop     r14
0x14000f384  pop     r13
0x14000f386  pop     r12
0x14000f388  pop     rdi
0x14000f389  pop     rsi
0x14000f38a  pop     rbx
0x14000f38b  retn
0x14000f38d  xor     esi, esi
0x14000f38f  mov     [rsp+228h+var_1C4], esi
0x14000f393  mov     byte ptr [rsp+228h+var_1CC], sil
0x14000f398  mov     [rsp+228h+var_1D8], r14b
0x14000f39d  mov     eax, 304h
0x14000f3a2  cmp     [r12], ax
0x14000f3a7  jnz     short loc_14000F3E0
0x14000f3a9  cmp     [rcx+238h], rsi
0x14000f3b0  jz      short loc_14000F3E0
0x14000f3b2  mov     rax, [rbx+10h]
0x14000f3b6  cmp     dword ptr [rax+34h], 2
0x14000f3ba  jnz     short loc_14000F3E0
0x14000f3bc  mov     eax, [rbx+20h]
0x14000f3bf  test    al, 4
0x14000f3c1  jnz     short loc_14000F3E0
0x14000f3c3  mov     rcx, [rbx+30h]
0x14000f3c7  add     rcx, 18h; Event
0x14000f3cb  xor     r8d, r8d; State
0x14000f3ce  xor     edx, edx; Type
0x14000f3d0  call    cs:__imp_KeInitializeEvent
0x14000f3d7  nop     dword ptr [rax+rax+00h]
0x14000f3dc  or      dword ptr [rbx+20h], 4
0x14000f3e0  jmp     short loc_14000F3EB
0x14000f3e2  mov     rdi, [rsp+228h+var_1B8]
0x14000f3e7  mov     esi, [rsp+228h+var_1C4]
0x14000f3eb  xor     edx, edx; Val
0x14000f3ed  mov     r8d, 140h; Size
0x14000f3f3  lea     rcx, [rsp+228h+var_188]; void *
0x14000f3fb  call    memset
0x14000f400  lea     rax, [rsp+228h+var_1C8]
0x14000f405  mov     [rsp+228h+var_1E0], rax
0x14000f40a  lea     rax, [rsp+228h+var_1D4]
0x14000f40f  mov     [rsp+228h+var_1E8], rax
0x14000f414  lea     rax, [rsp+228h+var_188]
0x14000f41c  mov     [rsp+228h+var_1F0], rax
0x14000f421  mov     [rsp+228h+var_1F8], r13d
0x14000f426  mov     qword ptr [rsp+228h+Priority], rdi
0x14000f42b  mov     [rsp+228h+BugCheckOnFailure], esi
0x14000f42f  mov     r9, r15
0x14000f432  mov     r8, r12
0x14000f435  mov     rdx, [rbx+8]
0x14000f439  mov     rcx, rbx
0x14000f43c  call    CdPrepareBuffers
0x14000f441  mov     [rsp+228h+var_1D7], al
0x14000f445  cmp     [rsp+228h+var_1C8], r13d
0x14000f44a  jnb     short loc_14000F458
0x14000f44c  mov     ecx, [rbx+20h]
0x14000f44f  test    cl, 4
0x14000f452  jz      loc_14000F5EF
0x14000f458  mov     esi, [rsp+228h+var_1D4]
0x14000f45c  cmp     esi, r14d
0x14000f45f  jnz     short loc_14000F4AB
0x14000f461  test    al, al
0x14000f463  jnz     short loc_14000F4AB
0x14000f465  cmp     [rsp+228h+var_1D8], al
0x14000f469  jz      short loc_14000F4AB
0x14000f46b  mov     r8, r12
0x14000f46e  lea     rdx, [rsp+228h+var_188]
0x14000f476  mov     rcx, rbx
0x14000f479  call    CdSingleAsync
0x14000f47e  xor     esi, esi
0x14000f480  mov     [rsp+228h+var_1D4], esi
0x14000f484  mov     eax, [rbx+20h]
0x14000f487  test    al, 4
0x14000f489  jz      short loc_14000F49F
0x14000f48b  mov     rcx, rbx
0x14000f48e  call    CdWaitSync
0x14000f493  mov     rax, [rbx+8]
0x14000f497  mov     edi, [rax+30h]
0x14000f49a  jmp     loc_14000F5A6
0x14000f49f  btr     eax, 8
0x14000f4a3  mov     [rbx+20h], eax
0x14000f4a6  jmp     loc_14000F5A1
0x14000f4ab  lea     r9, [rsp+228h+var_188]
0x14000f4b3  mov     r8d, esi
0x14000f4b6  mov     rdx, r12
0x14000f4b9  mov     rcx, rbx
0x14000f4bc  call    CdMultipleAsync
0x14000f4c1  mov     eax, [rbx+20h]
0x14000f4c4  test    al, 4
0x14000f4c6  jz      loc_14000F594
0x14000f4cc  mov     rcx, rbx
0x14000f4cf  call    CdWaitSync
0x14000f4d4  mov     rax, [rbx+8]
0x14000f4d8  mov     edi, [rax+30h]
0x14000f4db  mov     [rsp+228h+var_1C0], edi
0x14000f4df  test    edi, edi
0x14000f4e1  js      loc_14000F5AA
0x14000f4e7  cmp     [rsp+228h+var_1D7], 0
0x14000f4ec  jz      short loc_14000F520
0x14000f4ee  mov     byte ptr [rsp+228h+BugCheckOnFailure], 0
0x14000f4f3  xor     r9d, r9d
0x14000f4f6  mov     r8d, esi
0x14000f4f9  lea     rdx, [rsp+228h+var_188]
0x14000f501  mov     rcx, rbx
0x14000f504  call    CdFinishBuffers
0x14000f509  mov     edx, [rsp+228h+var_1CC]
0x14000f50d  movzx   edx, dl
0x14000f510  test    al, al
0x14000f512  cmovnz  edx, r14d
0x14000f516  mov     [rsp+228h+var_1CC], edx
0x14000f51a  mov     [rsp+228h+var_1D0], dl
0x14000f51e  jmp     short loc_14000F524
0x14000f520  mov     edx, [rsp+228h+var_1CC]
0x14000f524  xor     esi, esi
0x14000f526  mov     [rsp+228h+var_1D4], esi
0x14000f52a  mov     r8d, [rsp+228h+var_1C8]
0x14000f52f  sub     r13d, r8d
0x14000f532  mov     [rsp+228h+var_1B0], r13d
0x14000f537  mov     rcx, [rsp+228h+var_1B8]
0x14000f53c  add     rcx, r8
0x14000f53f  mov     [rsp+228h+var_1B8], rcx
0x14000f544  mov     [rsp+228h+var_1A0], rcx
0x14000f54c  add     r15, r8
0x14000f54f  mov     [rsp+228h+var_198], r15
0x14000f557  mov     eax, [rsp+228h+var_1C4]
0x14000f55b  add     eax, r8d
0x14000f55e  mov     [rsp+228h+var_1C4], eax
0x14000f562  mov     [rsp+228h+var_1AC], eax
0x14000f566  mov     [rsp+228h+var_1D8], sil
0x14000f56b  test    r13d, r13d
0x14000f56e  jnz     loc_14000F3E2
0x14000f574  test    dl, dl
0x14000f576  jz      short loc_14000F5AA
0x14000f578  mov     rcx, [rbx+8]
0x14000f57c  xor     r8d, r8d
0x14000f57f  mov     dl, r14b
0x14000f582  mov     rcx, [rcx+8]
0x14000f586  call    cs:__imp_KeFlushIoBuffers
0x14000f58d  nop     dword ptr [rax+rax+00h]
0x14000f592  jmp     short loc_14000F5AA
0x14000f594  btr     eax, 8
0x14000f598  mov     [rbx+20h], eax
0x14000f59b  xor     esi, esi
0x14000f59d  mov     [rsp+228h+var_1D4], esi
0x14000f5a1  mov     edi, 103h
0x14000f5a6  mov     [rsp+228h+var_1C0], edi
0x14000f5aa  test    esi, esi
0x14000f5ac  jz      short loc_14000F5C9
0x14000f5ae  mov     byte ptr [rsp+228h+BugCheckOnFailure], 0
0x14000f5b3  mov     r9b, r14b
0x14000f5b6  mov     r8d, esi
0x14000f5b9  lea     rdx, [rsp+228h+var_188]
0x14000f5c1  mov     rcx, rbx
0x14000f5c4  call    CdFinishBuffers
0x14000f5c9  mov     eax, edi
0x14000f5cb  jmp     loc_14000F369
0x14000f5d0  mov     [rsp+228h+BugCheckOnFailure], 179h
0x14000f5d8  mov     r9d, 0A0000h
0x14000f5de  xor     r8d, r8d
0x14000f5e1  mov     edx, 0C000009Ah
0x14000f5e6  mov     rcx, rbx
0x14000f5e9  call    CdRaiseStatusEx
0x14000f5ef  mov     [rsp+228h+BugCheckOnFailure], 1CAh
0x14000f5f7  mov     r9d, 0A0000h
0x14000f5fd  xor     r8d, r8d
0x14000f600  mov     edx, 0C00000D8h
0x14000f605  mov     rcx, rbx
0x14000f608  call    CdRaiseStatusEx
0x14001b765  push    rbp
0x14001b767  sub     rsp, 50h
0x14001b76b  mov     rbp, rdx
0x14001b76e  mov     r8d, [rbp+54h]
0x14001b772  test    r8d, r8d
0x14001b775  jz      short loc_14001B793
0x14001b777  mov     [rsp+58h+var_38], 0
0x14001b77c  mov     r9b, 1
0x14001b77f  lea     rdx, [rbp+0A0h]
0x14001b786  mov     rcx, [rbp+80h]
0x14001b78d  call    CdFinishBuffers
0x14001b792  nop
0x14001b793  add     rsp, 50h
0x14001b797  pop     rbp
0x14001b798  retn
```
