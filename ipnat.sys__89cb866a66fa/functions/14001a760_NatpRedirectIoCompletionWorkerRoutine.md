# NatpRedirectIoCompletionWorkerRoutine

- ea: `0x14001a760`
- end: `0x14001a991`
- name: `NatpRedirectIoCompletionWorkerRoutine`
- size: `561`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x14001a760`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14001a7fb`
- `ntoskrnl!IoFreeWorkItem` at `0x14001a933`
- `ntoskrnl!IoFreeWorkItem` at `0x14001a7fb`
- `ntoskrnl!IoFreeWorkItem` at `0x14001a933`
- `ntoskrnl!IoSetIoCompletion` at `0x14001a8f6`
- `ntoskrnl!IoSetIoCompletion` at `0x14001a8f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a813`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a8c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a944`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a813`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a8c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a944`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a7ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a905`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a7ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a905`

## pseudocode

```c
void __fastcall NatpRedirectIoCompletionWorkerRoutine(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  KIRQL v3; // bl
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbp
  _QWORD *v10; // rdi
  int v11; // [rsp+28h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  v3 = KeAcquireSpinLockRaiseToDpc(&RedirectCompletionLock);
  if ( RedirectIoWorkItem )
  {
    while ( 1 )
    {
      v6 = RedirectCompletionList;
      if ( (__int64 *)RedirectCompletionList == &RedirectCompletionList )
        break;
      if ( *(__int64 **)(RedirectCompletionList + 8) != &RedirectCompletionList
        || (v7 = *(_QWORD *)RedirectCompletionList,
            *(_QWORD *)(*(_QWORD *)RedirectCompletionList + 8LL) != RedirectCompletionList) )
      {
        __fastfail(3u);
      }
      RedirectCompletionList = *(_QWORD *)RedirectCompletionList;
      *(_QWORD *)(v7 + 8) = &RedirectCompletionList;
      *(_QWORD *)(v6 + 8) = v6;
      *(_QWORD *)v6 = v6;
      v8 = *(_QWORD *)(v6 + 112);
      if ( v8 && (*(_DWORD *)(v6 + 96) & 0x40000020) == 0x40000020 )
      {
        v9 = *(_QWORD *)(v8 + 96);
        v10 = *(_QWORD **)(*(_QWORD *)(v6 + 120) + 176LL);
        *(_DWORD *)(v6 + 96) &= ~0x40000000u;
        KeReleaseSpinLock(&RedirectCompletionLock, v3);
        if ( v10 )
        {
          LOBYTE(v11) = 0;
          IoSetIoCompletion(*v10, v10[1], v9, 259, 0, v11);
        }
        v3 = KeAcquireSpinLockRaiseToDpc(&RedirectCompletionLock);
      }
    }
    RedirectIoCompletionPending = 0;
    if ( !RedirectIoWorkItem )
      IoFreeWorkItem(Context);
    KeReleaseSpinLock(&RedirectCompletionLock, v3);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v5 = 109;
      goto LABEL_29;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
    }
    IoFreeWorkItem(Context);
    RedirectIoCompletionPending = 0;
    KeReleaseSpinLock(&RedirectCompletionLock, v3);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v5 = 108;
LABEL_29:
      WPP_SF_(v4->AttachedDevice, v5, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14001a760  push    rbx
0x14001a762  push    rbp
0x14001a763  push    rsi
0x14001a764  push    rdi
0x14001a765  push    r13
0x14001a767  sub     rsp, 30h
0x14001a76b  mov     rsi, rdx
0x14001a76e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a775  lea     rdi, WPP_GLOBAL_Control
0x14001a77c  cmp     rcx, rdi
0x14001a77f  jz      short loc_14001A7A3
0x14001a781  mov     eax, [rcx+2Ch]
0x14001a784  test    al, 1
0x14001a786  jz      short loc_14001A7A3
0x14001a788  cmp     byte ptr [rcx+29h], 6
0x14001a78c  jb      short loc_14001A7A3
0x14001a78e  mov     rcx, [rcx+18h]
0x14001a792  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a799  mov     edx, 6Ah ; 'j'
0x14001a79e  call    WPP_SF_
0x14001a7a3  lea     r13, RedirectCompletionLock
0x14001a7aa  mov     rcx, r13; SpinLock
0x14001a7ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a7b4  nop     dword ptr [rax+rax+00h]
0x14001a7b9  cmp     cs:RedirectIoWorkItem, 0
0x14001a7c1  mov     bl, al
0x14001a7c3  jnz     loc_14001A84E
0x14001a7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7d0  cmp     rcx, rdi
0x14001a7d3  jz      short loc_14001A7F8
0x14001a7d5  mov     edx, [rcx+2Ch]
0x14001a7d8  test    dl, 1
0x14001a7db  jz      short loc_14001A7F8
0x14001a7dd  cmp     byte ptr [rcx+29h], 2
0x14001a7e1  jb      short loc_14001A7F8
0x14001a7e3  mov     rcx, [rcx+18h]
0x14001a7e7  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a7ee  mov     edx, 6Bh ; 'k'
0x14001a7f3  call    WPP_SF_
0x14001a7f8  mov     rcx, rsi; IoWorkItem
0x14001a7fb  call    cs:__imp_IoFreeWorkItem
0x14001a802  nop     dword ptr [rax+rax+00h]
0x14001a807  mov     dl, bl; NewIrql
0x14001a809  mov     cs:RedirectIoCompletionPending, 0
0x14001a810  mov     rcx, r13; SpinLock
0x14001a813  call    cs:__imp_KeReleaseSpinLock
0x14001a81a  nop     dword ptr [rax+rax+00h]
0x14001a81f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a826  cmp     rcx, rdi
0x14001a829  jz      loc_14001A985
0x14001a82f  mov     eax, [rcx+2Ch]
0x14001a832  test    al, 1
0x14001a834  jz      loc_14001A985
0x14001a83a  cmp     byte ptr [rcx+29h], 6
0x14001a83e  jb      loc_14001A985
0x14001a844  mov     edx, 6Ch ; 'l'
0x14001a849  jmp     loc_14001A975
0x14001a84e  lea     r8, RedirectCompletionList
0x14001a855  mov     rdx, cs:RedirectCompletionList
0x14001a85c  cmp     rdx, r8
0x14001a85f  jz      loc_14001A91F
0x14001a865  cmp     [rdx+8], r8
0x14001a869  jnz     loc_14001A918
0x14001a86f  mov     rax, [rdx]
0x14001a872  cmp     [rax+8], rdx
0x14001a876  jnz     loc_14001A918
0x14001a87c  mov     cs:RedirectCompletionList, rax
0x14001a883  mov     [rax+8], r8
0x14001a887  mov     [rdx+8], rdx
0x14001a88b  mov     [rdx], rdx
0x14001a88e  mov     rcx, [rdx+70h]
0x14001a892  test    rcx, rcx
0x14001a895  jz      short loc_14001A855
0x14001a897  mov     r9d, [rdx+60h]
0x14001a89b  mov     eax, r9d
0x14001a89e  and     eax, 40000020h
0x14001a8a3  cmp     eax, 40000020h
0x14001a8a8  jnz     short loc_14001A855
0x14001a8aa  mov     rax, [rdx+78h]
0x14001a8ae  btr     r9d, 1Eh
0x14001a8b3  mov     rbp, [rcx+60h]
0x14001a8b7  mov     rcx, r13; SpinLock
0x14001a8ba  mov     rdi, [rax+0B0h]
0x14001a8c1  mov     [rdx+60h], r9d
0x14001a8c5  mov     dl, bl; NewIrql
0x14001a8c7  call    cs:__imp_KeReleaseSpinLock
0x14001a8ce  nop     dword ptr [rax+rax+00h]
0x14001a8d3  test    rdi, rdi
0x14001a8d6  jz      short loc_14001A902
0x14001a8d8  mov     rdx, [rdi+8]
0x14001a8dc  mov     r9d, 103h
0x14001a8e2  mov     rcx, [rdi]
0x14001a8e5  mov     r8, rbp
0x14001a8e8  mov     byte ptr [rsp+58h+var_30], 0
0x14001a8ed  mov     [rsp+58h+var_38], 0
0x14001a8f6  call    cs:__imp_IoSetIoCompletion
0x14001a8fd  nop     dword ptr [rax+rax+00h]
0x14001a902  mov     rcx, r13; SpinLock
0x14001a905  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a90c  nop     dword ptr [rax+rax+00h]
0x14001a911  mov     bl, al
0x14001a913  jmp     loc_14001A84E
0x14001a918  mov     ecx, 3
0x14001a91d  int     29h; Win8: RtlFailFast(ecx)
0x14001a91f  cmp     cs:RedirectIoWorkItem, 0
0x14001a927  mov     cs:RedirectIoCompletionPending, 0
0x14001a92e  jnz     short loc_14001A93F
0x14001a930  mov     rcx, rsi; IoWorkItem
0x14001a933  call    cs:__imp_IoFreeWorkItem
0x14001a93a  nop     dword ptr [rax+rax+00h]
0x14001a93f  mov     dl, bl; NewIrql
0x14001a941  mov     rcx, r13; SpinLock
0x14001a944  call    cs:__imp_KeReleaseSpinLock
0x14001a94b  nop     dword ptr [rax+rax+00h]
0x14001a950  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a957  lea     rax, WPP_GLOBAL_Control
0x14001a95e  cmp     rcx, rax
0x14001a961  jz      short loc_14001A985
0x14001a963  mov     eax, [rcx+2Ch]
0x14001a966  test    al, 1
0x14001a968  jz      short loc_14001A985
0x14001a96a  cmp     byte ptr [rcx+29h], 6
0x14001a96e  jb      short loc_14001A985
0x14001a970  mov     edx, 6Dh ; 'm'
0x14001a975  mov     rcx, [rcx+18h]
0x14001a979  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a980  call    WPP_SF_
0x14001a985  add     rsp, 30h
0x14001a989  pop     r13
0x14001a98b  pop     rdi
0x14001a98c  pop     rsi
0x14001a98d  pop     rbp
0x14001a98e  pop     rbx
0x14001a98f  retn
```
