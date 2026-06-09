# FveDcbIfcFilterCloseCleanup

- ea: `0x140085840`
- end: `0x140085abc`
- name: `FveDcbIfcFilterCloseCleanup`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008e44`
- `0x14000a150`
- `0x14000dedc`
- `0x14002d440`
- `0x140085840`
- `0x140086948`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140085a07`
- `ntoskrnl!IofCompleteRequest` at `0x140085a07`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140085909`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140085909`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140085939`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140085939`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400859c0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400859c0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400859d3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400859d3`

## pseudocode

```c
__int64 __fastcall FveDcbIfcFilterCloseCleanup(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // rbp
  __int64 v6; // r15
  unsigned int v7; // edi
  unsigned __int64 FsContext; // rax
  int v9; // r12d
  __int64 v10; // rbx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      55,
      WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
      CurrentStackLocation->FileObject);
  }
  if ( !a1 || (v6 = *(_QWORD *)(a1 + 200)) == 0 )
  {
    v7 = -1073741811;
    if ( a1 )
      goto LABEL_28;
    goto LABEL_27;
  }
  if ( *(_DWORD *)(a1 + 176) == 3 )
  {
    if ( *(_DWORD *)(v6 + 8) > 2u )
      goto LABEL_33;
    v7 = 0;
    if ( !FileObject )
      goto LABEL_28;
    FsContext = (unsigned __int64)FileObject->FsContext;
    if ( !FsContext )
      goto LABEL_28;
    if ( (FsContext & 0xFFFFFFFFFFFFFFFCuLL) != a1 )
    {
LABEL_33:
      v7 = -1073741811;
      goto LABEL_28;
    }
    v9 = (int)FileObject->FsContext;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 200LL);
    if ( v10 && IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 8), (PVOID)v10, File, 1u, 0x20u) >= 0 )
    {
      if ( *(_QWORD *)v10 )
        FveWrqCompleteRequestByFileObject(*(_QWORD *)v10, FileObject);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 8), (PVOID)v10, 0x20u);
    }
    if ( (v9 & 2) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_S(
          WPP_GLOBAL_Control->AttachedDevice,
          56,
          WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
          *(_QWORD *)(a1 + 152));
      }
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        57,
        WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
        *(_QWORD *)(a1 + 152));
    }
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
    *(_QWORD *)v6 = 0;
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
    FileObject->FsContext = 0;
    FileObject->FsContext2 = 0;
LABEL_27:
    BlDcbDeref(a1);
LABEL_28:
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
    goto LABEL_19;
  }
LABEL_18:
  v7 = -1073741822;
