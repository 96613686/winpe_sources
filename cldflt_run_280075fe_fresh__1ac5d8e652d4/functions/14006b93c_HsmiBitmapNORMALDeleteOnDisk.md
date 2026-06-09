# HsmiBitmapNORMALDeleteOnDisk

- ea: `0x14006b93c`
- end: `0x14006bb21`
- name: `HsmiBitmapNORMALDeleteOnDisk`
- size: `485`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400365c8`
- `0x140044b40`
- `0x14006a8c4`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x140018e90`
- `0x14003659c`
- `0x14006b93c`
- `0x14006bb28`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14006b94e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006b94e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006ba45`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006ba45`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14006b9e5`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14006b9e5`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14006b963`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14006b963`

## pseudocode

```c
void __fastcall HsmiBitmapNORMALDeleteOnDisk(unsigned int *Context)
{
  __int64 v1; // rdi
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rsi
  NTSTATUS v4; // ebp
  __int64 v5; // rsi
  int v6; // r8d
  __int64 v7; // [rsp+38h] [rbp-30h]

  v1 = *((_QWORD *)Context + 5);
  if ( IoGetTopLevelIrp() )
  {
    GenericWorkItem = FltAllocateGenericWorkItem();
    if ( GenericWorkItem )
    {
      if ( (int)Context[5] > 0 )
        _InterlockedIncrement((volatile signed __int32 *)Context + 5);
      v4 = FltQueueGenericWorkItem(
             GenericWorkItem,
             *(PVOID *)(v1 + 32),
             HsmiBitmapNORMALDeleteOnDiskWorker,
             DelayedWorkQueue,
             Context);
      HsmDbgBreakOnStatus((unsigned int)v4);
      if ( v4 < 0 )
      {
        HsmpBitmapRelease(Context);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
            (unsigned int)v4);
        }
        FltFreeGenericWorkItem(GenericWorkItem);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids, 3221225626LL);
    }
  }
  else
  {
    v5 = (unsigned int)HsmiBitmapNormalDeleteStream(v1, *(_QWORD *)Context, Context[8], 0);
    HsmDbgBreakOnStatus(v5);
    if ( (int)(v5 + 0x80000000) >= 0 && (_DWORD)v5 != -1073741772 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qisdd(
          WPP_GLOBAL_Control->AttachedDevice,
          105,
          v6,
          (_DWORD)Context,
          *(_QWORD *)Context,
          (__int64)(Context + 8),
          0,
          v5);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v7) = v5;
      WPP_SF_qisdd(
        WPP_GLOBAL_Control->AttachedDevice,
        106,
        v6,
        (_DWORD)Context,
        *(_QWORD *)Context,
        (__int64)(Context + 8),
        0,
        v7);
    }
  }
}

```

## disassembly

