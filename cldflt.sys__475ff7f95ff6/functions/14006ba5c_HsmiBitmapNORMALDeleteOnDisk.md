# HsmiBitmapNORMALDeleteOnDisk

- ea: `0x14006ba5c`
- end: `0x14006bc41`
- name: `HsmiBitmapNORMALDeleteOnDisk`
- size: `485`
- prototype: `void __fastcall(unsigned int *Context)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400365c8`
- `0x140044c30`
- `0x14006a9e4`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x140018f10`
- `0x14003659c`
- `0x14006ba5c`
- `0x14006bc48`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14006ba6e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14006ba6e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006bb65`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006bb65`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14006bb05`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14006bb05`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14006ba83`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14006ba83`

## pseudocode

```c
void __fastcall HsmiBitmapNORMALDeleteOnDisk(unsigned int *Context)
{
  __int64 v1; // rdi
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rsi
  NTSTATUS v4; // ebp
  int v5; // esi
  int v6; // r8d

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
      HsmDbgBreakOnStatus(v4);
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
    v5 = HsmiBitmapNormalDeleteStream(v1, *(_QWORD *)Context, Context[8], 0);
    HsmDbgBreakOnStatus(v5);
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -1073741772 )
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
      WPP_SF_qisdd(
        WPP_GLOBAL_Control->AttachedDevice,
        106,
        v6,
        (_DWORD)Context,
        *(_QWORD *)Context,
        (__int64)(Context + 8),
        0,
        v5);
    }
  }
}