LABEL_19:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140085840  push    rbx
0x140085842  push    rbp
0x140085843  push    rsi
0x140085844  push    rdi
0x140085845  push    r12
0x140085847  push    r13
0x140085849  push    r14
0x14008584b  push    r15
0x14008584d  sub     rsp, 38h
0x140085851  mov     rax, [rdx+0B8h]
0x140085858  mov     r14, rdx
0x14008585b  mov     rsi, rcx
0x14008585e  mov     rbp, [rax+30h]
0x140085862  mov     rcx, cs:WPP_GLOBAL_Control
0x140085869  lea     rbx, WPP_GLOBAL_Control
0x140085870  mov     r13d, 400h
0x140085876  cmp     rcx, rbx
0x140085879  jz      short loc_140085885
0x14008587b  test    [rcx+2Ch], r13d
0x14008587f  jnz     loc_140085A3C
0x140085885  test    rsi, rsi
0x140085888  jz      loc_140085997
0x14008588e  mov     r15, [rsi+0C8h]
0x140085895  test    r15, r15
0x140085898  jz      loc_140085997
0x14008589e  cmp     dword ptr [rsi+0B0h], 3
0x1400858a5  jnz     loc_140085968
0x1400858ab  cmp     dword ptr [r15+8], 2
0x1400858b0  ja      loc_140085A63
0x1400858b6  xor     edi, edi
0x1400858b8  test    rbp, rbp
0x1400858bb  jz      loc_1400859F6
0x1400858c1  mov     rax, [rbp+18h]
0x1400858c5  test    rax, rax
0x1400858c8  jz      loc_1400859F6
0x1400858ce  and     rax, 0FFFFFFFFFFFFFFFCh
0x1400858d2  cmp     rax, rsi
0x1400858d5  jnz     loc_140085A63
0x1400858db  mov     rax, [rsi+8]
0x1400858df  mov     r12d, [rbp+18h]
0x1400858e3  mov     rbx, [rax+0C8h]
0x1400858ea  test    rbx, rbx
0x1400858ed  jz      short loc_140085945
0x1400858ef  lea     r9d, [rdi+1]; Line
0x1400858f3  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1400858fb  lea     r8, File; File
0x140085902  mov     rdx, rbx; Tag
0x140085905  lea     rcx, [rbx+8]; RemoveLock
0x140085909  call    cs:__imp_IoAcquireRemoveLockEx
0x140085910  nop     dword ptr [rax+rax+00h]
0x140085915  test    eax, eax
0x140085917  js      short loc_140085945
0x140085919  mov     rax, [rbx]
0x14008591c  test    rax, rax
0x14008591f  jz      short loc_14008592C
0x140085921  mov     rcx, [rbx]
0x140085924  mov     rdx, rbp
0x140085927  call    FveWrqCompleteRequestByFileObject
0x14008592c  mov     r8d, 20h ; ' '; RemlockSize
0x140085932  lea     rcx, [rbx+8]; RemoveLock
0x140085936  mov     rdx, rbx; Tag
0x140085939  call    cs:__imp_IoReleaseRemoveLockEx
0x140085940  nop     dword ptr [rax+rax+00h]
0x140085945  test    r12b, 2
0x140085949  jnz     short loc_1400859A3
0x14008594b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085952  lea     rbx, WPP_GLOBAL_Control
0x140085959  cmp     rcx, rbx
0x14008595c  jz      short loc_140085968
0x14008595e  test    [rcx+2Ch], r13d
0x140085962  jnz     loc_140085A6A
0x140085968  mov     edi, 0C0000002h
0x14008596d  mov     rcx, cs:WPP_GLOBAL_Control
0x140085974  cmp     rcx, rbx
0x140085977  jz      short loc_140085983
0x140085979  test    [rcx+2Ch], r13d
0x14008597d  jnz     loc_140085A95
0x140085983  mov     eax, edi
0x140085985  add     rsp, 38h
0x140085989  pop     r15
0x14008598b  pop     r14
0x14008598d  pop     r13
0x14008598f  pop     r12
0x140085991  pop     rdi
0x140085992  pop     rsi
0x140085993  pop     rbp
0x140085994  pop     rbx
0x140085995  retn
0x140085997  mov     edi, 0C000000Dh
0x14008599c  test    rsi, rsi
0x14008599f  jz      short loc_1400859EE
0x1400859a1  jmp     short loc_1400859F6
0x1400859a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400859aa  lea     rax, WPP_GLOBAL_Control
0x1400859b1  cmp     rcx, rax
0x1400859b4  jz      short loc_1400859BC
0x1400859b6  test    [rcx+2Ch], r13d
0x1400859ba  jnz     short loc_140085A18
0x1400859bc  lea     rcx, [rsi+50h]; Mutex
0x1400859c0  call    cs:__imp_KeAcquireGuardedMutex
0x1400859c7  nop     dword ptr [rax+rax+00h]
0x1400859cc  lea     rcx, [rsi+50h]; Mutex
0x1400859d0  mov     [r15], rdi
0x1400859d3  call    cs:__imp_KeReleaseGuardedMutex
0x1400859da  nop     dword ptr [rax+rax+00h]
0x1400859df  mov     [rbp+18h], rdi
0x1400859e3  lea     rbx, WPP_GLOBAL_Control
0x1400859ea  mov     [rbp+20h], rdi
0x1400859ee  mov     rcx, rsi
0x1400859f1  call    BlDcbDeref
0x1400859f6  xor     edx, edx; PriorityBoost
0x1400859f8  mov     qword ptr [r14+38h], 0
0x140085a00  mov     rcx, r14; Irp
0x140085a03  mov     [r14+30h], edi
0x140085a07  call    cs:__imp_IofCompleteRequest
0x140085a0e  nop     dword ptr [rax+rax+00h]
0x140085a13  jmp     loc_14008596D
0x140085a18  cmp     byte ptr [rcx+29h], 5
0x140085a1c  jb      short loc_1400859BC
0x140085a1e  mov     r9, [rsi+98h]
0x140085a25  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140085a2c  mov     rcx, [rcx+18h]
0x140085a30  mov     edx, 39h ; '9'
0x140085a35  call    WPP_SF_S
0x140085a3a  jmp     short loc_1400859BC
0x140085a3c  cmp     byte ptr [rcx+29h], 5
0x140085a40  jb      loc_140085885
0x140085a46  mov     rcx, [rcx+18h]
0x140085a4a  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140085a51  mov     edx, 37h ; '7'
0x140085a56  mov     r9, rbp
0x140085a59  call    WPP_SF_q
0x140085a5e  jmp     loc_140085885
0x140085a63  mov     edi, 0C000000Dh
0x140085a68  jmp     short loc_1400859F6
0x140085a6a  cmp     byte ptr [rcx+29h], 5
0x140085a6e  jb      loc_140085968
0x140085a74  mov     r9, [rsi+98h]
0x140085a7b  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140085a82  mov     rcx, [rcx+18h]
0x140085a86  mov     edx, 38h ; '8'
0x140085a8b  call    WPP_SF_S
0x140085a90  jmp     loc_140085968
0x140085a95  cmp     byte ptr [rcx+29h], 5
0x140085a99  jb      loc_140085983
0x140085a9f  mov     rcx, [rcx+18h]
0x140085aa3  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140085aaa  mov     edx, 3Ah ; ':'
0x140085aaf  mov     r9d, edi
0x140085ab2  call    WPP_SF_d
0x140085ab7  jmp     loc_140085983
```
