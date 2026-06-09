# WinsDgramCompletion

- ea: `0x140052100`
- end: `0x1400522de`
- name: `WinsDgramCompletion`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140006900`
- `0x140007be8`
- `0x14000b810`
- `0x14000dc40`
- `0x1400304c8`
- `0x140040294`
- `0x140052100`
- `0x1400522e4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005227a`
- `ntoskrnl!IofCompleteRequest` at `0x14005227a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052118`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052289`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052118`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052289`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400521e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052252`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400522b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400521e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052252`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400522b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400522a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400522a7`

## pseudocode

```c
__int64 __fastcall WinsDgramCompletion(__int64 a1)
{
  KIRQL v2; // si
  __int64 v3; // r8
  struct _DEVICE_OBJECT *v4; // rbp
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rcx

  v2 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( !pWinsInfo || *(_QWORD *)(a1 + 176) != *(_DWORD *)(pWinsInfo + 88) )
  {
    ExFreePoolWithTag(*(PVOID *)(a1 + 64), 0);
    goto LABEL_17;
  }
  WinsFreeMem(pWinsInfo, *(_QWORD *)(a1 + 64), *(unsigned int *)(a1 + 136), 0);
  if ( *(_QWORD *)(pWinsInfo + 40) == pWinsInfo + 40 )
  {
LABEL_17:
    KeReleaseSpinLock(&SpinLock, v2);
    return FreeTracker(a1, 4);
  }
  v4 = *(struct _DEVICE_OBJECT **)(pWinsInfo + 56);
  if ( !v4 || (LOBYTE(v3) = 1, !(unsigned __int8)NBT_REFERENCE_DEVICE(v4, 12, v3)) )
  {
    while ( 1 )
    {
      v8 = (_QWORD *)(pWinsInfo + 40);
      v9 = *(_QWORD **)(pWinsInfo + 40);
      if ( v9 == (_QWORD *)(pWinsInfo + 40) )
        goto LABEL_17;
      if ( (_QWORD *)v9[1] != v8 )
        goto LABEL_15;
      v10 = *v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 )
        goto LABEL_15;
      *v8 = v10;
      *(_QWORD *)(v10 + 8) = v8;
      KeReleaseSpinLock(&SpinLock, v2);
      NbtCancelCancelRoutine(v9 - 21);
      *((_DWORD *)v9 - 30) = -1073741218;
      IofCompleteRequest((PIRP)(v9 - 21), 2);
      v2 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    }
  }
  if ( (BYTE2(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1040, 25, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids);
  v5 = (_QWORD *)(pWinsInfo + 40);
  v6 = *(_QWORD **)(pWinsInfo + 40);
  if ( v6[1] != pWinsInfo + 40 || (v7 = *v6, *(_QWORD **)(*v6 + 8LL) != v6) )
LABEL_15:
    __fastfail(3u);
  *v5 = v7;
  *(_QWORD *)(v7 + 8) = v5;
  KeReleaseSpinLock(&SpinLock, v2);
  NbtCancelCancelRoutine(v6 - 21);
  WinsSendDatagram(v4, (IRP *)(v6 - 21), 1);
  NBT_DEREFERENCE_DEVICE(v4, 12);
  return FreeTracker(a1, 4);
}

```

## disassembly

```asm
0x140052100  push    rbx
0x140052102  push    rbp
0x140052103  push    rsi
0x140052104  push    rdi
0x140052105  push    r14
0x140052107  sub     rsp, 20h
0x14005210b  mov     rdi, rcx
0x14005210e  lea     r14, SpinLock
0x140052115  mov     rcx, r14; SpinLock
0x140052118  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005211f  nop     dword ptr [rax+rax+00h]
0x140052124  mov     rcx, cs:pWinsInfo
0x14005212b  mov     sil, al
0x14005212e  test    rcx, rcx
0x140052131  jz      loc_1400522A1
0x140052137  movsxd  rdx, dword ptr [rcx+58h]
0x14005213b  cmp     [rdi+0B0h], rdx
0x140052142  jnz     loc_1400522A1
0x140052148  mov     r8d, [rdi+88h]
0x14005214f  xor     r9d, r9d
0x140052152  mov     rdx, [rdi+40h]
0x140052156  call    WinsFreeMem
0x14005215b  mov     rbp, cs:pWinsInfo
0x140052162  lea     rax, [rbp+28h]
0x140052166  cmp     [rax], rax
0x140052169  jz      loc_1400522B3
0x14005216f  mov     rbp, [rbp+38h]
0x140052173  test    rbp, rbp
0x140052176  jz      loc_140052223
0x14005217c  mov     r8b, 1
0x14005217f  mov     edx, 0Ch
0x140052184  mov     rcx, rbp
0x140052187  call    NBT_REFERENCE_DEVICE
0x14005218c  test    al, al
0x14005218e  jz      loc_140052223
0x140052194  test    byte ptr cs:xmmword_140038420+2, 1
0x14005219b  jz      short loc_1400521B3
0x14005219d  mov     edx, 19h
0x1400521a2  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400521a9  mov     ecx, 410h
0x1400521ae  call    WPP_SF_
0x1400521b3  mov     rax, cs:pWinsInfo
0x1400521ba  add     rax, 28h ; '('
0x1400521be  mov     rbx, [rax]
0x1400521c1  cmp     [rbx+8], rax
0x1400521c5  jnz     loc_14005229A
0x1400521cb  mov     rcx, [rbx]
0x1400521ce  cmp     [rcx+8], rbx
0x1400521d2  jnz     loc_14005229A
0x1400521d8  mov     [rax], rcx
0x1400521db  mov     dl, sil; NewIrql
0x1400521de  mov     [rcx+8], rax
0x1400521e2  mov     rcx, r14; SpinLock
0x1400521e5  call    cs:__imp_KeReleaseSpinLock
0x1400521ec  nop     dword ptr [rax+rax+00h]
0x1400521f1  lea     rcx, [rbx-0A8h]
0x1400521f8  call    NbtCancelCancelRoutine
0x1400521fd  mov     r8b, 1
0x140052200  lea     rdx, [rbx-0A8h]
0x140052207  mov     rcx, rbp
0x14005220a  call    WinsSendDatagram
0x14005220f  xor     r8d, r8d
0x140052212  mov     rcx, rbp
0x140052215  lea     edx, [r8+0Ch]
0x140052219  call    NBT_DEREFERENCE_DEVICE
0x14005221e  jmp     loc_1400522C5
0x140052223  mov     rax, cs:pWinsInfo
0x14005222a  add     rax, 28h ; '('
0x14005222e  mov     rbx, [rax]
0x140052231  cmp     rbx, rax
0x140052234  jz      short loc_1400522B3
0x140052236  cmp     [rbx+8], rax
0x14005223a  jnz     short loc_14005229A
0x14005223c  mov     rcx, [rbx]
0x14005223f  cmp     [rcx+8], rbx
0x140052243  jnz     short loc_14005229A
0x140052245  mov     [rax], rcx
0x140052248  mov     dl, sil; NewIrql
0x14005224b  mov     [rcx+8], rax
0x14005224f  mov     rcx, r14; SpinLock
0x140052252  call    cs:__imp_KeReleaseSpinLock
0x140052259  nop     dword ptr [rax+rax+00h]
0x14005225e  lea     rcx, [rbx-0A8h]
0x140052265  call    NbtCancelCancelRoutine
0x14005226a  mov     dl, 2; PriorityBoost
0x14005226c  mov     dword ptr [rbx-78h], 0C000025Eh
0x140052273  lea     rcx, [rbx-0A8h]; Irp
0x14005227a  call    cs:__imp_IofCompleteRequest
0x140052281  nop     dword ptr [rax+rax+00h]
0x140052286  mov     rcx, r14; SpinLock
0x140052289  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140052290  nop     dword ptr [rax+rax+00h]
0x140052295  mov     sil, al
0x140052298  jmp     short loc_140052223
0x14005229a  mov     ecx, 3
0x14005229f  int     29h; Win8: RtlFailFast(ecx)
0x1400522a1  mov     rcx, [rdi+40h]; P
0x1400522a5  xor     edx, edx; Tag
0x1400522a7  call    cs:__imp_ExFreePoolWithTag
0x1400522ae  nop     dword ptr [rax+rax+00h]
0x1400522b3  mov     dl, sil; NewIrql
0x1400522b6  mov     rcx, r14; SpinLock
0x1400522b9  call    cs:__imp_KeReleaseSpinLock
0x1400522c0  nop     dword ptr [rax+rax+00h]
0x1400522c5  mov     edx, 4
0x1400522ca  mov     rcx, rdi
0x1400522cd  call    FreeTracker
0x1400522d2  add     rsp, 20h
0x1400522d6  pop     r14
0x1400522d8  pop     rdi
0x1400522d9  pop     rsi
0x1400522da  pop     rbp
0x1400522db  pop     rbx
0x1400522dc  retn
```
