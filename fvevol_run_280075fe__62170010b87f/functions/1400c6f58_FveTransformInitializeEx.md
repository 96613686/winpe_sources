# FveTransformInitializeEx

- ea: `0x1400c6f58`
- end: `0x1400c7352`
- name: `FveTransformInitializeEx`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14007b540`
- `0x1400c6f20`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x1400c6f58`
- `0x1400d0570`
- `0x1400e51a8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400c7237`
- `ntoskrnl!KeInitializeEvent` at `0x1400c724c`
- `ntoskrnl!KeInitializeEvent` at `0x1400c72d6`
- `ntoskrnl!KeInitializeEvent` at `0x1400c7237`
- `ntoskrnl!KeInitializeEvent` at `0x1400c724c`
- `ntoskrnl!KeInitializeEvent` at `0x1400c72d6`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70c1`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70d6`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70e9`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70fb`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7112`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7124`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7137`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7149`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70c1`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70d6`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70e9`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c70fb`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7112`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7124`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7137`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400c7149`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400c7034`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400c7034`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400c7098`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400c7098`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400c70aa`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400c70aa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c7262`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c7262`
- `ntoskrnl!IoAllocateMdl` at `0x1400c707d`
- `ntoskrnl!IoAllocateMdl` at `0x1400c707d`
- `ntoskrnl!ExAllocatePool2` at `0x1400c6fc4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c704d`
- `ntoskrnl!ExAllocatePool2` at `0x1400c716a`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400c6fc4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c704d`
- `ntoskrnl!ExAllocatePool2` at `0x1400c716a`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71e8`

## pseudocode

```c
__int64 __fastcall FveTransformInitializeEx(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        ULONG_PTR *a7)
{
  __int64 v8; // rbx
  __int64 v11; // r15
  void *Pool2; // rax
  ULONG_PTR v13; // rdi
  unsigned int v14; // ebx
  void *v15; // rax
  struct _MDL *Mdl; // rax
  struct _MDL *v17; // rbx
  ULONG ActiveProcessorCount; // ebx
  void *v19; // rax
  void *v20; // rax
  void *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rsi
  PVOID v24; // rax

  v8 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids);
  }
  v11 = *(_QWORD *)(a1 + 8);
  Pool2 = (void *)ExAllocatePool2(64, 432, 1984255558);
  v13 = (ULONG_PTR)Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x1B0u);
    *(_QWORD *)(v13 + 8) = a1;
    *(_DWORD *)(v13 + 88) = a2;
    *(_DWORD *)(v13 + 84) = 1;
    *(_QWORD *)(v13 + 144) = *(_QWORD *)(a1 + 1048);
    *(_DWORD *)(v13 + 252) = *(_DWORD *)(a1 + 1308);
    *(_QWORD *)(v13 + 200) = a4;
    *(_QWORD *)(v13 + 160) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)(v13 + 392));
    v15 = (void *)ExAllocatePool2(64, v8, 1984255558);
    if ( !v15 )
      goto LABEL_25;
    *(_QWORD *)(v13 + 112) = v15;
    *(_DWORD *)(v13 + 120) = v8;
    Mdl = IoAllocateMdl(v15, v8, 0, 0, 0);
    v17 = Mdl;
    if ( !Mdl )
      goto LABEL_25;
    if ( ((MmBuildMdlForNonPagedPool(Mdl),
           MmMdlPageContentsState(v17, 1),
           *(_QWORD *)(v13 + 104) = v17,
           ActiveProcessorCount = 8,
           KeQueryActiveProcessorCountEx(0xFFFFu) <= 8)
       && !KeQueryActiveProcessorCountEx(0xFFFFu)
       || KeQueryActiveProcessorCountEx(0xFFFFu) > 8
       || KeQueryActiveProcessorCountEx(0xFFFFu))
      && (KeQueryActiveProcessorCountEx(0xFFFFu) > 8 || KeQueryActiveProcessorCountEx(0xFFFFu)) )
    {
      if ( KeQueryActiveProcessorCountEx(0xFFFFu) <= 8 )
        ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
    }
    else
    {
      ActiveProcessorCount = 1;
    }
    *(_DWORD *)(v13 + 72) = ActiveProcessorCount;
    v19 = (void *)ExAllocatePool2(64, 80LL * ActiveProcessorCount, 1984255558);
    *(_QWORD *)v13 = v19;
    if ( !v19 )
      goto LABEL_25;
    memset(v19, 0, 80LL * *(unsigned int *)(v13 + 72));
    v20 = (void *)ExAllocatePool2(64, 8LL * (unsigned int)(2 * *(_DWORD *)(v13 + 72)), 1984255558);
    *(_QWORD *)(v13 + 40) = v20;
    if ( v20
      && (memset(v20, 0, 8LL * (unsigned int)(2 * *(_DWORD *)(v13 + 72))),
          v21 = (void *)ExAllocatePool2(64, 48LL * (unsigned int)(2 * *(_DWORD *)(v13 + 72)), 1984255558),
          (*(_QWORD *)(v13 + 48) = v21) != 0) )
    {
      memset(v21, 0, 48LL * (unsigned int)(2 * *(_DWORD *)(v13 + 72)));
      v22 = 0;
      while ( (unsigned int)v22 < *(_DWORD *)(v13 + 72) )
      {
        v23 = *(_QWORD *)v13 + 80 * v22;
        KeInitializeEvent((PRKEVENT)(v23 + 16), NotificationEvent, 0);
        KeInitializeEvent((PRKEVENT)(v23 + 40), NotificationEvent, 0);
        *(_QWORD *)v23 = v13;
        v24 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v11 + 352));
        *(_QWORD *)(v23 + 8) = v24;
        if ( !v24 )
          goto LABEL_25;
        FveWorkItemInitialize(
          v11,
          *(_QWORD *)a1,
          *(unsigned int *)(a1 + 1324),
          v24,
          3,
          FveTransformAddRef,
          &FveTransformDeRef,
          v13);
        v22 = (unsigned int)(v22 + 1);
        *(_QWORD *)(*(_QWORD *)(v23 + 8) + 24LL) = v23;
      }
      v14 = 0;
      KeInitializeEvent((PRKEVENT)(v13 + 16), NotificationEvent, 0);
      *(_QWORD *)(v13 + 56) = a5;
      *(_QWORD *)(v13 + 64) = a6;
      *a7 = v13;
    }
    else
    {
LABEL_25:
      v14 = -1073741670;
      FveTransformCleanup(v13);
    }
  }
  else
  {
    v14 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x1400c6f58  push    rbx
0x1400c6f5a  push    rbp
0x1400c6f5b  push    rsi
0x1400c6f5c  push    rdi
0x1400c6f5d  push    r12
0x1400c6f5f  push    r13
0x1400c6f61  push    r14
0x1400c6f63  push    r15
0x1400c6f65  sub     rsp, 48h
0x1400c6f69  mov     rsi, r9
0x1400c6f6c  mov     ebx, r8d
0x1400c6f6f  mov     ebp, edx
0x1400c6f71  mov     r14, rcx
0x1400c6f74  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c6f7b  lea     rax, WPP_GLOBAL_Control
0x1400c6f82  cmp     rcx, rax
0x1400c6f85  jz      short loc_1400C6FA9
0x1400c6f87  mov     eax, [rcx+2Ch]
0x1400c6f8a  test    al, 2
0x1400c6f8c  jz      short loc_1400C6FA9
0x1400c6f8e  cmp     byte ptr [rcx+29h], 5
0x1400c6f92  jb      short loc_1400C6FA9
0x1400c6f94  mov     rcx, [rcx+18h]
0x1400c6f98  lea     r8, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids
0x1400c6f9f  mov     edx, 0Ah
0x1400c6fa4  call    WPP_SF_
0x1400c6fa9  mov     r15, [r14+8]
0x1400c6fad  mov     r13d, 76455646h
0x1400c6fb3  mov     r12d, 1B0h
0x1400c6fb9  mov     r8d, r13d
0x1400c6fbc  mov     edx, r12d
0x1400c6fbf  mov     ecx, 40h ; '@'
0x1400c6fc4  call    cs:__imp_ExAllocatePool2
0x1400c6fcb  nop     dword ptr [rax+rax+00h]
0x1400c6fd0  mov     rdi, rax
0x1400c6fd3  test    rax, rax
0x1400c6fd6  jnz     short loc_1400C6FE2
0x1400c6fd8  mov     ebx, 0C000009Ah
0x1400c6fdd  jmp     loc_1400C7305
0x1400c6fe2  mov     r8, r12; Size
0x1400c6fe5  xor     edx, edx; Val
0x1400c6fe7  mov     rcx, rdi; void *
0x1400c6fea  call    memset
0x1400c6fef  mov     [rdi+8], r14
0x1400c6ff3  lea     rcx, [rdi+188h]; SpinLock
0x1400c6ffa  mov     [rdi+58h], ebp
0x1400c6ffd  mov     r12d, 1
0x1400c7003  mov     [rdi+54h], r12d
0x1400c7007  mov     rax, [r14+418h]
0x1400c700e  mov     [rdi+90h], rax
0x1400c7015  mov     eax, [r14+51Ch]
0x1400c701c  mov     [rdi+0FCh], eax
0x1400c7022  mov     [rdi+0C8h], rsi
0x1400c7029  mov     qword ptr [rdi+0A0h], 0
0x1400c7034  call    cs:__imp_KeInitializeSpinLock
0x1400c703b  nop     dword ptr [rax+rax+00h]
0x1400c7040  lea     ebp, [r12+3Fh]
0x1400c7045  mov     rdx, rbx
0x1400c7048  mov     ecx, ebp
0x1400c704a  mov     r8d, r13d
0x1400c704d  call    cs:__imp_ExAllocatePool2
0x1400c7054  nop     dword ptr [rax+rax+00h]
0x1400c7059  test    rax, rax
0x1400c705c  jz      loc_1400C72C1
0x1400c7062  xor     r9d, r9d; ChargeQuota
0x1400c7065  mov     [rdi+70h], rax
0x1400c7069  xor     r8d, r8d; SecondaryBuffer
0x1400c706c  mov     [rdi+78h], ebx
0x1400c706f  mov     edx, ebx; Length
0x1400c7071  mov     [rsp+88h+Irp], 0; Irp
0x1400c707a  mov     rcx, rax; VirtualAddress
0x1400c707d  call    cs:__imp_IoAllocateMdl
0x1400c7084  nop     dword ptr [rax+rax+00h]
0x1400c7089  mov     rbx, rax
0x1400c708c  test    rax, rax
0x1400c708f  jz      loc_1400C72C1
0x1400c7095  mov     rcx, rax; MemoryDescriptorList
0x1400c7098  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400c709f  nop     dword ptr [rax+rax+00h]
0x1400c70a4  mov     edx, r12d
0x1400c70a7  mov     rcx, rbx
0x1400c70aa  call    cs:__imp_MmMdlPageContentsState
0x1400c70b1  nop     dword ptr [rax+rax+00h]
0x1400c70b6  mov     esi, 0FFFFh
0x1400c70bb  mov     [rdi+68h], rbx
0x1400c70bf  mov     ecx, esi; GroupNumber
0x1400c70c1  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c70c8  nop     dword ptr [rax+rax+00h]
0x1400c70cd  lea     ebx, [rbp-38h]
0x1400c70d0  cmp     eax, ebx
0x1400c70d2  ja      short loc_1400C70E7
0x1400c70d4  mov     ecx, esi; GroupNumber
0x1400c70d6  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c70dd  nop     dword ptr [rax+rax+00h]
0x1400c70e2  cmp     eax, r12d
0x1400c70e5  jb      short loc_1400C7110
0x1400c70e7  mov     ecx, esi; GroupNumber
0x1400c70e9  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c70f0  nop     dword ptr [rax+rax+00h]
0x1400c70f5  cmp     eax, ebx
0x1400c70f7  ja      short loc_1400C7110
0x1400c70f9  mov     ecx, esi; GroupNumber
0x1400c70fb  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c7102  nop     dword ptr [rax+rax+00h]
0x1400c7107  test    eax, eax
0x1400c7109  jnz     short loc_1400C7110
0x1400c710b  mov     ebx, r12d
0x1400c710e  jmp     short loc_1400C7157
0x1400c7110  mov     ecx, esi; GroupNumber
0x1400c7112  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c7119  nop     dword ptr [rax+rax+00h]
0x1400c711e  cmp     eax, ebx
0x1400c7120  ja      short loc_1400C7135
0x1400c7122  mov     ecx, esi; GroupNumber
0x1400c7124  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c712b  nop     dword ptr [rax+rax+00h]
0x1400c7130  cmp     eax, r12d
0x1400c7133  jb      short loc_1400C710B
0x1400c7135  mov     ecx, esi; GroupNumber
0x1400c7137  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c713e  nop     dword ptr [rax+rax+00h]
0x1400c7143  cmp     eax, ebx
0x1400c7145  ja      short loc_1400C7157
0x1400c7147  mov     ecx, esi; GroupNumber
0x1400c7149  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400c7150  nop     dword ptr [rax+rax+00h]
0x1400c7155  mov     ebx, eax
0x1400c7157  mov     eax, ebx
0x1400c7159  mov     r8d, r13d
0x1400c715c  mov     rcx, rbp
0x1400c715f  mov     [rdi+48h], ebx
0x1400c7162  lea     rdx, [rax+rax*4]
0x1400c7166  shl     rdx, 4
0x1400c716a  call    cs:__imp_ExAllocatePool2
0x1400c7171  nop     dword ptr [rax+rax+00h]
0x1400c7176  mov     [rdi], rax
0x1400c7179  mov     rcx, rax; void *
0x1400c717c  test    rax, rax
0x1400c717f  jz      loc_1400C72C1
0x1400c7185  mov     eax, [rdi+48h]
0x1400c7188  xor     edx, edx; Val
0x1400c718a  lea     r8, [rax+rax*4]
0x1400c718e  shl     r8, 4; Size
0x1400c7192  call    memset
0x1400c7197  mov     eax, [rdi+48h]
0x1400c719a  mov     r8d, r13d
0x1400c719d  mov     rcx, rbp
0x1400c71a0  lea     edx, [rax+rax]
0x1400c71a3  shl     rdx, 3
0x1400c71a7  call    cs:__imp_ExAllocatePool2
0x1400c71ae  nop     dword ptr [rax+rax+00h]
0x1400c71b3  mov     [rdi+28h], rax
0x1400c71b7  mov     rcx, rax; void *
0x1400c71ba  test    rax, rax
0x1400c71bd  jz      loc_1400C72C1
0x1400c71c3  mov     eax, [rdi+48h]
0x1400c71c6  xor     edx, edx; Val
0x1400c71c8  lea     r8d, [rax+rax]
0x1400c71cc  shl     r8, 3; Size
0x1400c71d0  call    memset
0x1400c71d5  mov     eax, [rdi+48h]
0x1400c71d8  mov     r8d, r13d
0x1400c71db  add     eax, eax
0x1400c71dd  mov     rcx, rbp
0x1400c71e0  lea     rdx, [rax+rax*2]
0x1400c71e4  shl     rdx, 4
0x1400c71e8  call    cs:__imp_ExAllocatePool2
0x1400c71ef  nop     dword ptr [rax+rax+00h]
0x1400c71f4  mov     [rdi+30h], rax
0x1400c71f8  mov     rcx, rax; void *
0x1400c71fb  test    rax, rax
0x1400c71fe  jz      loc_1400C72C1
0x1400c7204  mov     eax, [rdi+48h]
0x1400c7207  xor     edx, edx; Val
0x1400c7209  add     eax, eax
0x1400c720b  lea     r8, [rax+rax*2]
0x1400c720f  shl     r8, 4; Size
0x1400c7213  call    memset
0x1400c7218  xor     ebx, ebx
0x1400c721a  xor     r8d, r8d; State
0x1400c721d  xor     edx, edx; Type
0x1400c721f  cmp     ebx, [rdi+48h]
0x1400c7222  jnb     loc_1400C72D0
0x1400c7228  lea     rsi, [rbx+rbx*4]
0x1400c722c  shl     rsi, 4
0x1400c7230  add     rsi, [rdi]
0x1400c7233  lea     rcx, [rsi+10h]; Event
0x1400c7237  call    cs:__imp_KeInitializeEvent
0x1400c723e  nop     dword ptr [rax+rax+00h]
0x1400c7243  lea     rcx, [rsi+28h]; Event
0x1400c7247  xor     r8d, r8d; State
0x1400c724a  xor     edx, edx; Type
0x1400c724c  call    cs:__imp_KeInitializeEvent
0x1400c7253  nop     dword ptr [rax+rax+00h]
0x1400c7258  mov     [rsi], rdi
0x1400c725b  mov     rcx, [r15+160h]; Lookaside
0x1400c7262  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400c7269  nop     dword ptr [rax+rax+00h]
0x1400c726e  mov     [rsi+8], rax
0x1400c7272  test    rax, rax
0x1400c7275  jz      short loc_1400C72C1
0x1400c7277  mov     r8d, [r14+52Ch]
0x1400c727e  lea     rcx, FveTransformDeRef
0x1400c7285  mov     rdx, [r14]
0x1400c7288  mov     r9, rax
0x1400c728b  mov     [rsp+88h+var_50], rdi
0x1400c7290  mov     [rsp+88h+var_58], rcx
0x1400c7295  lea     rcx, FveTransformAddRef
0x1400c729c  mov     [rsp+88h+var_60], rcx
0x1400c72a1  mov     rcx, r15
0x1400c72a4  mov     dword ptr [rsp+88h+Irp], 3
0x1400c72ac  call    FveWorkItemInitialize
0x1400c72b1  mov     rax, [rsi+8]
0x1400c72b5  add     ebx, r12d
0x1400c72b8  mov     [rax+18h], rsi
0x1400c72bc  jmp     loc_1400C721A
0x1400c72c1  mov     rcx, rdi; BugCheckParameter2
0x1400c72c4  mov     ebx, 0C000009Ah
0x1400c72c9  call    FveTransformCleanup
0x1400c72ce  jmp     short loc_1400C7305
0x1400c72d0  xor     ebx, ebx
0x1400c72d2  lea     rcx, [rdi+10h]; Event
0x1400c72d6  call    cs:__imp_KeInitializeEvent
0x1400c72dd  nop     dword ptr [rax+rax+00h]
0x1400c72e2  mov     rax, [rsp+88h+arg_20]
0x1400c72ea  mov     [rdi+38h], rax
0x1400c72ee  mov     rax, [rsp+88h+arg_28]
0x1400c72f6  mov     [rdi+40h], rax
0x1400c72fa  mov     rax, [rsp+88h+arg_30]
0x1400c7302  mov     [rax], rdi
0x1400c7305  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c730c  lea     rax, WPP_GLOBAL_Control
0x1400c7313  cmp     rcx, rax
0x1400c7316  jz      short loc_1400C733E
0x1400c7318  mov     edx, [rcx+2Ch]
0x1400c731b  test    dl, 2
0x1400c731e  jz      short loc_1400C733E
0x1400c7320  cmp     byte ptr [rcx+29h], 5
0x1400c7324  jb      short loc_1400C733E
0x1400c7326  mov     rcx, [rcx+18h]
0x1400c732a  lea     r8, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids
0x1400c7331  mov     edx, 0Bh
0x1400c7336  mov     r9d, ebx
0x1400c7339  call    WPP_SF_d
0x1400c733e  mov     eax, ebx
0x1400c7340  add     rsp, 48h
0x1400c7344  pop     r15
0x1400c7346  pop     r14
0x1400c7348  pop     r13
0x1400c734a  pop     r12
0x1400c734c  pop     rdi
0x1400c734d  pop     rsi
0x1400c734e  pop     rbp
0x1400c734f  pop     rbx
0x1400c7350  retn
```
