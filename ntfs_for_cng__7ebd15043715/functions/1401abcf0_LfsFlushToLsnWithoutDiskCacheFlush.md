# LfsFlushToLsnWithoutDiskCacheFlush

- ea: `0x1401abcf0`
- end: `0x1401ac076`
- name: `LfsFlushToLsnWithoutDiskCacheFlush`
- size: `902`
- prototype: `__int64 __fastcall(__int64, __int64, char, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400177d0`
- `0x140140660`
- `0x140192470`
- `0x1401aae60`
- `0x140268608`

## callees

- `0x1400240c0`
- `0x140027f08`
- `0x14002f140`
- `0x1401abcf0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401abfa4`
- `ntoskrnl!KeSetEvent` at `0x1401abfa4`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abeaf`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abf1e`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abeaf`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abf1e`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401abec2`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401abec2`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401abefc`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401abefc`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ac023`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ac023`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401abf51`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401abf51`
- `ntoskrnl!KeInitializeEvent` at `0x1401abdf1`
- `ntoskrnl!KeInitializeEvent` at `0x1401abdf1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abe47`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abed9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abe47`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abed9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401abe27`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401abe27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abd44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abf70`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abd44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abf70`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ac037`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ac037`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401abe09`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401abe09`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401abfb2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401abfb2`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac012`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac069`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac012`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac069`

## pseudocode

```c
__int64 __fastcall LfsFlushToLsnWithoutDiskCacheFlush(__int64 a1, __int64 a2, char a3, _QWORD *a4)
{
  unsigned int v8; // r15d
  __int64 v9; // rsi
  KPRIORITY v10; // r13d
  __int64 *v11; // rax
  __int64 v12; // rax
  char v13; // r15
  struct _ERESOURCE *v14; // rcx
  struct _KEVENT *v15; // rcx
  _QWORD *i; // rax
  _QWORD *v17; // rcx
  __int128 v19; // [rsp+50h] [rbp-68h] BYREF
  _BYTE Event[32]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v21; // [rsp+80h] [rbp-38h]
  BOOLEAN IsResourceAcquiredExclusiveLite; // [rsp+C0h] [rbp+8h]

  if ( !a1 || *(_WORD *)a1 != 2049 )
    ExRaiseStatus(-1073741790);
  v8 = 0;
  if ( a4 )
    *a4 = 0;
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 56), 1u);
  v9 = *(_QWORD *)(a1 + 24);
  if ( v9 )
  {
    if ( (*(_DWORD *)(v9 + 428) & 0x400) == 0 )
    {
      if ( *(_WORD *)(a1 + 34) >= *(_WORD *)(*(_QWORD *)(v9 + 200) + 8LL)
        || *(_WORD *)(a1 + 32) != *(_WORD *)(*(unsigned int *)(a1 + 48) + *(_QWORD *)(v9 + 208) + 20LL) )
      {
        ExRaiseStatus(-1073741790);
      }
      v19 = 0;
      memset(Event, 0, sizeof(Event));
      v21 = 0;
      v10 = 0;
      v11 = *(__int64 **)(v9 + 200);
      if ( a2 > *v11 )
        a2 = *v11;
      KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
      *(_QWORD *)&Event[24] = a2;
      IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v9 + 456));
      while ( 1 )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v9 + 456) + 120LL));
        v12 = *(_QWORD *)(v9 + 456);
        if ( a2 <= *(_QWORD *)(v9 + 280) )
        {
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v12 + 120));
          goto LABEL_14;
        }
        if ( *(_DWORD *)(v12 + 176) )
        {
          for ( i = *(_QWORD **)(v9 + 472); i != (_QWORD *)(v9 + 472) && i[5] <= a2; i = (_QWORD *)*i )
            ;
          v17 = (_QWORD *)i[1];
          if ( (_QWORD *)*v17 != i )
            __fastfail(3u);
          v13 = 0;
          *(_QWORD *)&v19 = i;
          *((_QWORD *)&v19 + 1) = v17;
          *v17 = &v19;
          i[1] = &v19;
        }
        else
        {
          *(_DWORD *)(v12 + 176) = 1;
          *(_QWORD *)(v9 + 504) = KeGetCurrentThread();
          v13 = 1;
          v10 = KeSetPriorityThread(KeGetCurrentThread(), 16);
          PsEnterPriorityRegion();
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v9 + 456) + 120LL));
        if ( v13 )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 464));
        LfsReleaseLfcb(v9);
        KeWaitForSingleObject(Event, Executive, 0, 0, 0);
        v14 = *(struct _ERESOURCE **)(v9 + 456);
        if ( IsResourceAcquiredExclusiveLite )
          ExAcquireResourceExclusiveLite(v14, 1u);
        else
          ExAcquireResourceSharedLite(v14, 1u);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v9 + 464)) )
        {
          v15 = *(struct _KEVENT **)(v9 + 608);
          if ( v15 )
            KeSetEvent(v15, 0, 0);
        }
      }
      LfsFlushLfcbOnNewStack(v9, a2, 0, a3);
      PsLeavePriorityRegion();
      if ( v10 != 16 )
        KeSetPriorityThread(KeGetCurrentThread(), v10);
    }
