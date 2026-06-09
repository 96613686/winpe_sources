# ClfsReadRestartArea

- ea: `0x14005c540`
- end: `0x14005c76a`
- name: `ClfsReadRestartArea`
- size: `554`
- prototype: `NTSTATUS __stdcall(PVOID pvMarshalContext, PVOID *ppvRestartBuffer, PULONG pcbRestartBuffer, PCLFS_LSN plsn, PVOID *ppvReadContext)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x14005c540`
- `0x14005c770`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c5e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c5e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c65b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079ff1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c65b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079ff1`

## string_xrefs

- `0x14005c643`: `ClfsReadRestartArea`
- `0x14005c6ac`: `ClfsReadRestartArea`
- `0x14005c6e8`: `ClfsReadRestartArea`
- `0x14005c74e`: `ClfsReadRestartArea`

## pseudocode

```c
NTSTATUS __stdcall ClfsReadRestartArea(
        PVOID pvMarshalContext,
        PVOID *ppvRestartBuffer,
        PULONG pcbRestartBuffer,
        PCLFS_LSN plsn,
        PVOID *ppvReadContext)
{
  NTSTATUS RestartArea; // ebx

  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      161,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadRestartArea",
      235);
  }
  if ( !pvMarshalContext || !ppvRestartBuffer || !pcbRestartBuffer || !plsn || !ppvReadContext )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        162,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadRestartArea",
        247,
        -1073741811);
    }
    return -1073741811;
  }
  *ppvRestartBuffer = 0;
  *pcbRestartBuffer = 0;
  *ppvReadContext = 0;
  *plsn = CLFS_LSN_NULL;
  if ( *(_QWORD *)pvMarshalContext != 0xC8C1FDF00ALL )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        163,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadRestartArea",
        16,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  RestartArea = CClfsKernelMarshallingContext::ReadRestartArea(
                  (CClfsKernelMarshallingContext *)pvMarshalContext,
                  ppvRestartBuffer,
                  pcbRestartBuffer,
                  plsn,
                  ppvReadContext);
  if ( RestartArea < 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      164,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadRestartArea",
      51,
      RestartArea,
      RestartArea);
  }
  KeLeaveCriticalRegion();
  if ( RestartArea >= 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      165,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadRestartArea",
      71);
  }
  return RestartArea;
}

