# NbtCancelWinsSendIrp

- ea: `0x1400526a0`
- end: `0x1400527a3`
- name: `NbtCancelWinsSendIrp`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140040294`
- `0x1400526a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005276c`
- `ntoskrnl!IofCompleteRequest` at `0x14005276c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400526de`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400526de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400526f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400526f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052750`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005278b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052750`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005278b`

## pseudocode

```c
void __fastcall NbtCancelWinsSendIrp(__int64 a1, IRP *a2)
{
  PVOID FsContext; // rbx
  KIRQL v4; // al
  KIRQL v5; // r9
  __int64 v6; // r8
  char v7; // bl
  _QWORD *i; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rdx

  if ( (BYTE2(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1040, 22, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids);
  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v5 = v4;
  if ( FsContext == (PVOID)pWinsInfo )
  {
    v6 = pWinsInfo + 40;
    v7 = 0;
    for ( i = *(_QWORD **)(pWinsInfo + 40); i != (_QWORD *)v6; i = (_QWORD *)*i )
    {
      if ( a2 == (IRP *)(i - 21) )
      {
        v9 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i || (v10 = (_QWORD *)i[1], (_QWORD *)*v10 != i) )
          __fastfail(3u);
        *v10 = v9;
        v7 = 1;
        v9[1] = v10;
      }
    }
    KeReleaseSpinLock(&SpinLock, v5);
    if ( v7 )
    {
      a2->IoStatus.Status = -1073741536;
      IofCompleteRequest(a2, 2);
    }
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v4);
  }
}

```

## disassembly

```asm
0x1400526a0  mov     [rsp+arg_0], rbx
0x1400526a5  push    rdi
0x1400526a6  sub     rsp, 20h
0x1400526aa  mov     rdi, rdx
0x1400526ad  test    byte ptr cs:xmmword_140038420+2, 1
0x1400526b4  jz      short loc_1400526CC
0x1400526b6  mov     edx, 16h
0x1400526bb  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400526c2  mov     ecx, 410h
0x1400526c7  call    WPP_SF_
0x1400526cc  mov     rax, [rdi+0B8h]
0x1400526d3  mov     rcx, [rax+30h]
0x1400526d7  mov     rbx, [rcx+18h]
0x1400526db  mov     cl, [rdi+45h]; Irql
0x1400526de  call    cs:__imp_IoReleaseCancelSpinLock
0x1400526e5  nop     dword ptr [rax+rax+00h]
0x1400526ea  lea     rcx, SpinLock; SpinLock
0x1400526f1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400526f8  nop     dword ptr [rax+rax+00h]
0x1400526fd  mov     r8, cs:pWinsInfo
0x140052704  mov     r9b, al
0x140052707  cmp     rbx, r8
0x14005270a  jnz     short loc_140052781
0x14005270c  add     r8, 28h ; '('
0x140052710  xor     bl, bl
0x140052712  mov     rcx, [r8]
0x140052715  jmp     short loc_140052741
0x140052717  lea     rax, [rcx-0A8h]
0x14005271e  cmp     rdi, rax
0x140052721  jnz     short loc_14005273E
0x140052723  mov     rax, [rcx]
0x140052726  cmp     [rax+8], rcx
0x14005272a  jnz     short loc_14005277A
0x14005272c  mov     rdx, [rcx+8]
0x140052730  cmp     [rdx], rcx
0x140052733  jnz     short loc_14005277A
0x140052735  mov     [rdx], rax
0x140052738  mov     bl, 1
0x14005273a  mov     [rax+8], rdx
0x14005273e  mov     rcx, [rcx]
0x140052741  cmp     rcx, r8
0x140052744  jnz     short loc_140052717
0x140052746  mov     dl, r9b; NewIrql
0x140052749  lea     rcx, SpinLock; SpinLock
0x140052750  call    cs:__imp_KeReleaseSpinLock
0x140052757  nop     dword ptr [rax+rax+00h]
0x14005275c  test    bl, bl
0x14005275e  jz      short loc_140052797
0x140052760  mov     dl, 2; PriorityBoost
0x140052762  mov     dword ptr [rdi+30h], 0C0000120h
0x140052769  mov     rcx, rdi; Irp
0x14005276c  call    cs:__imp_IofCompleteRequest
0x140052773  nop     dword ptr [rax+rax+00h]
0x140052778  jmp     short loc_140052797
0x14005277a  mov     ecx, 3
0x14005277f  int     29h; Win8: RtlFailFast(ecx)
0x140052781  mov     dl, r9b; NewIrql
0x140052784  lea     rcx, SpinLock; SpinLock
0x14005278b  call    cs:__imp_KeReleaseSpinLock
0x140052792  nop     dword ptr [rax+rax+00h]
0x140052797  mov     rbx, [rsp+28h+arg_0]
0x14005279c  add     rsp, 20h
0x1400527a0  pop     rdi
0x1400527a1  retn
```
