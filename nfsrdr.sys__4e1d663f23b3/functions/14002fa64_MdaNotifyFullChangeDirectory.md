# MdaNotifyFullChangeDirectory

- ea: `0x14002fa64`
- end: `0x14002fe09`
- name: `MdaNotifyFullChangeDirectory`
- size: `933`
- prototype: `void __fastcall(PFAST_MUTEX FastMutex, _QWORD *, __int64, const UNICODE_STRING *, char, int, int, PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001a820`

## callees

- `0x1400159cc`
- `0x14002f4b0`
- `0x14002f744`
- `0x14002f954`
- `0x14002fa64`
- `0x140030724`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002fc00`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002fc00`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002fad4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002fad4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002fdc2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b6ed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002fdc2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b6ed`
- `ntoskrnl!ExAllocatePool2` at `0x14002fba7`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd63`
- `ntoskrnl!ExAllocatePool2` at `0x14002fba7`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd63`
- `rdbss!RxLowIoCompletion` at `0x14002fb64`
- `rdbss!RxLowIoCompletion` at `0x14002fcff`
- `rdbss!RxLowIoCompletion` at `0x14002fb64`
- `rdbss!RxLowIoCompletion` at `0x14002fcff`

## pseudocode

```c
void __fastcall MdaNotifyFullChangeDirectory(
        PFAST_MUTEX FastMutex,
        _QWORD *a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        char a5,
        int a6,
        int a7,
        PRX_CONTEXT RxContext)
{
  struct _KTHREAD *CurrentThread; // rbx
  _QWORD *i; // rbx
  _QWORD *v13; // rcx
  PIRP CurrentIrp; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 IsNotifyOnList; // rax
  ULONG_PTR v17; // rbx
  void *Pool2; // rax
  _WORD *v19; // rax
  _QWORD *v20; // rcx
  __int16 v21; // cx
  unsigned int v22; // r8d
  _QWORD *v23; // rax
  ULONG_PTR v24; // rbx
  ULONG_PTR **v25; // rcx
  ULONG_PTR *v26; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  if ( FastMutex )
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)&FastMutex[1].Count )
    {
      ExAcquireFastMutexUnsafe(FastMutex);
      *(_QWORD *)&FastMutex[1].Count = CurrentThread;
    }
    ++LODWORD(FastMutex[1].Owner);
    if ( !RxContext )
    {
      for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
      {
        v13 = i - 70;
        if ( *(i - 68) == a3 )
        {
          *((_WORD *)v13 + 296) |= 0x20u;
          if ( (_QWORD *)v13[72] != v13 + 72 )
            MdaNotifyCompleteIrpList(v13, 3221225558LL);
        }
      }
      goto LABEL_41;
    }
    CurrentIrp = RxContext->CurrentIrp;
    CurrentStackLocation = CurrentIrp->Tail.Overlay.CurrentStackLocation;
    CurrentIrp->IoStatus.Status = 0;
    RxContext->CurrentIrp->IoStatus.Information = 0;
    if ( (CurrentStackLocation->FileObject->Flags & 0x4000) != 0 )
      goto LABEL_15;
    IsNotifyOnList = MdaIsNotifyOnList(a2, a3);
    v17 = IsNotifyOnList;
    if ( IsNotifyOnList )
    {
      v21 = *(_WORD *)(IsNotifyOnList + 592);
      if ( (v21 & 4) != 0 )
      {
LABEL_15:
        RxContext->StoredStatus = 267;
LABEL_16:
        RxLowIoCompletion(RxContext);
        goto LABEL_41;
      }
      if ( (v21 & 0x20) != 0 )
      {
        RxContext->StoredStatus = -1073741738;
        goto LABEL_16;
      }
      if ( (v21 & 0xA) == 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
        }
        *(_WORD *)(v17 + 592) &= ~2u;
        RxContext->StoredStatus = 268;
        RxLowIoCompletion(RxContext);
        goto LABEL_41;
      }
      v22 = *(_DWORD *)(IsNotifyOnList + 624);
      if ( v22 && (v21 & 8) == 0 )
      {
        *(_QWORD *)(IsNotifyOnList + 624) = 0;
        MdaNotifyCompleteIrp(RxContext, IsNotifyOnList, v22, 0);
        goto LABEL_41;
      }
    }
    else
    {
      Pool2 = (void *)ExAllocatePool2(258, 632, 1683121742);
      v17 = (ULONG_PTR)Pool2;
      if ( !Pool2 )
        goto LABEL_41;
      memset(Pool2, 0, 0x278u);
      *(_QWORD *)v17 = FastMutex;
      *(_QWORD *)(v17 + 8) = a3;
      *(_QWORD *)(v17 + 16) = CurrentStackLocation->FileObject->FsContext;
      *(_WORD *)(v17 + 26) = 520;
      *(_QWORD *)(v17 + 32) = v17 + 40;
      RtlCopyUnicodeString((PUNICODE_STRING)(v17 + 24), a4);
      *(_QWORD *)(v17 + 584) = v17 + 576;
      *(_QWORD *)(v17 + 576) = v17 + 576;
      v19 = (_WORD *)(v17 + 592);
      if ( a5 )
        *v19 |= 1u;
      *(_BYTE *)(v17 + 594) = 2;
      if ( a4->Length == 2 )
        *v19 |= 0x10u;
      *(_DWORD *)(v17 + 596) = a7;
      *(_DWORD *)(v17 + 616) = CurrentStackLocation->Parameters.Read.Length;
      v20 = (_QWORD *)a2[1];
      if ( (_QWORD *)*v20 != a2 )
LABEL_39:
        __fastfail(3u);
      *(_QWORD *)(v17 + 560) = a2;
      *(_QWORD *)(v17 + 568) = v20;
      *v20 = v17 + 560;
      a2[1] = v17 + 560;
    }
    RxContext->CurrentIrp->IoStatus.Information = v17;
    v23 = (_QWORD *)ExAllocatePool2(258, 24, 1699898958);
    if ( v23 )
    {
      *v23 = RxContext;
      v24 = v17 + 576;
      v25 = *(ULONG_PTR ***)(v24 + 8);
      if ( *v25 != (ULONG_PTR *)v24 )
        goto LABEL_39;
      v26 = v23 + 1;
      *v26 = v24;
      v26[1] = (ULONG_PTR)v25;
      *v25 = v26;
      *(_QWORD *)(v24 + 8) = v26;
      MdaNotifySetCancelRoutine(RxContext);
    }
