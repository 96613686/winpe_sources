# CVirtualAddressAllocator::RemoveVaRangeFromVad(VIDMM_MAPPED_VA_RANGE *,bool,bool,bool)

- ea: `0x140102950`
- end: `0x140102ae8`
- name: `?RemoveVaRangeFromVad@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_MAPPED_VA_RANGE@@_N11@Z`
- size: `408`
- prototype: `void __usercall(CVirtualAddressAllocator *__hidden this@<rcx>, PVOID Entry@<rdx>, bool@<r8b>, bool@<r9b>, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140097100`
- `0x140101f6c`

## callees

- `0x14002f580`
- `0x14002f6a8`
- `0x140100650`
- `0x140102950`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140102ab6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140102ab6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140102ac7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140102ac7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102a88`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102a88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140102a94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140102a94`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010299a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010299a`

## pseudocode

```c
void __fastcall CVirtualAddressAllocator::RemoveVaRangeFromVad(
        CVirtualAddressAllocator *this,
        unsigned int *Entry,
        char a3,
        char a4,
        bool a5)
{
  __int64 v5; // rdi
  unsigned __int64 v7; // rcx
  char v9; // si
  __int64 **VidMmAllocFromOwner; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // r8
  char *v15; // rsi
  __int64 v16; // rax
  char **v17; // rdx
  __int64 v18; // rbp
  __int64 v19; // r14

  v5 = *(_QWORD *)Entry;
  v7 = Entry[18];
  v9 = a3;
  if ( (v7 & 0x4000) != 0 )
  {
    RtlAvlRemoveNode(v5 + 24 * (((v7 >> 4) & 0x3F) + 4), Entry + 2);
    Entry[18] &= ~0x4000u;
    LODWORD(v7) = Entry[18];
  }
  VidMmAllocFromOwner = (__int64 **)GetVidMmAllocFromOwner(v7 & 0xF, *((_QWORD *)Entry + 8));
  if ( VidMmAllocFromOwner )
  {
    v12 = Entry + 8;
    v13 = *((_QWORD *)Entry + 4);
    if ( v13 )
    {
      if ( *(_QWORD **)(v13 + 8) != v12 )
        goto LABEL_17;
      v14 = (_QWORD *)*((_QWORD *)Entry + 5);
      if ( (_QWORD *)*v14 != v12 )
        goto LABEL_17;
      *v14 = v13;
      *(_QWORD *)(v13 + 8) = v14;
      *v12 = 0;
    }
    v15 = (char *)(Entry + 12);
    if ( !*((_QWORD *)Entry + 6) )
    {
LABEL_13:
      v9 = a3;
      goto LABEL_4;
    }
    v18 = **VidMmAllocFromOwner;
    v19 = v18 + 192;
    if ( !a5 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v19, 0);
      *(_QWORD *)(v18 + 200) = KeGetCurrentThread();
    }
    v16 = *(_QWORD *)v15;
    if ( *(char **)(*(_QWORD *)v15 + 8LL) == v15 )
    {
      v17 = (char **)*((_QWORD *)Entry + 7);
      if ( *v17 == v15 )
      {
        *v17 = (char *)v16;
        *(_QWORD *)(v16 + 8) = v17;
        *(_QWORD *)v15 = 0;
        if ( !a5 )
        {
          *(_QWORD *)(v18 + 200) = 0;
          ExReleasePushLockExclusiveEx(v19, 0);
          KeLeaveCriticalRegion();
        }
        goto LABEL_13;
      }
    }
LABEL_17:
    __fastfail(3u);
  }
LABEL_4:
  --*(_DWORD *)(v5 + 76);
  if ( a4 )
    *(_QWORD *)Entry = 0;
  VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(Entry);
  if ( v9 && (*(_BYTE *)(v5 + 72) & 0xF) == 3 && !*(_DWORD *)(v5 + 76) )
    CVirtualAddressAllocator::FreeVadVirtualAddressRangeInternal(this, (struct VIDMM_VAD *)v5);
}

