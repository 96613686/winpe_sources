# VctpTearDownEndpoint

- ea: `0x14002d3f0`
- end: `0x14002d6b6`
- name: `VctpTearDownEndpoint`
- size: `710`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14002d3f0`
- `0x140031200`
- `0x14003838c`
- `0x14003faa8`
- `0x14004b4cc`
- `0x1400903a0`
- `0x140091bb0`
- `0x140093790`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002d551`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002d551`
- `ntoskrnl!IoFreeIrp` at `0x14002d4e7`
- `ntoskrnl!IoFreeIrp` at `0x14002d4e7`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002d463`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002d463`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d4c7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d4c7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d476`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d476`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d485`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d485`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d567`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d58d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d632`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d656`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d680`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d567`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d58d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d632`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d656`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d680`
- `rdbss!RxFreeMdl` at `0x14002d524`
- `rdbss!RxFreeMdl` at `0x14002d524`

## pseudocode

```c
void __fastcall VctpTearDownEndpoint(struct _EX_RUNDOWN_REF *Context)
{
  ULONG_PTR Count; // rdi
  int v3; // r8d
  unsigned int v4; // r14d
  KIRQL v5; // bp
  IRP *v6; // rcx
  PVOID Ptr; // rcx
  _QWORD *i; // rdi
  __int64 v9; // rax
  void *v10; // rax
  __int64 v11; // rcx
  PVOID v12; // rcx
  ULONG_PTR v13; // rcx
  PVOID v14; // rcx
  PVOID v15; // rcx
  PVOID v16; // rcx

  Count = Context[3].Count;
  v4 = RxCeTearDownVC((PRXCE_VC)Context);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_39c16dc859303064795977fd63584161_Traceguids, v4);
  }
  if ( Context[63].Count )
  {
    ExWaitForRundownProtectionRelease(Context + 62);
    v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(Count + 1920));
    *(_DWORD *)(Count + 2352) = (unsigned int)PsGetCurrentThreadId();
    if ( (struct _EX_RUNDOWN_REF *)Context[67].Count != &Context[67] )
      SmbCeRemoveVcEndpointLite(Context[63].Count, (__int64)Context);
    *(_DWORD *)(Count + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(Count + 1920), v5);
  }
  if ( LODWORD(Context[40].Count) == 1 )
  {
    v6 = (IRP *)Context[15].Count;
    if ( v6 )
    {
      IoFreeIrp(v6);
      Context[15].Count = 0;
    }
  }
  Ptr = Context[4].Ptr;
  if ( Ptr )
    SmbCepDereferenceTransport(Ptr);
  for ( i = (_QWORD *)_InterlockedExchange64((volatile __int64 *)&Context[60], 0);
        i;
        i = (_QWORD *)_InterlockedExchange64((volatile __int64 *)&Context[60], 0) )
  {
    RxFreeMdl(i[6]);
    v9 = i[7];
    if ( v9 )
    {
      v10 = (void *)(v9 & 0xFFFFFFFFFFFFFFF8uLL);
      v11 = i[7] & 7LL;
      if ( (unsigned int)v11 > 4 )
        ExFreePoolWithTag(v10, 0x6D535056u);
      else
        ExFreeToNPagedLookasideList(&SmbBufferLookasideList + v11, v10);
    }
    *(_OWORD *)i = 0;
    *((_OWORD *)i + 1) = 0;
    *((_OWORD *)i + 2) = 0;
    *((_OWORD *)i + 3) = 0;
    ExFreePoolWithTag(i, 0x6D534352u);
  }
  v12 = Context[58].Ptr;
  if ( v12 )
    ExFreePoolWithTag(v12, 0x6D536E44u);
  Context[58].Count = 0;
  LODWORD(Context[57].Count) = 0;
  v13 = Context[64].Count;
  if ( v13 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
      McTemplateK0hzr0p_EtwWriteTransfer(v13, (unsigned int)&SmbTeardownMidWindow, v3, 0, 0, Context[64].Count);
    SmbCseTeardownSlidingWindow(Context[64].Ptr);
    Context[64].Count = 0;
  }
  v14 = Context[69].Ptr;
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0x6D53674Eu);
    Context[69].Count = 0;
  }
  v15 = Context[72].Ptr;
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0x6D536850u);
    Context[72].Count = 0;
    HIDWORD(Context[71].Ptr) = 0;
  }
  v16 = Context[77].Ptr;
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0x6D53674Eu);
    Context[77].Count = 0;
    LODWORD(Context[78].Count) = 0;
  }
  SmbMmFreeServerTransport(Context);
}