```

## disassembly

```asm
0x14006ba5c  push    rbx
0x14006ba5e  push    rbp
0x14006ba5f  push    rsi
0x14006ba60  push    rdi
0x14006ba61  push    r14
0x14006ba63  sub     rsp, 40h
0x14006ba67  mov     rdi, [rcx+28h]
0x14006ba6b  mov     rbx, rcx
0x14006ba6e  call    cs:__imp_IoGetTopLevelIrp
0x14006ba75  nop     dword ptr [rax+rax+00h]
0x14006ba7a  test    rax, rax
0x14006ba7d  jz      loc_14006BB76
0x14006ba83  call    cs:__imp_FltAllocateGenericWorkItem
0x14006ba8a  nop     dword ptr [rax+rax+00h]
0x14006ba8f  mov     rsi, rax
0x14006ba92  test    rax, rax
0x14006ba95  jnz     short loc_14006BAE1
0x14006ba97  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ba9e  lea     rdi, WPP_GLOBAL_Control
0x14006baa5  cmp     rcx, rdi
0x14006baa8  jz      loc_14006BC35
0x14006baae  mov     eax, [rcx+2Ch]
0x14006bab1  test    al, 1
0x14006bab3  jz      loc_14006BC35
0x14006bab9  cmp     byte ptr [rcx+29h], 2
0x14006babd  jb      loc_14006BC35
0x14006bac3  mov     rcx, [rcx+18h]
0x14006bac7  lea     edx, [rsi+67h]
0x14006baca  mov     r9d, 0C000009Ah
0x14006bad0  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006bad7  call    WPP_SF_d
0x14006badc  jmp     loc_14006BC35
0x14006bae1  mov     eax, [rbx+14h]
0x14006bae4  test    eax, eax
0x14006bae6  jle     short loc_14006BAEC
0x14006bae8  lock inc dword ptr [rbx+14h]
0x14006baec  mov     rdx, [rdi+20h]; FltObject
0x14006baf0  lea     r8, HsmiBitmapNORMALDeleteOnDiskWorker; WorkerRoutine
0x14006baf7  mov     r9d, 1; QueueType
0x14006bafd  mov     [rsp+68h+Context], rbx; Context
0x14006bb02  mov     rcx, rsi; FltWorkItem
0x14006bb05  call    cs:__imp_FltQueueGenericWorkItem
0x14006bb0c  nop     dword ptr [rax+rax+00h]
0x14006bb11  mov     ecx, eax
0x14006bb13  mov     ebp, eax
0x14006bb15  call    HsmDbgBreakOnStatus
0x14006bb1a  test    ebp, ebp
0x14006bb1c  jns     loc_14006BC35
0x14006bb22  mov     rcx, rbx
0x14006bb25  call    HsmpBitmapRelease
0x14006bb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bb31  lea     rdi, WPP_GLOBAL_Control
0x14006bb38  cmp     rcx, rdi
0x14006bb3b  jz      short loc_14006BB62
0x14006bb3d  mov     eax, [rcx+2Ch]
0x14006bb40  test    al, 1
0x14006bb42  jz      short loc_14006BB62
0x14006bb44  cmp     byte ptr [rcx+29h], 2
0x14006bb48  jb      short loc_14006BB62
0x14006bb4a  mov     rcx, [rcx+18h]
0x14006bb4e  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14006bb55  mov     edx, 68h ; 'h'
0x14006bb5a  mov     r9d, ebp
0x14006bb5d  call    WPP_SF_d
0x14006bb62  mov     rcx, rsi; FltWorkItem
0x14006bb65  call    cs:__imp_FltFreeGenericWorkItem
0x14006bb6c  nop     dword ptr [rax+rax+00h]
0x14006bb71  jmp     loc_14006BC35
0x14006bb76  mov     rdx, [rbx]
0x14006bb79  lea     r14, [rbx+20h]
0x14006bb7d  mov     r8d, [r14]
0x14006bb80  xor     r9d, r9d
0x14006bb83  mov     rcx, rdi
0x14006bb86  call    HsmiBitmapNormalDeleteStream
0x14006bb8b  mov     ecx, eax
0x14006bb8d  mov     esi, eax
0x14006bb8f  call    HsmDbgBreakOnStatus
0x14006bb94  mov     eax, 80000000h
0x14006bb99  lea     rdi, WPP_GLOBAL_Control
0x14006bba0  lea     ecx, [rsi+rax]
0x14006bba3  test    eax, ecx
0x14006bba5  jnz     short loc_14006BBF2
0x14006bba7  cmp     esi, 0C0000034h
0x14006bbad  jz      short loc_14006BBF2
0x14006bbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bbb6  cmp     rcx, rdi
0x14006bbb9  jz      short loc_14006BC35
0x14006bbbb  mov     eax, [rcx+2Ch]
0x14006bbbe  test    al, 1
0x14006bbc0  jz      short loc_14006BBF2
0x14006bbc2  cmp     byte ptr [rcx+29h], 2
0x14006bbc6  jb      short loc_14006BBF2
0x14006bbc8  mov     rax, [rbx]
0x14006bbcb  mov     edx, 69h ; 'i'
0x14006bbd0  mov     rcx, [rcx+18h]
0x14006bbd4  mov     r9, rbx
0x14006bbd7  mov     [rsp+68h+var_30], esi
0x14006bbdb  mov     [rsp+68h+var_38], 0
0x14006bbe3  mov     [rsp+68h+var_40], r14
0x14006bbe8  mov     [rsp+68h+Context], rax
0x14006bbed  call    WPP_SF_qisdd
0x14006bbf2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bbf9  cmp     rcx, rdi
0x14006bbfc  jz      short loc_14006BC35
0x14006bbfe  mov     eax, [rcx+2Ch]
0x14006bc01  test    al, 1
0x14006bc03  jz      short loc_14006BC35
0x14006bc05  cmp     byte ptr [rcx+29h], 4
0x14006bc09  jb      short loc_14006BC35
0x14006bc0b  mov     rax, [rbx]
0x14006bc0e  mov     edx, 6Ah ; 'j'
0x14006bc13  mov     rcx, [rcx+18h]
0x14006bc17  mov     r9, rbx
0x14006bc1a  mov     [rsp+68h+var_30], esi
0x14006bc1e  mov     [rsp+68h+var_38], 0
0x14006bc26  mov     [rsp+68h+var_40], r14
0x14006bc2b  mov     [rsp+68h+Context], rax
0x14006bc30  call    WPP_SF_qisdd
0x14006bc35  add     rsp, 40h
0x14006bc39  pop     r14
0x14006bc3b  pop     rdi
0x14006bc3c  pop     rsi
0x14006bc3d  pop     rbp
0x14006bc3e  pop     rbx
0x14006bc3f  retn
```
