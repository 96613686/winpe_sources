# NbtCancelListen

- ea: `0x14002def0`
- end: `0x14002e059`
- name: `NbtCancelListen`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14002def0`
- `0x1400401c4`
- `0x140040294`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002e009`
- `ntoskrnl!IofCompleteRequest` at `0x14002e009`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002df68`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e043`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002df68`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002e043`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dfaa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dfaa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dff1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e032`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dff1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e01a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e01a`

## pseudocode

```c
void __fastcall NbtCancelListen(__int64 a1, IRP *a2)
{
  _DWORD *FsContext; // rsi
  __int64 v4; // rbx
  KSPIN_LOCK *v5; // rbp
  KIRQL v6; // al
  _QWORD *v7; // rcx
  KIRQL v8; // dl
  _QWORD *i; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // r8

  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_(1049, 72, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( !FsContext
    || ((FsContext[4] - 829321027) & 0xFEFFFFFF) != 0
    || (v4 = *((_QWORD *)FsContext + 5)) == 0
    || ((*(_DWORD *)(v4 + 16) - 829320259) & 0xFEFFFFFF) != 0 )
  {
    IoReleaseCancelSpinLock(a2->CancelIrql);
  }
  else
  {
    IoReleaseCancelSpinLock(a2->CancelIrql);
    if ( (BYTE10(xmmword_140038420) & 0x10) != 0 )
      WPP_SF_qqq(1300, 73, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, a2, FsContext, v4);
    v5 = (KSPIN_LOCK *)(v4 + 264);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 264));
    v7 = (_QWORD *)(v4 + 120);
    v8 = v6;
    for ( i = *(_QWORD **)(v4 + 120); ; i = (_QWORD *)*i )
    {
      if ( i == v7 )
      {
        KeReleaseSpinLock(v5, v6);
        return;
      }
      if ( (_DWORD *)i[4] == FsContext && (IRP *)i[2] == a2 )
        break;
    }
    v10 = (_QWORD *)*i;
    if ( *(_QWORD **)(*i + 8LL) != i || (v11 = (_QWORD *)i[1], (_QWORD *)*v11 != i) )
      __fastfail(3u);
    *v11 = v10;
    v10[1] = v11;
    KeReleaseSpinLock(v5, v8);
    a2->IoStatus.Status = -1073741536;
    IofCompleteRequest(a2, 2);
    ExFreePoolWithTag(i, 0);
  }
}

```

## disassembly

```asm
0x14002def0  push    rbx
0x14002def2  push    rbp
0x14002def3  push    rsi
0x14002def4  push    rdi
0x14002def5  sub     rsp, 38h
0x14002def9  mov     rdi, rdx
0x14002defc  test    byte ptr cs:xmmword_140038420+3, 2
0x14002df03  jz      short loc_14002DF1B
0x14002df05  mov     edx, 48h ; 'H'
0x14002df0a  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14002df11  mov     ecx, 419h
0x14002df16  call    WPP_SF_
0x14002df1b  mov     rax, [rdi+0B8h]
0x14002df22  mov     rcx, [rax+30h]
0x14002df26  mov     rsi, [rcx+18h]
0x14002df2a  test    rsi, rsi
0x14002df2d  jz      loc_14002E040
0x14002df33  mov     eax, [rsi+10h]
0x14002df36  mov     ecx, 0FEFFFFFFh
0x14002df3b  sub     eax, 316E6F43h
0x14002df40  test    ecx, eax
0x14002df42  jnz     loc_14002E040
0x14002df48  mov     rbx, [rsi+28h]
0x14002df4c  test    rbx, rbx
0x14002df4f  jz      loc_14002E040
0x14002df55  mov     eax, [rbx+10h]
0x14002df58  sub     eax, 316E6C43h
0x14002df5d  test    ecx, eax
0x14002df5f  jnz     loc_14002E040
0x14002df65  mov     cl, [rdi+45h]; Irql
0x14002df68  call    cs:__imp_IoReleaseCancelSpinLock
0x14002df6f  nop     dword ptr [rax+rax+00h]
0x14002df74  test    byte ptr cs:xmmword_140038420+0Ah, 10h
0x14002df7b  jz      short loc_14002DFA0
0x14002df7d  mov     edx, 49h ; 'I'
0x14002df82  mov     [rsp+58h+var_30], rbx
0x14002df87  mov     ecx, 514h
0x14002df8c  mov     [rsp+58h+var_38], rsi
0x14002df91  mov     r9, rdi
0x14002df94  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14002df9b  call    WPP_SF_qqq
0x14002dfa0  lea     rbp, [rbx+108h]
0x14002dfa7  mov     rcx, rbp; SpinLock
0x14002dfaa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002dfb1  nop     dword ptr [rax+rax+00h]
0x14002dfb6  lea     rcx, [rbx+78h]
0x14002dfba  mov     dl, al; NewIrql
0x14002dfbc  mov     rbx, [rcx]
0x14002dfbf  cmp     rbx, rcx
0x14002dfc2  jz      short loc_14002E02F
0x14002dfc4  cmp     [rbx+20h], rsi
0x14002dfc8  jnz     short loc_14002DFD0
0x14002dfca  cmp     [rbx+10h], rdi
0x14002dfce  jz      short loc_14002DFD5
0x14002dfd0  mov     rbx, [rbx]
0x14002dfd3  jmp     short loc_14002DFBF
0x14002dfd5  mov     rax, [rbx]
0x14002dfd8  cmp     [rax+8], rbx
0x14002dfdc  jnz     short loc_14002E028
0x14002dfde  mov     r8, [rbx+8]
0x14002dfe2  cmp     [r8], rbx
0x14002dfe5  jnz     short loc_14002E028
0x14002dfe7  mov     [r8], rax
0x14002dfea  mov     rcx, rbp; SpinLock
0x14002dfed  mov     [rax+8], r8
0x14002dff1  call    cs:__imp_KeReleaseSpinLock
0x14002dff8  nop     dword ptr [rax+rax+00h]
0x14002dffd  mov     dl, 2; PriorityBoost
0x14002dfff  mov     dword ptr [rdi+30h], 0C0000120h
0x14002e006  mov     rcx, rdi; Irp
0x14002e009  call    cs:__imp_IofCompleteRequest
0x14002e010  nop     dword ptr [rax+rax+00h]
0x14002e015  xor     edx, edx; Tag
0x14002e017  mov     rcx, rbx; P
0x14002e01a  call    cs:__imp_ExFreePoolWithTag
0x14002e021  nop     dword ptr [rax+rax+00h]
0x14002e026  jmp     short loc_14002E04F
0x14002e028  mov     ecx, 3
0x14002e02d  int     29h; Win8: RtlFailFast(ecx)
0x14002e02f  mov     rcx, rbp; SpinLock
0x14002e032  call    cs:__imp_KeReleaseSpinLock
0x14002e039  nop     dword ptr [rax+rax+00h]
0x14002e03e  jmp     short loc_14002E04F
0x14002e040  mov     cl, [rdi+45h]; Irql
0x14002e043  call    cs:__imp_IoReleaseCancelSpinLock
0x14002e04a  nop     dword ptr [rax+rax+00h]
0x14002e04f  add     rsp, 38h
0x14002e053  pop     rdi
0x14002e054  pop     rsi
0x14002e055  pop     rbp
0x14002e056  pop     rbx
0x14002e057  retn
```
