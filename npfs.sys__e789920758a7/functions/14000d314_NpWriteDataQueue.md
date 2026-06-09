# NpWriteDataQueue

- ea: `0x14000d314`
- end: `0x14000d626`
- name: `NpWriteDataQueue`
- size: `786`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int, char, int, unsigned int *, __int64, unsigned int, __int64, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000b54c`
- `0x14000ca2c`
- `0x14000cff8`
- `0x140010890`

## callees

- `0x140001ad4`
- `0x140001e40`
- `0x14000d314`
- `0x140010290`
- `0x140010310`
- `0x140013d70`
- `0x140013e30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d43e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d43e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d53a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d53a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5f3`

## pseudocode

```c
__int64 __fastcall NpWriteDataQueue(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        int a6,
        unsigned int *a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        __int64 a11)
{
  unsigned int v11; // r14d
  char v12; // si
  char v13; // di
  __int64 NextRealDataQueueEntry; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // r15d
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  int v23; // edx
  size_t v24; // r12
  void *Pool2; // rdi
  __int64 result; // rax
  void *v27; // rdx
  __int64 v28; // rdx
  int ClientSecurityContext; // r14d
  __int64 v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rax
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  char v35; // [rsp+20h] [rbp-58h]
  __int64 v36; // [rsp+28h] [rbp-50h] BYREF
  PVOID P; // [rsp+30h] [rbp-48h]
  __int64 v38; // [rsp+80h] [rbp+8h]
  char v42[8]; // [rsp+A8h] [rbp+30h]

  v38 = a1;
  v11 = a4;
  v12 = 0;
  v36 = 0;
  v35 = 0;
  *a7 = a4;
  if ( a6 || (v13 = 1, a4) )
    v13 = 0;
  v42[0] = v13;
  while ( 1 )
  {
    NextRealDataQueueEntry = NpGetNextRealDataQueueEntry(a1, a11);
    v16 = NextRealDataQueueEntry;
    if ( *(_DWORD *)(v38 + 16) || !*a7 && !v13 )
      break;
    v17 = *(_DWORD *)(NextRealDataQueueEntry + 40);
    v18 = *(_QWORD *)(NextRealDataQueueEntry + 16);
    v19 = *(_QWORD *)(v18 + 184);
    if ( *(_BYTE *)v19 == 13 && *(_DWORD *)(v19 + 24) == 1138688 && (v17 < v11 || v13) )
    {
      LOBYTE(v15) = 1;
      v20 = NpRemoveDataQueueEntry(v38, v15, a11);
      if ( v20 )
      {
        *(_DWORD *)(v20 + 48) = -2147483643;
        v21 = *(_QWORD **)(a11 + 8);
        if ( *v21 != a11 )
          goto LABEL_50;
        v22 = (_QWORD *)(v20 + 168);
        *v22 = a11;
        v22[1] = v21;
        *v21 = v22;
        *(_QWORD *)(a11 + 8) = v22;
      }
    }
    else
    {
      v23 = *(_DWORD *)(v16 + 32);
      if ( v23 == 1 )
      {
        *(_QWORD *)(v18 + 88) = 0;
        v23 = *(_DWORD *)(v16 + 32);
      }
      if ( *a7 < v17 )
        v17 = *a7;
      if ( v23 == 1 || !v17 )
      {
        Pool2 = *(void **)(*(_QWORD *)(v16 + 16) + 24LL);
        P = Pool2;
        v24 = v17;
      }
      else
      {
        v24 = v17;
        Pool2 = (void *)ExAllocatePool2(64, v17, 1380347982);
        P = Pool2;
        if ( !Pool2 )
          return 3221225626LL;
        v12 = 1;
      }
      v27 = (void *)(a3 + v11 - *a7);
      if ( a5 )
        RtlCopyFromUser(Pool2, v27, v24);
      else
        RtlCopyVolatileMemory(Pool2, v27, v24);
      if ( !v35 )
      {
        ClientSecurityContext = NpGetClientSecurityContext(a9, a8, a10, &v36);
        if ( ClientSecurityContext < 0 )
        {
          if ( v12 )
            ExFreePoolWithTag(Pool2, 0);
          return (unsigned int)ClientSecurityContext;
        }
        v35 = 1;
        NpCopyClientContext(a8, v36);
        v11 = a4;
      }
      LOBYTE(v28) = 1;
      v30 = NpRemoveDataQueueEntry(v38, v28, a11);
      v31 = v30;
      if ( !v30 )
      {
        if ( v12 )
          ExFreePoolWithTag(Pool2, 0);
        v12 = 0;
LABEL_38:
        v13 = v42[0];
        goto LABEL_39;
      }
      *a7 -= v17;
      *(_QWORD *)(v30 + 56) = v24;
      if ( v12 )
      {
        *(_QWORD *)(v30 + 24) = Pool2;
        *(_DWORD *)(v30 + 16) |= 0x70u;
      }
      v32 = (_QWORD *)(v30 + 168);
      v12 = 0;
      if ( *a7 )
      {
        if ( a2 == 1 )
          *(_DWORD *)(v31 + 48) = -2147483643;
        else
          *(_DWORD *)(v31 + 48) = 0;
        v34 = *(_QWORD **)(a11 + 8);
        if ( *v34 != a11 )
LABEL_50:
          __fastfail(3u);
        *v32 = a11;
        v32[1] = v34;
        *v34 = v32;
        *(_QWORD *)(a11 + 8) = v32;
        goto LABEL_38;
      }
      *(_DWORD *)(v31 + 48) = 0;
      v33 = *(_QWORD **)(a11 + 8);
      if ( *v33 != a11 )
        goto LABEL_50;
      *v32 = a11;
      v32[1] = v33;
      *v33 = v32;
      *(_QWORD *)(a11 + 8) = v32;
      v13 = 0;
      v42[0] = 0;
    }
LABEL_39:
    a1 = v38;
  }
  if ( *a7 )
    return 3221225494LL;
  result = 0;
  if ( v13 )
    return 3221225494LL;
  return result;
}

