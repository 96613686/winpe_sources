# LfsFlushToLsnWithoutDiskCacheFlush

- ea: `0x1401abd40`
- end: `0x1401ac0c6`
- name: `LfsFlushToLsnWithoutDiskCacheFlush`
- size: `902`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400177d0`
- `0x1401406b0`
- `0x1401924c0`
- `0x1401aaeb0`
- `0x140268658`

## callees

- `0x1400240c0`
- `0x140027f08`
- `0x14002f140`
- `0x1401abd40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401abff4`
- `ntoskrnl!KeSetEvent` at `0x1401abff4`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abeff`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abf6e`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abeff`
- `ntoskrnl!KeSetPriorityThread` at `0x1401abf6e`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401abf12`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401abf12`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401abf4c`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401abf4c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ac073`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ac073`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401abfa1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401abfa1`
- `ntoskrnl!KeInitializeEvent` at `0x1401abe41`
- `ntoskrnl!KeInitializeEvent` at `0x1401abe41`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abe97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abf29`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abe97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401abf29`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401abe77`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401abe77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abd94`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abfc0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abd94`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401abfc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ac087`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ac087`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401abe59`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401abe59`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401ac002`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401ac002`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac062`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac0b9`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac062`
- `ntoskrnl!ExRaiseStatus` at `0x1401ac0b9`

## pseudocode

