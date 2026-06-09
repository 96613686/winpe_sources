# CdOpenByFileId

- ea: `0x14000dc38`
- end: `0x14000e1c7`
- name: `CdOpenByFileId`
- size: `1423`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c8b4`

## callees

- `0x140002df0`
- `0x140003300`
- `0x14000b684`
- `0x14000d400`
- `0x14000dc38`
- `0x14001203c`
- `0x140012464`
- `0x140012884`
- `0x14001292c`
- `0x140016998`
- `0x140016a20`
- `0x1400181a4`
- `0x140019238`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000dd07`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000de7a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e069`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000dd07`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000de7a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e069`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000dd89`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000de52`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000dea6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e041`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e096`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e103`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b5f7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000dd89`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000de52`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000dea6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e041`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e096`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e103`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b5f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e007`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e007`
- `ntoskrnl!CcUnpinData` at `0x14000e133`
- `ntoskrnl!CcUnpinData` at `0x14001b629`
- `ntoskrnl!CcUnpinData` at `0x14000e133`
- `ntoskrnl!CcUnpinData` at `0x14001b629`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e195`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b657`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b685`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e195`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b657`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b685`

## pseudocode

```c
__int64 __fastcall CdOpenByFileId(PIRP *Context, __int64 a2, __int64 a3, __int64 *a4)
{
  unsigned int v7; // edi
  char v8; // r14
  char v9; // r13
  __int64 DesiredAccess; // rcx
  char v11; // r12
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r13
  unsigned int v18; // r13d
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 v22; // rbx
  char v23; // al
  struct _FAST_MUTEX *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rdx
  char v27; // al
  struct _FAST_MUTEX *v28; // rcx
  int v30; // [rsp+44h] [rbp-454h]
  __int64 v31; // [rsp+48h] [rbp-450h]
  PVOID P[26]; // [rsp+80h] [rbp-418h] BYREF
  _QWORD v35[96]; // [rsp+150h] [rbp-348h] BYREF

  v7 = -1073741790;
  v8 = 0;
  memset(v35, 0, sizeof(v35));
  v9 = 0;
  memset(P, 0, 0xC8u);
  v11 = 0;
  v12 = **(_QWORD **)(*(_QWORD *)(a2 + 48) + 96LL);
  if ( (int)v12 >= 0 )
  {
    v30 = 4;
  }
  else
  {
    if ( (v12 & 0x7FFFFFFF) != 0 )
    {
      v7 = -1073741811;
      goto LABEL_36;
    }
    v30 = 3;
  }
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
  v8 = 1;
  v14 = CdLookupFcbTable(v13, a3, v12);
  v17 = v14;
  if ( v14 )
  {
    DesiredAccess = *(unsigned int *)(a2 + 16);
    if ( (*(_DWORD *)(v14 + 176) & 0x10) != 0 )
    {
      if ( (DesiredAccess & 0x40) != 0 )
      {
        v7 = -1073741638;
        goto LABEL_34;
      }
    }
    else if ( (DesiredAccess & 1) != 0 )
    {
      v7 = -1073741565;
      goto LABEL_34;
    }
    v8 = 0;
    if ( *a4 )
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*a4 + 200) + 32LL));
    LOBYTE(v16) = 1;
    v27 = CdAcquireResource(Context, *(_QWORD *)(v17 + 200) + 32LL, v16, 0);
    v28 = (struct _FAST_MUTEX *)(a3 + 336);
    if ( !v27 )
    {
      ++*(_DWORD *)(v17 + 164);
      *(_QWORD *)(a3 + 392) = 0;
      ExReleaseFastMutex(v28);
      CdAcquireResource(Context, *(_QWORD *)(v17 + 200) + 32LL, 0, 0);
      ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
      *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
      --*(_DWORD *)(v17 + 164);
      v28 = (struct _FAST_MUTEX *)(a3 + 336);
    }
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex(v28);
    *a4 = v17;
    DesiredAccess = *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL);
    if ( (DesiredAccess & 0x50156) == 0 )
      v7 = CdCompleteFcbOpen(Context, a2, a3, a4, v30, 1, DesiredAccess);
    goto LABEL_34;
  }
  v18 = HIDWORD(v12);
  v8 = 0;
  HIDWORD(v31) = HIDWORD(v12);
  LODWORD(v31) = 0x80000000;
  v19 = CdLookupFcbTable(v15, a3, v31);
  v21 = v19;
  if ( !v19 )
  {
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
    v22 = *(_QWORD *)(a3 + 88);
    if ( v18 <= *(_DWORD *)(v22 + 32) )
    {
      memset(P, 0, 0xC8u);
      v11 = 1;
      CdLookupPathEntry((__int64)Context, *(_DWORD *)(v22 + 480), 1, 1, (__int64)P);
      while ( (unsigned __int8)CdLookupNextPathEntry(Context, P, &P[4]) && HIDWORD(P[4]) <= v18 )
        ;
      v7 = -1073741811;
      goto LABEL_35;
    }
    goto LABEL_9;
  }
  LOBYTE(v20) = 1;
  v23 = CdAcquireResource(Context, *(_QWORD *)(v19 + 200) + 32LL, v20, 0);
  v24 = (struct _FAST_MUTEX *)(a3 + 336);
  if ( !v23 )
  {
    ++*(_DWORD *)(v21 + 164);
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex(v24);
    CdAcquireResource(Context, *(_QWORD *)(v21 + 200) + 32LL, 0, 0);
    ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
    *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
    --*(_DWORD *)(v21 + 164);
    v24 = (struct _FAST_MUTEX *)(a3 + 336);
  }
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex(v24);
  *a4 = v21;
  v25 = v12 & 0x7FFFFFFF;
  if ( !*(_QWORD *)(v21 + 472) )
    CdCreateInternalStream((__int64)Context, *(_QWORD *)(v21 + 120), v21, (UNICODE_STRING *)(v21 + 344));
  if ( v25 > *(_DWORD *)(v21 + 32) )
  {
LABEL_9:
    v7 = -1073741811;
LABEL_34:
    v11 = 0;
LABEL_35:
    v9 = 0;
    goto LABEL_36;
  }
  memset(v35, 0, sizeof(v35));
  v35[0] = &v35[12];
  v35[1] = &v35[40];
  v35[2] = &v35[68];
  WORD1(v35[5]) = 24;
  v35[6] = &v35[9];
  CdLookupDirent((__int64)Context, v21, *(_DWORD *)(v21 + 480), (__int64)&v35[40]);
  CdUpdateDirentFromRawDirent((__int64)Context, v26, v35[1], v35[1] + 32LL);
  v9 = 1;
  while ( CdLookupNextInitialFileDirent((__int64)Context, v21, (__int64)v35) && *(_DWORD *)(v35[1] + 32LL) <= v25 )
    ;
  v7 = -1073741811;
  v11 = 0;
