# NbtCancelRcvDgram

- ea: `0x14002e060`
- end: `0x14002e1c2`
- name: `NbtCancelRcvDgram`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14002e060`
- `0x140040294`
- `0x140040590`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002e16e`
- `ntoskrnl!IofCompleteRequest` at `0x14002e16e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e091`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e147`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e196`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e091`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e147`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e196`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002e0b6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002e0b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e0a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e0a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e15d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e1ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e15d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e1ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e17f`

## pseudocode

```c
void __fastcall NbtCancelRcvDgram(__int64 a1, IRP *a2)
{
  KIRQL *p_CancelIrql; // rsi
  KIRQL v4; // bp
  _QWORD *FsContext; // rbx
  _QWORD *v6; // rcx
  _QWORD *i; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // r8
  KIRQL v10; // cl

  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_(1049, 82, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
  p_CancelIrql = &a2->CancelIrql;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  IoAcquireCancelSpinLock(&a2->CancelIrql);
  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( (BYTE11(xmmword_140038420) & 0x20) != 0 )
    WPP_SF_qq(1309, 83, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, a2, FsContext);
  if ( FsContext && *((_DWORD *)FsContext + 4) == 829320259 )
  {
    v6 = FsContext + 13;
    for ( i = (_QWORD *)FsContext[13]; i != v6; i = (_QWORD *)*i )
    {
      v8 = (_QWORD *)*i;
      if ( (IRP *)i[2] == a2 )
      {
        if ( (_QWORD *)v8[1] != i || (v9 = (_QWORD *)i[1], (_QWORD *)*v9 != i) )
          __fastfail(3u);
        *v9 = v8;
        v8[1] = v9;
        v10 = *p_CancelIrql;
        a2->IoStatus.Status = -1073741536;
        IoReleaseCancelSpinLock(v10);
        KeReleaseSpinLock(&SpinLock, v4);
        IofCompleteRequest(a2, 2);
        ExFreePoolWithTag(i, 0);
        return;
      }
    }
  }
  IoReleaseCancelSpinLock(*p_CancelIrql);
  KeReleaseSpinLock(&SpinLock, v4);
}

```

## disassembly

```asm
0x14002e060  push    rbx
0x14002e062  push    rbp
0x14002e063  push    rsi
0x14002e064  push    rdi
0x14002e065  sub     rsp, 38h
0x14002e069  mov     rdi, rdx
0x14002e06c  test    byte ptr cs:xmmword_140038420+3, 2
0x14002e073  jz      short loc_14002E08B
0x14002e075  mov     edx, 52h ; 'R'
0x14002e07a  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14002e081  mov     ecx, 419h
0x14002e086  call    WPP_SF_
0x14002e08b  lea     rsi, [rdi+45h]
0x14002e08f  mov     cl, [rsi]; Irql
0x14002e091  call    cs:__imp_IoReleaseCancelSpinLock
0x14002e098  nop     dword ptr [rax+rax+00h]
0x14002e09d  lea     rcx, SpinLock; SpinLock
0x14002e0a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e0ab  nop     dword ptr [rax+rax+00h]
0x14002e0b0  mov     rcx, rsi; Irql
0x14002e0b3  mov     bpl, al
0x14002e0b6  call    cs:__imp_IoAcquireCancelSpinLock
0x14002e0bd  nop     dword ptr [rax+rax+00h]
0x14002e0c2  mov     rcx, [rdi+0B8h]
0x14002e0c9  mov     rdx, [rcx+30h]
0x14002e0cd  mov     rbx, [rdx+18h]
0x14002e0d1  test    byte ptr cs:xmmword_140038420+0Bh, 20h
0x14002e0d8  jz      short loc_14002E0F8
0x14002e0da  mov     edx, 53h ; 'S'
0x14002e0df  mov     [rsp+58h+var_38], rbx
0x14002e0e4  mov     ecx, 51Dh
0x14002e0e9  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14002e0f0  mov     r9, rdi
0x14002e0f3  call    WPP_SF_qq
0x14002e0f8  test    rbx, rbx
0x14002e0fb  jz      loc_14002E194
0x14002e101  cmp     dword ptr [rbx+10h], 316E6C43h
0x14002e108  jnz     loc_14002E194
0x14002e10e  lea     rcx, [rbx+68h]
0x14002e112  mov     rbx, [rcx]
0x14002e115  cmp     rbx, rcx
0x14002e118  jz      short loc_14002E194
0x14002e11a  mov     rax, [rbx]
0x14002e11d  cmp     [rbx+10h], rdi
0x14002e121  jz      short loc_14002E128
0x14002e123  mov     rbx, rax
0x14002e126  jmp     short loc_14002E115
0x14002e128  cmp     [rax+8], rbx
0x14002e12c  jnz     short loc_14002E18D
0x14002e12e  mov     r8, [rbx+8]
0x14002e132  cmp     [r8], rbx
0x14002e135  jnz     short loc_14002E18D
0x14002e137  mov     [r8], rax
0x14002e13a  mov     [rax+8], r8
0x14002e13e  mov     cl, [rsi]; Irql
0x14002e140  mov     dword ptr [rdi+30h], 0C0000120h
0x14002e147  call    cs:__imp_IoReleaseCancelSpinLock
0x14002e14e  nop     dword ptr [rax+rax+00h]
0x14002e153  mov     dl, bpl; NewIrql
0x14002e156  lea     rcx, SpinLock; SpinLock
0x14002e15d  call    cs:__imp_KeReleaseSpinLock
0x14002e164  nop     dword ptr [rax+rax+00h]
0x14002e169  mov     dl, 2; PriorityBoost
0x14002e16b  mov     rcx, rdi; Irp
0x14002e16e  call    cs:__imp_IofCompleteRequest
0x14002e175  nop     dword ptr [rax+rax+00h]
0x14002e17a  xor     edx, edx; Tag
0x14002e17c  mov     rcx, rbx; P
0x14002e17f  call    cs:__imp_ExFreePoolWithTag
0x14002e186  nop     dword ptr [rax+rax+00h]
0x14002e18b  jmp     short loc_14002E1B8
0x14002e18d  mov     ecx, 3
0x14002e192  int     29h; Win8: RtlFailFast(ecx)
0x14002e194  mov     cl, [rsi]; Irql
0x14002e196  call    cs:__imp_IoReleaseCancelSpinLock
0x14002e19d  nop     dword ptr [rax+rax+00h]
0x14002e1a2  mov     dl, bpl; NewIrql
0x14002e1a5  lea     rcx, SpinLock; SpinLock
0x14002e1ac  call    cs:__imp_KeReleaseSpinLock
0x14002e1b3  nop     dword ptr [rax+rax+00h]
0x14002e1b8  add     rsp, 38h
0x14002e1bc  pop     rdi
0x14002e1bd  pop     rsi
0x14002e1be  pop     rbp
0x14002e1bf  pop     rbx
0x14002e1c0  retn
```
