# RcvIrpFromWins

- ea: `0x14003027c`
- end: `0x1400304c0`
- name: `RcvIrpFromWins`
- size: `580`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400527ac`

## callees

- `0x140004880`
- `0x14000dccc`
- `0x14003027c`
- `0x140031140`
- `0x140040214`
- `0x140040428`
- `0x140052480`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030363`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030363`
- `ntoskrnl!IofCompleteRequest` at `0x140030409`
- `ntoskrnl!IofCompleteRequest` at `0x140030409`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400302a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400302db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400302a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400302db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400302c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400303c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030478`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030490`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400302c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400303c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030478`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400303b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400303b2`

## pseudocode

```c
__int64 __fastcall RcvIrpFromWins(PIRP Irp)
{
  _QWORD *FsContext; // rsi
  KIRQL v3; // al
  ULONG v4; // r15d
  KIRQL v5; // bp
  _QWORD *v6; // rax
  char *v7; // r14
  _QWORD *v8; // rcx
  PMDL MdlAddress; // rbx
  PVOID MappedSystemVa; // rax
  ULONG ByteCount; // edx
  ULONG v12; // ebx
  ULONG v13; // ecx
  NTSTATUS v14; // ebx
  int v15; // eax

  FsContext = Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  v3 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v4 = 0;
  v5 = v3;
  if ( !RefreshedYet )
  {
    KeReleaseSpinLock(&SpinLock, v3);
    InitiateRefresh();
    v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    RefreshedYet = 1;
  }
  if ( !FsContext || FsContext != (_QWORD *)pWinsInfo )
  {
    KeReleaseSpinLock(&SpinLock, v5);
    v14 = -1073741816;
    goto LABEL_30;
  }
  v6 = FsContext + 3;
  v7 = (char *)FsContext[3];
  if ( v7 != (char *)(FsContext + 3) )
  {
    if ( *((_QWORD **)v7 + 1) != v6 || (v8 = *(_QWORD **)v7, *(char **)(*(_QWORD *)v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress
      && ((MdlAddress->MdlFlags & 5) == 0
        ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u))
        : (MappedSystemVa = MdlAddress->MappedSystemVa),
          MappedSystemVa) )
    {
      ByteCount = MdlAddress->ByteCount;
      v12 = *((_DWORD *)v7 + 4);
      v13 = v12;
      if ( v12 > ByteCount )
        v13 = ByteCount;
      v4 = v13;
      memmove(MappedSystemVa, v7 + 20, v13);
      v14 = v4 < v12 ? 0x80000005 : 0;
    }
    else
    {
      v14 = -1073741823;
    }
    *((_DWORD *)FsContext + 18) -= *((_DWORD *)v7 + 4);
    ExFreePoolWithTag(v7, 0);
    KeReleaseSpinLock(&SpinLock, v5);
    if ( (BYTE2(xmmword_140038420) & 1) != 0 )
      WPP_SF_dq(1040, 16, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, 3221225480LL, Irp);
    Irp->IoStatus.Information = v4;
    Irp->IoStatus.Status = v14;
    IofCompleteRequest(Irp, 0);
    return (unsigned int)v14;
  }
  if ( FsContext[8] )
  {
    v14 = -1073741637;
  }
  else
  {
    v15 = NTCheckSetCancelRoutine(Irp, &NbtCancelWinsIrp);
    v14 = v15;
    if ( v15 >= 0 )
    {
      if ( (BYTE2(xmmword_140038420) & 1) != 0 )
        WPP_SF_qD(1040, 17, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, Irp, v15);
      FsContext[8] = Irp;
      v14 = 259;
    }
  }
  KeReleaseSpinLock(&SpinLock, v5);
  if ( v14 < 0 )
LABEL_30:
    NTIoComplete(Irp);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003027c  push    rbx
0x14003027e  push    rbp
0x14003027f  push    rsi
0x140030280  push    rdi
0x140030281  push    r12
0x140030283  push    r14
0x140030285  push    r15
0x140030287  sub     rsp, 30h
0x14003028b  mov     rax, [rcx+0B8h]
0x140030292  lea     r12, SpinLock
0x140030299  mov     rdi, rcx
0x14003029c  mov     rcx, r12; SpinLock
0x14003029f  mov     rdx, [rax+30h]
0x1400302a3  mov     rsi, [rdx+18h]
0x1400302a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400302ae  nop     dword ptr [rax+rax+00h]
0x1400302b3  xor     r15d, r15d
0x1400302b6  mov     bpl, al
0x1400302b9  cmp     cs:RefreshedYet, r15b
0x1400302c0  jnz     short loc_1400302F1
0x1400302c2  mov     dl, al; NewIrql
0x1400302c4  mov     rcx, r12; SpinLock
0x1400302c7  call    cs:__imp_KeReleaseSpinLock
0x1400302ce  nop     dword ptr [rax+rax+00h]
0x1400302d3  call    InitiateRefresh
0x1400302d8  mov     rcx, r12; SpinLock
0x1400302db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400302e2  nop     dword ptr [rax+rax+00h]
0x1400302e7  mov     bpl, al
0x1400302ea  mov     cs:RefreshedYet, 1
0x1400302f1  test    rsi, rsi
0x1400302f4  jz      loc_14003048A
0x1400302fa  cmp     rsi, cs:pWinsInfo
0x140030301  jnz     loc_14003048A
0x140030307  lea     rax, [rsi+18h]
0x14003030b  mov     r14, [rax]
0x14003030e  cmp     r14, rax
0x140030311  jz      loc_140030421
0x140030317  cmp     [r14+8], rax
0x14003031b  jnz     loc_14003041A
0x140030321  mov     rcx, [r14]
0x140030324  cmp     [rcx+8], r14
0x140030328  jnz     loc_14003041A
0x14003032e  mov     [rax], rcx
0x140030331  mov     [rcx+8], rax
0x140030335  mov     rbx, [rdi+8]
0x140030339  test    rbx, rbx
0x14003033c  jz      short loc_1400303A1
0x14003033e  test    byte ptr [rbx+0Ah], 5
0x140030342  jz      short loc_14003034A
0x140030344  mov     rax, [rbx+18h]
0x140030348  jmp     short loc_14003036F
0x14003034a  xor     r9d, r9d; RequestedAddress
0x14003034d  mov     [rsp+68h+Priority], 40000020h; Priority
0x140030355  xor     edx, edx; AccessMode
0x140030357  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14003035c  mov     rcx, rbx; MemoryDescriptorList
0x14003035f  lea     r8d, [r9+1]; CacheType
0x140030363  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003036a  nop     dword ptr [rax+rax+00h]
0x14003036f  test    rax, rax
0x140030372  jz      short loc_1400303A1
0x140030374  mov     edx, [rbx+28h]
0x140030377  mov     ebx, [r14+10h]
0x14003037b  cmp     ebx, edx
0x14003037d  mov     ecx, ebx
0x14003037f  cmova   ecx, edx
0x140030382  lea     rdx, [r14+14h]; Src
0x140030386  mov     r15d, ecx
0x140030389  mov     r8d, ecx; Size
0x14003038c  mov     rcx, rax; void *
0x14003038f  call    memmove
0x140030394  cmp     r15d, ebx
0x140030397  sbb     ebx, ebx
0x140030399  and     ebx, 80000005h
0x14003039f  jmp     short loc_1400303A6
0x1400303a1  mov     ebx, 0C0000001h
0x1400303a6  mov     eax, [r14+10h]
0x1400303aa  xor     edx, edx; Tag
0x1400303ac  sub     [rsi+48h], eax
0x1400303af  mov     rcx, r14; P
0x1400303b2  call    cs:__imp_ExFreePoolWithTag
0x1400303b9  nop     dword ptr [rax+rax+00h]
0x1400303be  mov     dl, bpl; NewIrql
0x1400303c1  mov     rcx, r12; SpinLock
0x1400303c4  call    cs:__imp_KeReleaseSpinLock
0x1400303cb  nop     dword ptr [rax+rax+00h]
0x1400303d0  test    byte ptr cs:xmmword_140038420+2, 1
0x1400303d7  jz      short loc_1400303FA
0x1400303d9  mov     edx, 10h
0x1400303de  mov     qword ptr [rsp+68h+BugCheckOnFailure], rdi
0x1400303e3  mov     ecx, 410h
0x1400303e8  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400303ef  mov     r9d, 0C0000008h
0x1400303f5  call    WPP_SF_dq
0x1400303fa  mov     ecx, r15d
0x1400303fd  xor     edx, edx; PriorityBoost
0x1400303ff  mov     [rdi+38h], rcx
0x140030403  mov     rcx, rdi; Irp
0x140030406  mov     [rdi+30h], ebx
0x140030409  call    cs:__imp_IofCompleteRequest
0x140030410  nop     dword ptr [rax+rax+00h]
0x140030415  jmp     loc_1400304AE
0x14003041a  mov     ecx, 3
0x14003041f  int     29h; Win8: RtlFailFast(ecx)
0x140030421  cmp     [rsi+40h], r15
0x140030425  jz      short loc_14003042E
0x140030427  mov     ebx, 0C00000BBh
0x14003042c  jmp     short loc_140030472
0x14003042e  lea     rdx, NbtCancelWinsIrp
0x140030435  mov     rcx, rdi
0x140030438  call    NTCheckSetCancelRoutine
0x14003043d  mov     ebx, eax
0x14003043f  test    eax, eax
0x140030441  js      short loc_140030472
0x140030443  test    byte ptr cs:xmmword_140038420+2, 1
0x14003044a  jz      short loc_140030469
0x14003044c  mov     edx, 11h
0x140030451  mov     [rsp+68h+BugCheckOnFailure], eax
0x140030455  mov     ecx, 410h
0x14003045a  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x140030461  mov     r9, rdi
0x140030464  call    WPP_SF_qD
0x140030469  mov     [rsi+40h], rdi
0x14003046d  mov     ebx, 103h
0x140030472  mov     dl, bpl; NewIrql
0x140030475  mov     rcx, r12; SpinLock
0x140030478  call    cs:__imp_KeReleaseSpinLock
0x14003047f  nop     dword ptr [rax+rax+00h]
0x140030484  test    ebx, ebx
0x140030486  jns     short loc_1400304AE
0x140030488  jmp     short loc_1400304A1
0x14003048a  mov     dl, bpl; NewIrql
0x14003048d  mov     rcx, r12; SpinLock
0x140030490  call    cs:__imp_KeReleaseSpinLock
0x140030497  nop     dword ptr [rax+rax+00h]
0x14003049c  mov     ebx, 0C0000008h
0x1400304a1  xor     r8d, r8d
0x1400304a4  mov     edx, ebx
0x1400304a6  mov     rcx, rdi; Irp
0x1400304a9  call    NTIoComplete
0x1400304ae  mov     eax, ebx
0x1400304b0  add     rsp, 30h
0x1400304b4  pop     r15
0x1400304b6  pop     r14
0x1400304b8  pop     r12
0x1400304ba  pop     rdi
0x1400304bb  pop     rsi
0x1400304bc  pop     rbp
0x1400304bd  pop     rbx
0x1400304be  retn
```
