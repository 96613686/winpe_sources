# HsmFileCacheCreateFileObject

- ea: `0x14001b610`
- end: `0x14001b8d4`
- name: `HsmFileCacheCreateFileObject`
- size: `708`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, __int64, __int64, PFILE_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140070984`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x14000d95c`
- `0x14001b4ac`
- `0x14001b610`
- `0x14001b8dc`
- `0x14001bbf8`
- `0x14001cc48`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14001b693`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14001b693`
- `ntoskrnl!CcInitializeCacheMap` at `0x14001b7f4`
- `ntoskrnl!CcInitializeCacheMap` at `0x14001b7f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b822`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b822`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ee1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b7c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b7c9`

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
  int StreamControlBlock; // esi

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
  if ( StreamControlBlock >= 0 )
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
      (unsigned int)StreamControlBlock);
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
  return (unsigned int)StreamControlBlock;
}

```

## disassembly

```asm
0x14001b610  mov     rax, rsp
0x14001b613  mov     [rax+20h], r9
0x14001b617  mov     [rax+18h], r8
0x14001b61b  mov     [rax+10h], edx
0x14001b61e  mov     [rax+8], rcx
0x14001b622  push    rbx
0x14001b623  push    rsi
0x14001b624  push    r12
0x14001b626  push    r13
0x14001b628  push    r14
0x14001b62a  push    r15
0x14001b62c  sub     rsp, 58h
0x14001b630  mov     r12, r9
0x14001b633  mov     r15, r8
0x14001b636  xor     esi, esi
0x14001b638  mov     [rax-44h], esi
0x14001b63b  mov     [rax-40h], rsi
0x14001b63f  mov     [rax+38h], rsi
0x14001b643  mov     [rax-48h], sil
0x14001b647  lea     r14, WPP_GLOBAL_Control
0x14001b64e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b655  cmp     rcx, r14
0x14001b658  jz      short loc_14001B67E
0x14001b65a  mov     eax, [rcx+2Ch]
0x14001b65d  test    al, 8
0x14001b65f  jz      short loc_14001B67E
0x14001b661  cmp     byte ptr [rcx+29h], 5
0x14001b665  jb      short loc_14001B67E
0x14001b667  mov     [rsp+88h+var_58], r9
0x14001b66c  mov     [rsp+88h+var_60], r8
0x14001b671  mov     dword ptr [rsp+88h+LazyWriteContext], edx
0x14001b675  mov     rcx, [rcx+18h]
0x14001b679  call    WPP_SF_qDqic
0x14001b67e  mov     r13, [rsp+88h+arg_38]
0x14001b686  mov     [r13+0], rsi
0x14001b68a  mov     rdx, cs:DeviceObject; DeviceObject
0x14001b691  xor     ecx, ecx; FileObject
0x14001b693  call    cs:__imp_IoCreateStreamFileObjectLite
0x14001b69a  nop     dword ptr [rax+rax+00h]
0x14001b69f  mov     rbx, rax
0x14001b6a2  mov     [rsp+88h+var_40], rax
0x14001b6a7  jmp     short loc_14001B6D1
0x14001b6a9  lea     r14, WPP_GLOBAL_Control
0x14001b6b0  mov     r13, [rsp+88h+arg_38]
0x14001b6b8  mov     r12, [rsp+88h+arg_18]
0x14001b6c0  mov     r15, [rsp+88h+arg_10]
0x14001b6c8  mov     esi, [rsp+88h+var_44]
0x14001b6cc  mov     rbx, [rsp+88h+var_40]
0x14001b6d1  test    esi, esi
0x14001b6d3  jns     short loc_14001B71F
0x14001b6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6dc  cmp     rcx, r14
0x14001b6df  jz      loc_14001B87E
0x14001b6e5  mov     eax, [rcx+2Ch]
0x14001b6e8  test    al, 8
0x14001b6ea  jz      loc_14001B87E
0x14001b6f0  cmp     byte ptr [rcx+29h], 2
0x14001b6f4  jb      loc_14001B87E
0x14001b6fa  mov     edx, 21h ; '!'
0x14001b6ff  mov     dword ptr [rsp+88h+LazyWriteContext], esi
0x14001b703  mov     r9, cs:DeviceObject
0x14001b70a  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b711  mov     rcx, [rcx+18h]
0x14001b715  call    WPP_SF_qd
0x14001b71a  jmp     loc_14001B87E
0x14001b71f  lea     rax, [rsp+88h+arg_30]
0x14001b727  mov     [rsp+88h+var_58], rax
0x14001b72c  mov     rax, [rsp+88h+arg_28]
0x14001b734  mov     [rsp+88h+LazyWriteContext], rax
0x14001b739  mov     r9, r12
0x14001b73c  mov     r8, r15
0x14001b73f  mov     edx, [rsp+88h+arg_8]
0x14001b746  mov     rcx, [rsp+88h+arg_0]
0x14001b74e  call    HsmiFileCacheAllocateStreamControlBlock
0x14001b753  mov     esi, eax
0x14001b755  mov     [rsp+88h+var_44], eax
0x14001b759  mov     ecx, eax
0x14001b75b  call    HsmDbgBreakOnStatus
0x14001b760  test    esi, esi
0x14001b762  jns     short loc_14001B7A6
0x14001b764  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b76b  cmp     rcx, r14
0x14001b76e  jz      loc_14001B87E
0x14001b774  mov     eax, [rcx+2Ch]
0x14001b777  test    al, 8
0x14001b779  jz      loc_14001B87E
0x14001b77f  cmp     byte ptr [rcx+29h], 2
0x14001b783  jb      loc_14001B87E
0x14001b789  mov     edx, 22h ; '"'
0x14001b78e  mov     r9d, esi
0x14001b791  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b798  mov     rcx, [rcx+18h]
0x14001b79c  call    WPP_SF_d
0x14001b7a1  jmp     loc_14001B87E
0x14001b7a6  mov     r15, [rsp+88h+arg_30]
0x14001b7ae  mov     [rbx+18h], r15
0x14001b7b2  lea     rax, [r15+100h]
0x14001b7b9  mov     [rbx+28h], rax
0x14001b7bd  mov     word ptr [rbx+4Dh], 1
0x14001b7c3  mov     word ptr [rbx+4Ah], 101h
0x14001b7c9  call    cs:__imp_KeEnterCriticalRegion
0x14001b7d0  nop     dword ptr [rax+rax+00h]
0x14001b7d5  mov     [rsp+88h+var_48], 1
0x14001b7da  lea     rdx, [r15+18h]; FileSizes
0x14001b7de  mov     [rsp+88h+LazyWriteContext], 0; LazyWriteContext
0x14001b7e7  lea     r9, Callbacks; Callbacks
0x14001b7ee  mov     r8b, 1; PinAccess
0x14001b7f1  mov     rcx, rbx; FileObject
0x14001b7f4  call    cs:__imp_CcInitializeCacheMap
0x14001b7fb  nop     dword ptr [rax+rax+00h]
0x14001b800  jmp     short loc_14001B822
0x14001b802  lea     r14, WPP_GLOBAL_Control
0x14001b809  mov     r13, [rsp+88h+arg_38]
0x14001b811  mov     r12, [rsp+88h+arg_18]
0x14001b819  mov     esi, [rsp+88h+var_44]
0x14001b81d  mov     rbx, [rsp+88h+var_40]
0x14001b822  call    cs:__imp_KeLeaveCriticalRegion
0x14001b829  nop     dword ptr [rax+rax+00h]
0x14001b82e  mov     [rsp+88h+var_48], 0
0x14001b833  test    esi, esi
0x14001b835  jns     short loc_14001B873
0x14001b837  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b83e  cmp     rcx, r14
0x14001b841  jz      short loc_14001B87E
0x14001b843  mov     eax, [rcx+2Ch]
0x14001b846  test    al, 8
0x14001b848  jz      short loc_14001B87E
0x14001b84a  cmp     byte ptr [rcx+29h], 2
0x14001b84e  jb      short loc_14001B87E
0x14001b850  mov     edx, 23h ; '#'
0x14001b855  mov     dword ptr [rsp+88h+var_60], esi
0x14001b859  mov     [rsp+88h+LazyWriteContext], r12
0x14001b85e  mov     r9, rbx
0x14001b861  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b868  mov     rcx, [rcx+18h]
0x14001b86c  call    WPP_SF_qqd
0x14001b871  jmp     short loc_14001B87E
0x14001b873  mov     [r13+0], rbx
0x14001b877  xor     ebx, ebx
0x14001b879  mov     [rsp+88h+var_40], rbx
0x14001b87e  test    rbx, rbx
0x14001b881  jz      short loc_14001B88B
0x14001b883  mov     rcx, rbx; Object
0x14001b886  call    HsmFileCacheCloseFileObject
0x14001b88b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b892  cmp     rcx, r14
0x14001b895  jz      short loc_14001B8C2
0x14001b897  mov     edx, [rcx+2Ch]
0x14001b89a  test    dl, 8
0x14001b89d  jz      short loc_14001B8C2
0x14001b89f  cmp     byte ptr [rcx+29h], 5
0x14001b8a3  jb      short loc_14001B8C2
0x14001b8a5  mov     edx, 24h ; '$'
0x14001b8aa  mov     dword ptr [rsp+88h+LazyWriteContext], esi
0x14001b8ae  mov     r9, [r13+0]
0x14001b8b2  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b8b9  mov     rcx, [rcx+18h]
0x14001b8bd  call    WPP_SF_qd
0x14001b8c2  mov     eax, esi
0x14001b8c4  add     rsp, 58h
0x14001b8c8  pop     r15
0x14001b8ca  pop     r14
0x14001b8cc  pop     r13
0x14001b8ce  pop     r12
0x14001b8d0  pop     rsi
0x14001b8d1  pop     rbx
0x14001b8d2  retn
0x14001edda  push    rbp
0x14001eddc  sub     rsp, 40h
0x14001ede0  mov     rbp, rdx
0x14001ede3  lea     rdx, [rbp+44h]
0x14001ede7  call    HsmFileCacheExceptionFilter
0x14001edec  nop
0x14001eded  add     rsp, 40h
0x14001edf1  pop     rbp
0x14001edf2  retn
0x14001edf4  push    rbp
0x14001edf6  sub     rsp, 40h
0x14001edfa  mov     rbp, rdx
0x14001edfd  lea     rdx, [rbp+44h]
0x14001ee01  call    HsmFileCacheExceptionFilter
0x14001ee06  nop
0x14001ee07  add     rsp, 40h
0x14001ee0b  pop     rbp
0x14001ee0c  retn
0x14001ee0e  push    rbp
0x14001ee10  sub     rsp, 40h
0x14001ee14  mov     rbp, rdx
0x14001ee17  cmp     byte ptr [rbp+40h], 0
0x14001ee1b  jz      short loc_14001EE2D
0x14001ee1d  call    cs:__imp_KeLeaveCriticalRegion
0x14001ee24  nop     dword ptr [rax+rax+00h]
0x14001ee29  mov     byte ptr [rbp+40h], 0
0x14001ee2d  mov     rcx, [rbp+48h]; Object
0x14001ee31  test    rcx, rcx
0x14001ee34  jz      short loc_14001EE3C
0x14001ee36  call    HsmFileCacheCloseFileObject
0x14001ee3b  nop
0x14001ee3c  add     rsp, 40h
0x14001ee40  pop     rbp
0x14001ee41  retn
```
