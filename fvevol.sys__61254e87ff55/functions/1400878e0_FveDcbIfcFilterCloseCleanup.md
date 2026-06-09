# FveDcbIfcFilterCloseCleanup

- ea: `0x1400878e0`
- end: `0x140087b5c`
- name: `FveDcbIfcFilterCloseCleanup`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008f04`
- `0x14000a210`
- `0x14000e0c4`
- `0x14002e440`
- `0x1400878e0`
- `0x1400889e8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140087aa7`
- `ntoskrnl!IofCompleteRequest` at `0x140087aa7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400879a9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400879a9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400879d9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400879d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140087a60`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140087a60`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140087a73`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140087a73`

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
0x1400878e0  push    rbx
0x1400878e2  push    rbp
0x1400878e3  push    rsi
0x1400878e4  push    rdi
0x1400878e5  push    r12
0x1400878e7  push    r13
0x1400878e9  push    r14
0x1400878eb  push    r15
0x1400878ed  sub     rsp, 38h
0x1400878f1  mov     rax, [rdx+0B8h]
0x1400878f8  mov     r14, rdx
0x1400878fb  mov     rsi, rcx
0x1400878fe  mov     rbp, [rax+30h]
0x140087902  mov     rcx, cs:WPP_GLOBAL_Control
0x140087909  lea     rbx, WPP_GLOBAL_Control
0x140087910  mov     r13d, 400h
0x140087916  cmp     rcx, rbx
0x140087919  jz      short loc_140087925
0x14008791b  test    [rcx+2Ch], r13d
0x14008791f  jnz     loc_140087ADC
0x140087925  test    rsi, rsi
0x140087928  jz      loc_140087A37
0x14008792e  mov     r15, [rsi+0C8h]
0x140087935  test    r15, r15
0x140087938  jz      loc_140087A37
0x14008793e  cmp     dword ptr [rsi+0B0h], 3
0x140087945  jnz     loc_140087A08
0x14008794b  cmp     dword ptr [r15+8], 2
0x140087950  ja      loc_140087B03
0x140087956  xor     edi, edi
0x140087958  test    rbp, rbp
0x14008795b  jz      loc_140087A96
0x140087961  mov     rax, [rbp+18h]
0x140087965  test    rax, rax
0x140087968  jz      loc_140087A96
0x14008796e  and     rax, 0FFFFFFFFFFFFFFFCh
0x140087972  cmp     rax, rsi
0x140087975  jnz     loc_140087B03
0x14008797b  mov     rax, [rsi+8]
0x14008797f  mov     r12d, [rbp+18h]
0x140087983  mov     rbx, [rax+0C8h]
0x14008798a  test    rbx, rbx
0x14008798d  jz      short loc_1400879E5
0x14008798f  lea     r9d, [rdi+1]; Line
0x140087993  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14008799b  lea     r8, File; File
0x1400879a2  mov     rdx, rbx; Tag
0x1400879a5  lea     rcx, [rbx+8]; RemoveLock
0x1400879a9  call    cs:__imp_IoAcquireRemoveLockEx
0x1400879b0  nop     dword ptr [rax+rax+00h]
0x1400879b5  test    eax, eax
0x1400879b7  js      short loc_1400879E5
0x1400879b9  mov     rax, [rbx]
0x1400879bc  test    rax, rax
0x1400879bf  jz      short loc_1400879CC
0x1400879c1  mov     rcx, [rbx]
0x1400879c4  mov     rdx, rbp
0x1400879c7  call    FveWrqCompleteRequestByFileObject
0x1400879cc  mov     r8d, 20h ; ' '; RemlockSize
0x1400879d2  lea     rcx, [rbx+8]; RemoveLock
0x1400879d6  mov     rdx, rbx; Tag
0x1400879d9  call    cs:__imp_IoReleaseRemoveLockEx
0x1400879e0  nop     dword ptr [rax+rax+00h]
0x1400879e5  test    r12b, 2
0x1400879e9  jnz     short loc_140087A43
0x1400879eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400879f2  lea     rbx, WPP_GLOBAL_Control
0x1400879f9  cmp     rcx, rbx
0x1400879fc  jz      short loc_140087A08
0x1400879fe  test    [rcx+2Ch], r13d
0x140087a02  jnz     loc_140087B0A
0x140087a08  mov     edi, 0C0000002h
0x140087a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140087a14  cmp     rcx, rbx
0x140087a17  jz      short loc_140087A23
0x140087a19  test    [rcx+2Ch], r13d
0x140087a1d  jnz     loc_140087B35
0x140087a23  mov     eax, edi
0x140087a25  add     rsp, 38h
0x140087a29  pop     r15
0x140087a2b  pop     r14
0x140087a2d  pop     r13
0x140087a2f  pop     r12
0x140087a31  pop     rdi
0x140087a32  pop     rsi
0x140087a33  pop     rbp
0x140087a34  pop     rbx
0x140087a35  retn
0x140087a37  mov     edi, 0C000000Dh
0x140087a3c  test    rsi, rsi
0x140087a3f  jz      short loc_140087A8E
0x140087a41  jmp     short loc_140087A96
0x140087a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140087a4a  lea     rax, WPP_GLOBAL_Control
0x140087a51  cmp     rcx, rax
0x140087a54  jz      short loc_140087A5C
0x140087a56  test    [rcx+2Ch], r13d
0x140087a5a  jnz     short loc_140087AB8
0x140087a5c  lea     rcx, [rsi+50h]; Mutex
0x140087a60  call    cs:__imp_KeAcquireGuardedMutex
0x140087a67  nop     dword ptr [rax+rax+00h]
0x140087a6c  lea     rcx, [rsi+50h]; Mutex
0x140087a70  mov     [r15], rdi
0x140087a73  call    cs:__imp_KeReleaseGuardedMutex
0x140087a7a  nop     dword ptr [rax+rax+00h]
0x140087a7f  mov     [rbp+18h], rdi
0x140087a83  lea     rbx, WPP_GLOBAL_Control
0x140087a8a  mov     [rbp+20h], rdi
0x140087a8e  mov     rcx, rsi
0x140087a91  call    BlDcbDeref
0x140087a96  xor     edx, edx; PriorityBoost
0x140087a98  mov     qword ptr [r14+38h], 0
0x140087aa0  mov     rcx, r14; Irp
0x140087aa3  mov     [r14+30h], edi
0x140087aa7  call    cs:__imp_IofCompleteRequest
0x140087aae  nop     dword ptr [rax+rax+00h]
0x140087ab3  jmp     loc_140087A0D
0x140087ab8  cmp     byte ptr [rcx+29h], 5
0x140087abc  jb      short loc_140087A5C
0x140087abe  mov     r9, [rsi+98h]
0x140087ac5  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087acc  mov     rcx, [rcx+18h]
0x140087ad0  mov     edx, 39h ; '9'
0x140087ad5  call    WPP_SF_S
0x140087ada  jmp     short loc_140087A5C
0x140087adc  cmp     byte ptr [rcx+29h], 5
0x140087ae0  jb      loc_140087925
0x140087ae6  mov     rcx, [rcx+18h]
0x140087aea  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087af1  mov     edx, 37h ; '7'
0x140087af6  mov     r9, rbp
0x140087af9  call    WPP_SF_q
0x140087afe  jmp     loc_140087925
0x140087b03  mov     edi, 0C000000Dh
0x140087b08  jmp     short loc_140087A96
0x140087b0a  cmp     byte ptr [rcx+29h], 5
0x140087b0e  jb      loc_140087A08
0x140087b14  mov     r9, [rsi+98h]
0x140087b1b  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087b22  mov     rcx, [rcx+18h]
0x140087b26  mov     edx, 38h ; '8'
0x140087b2b  call    WPP_SF_S
0x140087b30  jmp     loc_140087A08
0x140087b35  cmp     byte ptr [rcx+29h], 5
0x140087b39  jb      loc_140087A23
0x140087b3f  mov     rcx, [rcx+18h]
0x140087b43  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087b4a  mov     edx, 3Ah ; ':'
0x140087b4f  mov     r9d, edi
0x140087b52  call    WPP_SF_d
0x140087b57  jmp     loc_140087A23
```
