# NcmCreateNotificationChannelContext

- ea: `0x14002ebb4`
- end: `0x14002ef1c`
- name: `NcmCreateNotificationChannelContext`
- size: `872`
- prototype: `__int64 __fastcall(struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *P, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002fb0c`

## callees

- `0x14002ebb4`
- `0x14002ef30`
- `0x14002fca8`
- `0x140050ea4`
- `0x14005cfd0`
- `0x140078100`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002ee6e`
- `ntoskrnl!KeInitializeEvent` at `0x14002ee6e`
- `ntoskrnl!wcsnlen` at `0x14002ec0c`
- `ntoskrnl!wcsnlen` at `0x14002ec95`
- `ntoskrnl!wcsnlen` at `0x14002eea9`
- `ntoskrnl!wcsnlen` at `0x14002ec0c`
- `ntoskrnl!wcsnlen` at `0x14002ec95`
- `ntoskrnl!wcsnlen` at `0x14002eea9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002edc1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14007c322`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002edc1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14007c322`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14002ecd9`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14002ed35`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14002ecd9`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14002ed35`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14007c2fa`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14007c2fa`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002ec43`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002ec43`
- `ntoskrnl!ExAllocatePool2` at `0x14002ec69`
- `ntoskrnl!ExAllocatePool2` at `0x14002ecf3`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed54`
- `ntoskrnl!ExAllocatePool2` at `0x14002ec69`
- `ntoskrnl!ExAllocatePool2` at `0x14002ecf3`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002edd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c333`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002edd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c333`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002ee3e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002ee3e`

## pseudocode

