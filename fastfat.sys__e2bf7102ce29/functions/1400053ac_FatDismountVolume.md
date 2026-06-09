# FatDismountVolume

- ea: `0x1400053ac`
- end: `0x1400055fb`
- name: `FatDismountVolume`
- size: `591`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x1400053ac`
- `0x140038eb4`
- `0x14003d880`
- `0x14003f1bc`
- `0x1400465f4`
- `0x1400466c8`
- `0x140048740`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14000546d`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1400055c5`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14000d289`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14000546d`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1400055c5`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14000d289`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005514`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005514`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140005530`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140005530`
- `ntoskrnl!FsRtlDismountComplete` at `0x14000554b`
- `ntoskrnl!FsRtlDismountComplete` at `0x14000d1ff`
- `ntoskrnl!FsRtlDismountComplete` at `0x14000554b`
- `ntoskrnl!FsRtlDismountComplete` at `0x14000d1ff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005486`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005486`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000555f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000559c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d219`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d243`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d257`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000555f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000559c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d219`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d243`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d257`

## pseudocode

```c
__int64 __fastcall FatDismountVolume(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  struct _IO_STACK_LOCATION *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 NextFcbBottomUp; // rax
  __int64 v11; // rcx
  __int64 i; // rdx
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v16[6]; // [rsp+28h] [rbp-30h] BYREF
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF
  struct _IO_STACK_LOCATION *v19; // [rsp+78h] [rbp+20h] BYREF

  Irql = 0;
  v18 = 0;
  v16[0] = 0;
  v19 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v18, v16, &v19) == 4
    && (v5 = v19) != 0
    && (*(_DWORD *)(&v19->Control + 1) & 0x20000) != 0 )
  {
    v6 = v18;
    if ( (*(_DWORD *)(v18 + 200) & 0x800) != 0 )
    {
      v7 = -1073741790;
    }
    else
    {
      v19 = CurrentStackLocation;
      if ( (*(_DWORD *)(v18 + 200) & 0x10000) != 0 )
      {
        v7 = -1073741202;
      }
      else
      {
        FsRtlNotifyVolumeEvent(CurrentStackLocation->FileObject, 1u);
        Entry[17] |= 2u;
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        v8 = 0;
        FatAcquireExclusiveVcb_Real(Entry, v6, 0);
        while ( 1 )
        {
          NextFcbBottomUp = FatGetNextFcbBottomUp(v9, v8, *(_QWORD *)(v6 + 208));
          v8 = NextFcbBottomUp;
          if ( !NextFcbBottomUp )
            break;
          FatAcquireExclusiveFcb(Entry, NextFcbBottomUp);
        }
        if ( (*(_DWORD *)(v6 + 200) & 0x10000) != 0 )
        {
          v7 = -1073741202;
        }
        else
        {
          FatFlushAndCleanVolume(Entry, Irp, v6, 2, 1);
          *(_DWORD *)(&v5->Control + 1) |= 0x10000u;
          *(_DWORD *)(v6 + 204) = 3;
          _InterlockedOr((volatile signed __int32 *)(v6 + 200), 0x10000u);
          IoAcquireVpbSpinLock(&Irql);
          *(_WORD *)(*(_QWORD *)(v6 + 192) + 4LL) |= 0x20u;
          IoReleaseVpbSpinLock(Irql);
          v7 = 0;
        }
        FsRtlDismountComplete(*(_QWORD *)(v6 + 136), v7);
        for ( i = 0; ; i = v14 )
        {
          v13 = FatGetNextFcbBottomUp(v11, i, *(_QWORD *)(v6 + 208));
          v14 = v13;
          if ( !v13 )
            break;
          ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
        }
        ExReleaseResourceLite((PERESOURCE)(v6 + 520));
        ExReleaseResourceLite(&Resource);
        if ( (int)(v7 + 0x80000000) >= 0 && v7 != -1073741202 )
          FsRtlNotifyVolumeEvent(CurrentStackLocation->FileObject, 2u);
      }
    }
  }
  else
  {
    v7 = -1073741811;
  }
  FatCompleteRequest_Real(Entry, Irp);
  return v7;
}

```

## disassembly

