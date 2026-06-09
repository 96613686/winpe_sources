# NptrigQueueWaitNamedPipeRequest

- ea: `0x140009b00`
- end: `0x140009d8d`
- name: `NptrigQueueWaitNamedPipeRequest`
- size: `653`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Cbd, __int64, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140001010`

## callees

- `0x140001860`
- `0x140001928`
- `0x140001c40`
- `0x140009b00`
- `0x140009da0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009c81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c81`
- `ntoskrnl!KeSetTimer` at `0x140009d62`
- `ntoskrnl!KeSetTimer` at `0x140009d62`
- `ntoskrnl!ExAllocatePool2` at `0x140009b4d`
- `ntoskrnl!ExAllocatePool2` at `0x140009b4d`
- `ntoskrnl!KeInitializeTimer` at `0x140009bfa`
- `ntoskrnl!KeInitializeTimer` at `0x140009bfa`
- `ntoskrnl!KeInitializeDpc` at `0x140009bea`
- `ntoskrnl!KeInitializeDpc` at `0x140009bea`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140009bb2`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140009bb2`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140009c6d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140009c6d`
- `FLTMGR!FltCbdqInsertIo` at `0x140009c4f`
- `FLTMGR!FltCbdqInsertIo` at `0x140009c4f`

## pseudocode