```c
__int64 __fastcall NcmCreateNotificationChannelContext(
        struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *P,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 Pool2; // rdi
  char v5; // r12
  char v6; // r15
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v9; // rsi
  unsigned int v10; // ebx
  const wchar_t *v11; // r14
  int v12; // eax
  ULONG_PTR v13; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  size_t v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // ebp
  struct _LIST_ENTRY *Flink; // rax
  ULONG_PTR *p_Signature; // rsi
  size_t v23; // rax
  int v24; // edx
  __int128 v25; // xmm1
  bool v26; // cf
  unsigned int v27; // edx
  unsigned int v28; // ecx
  __int64 v29; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+50h] [rbp-68h] BYREF

  Pool2 = 0;
  v5 = 0;
  v6 = 0;
  v9 = P;
  memset(&Context, 0, sizeof(Context));
  if ( !P )
  {
    v10 = *(_DWORD *)(a4 + 128);
    v11 = (const wchar_t *)(a4 + 132);
    v12 = wcsnlen((const wchar_t *)(a4 + 132), 0x104u);
    v13 = (unsigned int)RtlCompute37Hash(v10, v11, (unsigned int)(2 * v12)) | 0x80000000;
    *(_OWORD *)&Context.ChainHead = 0;
    for ( i = RtlLookupEntryHashTable(&stru_14009B008, v13, &Context);
          ;
          i = RtlGetNextEntryHashTable(&stru_14009B008, &Context) )
    {
      Pool2 = (__int64)i;
      if ( !i )
        break;
      if ( *(_DWORD *)(a4 + 128) == HIDWORD(i[1].Linkage.Flink) )
      {
        v23 = wcsnlen(v11, 0x104u);
        if ( !wmemcmp((const wchar_t *)(Pool2 + 32), v11, v23) )
          goto LABEL_6;
      }
    }
    Pool2 = ExAllocatePool2(64, 568, 1835232846);
    if ( !Pool2 )
      goto LABEL_9;
    *(_DWORD *)(Pool2 + 28) = *(_DWORD *)(a4 + 128);
    v5 = 1;
    v15 = wcsnlen(v11, 0x104u);
    memmove((void *)(Pool2 + 32), v11, 2 * v15);
    *(_DWORD *)(Pool2 + 552) = *(_DWORD *)(a4 + 664);
    *(_DWORD *)(Pool2 + 556) = *(_DWORD *)(a4 + 668);
    RtlInsertEntryHashTable(&stru_14009B008, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Pool2, v13, 0);
LABEL_6:
    v16 = ExAllocatePool2(64, 56, 1835232846);
    v9 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)v16;
    if ( !v16 )
      goto LABEL_9;
    *(_DWORD *)(v16 + 24) = *(_DWORD *)a3;
    *(_QWORD *)(v16 + 32) = Pool2;
    *(_QWORD *)(v16 + 48) = v16 + 40;
    v6 = 1;
    *(_QWORD *)(v16 + 40) = v16 + 40;
    RtlInsertEntryHashTable(&stru_14009B030, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v16, a2, 0);
    ++*(_DWORD *)(Pool2 + 24);
  }
  v17 = ExAllocatePool2(64, 304, 1835232846);
  v18 = v17;
  if ( !v17 )
  {
LABEL_9:
    v19 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids, 3221225626LL);
    }
    if ( v6 )
    {
      RtlRemoveEntryHashTable(&stru_14009B030, v9, 0);
      ExFreePoolWithTag(v9, 0);
      --*(_DWORD *)(Pool2 + 24);
    }
    if ( v5 )
    {
      RtlRemoveEntryHashTable(&stru_14009B008, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Pool2, 0);
      ExFreePoolWithTag((PVOID)Pool2, 0);
    }
    return v19;
  }
  *(_QWORD *)(v17 + 16) = 1;
  *(_QWORD *)(v17 + 40) = *(_QWORD *)(a3 + 8);
  v24 = *(_DWORD *)(v17 + 264) ^ ((unsigned __int8)*(_DWORD *)(v17 + 264) ^ *(_BYTE *)(a4 + 704)) & 1;
  *(_DWORD *)(v17 + 264) = v24;
  *(_OWORD *)(v17 + 56) = *(_OWORD *)(a4 + 672);
  *(_OWORD *)(v17 + 88) = *(_OWORD *)a4;
  *(_OWORD *)(v17 + 104) = *(_OWORD *)(a4 + 16);
  *(_OWORD *)(v17 + 120) = *(_OWORD *)(a4 + 32);
  *(_OWORD *)(v17 + 136) = *(_OWORD *)(a4 + 48);
  *(_OWORD *)(v17 + 152) = *(_OWORD *)(a4 + 64);
  *(_OWORD *)(v17 + 168) = *(_OWORD *)(a4 + 80);
  *(_OWORD *)(v17 + 184) = *(_OWORD *)(a4 + 96);
  v25 = *(_OWORD *)(a4 + 112);
  *(_DWORD *)(v17 + 224) = 1;
  *(_QWORD *)(v17 + 48) = v9;
  *(_OWORD *)(v17 + 200) = v25;
  v26 = *(_BYTE *)(a4 + 706) != 0;
  *(_DWORD *)(v17 + 292) = 0;
  *(_DWORD *)(v17 + 264) = v24 & 0xFFFFFFEF | (v26 ? 0x10 : 0);
  v27 = v24 & 0xFFFFFFCF | (v26 ? 0x10 : 0) | (*(_BYTE *)(a4 + 707) != 0 ? 0x20 : 0);
  *(_DWORD *)(v17 + 264) = v27;
  *(_DWORD *)(v17 + 268) = *(_DWORD *)(a4 + 708);
  v28 = v27 & 0xFFFFFFBF | (*(_BYTE *)(a4 + 705) != 0 ? 0x40 : 0);
  *(_DWORD *)(v17 + 264) = v28;
  if ( (v28 & 1) == 0 )
  {
    v29 = *(_QWORD *)(v17 + 56);
    if ( !v29 )
      v29 = *(_QWORD *)(v18 + 64);
    if ( v29 )
      *(_DWORD *)(v18 + 264) = v28 | 4;
  }
  *(_OWORD *)(v18 + 72) = *(_OWORD *)(a4 + 688);
  KeInitializeSpinLock((PKSPIN_LOCK)(v18 + 32));
  *(_QWORD *)(v18 + 280) = v18 + 272;
  *(_QWORD *)(v18 + 272) = v18 + 272;
  *(_DWORD *)(v18 + 232) = 2;
  KeInitializeEvent((PRKEVENT)(v18 + 240), NotificationEvent, 0);
  Flink = v9[2].Linkage.Flink;
  p_Signature = &v9[1].Signature;
  if ( (ULONG_PTR *)Flink->Flink != p_Signature )
    __fastfail(3u);
  *(_QWORD *)v18 = p_Signature;
  v19 = 0;
  *(_QWORD *)(v18 + 8) = Flink;
  Flink->Flink = (struct _LIST_ENTRY *)v18;
  p_Signature[1] = v18;
  _InterlockedIncrement(&dword_14009B068);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF_qddd(
      WPP_GLOBAL_Control->AttachedDevice,
      (*(_DWORD *)(v18 + 264) >> 6) & 1,
      *(_DWORD *)(v18 + 264) & 1,
      v18,
      (*(_DWORD *)(v18 + 264) >> 4) & 1,
      (*(_DWORD *)(v18 + 264) >> 6) & 1,
      *(_DWORD *)(v18 + 264) & 1);
  }
  return v19;
}

```

