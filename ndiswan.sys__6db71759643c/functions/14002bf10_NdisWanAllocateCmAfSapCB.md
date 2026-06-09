# NdisWanAllocateCmAfSapCB

- ea: `0x14002bf10`
- end: `0x14002c014`
- name: `NdisWanAllocateCmAfSapCB`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140026170`

## callees

- `0x14000a290`
- `0x140016700`
- `0x14002bf10`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002bfdb`
- `ntoskrnl!KeInitializeEvent` at `0x14002bfdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bff4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bff4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bf9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bf9e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002bf29`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002bf29`

## pseudocode

```c
char *__fastcall NdisWanAllocateCmAfSapCB(__int64 a1)
{
  char *v2; // rax
  char *v3; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx

  v2 = (char *)ExAllocateFromNPagedLookasideList(&AfSapVcCBList);
  v3 = v2;
  if ( v2 )
  {
    memset(v2, 0, 0x68u);
    *((_DWORD *)v3 + 4) = 538996035;
    *((_QWORD *)v3 + 3) = a1;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    *(_BYTE *)(a1 + 168) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 160));
    v5 = (_QWORD *)(a1 + 48);
    v6 = *(_QWORD *)(a1 + 48);
    if ( *(_QWORD *)(v6 + 8) != a1 + 48 )
      __fastfail(3u);
    *(_QWORD *)v3 = v6;
    *((_QWORD *)v3 + 1) = v5;
    *(_QWORD *)(v6 + 8) = v3;
    *v5 = v3;
    KeInitializeEvent((PRKEVENT)(v3 + 56), NotificationEvent, 0);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 64));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 160), *(_BYTE *)(a1 + 168));
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14002bf10  mov     [rsp+arg_0], rbx
0x14002bf15  mov     [rsp+arg_8], rsi
0x14002bf1a  push    rdi
0x14002bf1b  sub     rsp, 20h
0x14002bf1f  mov     rdi, rcx
0x14002bf22  lea     rcx, AfSapVcCBList; Lookaside
0x14002bf29  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002bf30  nop     dword ptr [rax+rax+00h]
0x14002bf35  mov     rbx, rax
0x14002bf38  test    rax, rax
0x14002bf3b  jnz     short loc_14002BF77
0x14002bf3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf44  lea     rax, WPP_GLOBAL_Control
0x14002bf4b  cmp     rcx, rax
0x14002bf4e  jz      short loc_14002BF70
0x14002bf50  mov     eax, [rcx+2Ch]
0x14002bf53  test    al, 40h
0x14002bf55  jz      short loc_14002BF70
0x14002bf57  cmp     byte ptr [rcx+29h], 2
0x14002bf5b  jb      short loc_14002BF70
0x14002bf5d  mov     rcx, [rcx+18h]
0x14002bf61  lea     edx, [rbx+27h]
0x14002bf64  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14002bf6b  call    WPP_SF_
0x14002bf70  xor     eax, eax
0x14002bf72  jmp     loc_14002C003
0x14002bf77  xor     edx, edx; Val
0x14002bf79  mov     rcx, rbx; void *
0x14002bf7c  lea     r8d, [rdx+68h]; Size
0x14002bf80  call    memset
0x14002bf85  mov     dword ptr [rbx+10h], 20206D43h
0x14002bf8c  mov     [rbx+18h], rdi
0x14002bf90  lock inc dword ptr [rdi+10h]
0x14002bf94  lea     rsi, [rdi+0A0h]
0x14002bf9b  mov     rcx, rsi; SpinLock
0x14002bf9e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002bfa5  nop     dword ptr [rax+rax+00h]
0x14002bfaa  mov     [rdi+0A8h], al
0x14002bfb0  lea     rax, [rdi+30h]
0x14002bfb4  mov     rcx, [rax]
0x14002bfb7  cmp     [rcx+8], rax
0x14002bfbb  jz      short loc_14002BFC4
0x14002bfbd  mov     ecx, 3
0x14002bfc2  int     29h; Win8: RtlFailFast(ecx)
0x14002bfc4  mov     [rbx], rcx
0x14002bfc7  xor     r8d, r8d; State
0x14002bfca  mov     [rbx+8], rax
0x14002bfce  xor     edx, edx; Type
0x14002bfd0  mov     [rcx+8], rbx
0x14002bfd4  lea     rcx, [rbx+38h]; Event
0x14002bfd8  mov     [rax], rbx
0x14002bfdb  call    cs:__imp_KeInitializeEvent
0x14002bfe2  nop     dword ptr [rax+rax+00h]
0x14002bfe7  lock inc dword ptr [rdi+40h]
0x14002bfeb  mov     dl, [rdi+0A8h]; NewIrql
0x14002bff1  mov     rcx, rsi; SpinLock
0x14002bff4  call    cs:__imp_KeReleaseSpinLock
0x14002bffb  nop     dword ptr [rax+rax+00h]
0x14002c000  mov     rax, rbx
0x14002c003  mov     rbx, [rsp+28h+arg_0]
0x14002c008  mov     rsi, [rsp+28h+arg_8]
0x14002c00d  add     rsp, 20h
0x14002c011  pop     rdi
0x14002c012  retn
```
