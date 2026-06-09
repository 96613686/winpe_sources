# ClassSendEjectionNotification

- ea: `0x140021ba4`
- end: `0x140021c00`
- name: `ClassSendEjectionNotification`
- size: `92`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400084b0`
- `0x140021c78`

## callees

- `0x140019020`
- `0x14001feac`
- `0x140021ba4`

## pseudocode

```c
void __fastcall ClassSendEjectionNotification(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  ClassSendNotification(FdoExtension, &GUID_IO_MEDIA_EJECT_REQUEST, 0, 0);
}

```

## disassembly

```asm
0x140021ba4  push    rbx
0x140021ba6  sub     rsp, 20h
0x140021baa  mov     rbx, rcx
0x140021bad  mov     rcx, cs:WPP_GLOBAL_Control
0x140021bb4  lea     rax, WPP_GLOBAL_Control
0x140021bbb  cmp     rcx, rax
0x140021bbe  jz      short loc_140021BE4
0x140021bc0  test    dword ptr [rcx+2Ch], 1000h
0x140021bc7  jz      short loc_140021BE4
0x140021bc9  cmp     byte ptr [rcx+29h], 4
0x140021bcd  jb      short loc_140021BE4
0x140021bcf  mov     rcx, [rcx+18h]
0x140021bd3  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021bda  mov     edx, 0Ah
0x140021bdf  call    WPP_SF_
0x140021be4  xor     r9d, r9d; ExtraData
0x140021be7  lea     rdx, GUID_IO_MEDIA_EJECT_REQUEST; Guid
0x140021bee  xor     r8d, r8d; ExtraDataSize
0x140021bf1  mov     rcx, rbx; FdoExtension
0x140021bf4  call    ClassSendNotification
0x140021bf9  add     rsp, 20h
0x140021bfd  pop     rbx
0x140021bfe  retn
```