```c
__int64 __fastcall NptrigQueueWaitNamedPipeRequest(
        PFLT_CALLBACK_DATA Cbd,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  __int64 v6; // rbx
  __int64 v9; // r15
  __int64 Pool2; // rax
  _QWORD *v11; // rdi
  size_t v13; // rsi
  const void *v14; // rdx
  PFLT_GENERIC_WORKITEM GenericWorkItem; // rax
  NTSTATUS inserted; // esi
  __int64 v17; // r8
  __int64 v18; // r8
  struct _FLT_GENERIC_WORKITEM *v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  int v22; // [rsp+7Ch] [rbp+24h]

  v22 = HIDWORD(a4);
  v6 = a4;
  NptrigCleanupOrphanedWaitNamedPipeRequests(a2);
  v9 = (unsigned __int16)(*a3 + 2);
  Pool2 = ExAllocatePool2(64, v9 + 208, 1735684174);
  v11 = (_QWORD *)Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  v13 = *a3;
  v14 = (const void *)*((_QWORD *)a3 + 1);
  *(_QWORD *)(Pool2 + 104) = Pool2 + 208;
  *(_WORD *)(Pool2 + 96) = v13;
  *(_WORD *)(Pool2 + 98) = v9;
  memmove((void *)(Pool2 + 208), v14, v13);
  *(_WORD *)(v11[13] + 2 * (v13 >> 1)) = 0;
  *((_DWORD *)v11 + 47) = 1;
  v11[25] = a2;
  GenericWorkItem = FltAllocateGenericWorkItem();
  v11[24] = GenericWorkItem;
  if ( !GenericWorkItem )
  {
    inserted = -1073741801;
LABEL_9:
    v19 = (struct _FLT_GENERIC_WORKITEM *)v11[24];
    if ( v19 )
      FltFreeGenericWorkItem(v19);
    ExFreePoolWithTag(v11, 0x6774704Eu);
    return (unsigned int)inserted;
  }
  _InterlockedExchange((volatile __int32 *)v11 + 28, 1);
  KeInitializeDpc((PRKDPC)(v11 + 1), NptrigWaitNamedPipeTimeoutCallback, v11);
  KeInitializeTimer((PKTIMER)(v11 + 15));
  NptrigTakeRequestRef(v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 25, v17, v11, Cbd);
  *v11 = Cbd;
  inserted = FltCbdqInsertIo(
               (PFLT_CALLBACK_DATA_QUEUE)(a2 + 24),
               Cbd,
               (PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT)v11 + 3,
               v11);
  if ( inserted < 0 )
    goto LABEL_9;
  if ( a5 )
  {
    if ( (v6 >= 0 || -v6 <= -*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 6)) && ((_DWORD)v6 || v22 != 0x80000000) )
    {
      *((_DWORD *)v11 + 46) = 0;
      goto LABEL_25;
    }
    v6 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 6);
    *((_DWORD *)v11 + 46) = 1;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_25;
    v21 = 27;
  }
  else
  {
    v6 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 6);
    *((_DWORD *)v11 + 46) = 1;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_25;
    v21 = 26;
  }
  WPP_SF_qq(v20->AttachedDevice, v21, v18, Cbd, v11);
LABEL_25:
  KeSetTimer((PKTIMER)(v11 + 15), (LARGE_INTEGER)v6, (PKDPC)(v11 + 1));
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140009b00  mov     [rsp+arg_8], rbx
0x140009b05  mov     [rsp+arg_10], rbp
0x140009b0a  mov     [rsp+arg_18], r9
0x140009b0f  push    rsi
0x140009b10  push    rdi
0x140009b11  push    r12
0x140009b13  push    r14
0x140009b15  push    r15
0x140009b17  sub     rsp, 30h
0x140009b1b  mov     r12, rcx
0x140009b1e  mov     rbx, r9
0x140009b21  mov     rcx, rdx
0x140009b24  mov     r14, r8
0x140009b27  mov     rbp, rdx
0x140009b2a  call    NptrigCleanupOrphanedWaitNamedPipeRequests
0x140009b2f  movzx   eax, word ptr [r14]
0x140009b33  mov     ecx, 40h ; '@'
0x140009b38  add     ax, 2
0x140009b3c  mov     r8d, 6774704Eh
0x140009b42  movzx   r15d, ax
0x140009b46  lea     rdx, [r15+0D0h]
0x140009b4d  call    cs:__imp_ExAllocatePool2
0x140009b54  nop     dword ptr [rax+rax+00h]
0x140009b59  mov     rdi, rax
0x140009b5c  test    rax, rax
0x140009b5f  jnz     short loc_140009B6B
0x140009b61  mov     eax, 0C0000017h
0x140009b66  jmp     loc_140009D75
0x140009b6b  movzx   esi, word ptr [r14]
0x140009b6f  lea     rcx, [rax+0D0h]; void *
0x140009b76  mov     rdx, [r14+8]; Src
0x140009b7a  mov     r8d, esi; Size
0x140009b7d  mov     [rsp+58h+arg_0], r13
0x140009b82  mov     [rax+68h], rcx
0x140009b86  mov     [rax+60h], si
0x140009b8a  mov     [rax+62h], r15w
0x140009b8f  call    memmove
0x140009b94  mov     rcx, [rdi+68h]
0x140009b98  xor     eax, eax
0x140009b9a  shr     rsi, 1
0x140009b9d  mov     [rcx+rsi*2], ax
0x140009ba1  mov     dword ptr [rdi+0BCh], 1
0x140009bab  mov     [rdi+0C8h], rbp
0x140009bb2  call    cs:__imp_FltAllocateGenericWorkItem
0x140009bb9  nop     dword ptr [rax+rax+00h]
0x140009bbe  mov     [rdi+0C0h], rax
0x140009bc5  test    rax, rax
0x140009bc8  jnz     short loc_140009BD4
0x140009bca  mov     esi, 0C0000017h
0x140009bcf  jmp     loc_140009C61
0x140009bd4  mov     eax, 1
0x140009bd9  lea     rdx, NptrigWaitNamedPipeTimeoutCallback; DeferredRoutine
0x140009be0  xchg    eax, [rdi+70h]
0x140009be3  mov     r8, rdi; DeferredContext
0x140009be6  lea     rcx, [rdi+8]; Dpc
0x140009bea  call    cs:__imp_KeInitializeDpc
0x140009bf1  nop     dword ptr [rax+rax+00h]
0x140009bf6  lea     rcx, [rdi+78h]; Timer
0x140009bfa  call    cs:__imp_KeInitializeTimer
0x140009c01  nop     dword ptr [rax+rax+00h]
0x140009c06  mov     rcx, rdi
0x140009c09  call    NptrigTakeRequestRef
0x140009c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c15  lea     rax, WPP_GLOBAL_Control
0x140009c1c  cmp     rcx, rax
0x140009c1f  jz      short loc_140009C3E
0x140009c21  mov     eax, [rcx+2Ch]
0x140009c24  test    al, 4
0x140009c26  jz      short loc_140009C3E
0x140009c28  mov     rcx, [rcx+18h]
0x140009c2c  mov     edx, 19h
0x140009c31  mov     r9, rdi
0x140009c34  mov     [rsp+58h+var_38], r12
0x140009c39  call    WPP_SF_qq
0x140009c3e  lea     r8, [rdi+48h]; Context
0x140009c42  mov     [rdi], r12
0x140009c45  lea     rcx, [rbp+18h]; Cbdq
0x140009c49  mov     r9, rdi; InsertContext
0x140009c4c  mov     rdx, r12; Cbd
0x140009c4f  call    cs:__imp_FltCbdqInsertIo
0x140009c56  nop     dword ptr [rax+rax+00h]
0x140009c5b  mov     esi, eax
0x140009c5d  test    eax, eax
0x140009c5f  jns     short loc_140009C92
0x140009c61  mov     rcx, [rdi+0C0h]; FltWorkItem
0x140009c68  test    rcx, rcx
0x140009c6b  jz      short loc_140009C79
0x140009c6d  call    cs:__imp_FltFreeGenericWorkItem
0x140009c74  nop     dword ptr [rax+rax+00h]
0x140009c79  mov     edx, 6774704Eh; Tag
0x140009c7e  mov     rcx, rdi; P
0x140009c81  call    cs:__imp_ExFreePoolWithTag
0x140009c88  nop     dword ptr [rax+rax+00h]
0x140009c8d  jmp     loc_140009D6E
0x140009c92  cmp     [rsp+58h+arg_20], 0
0x140009c9a  jnz     short loc_140009CDA
0x140009c9c  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140009ca3  mov     rbx, [rbx+30h]
0x140009ca7  mov     dword ptr [rdi+0B8h], 1
0x140009cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140009cb8  lea     rax, WPP_GLOBAL_Control
0x140009cbf  cmp     rcx, rax
0x140009cc2  jz      loc_140009D57
0x140009cc8  mov     eax, [rcx+2Ch]
0x140009ccb  test    al, 4
0x140009ccd  jz      loc_140009D57
0x140009cd3  mov     edx, 1Ah
0x140009cd8  jmp     short loc_140009D3A
0x140009cda  test    rbx, rbx
0x140009cdd  jns     short loc_140009CF8
0x140009cdf  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140009ce6  mov     rcx, [rax+30h]
0x140009cea  mov     rax, rbx
0x140009ced  neg     rax
0x140009cf0  neg     rcx
0x140009cf3  cmp     rax, rcx
0x140009cf6  jg      short loc_140009D06
0x140009cf8  test    ebx, ebx
0x140009cfa  jnz     short loc_140009D4D
0x140009cfc  cmp     dword ptr [rsp+58h+arg_18+4], 80000000h
0x140009d04  jnz     short loc_140009D4D
0x140009d06  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140009d0d  mov     rbx, [rbx+30h]
0x140009d11  mov     dword ptr [rdi+0B8h], 1
0x140009d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d22  lea     rax, WPP_GLOBAL_Control
0x140009d29  cmp     rcx, rax
0x140009d2c  jz      short loc_140009D57
0x140009d2e  mov     eax, [rcx+2Ch]
0x140009d31  test    al, 4
0x140009d33  jz      short loc_140009D57
0x140009d35  mov     edx, 1Bh
0x140009d3a  mov     rcx, [rcx+18h]
0x140009d3e  mov     r9, r12
0x140009d41  mov     [rsp+58h+var_38], rdi
0x140009d46  call    WPP_SF_qq
0x140009d4b  jmp     short loc_140009D57
0x140009d4d  mov     dword ptr [rdi+0B8h], 0
0x140009d57  lea     r8, [rdi+8]; Dpc
0x140009d5b  mov     rdx, rbx; DueTime
0x140009d5e  lea     rcx, [rdi+78h]; Timer
0x140009d62  call    cs:__imp_KeSetTimer
0x140009d69  nop     dword ptr [rax+rax+00h]
0x140009d6e  mov     r13, [rsp+58h+arg_0]
0x140009d73  mov     eax, esi
0x140009d75  mov     rbx, [rsp+58h+arg_8]
0x140009d7a  mov     rbp, [rsp+58h+arg_10]
0x140009d7f  add     rsp, 30h
0x140009d83  pop     r15
0x140009d85  pop     r14
0x140009d87  pop     r12
0x140009d89  pop     rdi
0x140009d8a  pop     rsi
0x140009d8b  retn
```
