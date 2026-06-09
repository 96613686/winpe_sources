# HsmFileCacheCreateFileObject

- ea: `0x14001b590`
- end: `0x14001b854`
- name: `HsmFileCacheCreateFileObject`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140070864`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x14000d95c`
- `0x14001b42c`
- `0x14001b590`
- `0x14001b85c`
- `0x14001bb78`
- `0x14001cbc8`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14001b613`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14001b613`
- `ntoskrnl!CcInitializeCacheMap` at `0x14001b774`
- `ntoskrnl!CcInitializeCacheMap` at `0x14001b774`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b7a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b7a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed9d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b749`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b749`

## pseudocode

```c
__int64 __fastcall HsmFileCacheCreateFileObject(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        PFILE_OBJECT *a8)
{
  PFILE_OBJECT StreamFileObjectLite; // rbx
  unsigned int StreamControlBlock; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qDqic(WPP_GLOBAL_Control->AttachedDevice);
  }
  *a8 = 0;
  StreamFileObjectLite = IoCreateStreamFileObjectLite(0, DeviceObject);
  StreamControlBlock = HsmiFileCacheAllocateStreamControlBlock(a1, a2, a3, a4, a6);
  HsmDbgBreakOnStatus(StreamControlBlock);
  if ( (StreamControlBlock & 0x80000000) == 0 )
  {
    StreamFileObjectLite->FsContext = 0;
    StreamFileObjectLite->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)256;
    *(_WORD *)&StreamFileObjectLite->SharedRead = 1;
    *(_WORD *)&StreamFileObjectLite->ReadAccess = 257;
    KeEnterCriticalRegion();
    CcInitializeCacheMap(StreamFileObjectLite, (PCC_FILE_SIZES)0x18, 1u, &Callbacks, 0);
    KeLeaveCriticalRegion();
    *a8 = StreamFileObjectLite;
    StreamFileObjectLite = 0;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      StreamControlBlock);
  }
  if ( StreamFileObjectLite )
    HsmFileCacheCloseFileObject(StreamFileObjectLite);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      *a8,
      StreamControlBlock);
  }
  return StreamControlBlock;
}

```

## disassembly

