# MdaCancelNotify

- ea: `0x14002f040`
- end: `0x14002f4a8`
- name: `MdaCancelNotify`
- size: `1128`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140030724`

## callees

- `0x1400159cc`
- `0x140017590`
- `0x14002f040`
- `0x140030724`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002f108`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002f108`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002f464`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b61f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002f464`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003b61f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f1f6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f2d7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f1f6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f2d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3f6`
- `ntoskrnl!ExAllocatePool2` at `0x14002f328`
- `ntoskrnl!ExAllocatePool2` at `0x14002f328`
- `rdbss!RxLowIoCompletion` at `0x14002f426`
- `rdbss!RxLowIoCompletion` at `0x14002f426`

## pseudocode

```c
__int64 __fastcall MdaCancelNotify(PRX_CONTEXT RxContext)
{
  PIRP CurrentIrp; // rax
  PFAST_MUTEX *Information; // r14
  PFAST_MUTEX v4; // rcx
  struct _KTHREAD *CurrentThread; // rdi
  _QWORD *v7; // r8
  PFAST_MUTEX *v8; // rax
  PFAST_MUTEX *v9; // r12
  struct _RX_CONTEXT *v10; // r13
  _QWORD *v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  struct _IRP **v14; // rdi
  struct _IRP *v15; // rdx
  PMDL MdlAddress; // rcx
  struct _IRP *MappedSystemVa; // rax
  PVOID Pool2; // r15
  unsigned int v19; // edi
  unsigned int *v20; // rdx
  _QWORD *v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  _BYTE *v24; // rax
  __int64 v25; // [rsp+58h] [rbp-70h]
  PFAST_MUTEX *P; // [rsp+80h] [rbp-48h]
  const void **v28; // [rsp+D8h] [rbp+10h]
  unsigned int *v29; // [rsp+E0h] [rbp+18h]
  _QWORD *v30; // [rsp+E8h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  CurrentIrp = RxContext->CurrentIrp;
  Information = (PFAST_MUTEX *)CurrentIrp->IoStatus.Information;
  CurrentIrp->IoStatus.Information = 0;
  v4 = *Information;
  if ( !*Information )
    return 3221225485LL;
  CurrentThread = KeGetCurrentThread();
  if ( CurrentThread != *(struct _KTHREAD **)&v4[1].Count )
  {
    ExAcquireFastMutexUnsafe(v4);
    *(_QWORD *)&(*Information)[1].Count = CurrentThread;
  }
  ++LODWORD((*Information)[1].Owner);
  v7 = Information + 72;
  v8 = Information + 72;
  v9 = (PFAST_MUTEX *)Information[72];
  while ( v9 != v8 )
  {
    P = v9 - 1;
    v10 = (struct _RX_CONTEXT *)*(v9 - 1);
    if ( !v10->CurrentIrp->Cancel )
      goto LABEL_50;
    v9 = (PFAST_MUTEX *)v9[1];
    v11 = *v9;
    v12 = *(_QWORD *)&(*v9)->Count;
    if ( *(PFAST_MUTEX *)(v12 + 8) != *v9 || (v13 = (_QWORD *)v11[1], (_QWORD *)*v13 != v11) )
      __fastfail(3u);
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    v14 = (struct _IRP **)(Information + 76);
    v28 = (const void **)(Information + 76);
    v15 = (struct _IRP *)Information[76];
    if ( v15 )
    {
      v30 = Information + 75;
      if ( !Information[75] )
      {
        if ( (MdlAddress = v10->CurrentIrp->MdlAddress) != 0
          && ((MdlAddress->MdlFlags & 5) == 0
            ? (MappedSystemVa = (struct _IRP *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u),
               v7 = Information + 72)
            : (MappedSystemVa = (struct _IRP *)MdlAddress->MappedSystemVa),
              v15 = *v14,
              MappedSystemVa == *v14)
          || v15 == v10->CurrentIrp->AssociatedIrp.MasterIrp )
        {
          Pool2 = 0;
          v19 = 0;
          v20 = (unsigned int *)(Information + 78);
          v29 = (unsigned int *)(Information + 78);
          if ( (_QWORD *)*v7 == v7 )
          {
            if ( *((_DWORD *)Information + 154) >= *v20 )
              v19 = *((_DWORD *)Information + 154);
          }
          else
          {
            v21 = *(_QWORD **)(*(_QWORD *)(*v7 - 8LL) + 40LL);
            v22 = *v20;
            v25 = v21[23];
            if ( *(_DWORD *)(v25 + 8) >= v22 )
            {
              if ( v21[3] )
              {
                Pool2 = (PVOID)v21[3];
                goto LABEL_28;
              }
              v23 = v21[1];
              if ( v23 )
              {
                if ( (*(_BYTE *)(v23 + 10) & 5) != 0 )
                {
                  Pool2 = *(PVOID *)(v23 + 24);
                  v19 = *(_DWORD *)(v25 + 8);
                }
                else
                {
                  Pool2 = MmMapLockedPagesSpecifyCache((PMDL)v23, 0, MmCached, 0, 0, 0x40000010u);
                  v19 = *(_DWORD *)(v25 + 8);
                  v22 = *v29;
                }
              }
              else
              {
LABEL_28:
                v19 = *(_DWORD *)(v25 + 8);
              }
              if ( v19 > *((_DWORD *)Information + 154) )
                v19 = *((_DWORD *)Information + 154);
              if ( v19 < v22 )
                v19 = 0;
            }
          }
          if ( v19 )
          {
            if ( Pool2 || (Pool2 = (PVOID)ExAllocatePool2(258, v19, 911369806), (*v30 = Pool2) != 0) )
            {
              memmove(Pool2, *v28, *v29);
              *((_DWORD *)Information + 155) = v19;
              *v28 = Pool2;
            }
            v24 = Information + 74;
          }
          else
          {
            v24 = Information + 74;
            *((_WORD *)Information + 296) |= 2u;
          }
          if ( (*v24 & 2) != 0 )
          {
            *v28 = 0;
            *v30 = 0;
            *((_DWORD *)Information + 157) = 0;
            *v29 = 0;
            *((_DWORD *)Information + 155) = 0;
          }
        }
      }
    }
    ExFreePoolWithTag(P, 0);
    if ( v10 != RxContext )
      MdaNotifySetCancelRoutine(v10);
    RxContext->StoredStatus = -1073741536;
    RxLowIoCompletion(v10);
    v7 = Information + 72;
LABEL_50:
    v9 = (PFAST_MUTEX *)*v9;
    v8 = Information + 72;
  }
  if ( !--LODWORD((*Information)[1].Owner) )
  {
    *(_QWORD *)&(*Information)[1].Count = 0;
    ExReleaseFastMutexUnsafe(*Information);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14002f040  mov     [rsp+arg_0], rcx
0x14002f045  push    rbx
0x14002f046  push    rsi
0x14002f047  push    rdi
0x14002f048  push    r12
0x14002f04a  push    r13
0x14002f04c  push    r14
0x14002f04e  push    r15
0x14002f050  sub     rsp, 90h
0x14002f057  mov     rbx, rcx
0x14002f05a  lea     r15, WPP_GLOBAL_Control
0x14002f061  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f068  cmp     rcx, r15
0x14002f06b  jz      short loc_14002F08B
0x14002f06d  test    dword ptr [rcx+2Ch], 80000h
0x14002f074  jz      short loc_14002F08B
0x14002f076  mov     edx, 23h ; '#'
0x14002f07b  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f082  mov     rcx, [rcx+18h]
0x14002f086  call    WPP_SF_
0x14002f08b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f092  cmp     rcx, r15
0x14002f095  jz      short loc_14002F0B8
0x14002f097  test    dword ptr [rcx+2Ch], 80000h
0x14002f09e  jz      short loc_14002F0B8
0x14002f0a0  mov     edx, 24h ; '$'
0x14002f0a5  mov     r9, rbx
0x14002f0a8  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f0af  mov     rcx, [rcx+18h]
0x14002f0b3  call    WPP_SF_q
0x14002f0b8  mov     rax, [rbx+28h]
0x14002f0bc  mov     r14, [rax+38h]
0x14002f0c0  xor     ebx, ebx
0x14002f0c2  mov     [rax+38h], rbx
0x14002f0c6  mov     rcx, [r14]; FastMutex
0x14002f0c9  test    rcx, rcx
0x14002f0cc  jnz     short loc_14002F0E7
0x14002f0ce  mov     eax, 0C000000Dh
0x14002f0d3  add     rsp, 90h
0x14002f0da  pop     r15
0x14002f0dc  pop     r14
0x14002f0de  pop     r13
0x14002f0e0  pop     r12
0x14002f0e2  pop     rdi
0x14002f0e3  pop     rsi
0x14002f0e4  pop     rbx
0x14002f0e5  retn
0x14002f0e7  mov     rsi, r14
0x14002f0ea  mov     [rsp+0C8h+var_80], r14
0x14002f0ef  mov     [rsp+0C8h+var_50], r14
0x14002f0f4  mov     [rsp+0C8h+var_78], r14
0x14002f0f9  mov     rdi, gs:188h
0x14002f102  cmp     rdi, [rcx+38h]
0x14002f106  jz      short loc_14002F11B
0x14002f108  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002f10f  nop     dword ptr [rax+rax+00h]
0x14002f114  mov     rax, [r14]
0x14002f117  mov     [rax+38h], rdi
0x14002f11b  mov     rax, [r14]
0x14002f11e  inc     dword ptr [rax+40h]
0x14002f121  lea     r8, [r14+240h]
0x14002f128  mov     [rsp+0C8h+var_88], r8
0x14002f12d  mov     rax, r8
0x14002f130  mov     [rsp+0C8h+var_40], rax
0x14002f138  mov     r12, [r8]
0x14002f13b  cmp     r12, rax
0x14002f13e  jz      loc_14002F44F
0x14002f144  lea     rax, [r12-8]
0x14002f149  mov     [rsp+0C8h+P], rax
0x14002f151  mov     r13, [rax]
0x14002f154  mov     [rsp+0C8h+var_58], r13
0x14002f159  mov     rax, [r13+28h]
0x14002f15d  cmp     [rax+44h], bl
0x14002f160  jz      loc_14002F437
0x14002f166  mov     r12, [r12+8]
0x14002f16b  mov     rax, [r12]
0x14002f16f  mov     rdx, [rax]
0x14002f172  cmp     [rdx+8], rax
0x14002f176  jnz     loc_14002F448
0x14002f17c  mov     rcx, [rax+8]
0x14002f180  cmp     [rcx], rax
0x14002f183  jnz     loc_14002F448
0x14002f189  mov     [rsp+0C8h+var_68], r12
0x14002f18e  mov     [rcx], rdx
0x14002f191  mov     [rdx+8], rcx
0x14002f195  lea     rdi, [rsi+260h]
0x14002f19c  mov     [rsp+0C8h+arg_8], rdi
0x14002f1a4  mov     rdx, [rdi]
0x14002f1a7  test    rdx, rdx
0x14002f1aa  jz      loc_14002F3EC
0x14002f1b0  lea     rax, [rsi+258h]
0x14002f1b7  mov     [rsp+0C8h+arg_18], rax
0x14002f1bf  cmp     [rax], rbx
0x14002f1c2  jnz     loc_14002F3EC
0x14002f1c8  mov     rax, [r13+28h]
0x14002f1cc  mov     rcx, [rax+8]; MemoryDescriptorList
0x14002f1d0  test    rcx, rcx
0x14002f1d3  jz      short loc_14002F20F
0x14002f1d5  test    byte ptr [rcx+0Ah], 5
0x14002f1d9  jz      short loc_14002F1E1
0x14002f1db  mov     rax, [rcx+18h]
0x14002f1df  jmp     short loc_14002F207
0x14002f1e1  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x14002f1e9  mov     [rsp+0C8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14002f1ed  xor     r9d, r9d; RequestedAddress
0x14002f1f0  xor     edx, edx; AccessMode
0x14002f1f2  lea     r8d, [r9+1]; CacheType
0x14002f1f6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f1fd  nop     dword ptr [rax+rax+00h]
0x14002f202  mov     r8, [rsp+0C8h+var_88]
0x14002f207  mov     rdx, [rdi]
0x14002f20a  cmp     rax, rdx
0x14002f20d  jz      short loc_14002F21D
0x14002f20f  mov     rax, [r13+28h]
0x14002f213  cmp     rdx, [rax+18h]
0x14002f217  jnz     loc_14002F3EC
0x14002f21d  mov     [rsp+0C8h+var_90], rbx
0x14002f222  mov     [rsp+0C8h+var_98], ebx
0x14002f226  mov     r15, rbx
0x14002f229  mov     [rsp+0C8h+var_90], rbx
0x14002f22e  mov     edi, ebx
0x14002f230  mov     [rsp+0C8h+var_98], ebx
0x14002f234  mov     rax, [r8]
0x14002f237  mov     rdx, [rsp+0C8h+var_78]
0x14002f23c  add     rdx, 270h
0x14002f243  mov     [rsp+0C8h+arg_10], rdx
0x14002f24b  cmp     rax, r8
0x14002f24e  jz      loc_14002F2FF
0x14002f254  mov     rax, [rax-8]
0x14002f258  mov     rcx, [rax+28h]
0x14002f25c  mov     edx, [rdx]
0x14002f25e  mov     rax, [rcx+0B8h]
0x14002f265  mov     [rsp+0C8h+var_70], rax
0x14002f26a  mov     r8d, [rax+8]
0x14002f26e  cmp     r8d, edx
0x14002f271  jb      loc_14002F30E
0x14002f277  mov     rax, [rcx+18h]
0x14002f27b  test    rax, rax
0x14002f27e  jz      short loc_14002F2AA
0x14002f280  mov     r15, rax
0x14002f283  mov     [rsp+0C8h+var_90], rax
0x14002f288  mov     edi, r8d
0x14002f28b  mov     [rsp+0C8h+var_98], edi
0x14002f28f  mov     eax, [rsi+268h]
0x14002f295  cmp     edi, eax
0x14002f297  cmova   edi, eax
0x14002f29a  mov     [rsp+0C8h+var_98], edi
0x14002f29e  cmp     edi, edx
0x14002f2a0  jnb     short loc_14002F30E
0x14002f2a2  mov     edi, ebx
0x14002f2a4  mov     [rsp+0C8h+var_98], ebx
0x14002f2a8  jmp     short loc_14002F30E
0x14002f2aa  mov     rcx, [rcx+8]; MemoryDescriptorList
0x14002f2ae  test    rcx, rcx
0x14002f2b1  jz      short loc_14002F288
0x14002f2b3  test    byte ptr [rcx+0Ah], 5
0x14002f2b7  jz      short loc_14002F2C2
0x14002f2b9  mov     r15, [rcx+18h]
0x14002f2bd  mov     edi, r8d
0x14002f2c0  jmp     short loc_14002F2F8
0x14002f2c2  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x14002f2ca  mov     [rsp+0C8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14002f2ce  xor     r9d, r9d; RequestedAddress
0x14002f2d1  xor     edx, edx; AccessMode
0x14002f2d3  lea     r8d, [r9+1]; CacheType
0x14002f2d7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f2de  nop     dword ptr [rax+rax+00h]
0x14002f2e3  mov     r15, rax
0x14002f2e6  mov     rdi, [rsp+0C8h+var_70]
0x14002f2eb  mov     edi, [rdi+8]
0x14002f2ee  mov     rdx, [rsp+0C8h+arg_10]
0x14002f2f6  mov     edx, [rdx]
0x14002f2f8  mov     [rsp+0C8h+var_90], r15
0x14002f2fd  jmp     short loc_14002F28B
0x14002f2ff  mov     eax, [rsi+268h]
0x14002f305  cmp     eax, [rdx]
0x14002f307  cmovnb  edi, eax
0x14002f30a  mov     [rsp+0C8h+var_98], edi
0x14002f30e  test    edi, edi
0x14002f310  jz      loc_14002F3B0
0x14002f316  test    r15, r15
0x14002f319  jnz     short loc_14002F34C
0x14002f31b  mov     edx, edi
0x14002f31d  mov     ecx, 102h
0x14002f322  mov     r8d, 3652664Eh
0x14002f328  call    cs:__imp_ExAllocatePool2
0x14002f32f  nop     dword ptr [rax+rax+00h]
0x14002f334  mov     r15, rax
0x14002f337  mov     [rsp+0C8h+var_90], rax
0x14002f33c  mov     rax, [rsp+0C8h+arg_18]
0x14002f344  mov     [rax], r15
0x14002f347  test    r15, r15
0x14002f34a  jz      short loc_14002F37B
0x14002f34c  mov     rax, [rsp+0C8h+arg_10]
0x14002f354  mov     r8d, [rax]; Size
0x14002f357  mov     rdx, [rsp+0C8h+arg_8]
0x14002f35f  mov     rdx, [rdx]; Src
0x14002f362  mov     rcx, r15; void *
0x14002f365  call    memmove
0x14002f36a  mov     [rsi+26Ch], edi
0x14002f370  mov     rax, [rsp+0C8h+arg_8]
0x14002f378  mov     [rax], r15
0x14002f37b  jmp     short loc_14002F3A3
0x14002f37d  mov     rsi, [rsp+0C8h+var_80]
0x14002f382  movzx   eax, word ptr [rsi+250h]
0x14002f389  or      ax, 2
0x14002f38d  mov     [rsi+250h], ax
0x14002f394  xor     ebx, ebx
0x14002f396  mov     r12, [rsp+0C8h+var_68]
0x14002f39b  mov     r14, rsi
0x14002f39e  mov     r13, [rsp+0C8h+var_58]
0x14002f3a3  mov     rax, [rsp+0C8h+var_50]
0x14002f3a8  add     rax, 250h
0x14002f3ae  jmp     short loc_14002F3BB
0x14002f3b0  lea     rax, [rsi+250h]
0x14002f3b7  or      word ptr [rax], 2
0x14002f3bb  test    byte ptr [rax], 2
0x14002f3be  jz      short loc_14002F3EC
0x14002f3c0  mov     rax, [rsp+0C8h+arg_8]
0x14002f3c8  mov     [rax], rbx
0x14002f3cb  mov     rax, [rsp+0C8h+arg_18]
0x14002f3d3  mov     [rax], rbx
0x14002f3d6  mov     [rsi+274h], ebx
0x14002f3dc  mov     rax, [rsp+0C8h+arg_10]
0x14002f3e4  mov     [rax], ebx
0x14002f3e6  mov     [rsi+26Ch], ebx
0x14002f3ec  xor     edx, edx; Tag
0x14002f3ee  mov     rcx, [rsp+0C8h+P]; P
0x14002f3f6  call    cs:__imp_ExFreePoolWithTag
0x14002f3fd  nop     dword ptr [rax+rax+00h]
0x14002f402  mov     rdi, [rsp+0C8h+arg_0]
0x14002f40a  cmp     r13, rdi
0x14002f40d  jz      short loc_14002F419
0x14002f40f  mov     dl, 1
0x14002f411  mov     rcx, r13; RxContext
0x14002f414  call    MdaNotifySetCancelRoutine
0x14002f419  mov     dword ptr [rdi+0B0h], 0C0000120h
0x14002f423  mov     rcx, r13; RxContext
0x14002f426  call    cs:__imp_RxLowIoCompletion
0x14002f42d  nop     dword ptr [rax+rax+00h]
0x14002f432  mov     r8, [rsp+0C8h+var_88]
0x14002f437  mov     r12, [r12]
0x14002f43b  mov     rax, [rsp+0C8h+var_40]
0x14002f443  jmp     loc_14002F13B
0x14002f448  mov     ecx, 3
0x14002f44d  int     29h; Win8: RtlFailFast(ecx)
0x14002f44f  mov     rax, [r14]
0x14002f452  dec     dword ptr [rax+40h]
0x14002f455  mov     rax, [r14]
0x14002f458  cmp     [rax+40h], ebx
0x14002f45b  jnz     short loc_14002F470
0x14002f45d  mov     [rax+38h], rbx
0x14002f461  mov     rcx, [r14]; FastMutex
0x14002f464  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002f46b  nop     dword ptr [rax+rax+00h]
0x14002f470  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f477  lea     rax, WPP_GLOBAL_Control
0x14002f47e  cmp     rcx, rax
0x14002f481  jz      short loc_14002F4A1
0x14002f483  test    dword ptr [rcx+2Ch], 80000h
0x14002f48a  jz      short loc_14002F4A1
0x14002f48c  mov     edx, 25h ; '%'
0x14002f491  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f498  mov     rcx, [rcx+18h]
0x14002f49c  call    WPP_SF_
0x14002f4a1  xor     eax, eax
0x14002f4a3  jmp     loc_14002F0D3
0x14003b5d3  push    rbp
0x14003b5d5  sub     rsp, 30h
0x14003b5d9  mov     rbp, rdx
0x14003b5dc  mov     rax, [rcx]
0x14003b5df  mov     ecx, [rax]
0x14003b5e1  xor     eax, eax
0x14003b5e3  cmp     ecx, 0C0000044h
0x14003b5e9  setz    al
0x14003b5ec  add     rsp, 30h
0x14003b5f0  pop     rbp
0x14003b5f1  retn
0x14003b5f3  push    rbp
0x14003b5f5  sub     rsp, 30h
0x14003b5f9  mov     rbp, rdx
0x14003b5fc  mov     rcx, [rbp+48h]
0x14003b600  mov     rax, [rcx]
0x14003b603  mov     edx, [rax+40h]
0x14003b606  dec     edx
0x14003b608  mov     [rax+40h], edx
0x14003b60b  mov     rax, [rcx]
0x14003b60e  cmp     dword ptr [rax+40h], 0
0x14003b612  jnz     short loc_14003B62C
0x14003b614  mov     qword ptr [rax+38h], 0
0x14003b61c  mov     rcx, [rcx]; FastMutex
0x14003b61f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003b626  nop     dword ptr [rax+rax+00h]
0x14003b62b  nop
0x14003b62c  lea     rax, WPP_GLOBAL_Control
0x14003b633  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b63a  cmp     rcx, rax
0x14003b63d  jz      short loc_14003B65E
0x14003b63f  mov     eax, [rcx+2Ch]
0x14003b642  bt      eax, 13h
  ... truncated ...
```