```

## disassembly

```asm
0x14002d3f0  mov     [rsp+arg_10], rbx
0x14002d3f5  mov     [rsp+arg_18], rsi
0x14002d3fa  push    r14
0x14002d3fc  sub     rsp, 30h
0x14002d400  mov     [rsp+38h+arg_8], rdi
0x14002d405  mov     rbx, rcx
0x14002d408  mov     rdi, [rcx+18h]
0x14002d40c  call    RxCeTearDownVC
0x14002d411  mov     r14d, eax
0x14002d414  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002d41b  lea     rax, WPP_GLOBAL_Control
0x14002d422  cmp     rcx, rax
0x14002d425  jz      short loc_14002D44D
0x14002d427  mov     edx, [rcx+2Ch]
0x14002d42a  test    dl, 4
0x14002d42d  jz      short loc_14002D44D
0x14002d42f  cmp     byte ptr [rcx+29h], 4
0x14002d433  jb      short loc_14002D44D
0x14002d435  mov     rcx, [rcx+18h]
0x14002d439  lea     r8, WPP_39c16dc859303064795977fd63584161_Traceguids
0x14002d440  mov     edx, 1Ah
0x14002d445  mov     r9d, r14d
0x14002d448  call    WPP_SF_d
0x14002d44d  cmp     qword ptr [rbx+1F8h], 0
0x14002d455  mov     [rsp+38h+arg_0], rbp
0x14002d45a  jz      short loc_14002D4D3
0x14002d45c  lea     rcx, [rbx+1F0h]; RunRef
0x14002d463  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002d46a  nop     dword ptr [rax+rax+00h]
0x14002d46f  lea     rcx, [rdi+780h]; SpinLock
0x14002d476  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002d47d  nop     dword ptr [rax+rax+00h]
0x14002d482  movzx   ebp, al
0x14002d485  call    cs:__imp_PsGetCurrentThreadId
0x14002d48c  nop     dword ptr [rax+rax+00h]
0x14002d491  lea     rdx, [rbx+218h]
0x14002d498  mov     [rdi+930h], eax
0x14002d49e  cmp     [rdx], rdx
0x14002d4a1  jz      short loc_14002D4B2
0x14002d4a3  mov     rcx, [rbx+1F8h]; BugCheckParameter2
0x14002d4aa  mov     rdx, rbx
0x14002d4ad  call    SmbCeRemoveVcEndpointLite
0x14002d4b2  movzx   edx, bpl; OldIrql
0x14002d4b6  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x14002d4c0  lea     rcx, [rdi+780h]; SpinLock
0x14002d4c7  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002d4ce  nop     dword ptr [rax+rax+00h]
0x14002d4d3  xor     esi, esi
0x14002d4d5  cmp     dword ptr [rbx+140h], 1
0x14002d4dc  jnz     short loc_14002D4F7
0x14002d4de  mov     rcx, [rbx+78h]; Irp
0x14002d4e2  test    rcx, rcx
0x14002d4e5  jz      short loc_14002D4F7
0x14002d4e7  call    cs:__imp_IoFreeIrp
0x14002d4ee  nop     dword ptr [rax+rax+00h]
0x14002d4f3  mov     [rbx+78h], rsi
0x14002d4f7  mov     rcx, [rbx+20h]; P
0x14002d4fb  test    rcx, rcx
0x14002d4fe  jz      short loc_14002D505
0x14002d500  call    SmbCepDereferenceTransport
0x14002d505  mov     rdi, rsi
0x14002d508  xchg    rdi, [rbx+1E0h]
0x14002d50f  test    rdi, rdi
0x14002d512  jz      loc_14002D5AC
0x14002d518  lea     rbp, SmbBufferLookasideList
0x14002d51f  nop
0x14002d520  mov     rcx, [rdi+30h]
0x14002d524  call    cs:__imp_RxFreeMdl
0x14002d52b  nop     dword ptr [rax+rax+00h]
0x14002d530  mov     rax, [rdi+38h]
0x14002d534  test    rax, rax
0x14002d537  jz      short loc_14002D573
0x14002d539  mov     ecx, eax
0x14002d53b  and     rax, 0FFFFFFFFFFFFFFF8h
0x14002d53f  and     ecx, 7
0x14002d542  cmp     ecx, 4
0x14002d545  ja      short loc_14002D55F
0x14002d547  shl     rcx, 7
0x14002d54b  mov     rdx, rax; Entry
0x14002d54e  add     rcx, rbp; Lookaside
0x14002d551  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002d558  nop     dword ptr [rax+rax+00h]
0x14002d55d  jmp     short loc_14002D573
0x14002d55f  mov     edx, 6D535056h; Tag
0x14002d564  mov     rcx, rax; P
0x14002d567  call    cs:__imp_ExFreePoolWithTag
0x14002d56e  nop     dword ptr [rax+rax+00h]
0x14002d573  xorps   xmm0, xmm0
0x14002d576  mov     edx, 6D534352h; Tag
0x14002d57b  movups  xmmword ptr [rdi], xmm0
0x14002d57e  mov     rcx, rdi; P
0x14002d581  movups  xmmword ptr [rdi+10h], xmm0
0x14002d585  movups  xmmword ptr [rdi+20h], xmm0
0x14002d589  movups  xmmword ptr [rdi+30h], xmm0
0x14002d58d  call    cs:__imp_ExFreePoolWithTag
0x14002d594  nop     dword ptr [rax+rax+00h]
0x14002d599  mov     rdi, rsi
0x14002d59c  xchg    rdi, [rbx+1E0h]
0x14002d5a3  test    rdi, rdi
0x14002d5a6  jnz     loc_14002D520
0x14002d5ac  mov     rcx, [rbx+1D0h]; P
0x14002d5b3  mov     rdi, [rsp+38h+arg_8]
0x14002d5b8  mov     rbp, [rsp+38h+arg_0]
0x14002d5bd  test    rcx, rcx
0x14002d5c0  jz      short loc_14002D5D3
0x14002d5c2  mov     edx, 6D536E44h; Tag
0x14002d5c7  call    cs:__imp_ExFreePoolWithTag
0x14002d5ce  nop     dword ptr [rax+rax+00h]
0x14002d5d3  mov     [rbx+1D0h], rsi
0x14002d5da  mov     [rbx+1C8h], esi
0x14002d5e0  mov     rcx, [rbx+200h]
0x14002d5e7  test    rcx, rcx
0x14002d5ea  jz      short loc_14002D621
0x14002d5ec  test    cs:Microsoft_Windows_SMBClientEnableBits, 8
0x14002d5f3  jz      short loc_14002D60E
0x14002d5f5  mov     [rsp+38h+var_10], rcx
0x14002d5fa  lea     rdx, SmbTeardownMidWindow
0x14002d601  xor     r9d, r9d
0x14002d604  mov     [rsp+38h+var_18], rsi
0x14002d609  call    McTemplateK0hzr0p_EtwWriteTransfer
0x14002d60e  mov     rcx, [rbx+200h]; P
0x14002d615  call    SmbCseTeardownSlidingWindow
0x14002d61a  mov     [rbx+200h], rsi
0x14002d621  mov     rcx, [rbx+228h]; P
0x14002d628  test    rcx, rcx
0x14002d62b  jz      short loc_14002D645
0x14002d62d  mov     edx, 6D53674Eh; Tag
0x14002d632  call    cs:__imp_ExFreePoolWithTag
0x14002d639  nop     dword ptr [rax+rax+00h]
0x14002d63e  mov     [rbx+228h], rsi
0x14002d645  mov     rcx, [rbx+240h]; P
0x14002d64c  test    rcx, rcx
0x14002d64f  jz      short loc_14002D66F
0x14002d651  mov     edx, 6D536850h; Tag
0x14002d656  call    cs:__imp_ExFreePoolWithTag
0x14002d65d  nop     dword ptr [rax+rax+00h]
0x14002d662  mov     [rbx+240h], rsi
0x14002d669  mov     [rbx+23Ch], esi
0x14002d66f  mov     rcx, [rbx+268h]; P
0x14002d676  test    rcx, rcx
0x14002d679  jz      short loc_14002D699
0x14002d67b  mov     edx, 6D53674Eh; Tag
0x14002d680  call    cs:__imp_ExFreePoolWithTag
0x14002d687  nop     dword ptr [rax+rax+00h]
0x14002d68c  mov     [rbx+268h], rsi
0x14002d693  mov     [rbx+270h], esi
0x14002d699  mov     rcx, rbx
0x14002d69c  call    SmbMmFreeServerTransport
0x14002d6a1  mov     rbx, [rsp+38h+arg_10]
0x14002d6a6  mov     eax, r14d
0x14002d6a9  mov     rsi, [rsp+38h+arg_18]
0x14002d6ae  add     rsp, 30h
0x14002d6b2  pop     r14
0x14002d6b4  retn
```