LABEL_14:
    v8 = *(_DWORD *)(v9 + 560);
    if ( a4 )
      *a4 = *(_QWORD *)(v9 + 280);
  }
  if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a1 + 56)) )
    ExReleaseResourceLite(*(PERESOURCE *)(a1 + 56));
  return v8;
}

```

## disassembly

```asm
0x1401abcf0  mov     [rsp+arg_8], rbx
0x1401abcf5  mov     [rsp+arg_10], rsi
0x1401abcfa  push    rdi
0x1401abcfb  push    r12
0x1401abcfd  push    r13
0x1401abcff  push    r14
0x1401abd01  push    r15
0x1401abd03  sub     rsp, 90h
0x1401abd0a  mov     r14, r9
0x1401abd0d  movzx   r12d, r8b
0x1401abd11  mov     rbx, rdx
0x1401abd14  mov     rdi, rcx
0x1401abd17  test    rcx, rcx
0x1401abd1a  jz      loc_1401AC064
0x1401abd20  mov     eax, 801h
0x1401abd25  cmp     [rcx], ax
0x1401abd28  jnz     loc_1401AC064
0x1401abd2e  xor     r15d, r15d
0x1401abd31  mov     [rsp+0B8h+var_70], rcx
0x1401abd36  test    r9, r9
0x1401abd39  jz      short loc_1401ABD3E
0x1401abd3b  mov     [r9], r15
0x1401abd3e  mov     dl, 1; Wait
0x1401abd40  mov     rcx, [rcx+38h]; Resource
0x1401abd44  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401abd4b  nop     dword ptr [rax+rax+00h]
0x1401abd50  mov     rsi, [rdi+18h]
0x1401abd54  test    rsi, rsi
0x1401abd57  jz      loc_1401AC01F
0x1401abd5d  mov     eax, [rsi+1ACh]
0x1401abd63  bt      eax, 0Ah
0x1401abd67  jb      loc_1401ABE53
0x1401abd6d  mov     rax, [rsi+0C8h]
0x1401abd74  movzx   ecx, word ptr [rax+8]
0x1401abd78  cmp     [rdi+22h], cx
0x1401abd7c  jnb     loc_1401AC00D
0x1401abd82  mov     ecx, [rdi+30h]
0x1401abd85  mov     rax, [rsi+0D0h]
0x1401abd8c  movzx   ecx, word ptr [rcx+rax+14h]
0x1401abd91  cmp     [rdi+20h], cx
0x1401abd95  jnz     loc_1401AC00D
0x1401abd9b  mov     [rsp+0B8h+var_78], rbx
0x1401abda0  xorps   xmm0, xmm0
0x1401abda3  xor     eax, eax
0x1401abda5  movups  [rsp+0B8h+var_68], xmm0
0x1401abdaa  movups  xmmword ptr [rsp+0B8h+Event], xmm0
0x1401abdaf  movups  xmmword ptr [rsp+0B8h+Event+10h], xmm0
0x1401abdb4  mov     [rsp+0B8h+var_38], rax
0x1401abdbc  xor     r13d, r13d
0x1401abdbf  mov     [rsp+0B8h+var_88], r13d
0x1401abdc4  mov     rax, ds:0FFFFF78000000320h
0x1401abdce  mov     rax, [rsi+0C8h]
0x1401abdd5  mov     rcx, [rax]
0x1401abdd8  cmp     rbx, rcx
0x1401abddb  cmovg   rbx, rcx
0x1401abddf  mov     [rsp+0B8h+var_78], rbx
0x1401abde4  xor     r8d, r8d; State
0x1401abde7  mov     edx, 1; Type
0x1401abdec  lea     rcx, [rsp+0B8h+Event]; Event
0x1401abdf1  call    cs:__imp_KeInitializeEvent
0x1401abdf8  nop     dword ptr [rax+rax+00h]
0x1401abdfd  mov     qword ptr [rsp+0B8h+Event+18h], rbx
0x1401abe02  mov     rcx, [rsi+1C8h]; Resource
0x1401abe09  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401abe10  nop     dword ptr [rax+rax+00h]
0x1401abe15  mov     [rsp+0B8h+arg_0], al
0x1401abe1c  mov     rcx, [rsi+1C8h]
0x1401abe23  add     rcx, 78h ; 'x'; FastMutex
0x1401abe27  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401abe2e  nop     dword ptr [rax+rax+00h]
0x1401abe33  mov     rax, [rsi+1C8h]
0x1401abe3a  cmp     rbx, [rsi+118h]
0x1401abe41  jg      short loc_1401ABE77
0x1401abe43  lea     rcx, [rax+78h]; FastMutex
0x1401abe47  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401abe4e  nop     dword ptr [rax+rax+00h]
0x1401abe53  mov     r15d, [rsi+230h]
0x1401abe5a  mov     [rsp+0B8h+var_80], r15d
0x1401abe5f  test    r14, r14
0x1401abe62  jz      loc_1401AC01F
0x1401abe68  mov     rax, [rsi+118h]
0x1401abe6f  mov     [r14], rax
0x1401abe72  jmp     loc_1401AC01F
0x1401abe77  cmp     dword ptr [rax+0B0h], 0
0x1401abe7e  jnz     loc_1401ABFC0
0x1401abe84  mov     dword ptr [rax+0B0h], 1
0x1401abe8e  mov     rax, gs:188h
0x1401abe97  mov     [rsi+1F8h], rax
0x1401abe9e  mov     r15b, 1
0x1401abea1  mov     rcx, gs:188h; Thread
0x1401abeaa  mov     edx, 10h; Priority
0x1401abeaf  call    cs:__imp_KeSetPriorityThread
0x1401abeb6  nop     dword ptr [rax+rax+00h]
0x1401abebb  mov     r13d, eax
0x1401abebe  mov     [rsp+0B8h+var_88], eax
0x1401abec2  call    cs:__imp_PsEnterPriorityRegion
0x1401abec9  nop     dword ptr [rax+rax+00h]
0x1401abece  mov     rcx, [rsi+1C8h]
0x1401abed5  add     rcx, 78h ; 'x'; FastMutex
0x1401abed9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401abee0  nop     dword ptr [rax+rax+00h]
0x1401abee5  mov     rcx, rsi
0x1401abee8  test    r15b, r15b
0x1401abeeb  jz      short loc_1401ABF2F
0x1401abeed  movzx   r9d, r12b
0x1401abef1  xor     r8d, r8d
0x1401abef4  mov     rdx, rbx
0x1401abef7  call    LfsFlushLfcbOnNewStack
0x1401abefc  call    cs:__imp_PsLeavePriorityRegion
0x1401abf03  nop     dword ptr [rax+rax+00h]
0x1401abf08  cmp     r13d, 10h
0x1401abf0c  jz      loc_1401ABE53
0x1401abf12  mov     rcx, gs:188h; Thread
0x1401abf1b  mov     edx, r13d; Priority
0x1401abf1e  call    cs:__imp_KeSetPriorityThread
0x1401abf25  nop     dword ptr [rax+rax+00h]
0x1401abf2a  jmp     loc_1401ABE53
0x1401abf2f  lock inc dword ptr [rsi+1D0h]
0x1401abf36  call    LfsReleaseLfcb
0x1401abf3b  mov     [rsp+0B8h+Timeout], 0; Timeout
0x1401abf44  xor     r9d, r9d; Alertable
0x1401abf47  xor     r8d, r8d; WaitMode
0x1401abf4a  xor     edx, edx; WaitReason
0x1401abf4c  lea     rcx, [rsp+0B8h+Event]; Object
0x1401abf51  call    cs:__imp_KeWaitForSingleObject
0x1401abf58  nop     dword ptr [rax+rax+00h]
0x1401abf5d  mov     rcx, [rsi+1C8h]; Resource
0x1401abf64  mov     dl, 1; Wait
0x1401abf66  cmp     [rsp+0B8h+arg_0], 0
0x1401abf6e  jz      short loc_1401ABFB2
0x1401abf70  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401abf77  nop     dword ptr [rax+rax+00h]
0x1401abf7c  mov     eax, 0FFFFFFFFh
0x1401abf81  lock xadd [rsi+1D0h], eax
0x1401abf89  sub     eax, 1
0x1401abf8c  jz      short loc_1401ABF93
0x1401abf8e  jmp     loc_1401ABE1C
0x1401abf93  mov     rcx, [rsi+260h]; Event
0x1401abf9a  test    rcx, rcx
0x1401abf9d  jz      short loc_1401ABF8E
0x1401abf9f  xor     r8d, r8d; Wait
0x1401abfa2  xor     edx, edx; Increment
0x1401abfa4  call    cs:__imp_KeSetEvent
0x1401abfab  nop     dword ptr [rax+rax+00h]
0x1401abfb0  jmp     short loc_1401ABF8E
0x1401abfb2  call    cs:__imp_ExAcquireResourceSharedLite
0x1401abfb9  nop     dword ptr [rax+rax+00h]
0x1401abfbe  jmp     short loc_1401ABF7C
0x1401abfc0  lea     rcx, [rsi+1D8h]
0x1401abfc7  mov     rax, [rcx]
0x1401abfca  cmp     rax, rcx
0x1401abfcd  jnz     short loc_1401ABFDF
0x1401abfcf  mov     rcx, [rax+8]
0x1401abfd3  cmp     [rcx], rax
0x1401abfd6  jz      short loc_1401ABFEA
0x1401abfd8  mov     ecx, 3
0x1401abfdd  int     29h; Win8: RtlFailFast(ecx)
0x1401abfdf  cmp     [rax+28h], rbx
0x1401abfe3  jg      short loc_1401ABFCF
0x1401abfe5  mov     rax, [rax]
0x1401abfe8  jmp     short loc_1401ABFCA
0x1401abfea  xor     r15b, r15b
0x1401abfed  mov     qword ptr [rsp+0B8h+var_68], rax
0x1401abff2  mov     qword ptr [rsp+0B8h+var_68+8], rcx
0x1401abff7  lea     rdx, [rsp+0B8h+var_68]
0x1401abffc  mov     [rcx], rdx
0x1401abfff  lea     rcx, [rsp+0B8h+var_68]
0x1401ac004  mov     [rax+8], rcx
0x1401ac008  jmp     loc_1401ABECE
0x1401ac00d  mov     ecx, 0C0000022h; Status
0x1401ac012  call    cs:__imp_ExRaiseStatus
0x1401ac01f  mov     rcx, [rdi+38h]; Resource
0x1401ac023  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ac02a  nop     dword ptr [rax+rax+00h]
0x1401ac02f  test    eax, eax
0x1401ac031  jz      short loc_1401AC043
0x1401ac033  mov     rcx, [rdi+38h]; Resource
0x1401ac037  call    cs:__imp_ExReleaseResourceLite
0x1401ac03e  nop     dword ptr [rax+rax+00h]
0x1401ac043  mov     eax, r15d
0x1401ac046  lea     r11, [rsp+0B8h+var_28]
0x1401ac04e  mov     rbx, [r11+38h]
0x1401ac052  mov     rsi, [r11+40h]
0x1401ac056  mov     rsp, r11
0x1401ac059  pop     r15
0x1401ac05b  pop     r14
0x1401ac05d  pop     r13
0x1401ac05f  pop     r12
0x1401ac061  pop     rdi
0x1401ac062  retn
0x1401ac064  mov     ecx, 0C0000022h; Status
0x1401ac069  call    cs:__imp_ExRaiseStatus
0x1402adfc0  push    rbp
0x1402adfc2  sub     rsp, 30h
0x1402adfc6  mov     rbp, rdx
0x1402adfc9  mov     rcx, [rbp+48h]
0x1402adfcd  call    LfsReleaseLch
0x1402adfd2  nop
0x1402adfd3  add     rsp, 30h
0x1402adfd7  pop     rbp
0x1402adfd8  retn
```
