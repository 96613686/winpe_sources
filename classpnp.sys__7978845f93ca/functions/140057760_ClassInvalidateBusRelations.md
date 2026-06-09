# ClassInvalidateBusRelations

- ea: `0x140057760`
- end: `0x140057814`
- name: `ClassInvalidateBusRelations`
- size: `180`
- prototype: `void __stdcall(PDEVICE_OBJECT Fdo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14001fbf4`
- `0x14003e470`
- `0x140057760`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005777c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005777c`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400577fc`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400577fc`

## pseudocode

```c
void __stdcall ClassInvalidateBusRelations(PDEVICE_OBJECT Fdo)
{
  void *DeviceExtension; // rbx
  __int64 (__fastcall **DriverObjectExtension)(PDEVICE_OBJECT); // rcx
  int v4; // eax

  DeviceExtension = Fdo->DeviceExtension;
  DriverObjectExtension = (__int64 (__fastcall **)(PDEVICE_OBJECT))IoGetDriverObjectExtension(
                                                                     Fdo->DriverObject,
                                                                     ClassInitialize);
  v4 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)DeviceExtension + 209) == 1 )
    v4 = DriverObjectExtension[46](Fdo);
  _InterlockedDecrement((volatile signed __int32 *)DeviceExtension + 209);
  if ( v4 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 179, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, (unsigned int)v4);
  }
  IoInvalidateDeviceRelations(*((PDEVICE_OBJECT *)DeviceExtension + 64), BusRelations);
}

```

## disassembly

```asm
0x140057760  mov     [rsp+arg_0], rbx
0x140057765  push    rdi
0x140057766  sub     rsp, 20h
0x14005776a  mov     rbx, [rcx+40h]
0x14005776e  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140057775  mov     rdi, rcx
0x140057778  mov     rcx, [rcx+8]; DriverObject
0x14005777c  call    cs:__imp_IoGetDriverObjectExtension
0x140057783  nop     dword ptr [rax+rax+00h]
0x140057788  mov     rcx, rax
0x14005778b  xor     eax, eax
0x14005778d  lea     edx, [rax+1]
0x140057790  lock xadd [rbx+344h], edx
0x140057798  inc     edx
0x14005779a  cmp     edx, 1
0x14005779d  jnz     short loc_1400577AE
0x14005779f  mov     rax, [rcx+170h]
0x1400577a6  mov     rcx, rdi
0x1400577a9  call    _guard_dispatch_icall
0x1400577ae  lock dec dword ptr [rbx+344h]
0x1400577b5  test    eax, eax
0x1400577b7  jns     short loc_1400577F3
0x1400577b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400577c0  lea     rdx, WPP_GLOBAL_Control
0x1400577c7  cmp     rcx, rdx
0x1400577ca  jz      short loc_1400577F3
0x1400577cc  test    dword ptr [rcx+2Ch], 4000h
0x1400577d3  jz      short loc_1400577F3
0x1400577d5  cmp     byte ptr [rcx+29h], 3
0x1400577d9  jb      short loc_1400577F3
0x1400577db  mov     rcx, [rcx+18h]
0x1400577df  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400577e6  mov     edx, 0B3h
0x1400577eb  mov     r9d, eax
0x1400577ee  call    WPP_SF_d
0x1400577f3  mov     rcx, [rbx+200h]; DeviceObject
0x1400577fa  xor     edx, edx; Type
0x1400577fc  call    cs:__imp_IoInvalidateDeviceRelations
0x140057803  nop     dword ptr [rax+rax+00h]
0x140057808  mov     rbx, [rsp+28h+arg_0]
0x14005780d  add     rsp, 20h
0x140057811  pop     rdi
0x140057812  retn
```