```asm
0x14006b93c  push    rbx
0x14006b93e  push    rbp
0x14006b93f  push    rsi
0x14006b940  push    rdi
0x14006b941  push    r14
0x14006b943  sub     rsp, 40h
0x14006b947  mov     rdi, [rcx+28h]
0x14006b94b  mov     rbx, rcx
0x14006b94e  call    cs:__imp_IoGetTopLevelIrp
0x14006b955  nop     dword ptr [rax+rax+00h]
0x14006b95a  test    rax, rax
0x14006b95d  jz      loc_14006BA56
0x14006b963  call    cs:__imp_FltAllocateGenericWorkItem
0x14006b96a  nop     dword ptr [rax+rax+00h]
0x14006b96f  mov     rsi, rax
0x14006b972  test    rax, rax
0x14006b975  jnz     short loc_14006B9C1
0x14006b977  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b97e  lea     rdi, WPP_GLOBAL_Control
0x14006b985  cmp     rcx, rdi
0x14006b988  jz      loc_14006BB15
0x14006b98e  mov     eax, [rcx+2Ch]
0x14006b991  test    al, 1
0x14006b993  jz      loc_14006BB15
0x14006b999  cmp     byte ptr [rcx+29h], 2
0x14006b99d  jb      loc_14006BB15
0x14006b9a3  mov     rcx, [rcx+18h]
0x14006b9a7  lea     edx, [rsi+67h]
0x14006b9aa  mov     r9d, 0C000009Ah
0x14006b9b0  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006b9b7  call    WPP_SF_d
0x14006b9bc  jmp     loc_14006BB15
0x14006b9c1  mov     eax, [rbx+14h]
0x14006b9c4  test    eax, eax
0x14006b9c6  jle     short loc_14006B9CC
0x14006b9c8  lock inc dword ptr [rbx+14h]
0x14006b9cc  mov     rdx, [rdi+20h]; FltObject
0x14006b9d0  lea     r8, HsmiBitmapNORMALDeleteOnDiskWorker; WorkerRoutine
0x14006b9d7  mov     r9d, 1; QueueType
0x14006b9dd  mov     [rsp+68h+Context], rbx; Context
0x14006b9e2  mov     rcx, rsi; FltWorkItem
0x14006b9e5  call    cs:__imp_FltQueueGenericWorkItem
0x14006b9ec  nop     dword ptr [rax+rax+00h]
0x14006b9f1  mov     ecx, eax
0x14006b9f3  mov     ebp, eax
0x14006b9f5  call    HsmDbgBreakOnStatus
0x14006b9fa  test    ebp, ebp
0x14006b9fc  jns     loc_14006BB15
0x14006ba02  mov     rcx, rbx
0x14006ba05  call    HsmpBitmapRelease
0x14006ba0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ba11  lea     rdi, WPP_GLOBAL_Control
0x14006ba18  cmp     rcx, rdi
0x14006ba1b  jz      short loc_14006BA42
0x14006ba1d  mov     eax, [rcx+2Ch]
0x14006ba20  test    al, 1
0x14006ba22  jz      short loc_14006BA42
0x14006ba24  cmp     byte ptr [rcx+29h], 2
0x14006ba28  jb      short loc_14006BA42
0x14006ba2a  mov     rcx, [rcx+18h]
0x14006ba2e  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006ba35  mov     edx, 68h ; 'h'
0x14006ba3a  mov     r9d, ebp
0x14006ba3d  call    WPP_SF_d
0x14006ba42  mov     rcx, rsi; FltWorkItem
0x14006ba45  call    cs:__imp_FltFreeGenericWorkItem
0x14006ba4c  nop     dword ptr [rax+rax+00h]
0x14006ba51  jmp     loc_14006BB15
0x14006ba56  mov     rdx, [rbx]
0x14006ba59  lea     r14, [rbx+20h]
0x14006ba5d  mov     r8d, [r14]
0x14006ba60  xor     r9d, r9d
0x14006ba63  mov     rcx, rdi
0x14006ba66  call    HsmiBitmapNormalDeleteStream
0x14006ba6b  mov     ecx, eax
0x14006ba6d  mov     esi, eax
0x14006ba6f  call    HsmDbgBreakOnStatus
0x14006ba74  mov     eax, 80000000h
0x14006ba79  lea     rdi, WPP_GLOBAL_Control
0x14006ba80  lea     ecx, [rsi+rax]
0x14006ba83  test    eax, ecx
0x14006ba85  jnz     short loc_14006BAD2
0x14006ba87  cmp     esi, 0C0000034h
0x14006ba8d  jz      short loc_14006BAD2
0x14006ba8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ba96  cmp     rcx, rdi
0x14006ba99  jz      short loc_14006BB15
0x14006ba9b  mov     eax, [rcx+2Ch]
0x14006ba9e  test    al, 1
0x14006baa0  jz      short loc_14006BAD2
0x14006baa2  cmp     byte ptr [rcx+29h], 2
0x14006baa6  jb      short loc_14006BAD2
0x14006baa8  mov     rax, [rbx]
0x14006baab  mov     edx, 69h ; 'i'
0x14006bab0  mov     rcx, [rcx+18h]
0x14006bab4  mov     r9, rbx
0x14006bab7  mov     dword ptr [rsp+68h+var_30], esi
0x14006babb  mov     [rsp+68h+var_38], 0
0x14006bac3  mov     [rsp+68h+var_40], r14
0x14006bac8  mov     [rsp+68h+Context], rax
0x14006bacd  call    WPP_SF_qisdd
0x14006bad2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bad9  cmp     rcx, rdi
0x14006badc  jz      short loc_14006BB15
0x14006bade  mov     eax, [rcx+2Ch]
0x14006bae1  test    al, 1
0x14006bae3  jz      short loc_14006BB15
0x14006bae5  cmp     byte ptr [rcx+29h], 4
0x14006bae9  jb      short loc_14006BB15
0x14006baeb  mov     rax, [rbx]
0x14006baee  mov     edx, 6Ah ; 'j'
0x14006baf3  mov     rcx, [rcx+18h]
0x14006baf7  mov     r9, rbx
0x14006bafa  mov     dword ptr [rsp+68h+var_30], esi
0x14006bafe  mov     [rsp+68h+var_38], 0
0x14006bb06  mov     [rsp+68h+var_40], r14
0x14006bb0b  mov     [rsp+68h+Context], rax
0x14006bb10  call    WPP_SF_qisdd
0x14006bb15  add     rsp, 40h
0x14006bb19  pop     r14
0x14006bb1b  pop     rdi
0x14006bb1c  pop     rsi
0x14006bb1d  pop     rbp
0x14006bb1e  pop     rbx
0x14006bb1f  retn
```
