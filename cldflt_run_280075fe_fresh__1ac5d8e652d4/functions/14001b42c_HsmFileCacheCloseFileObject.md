# HsmFileCacheCloseFileObject

- ea: `0x14001b42c`
- end: `0x14001b587`
- name: `HsmFileCacheCloseFileObject`
- size: `347`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14001b590`
- `0x14006b7ec`
- `0x140070864`
- `0x14007f7e8`

## callees

- `0x14000dee4`
- `0x1400105c4`
- `0x14001b42c`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x14001b503`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14001b503`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001b4b8`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001b4b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b510`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b510`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b4a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b4a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b532`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b532`
- `ntoskrnl!KeInitializeEvent` at `0x14001b493`
- `ntoskrnl!KeInitializeEvent` at `0x14001b493`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b541`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b541`

## pseudocode

```c
LONG_PTR __fastcall HsmFileCacheCloseFileObject(struct _FILE_OBJECT *Object)
{
  LONG_PTR result; // rax
  struct _CACHE_UNINITIALIZE_EVENT Event; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, Object);
  }
  if ( Object->FsContext )
  {
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event.Event, NotificationEvent, 0);
    KeEnterCriticalRegion();
    if ( !CcPurgeCacheSection(Object->SectionObjectPointer, 0, 0, 0)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, Object);
    }
    CcUninitializeCacheMap(Object, 0, &Event);
    KeLeaveCriticalRegion();
    KeWaitForSingleObject(&Event.Event, Executive, 0, 0, 0);
  }
  result = ObfDereferenceObject(Object);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14001b42c  mov     [rsp+arg_8], rbx
0x14001b431  push    rdi
0x14001b432  sub     rsp, 50h
0x14001b436  mov     rbx, rcx
0x14001b439  lea     rdi, WPP_GLOBAL_Control
0x14001b440  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b447  cmp     rcx, rdi
0x14001b44a  jz      short loc_14001B471
0x14001b44c  mov     eax, [rcx+2Ch]
0x14001b44f  test    al, 8
0x14001b451  jz      short loc_14001B471
0x14001b453  cmp     byte ptr [rcx+29h], 5
0x14001b457  jb      short loc_14001B471
0x14001b459  mov     edx, 25h ; '%'
0x14001b45e  mov     r9, rbx
0x14001b461  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b468  mov     rcx, [rcx+18h]
0x14001b46c  call    WPP_SF_q
0x14001b471  cmp     qword ptr [rbx+18h], 0
0x14001b476  jz      loc_14001B53E
0x14001b47c  xorps   xmm0, xmm0
0x14001b47f  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14001b484  movups  xmmword ptr [rsp+58h+Event.Header.WaitListHead.Blink], xmm0
0x14001b489  xor     r8d, r8d; State
0x14001b48c  xor     edx, edx; Type
0x14001b48e  lea     rcx, [rsp+58h+Event.Header.WaitListHead]; Event
0x14001b493  call    cs:__imp_KeInitializeEvent
0x14001b49a  nop     dword ptr [rax+rax+00h]
0x14001b49f  nop
0x14001b4a0  call    cs:__imp_KeEnterCriticalRegion
0x14001b4a7  nop     dword ptr [rax+rax+00h]
0x14001b4ac  xor     r9d, r9d; Flags
0x14001b4af  xor     r8d, r8d; Length
0x14001b4b2  xor     edx, edx; FileOffset
0x14001b4b4  mov     rcx, [rbx+28h]; SectionObjectPointer
0x14001b4b8  call    cs:__imp_CcPurgeCacheSection
0x14001b4bf  nop     dword ptr [rax+rax+00h]
0x14001b4c4  test    al, al
0x14001b4c6  jnz     short loc_14001B4F9
0x14001b4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4cf  cmp     rcx, rdi
0x14001b4d2  jz      short loc_14001B4F9
0x14001b4d4  mov     eax, [rcx+2Ch]
0x14001b4d7  test    al, 8
0x14001b4d9  jz      short loc_14001B4F9
0x14001b4db  cmp     byte ptr [rcx+29h], 3
0x14001b4df  jb      short loc_14001B4F9
0x14001b4e1  mov     edx, 26h ; '&'
0x14001b4e6  mov     r9, rbx
0x14001b4e9  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b4f0  mov     rcx, [rcx+18h]
0x14001b4f4  call    WPP_SF_q
0x14001b4f9  lea     r8, [rsp+58h+Event]; UninitializeEvent
0x14001b4fe  xor     edx, edx; TruncateSize
0x14001b500  mov     rcx, rbx; FileObject
0x14001b503  call    cs:__imp_CcUninitializeCacheMap
0x14001b50a  nop     dword ptr [rax+rax+00h]
0x14001b50f  nop
0x14001b510  call    cs:__imp_KeLeaveCriticalRegion
0x14001b517  nop     dword ptr [rax+rax+00h]
0x14001b51c  mov     [rsp+58h+Timeout], 0; Timeout
0x14001b525  xor     r9d, r9d; Alertable
0x14001b528  xor     r8d, r8d; WaitMode
0x14001b52b  xor     edx, edx; WaitReason
0x14001b52d  lea     rcx, [rsp+58h+Event.Header.WaitListHead]; Object
0x14001b532  call    cs:__imp_KeWaitForSingleObject
0x14001b539  nop     dword ptr [rax+rax+00h]
0x14001b53e  mov     rcx, rbx; Object
0x14001b541  call    cs:__imp_ObfDereferenceObject
0x14001b548  nop     dword ptr [rax+rax+00h]
0x14001b54d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b554  cmp     rcx, rdi
0x14001b557  jz      short loc_14001B57B
0x14001b559  mov     eax, [rcx+2Ch]
0x14001b55c  test    al, 8
0x14001b55e  jz      short loc_14001B57B
0x14001b560  cmp     byte ptr [rcx+29h], 5
0x14001b564  jb      short loc_14001B57B
0x14001b566  mov     edx, 27h ; '''
0x14001b56b  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b572  mov     rcx, [rcx+18h]
0x14001b576  call    WPP_SF_
0x14001b57b  mov     rbx, [rsp+58h+arg_8]
0x14001b580  add     rsp, 50h
0x14001b584  pop     rdi
0x14001b585  retn
0x14001ed37  push    rbp
0x14001ed39  sub     rsp, 30h
0x14001ed3d  mov     rbp, rdx
0x14001ed40  call    cs:__imp_KeLeaveCriticalRegion
0x14001ed47  nop     dword ptr [rax+rax+00h]
0x14001ed4c  nop
0x14001ed4d  add     rsp, 30h
0x14001ed51  pop     rbp
0x14001ed52  retn
```
