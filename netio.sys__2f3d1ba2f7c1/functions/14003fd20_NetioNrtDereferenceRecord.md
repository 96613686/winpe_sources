# NetioNrtDereferenceRecord

- ea: `0x14003fd20`
- end: `0x14003fe60`
- name: `NetioNrtDereferenceRecord`
- size: `320`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003fc10`
- `0x14003fca0`
- `0x14003fe68`
- `0x140040000`
- `0x140040330`
- `0x14004f488`
- `0x1400769f0`

## callees

- `0x14003fd20`
- `0x14003fe68`
- `0x1400408d0`
- `0x14004faf8`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fdd2`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fe2f`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fdd2`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14003fe2f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003fd52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003fd52`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003fd9c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003fd9c`

## pseudocode

```c
void __fastcall NetioNrtDereferenceRecord(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)
{
  PKSPIN_LOCK v1; // rdi
  char v3; // si
  int i; // edx
  signed __int64 v5; // rax
  bool v6; // cc
  signed __int64 v7; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v1 = NrtRecordSet;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v3 = 0;
  KeAcquireInStackQueuedSpinLock(NrtRecordSet, &LockHandle);
  for ( i = 0; i <= *((_DWORD *)v1 + 2); ++i )
  {
    while ( LODWORD(v1[8 * (__int64)i + 8]) )
      ;
  }
  v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)&Entry[2], 0xFFFFFFFFFFFFFFFFuLL);
  v6 = v5 <= 1;
  v7 = v5 - 1;
  if ( v6 )
  {
    if ( v7 )
      __fastfail(0xEu);
    RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)NrtRecordSet[40], Entry, 0);
    if ( Entry[3].Signature )
      RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)NrtRecordSet[41], Entry + 1, 0);
    v3 = 1;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids, Entry);
    }
    NetioNrtWppLogRecord(Entry, 4);
    NrtDeleteRecord(Entry);
  }
}

```

## disassembly

```asm
0x14003fd20  mov     r11, rsp
0x14003fd23  mov     [r11+8], rbx
0x14003fd27  mov     [r11+10h], rsi
0x14003fd2b  push    rdi
0x14003fd2c  sub     rsp, 40h
0x14003fd30  mov     rdi, cs:NrtRecordSet
0x14003fd37  lea     rdx, [r11-28h]; LockHandle
0x14003fd3b  xorps   xmm0, xmm0
0x14003fd3e  mov     rbx, rcx
0x14003fd41  xor     eax, eax
0x14003fd43  mov     rcx, rdi; SpinLock
0x14003fd46  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14003fd4b  mov     [r11-18h], rax
0x14003fd4f  xor     sil, sil
0x14003fd52  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003fd59  nop     dword ptr [rax+rax+00h]
0x14003fd5e  xor     edx, edx
0x14003fd60  cmp     [rdi+8], edx
0x14003fd63  jl      short loc_14003FD7B
0x14003fd65  movsxd  rcx, edx
0x14003fd68  shl     rcx, 6
0x14003fd6c  mov     eax, [rcx+rdi+40h]
0x14003fd70  test    eax, eax
0x14003fd72  jnz     short loc_14003FD6C
0x14003fd74  inc     edx
0x14003fd76  cmp     edx, [rdi+8]
0x14003fd79  jle     short loc_14003FD65
0x14003fd7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003fd7f  lock xadd [rbx+30h], rax
0x14003fd85  sub     rax, 1
0x14003fd89  jg      short loc_14003FD97
0x14003fd8b  test    rax, rax
0x14003fd8e  jz      short loc_14003FDBE
0x14003fd90  mov     ecx, 0Eh
0x14003fd95  int     29h; Win8: RtlFailFast(ecx)
0x14003fd97  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14003fd9c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003fda3  nop     dword ptr [rax+rax+00h]
0x14003fda8  test    sil, sil
0x14003fdab  jnz     short loc_14003FDEA
0x14003fdad  mov     rbx, [rsp+48h+arg_0]
0x14003fdb2  mov     rsi, [rsp+48h+arg_8]
0x14003fdb7  add     rsp, 40h
0x14003fdbb  pop     rdi
0x14003fdbc  retn
0x14003fdbe  mov     rcx, cs:NrtRecordSet
0x14003fdc5  xor     r8d, r8d; Context
0x14003fdc8  mov     rdx, rbx; Entry
0x14003fdcb  mov     rcx, [rcx+140h]; HashTable
0x14003fdd2  call    cs:__imp_RtlRemoveEntryHashTable
0x14003fdd9  nop     dword ptr [rax+rax+00h]
0x14003fdde  cmp     qword ptr [rbx+58h], 0
0x14003fde3  jnz     short loc_14003FE1A
0x14003fde5  mov     sil, 1
0x14003fde8  jmp     short loc_14003FD97
0x14003fdea  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fdf1  lea     rax, WPP_GLOBAL_Control
0x14003fdf8  cmp     rcx, rax
0x14003fdfb  jz      short loc_14003FE03
0x14003fdfd  cmp     byte ptr [rcx+29h], 4
0x14003fe01  jnb     short loc_14003FE3D
0x14003fe03  mov     edx, 4
0x14003fe08  mov     rcx, rbx
0x14003fe0b  call    NetioNrtWppLogRecord
0x14003fe10  mov     rcx, rbx; P
0x14003fe13  call    NrtDeleteRecord
0x14003fe18  jmp     short loc_14003FDAD
0x14003fe1a  mov     rcx, cs:NrtRecordSet
0x14003fe21  lea     rdx, [rbx+18h]; Entry
0x14003fe25  xor     r8d, r8d; Context
0x14003fe28  mov     rcx, [rcx+148h]; HashTable
0x14003fe2f  call    cs:__imp_RtlRemoveEntryHashTable
0x14003fe36  nop     dword ptr [rax+rax+00h]
0x14003fe3b  jmp     short loc_14003FDE5
0x14003fe3d  test    dword ptr [rcx+2Ch], 100000h
0x14003fe44  jz      short loc_14003FE03
0x14003fe46  mov     rcx, [rcx+18h]
0x14003fe4a  lea     r8, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids
0x14003fe51  mov     edx, 22h ; '"'
0x14003fe56  mov     r9, rbx
0x14003fe59  call    WPP_SF_q
0x14003fe5e  jmp     short loc_14003FE03
```