```

## disassembly

```asm
0x14000d314  mov     rax, rsp
0x14000d317  mov     [rax+20h], r9d
0x14000d31b  mov     [rax+18h], r8
0x14000d31f  mov     [rax+10h], edx
0x14000d322  mov     [rax+8], rcx
0x14000d326  push    rbx
0x14000d327  push    rsi
0x14000d328  push    rdi
0x14000d329  push    r12
0x14000d32b  push    r13
0x14000d32d  push    r14
0x14000d32f  push    r15
0x14000d331  sub     rsp, 40h
0x14000d335  mov     r14d, r9d
0x14000d338  mov     rbx, [rsp+78h+arg_50]
0x14000d340  xor     esi, esi
0x14000d342  mov     [rax-50h], rsi
0x14000d346  mov     [rsp+78h+var_58], sil
0x14000d34b  mov     r13, [rsp+78h+arg_30]
0x14000d353  mov     [r13+0], r9d
0x14000d357  cmp     dword ptr [rsp+78h+arg_28], esi
0x14000d35e  jnz     short loc_14000D368
0x14000d360  test    r9d, r9d
0x14000d363  mov     dil, 1
0x14000d366  jz      short loc_14000D36B
0x14000d368  mov     dil, sil
0x14000d36b  mov     [rsp+78h+arg_28], dil
0x14000d373  mov     rdx, rbx
0x14000d376  call    NpGetNextRealDataQueueEntry
0x14000d37b  mov     rcx, rax
0x14000d37e  mov     r9, [rsp+78h+arg_0]
0x14000d386  cmp     [r9+10h], esi
0x14000d38a  jnz     loc_14000D603
0x14000d390  cmp     [r13+0], esi
0x14000d394  ja      short loc_14000D39F
0x14000d396  test    dil, dil
0x14000d399  jz      loc_14000D603
0x14000d39f  mov     r15d, [rcx+28h]
0x14000d3a3  mov     r8, [rcx+10h]
0x14000d3a7  mov     rax, [r8+0B8h]
0x14000d3ae  cmp     byte ptr [rax], 0Dh
0x14000d3b1  jnz     short loc_14000D409
0x14000d3b3  cmp     dword ptr [rax+18h], 116000h
0x14000d3ba  jnz     short loc_14000D409
0x14000d3bc  cmp     r15d, r14d
0x14000d3bf  jb      short loc_14000D3C6
0x14000d3c1  test    dil, dil
0x14000d3c4  jz      short loc_14000D409
0x14000d3c6  mov     r8, rbx
0x14000d3c9  mov     dl, 1
0x14000d3cb  mov     rcx, r9
0x14000d3ce  call    NpRemoveDataQueueEntry
0x14000d3d3  test    rax, rax
0x14000d3d6  jz      loc_14000D550
0x14000d3dc  mov     dword ptr [rax+30h], 80000005h
0x14000d3e3  mov     rcx, [rbx+8]
0x14000d3e7  cmp     [rcx], rbx
0x14000d3ea  jnz     loc_14000D5D9
0x14000d3f0  add     rax, 0A8h
0x14000d3f6  mov     [rax], rbx
0x14000d3f9  mov     [rax+8], rcx
0x14000d3fd  mov     [rcx], rax
0x14000d400  mov     [rbx+8], rax
0x14000d404  jmp     loc_14000D550
0x14000d409  mov     edx, [rcx+20h]
0x14000d40c  cmp     edx, 1
0x14000d40f  jnz     short loc_14000D418
0x14000d411  mov     [r8+58h], rsi
0x14000d415  mov     edx, [rcx+20h]
0x14000d418  mov     eax, [r13+0]
0x14000d41c  cmp     eax, r15d
0x14000d41f  cmovb   r15d, eax
0x14000d423  cmp     edx, 1
0x14000d426  jz      short loc_14000D466
0x14000d428  test    r15d, r15d
0x14000d42b  jz      short loc_14000D466
0x14000d42d  mov     r12d, r15d
0x14000d430  mov     r8d, 5246704Eh
0x14000d436  mov     edx, r15d
0x14000d439  mov     ecx, 40h ; '@'
0x14000d43e  call    cs:__imp_ExAllocatePool2
0x14000d445  nop     dword ptr [rax+rax+00h]
0x14000d44a  mov     rdi, rax
0x14000d44d  mov     [rsp+78h+P], rax
0x14000d452  test    rax, rax
0x14000d455  jnz     short loc_14000D461
0x14000d457  mov     eax, 0C000009Ah
0x14000d45c  jmp     loc_14000D615
0x14000d461  mov     sil, 1
0x14000d464  jmp     short loc_14000D476
0x14000d466  mov     rax, [rcx+10h]
0x14000d46a  mov     rdi, [rax+18h]
0x14000d46e  mov     [rsp+78h+P], rdi
0x14000d473  mov     r12d, r15d
0x14000d476  mov     byte ptr [rsp+78h+arg_30], sil
0x14000d47e  mov     edx, r14d
0x14000d481  sub     edx, [r13+0]
0x14000d485  add     rdx, [rsp+78h+arg_10]; Src
0x14000d48d  mov     r8, r12; Size
0x14000d490  mov     rcx, rdi; void *
0x14000d493  cmp     [rsp+78h+arg_20], 0
0x14000d49b  jz      short loc_14000D4A4
0x14000d49d  call    RtlCopyFromUser
0x14000d4a2  jmp     short loc_14000D4AA
0x14000d4a4  call    RtlCopyVolatileMemory
0x14000d4a9  nop
0x14000d4aa  cmp     [rsp+78h+var_58], 0
0x14000d4af  jnz     short loc_14000D516
0x14000d4b1  lea     r9, [rsp+78h+var_50]
0x14000d4b6  mov     r8, [rsp+78h+arg_48]
0x14000d4be  mov     rdx, [rsp+78h+arg_38]
0x14000d4c6  mov     ecx, [rsp+78h+arg_40]
0x14000d4cd  call    NpGetClientSecurityContext
0x14000d4d2  mov     r14d, eax
0x14000d4d5  test    eax, eax
0x14000d4d7  jns     short loc_14000D4F7
0x14000d4d9  test    sil, sil
0x14000d4dc  jz      short loc_14000D4EF
0x14000d4de  xor     edx, edx; Tag
0x14000d4e0  mov     rcx, rdi; P
0x14000d4e3  call    cs:__imp_ExFreePoolWithTag
0x14000d4ea  nop     dword ptr [rax+rax+00h]
0x14000d4ef  mov     eax, r14d
0x14000d4f2  jmp     loc_14000D615
0x14000d4f7  mov     [rsp+78h+var_58], 1
0x14000d4fc  mov     rdx, [rsp+78h+var_50]
0x14000d501  mov     rcx, [rsp+78h+arg_38]
0x14000d509  call    NpCopyClientContext
0x14000d50e  mov     r14d, [rsp+78h+arg_18]
0x14000d516  mov     r8, rbx
0x14000d519  mov     dl, 1
0x14000d51b  mov     rcx, [rsp+78h+arg_0]
0x14000d523  call    NpRemoveDataQueueEntry
0x14000d528  mov     rcx, rax
0x14000d52b  test    rax, rax
0x14000d52e  jnz     short loc_14000D55D
0x14000d530  test    sil, sil
0x14000d533  jz      short loc_14000D546
0x14000d535  xor     edx, edx; Tag
0x14000d537  mov     rcx, rdi; P
0x14000d53a  call    cs:__imp_ExFreePoolWithTag
0x14000d541  nop     dword ptr [rax+rax+00h]
0x14000d546  xor     esi, esi
0x14000d548  mov     dil, [rsp+78h+arg_28]
0x14000d550  mov     rcx, [rsp+78h+arg_0]
0x14000d558  jmp     loc_14000D373
0x14000d55d  sub     [r13+0], r15d
0x14000d561  mov     [rax+38h], r12
0x14000d565  test    sil, sil
0x14000d568  jz      short loc_14000D572
0x14000d56a  mov     [rax+18h], rdi
0x14000d56e  or      dword ptr [rax+10h], 70h
0x14000d572  add     rax, 0A8h
0x14000d578  xor     esi, esi
0x14000d57a  cmp     [r13+0], esi
0x14000d57e  jnz     short loc_14000D5A7
0x14000d580  mov     [rcx+30h], esi
0x14000d583  mov     rcx, [rbx+8]
0x14000d587  cmp     [rcx], rbx
0x14000d58a  jnz     short loc_14000D5D9
0x14000d58c  mov     [rax], rbx
0x14000d58f  mov     [rax+8], rcx
0x14000d593  mov     [rcx], rax
0x14000d596  mov     [rbx+8], rax
0x14000d59a  mov     dil, sil
0x14000d59d  mov     [rsp+78h+arg_28], sil
0x14000d5a5  jmp     short loc_14000D550
0x14000d5a7  cmp     [rsp+78h+arg_8], 1
0x14000d5af  jnz     short loc_14000D5CD
0x14000d5b1  mov     dword ptr [rcx+30h], 80000005h
0x14000d5b8  jmp     short loc_14000D5D0
0x14000d5ba  mov     [rax], rbx
0x14000d5bd  mov     [rax+8], rcx
0x14000d5c1  mov     [rcx], rax
0x14000d5c4  mov     [rbx+8], rax
0x14000d5c8  jmp     loc_14000D548
0x14000d5cd  mov     [rcx+30h], esi
0x14000d5d0  mov     rcx, [rbx+8]
0x14000d5d4  cmp     [rcx], rbx
0x14000d5d7  jz      short loc_14000D5BA
0x14000d5d9  mov     ecx, 3
0x14000d5de  int     29h; Win8: RtlFailFast(ecx)
0x14000d5e0  mov     ebx, eax
0x14000d5e2  cmp     byte ptr [rsp+78h+arg_30], 0
0x14000d5ea  jz      short loc_14000D5FF
0x14000d5ec  xor     edx, edx; Tag
0x14000d5ee  mov     rcx, [rsp+78h+P]; P
0x14000d5f3  call    cs:__imp_ExFreePoolWithTag
0x14000d5fa  nop     dword ptr [rax+rax+00h]
0x14000d5ff  mov     eax, ebx
0x14000d601  jmp     short loc_14000D615
0x14000d603  cmp     [r13+0], esi
0x14000d607  ja      short loc_14000D610
0x14000d609  test    dil, dil
0x14000d60c  mov     eax, esi
0x14000d60e  jz      short loc_14000D615
0x14000d610  mov     eax, 0C0000016h
0x14000d615  add     rsp, 40h
0x14000d619  pop     r15
0x14000d61b  pop     r14
0x14000d61d  pop     r13
0x14000d61f  pop     r12
0x14000d621  pop     rdi
0x14000d622  pop     rsi
0x14000d623  pop     rbx
0x14000d624  retn
0x140016605  push    rbp
0x140016607  sub     rsp, 20h
0x14001660b  mov     rbp, rdx
0x14001660e  xor     eax, eax
0x140016610  cmp     [rbp+0A0h], al
0x140016616  setnz   al
0x140016619  mov     [rbp+24h], eax
0x14001661c  mov     eax, [rbp+24h]
0x14001661f  add     rsp, 20h
0x140016623  pop     rbp
0x140016624  retn
```