```asm
0x1400053ac  mov     rax, rsp
0x1400053af  mov     [rax+8], rbx
0x1400053b3  push    rsi
0x1400053b4  push    rdi
0x1400053b5  push    r13
0x1400053b7  push    r14
0x1400053b9  push    r15
0x1400053bb  sub     rsp, 30h
0x1400053bf  mov     r13, rdx
0x1400053c2  mov     rsi, rcx
0x1400053c5  mov     byte ptr [rax+10h], 0
0x1400053c9  mov     qword ptr [rax+18h], 0
0x1400053d1  mov     qword ptr [rax-30h], 0
0x1400053d9  mov     qword ptr [rax+20h], 0
0x1400053e1  mov     r15, [rdx+0B8h]
0x1400053e8  lea     r9, [rax+20h]
0x1400053ec  lea     r8, [rax-30h]
0x1400053f0  lea     rdx, [rax+18h]
0x1400053f4  mov     rcx, [r15+30h]
0x1400053f8  call    FatDecodeFileObject
0x1400053fd  cmp     eax, 4
0x140005400  jnz     loc_1400055D3
0x140005406  mov     rbx, [rsp+58h+arg_18]
0x14000540b  test    rbx, rbx
0x14000540e  jz      loc_1400055D3
0x140005414  test    dword ptr [rbx+4], 20000h
0x14000541b  jz      loc_1400055D3
0x140005421  mov     rdi, [rsp+58h+arg_10]
0x140005426  mov     eax, [rdi+0C8h]
0x14000542c  bt      eax, 0Bh
0x140005430  jnb     short loc_14000543C
0x140005432  mov     ebx, 0C0000022h
0x140005437  jmp     loc_1400055D8
0x14000543c  mov     [rsp+58h+arg_18], r15
0x140005441  mov     eax, [rdi+0C8h]
0x140005447  bt      eax, 10h
0x14000544b  jnb     short loc_140005457
0x14000544d  mov     ebx, 0C000026Eh
0x140005452  jmp     loc_1400055D8
0x140005457  mov     [rsp+58h+var_34], 0
0x14000545f  mov     [rsp+58h+var_38], 0
0x140005464  mov     edx, 1; EventCode
0x140005469  mov     rcx, [r15+30h]; FileObject
0x14000546d  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140005474  nop     dword ptr [rax+rax+00h]
0x140005479  or      dword ptr [rsi+44h], 2
0x14000547d  mov     dl, 1; Wait
0x14000547f  lea     rcx, Resource; Resource
0x140005486  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000548d  nop     dword ptr [rax+rax+00h]
0x140005492  nop
0x140005493  xor     r14d, r14d
0x140005496  xor     r8d, r8d
0x140005499  mov     rdx, rdi
0x14000549c  mov     rcx, rsi
0x14000549f  call    FatAcquireExclusiveVcb_Real
0x1400054a4  mov     r8, [rdi+0D0h]
0x1400054ab  mov     rdx, r14
0x1400054ae  call    FatGetNextFcbBottomUp
0x1400054b3  mov     r14, rax
0x1400054b6  test    rax, rax
0x1400054b9  jz      short loc_1400054C8
0x1400054bb  mov     rdx, rax
0x1400054be  mov     rcx, rsi
0x1400054c1  call    FatAcquireExclusiveFcb
0x1400054c6  jmp     short loc_1400054A4
0x1400054c8  mov     [rsp+58h+var_38], 1
0x1400054cd  mov     eax, [rdi+0C8h]
0x1400054d3  mov     r14d, 10000h
0x1400054d9  test    r14d, eax
0x1400054dc  jz      short loc_1400054E5
0x1400054de  mov     ebx, 0C000026Eh
0x1400054e3  jmp     short loc_14000553E
0x1400054e5  mov     r9d, 2
0x1400054eb  mov     r8, rdi
0x1400054ee  mov     rdx, r13
0x1400054f1  mov     rcx, rsi
0x1400054f4  call    FatFlushAndCleanVolume
0x1400054f9  or      [rbx+4], r14d
0x1400054fd  mov     dword ptr [rdi+0CCh], 3
0x140005507  lock or [rdi+0C8h], r14d
0x14000550f  lea     rcx, [rsp+58h+Irql]; Irql
0x140005514  call    cs:__imp_IoAcquireVpbSpinLock
0x14000551b  nop     dword ptr [rax+rax+00h]
0x140005520  mov     rax, [rdi+0C0h]
0x140005527  or      word ptr [rax+4], 20h
0x14000552c  mov     cl, [rsp+58h+Irql]; Irql
0x140005530  call    cs:__imp_IoReleaseVpbSpinLock
0x140005537  nop     dword ptr [rax+rax+00h]
0x14000553c  xor     ebx, ebx
0x14000553e  mov     [rsp+58h+var_34], ebx
0x140005542  mov     edx, ebx
0x140005544  mov     rcx, [rdi+88h]
0x14000554b  call    cs:__imp_FsRtlDismountComplete
0x140005552  nop     dword ptr [rax+rax+00h]
0x140005557  xor     edx, edx
0x140005559  jmp     short loc_14000556E
0x14000555b  mov     rcx, [r14+8]; Resource
0x14000555f  call    cs:__imp_ExReleaseResourceLite
0x140005566  nop     dword ptr [rax+rax+00h]
0x14000556b  mov     rdx, r14
0x14000556e  mov     r8, [rdi+0D0h]
0x140005575  call    FatGetNextFcbBottomUp
0x14000557a  test    rax, rax
0x14000557d  mov     r14, rax
0x140005580  jnz     short loc_14000555B
0x140005582  lea     rcx, [rdi+208h]; Resource
0x140005589  call    cs:__imp_ExReleaseResourceLite
0x140005590  nop     dword ptr [rax+rax+00h]
0x140005595  lea     rcx, Resource; Resource
0x14000559c  call    cs:__imp_ExReleaseResourceLite
0x1400055a3  nop     dword ptr [rax+rax+00h]
0x1400055a8  mov     ecx, 80000000h
0x1400055ad  lea     eax, [rbx+rcx]
0x1400055b0  test    ecx, eax
0x1400055b2  jnz     short loc_1400055D8
0x1400055b4  cmp     ebx, 0C000026Eh
0x1400055ba  jz      short loc_1400055D8
0x1400055bc  mov     edx, 2; EventCode
0x1400055c1  mov     rcx, [r15+30h]; FileObject
0x1400055c5  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1400055cc  nop     dword ptr [rax+rax+00h]
0x1400055d1  jmp     short loc_1400055D8
0x1400055d3  mov     ebx, 0C000000Dh
0x1400055d8  mov     r8d, ebx
0x1400055db  mov     rdx, r13; Irp
0x1400055de  mov     rcx, rsi; Entry
0x1400055e1  call    FatCompleteRequest_Real
0x1400055e6  mov     eax, ebx
0x1400055e8  mov     rbx, [rsp+58h+arg_0]
0x1400055ed  add     rsp, 30h
0x1400055f1  pop     r15
0x1400055f3  pop     r14
0x1400055f5  pop     r13
0x1400055f7  pop     rdi
0x1400055f8  pop     rsi
0x1400055f9  retn
0x14000d1dd  push    rbx
0x14000d1df  push    rbp
0x14000d1e0  push    rsi
0x14000d1e1  push    rdi
0x14000d1e2  push    r14
0x14000d1e4  sub     rsp, 20h
0x14000d1e8  mov     rbp, rdx
0x14000d1eb  movzx   r14d, cl
0x14000d1ef  mov     esi, [rbp+24h]
0x14000d1f2  mov     edx, esi
0x14000d1f4  mov     rdi, [rbp+70h]
0x14000d1f8  mov     rcx, [rdi+88h]
0x14000d1ff  call    cs:__imp_FsRtlDismountComplete
0x14000d206  nop     dword ptr [rax+rax+00h]
0x14000d20b  cmp     byte ptr [rbp+20h], 0
0x14000d20f  jz      short loc_14000D250
0x14000d211  xor     edx, edx
0x14000d213  jmp     short loc_14000D228
0x14000d215  mov     rcx, [rbx+8]; Resource
0x14000d219  call    cs:__imp_ExReleaseResourceLite
0x14000d220  nop     dword ptr [rax+rax+00h]
0x14000d225  mov     rdx, rbx
0x14000d228  mov     r8, [rdi+0D0h]
0x14000d22f  call    FatGetNextFcbBottomUp
0x14000d234  test    rax, rax
0x14000d237  mov     rbx, rax
0x14000d23a  jnz     short loc_14000D215
0x14000d23c  lea     rcx, [rdi+208h]; Resource
0x14000d243  call    cs:__imp_ExReleaseResourceLite
0x14000d24a  nop     dword ptr [rax+rax+00h]
0x14000d24f  nop
0x14000d250  lea     rcx, Resource; Resource
0x14000d257  call    cs:__imp_ExReleaseResourceLite
0x14000d25e  nop     dword ptr [rax+rax+00h]
0x14000d263  mov     eax, 80000000h
0x14000d268  add     eax, esi
0x14000d26a  js      short loc_14000D274
0x14000d26c  cmp     esi, 0C000026Eh
0x14000d272  jnz     short loc_14000D27C
0x14000d274  mov     eax, r14d
0x14000d277  test    r14b, r14b
0x14000d27a  jz      short loc_14000D296
0x14000d27c  mov     edx, 2; EventCode
0x14000d281  mov     rcx, [rbp+78h]
0x14000d285  mov     rcx, [rcx+30h]; FileObject
0x14000d289  call    cs:__imp_FsRtlNotifyVolumeEvent
0x14000d290  nop     dword ptr [rax+rax+00h]
0x14000d295  nop
0x14000d296  add     rsp, 20h
0x14000d29a  pop     r14
0x14000d29c  pop     rdi
0x14000d29d  pop     rsi
0x14000d29e  pop     rbp
0x14000d29f  pop     rbx
0x14000d2a0  retn
```