```c
__int64 __fastcall LfsFlushToLsnWithoutDiskCacheFlush(__int64 a1, __int64 a2, unsigned __int8 a3, _QWORD *a4)
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
0x1401abd40  mov     [rsp+arg_8], rbx
0x1401abd45  mov     [rsp+arg_10], rsi
0x1401abd4a  push    rdi
0x1401abd4b  push    r12
0x1401abd4d  push    r13
0x1401abd4f  push    r14
0x1401abd51  push    r15
0x1401abd53  sub     rsp, 90h
0x1401abd5a  mov     r14, r9
0x1401abd5d  movzx   r12d, r8b
0x1401abd61  mov     rbx, rdx
0x1401abd64  mov     rdi, rcx
0x1401abd67  test    rcx, rcx
0x1401abd6a  jz      loc_1401AC0B4
0x1401abd70  mov     eax, 801h
0x1401abd75  cmp     [rcx], ax
0x1401abd78  jnz     loc_1401AC0B4
0x1401abd7e  xor     r15d, r15d
0x1401abd81  mov     [rsp+0B8h+var_70], rcx
0x1401abd86  test    r9, r9
0x1401abd89  jz      short loc_1401ABD8E
0x1401abd8b  mov     [r9], r15
0x1401abd8e  mov     dl, 1; Wait
0x1401abd90  mov     rcx, [rcx+38h]; Resource
0x1401abd94  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401abd9b  nop     dword ptr [rax+rax+00h]
0x1401abda0  mov     rsi, [rdi+18h]
0x1401abda4  test    rsi, rsi
0x1401abda7  jz      loc_1401AC06F
0x1401abdad  mov     eax, [rsi+1ACh]
0x1401abdb3  bt      eax, 0Ah
0x1401abdb7  jb      loc_1401ABEA3
0x1401abdbd  mov     rax, [rsi+0C8h]
0x1401abdc4  movzx   ecx, word ptr [rax+8]
0x1401abdc8  cmp     [rdi+22h], cx
0x1401abdcc  jnb     loc_1401AC05D
0x1401abdd2  mov     ecx, [rdi+30h]
0x1401abdd5  mov     rax, [rsi+0D0h]
0x1401abddc  movzx   ecx, word ptr [rcx+rax+14h]
0x1401abde1  cmp     [rdi+20h], cx
0x1401abde5  jnz     loc_1401AC05D
0x1401abdeb  mov     [rsp+0B8h+var_78], rbx
0x1401abdf0  xorps   xmm0, xmm0
0x1401abdf3  xor     eax, eax
0x1401abdf5  movups  [rsp+0B8h+var_68], xmm0
0x1401abdfa  movups  xmmword ptr [rsp+0B8h+Event], xmm0
0x1401abdff  movups  xmmword ptr [rsp+0B8h+Event+10h], xmm0
0x1401abe04  mov     [rsp+0B8h+var_38], rax
0x1401abe0c  xor     r13d, r13d
0x1401abe0f  mov     [rsp+0B8h+var_88], r13d
0x1401abe14  mov     rax, ds:0FFFFF78000000320h
0x1401abe1e  mov     rax, [rsi+0C8h]
0x1401abe25  mov     rcx, [rax]
0x1401abe28  cmp     rbx, rcx
0x1401abe2b  cmovg   rbx, rcx
0x1401abe2f  mov     [rsp+0B8h+var_78], rbx
0x1401abe34  xor     r8d, r8d; State
0x1401abe37  mov     edx, 1; Type
0x1401abe3c  lea     rcx, [rsp+0B8h+Event]; Event
0x1401abe41  call    cs:__imp_KeInitializeEvent
0x1401abe48  nop     dword ptr [rax+rax+00h]
0x1401abe4d  mov     qword ptr [rsp+0B8h+Event+18h], rbx
0x1401abe52  mov     rcx, [rsi+1C8h]; Resource
0x1401abe59  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401abe60  nop     dword ptr [rax+rax+00h]
0x1401abe65  mov     [rsp+0B8h+arg_0], al
0x1401abe6c  mov     rcx, [rsi+1C8h]
0x1401abe73  add     rcx, 78h ; 'x'; FastMutex
0x1401abe77  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401abe7e  nop     dword ptr [rax+rax+00h]
0x1401abe83  mov     rax, [rsi+1C8h]
0x1401abe8a  cmp     rbx, [rsi+118h]
0x1401abe91  jg      short loc_1401ABEC7
0x1401abe93  lea     rcx, [rax+78h]; FastMutex
0x1401abe97  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401abe9e  nop     dword ptr [rax+rax+00h]
0x1401abea3  mov     r15d, [rsi+230h]
0x1401abeaa  mov     [rsp+0B8h+var_80], r15d
0x1401abeaf  test    r14, r14
0x1401abeb2  jz      loc_1401AC06F
0x1401abeb8  mov     rax, [rsi+118h]
0x1401abebf  mov     [r14], rax
0x1401abec2  jmp     loc_1401AC06F
0x1401abec7  cmp     dword ptr [rax+0B0h], 0
0x1401abece  jnz     loc_1401AC010
0x1401abed4  mov     dword ptr [rax+0B0h], 1
0x1401abede  mov     rax, gs:188h
0x1401abee7  mov     [rsi+1F8h], rax
0x1401abeee  mov     r15b, 1
0x1401abef1  mov     rcx, gs:188h; Thread
0x1401abefa  mov     edx, 10h; Priority
0x1401abeff  call    cs:__imp_KeSetPriorityThread
0x1401abf06  nop     dword ptr [rax+rax+00h]
0x1401abf0b  mov     r13d, eax
0x1401abf0e  mov     [rsp+0B8h+var_88], eax
0x1401abf12  call    cs:__imp_PsEnterPriorityRegion
0x1401abf19  nop     dword ptr [rax+rax+00h]
0x1401abf1e  mov     rcx, [rsi+1C8h]
0x1401abf25  add     rcx, 78h ; 'x'; FastMutex
0x1401abf29  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401abf30  nop     dword ptr [rax+rax+00h]
0x1401abf35  mov     rcx, rsi
0x1401abf38  test    r15b, r15b
0x1401abf3b  jz      short loc_1401ABF7F
0x1401abf3d  movzx   r9d, r12b
0x1401abf41  xor     r8d, r8d
0x1401abf44  mov     rdx, rbx
0x1401abf47  call    LfsFlushLfcbOnNewStack
0x1401abf4c  call    cs:__imp_PsLeavePriorityRegion
0x1401abf53  nop     dword ptr [rax+rax+00h]
0x1401abf58  cmp     r13d, 10h
0x1401abf5c  jz      loc_1401ABEA3
0x1401abf62  mov     rcx, gs:188h; Thread
0x1401abf6b  mov     edx, r13d; Priority
0x1401abf6e  call    cs:__imp_KeSetPriorityThread
0x1401abf75  nop     dword ptr [rax+rax+00h]
0x1401abf7a  jmp     loc_1401ABEA3
0x1401abf7f  lock inc dword ptr [rsi+1D0h]
0x1401abf86  call    LfsReleaseLfcb
0x1401abf8b  mov     [rsp+0B8h+Timeout], 0; Timeout
0x1401abf94  xor     r9d, r9d; Alertable
0x1401abf97  xor     r8d, r8d; WaitMode
0x1401abf9a  xor     edx, edx; WaitReason
0x1401abf9c  lea     rcx, [rsp+0B8h+Event]; Object
0x1401abfa1  call    cs:__imp_KeWaitForSingleObject
0x1401abfa8  nop     dword ptr [rax+rax+00h]
0x1401abfad  mov     rcx, [rsi+1C8h]; Resource
0x1401abfb4  mov     dl, 1; Wait
0x1401abfb6  cmp     [rsp+0B8h+arg_0], 0
0x1401abfbe  jz      short loc_1401AC002
0x1401abfc0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401abfc7  nop     dword ptr [rax+rax+00h]
0x1401abfcc  mov     eax, 0FFFFFFFFh
0x1401abfd1  lock xadd [rsi+1D0h], eax
0x1401abfd9  sub     eax, 1
0x1401abfdc  jz      short loc_1401ABFE3
0x1401abfde  jmp     loc_1401ABE6C
0x1401abfe3  mov     rcx, [rsi+260h]; Event
0x1401abfea  test    rcx, rcx
0x1401abfed  jz      short loc_1401ABFDE
0x1401abfef  xor     r8d, r8d; Wait
0x1401abff2  xor     edx, edx; Increment
0x1401abff4  call    cs:__imp_KeSetEvent
0x1401abffb  nop     dword ptr [rax+rax+00h]
0x1401ac000  jmp     short loc_1401ABFDE
0x1401ac002  call    cs:__imp_ExAcquireResourceSharedLite
0x1401ac009  nop     dword ptr [rax+rax+00h]
0x1401ac00e  jmp     short loc_1401ABFCC
0x1401ac010  lea     rcx, [rsi+1D8h]
0x1401ac017  mov     rax, [rcx]
0x1401ac01a  cmp     rax, rcx
0x1401ac01d  jnz     short loc_1401AC02F
0x1401ac01f  mov     rcx, [rax+8]
0x1401ac023  cmp     [rcx], rax
0x1401ac026  jz      short loc_1401AC03A
0x1401ac028  mov     ecx, 3
0x1401ac02d  int     29h; Win8: RtlFailFast(ecx)
0x1401ac02f  cmp     [rax+28h], rbx
0x1401ac033  jg      short loc_1401AC01F
0x1401ac035  mov     rax, [rax]
0x1401ac038  jmp     short loc_1401AC01A
0x1401ac03a  xor     r15b, r15b
0x1401ac03d  mov     qword ptr [rsp+0B8h+var_68], rax
0x1401ac042  mov     qword ptr [rsp+0B8h+var_68+8], rcx
0x1401ac047  lea     rdx, [rsp+0B8h+var_68]
0x1401ac04c  mov     [rcx], rdx
0x1401ac04f  lea     rcx, [rsp+0B8h+var_68]
0x1401ac054  mov     [rax+8], rcx
0x1401ac058  jmp     loc_1401ABF1E
0x1401ac05d  mov     ecx, 0C0000022h; Status
0x1401ac062  call    cs:__imp_ExRaiseStatus
0x1401ac06f  mov     rcx, [rdi+38h]; Resource
0x1401ac073  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ac07a  nop     dword ptr [rax+rax+00h]
0x1401ac07f  test    eax, eax
0x1401ac081  jz      short loc_1401AC093
0x1401ac083  mov     rcx, [rdi+38h]; Resource
0x1401ac087  call    cs:__imp_ExReleaseResourceLite
0x1401ac08e  nop     dword ptr [rax+rax+00h]
0x1401ac093  mov     eax, r15d
0x1401ac096  lea     r11, [rsp+0B8h+var_28]
0x1401ac09e  mov     rbx, [r11+38h]
0x1401ac0a2  mov     rsi, [r11+40h]
0x1401ac0a6  mov     rsp, r11
0x1401ac0a9  pop     r15
0x1401ac0ab  pop     r14
0x1401ac0ad  pop     r13
0x1401ac0af  pop     r12
0x1401ac0b1  pop     rdi
0x1401ac0b2  retn
0x1401ac0b4  mov     ecx, 0C0000022h; Status
0x1401ac0b9  call    cs:__imp_ExRaiseStatus
0x1402ae010  push    rbp
0x1402ae012  sub     rsp, 30h
0x1402ae016  mov     rbp, rdx
0x1402ae019  mov     rcx, [rbp+48h]
0x1402ae01d  call    LfsReleaseLch
0x1402ae022  nop
0x1402ae023  add     rsp, 30h
0x1402ae027  pop     rbp
0x1402ae028  retn
```
