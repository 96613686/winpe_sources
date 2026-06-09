# HsmFileCacheCloseFileObject

- ea: `0x14001b4ac`
- end: `0x14001b607`
- name: `HsmFileCacheCloseFileObject`
- size: `347`
- prototype: `LONG_PTR __fastcall(struct _FILE_OBJECT *Object)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14001b610`
- `0x14006b90c`
- `0x140070984`
- `0x14007f980`

## callees

- `0x14000dee4`
- `0x140010644`
- `0x14001b4ac`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x14001b583`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14001b583`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001b538`
- `ntoskrnl!CcPurgeCacheSection` at `0x14001b538`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b590`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001edc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b590`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001edc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b520`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b520`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b5b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b5b2`
- `ntoskrnl!KeInitializeEvent` at `0x14001b513`
- `ntoskrnl!KeInitializeEvent` at `0x14001b513`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5c1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5c1`

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
0x14001b4ac  mov     [rsp+arg_8], rbx
0x14001b4b1  push    rdi
0x14001b4b2  sub     rsp, 50h
0x14001b4b6  mov     rbx, rcx
0x14001b4b9  lea     rdi, WPP_GLOBAL_Control
0x14001b4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4c7  cmp     rcx, rdi
0x14001b4ca  jz      short loc_14001B4F1
0x14001b4cc  mov     eax, [rcx+2Ch]
0x14001b4cf  test    al, 8
0x14001b4d1  jz      short loc_14001B4F1
0x14001b4d3  cmp     byte ptr [rcx+29h], 5
0x14001b4d7  jb      short loc_14001B4F1
0x14001b4d9  mov     edx, 25h ; '%'
0x14001b4de  mov     r9, rbx
0x14001b4e1  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b4e8  mov     rcx, [rcx+18h]
0x14001b4ec  call    WPP_SF_q
0x14001b4f1  cmp     qword ptr [rbx+18h], 0
0x14001b4f6  jz      loc_14001B5BE
0x14001b4fc  xorps   xmm0, xmm0
0x14001b4ff  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14001b504  movups  xmmword ptr [rsp+58h+Event.Header.WaitListHead.Blink], xmm0
0x14001b509  xor     r8d, r8d; State
0x14001b50c  xor     edx, edx; Type
0x14001b50e  lea     rcx, [rsp+58h+Event.Header.WaitListHead]; Event
0x14001b513  call    cs:__imp_KeInitializeEvent
0x14001b51a  nop     dword ptr [rax+rax+00h]
0x14001b51f  nop
0x14001b520  call    cs:__imp_KeEnterCriticalRegion
0x14001b527  nop     dword ptr [rax+rax+00h]
0x14001b52c  xor     r9d, r9d; Flags
0x14001b52f  xor     r8d, r8d; Length
0x14001b532  xor     edx, edx; FileOffset
0x14001b534  mov     rcx, [rbx+28h]; SectionObjectPointer
0x14001b538  call    cs:__imp_CcPurgeCacheSection
0x14001b53f  nop     dword ptr [rax+rax+00h]
0x14001b544  test    al, al
0x14001b546  jnz     short loc_14001B579
0x14001b548  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b54f  cmp     rcx, rdi
0x14001b552  jz      short loc_14001B579
0x14001b554  mov     eax, [rcx+2Ch]
0x14001b557  test    al, 8
0x14001b559  jz      short loc_14001B579
0x14001b55b  cmp     byte ptr [rcx+29h], 3
0x14001b55f  jb      short loc_14001B579
0x14001b561  mov     edx, 26h ; '&'
0x14001b566  mov     r9, rbx
0x14001b569  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b570  mov     rcx, [rcx+18h]
0x14001b574  call    WPP_SF_q
0x14001b579  lea     r8, [rsp+58h+Event]; UninitializeEvent
0x14001b57e  xor     edx, edx; TruncateSize
0x14001b580  mov     rcx, rbx; FileObject
0x14001b583  call    cs:__imp_CcUninitializeCacheMap
0x14001b58a  nop     dword ptr [rax+rax+00h]
0x14001b58f  nop
0x14001b590  call    cs:__imp_KeLeaveCriticalRegion
0x14001b597  nop     dword ptr [rax+rax+00h]
0x14001b59c  mov     [rsp+58h+Timeout], 0; Timeout
0x14001b5a5  xor     r9d, r9d; Alertable
0x14001b5a8  xor     r8d, r8d; WaitMode
0x14001b5ab  xor     edx, edx; WaitReason
0x14001b5ad  lea     rcx, [rsp+58h+Event.Header.WaitListHead]; Object
0x14001b5b2  call    cs:__imp_KeWaitForSingleObject
0x14001b5b9  nop     dword ptr [rax+rax+00h]
0x14001b5be  mov     rcx, rbx; Object
0x14001b5c1  call    cs:__imp_ObfDereferenceObject
0x14001b5c8  nop     dword ptr [rax+rax+00h]
0x14001b5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5d4  cmp     rcx, rdi
0x14001b5d7  jz      short loc_14001B5FB
0x14001b5d9  mov     eax, [rcx+2Ch]
0x14001b5dc  test    al, 8
0x14001b5de  jz      short loc_14001B5FB
0x14001b5e0  cmp     byte ptr [rcx+29h], 5
0x14001b5e4  jb      short loc_14001B5FB
0x14001b5e6  mov     edx, 27h ; '''
0x14001b5eb  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b5f2  mov     rcx, [rcx+18h]
0x14001b5f6  call    WPP_SF_
0x14001b5fb  mov     rbx, [rsp+58h+arg_8]
0x14001b600  add     rsp, 50h
0x14001b604  pop     rdi
0x14001b605  retn
0x14001edb7  push    rbp
0x14001edb9  sub     rsp, 30h
0x14001edbd  mov     rbp, rdx
0x14001edc0  call    cs:__imp_KeLeaveCriticalRegion
0x14001edc7  nop     dword ptr [rax+rax+00h]
0x14001edcc  nop
0x14001edcd  add     rsp, 30h
0x14001edd1  pop     rbp
0x14001edd2  retn
```
