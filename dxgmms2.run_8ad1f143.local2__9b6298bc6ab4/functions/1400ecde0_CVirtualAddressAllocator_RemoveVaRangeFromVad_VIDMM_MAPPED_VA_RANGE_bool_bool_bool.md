# CVirtualAddressAllocator::RemoveVaRangeFromVad(VIDMM_MAPPED_VA_RANGE *,bool,bool,bool)

- ea: `0x1400ecde0`
- end: `0x1400ecf78`
- name: `?RemoveVaRangeFromVad@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_MAPPED_VA_RANGE@@_N11@Z`
- size: `408`
- prototype: `void __usercall(CVirtualAddressAllocator *__hidden this@<rcx>, PVOID Entry@<rdx>, bool@<r8b>, bool@<r9b>, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400941c8`
- `0x1400ec3fc`

## callees

- `0x140031704`
- `0x14003180c`
- `0x1400eaae0`
- `0x1400ecde0`

## import_xrefs

- `ntoskrnl!RtlAvlRemoveNode` at `0x1400ece2a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400ece2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ecf46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ecf46`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ecf57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ecf57`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ecf18`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ecf18`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ecf24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ecf24`

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
0x1400ecde0  mov     [rsp+arg_0], rbx
0x1400ecde5  mov     [rsp+arg_8], rbp
0x1400ecdea  mov     [rsp+arg_10], r8b
0x1400ecdef  push    rsi
0x1400ecdf0  push    rdi
0x1400ecdf1  push    r12
0x1400ecdf3  push    r13
0x1400ecdf5  push    r14
0x1400ecdf7  sub     rsp, 20h
0x1400ecdfb  mov     rdi, [rdx]
0x1400ecdfe  mov     r13, rcx
0x1400ece01  mov     ecx, [rdx+48h]
0x1400ece04  mov     r12b, r9b
0x1400ece07  mov     sil, r8b
0x1400ece0a  mov     rbx, rdx
0x1400ece0d  bt      ecx, 0Eh
0x1400ece11  jnb     short loc_1400ECE3E
0x1400ece13  shr     rcx, 4
0x1400ece17  add     rdx, 8
0x1400ece1b  and     ecx, 3Fh
0x1400ece1e  add     rcx, 4
0x1400ece22  lea     rax, [rcx+rcx*2]
0x1400ece26  lea     rcx, [rdi+rax*8]
0x1400ece2a  call    cs:__imp_RtlAvlRemoveNode
0x1400ece31  nop     dword ptr [rax+rax+00h]
0x1400ece36  btr     dword ptr [rbx+48h], 0Eh
0x1400ece3b  mov     ecx, [rbx+48h]
0x1400ece3e  mov     rdx, [rbx+40h]
0x1400ece42  and     ecx, 0Fh
0x1400ece45  call    ?GetVidMmAllocFromOwner@@YAPEAUVIDMM_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1400ece4a  test    rax, rax
0x1400ece4d  jnz     short loc_1400ECE83
0x1400ece4f  dec     dword ptr [rdi+4Ch]
0x1400ece52  test    r12b, r12b
0x1400ece55  jz      short loc_1400ECE5E
0x1400ece57  mov     qword ptr [rbx], 0
0x1400ece5e  mov     rcx, rbx; Entry
0x1400ece61  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1400ece66  test    sil, sil
0x1400ece69  jnz     short loc_1400ECEBD
0x1400ece6b  mov     rbx, [rsp+48h+arg_0]
0x1400ece70  mov     rbp, [rsp+48h+arg_8]
0x1400ece75  add     rsp, 20h
0x1400ece79  pop     r14
0x1400ece7b  pop     r13
0x1400ece7d  pop     r12
0x1400ece7f  pop     rdi
0x1400ece80  pop     rsi
0x1400ece81  retn
0x1400ece83  lea     rcx, [rbx+20h]
0x1400ece87  mov     rdx, [rcx]
0x1400ece8a  test    rdx, rdx
0x1400ece8d  jz      short loc_1400ECEAC
0x1400ece8f  cmp     [rdx+8], rcx
0x1400ece93  jnz     short loc_1400ECEDA
0x1400ece95  mov     r8, [rcx+8]
0x1400ece99  cmp     [r8], rcx
0x1400ece9c  jnz     short loc_1400ECEDA
0x1400ece9e  mov     [r8], rdx
0x1400ecea1  mov     [rdx+8], r8
0x1400ecea5  mov     qword ptr [rcx], 0
0x1400eceac  lea     rsi, [rbx+30h]
0x1400eceb0  cmp     qword ptr [rsi], 0
0x1400eceb4  jnz     short loc_1400ECF32
0x1400eceb6  mov     sil, [rsp+48h+arg_10]
0x1400ecebb  jmp     short loc_1400ECE4F
0x1400ecebd  mov     eax, [rdi+48h]
0x1400ecec0  and     eax, 0Fh
0x1400ecec3  cmp     al, 3
0x1400ecec5  jnz     short loc_1400ECE6B
0x1400ecec7  cmp     dword ptr [rdi+4Ch], 0
0x1400ececb  jnz     short loc_1400ECE6B
0x1400ececd  mov     rdx, rdi; struct VIDMM_VAD *
0x1400eced0  mov     rcx, r13; this
0x1400eced3  call    ?FreeVadVirtualAddressRangeInternal@CVirtualAddressAllocator@@AEAAXPEAUVIDMM_VAD@@@Z; CVirtualAddressAllocator::FreeVadVirtualAddressRangeInternal(VIDMM_VAD *)
0x1400eced8  jmp     short loc_1400ECE6B
0x1400eceda  mov     ecx, 3
0x1400ecedf  int     29h; Win8: RtlFailFast(ecx)
0x1400ecee1  mov     rax, [rsi]
0x1400ecee4  cmp     [rax+8], rsi
0x1400ecee8  jnz     short loc_1400ECEDA
0x1400eceea  mov     rdx, [rsi+8]
0x1400eceee  cmp     [rdx], rsi
0x1400ecef1  jnz     short loc_1400ECEDA
0x1400ecef3  cmp     [rsp+48h+arg_20], 0
0x1400ecef8  mov     [rdx], rax
0x1400ecefb  mov     [rax+8], rdx
0x1400eceff  mov     qword ptr [rsi], 0
0x1400ecf06  jnz     short loc_1400ECEB6
0x1400ecf08  xor     edx, edx
0x1400ecf0a  mov     qword ptr [rbp+0C8h], 0
0x1400ecf15  mov     rcx, r14
0x1400ecf18  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400ecf1f  nop     dword ptr [rax+rax+00h]
0x1400ecf24  call    cs:__imp_KeLeaveCriticalRegion
0x1400ecf2b  nop     dword ptr [rax+rax+00h]
0x1400ecf30  jmp     short loc_1400ECEB6
0x1400ecf32  mov     rax, [rax]
0x1400ecf35  mov     rbp, [rax]
0x1400ecf38  cmp     [rsp+48h+arg_20], 0
0x1400ecf3d  lea     r14, [rbp+0C0h]
0x1400ecf44  jnz     short loc_1400ECEE1
0x1400ecf46  call    cs:__imp_KeEnterCriticalRegion
0x1400ecf4d  nop     dword ptr [rax+rax+00h]
0x1400ecf52  xor     edx, edx
0x1400ecf54  mov     rcx, r14
0x1400ecf57  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400ecf5e  nop     dword ptr [rax+rax+00h]
0x1400ecf63  mov     rax, gs:188h
0x1400ecf6c  mov     [rbp+0C8h], rax
0x1400ecf73  jmp     loc_1400ECEE1
```