## disassembly

```asm
0x14002ebb4  mov     dword ptr [rsp+Signature], edx
0x14002ebb8  push    rbx
0x14002ebb9  push    rbp
0x14002ebba  push    rsi
0x14002ebbb  push    rdi
0x14002ebbc  push    r12
0x14002ebbe  push    r13
0x14002ebc0  push    r14
0x14002ebc2  push    r15
0x14002ebc4  sub     rsp, 78h
0x14002ebc8  xor     eax, eax
0x14002ebca  xorps   xmm0, xmm0
0x14002ebcd  xor     edi, edi
0x14002ebcf  mov     [rsp+0B8h+Context.Signature], rax
0x14002ebd4  xor     r12b, r12b
0x14002ebd7  xor     r15b, r15b
0x14002ebda  mov     rbp, r9
0x14002ebdd  mov     r13, r8
0x14002ebe0  mov     rsi, rcx
0x14002ebe3  movups  [rsp+0B8h+var_78], xmm0
0x14002ebe8  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x14002ebed  test    rcx, rcx
0x14002ebf0  jnz     loc_14002ED44
0x14002ebf6  mov     ebx, [r9+80h]
0x14002ebfd  lea     r14, [r9+84h]
0x14002ec04  mov     rcx, r14; Src
0x14002ec07  mov     edx, 104h; MaxCount
0x14002ec0c  call    cs:__imp_wcsnlen
0x14002ec13  nop     dword ptr [rax+rax+00h]
0x14002ec18  mov     rdx, r14
0x14002ec1b  mov     ecx, ebx
0x14002ec1d  lea     r8d, [rax+rax]
0x14002ec21  call    RtlCompute37Hash
0x14002ec26  bts     eax, 1Fh
0x14002ec2a  lea     r8, [rsp+0B8h+Context]; Context
0x14002ec2f  xorps   xmm0, xmm0
0x14002ec32  mov     edx, eax; Signature
0x14002ec34  lea     rcx, stru_14009B008; HashTable
0x14002ec3b  mov     ebx, eax
0x14002ec3d  movdqu  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x14002ec43  call    cs:__imp_RtlLookupEntryHashTable
0x14002ec4a  nop     dword ptr [rax+rax+00h]
0x14002ec4f  mov     rdi, rax
0x14002ec52  test    rax, rax
0x14002ec55  jnz     loc_14002EE92
0x14002ec5b  mov     edx, 238h
0x14002ec60  lea     ecx, [rax+40h]
0x14002ec63  mov     r8d, 6D636E4Eh
0x14002ec69  call    cs:__imp_ExAllocatePool2
0x14002ec70  nop     dword ptr [rax+rax+00h]
0x14002ec75  mov     rdi, rax
0x14002ec78  test    rax, rax
0x14002ec7b  jz      loc_14002ED6C
0x14002ec81  mov     eax, [rbp+80h]
0x14002ec87  mov     edx, 104h; MaxCount
0x14002ec8c  mov     rcx, r14; Src
0x14002ec8f  mov     [rdi+1Ch], eax
0x14002ec92  mov     r12b, 1
0x14002ec95  call    cs:__imp_wcsnlen
0x14002ec9c  nop     dword ptr [rax+rax+00h]
0x14002eca1  lea     rcx, [rdi+20h]; void *
0x14002eca5  mov     rdx, r14; Src
0x14002eca8  lea     r8, [rax+rax]; Size
0x14002ecac  call    memmove
0x14002ecb1  mov     eax, [rbp+298h]
0x14002ecb7  lea     rcx, stru_14009B008; HashTable
0x14002ecbe  mov     [rdi+228h], eax
0x14002ecc4  xor     r9d, r9d; Context
0x14002ecc7  mov     eax, [rbp+29Ch]
0x14002eccd  mov     r8, rbx; Signature
0x14002ecd0  mov     rdx, rdi; Entry
0x14002ecd3  mov     [rdi+22Ch], eax
0x14002ecd9  call    cs:__imp_RtlInsertEntryHashTable
0x14002ece0  nop     dword ptr [rax+rax+00h]
0x14002ece5  mov     edx, 38h ; '8'
0x14002ecea  mov     r8d, 6D636E4Eh
0x14002ecf0  lea     ecx, [rdx+8]
0x14002ecf3  call    cs:__imp_ExAllocatePool2
0x14002ecfa  nop     dword ptr [rax+rax+00h]
0x14002ecff  mov     rsi, rax
0x14002ed02  test    rax, rax
0x14002ed05  jz      short loc_14002ED6C
0x14002ed07  mov     eax, [r13+0]
0x14002ed0b  lea     rcx, stru_14009B030; HashTable
0x14002ed12  mov     r8d, dword ptr [rsp+0B8h+Signature]; Signature
0x14002ed1a  xor     r9d, r9d; Context
0x14002ed1d  mov     [rsi+18h], eax
0x14002ed20  mov     rdx, rsi; Entry
0x14002ed23  lea     rax, [rsi+28h]
0x14002ed27  mov     [rsi+20h], rdi
0x14002ed2b  mov     [rax+8], rax
0x14002ed2f  mov     r15b, 1
0x14002ed32  mov     [rax], rax
0x14002ed35  call    cs:__imp_RtlInsertEntryHashTable
0x14002ed3c  nop     dword ptr [rax+rax+00h]
0x14002ed41  inc     dword ptr [rdi+18h]
0x14002ed44  mov     edx, 130h
0x14002ed49  mov     ecx, 40h ; '@'
0x14002ed4e  mov     r8d, 6D636E4Eh
0x14002ed54  call    cs:__imp_ExAllocatePool2
0x14002ed5b  nop     dword ptr [rax+rax+00h]
0x14002ed60  mov     rbx, rax
0x14002ed63  test    rax, rax
0x14002ed66  jnz     loc_14007C345
0x14002ed6c  mov     ebp, 0C000009Ah
0x14002ed71  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ed78  lea     rax, WPP_GLOBAL_Control
0x14002ed7f  cmp     rcx, rax
0x14002ed82  jz      short loc_14002EDAB
0x14002ed84  cmp     byte ptr [rcx+29h], 3
0x14002ed88  jb      short loc_14002EDAB
0x14002ed8a  test    dword ptr [rcx+2Ch], 200000h
0x14002ed91  jz      short loc_14002EDAB
0x14002ed93  mov     rcx, [rcx+18h]
0x14002ed97  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14002ed9e  mov     edx, 23h ; '#'
0x14002eda3  mov     r9d, ebp
0x14002eda6  call    WPP_SF_d
0x14002edab  test    r15b, r15b
0x14002edae  jz      loc_14007C30C
0x14002edb4  xor     r8d, r8d; Context
0x14002edb7  lea     rcx, stru_14009B030; HashTable
0x14002edbe  mov     rdx, rsi; Entry
0x14002edc1  call    cs:__imp_RtlRemoveEntryHashTable
0x14002edc8  nop     dword ptr [rax+rax+00h]
0x14002edcd  xor     edx, edx; Tag
0x14002edcf  mov     rcx, rsi; P
0x14002edd2  call    cs:__imp_ExFreePoolWithTag
0x14002edd9  nop     dword ptr [rax+rax+00h]
0x14002edde  dec     dword ptr [rdi+18h]
0x14002ede1  jmp     loc_14007C30C
0x14002ede6  mov     [rbx], rsi
0x14002ede9  xor     ebp, ebp
0x14002edeb  mov     [rbx+8], rax
0x14002edef  mov     [rax], rbx
0x14002edf2  mov     [rsi+8], rbx
0x14002edf6  lock inc cs:dword_14009B068
0x14002edfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee04  lea     rax, WPP_GLOBAL_Control
0x14002ee0b  cmp     rcx, rax
0x14002ee0e  jz      short loc_14002EE1A
0x14002ee10  cmp     byte ptr [rcx+29h], 3
0x14002ee14  jnb     loc_14002EED1
0x14002ee1a  mov     eax, ebp
0x14002ee1c  add     rsp, 78h
0x14002ee20  pop     r15
0x14002ee22  pop     r14
0x14002ee24  pop     r13
0x14002ee26  pop     r12
0x14002ee28  pop     rdi
0x14002ee29  pop     rsi
0x14002ee2a  pop     rbp
0x14002ee2b  pop     rbx
0x14002ee2c  retn
0x14002ee2e  movups  xmm0, xmmword ptr [rbp+2B0h]
0x14002ee35  lea     rcx, [rbx+20h]; SpinLock
0x14002ee39  movdqu  xmmword ptr [rbx+48h], xmm0
0x14002ee3e  call    cs:__imp_KeInitializeSpinLock
0x14002ee45  nop     dword ptr [rax+rax+00h]
0x14002ee4a  lea     rax, [rbx+110h]
0x14002ee51  xor     r8d, r8d; State
0x14002ee54  mov     [rax+8], rax
0x14002ee58  lea     rcx, [rbx+0F0h]; Event
0x14002ee5f  mov     [rax], rax
0x14002ee62  xor     edx, edx; Type
0x14002ee64  mov     dword ptr [rbx+0E8h], 2
0x14002ee6e  call    cs:__imp_KeInitializeEvent
0x14002ee75  nop     dword ptr [rax+rax+00h]
0x14002ee7a  mov     rax, [rsi+30h]
0x14002ee7e  add     rsi, 28h ; '('
0x14002ee82  cmp     [rax], rsi
0x14002ee85  jz      loc_14002EDE6
0x14002ee8b  mov     ecx, 3
0x14002ee90  int     29h; Win8: RtlFailFast(ecx)
0x14002ee92  mov     eax, [rdi+1Ch]
0x14002ee95  cmp     [rbp+80h], eax
0x14002ee9b  jnz     loc_14007C2EE
0x14002eea1  mov     edx, 104h; MaxCount
0x14002eea6  mov     rcx, r14; Src
0x14002eea9  call    cs:__imp_wcsnlen
0x14002eeb0  nop     dword ptr [rax+rax+00h]
0x14002eeb5  lea     rcx, [rdi+20h]; S1
0x14002eeb9  mov     rdx, r14; S2
0x14002eebc  mov     r8, rax; N
0x14002eebf  call    wmemcmp
0x14002eec4  test    eax, eax
0x14002eec6  jz      loc_14002ECE5
0x14002eecc  jmp     loc_14007C2EE
0x14002eed1  test    dword ptr [rcx+2Ch], 200000h
0x14002eed8  jz      loc_14002EE1A
0x14002eede  mov     r9d, [rbx+108h]
0x14002eee5  mov     r8d, r9d
0x14002eee8  mov     rcx, [rcx+18h]
0x14002eeec  mov     edx, r9d
0x14002eeef  shr     r9d, 4
0x14002eef3  and     r8d, 1
0x14002eef7  and     r9d, 1
0x14002eefb  mov     [rsp+0B8h+var_88], r8d
0x14002ef00  shr     edx, 6
0x14002ef03  and     edx, 1
0x14002ef06  mov     [rsp+0B8h+var_90], edx
0x14002ef0a  mov     [rsp+0B8h+var_98], r9d
0x14002ef0f  mov     r9, rbx
0x14002ef12  call    WPP_SF_qddd
0x14002ef17  jmp     loc_14002EE1A
0x14007c2ee  lea     rdx, [rsp+0B8h+Context]; Context
0x14007c2f3  lea     rcx, stru_14009B008; HashTable
0x14007c2fa  call    cs:__imp_RtlGetNextEntryHashTable
0x14007c301  nop     dword ptr [rax+rax+00h]
0x14007c306  nop
0x14007c307  jmp     loc_14002EC4F
0x14007c30c  test    r12b, r12b
0x14007c30f  jz      loc_14002EE1A
0x14007c315  xor     r8d, r8d; Context
0x14007c318  lea     rcx, stru_14009B008; HashTable
0x14007c31f  mov     rdx, rdi; Entry
0x14007c322  call    cs:__imp_RtlRemoveEntryHashTable
0x14007c329  nop     dword ptr [rax+rax+00h]
0x14007c32e  xor     edx, edx; Tag
0x14007c330  mov     rcx, rdi; P
0x14007c333  call    cs:__imp_ExFreePoolWithTag
0x14007c33a  nop     dword ptr [rax+rax+00h]
0x14007c33f  nop
0x14007c340  jmp     loc_14002EE1A
0x14007c345  mov     qword ptr [rax+10h], 1
0x14007c34d  mov     rax, [r13+8]
0x14007c351  mov     [rbx+28h], rax
0x14007c355  movzx   edx, byte ptr [rbp+2C0h]
0x14007c35c  mov     eax, [rbx+108h]
0x14007c362  xor     edx, eax
0x14007c364  and     edx, 1
0x14007c367  xor     edx, eax
0x14007c369  mov     [rbx+108h], edx
0x14007c36f  movups  xmm0, xmmword ptr [rbp+2A0h]
0x14007c376  movdqu  xmmword ptr [rbx+38h], xmm0
0x14007c37b  movups  xmm0, xmmword ptr [rbp+0]
0x14007c37f  movups  xmmword ptr [rbx+58h], xmm0
0x14007c383  movups  xmm1, xmmword ptr [rbp+10h]
0x14007c387  movups  xmmword ptr [rbx+68h], xmm1
0x14007c38b  movups  xmm0, xmmword ptr [rbp+20h]
0x14007c38f  movups  xmmword ptr [rbx+78h], xmm0
0x14007c393  movups  xmm1, xmmword ptr [rbp+30h]
0x14007c397  movups  xmmword ptr [rbx+88h], xmm1
0x14007c39e  movups  xmm0, xmmword ptr [rbp+40h]
0x14007c3a2  movups  xmmword ptr [rbx+98h], xmm0
0x14007c3a9  movups  xmm1, xmmword ptr [rbp+50h]
0x14007c3ad  movups  xmmword ptr [rbx+0A8h], xmm1
0x14007c3b4  movups  xmm0, xmmword ptr [rbp+60h]
0x14007c3b8  movups  xmmword ptr [rbx+0B8h], xmm0
0x14007c3bf  movups  xmm1, xmmword ptr [rbp+70h]
0x14007c3c3  mov     dword ptr [rbx+0E0h], 1
0x14007c3cd  mov     [rbx+30h], rsi
0x14007c3d1  movups  xmmword ptr [rbx+0C8h], xmm1
0x14007c3d8  mov     al, [rbp+2C2h]
0x14007c3de  neg     al
0x14007c3e0  mov     dword ptr [rbx+124h], 0
0x14007c3ea  sbb     ecx, ecx
0x14007c3ec  and     edx, 0FFFFFFEFh
0x14007c3ef  and     ecx, 10h
0x14007c3f2  or      ecx, edx
0x14007c3f4  mov     [rbx+108h], ecx
0x14007c3fa  mov     al, [rbp+2C3h]
0x14007c400  neg     al
0x14007c402  sbb     edx, edx
0x14007c404  and     ecx, 0FFFFFFDFh
0x14007c407  and     edx, 20h
0x14007c40a  or      edx, ecx
0x14007c40c  mov     [rbx+108h], edx
0x14007c412  mov     eax, [rbp+2C4h]
0x14007c418  mov     [rbx+10Ch], eax
0x14007c41e  mov     al, [rbp+2C1h]
0x14007c424  neg     al
0x14007c426  sbb     ecx, ecx
0x14007c428  and     edx, 0FFFFFFBFh
0x14007c42b  and     ecx, 40h
0x14007c42e  or      ecx, edx
0x14007c430  mov     [rbx+108h], ecx
0x14007c436  test    cl, 1
0x14007c439  jnz     loc_14002EE2E
0x14007c43f  mov     rax, [rbx+38h]
0x14007c443  sub     rax, qword ptr [rsp+0B8h+var_78]
0x14007c448  jnz     short loc_14007C453
0x14007c44a  mov     rax, [rbx+40h]
0x14007c44e  sub     rax, qword ptr [rsp+0B8h+var_78+8]
0x14007c453  test    rax, rax
0x14007c456  jz      loc_14002EE2E
0x14007c45c  or      ecx, 4
0x14007c45f  mov     [rbx+108h], ecx
0x14007c465  jmp     loc_14002EE2E
```