LABEL_36:
  if ( v8 )
  {
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  }
  if ( v9 )
    CdCleanupFileContext(DesiredAccess, v35);
  if ( v11 )
  {
    if ( P[2] )
    {
      CcUnpinData(P[2]);
      P[2] = 0;
    }
    if ( BYTE4(P[3]) && P[0] )
    {
      ExFreePoolWithTag(P[0], 0);
      P[0] = 0;
    }
    if ( ((__int64)P[8] & 1) != 0 && P[10] )
      ExFreePoolWithTag(P[10], 0);
  }
  return v7;
}

```

## disassembly

```asm
0x14000dc38  push    rbx
0x14000dc3a  push    rsi
0x14000dc3b  push    rdi
0x14000dc3c  push    r12
0x14000dc3e  push    r13
0x14000dc40  push    r14
0x14000dc42  push    r15
0x14000dc44  sub     rsp, 460h
0x14000dc4b  mov     rax, cs:__security_cookie
0x14000dc52  xor     rax, rsp
0x14000dc55  mov     [rsp+498h+var_48], rax
0x14000dc5d  mov     [rsp+498h+var_448], r9
0x14000dc62  mov     rsi, r8
0x14000dc65  mov     rbx, rdx
0x14000dc68  mov     [rsp+498h+var_440], rdx
0x14000dc6d  mov     r15, rcx
0x14000dc70  mov     [rsp+498h+var_428], r8
0x14000dc75  mov     edi, 0C0000022h
0x14000dc7a  xor     r14b, r14b
0x14000dc7d  mov     [rsp+498h+var_456], r14b
0x14000dc82  xor     edx, edx; Val
0x14000dc84  mov     r8d, 300h; Size
0x14000dc8a  lea     rcx, [rsp+498h+var_348]; void *
0x14000dc92  call    memset
0x14000dc97  xor     r13b, r13b
0x14000dc9a  mov     [rsp+498h+var_458], r13b
0x14000dc9f  xor     edx, edx; Val
0x14000dca1  mov     r8d, 0C8h; Size
0x14000dca7  lea     rcx, [rsp+498h+P]; void *
0x14000dcaf  call    memset
0x14000dcb4  xor     r12b, r12b
0x14000dcb7  mov     [rsp+498h+var_457], r12b
0x14000dcbc  mov     [rsp+498h+var_450], 0
0x14000dcc5  mov     rax, [rbx+30h]
0x14000dcc9  mov     rbx, [rax+60h]
0x14000dccd  mov     rbx, [rbx]
0x14000dcd0  mov     [rsp+498h+var_438], rbx
0x14000dcd5  test    ebx, ebx
0x14000dcd7  jns     short loc_14000DCF5
0x14000dcd9  test    ebx, 7FFFFFFFh
0x14000dcdf  jz      short loc_14000DCEB
0x14000dce1  mov     edi, 0C000000Dh
0x14000dce6  jmp     loc_14000E0EC
0x14000dceb  mov     [rsp+498h+var_454], 3
0x14000dcf3  jmp     short loc_14000DCFD
0x14000dcf5  mov     [rsp+498h+var_454], 4
0x14000dcfd  lea     r12, [rsi+150h]
0x14000dd04  mov     rcx, r12; FastMutex
0x14000dd07  call    cs:__imp_ExAcquireFastMutex
0x14000dd0e  nop     dword ptr [rax+rax+00h]
0x14000dd13  mov     rax, gs:188h
0x14000dd1c  mov     [rsi+188h], rax
0x14000dd23  mov     r14b, 1
0x14000dd26  mov     [rsp+498h+var_456], r14b
0x14000dd2b  mov     r8, rbx
0x14000dd2e  mov     rdx, rsi
0x14000dd31  call    CdLookupFcbTable
0x14000dd36  mov     r13, rax
0x14000dd39  mov     [rsp+498h+var_430], rax
0x14000dd3e  test    rax, rax
0x14000dd41  jnz     loc_14000DFBC
0x14000dd47  mov     r13d, dword ptr [rsp+498h+var_438+4]
0x14000dd4c  xor     r14d, r14d
0x14000dd4f  mov     dword ptr [rsp+498h+var_450], r14d
0x14000dd54  mov     dword ptr [rsp+498h+var_450+4], r13d
0x14000dd59  mov     dword ptr [rsp+498h+var_450], 80000000h
0x14000dd61  mov     r8, [rsp+498h+var_450]
0x14000dd66  mov     rdx, rsi
0x14000dd69  call    CdLookupFcbTable
0x14000dd6e  mov     rdi, rax
0x14000dd71  mov     [rsp+498h+var_430], rax
0x14000dd76  test    rax, rax
0x14000dd79  jnz     loc_14000DE25
0x14000dd7f  mov     [rsi+188h], r14
0x14000dd86  mov     rcx, r12; FastMutex
0x14000dd89  call    cs:__imp_ExReleaseFastMutex
0x14000dd90  nop     dword ptr [rax+rax+00h]
0x14000dd95  mov     [rsp+498h+var_456], r14b
0x14000dd9a  mov     rbx, [rsi+58h]
0x14000dd9e  cmp     r13d, [rbx+20h]
0x14000dda2  jbe     short loc_14000DDAE
0x14000dda4  mov     edi, 0C000000Dh
0x14000dda9  jmp     loc_14000E0E2
0x14000ddae  xor     edx, edx; Val
0x14000ddb0  mov     r8d, 0C8h; Size
0x14000ddb6  lea     rcx, [rsp+498h+P]; void *
0x14000ddbe  call    memset
0x14000ddc3  mov     r12b, 1
0x14000ddc6  mov     [rsp+498h+var_457], r12b
0x14000ddcb  lea     rax, [rsp+498h+P]
0x14000ddd3  mov     qword ptr [rsp+498h+var_478], rax
0x14000ddd8  mov     r9b, r12b
0x14000dddb  mov     r8d, 1
0x14000dde1  mov     edx, [rbx+1E0h]
0x14000dde7  mov     rcx, r15
0x14000ddea  call    CdLookupPathEntry
0x14000ddef  lea     r8, [rsp+498h+var_3F8]
0x14000ddf7  lea     rdx, [rsp+498h+P]
0x14000ddff  mov     rcx, r15
0x14000de02  call    CdLookupNextPathEntry
0x14000de07  mov     [rsp+498h+var_455], al
0x14000de0b  test    al, al
0x14000de0d  jz      short loc_14000DE1B
0x14000de0f  cmp     [rsp+498h+var_3F4], r13d
0x14000de17  ja      short loc_14000DE1B
0x14000de19  jmp     short loc_14000DDEF
0x14000de1b  mov     edi, 0C000000Dh
0x14000de20  jmp     loc_14000E0E7
0x14000de25  mov     rdx, [rax+0C8h]
0x14000de2c  add     rdx, 20h ; ' '
0x14000de30  xor     r9d, r9d
0x14000de33  mov     r8b, 1
0x14000de36  mov     rcx, r15
0x14000de39  call    CdAcquireResource
0x14000de3e  mov     rcx, r12; FastMutex
0x14000de41  test    al, al
0x14000de43  jnz     short loc_14000DE9F
0x14000de45  inc     dword ptr [rdi+0A4h]
0x14000de4b  mov     [rsi+188h], r14
0x14000de52  call    cs:__imp_ExReleaseFastMutex
0x14000de59  nop     dword ptr [rax+rax+00h]
0x14000de5e  mov     rdx, [rdi+0C8h]
0x14000de65  add     rdx, 20h ; ' '
0x14000de69  xor     r9d, r9d
0x14000de6c  xor     r8d, r8d
0x14000de6f  mov     rcx, r15
0x14000de72  call    CdAcquireResource
0x14000de77  mov     rcx, r12; FastMutex
0x14000de7a  call    cs:__imp_ExAcquireFastMutex
0x14000de81  nop     dword ptr [rax+rax+00h]
0x14000de86  mov     rax, gs:188h
0x14000de8f  mov     [rsi+188h], rax
0x14000de96  dec     dword ptr [rdi+0A4h]
0x14000de9c  mov     rcx, r12; FastMutex
0x14000de9f  mov     [rsi+188h], r14
0x14000dea6  call    cs:__imp_ExReleaseFastMutex
0x14000dead  nop     dword ptr [rax+rax+00h]
0x14000deb2  mov     [rsp+498h+var_456], r14b
0x14000deb7  mov     rax, [rsp+498h+var_448]
0x14000debc  mov     [rax], rdi
0x14000debf  btr     ebx, 1Fh
0x14000dec3  cmp     [rdi+1D8h], r14
0x14000deca  jnz     short loc_14000DEE2
0x14000decc  lea     r9, [rdi+158h]
0x14000ded3  mov     r8, rdi
0x14000ded6  mov     rdx, [rdi+78h]
0x14000deda  mov     rcx, r15
0x14000dedd  call    CdCreateInternalStream
0x14000dee2  cmp     ebx, [rdi+20h]
0x14000dee5  ja      loc_14000DDA4
0x14000deeb  xor     edx, edx; Val
0x14000deed  mov     r8d, 300h; Size
0x14000def3  lea     rcx, [rsp+498h+var_348]; void *
0x14000defb  call    memset
0x14000df00  lea     rax, [rsp+498h+var_2E8]
0x14000df08  mov     [rsp+498h+var_348], rax
0x14000df10  lea     rax, [rsp+498h+var_208]
0x14000df18  mov     [rsp+498h+var_340], rax
0x14000df20  lea     rax, [rsp+498h+var_128]
0x14000df28  mov     [rsp+498h+var_338], rax
0x14000df30  mov     eax, 18h
0x14000df35  mov     [rsp+498h+var_31E], ax
0x14000df3d  lea     rax, [rsp+498h+var_300]
0x14000df45  mov     [rsp+498h+var_318], rax
0x14000df4d  lea     r9, [rsp+498h+var_208]
0x14000df55  mov     r8d, [rdi+1E0h]
0x14000df5c  mov     rdx, rdi
0x14000df5f  mov     rcx, r15
0x14000df62  call    CdLookupDirent
0x14000df67  mov     r8, [rsp+498h+var_340]
0x14000df6f  lea     r9, [r8+20h]
0x14000df73  mov     rcx, r15
0x14000df76  call    CdUpdateDirentFromRawDirent
0x14000df7b  mov     r13b, 1
0x14000df7e  mov     [rsp+498h+var_458], r13b
0x14000df83  lea     r8, [rsp+498h+var_348]
0x14000df8b  mov     rdx, rdi
0x14000df8e  mov     rcx, r15
0x14000df91  call    CdLookupNextInitialFileDirent
0x14000df96  mov     [rsp+498h+var_455], al
0x14000df9a  test    al, al
0x14000df9c  jz      short loc_14000DFAD
0x14000df9e  mov     rax, [rsp+498h+var_340]
0x14000dfa6  cmp     [rax+20h], ebx
0x14000dfa9  ja      short loc_14000DFAD
0x14000dfab  jmp     short loc_14000DF83
0x14000dfad  mov     edi, 0C000000Dh
0x14000dfb2  mov     r12b, [rsp+498h+var_457]
0x14000dfb7  jmp     loc_14000E0EC
0x14000dfbc  mov     rcx, [rsp+498h+var_440]
0x14000dfc1  mov     ecx, [rcx+10h]
0x14000dfc4  mov     eax, [rax+0B0h]
0x14000dfca  test    al, 10h
0x14000dfcc  jz      short loc_14000DFDD
0x14000dfce  test    cl, 40h
0x14000dfd1  jz      short loc_14000DFEC
0x14000dfd3  mov     edi, 0C00000BAh
0x14000dfd8  jmp     loc_14000E0E2
0x14000dfdd  test    r14b, cl
0x14000dfe0  jz      short loc_14000DFEC
0x14000dfe2  mov     edi, 0C0000103h
0x14000dfe7  jmp     loc_14000E0E2
0x14000dfec  mov     rbx, [rsp+498h+var_448]
0x14000dff1  mov     rcx, [rbx]
0x14000dff4  xor     r14d, r14d
0x14000dff7  test    rcx, rcx
0x14000dffa  jz      short loc_14000E013
0x14000dffc  mov     rcx, [rcx+0C8h]
0x14000e003  add     rcx, 20h ; ' '; Resource
0x14000e007  call    cs:__imp_ExReleaseResourceLite
0x14000e00e  nop     dword ptr [rax+rax+00h]
0x14000e013  mov     rdx, [r13+0C8h]
0x14000e01a  add     rdx, 20h ; ' '
0x14000e01e  xor     r9d, r9d
0x14000e021  mov     r8b, 1
0x14000e024  mov     rcx, r15
0x14000e027  call    CdAcquireResource
0x14000e02c  mov     rcx, r12; FastMutex
0x14000e02f  test    al, al
0x14000e031  jnz     short loc_14000E08F
0x14000e033  inc     dword ptr [r13+0A4h]
0x14000e03a  mov     [rsi+188h], r14
0x14000e041  call    cs:__imp_ExReleaseFastMutex
0x14000e048  nop     dword ptr [rax+rax+00h]
0x14000e04d  mov     rdx, [r13+0C8h]
0x14000e054  add     rdx, 20h ; ' '
0x14000e058  xor     r9d, r9d
0x14000e05b  xor     r8d, r8d
0x14000e05e  mov     rcx, r15
0x14000e061  call    CdAcquireResource
0x14000e066  mov     rcx, r12; FastMutex
0x14000e069  call    cs:__imp_ExAcquireFastMutex
0x14000e070  nop     dword ptr [rax+rax+00h]
0x14000e075  mov     rax, gs:188h
0x14000e07e  mov     [rsi+188h], rax
0x14000e085  dec     dword ptr [r13+0A4h]
0x14000e08c  mov     rcx, r12; FastMutex
0x14000e08f  mov     [rsi+188h], r14
0x14000e096  call    cs:__imp_ExReleaseFastMutex
0x14000e09d  nop     dword ptr [rax+rax+00h]
0x14000e0a2  mov     [rsp+498h+var_456], r14b
0x14000e0a7  mov     [rbx], r13
0x14000e0aa  mov     rdx, [rsp+498h+var_440]
0x14000e0af  mov     rax, [rdx+8]
0x14000e0b3  mov     ecx, [rax+10h]
0x14000e0b6  test    ecx, 50156h
0x14000e0bc  jnz     short loc_14000E0E2
0x14000e0be  mov     [rsp+498h+DesiredAccess], ecx; DesiredAccess
0x14000e0c2  mov     [rsp+498h+var_470], 1; int
0x14000e0ca  mov     eax, [rsp+498h+var_454]
0x14000e0ce  mov     [rsp+498h+var_478], eax; int
0x14000e0d2  mov     r9, rbx
0x14000e0d5  mov     r8, rsi
0x14000e0d8  mov     rcx, r15; Context
0x14000e0db  call    CdCompleteFcbOpen
0x14000e0e0  mov     edi, eax
0x14000e0e2  mov     r12b, [rsp+498h+var_457]
0x14000e0e7  mov     r13b, [rsp+498h+var_458]
0x14000e0ec  test    r14b, r14b
0x14000e0ef  jz      short loc_14000E10F
0x14000e0f1  mov     qword ptr [rsi+188h], 0
0x14000e0fc  lea     rcx, [rsi+150h]; FastMutex
0x14000e103  call    cs:__imp_ExReleaseFastMutex
0x14000e10a  nop     dword ptr [rax+rax+00h]
0x14000e10f  test    r13b, r13b
0x14000e112  jz      short loc_14000E121
0x14000e114  lea     rdx, [rsp+498h+var_348]
0x14000e11c  call    CdCleanupFileContext
0x14000e121  test    r12b, r12b
0x14000e124  jz      short loc_14000E1A1
0x14000e126  mov     rcx, [rsp+498h+Bcb]; Bcb
0x14000e12e  test    rcx, rcx
0x14000e131  jz      short loc_14000E14B
0x14000e133  call    cs:__imp_CcUnpinData
0x14000e13a  nop     dword ptr [rax+rax+00h]
0x14000e13f  mov     [rsp+498h+Bcb], 0
0x14000e14b  cmp     [rsp+498h+var_3FC], 0
0x14000e153  jz      short loc_14000E17C
0x14000e155  mov     rcx, [rsp+498h+P]; P
0x14000e15d  test    rcx, rcx
0x14000e160  jz      short loc_14000E17C
0x14000e162  xor     edx, edx; Tag
0x14000e164  call    cs:__imp_ExFreePoolWithTag
0x14000e16b  nop     dword ptr [rax+rax+00h]
0x14000e170  mov     [rsp+498h+P], 0
0x14000e17c  test    [rsp+498h+var_3D8], 1
0x14000e184  jz      short loc_14000E1A1
0x14000e186  mov     rcx, [rsp+498h+var_3C8]; P
0x14000e18e  test    rcx, rcx
0x14000e191  jz      short loc_14000E1A1
0x14000e193  xor     edx, edx; Tag
0x14000e195  call    cs:__imp_ExFreePoolWithTag
0x14000e19c  nop     dword ptr [rax+rax+00h]
0x14000e1a1  mov     eax, edi
0x14000e1a3  mov     rcx, [rsp+498h+var_48]
0x14000e1ab  xor     rcx, rsp; StackCookie
0x14000e1ae  call    __security_check_cookie
0x14000e1b3  add     rsp, 460h
0x14000e1ba  pop     r15
0x14000e1bc  pop     r14
  ... truncated ...
```