LABEL_41:
    if ( LODWORD(FastMutex[1].Owner)-- == 1 )
    {
      *(_QWORD *)&FastMutex[1].Count = 0;
      ExReleaseFastMutexUnsafe(FastMutex);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14002fa64  mov     [rsp+arg_8], rbx
0x14002fa69  mov     [rsp+SourceString], r9
0x14002fa6e  mov     [rsp+arg_0], rcx
0x14002fa73  push    rsi
0x14002fa74  push    rdi
0x14002fa75  push    r13
0x14002fa77  push    r14
0x14002fa79  push    r15
0x14002fa7b  sub     rsp, 30h
0x14002fa7f  mov     r14, r8
0x14002fa82  mov     r15, rdx
0x14002fa85  mov     rsi, rcx
0x14002fa88  lea     rax, WPP_GLOBAL_Control
0x14002fa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fa96  cmp     rcx, rax
0x14002fa99  jz      short loc_14002FAB9
0x14002fa9b  test    dword ptr [rcx+2Ch], 80000h
0x14002faa2  jz      short loc_14002FAB9
0x14002faa4  mov     edx, 0Eh
0x14002faa9  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002fab0  mov     rcx, [rcx+18h]
0x14002fab4  call    WPP_SF_
0x14002fab9  test    rsi, rsi
0x14002fabc  jz      loc_14002FDF6
0x14002fac2  mov     rbx, gs:188h
0x14002facb  cmp     rbx, [rsi+38h]
0x14002facf  jz      short loc_14002FAE4
0x14002fad1  mov     rcx, rsi; FastMutex
0x14002fad4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002fadb  nop     dword ptr [rax+rax+00h]
0x14002fae0  mov     [rsi+38h], rbx
0x14002fae4  inc     dword ptr [rsi+40h]
0x14002fae7  mov     rdi, [rsp+58h+RxContext]
0x14002faef  test    rdi, rdi
0x14002faf2  jnz     short loc_14002FB2C
0x14002faf4  mov     rbx, [r15]
0x14002faf7  cmp     rbx, r15
0x14002fafa  jz      short loc_14002FB70
0x14002fafc  lea     rcx, [rbx-230h]
0x14002fb03  cmp     [rcx+10h], r14
0x14002fb07  jnz     short loc_14002FB27
0x14002fb09  or      word ptr [rcx+250h], 20h
0x14002fb11  lea     rax, [rcx+240h]
0x14002fb18  cmp     [rax], rax
0x14002fb1b  jz      short loc_14002FB27
0x14002fb1d  mov     edx, 0C0000056h
0x14002fb22  call    MdaNotifyCompleteIrpList
0x14002fb27  mov     rbx, [rbx]
0x14002fb2a  jmp     short loc_14002FAF7
0x14002fb2c  mov     rax, [rdi+28h]
0x14002fb30  mov     r13, [rax+0B8h]
0x14002fb37  mov     dword ptr [rax+30h], 0
0x14002fb3e  mov     rax, [rdi+28h]
0x14002fb42  mov     qword ptr [rax+38h], 0
0x14002fb4a  mov     rax, [r13+30h]
0x14002fb4e  test    dword ptr [rax+50h], 4000h
0x14002fb55  jz      short loc_14002FB7B
0x14002fb57  mov     dword ptr [rdi+0B0h], 10Bh
0x14002fb61  mov     rcx, rdi; RxContext
0x14002fb64  call    cs:__imp_RxLowIoCompletion
0x14002fb6b  nop     dword ptr [rax+rax+00h]
0x14002fb70  mov     r14d, 10h
0x14002fb76  jmp     loc_14002FDAA
0x14002fb7b  mov     rdx, r14
0x14002fb7e  mov     rcx, r15
0x14002fb81  call    MdaIsNotifyOnList
0x14002fb86  mov     rbx, rax
0x14002fb89  mov     [rsp+58h+var_38], rax
0x14002fb8e  test    rax, rax
0x14002fb91  jnz     loc_14002FC89
0x14002fb97  mov     edx, 278h
0x14002fb9c  mov     ecx, 102h
0x14002fba1  mov     r8d, 6452664Eh
0x14002fba7  call    cs:__imp_ExAllocatePool2
0x14002fbae  nop     dword ptr [rax+rax+00h]
0x14002fbb3  mov     rbx, rax
0x14002fbb6  mov     [rsp+58h+var_38], rax
0x14002fbbb  test    rax, rax
0x14002fbbe  jz      short loc_14002FB70
0x14002fbc0  xor     edx, edx; Val
0x14002fbc2  mov     r8d, 278h; Size
0x14002fbc8  mov     rcx, rax; void *
0x14002fbcb  call    memset
0x14002fbd0  mov     [rbx], rsi
0x14002fbd3  mov     [rbx+8], r14
0x14002fbd7  mov     rax, [r13+30h]
0x14002fbdb  mov     rcx, [rax+18h]
0x14002fbdf  mov     [rbx+10h], rcx
0x14002fbe3  mov     eax, 208h
0x14002fbe8  mov     [rbx+1Ah], ax
0x14002fbec  lea     rax, [rbx+28h]
0x14002fbf0  mov     [rbx+20h], rax
0x14002fbf4  lea     rcx, [rbx+18h]; DestinationString
0x14002fbf8  mov     r14, [rsp+58h+SourceString]
0x14002fbfd  mov     rdx, r14; SourceString
0x14002fc00  call    cs:__imp_RtlCopyUnicodeString
0x14002fc07  nop     dword ptr [rax+rax+00h]
0x14002fc0c  lea     rax, [rbx+240h]
0x14002fc13  mov     [rax+8], rax
0x14002fc17  mov     [rax], rax
0x14002fc1a  lea     rax, [rbx+250h]
0x14002fc21  cmp     [rsp+58h+arg_20], 0
0x14002fc29  jz      short loc_14002FC33
0x14002fc2b  mov     ecx, 1
0x14002fc30  or      [rax], cx
0x14002fc33  mov     byte ptr [rbx+252h], 2
0x14002fc3a  cmp     word ptr [r14], 2
0x14002fc3f  mov     r14d, 10h
0x14002fc45  jnz     short loc_14002FC4B
0x14002fc47  or      [rax], r14w
0x14002fc4b  mov     eax, [rsp+58h+arg_30]
0x14002fc52  mov     [rbx+254h], eax
0x14002fc58  mov     eax, [r13+8]
0x14002fc5c  mov     [rbx+268h], eax
0x14002fc62  mov     rcx, [r15+8]
0x14002fc66  cmp     [rcx], r15
0x14002fc69  jnz     loc_14002FD87
0x14002fc6f  lea     rax, [rbx+230h]
0x14002fc76  mov     [rax], r15
0x14002fc79  mov     [rax+8], rcx
0x14002fc7d  mov     [rcx], rax
0x14002fc80  mov     [r15+8], rax
0x14002fc84  jmp     loc_14002FD4B
0x14002fc89  movzx   ecx, word ptr [rax+250h]
0x14002fc90  test    cl, 4
0x14002fc93  jnz     loc_14002FB57
0x14002fc99  test    cl, 20h
0x14002fc9c  jz      short loc_14002FCAD
0x14002fc9e  mov     dword ptr [rdi+0B0h], 0C0000056h
0x14002fca8  jmp     loc_14002FB61
0x14002fcad  mov     al, cl
0x14002fcaf  and     al, 0Ah
0x14002fcb1  cmp     al, 2
0x14002fcb3  jnz     short loc_14002FD16
0x14002fcb5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fcbc  lea     r15, WPP_GLOBAL_Control
0x14002fcc3  cmp     rcx, r15
0x14002fcc6  jz      short loc_14002FCE6
0x14002fcc8  test    dword ptr [rcx+2Ch], 80000h
0x14002fccf  jz      short loc_14002FCE6
0x14002fcd1  mov     edx, 0Fh
0x14002fcd6  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002fcdd  mov     rcx, [rcx+18h]
0x14002fce1  call    WPP_SF_
0x14002fce6  mov     eax, 0FFFDh
0x14002fceb  and     [rbx+250h], ax
0x14002fcf2  mov     dword ptr [rdi+0B0h], 10Ch
0x14002fcfc  mov     rcx, rdi; RxContext
0x14002fcff  call    cs:__imp_RxLowIoCompletion
0x14002fd06  nop     dword ptr [rax+rax+00h]
0x14002fd0b  mov     r14d, 10h
0x14002fd11  jmp     loc_14002FDB1
0x14002fd16  mov     r8d, [rbx+270h]
0x14002fd1d  test    r8d, r8d
0x14002fd20  jz      short loc_14002FD45
0x14002fd22  test    cl, 8
0x14002fd25  jnz     short loc_14002FD45
0x14002fd27  mov     qword ptr [rbx+270h], 0
0x14002fd32  xor     r9d, r9d
0x14002fd35  mov     rdx, rbx
0x14002fd38  mov     rcx, rdi; RxContext
0x14002fd3b  call    MdaNotifyCompleteIrp
0x14002fd40  jmp     loc_14002FB70
0x14002fd45  mov     r14d, 10h
0x14002fd4b  mov     rax, [rdi+28h]
0x14002fd4f  mov     [rax+38h], rbx
0x14002fd53  mov     edx, 18h
0x14002fd58  mov     ecx, 102h
0x14002fd5d  mov     r8d, 6552664Eh
0x14002fd63  call    cs:__imp_ExAllocatePool2
0x14002fd6a  nop     dword ptr [rax+rax+00h]
0x14002fd6f  test    rax, rax
0x14002fd72  jz      short loc_14002FDAA
0x14002fd74  mov     [rax], rdi
0x14002fd77  add     rbx, 240h
0x14002fd7e  mov     rcx, [rbx+8]
0x14002fd82  cmp     [rcx], rbx
0x14002fd85  jz      short loc_14002FD8E
0x14002fd87  mov     ecx, 3
0x14002fd8c  int     29h; Win8: RtlFailFast(ecx)
0x14002fd8e  add     rax, 8
0x14002fd92  mov     [rax], rbx
0x14002fd95  mov     [rax+8], rcx
0x14002fd99  mov     [rcx], rax
0x14002fd9c  mov     [rbx+8], rax
0x14002fda0  xor     edx, edx
0x14002fda2  mov     rcx, rdi; RxContext
0x14002fda5  call    MdaNotifySetCancelRoutine
0x14002fdaa  lea     r15, WPP_GLOBAL_Control
0x14002fdb1  add     dword ptr [rsi+40h], 0FFFFFFFFh
0x14002fdb5  jnz     short loc_14002FDCE
0x14002fdb7  mov     qword ptr [rsi+38h], 0
0x14002fdbf  mov     rcx, rsi; FastMutex
0x14002fdc2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002fdc9  nop     dword ptr [rax+rax+00h]
0x14002fdce  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdd5  cmp     rcx, r15
0x14002fdd8  jz      short loc_14002FDF6
0x14002fdda  test    dword ptr [rcx+2Ch], 80000h
0x14002fde1  jz      short loc_14002FDF6
0x14002fde3  mov     edx, r14d
0x14002fde6  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002fded  mov     rcx, [rcx+18h]
0x14002fdf1  call    WPP_SF_
0x14002fdf6  mov     rbx, [rsp+58h+arg_8]
0x14002fdfb  add     rsp, 30h
0x14002fdff  pop     r15
0x14002fe01  pop     r14
0x14002fe03  pop     r13
0x14002fe05  pop     rdi
0x14002fe06  pop     rsi
0x14002fe07  retn
0x14003b6d2  push    rbp
0x14003b6d4  sub     rsp, 20h
0x14003b6d8  mov     rbp, rdx
0x14003b6db  mov     rcx, [rbp+60h]; FastMutex
0x14003b6df  sub     dword ptr [rcx+40h], 1
0x14003b6e3  jnz     short loc_14003B6FA
0x14003b6e5  mov     qword ptr [rcx+38h], 0
0x14003b6ed  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003b6f4  nop     dword ptr [rax+rax+00h]
0x14003b6f9  nop
0x14003b6fa  lea     rax, WPP_GLOBAL_Control
0x14003b701  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b708  cmp     rcx, rax
0x14003b70b  jz      short loc_14003B72C
0x14003b70d  test    dword ptr [rcx+2Ch], 80000h
0x14003b714  jz      short loc_14003B72C
0x14003b716  mov     edx, 10h
0x14003b71b  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14003b722  mov     rcx, [rcx+18h]
0x14003b726  call    WPP_SF_
0x14003b72b  nop
0x14003b72c  add     rsp, 20h
0x14003b730  pop     rbp
0x14003b731  retn
```
