# DoDerefVcWork

- ea: `0x1400156d8`
- end: `0x1400157fc`
- name: `DoDerefVcWork`
- size: `292`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `28`
- callee_count: `4`
- tags: ``

## callers

- `0x1400011b0`
- `0x140001680`
- `0x1400019d0`
- `0x140003860`
- `0x140003940`
- `0x140004760`
- `0x14000f020`
- `0x14000f250`
- `0x14000f630`
- `0x14000f830`
- `0x14000fbb0`
- `0x14000fcb0`
- `0x140010240`
- `0x1400103c0`
- `0x1400104f0`
- `0x140010600`
- `0x140011660`
- `0x140011ab0`
- `0x140012040`
- `0x140012210`
- `0x140012a00`
- `0x140012b20`
- `0x140012f00`
- `0x140013770`
- `0x140014310`
- `0x140014b20`
- `0x1400150f0`
- `0x1400166e0`

## callees

- `0x1400078f0`
- `0x1400155e4`
- `0x1400156d8`
- `0x140016628`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015782`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015782`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015729`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001576c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400157cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015729`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001576c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400157cd`
- `NDIS!NdisCoDeleteVc` at `0x14001573d`
- `NDIS!NdisCoDeleteVc` at `0x140015756`
- `NDIS!NdisCoDeleteVc` at `0x14001573d`
- `NDIS!NdisCoDeleteVc` at `0x140015756`

## pseudocode

```c
__int64 __fastcall DoDerefVcWork(_DWORD *Entry)
{
  int v1; // esi
  __int64 v3; // rdi
  KSPIN_LOCK *v4; // rcx
  KIRQL v5; // dl
  void *v6; // r14
  unsigned int v7; // esi
  void *v8; // rbp
  char v9; // si
  _DWORD **v10; // rdx
  PVOID *v11; // rcx

  v1 = Entry[8];
  v3 = *((_QWORD *)Entry + 7);
  v4 = (KSPIN_LOCK *)(Entry + 128);
  v5 = *((_BYTE *)Entry + 520);
  if ( (v1 & 2) != 0 )
  {
    v6 = (void *)*((_QWORD *)Entry + 8);
    v7 = v1 & 0xFFFFFFFD;
    v8 = (void *)*((_QWORD *)Entry + 5);
    Entry[8] = v7;
    v9 = v7 & 1;
    *((_QWORD *)Entry + 8) = 0;
    *((_QWORD *)Entry + 5) = 0;
    KeReleaseSpinLock(v4, v5);
    if ( v6 )
      NdisCoDeleteVc(v6);
    if ( v9 && v8 )
      NdisCoDeleteVc(v8);
    RemoveVcFromTable(Entry);
  }
  else
  {
    KeReleaseSpinLock(v4, v5);
  }
  *(_BYTE *)(v3 + 192) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 184));
  v10 = (_DWORD **)*((_QWORD *)Entry + 60);
  if ( v10[1] != Entry + 120 || (v11 = (PVOID *)*((_QWORD *)Entry + 61), *v11 != Entry + 120) )
    __fastfail(3u);
  *v11 = v10;
  v10[1] = v11;
  if ( (*(_DWORD *)(v3 + 20))-- == 1 )
    DoDerefClAfWork(v3);
  else
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 184), *(_BYTE *)(v3 + 192));
  return PxFreeVc(Entry);
}

```

## disassembly

```asm
0x1400156d8  mov     [rsp+arg_8], rbx
0x1400156dd  mov     [rsp+arg_10], rbp
0x1400156e2  push    rsi
0x1400156e3  push    rdi
0x1400156e4  push    r14
0x1400156e6  sub     rsp, 20h
0x1400156ea  mov     esi, [rcx+20h]
0x1400156ed  mov     rbx, rcx
0x1400156f0  mov     rdi, [rcx+38h]
0x1400156f4  add     rcx, 200h; SpinLock
0x1400156fb  mov     dl, [rbx+208h]; NewIrql
0x140015701  test    sil, 2
0x140015705  jz      short loc_14001576C
0x140015707  mov     r14, [rbx+40h]
0x14001570b  and     esi, 0FFFFFFFDh
0x14001570e  mov     rbp, [rbx+28h]
0x140015712  mov     [rbx+20h], esi
0x140015715  and     sil, 1
0x140015719  mov     qword ptr [rbx+40h], 0
0x140015721  mov     qword ptr [rbx+28h], 0
0x140015729  call    cs:__imp_KeReleaseSpinLock
0x140015730  nop     dword ptr [rax+rax+00h]
0x140015735  test    r14, r14
0x140015738  jz      short loc_140015749
0x14001573a  mov     rcx, r14; NdisVcHandle
0x14001573d  call    cs:__imp_NdisCoDeleteVc
0x140015744  nop     dword ptr [rax+rax+00h]
0x140015749  test    sil, sil
0x14001574c  jz      short loc_140015762
0x14001574e  test    rbp, rbp
0x140015751  jz      short loc_140015762
0x140015753  mov     rcx, rbp; NdisVcHandle
0x140015756  call    cs:__imp_NdisCoDeleteVc
0x14001575d  nop     dword ptr [rax+rax+00h]
0x140015762  mov     rcx, rbx
0x140015765  call    RemoveVcFromTable
0x14001576a  jmp     short loc_140015778
0x14001576c  call    cs:__imp_KeReleaseSpinLock
0x140015773  nop     dword ptr [rax+rax+00h]
0x140015778  lea     rsi, [rdi+0B8h]
0x14001577f  mov     rcx, rsi; SpinLock
0x140015782  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015789  nop     dword ptr [rax+rax+00h]
0x14001578e  mov     [rdi+0C0h], al
0x140015794  lea     rax, [rbx+1E0h]
0x14001579b  mov     rdx, [rax]
0x14001579e  cmp     [rdx+8], rax
0x1400157a2  jnz     short loc_1400157F5
0x1400157a4  mov     rcx, [rax+8]
0x1400157a8  cmp     [rcx], rax
0x1400157ab  jnz     short loc_1400157F5
0x1400157ad  mov     [rcx], rdx
0x1400157b0  mov     [rdx+8], rcx
0x1400157b4  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x1400157b8  jnz     short loc_1400157C4
0x1400157ba  mov     rcx, rdi
0x1400157bd  call    DoDerefClAfWork
0x1400157c2  jmp     short loc_1400157D9
0x1400157c4  mov     dl, [rdi+0C0h]; NewIrql
0x1400157ca  mov     rcx, rsi; SpinLock
0x1400157cd  call    cs:__imp_KeReleaseSpinLock
0x1400157d4  nop     dword ptr [rax+rax+00h]
0x1400157d9  mov     rcx, rbx; Entry
0x1400157dc  call    PxFreeVc
0x1400157e1  mov     rbx, [rsp+38h+arg_8]
0x1400157e6  mov     rbp, [rsp+38h+arg_10]
0x1400157eb  add     rsp, 20h
0x1400157ef  pop     r14
0x1400157f1  pop     rdi
0x1400157f2  pop     rsi
0x1400157f3  retn
0x1400157f5  mov     ecx, 3
0x1400157fa  int     29h; Win8: RtlFailFast(ecx)
```