```

## disassembly

```asm
0x14005c540  push    rbx
0x14005c542  push    rsi
0x14005c543  push    r12
0x14005c545  push    r13
0x14005c547  push    r14
0x14005c549  push    r15
0x14005c54b  sub     rsp, 48h
0x14005c54f  mov     r15, r9
0x14005c552  mov     r12, r8
0x14005c555  mov     r13, rdx
0x14005c558  mov     rbx, rcx
0x14005c55b  lea     rsi, WPP_GLOBAL_Control
0x14005c562  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c569  cmp     rcx, rsi
0x14005c56c  jnz     loc_14005C692
0x14005c572  test    rbx, rbx
0x14005c575  jz      loc_14005C6C8
0x14005c57b  test    r13, r13
0x14005c57e  jz      loc_14005C6C8
0x14005c584  test    r12, r12
0x14005c587  jz      loc_14005C6C8
0x14005c58d  test    r15, r15
0x14005c590  jz      loc_14005C6C8
0x14005c596  mov     r14, [rsp+78h+ppvReadContext]
0x14005c59e  test    r14, r14
0x14005c5a1  jz      loc_14005C6C8
0x14005c5a7  mov     qword ptr [r13+0], 0
0x14005c5af  mov     dword ptr [r12], 0
0x14005c5b7  mov     qword ptr [r14], 0
0x14005c5be  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x14005c5c5  mov     [r15], rax
0x14005c5c8  cmp     dword ptr [rbx], 0C1FDF00Ah
0x14005c5ce  jnz     loc_14005C704
0x14005c5d4  cmp     dword ptr [rbx+4], 0C8h
0x14005c5db  jnz     loc_14005C704
0x14005c5e1  call    cs:__imp_KeEnterCriticalRegion
0x14005c5e8  nop     dword ptr [rax+rax+00h]
0x14005c5ed  nop
0x14005c5ee  mov     [rsp+78h+var_58], r14; void **
0x14005c5f3  mov     r9, r15; union _CLS_LSN *
0x14005c5f6  mov     r8, r12; unsigned int *
0x14005c5f9  mov     rdx, r13; void **
0x14005c5fc  mov     rcx, rbx; this
0x14005c5ff  call    ?ReadRestartArea@CClfsKernelMarshallingContext@@QEAAJAEAPEAXAEAKAEAT_CLS_LSN@@0@Z; CClfsKernelMarshallingContext::ReadRestartArea(void * &,ulong &,_CLS_LSN &,void * &)
0x14005c604  mov     ebx, eax
0x14005c606  mov     [rsp+78h+var_48], eax
0x14005c60a  jmp     short loc_14005C619
0x14005c60c  mov     ebx, eax
0x14005c60e  mov     [rsp+78h+var_48], eax
0x14005c612  lea     rsi, WPP_GLOBAL_Control
0x14005c619  test    ebx, ebx
0x14005c61b  jns     short loc_14005C65B
0x14005c61d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c624  cmp     rcx, rsi
0x14005c627  jz      short loc_14005C65B
0x14005c629  mov     eax, [rcx+2Ch]
0x14005c62c  bt      eax, 1Ah
0x14005c630  jnb     short loc_14005C65B
0x14005c632  mov     edx, 0A4h
0x14005c637  mov     [rsp+78h+var_50], ebx
0x14005c63b  mov     dword ptr [rsp+78h+var_58], 1333h
0x14005c643  lea     r9, aClfsreadrestar_0; "ClfsReadRestartArea"
0x14005c64a  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005c651  mov     rcx, [rcx+18h]
0x14005c655  call    WPP_SF_slD
0x14005c65a  nop
0x14005c65b  call    cs:__imp_KeLeaveCriticalRegion
0x14005c662  nop     dword ptr [rax+rax+00h]
0x14005c667  test    ebx, ebx
0x14005c669  js      short loc_14005C680
0x14005c66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c672  cmp     rcx, rsi
0x14005c675  jz      short loc_14005C680
0x14005c677  test    dword ptr [rcx+2Ch], 4000000h
0x14005c67e  jnz     short loc_14005C6DB
0x14005c680  mov     eax, ebx
0x14005c682  add     rsp, 48h
0x14005c686  pop     r15
0x14005c688  pop     r14
0x14005c68a  pop     r13
0x14005c68c  pop     r12
0x14005c68e  pop     rsi
0x14005c68f  pop     rbx
0x14005c690  retn
0x14005c692  test    dword ptr [rcx+2Ch], 4000000h
0x14005c699  jz      loc_14005C572
0x14005c69f  mov     edx, 0A1h
0x14005c6a4  mov     dword ptr [rsp+78h+var_58], 12EBh
0x14005c6ac  lea     r9, aClfsreadrestar_0; "ClfsReadRestartArea"
0x14005c6b3  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005c6ba  mov     rcx, [rcx+18h]
0x14005c6be  call    WPP_SF_sd
0x14005c6c3  jmp     loc_14005C572
0x14005c6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c6cf  cmp     rcx, rsi
0x14005c6d2  jnz     short loc_14005C730
0x14005c6d4  mov     eax, 0C000000Dh
0x14005c6d9  jmp     short loc_14005C682
0x14005c6db  mov     edx, 0A5h
0x14005c6e0  mov     dword ptr [rsp+78h+var_58], 1347h
0x14005c6e8  lea     r9, aClfsreadrestar_0; "ClfsReadRestartArea"
0x14005c6ef  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005c6f6  mov     rcx, [rcx+18h]
0x14005c6fa  call    WPP_SF_sd
0x14005c6ff  jmp     loc_14005C680
0x14005c704  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c70b  cmp     rcx, rsi
0x14005c70e  jz      short loc_14005C6D4
0x14005c710  test    dword ptr [rcx+2Ch], 4000000h
0x14005c717  jz      short loc_14005C6D4
0x14005c719  mov     edx, 0A3h
0x14005c71e  mov     [rsp+78h+var_50], 0C000000Dh
0x14005c726  mov     dword ptr [rsp+78h+var_58], 1310h
0x14005c72e  jmp     short loc_14005C74E
0x14005c730  test    dword ptr [rcx+2Ch], 4000000h
0x14005c737  jz      short loc_14005C6D4
0x14005c739  mov     edx, 0A2h
0x14005c73e  mov     [rsp+78h+var_50], 0C000000Dh
0x14005c746  mov     dword ptr [rsp+78h+var_58], 12F7h
0x14005c74e  lea     r9, aClfsreadrestar_0; "ClfsReadRestartArea"
0x14005c755  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005c75c  mov     rcx, [rcx+18h]
0x14005c760  call    WPP_SF_slD
0x14005c765  jmp     loc_14005C6D4
0x140079fe8  push    rbp
0x140079fea  sub     rsp, 30h
0x140079fee  mov     rbp, rdx
0x140079ff1  call    cs:__imp_KeLeaveCriticalRegion
0x140079ff8  nop     dword ptr [rax+rax+00h]
0x140079ffd  nop
0x140079ffe  add     rsp, 30h
0x14007a002  pop     rbp
0x14007a003  retn
```
