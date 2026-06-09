# ACpCompleteStorageCancelled

- ea: `0x140020f9c`
- end: `0x140021077`
- name: `ACpCompleteStorageCancelled`
- size: `219`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020ca0`

## callees

- `0x140003d84`
- `0x140009adc`
- `0x14000a1d4`
- `0x140012754`
- `0x1400177c4`
- `0x140020f9c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140020fbd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020fbd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020fcd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020fcd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002104d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002104d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021059`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021059`

## pseudocode

```c
void __fastcall ACpCompleteStorageCancelled(struct _DEVICE_OBJECT *a1, unsigned int a2, __int64 a3, int a4)
{
  char *DeviceExtension; // rbx
  __int64 i; // rdi
  CTransaction **v10; // rax
  CQEntry *v11; // rsi

  DeviceExtension = (char *)a1->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v10 = (CTransaction **)CPacketHandleToCPacket(a1, *(struct CPacket **)(a3 + 8 * i));
    v11 = (CQEntry *)v10;
    if ( v10 )
    {
      CPacket::HandleStorageCompleted(v10, a4);
      CQEntry::ReleaseBuffer(v11);
      CBaseObject::Release(v11);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        16,
        &WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids,
        *(_QWORD *)(a3 + 8 * i));
    }
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140020f9c  push    rbx
0x140020f9e  push    rbp
0x140020f9f  push    rsi
0x140020fa0  push    rdi
0x140020fa1  push    r12
0x140020fa3  push    r13
0x140020fa5  push    r14
0x140020fa7  push    r15
0x140020fa9  sub     rsp, 28h
0x140020fad  mov     rbx, [rcx+40h]
0x140020fb1  mov     r12d, r9d
0x140020fb4  mov     r15, r8
0x140020fb7  mov     r14d, edx
0x140020fba  mov     r13, rcx
0x140020fbd  call    cs:__imp_KeEnterCriticalRegion
0x140020fc4  nop     dword ptr [rax+rax+00h]
0x140020fc9  lea     rcx, [rbx+8]; FastMutex
0x140020fcd  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140020fd4  nop     dword ptr [rax+rax+00h]
0x140020fd9  xor     edi, edi
0x140020fdb  test    r14d, r14d
0x140020fde  jz      short loc_140021049
0x140020fe0  mov     rdx, [r15+rdi*8]; struct CPacket *
0x140020fe4  mov     rcx, r13; struct _DEVICE_OBJECT *
0x140020fe7  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x140020fec  mov     rsi, rax
0x140020fef  test    rax, rax
0x140020ff2  jnz     short loc_140021027
0x140020ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ffb  lea     rax, WPP_GLOBAL_Control
0x140021002  cmp     rcx, rax
0x140021005  jz      short loc_140021042
0x140021007  mov     eax, [rcx+6Ch]
0x14002100a  test    al, 1
0x14002100c  jz      short loc_140021042
0x14002100e  mov     r9, [r15+rdi*8]
0x140021012  lea     edx, [rsi+10h]
0x140021015  mov     rcx, [rcx+58h]
0x140021019  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x140021020  call    WPP_SF_q
0x140021025  jmp     short loc_140021042
0x140021027  mov     edx, r12d; int
0x14002102a  mov     rcx, rsi; this
0x14002102d  call    ?HandleStorageCompleted@CPacket@@QEAAXJ@Z; CPacket::HandleStorageCompleted(long)
0x140021032  mov     rcx, rsi; this
0x140021035  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x14002103a  mov     rcx, rsi; this
0x14002103d  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140021042  inc     edi
0x140021044  cmp     edi, r14d
0x140021047  jb      short loc_140020FE0
0x140021049  lea     rcx, [rbx+8]; FastMutex
0x14002104d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140021054  nop     dword ptr [rax+rax+00h]
0x140021059  call    cs:__imp_KeLeaveCriticalRegion
0x140021060  nop     dword ptr [rax+rax+00h]
0x140021065  add     rsp, 28h
0x140021069  pop     r15
0x14002106b  pop     r14
0x14002106d  pop     r13
0x14002106f  pop     r12
0x140021071  pop     rdi
0x140021072  pop     rsi
0x140021073  pop     rbp
0x140021074  pop     rbx
0x140021075  retn
```