```

## disassembly

```asm
0x140102950  mov     [rsp+arg_0], rbx
0x140102955  mov     [rsp+arg_8], rbp
0x14010295a  mov     [rsp+arg_10], r8b
0x14010295f  push    rsi
0x140102960  push    rdi
0x140102961  push    r12
0x140102963  push    r13
0x140102965  push    r14
0x140102967  sub     rsp, 20h
0x14010296b  mov     rdi, [rdx]
0x14010296e  mov     r13, rcx
0x140102971  mov     ecx, [rdx+48h]
0x140102974  mov     r12b, r9b
0x140102977  mov     sil, r8b
0x14010297a  mov     rbx, rdx
0x14010297d  bt      ecx, 0Eh
0x140102981  jnb     short loc_1401029AE
0x140102983  shr     rcx, 4
0x140102987  add     rdx, 8
0x14010298b  and     ecx, 3Fh
0x14010298e  add     rcx, 4
0x140102992  lea     rax, [rcx+rcx*2]
0x140102996  lea     rcx, [rdi+rax*8]
0x14010299a  call    cs:__imp_RtlAvlRemoveNode
0x1401029a1  nop     dword ptr [rax+rax+00h]
0x1401029a6  btr     dword ptr [rbx+48h], 0Eh
0x1401029ab  mov     ecx, [rbx+48h]
0x1401029ae  mov     rdx, [rbx+40h]
0x1401029b2  and     ecx, 0Fh
0x1401029b5  call    ?GetVidMmAllocFromOwner@@YAPEAUVIDMM_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1401029ba  test    rax, rax
0x1401029bd  jnz     short loc_1401029F3
0x1401029bf  dec     dword ptr [rdi+4Ch]
0x1401029c2  test    r12b, r12b
0x1401029c5  jz      short loc_1401029CE
0x1401029c7  mov     qword ptr [rbx], 0
0x1401029ce  mov     rcx, rbx; Entry
0x1401029d1  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1401029d6  test    sil, sil
0x1401029d9  jnz     short loc_140102A2D
0x1401029db  mov     rbx, [rsp+48h+arg_0]
0x1401029e0  mov     rbp, [rsp+48h+arg_8]
0x1401029e5  add     rsp, 20h
0x1401029e9  pop     r14
0x1401029eb  pop     r13
0x1401029ed  pop     r12
0x1401029ef  pop     rdi
0x1401029f0  pop     rsi
0x1401029f1  retn
0x1401029f3  lea     rcx, [rbx+20h]
0x1401029f7  mov     rdx, [rcx]
0x1401029fa  test    rdx, rdx
0x1401029fd  jz      short loc_140102A1C
0x1401029ff  cmp     [rdx+8], rcx
0x140102a03  jnz     short loc_140102A4A
0x140102a05  mov     r8, [rcx+8]
0x140102a09  cmp     [r8], rcx
0x140102a0c  jnz     short loc_140102A4A
0x140102a0e  mov     [r8], rdx
0x140102a11  mov     [rdx+8], r8
0x140102a15  mov     qword ptr [rcx], 0
0x140102a1c  lea     rsi, [rbx+30h]
0x140102a20  cmp     qword ptr [rsi], 0
0x140102a24  jnz     short loc_140102AA2
0x140102a26  mov     sil, [rsp+48h+arg_10]
0x140102a2b  jmp     short loc_1401029BF
0x140102a2d  mov     eax, [rdi+48h]
0x140102a30  and     eax, 0Fh
0x140102a33  cmp     al, 3
0x140102a35  jnz     short loc_1401029DB
0x140102a37  cmp     dword ptr [rdi+4Ch], 0
0x140102a3b  jnz     short loc_1401029DB
0x140102a3d  mov     rdx, rdi; struct VIDMM_VAD *
0x140102a40  mov     rcx, r13; this
0x140102a43  call    ?FreeVadVirtualAddressRangeInternal@CVirtualAddressAllocator@@AEAAXPEAUVIDMM_VAD@@@Z; CVirtualAddressAllocator::FreeVadVirtualAddressRangeInternal(VIDMM_VAD *)
0x140102a48  jmp     short loc_1401029DB
0x140102a4a  mov     ecx, 3
0x140102a4f  int     29h; Win8: RtlFailFast(ecx)
0x140102a51  mov     rax, [rsi]
0x140102a54  cmp     [rax+8], rsi
0x140102a58  jnz     short loc_140102A4A
0x140102a5a  mov     rdx, [rsi+8]
0x140102a5e  cmp     [rdx], rsi
0x140102a61  jnz     short loc_140102A4A
0x140102a63  cmp     [rsp+48h+arg_20], 0
0x140102a68  mov     [rdx], rax
0x140102a6b  mov     [rax+8], rdx
0x140102a6f  mov     qword ptr [rsi], 0
0x140102a76  jnz     short loc_140102A26
0x140102a78  xor     edx, edx
0x140102a7a  mov     qword ptr [rbp+0C8h], 0
0x140102a85  mov     rcx, r14
0x140102a88  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140102a8f  nop     dword ptr [rax+rax+00h]
0x140102a94  call    cs:__imp_KeLeaveCriticalRegion
0x140102a9b  nop     dword ptr [rax+rax+00h]
0x140102aa0  jmp     short loc_140102A26
0x140102aa2  mov     rax, [rax]
0x140102aa5  mov     rbp, [rax]
0x140102aa8  cmp     [rsp+48h+arg_20], 0
0x140102aad  lea     r14, [rbp+0C0h]
0x140102ab4  jnz     short loc_140102A51
0x140102ab6  call    cs:__imp_KeEnterCriticalRegion
0x140102abd  nop     dword ptr [rax+rax+00h]
0x140102ac2  xor     edx, edx
0x140102ac4  mov     rcx, r14
0x140102ac7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140102ace  nop     dword ptr [rax+rax+00h]
0x140102ad3  mov     rax, gs:188h
0x140102adc  mov     [rbp+0C8h], rax
0x140102ae3  jmp     loc_140102A51
```
