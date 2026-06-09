# SmbCeInitializeExchange

- ea: `0x1400181f0`
- end: `0x14001866b`
- name: `SmbCeInitializeExchange`
- size: `1147`
- prototype: `__int64 __fastcall(char **, __int64, __int64, _DWORD *, __int64, __int64, unsigned int Size, __int64 (__fastcall **)())`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002c7f0`
- `0x14002eeb0`

## callees

- `0x140003480`
- `0x140013540`
- `0x1400135e0`
- `0x1400181f0`
- `0x140018680`
- `0x1400221e0`
- `0x140037eb0`
- `0x140038460`
- `0x14003e684`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005df00`
- `ntoskrnl!KeInitializeEvent` at `0x14005df00`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001841e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001841e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001825a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001825a`
- `ntoskrnl!ExAllocatePool2` at `0x140018553`
- `ntoskrnl!ExAllocatePool2` at `0x140018553`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001862c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001862c`

## pseudocode

```c
__int64 __fastcall SmbCeInitializeExchange(
        char **a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        unsigned int Size,
        __int64 (__fastcall **a8)())
{
  char *Pool2; // rbx
  size_t v13; // r15
  int v14; // r13d
  int v15; // edx
  __int64 v16; // r14
  __int64 (__fastcall **v17)(); // rax
  unsigned int v18; // edx
  int v19; // eax
  int v20; // eax
  int v21; // ecx
  int v22; // edx
  int v23; // eax
  int v24; // r8d
  int v25; // ecx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // edx
  int v30; // ecx
  int LockArray_high; // r15d
  struct _LOOKASIDE_LIST_EX *v32; // rbx
  char *v33; // rbx
  __int64 v35; // rcx
  __int64 v36; // rax
  char v37; // cl
  int v38; // eax
  KIRQL v39; // di
  int v40; // eax
  __int64 v41; // r8
  __int16 v42; // [rsp+50h] [rbp-58h]
  int v43; // [rsp+B0h] [rbp+8h]

  Pool2 = *a1;
  v42 = 0;
  if ( *a1 )
  {
    v43 = 2;
    v13 = Size;
    v14 = 0;
    goto LABEL_3;
  }
  if ( Size > 0x1000 )
  {
    v14 = 0;
    v43 = 0;
    v13 = Size;
    Pool2 = (char *)ExAllocatePool2(66, Size, 1834181464);
  }
  else
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v32 = (struct _LOOKASIDE_LIST_EX *)((char *)SmbMmExchangeLookasideList
                                      + 128 * (unsigned __int64)(unsigned __int16)LockArray_high);
    if ( !LOBYTE(v32[3].L.Depth) )
      PplpLazyInitializeLookasideList((__int64)SmbMmExchangeLookasideList, (__int64)&v32[2]);
    v33 = (char *)ExAllocateFromLookasideListEx(v32 + 2);
    if ( !v33 )
      return 3221225626LL;
    v42 = LockArray_high;
    v14 = 4;
    v43 = 4;
    Pool2 = &v33[-((Size + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 4096];
    v13 = Size;
  }
  if ( !Pool2 )
    return 3221225626LL;
LABEL_3:
  memset(Pool2, 0, v13);
  *(_WORD *)Pool2 = -7424;
  *((_WORD *)Pool2 + 1) = Size;
  *((_DWORD *)Pool2 + 1) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)Pool2 + 3);
  if ( a3 )
  {
    SmbCeReferenceBindingObject(a3);
    *((_QWORD *)Pool2 + 12) = a3;
  }
  if ( a6 )
  {
    *((_QWORD *)Pool2 + 11) = a6;
    *((_QWORD *)Pool2 + 10) = *(_QWORD *)(a6 + 416);
    a4 = *(_DWORD **)(*(_QWORD *)(a6 + 416) + 384LL);
    *((_QWORD *)Pool2 + 9) = a4;
    SmbCeReferenceVNetRootContext(a6);
    v15 = *(_DWORD *)(a6 + 264);
  }
  else if ( a5 )
  {
    *((_QWORD *)Pool2 + 10) = a5;
    a4 = *(_DWORD **)(a5 + 384);
    *((_QWORD *)Pool2 + 9) = a4;
    SmbCeReferenceSessionEntry(a5);
    v15 = *(_DWORD *)(a5 + 264);
  }
  else
  {
    *((_QWORD *)Pool2 + 9) = a4;
    SmbCeReferenceServerEntry((ULONG_PTR)a4);
    v15 = a4[98];
  }
  v16 = *(_QWORD *)(*((_QWORD *)Pool2 + 9) + 24LL);
  v17 = &Smb2NoOpExchangeDispatch;
  if ( a8 )
    v17 = a8;
  *((_QWORD *)Pool2 + 6) = a2;
  *((_QWORD *)Pool2 + 29) = v17;
  *((_DWORD *)Pool2 + 10) = 0;
  *((_DWORD *)Pool2 + 17) = v43;
  if ( v14 )
    *((_WORD *)Pool2 + 17) = v42;
  *((_QWORD *)Pool2 + 25) = MEMORY[0xFFFFF78000000008];
  if ( !a2 )
    goto LABEL_62;
  *(_QWORD *)(a2 + 216) = Pool2;
  v18 = v15 & 0xFFFFFFFE;
  v19 = *(_DWORD *)(v16 + 2348);
  if ( v19 )
    v20 = 2 * v19;
  else
    v20 = 4;
  *((_DWORD *)Pool2 + 55) = v18 + v20;
  v21 = *(_DWORD *)(v16 + 2348);
  v22 = a4[158];
  v23 = a4[175];
  v24 = a4[152];
  if ( v21 )
    v25 = v22 + v24 + v23 + v21 + 2;
  else
    v25 = v22 + v24 + v23 + 4;
  *((_DWORD *)Pool2 + 56) = v25;
  v26 = *(_QWORD *)(a2 + 64);
  if ( v26 )
  {
    if ( (*(_DWORD *)(v26 + 72) & 1) != 0 )
      _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x8000u);
    v36 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 56LL);
    if ( v36 && (*(_DWORD *)(v36 + 4) & 2) != 0 )
      goto LABEL_43;
    if ( !*(_BYTE *)(*(_QWORD *)(*((_QWORD *)Pool2 + 9) + 24LL) + 1312LL) )
    {
      v37 = qword_14007D1E6;
      if ( (qword_14007D1E6 & 8) == 0 )
        v37 = word_14007D1CA;
      if ( (v37 & 1) != 0 )
LABEL_43:
        _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x4000000u);
    }
  }
  v27 = *(_QWORD *)(a2 + 72);
  if ( !v27 )
  {
    v40 = *(_DWORD *)(a6 + 448);
    if ( (v40 & 0x400) != 0 )
    {
      _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x1000000u);
    }
    else if ( (v40 & 0x200) != 0 )
    {
      _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x800u);
    }
    goto LABEL_24;
  }
  v28 = *(_QWORD *)(v27 + 48);
  if ( v28 )
  {
    v29 = *(_DWORD *)(v28 + 8);
    if ( (v29 & 0x400) == 0 )
    {
      v35 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 136LL);
      if ( !*(_DWORD *)(v35 + 76) )
      {
        if ( (v29 & 0x200) == 0 && !*(_DWORD *)(v35 + 72) )
          goto LABEL_21;
        goto LABEL_34;
      }
    }
LABEL_20:
    _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x1000000u);
    goto LABEL_21;
  }
  v38 = *(_DWORD *)(a6 + 448);
  if ( (v38 & 0x400) != 0 )
    goto LABEL_20;
  if ( (v38 & 0x200) != 0 )
LABEL_34:
    _InterlockedOr((volatile signed __int32 *)Pool2 + 17, 0x800u);
LABEL_21:
  v30 = *(_DWORD *)(*((_QWORD *)Pool2 + 10) + 576LL);
  if ( v30 != -1 && dword_14007D09C != v30 )
  {
    v39 = SmbCeAcquireSpinLock(v16);
    SmbCeRecoverSessionEntryLite(*((_QWORD *)Pool2 + 10), 3221226332LL);
    *(_DWORD *)(v16 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v16 + 1920), v39);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 56) + 232LL) & 0x1000) != 0 )
    *((_DWORD *)Pool2 + 54) = dword_14007D094;
LABEL_24:
  *(_OWORD *)(Pool2 + 312) = *(_OWORD *)(a2 + 412);
  Pool2[33] = *(_BYTE *)(a2 + 170);
LABEL_62:
  *((_QWORD *)Pool2 + 21) = Pool2 + 160;
  *((_QWORD *)Pool2 + 20) = Pool2 + 160;
  *((_QWORD *)Pool2 + 19) = Pool2 + 144;
  *((_QWORD *)Pool2 + 18) = Pool2 + 144;
  *((_QWORD *)Pool2 + 17) = Pool2 + 128;
  *((_QWORD *)Pool2 + 16) = Pool2 + 128;
  *((_QWORD *)Pool2 + 15) = 0;
  KeInitializeEvent((PRKEVENT)(Pool2 + 176), NotificationEvent, 0);
  _InterlockedIncrement((volatile signed __int32 *)(v16 + 2600));
  *a1 = Pool2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqqqq(
      WPP_GLOBAL_Control->AttachedDevice,
      *((_QWORD *)Pool2 + 6),
      v41,
      Pool2,
      *((_QWORD *)Pool2 + 6),
      *((_QWORD *)Pool2 + 12),
      *((_QWORD *)Pool2 + 10),
      *((_QWORD *)Pool2 + 11),
      *((_QWORD *)Pool2 + 9));
  }
  return 0;
}

```