```asm
0x14001b590  mov     rax, rsp
0x14001b593  mov     [rax+20h], r9
0x14001b597  mov     [rax+18h], r8
0x14001b59b  mov     [rax+10h], edx
0x14001b59e  mov     [rax+8], rcx
0x14001b5a2  push    rbx
0x14001b5a3  push    rsi
0x14001b5a4  push    r12
0x14001b5a6  push    r13
0x14001b5a8  push    r14
0x14001b5aa  push    r15
0x14001b5ac  sub     rsp, 58h
0x14001b5b0  mov     r12, r9
0x14001b5b3  mov     r15, r8
0x14001b5b6  xor     esi, esi
0x14001b5b8  mov     [rax-44h], esi
0x14001b5bb  mov     [rax-40h], rsi
0x14001b5bf  mov     [rax+38h], rsi
0x14001b5c3  mov     [rax-48h], sil
0x14001b5c7  lea     r14, WPP_GLOBAL_Control
0x14001b5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5d5  cmp     rcx, r14
0x14001b5d8  jz      short loc_14001B5FE
0x14001b5da  mov     eax, [rcx+2Ch]
0x14001b5dd  test    al, 8
0x14001b5df  jz      short loc_14001B5FE
0x14001b5e1  cmp     byte ptr [rcx+29h], 5
0x14001b5e5  jb      short loc_14001B5FE
0x14001b5e7  mov     [rsp+88h+var_58], r9
0x14001b5ec  mov     [rsp+88h+var_60], r8
0x14001b5f1  mov     dword ptr [rsp+88h+LazyWriteContext], edx
0x14001b5f5  mov     rcx, [rcx+18h]
0x14001b5f9  call    WPP_SF_qDqic
0x14001b5fe  mov     r13, [rsp+88h+arg_38]
0x14001b606  mov     [r13+0], rsi
0x14001b60a  mov     rdx, cs:DeviceObject; DeviceObject
0x14001b611  xor     ecx, ecx; FileObject
0x14001b613  call    cs:__imp_IoCreateStreamFileObjectLite
0x14001b61a  nop     dword ptr [rax+rax+00h]
0x14001b61f  mov     rbx, rax
0x14001b622  mov     [rsp+88h+var_40], rax
0x14001b627  jmp     short loc_14001B651
0x14001b629  lea     r14, WPP_GLOBAL_Control
0x14001b630  mov     r13, [rsp+88h+arg_38]
0x14001b638  mov     r12, [rsp+88h+arg_18]
0x14001b640  mov     r15, [rsp+88h+arg_10]
0x14001b648  mov     esi, [rsp+88h+var_44]
0x14001b64c  mov     rbx, [rsp+88h+var_40]
0x14001b651  test    esi, esi
0x14001b653  jns     short loc_14001B69F
0x14001b655  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b65c  cmp     rcx, r14
0x14001b65f  jz      loc_14001B7FE
0x14001b665  mov     eax, [rcx+2Ch]
0x14001b668  test    al, 8
0x14001b66a  jz      loc_14001B7FE
0x14001b670  cmp     byte ptr [rcx+29h], 2
0x14001b674  jb      loc_14001B7FE
0x14001b67a  mov     edx, 21h ; '!'
0x14001b67f  mov     dword ptr [rsp+88h+LazyWriteContext], esi
0x14001b683  mov     r9, cs:DeviceObject
0x14001b68a  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b691  mov     rcx, [rcx+18h]
0x14001b695  call    WPP_SF_qd
0x14001b69a  jmp     loc_14001B7FE
0x14001b69f  lea     rax, [rsp+88h+arg_30]
0x14001b6a7  mov     [rsp+88h+var_58], rax
0x14001b6ac  mov     rax, [rsp+88h+arg_28]
0x14001b6b4  mov     [rsp+88h+LazyWriteContext], rax
0x14001b6b9  mov     r9, r12
0x14001b6bc  mov     r8, r15
0x14001b6bf  mov     edx, [rsp+88h+arg_8]
0x14001b6c6  mov     rcx, [rsp+88h+arg_0]
0x14001b6ce  call    HsmiFileCacheAllocateStreamControlBlock
0x14001b6d3  mov     esi, eax
0x14001b6d5  mov     [rsp+88h+var_44], eax
0x14001b6d9  mov     ecx, eax
0x14001b6db  call    HsmDbgBreakOnStatus
0x14001b6e0  test    esi, esi
0x14001b6e2  jns     short loc_14001B726
0x14001b6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6eb  cmp     rcx, r14
0x14001b6ee  jz      loc_14001B7FE
0x14001b6f4  mov     eax, [rcx+2Ch]
0x14001b6f7  test    al, 8
0x14001b6f9  jz      loc_14001B7FE
0x14001b6ff  cmp     byte ptr [rcx+29h], 2
0x14001b703  jb      loc_14001B7FE
0x14001b709  mov     edx, 22h ; '"'
0x14001b70e  mov     r9d, esi
0x14001b711  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b718  mov     rcx, [rcx+18h]
0x14001b71c  call    WPP_SF_d
0x14001b721  jmp     loc_14001B7FE
0x14001b726  mov     r15, [rsp+88h+arg_30]
0x14001b72e  mov     [rbx+18h], r15
0x14001b732  lea     rax, [r15+100h]
0x14001b739  mov     [rbx+28h], rax
0x14001b73d  mov     word ptr [rbx+4Dh], 1
0x14001b743  mov     word ptr [rbx+4Ah], 101h
0x14001b749  call    cs:__imp_KeEnterCriticalRegion
0x14001b750  nop     dword ptr [rax+rax+00h]
0x14001b755  mov     [rsp+88h+var_48], 1
0x14001b75a  lea     rdx, [r15+18h]; FileSizes
0x14001b75e  mov     [rsp+88h+LazyWriteContext], 0; LazyWriteContext
0x14001b767  lea     r9, Callbacks; Callbacks
0x14001b76e  mov     r8b, 1; PinAccess
0x14001b771  mov     rcx, rbx; FileObject
0x14001b774  call    cs:__imp_CcInitializeCacheMap
0x14001b77b  nop     dword ptr [rax+rax+00h]
0x14001b780  jmp     short loc_14001B7A2
0x14001b782  lea     r14, WPP_GLOBAL_Control
0x14001b789  mov     r13, [rsp+88h+arg_38]
0x14001b791  mov     r12, [rsp+88h+arg_18]
0x14001b799  mov     esi, [rsp+88h+var_44]
0x14001b79d  mov     rbx, [rsp+88h+var_40]
0x14001b7a2  call    cs:__imp_KeLeaveCriticalRegion
0x14001b7a9  nop     dword ptr [rax+rax+00h]
0x14001b7ae  mov     [rsp+88h+var_48], 0
0x14001b7b3  test    esi, esi
0x14001b7b5  jns     short loc_14001B7F3
0x14001b7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b7be  cmp     rcx, r14
0x14001b7c1  jz      short loc_14001B7FE
0x14001b7c3  mov     eax, [rcx+2Ch]
0x14001b7c6  test    al, 8
0x14001b7c8  jz      short loc_14001B7FE
0x14001b7ca  cmp     byte ptr [rcx+29h], 2
0x14001b7ce  jb      short loc_14001B7FE
0x14001b7d0  mov     edx, 23h ; '#'
0x14001b7d5  mov     dword ptr [rsp+88h+var_60], esi
0x14001b7d9  mov     [rsp+88h+LazyWriteContext], r12
0x14001b7de  mov     r9, rbx
0x14001b7e1  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b7e8  mov     rcx, [rcx+18h]
0x14001b7ec  call    WPP_SF_qqd
0x14001b7f1  jmp     short loc_14001B7FE
0x14001b7f3  mov     [r13+0], rbx
0x14001b7f7  xor     ebx, ebx
0x14001b7f9  mov     [rsp+88h+var_40], rbx
0x14001b7fe  test    rbx, rbx
0x14001b801  jz      short loc_14001B80B
0x14001b803  mov     rcx, rbx; Object
0x14001b806  call    HsmFileCacheCloseFileObject
0x14001b80b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b812  cmp     rcx, r14
0x14001b815  jz      short loc_14001B842
0x14001b817  mov     edx, [rcx+2Ch]
0x14001b81a  test    dl, 8
0x14001b81d  jz      short loc_14001B842
0x14001b81f  cmp     byte ptr [rcx+29h], 5
0x14001b823  jb      short loc_14001B842
0x14001b825  mov     edx, 24h ; '$'
0x14001b82a  mov     dword ptr [rsp+88h+LazyWriteContext], esi
0x14001b82e  mov     r9, [r13+0]
0x14001b832  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b839  mov     rcx, [rcx+18h]
0x14001b83d  call    WPP_SF_qd
0x14001b842  mov     eax, esi
0x14001b844  add     rsp, 58h
0x14001b848  pop     r15
0x14001b84a  pop     r14
0x14001b84c  pop     r13
0x14001b84e  pop     r12
0x14001b850  pop     rsi
0x14001b851  pop     rbx
0x14001b852  retn
0x14001ed5a  push    rbp
0x14001ed5c  sub     rsp, 40h
0x14001ed60  mov     rbp, rdx
0x14001ed63  lea     rdx, [rbp+44h]
0x14001ed67  call    HsmFileCacheExceptionFilter
0x14001ed6c  nop
0x14001ed6d  add     rsp, 40h
0x14001ed71  pop     rbp
0x14001ed72  retn
0x14001ed74  push    rbp
0x14001ed76  sub     rsp, 40h
0x14001ed7a  mov     rbp, rdx
0x14001ed7d  lea     rdx, [rbp+44h]
0x14001ed81  call    HsmFileCacheExceptionFilter
0x14001ed86  nop
0x14001ed87  add     rsp, 40h
0x14001ed8b  pop     rbp
0x14001ed8c  retn
0x14001ed8e  push    rbp
0x14001ed90  sub     rsp, 40h
0x14001ed94  mov     rbp, rdx
0x14001ed97  cmp     byte ptr [rbp+40h], 0
0x14001ed9b  jz      short loc_14001EDAD
0x14001ed9d  call    cs:__imp_KeLeaveCriticalRegion
0x14001eda4  nop     dword ptr [rax+rax+00h]
0x14001eda9  mov     byte ptr [rbp+40h], 0
0x14001edad  mov     rcx, [rbp+48h]; Object
0x14001edb1  test    rcx, rcx
0x14001edb4  jz      short loc_14001EDBC
0x14001edb6  call    HsmFileCacheCloseFileObject
0x14001edbb  nop
0x14001edbc  add     rsp, 40h
0x14001edc0  pop     rbp
0x14001edc1  retn
```