## disassembly

```asm
0x1400181f0  push    rbx
0x1400181f2  push    rbp
0x1400181f3  push    rsi
0x1400181f4  push    rdi
0x1400181f5  push    r12
0x1400181f7  push    r13
0x1400181f9  push    r14
0x1400181fb  push    r15
0x1400181fd  sub     rsp, 68h
0x140018201  mov     rbx, [rcx]
0x140018204  mov     rbp, r9
0x140018207  mov     edi, dword ptr [rsp+0A8h+Size]
0x14001820e  mov     r14, r8
0x140018211  mov     dword ptr [rsp+0A8h+var_58], 0
0x140018219  mov     rsi, rdx
0x14001821c  mov     r12, rcx
0x14001821f  test    rbx, rbx
0x140018222  jz      loc_1400183E1
0x140018228  mov     [rsp+0A8h+arg_0], 2
0x140018233  mov     r15d, edi
0x140018236  xor     r13d, r13d
0x140018239  mov     r8, r15; Size
0x14001823c  xor     edx, edx; Val
0x14001823e  mov     rcx, rbx; void *
0x140018241  call    memset
0x140018246  lea     rcx, [rbx+18h]; SpinLock
0x14001824a  mov     word ptr [rbx], 0E300h
0x14001824f  mov     [rbx+2], di
0x140018253  mov     dword ptr [rbx+4], 1
0x14001825a  call    cs:__imp_KeInitializeSpinLock
0x140018261  nop     dword ptr [rax+rax+00h]
0x140018266  test    r14, r14
0x140018269  jnz     loc_140018564
0x14001826f  mov     rdi, [rsp+0A8h+arg_28]
0x140018277  test    rdi, rdi
0x14001827a  jz      loc_140018575
0x140018280  mov     [rbx+58h], rdi
0x140018284  mov     rcx, rdi
0x140018287  mov     rax, [rdi+1A0h]
0x14001828e  mov     [rbx+50h], rax
0x140018292  mov     rax, [rdi+1A0h]
0x140018299  mov     rbp, [rax+180h]
0x1400182a0  mov     [rbx+48h], rbp
0x1400182a4  call    SmbCeReferenceVNetRootContext
0x1400182a9  mov     edx, [rdi+108h]
0x1400182af  mov     rax, [rbx+48h]
0x1400182b3  xor     r15d, r15d
0x1400182b6  mov     rcx, [rsp+0A8h+arg_38]
0x1400182be  test    rcx, rcx
0x1400182c1  mov     r14, [rax+18h]
0x1400182c5  lea     rax, Smb2NoOpExchangeDispatch
0x1400182cc  cmovnz  rax, rcx
0x1400182d0  mov     [rbx+30h], rsi
0x1400182d4  mov     [rbx+0E8h], rax
0x1400182db  mov     eax, [rsp+0A8h+arg_0]
0x1400182e2  mov     [rbx+28h], r15d
0x1400182e6  mov     [rbx+44h], eax
0x1400182e9  test    r13d, r13d
0x1400182ec  jnz     loc_1400185A9
0x1400182f2  mov     rax, ds:0FFFFF78000000008h
0x1400182fc  mov     [rbx+0C8h], rax
0x140018303  test    rsi, rsi
0x140018306  jz      loc_14005DEC6
0x14001830c  mov     [rsi+0D8h], rbx
0x140018313  and     edx, 0FFFFFFFEh
0x140018316  mov     eax, [r14+92Ch]
0x14001831d  test    eax, eax
0x14001831f  jz      loc_14001844D
0x140018325  add     eax, eax
0x140018327  add     eax, edx
0x140018329  mov     [rbx+0DCh], eax
0x14001832f  mov     ecx, [r14+92Ch]
0x140018336  mov     edx, [rbp+278h]
0x14001833c  mov     eax, [rbp+2BCh]
0x140018342  mov     r8d, [rbp+260h]
0x140018349  test    ecx, ecx
0x14001834b  jz      loc_140018457
0x140018351  add     eax, r8d
0x140018354  add     ecx, 2
0x140018357  add     eax, edx
0x140018359  add     ecx, eax
0x14001835b  mov     [rbx+0E0h], ecx
0x140018361  mov     rax, [rsi+40h]
0x140018365  test    rax, rax
0x140018368  jnz     loc_140018491
0x14001836e  mov     rax, [rsi+48h]
0x140018372  test    rax, rax
0x140018375  jz      loc_14001864E
0x14001837b  mov     rcx, [rax+30h]
0x14001837f  test    rcx, rcx
0x140018382  jz      loc_1400185D2
0x140018388  mov     edx, [rcx+8]
0x14001838b  bt      edx, 0Ah
0x14001838f  jnb     loc_140018465
0x140018395  lock or dword ptr [rbx+44h], 1000000h
0x14001839d  mov     rax, [rbx+50h]
0x1400183a1  mov     ecx, [rax+240h]
0x1400183a7  cmp     ecx, 0FFFFFFFFh
0x1400183aa  jnz     loc_1400185F1
0x1400183b0  mov     rax, [rsi+38h]
0x1400183b4  test    dword ptr [rax+0E8h], 1000h
0x1400183be  jnz     loc_14001863D
0x1400183c4  movups  xmm0, xmmword ptr [rsi+19Ch]
0x1400183cb  movups  xmmword ptr [rbx+138h], xmm0
0x1400183d2  movzx   eax, byte ptr [rsi+0AAh]
0x1400183d9  mov     [rbx+21h], al
0x1400183dc  jmp     loc_14005DEC6
0x1400183e1  cmp     edi, 1000h
0x1400183e7  ja      loc_140018537
0x1400183ed  mov     r15d, gs:1A4h
0x1400183f6  mov     rcx, cs:SmbMmExchangeLookasideList
0x1400183fd  movzx   ebx, r15w
0x140018401  shl     rbx, 7
0x140018405  add     rbx, rcx
0x140018408  movzx   eax, byte ptr [rbx+130h]
0x14001840f  test    al, al
0x140018411  jz      loc_1400184ED
0x140018417  lea     rcx, [rbx+0C0h]; Lookaside
0x14001841e  call    cs:__imp_ExAllocateFromLookasideListEx
0x140018425  nop     dword ptr [rax+rax+00h]
0x14001842a  mov     rbx, rax
0x14001842d  test    rax, rax
0x140018430  jnz     loc_14001850C
0x140018436  mov     eax, 0C000009Ah
0x14001843b  add     rsp, 68h
0x14001843f  pop     r15
0x140018441  pop     r14
0x140018443  pop     r13
0x140018445  pop     r12
0x140018447  pop     rdi
0x140018448  pop     rsi
0x140018449  pop     rbp
0x14001844a  pop     rbx
0x14001844b  retn
0x14001844d  mov     eax, 4
0x140018452  jmp     loc_140018327
0x140018457  lea     ecx, [r8+rax]
0x14001845b  add     ecx, 4
0x14001845e  add     ecx, edx
0x140018460  jmp     loc_14001835B
0x140018465  mov     rax, [rsi+38h]
0x140018469  mov     rcx, [rax+88h]
0x140018470  cmp     [rcx+4Ch], r15d
0x140018474  ja      loc_140018395
0x14001847a  bt      edx, 9
0x14001847e  jnb     loc_1400185C3
0x140018484  lock or dword ptr [rbx+44h], 800h
0x14001848c  jmp     loc_14001839D
0x140018491  mov     eax, [rax+48h]
0x140018494  test    al, 1
0x140018496  jnz     loc_1400185B6
0x14001849c  mov     rax, [rsi+40h]
0x1400184a0  mov     rax, [rax+38h]
0x1400184a4  test    rax, rax
0x1400184a7  jz      short loc_1400184B0
0x1400184a9  mov     eax, [rax+4]
0x1400184ac  test    al, 2
0x1400184ae  jnz     short loc_1400184E0
0x1400184b0  mov     rax, [rbx+48h]
0x1400184b4  mov     rcx, [rax+18h]
0x1400184b8  cmp     [rcx+520h], r15b
0x1400184bf  jnz     loc_14001836E
0x1400184c5  mov     rcx, cs:qword_14007D1E6
0x1400184cc  test    cl, 8
0x1400184cf  cmovz   cx, cs:word_14007D1CA
0x1400184d7  test    cl, 1
0x1400184da  jz      loc_14001836E
0x1400184e0  lock or dword ptr [rbx+44h], 4000000h
0x1400184e8  jmp     loc_14001836E
0x1400184ed  lea     rdx, [rbx+0C0h]
0x1400184f4  call    PplpLazyInitializeLookasideList
0x1400184f9  jmp     loc_140018417
0x1400184fe  test    rbx, rbx
0x140018501  jnz     loc_140018239
0x140018507  jmp     loc_140018436
0x14001850c  lea     rax, [rdi+7]
0x140018510  mov     [rsp+0A8h+var_58], r15w
0x140018516  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001851a  mov     r13d, 4
0x140018520  sub     rbx, rax
0x140018523  mov     [rsp+0A8h+arg_0], r13d
0x14001852b  add     rbx, 1000h
0x140018532  mov     r15, rdi
0x140018535  jmp     short loc_1400184FE
0x140018537  xor     r13d, r13d
0x14001853a  mov     r8d, 6D536358h
0x140018540  mov     rdx, rdi
0x140018543  mov     [rsp+0A8h+arg_0], r13d
0x14001854b  mov     ecx, 42h ; 'B'
0x140018550  mov     r15, rdi
0x140018553  call    cs:__imp_ExAllocatePool2
0x14001855a  nop     dword ptr [rax+rax+00h]
0x14001855f  mov     rbx, rax
0x140018562  jmp     short loc_1400184FE
0x140018564  mov     rcx, r14
0x140018567  call    SmbCeReferenceBindingObject
0x14001856c  mov     [rbx+60h], r14
0x140018570  jmp     loc_14001826F
0x140018575  mov     r14, [rsp+0A8h+arg_20]
0x14001857d  test    r14, r14
0x140018580  jz      loc_14005DE98
0x140018586  mov     [rbx+50h], r14
0x14001858a  mov     rcx, r14
0x14001858d  mov     rbp, [r14+180h]
0x140018594  mov     [rbx+48h], rbp
0x140018598  call    SmbCeReferenceSessionEntry
0x14001859d  mov     edx, [r14+108h]
0x1400185a4  jmp     loc_1400182AF
0x1400185a9  mov     eax, dword ptr [rsp+0A8h+var_58]
0x1400185ad  mov     [rbx+22h], ax
0x1400185b1  jmp     loc_1400182F2
0x1400185b6  lock or dword ptr [rbx+44h], 8000h
0x1400185be  jmp     loc_14001849C
0x1400185c3  cmp     [rcx+48h], r15d
0x1400185c7  jbe     loc_14001839D
0x1400185cd  jmp     loc_140018484
0x1400185d2  mov     eax, [rdi+1C0h]
0x1400185d8  bt      eax, 0Ah
0x1400185dc  jb      loc_140018395
0x1400185e2  bt      eax, 9
0x1400185e6  jnb     loc_14001839D
0x1400185ec  jmp     loc_140018484
0x1400185f1  cmp     cs:dword_14007D09C, ecx
0x1400185f7  jz      loc_1400183B0
0x1400185fd  mov     rcx, r14
0x140018600  call    SmbCeAcquireSpinLock
0x140018605  mov     rcx, [rbx+50h]
0x140018609  mov     edx, 0C000035Ch
0x14001860e  movzx   edi, al
0x140018611  call    SmbCeRecoverSessionEntryLite
0x140018616  lea     rcx, [r14+780h]; SpinLock
0x14001861d  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x140018628  movzx   edx, dil; OldIrql
0x14001862c  call    cs:__imp_ExReleaseSpinLockExclusive
0x140018633  nop     dword ptr [rax+rax+00h]
0x140018638  jmp     loc_1400183B0
0x14001863d  mov     eax, cs:dword_14007D094
0x140018643  mov     [rbx+0D8h], eax
0x140018649  jmp     loc_1400183C4
0x14001864e  mov     eax, [rdi+1C0h]
0x140018654  bt      eax, 0Ah
0x140018658  jnb     loc_14005DEAF
0x14001865e  lock or dword ptr [rbx+44h], 1000000h
0x140018666  jmp     loc_1400183C4
0x14005de98  mov     rcx, rbp; BugCheckParameter2
0x14005de9b  mov     [rbx+48h], rbp
0x14005de9f  call    SmbCeReferenceServerEntry
0x14005dea4  mov     edx, [rbp+188h]
0x14005deaa  jmp     loc_1400182AF
0x14005deaf  bt      eax, 9
0x14005deb3  jnb     loc_1400183C4
0x14005deb9  lock or dword ptr [rbx+44h], 800h
0x14005dec1  jmp     loc_1400183C4
0x14005dec6  lea     rax, [rbx+0A0h]
0x14005decd  xor     r8d, r8d; State
0x14005ded0  mov     [rax+8], rax
0x14005ded4  lea     rcx, [rbx+0B0h]; Event
0x14005dedb  mov     [rax], rax
0x14005dede  xor     edx, edx; Type
0x14005dee0  lea     rax, [rbx+90h]
0x14005dee7  mov     [rax+8], rax
0x14005deeb  mov     [rax], rax
0x14005deee  lea     rax, [rbx+80h]
0x14005def5  mov     [rax+8], rax
0x14005def9  mov     [rax], rax
0x14005defc  mov     [rbx+78h], r15
0x14005df00  call    cs:__imp_KeInitializeEvent
0x14005df07  nop     dword ptr [rax+rax+00h]
0x14005df0c  lock inc dword ptr [r14+0A28h]
0x14005df14  mov     [r12], rbx
0x14005df18  mov     rcx, cs:WPP_GLOBAL_Control
0x14005df1f  lea     rax, WPP_GLOBAL_Control
0x14005df26  cmp     rcx, rax
0x14005df29  jz      short loc_14005DF71
0x14005df2b  mov     eax, [rcx+2Ch]
0x14005df2e  test    al, 10h
0x14005df30  jz      short loc_14005DF71
0x14005df32  cmp     byte ptr [rcx+29h], 4
0x14005df36  jb      short loc_14005DF71
0x14005df38  mov     rdx, [rbx+48h]
0x14005df3c  mov     r9, rbx
0x14005df3f  mov     rcx, [rcx+18h]
0x14005df43  mov     [rsp+0A8h+var_68], rdx
0x14005df48  mov     rdx, [rbx+58h]
0x14005df4c  mov     [rsp+0A8h+var_70], rdx
0x14005df51  mov     rdx, [rbx+50h]
0x14005df55  mov     [rsp+0A8h+var_78], rdx
0x14005df5a  mov     rdx, [rbx+60h]
0x14005df5e  mov     [rsp+0A8h+var_80], rdx
0x14005df63  mov     rdx, [rbx+30h]
0x14005df67  mov     [rsp+0A8h+var_88], rdx
0x14005df6c  call    WPP_SF_qqqqqq
0x14005df71  xor     eax, eax
0x14005df73  jmp     loc_14001843B
```
