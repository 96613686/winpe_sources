# ReadNodeNameValue

- ea: `0x18004ce70`
- end: `0x18004d109`
- name: `ReadNodeNameValue`
- size: `665`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18004bc10`
- `0x18004bf20`
- `0x18004c3c0`

## callees

- `0x1800074e0`
- `0x18000a660`
- `0x18000c630`
- `0x18004ce70`
- `0x18004d110`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18004cf22`
- `ntoskrnl!ObfDereferenceObject` at `0x18004d0b1`
- `ntoskrnl!ObfDereferenceObject` at `0x18004cf22`
- `ntoskrnl!ObfDereferenceObject` at `0x18004d0b1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004cee1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004cee1`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18004cea6`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18004cea6`
- `ntoskrnl!ZwClose` at `0x18004cf13`
- `ntoskrnl!ZwClose` at `0x18004cf13`

## pseudocode

```c
__int64 __fastcall ReadNodeNameValue(__int64 a1, __int64 a2, const wchar_t *a3)
{
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  PDEVICE_OBJECT v7; // rdi
  NTSTATUS DeviceNodeNameValue; // ebx
  int v9; // edx
  int v11; // [rsp+20h] [rbp-88h]
  void *DeviceRegKey; // [rsp+B0h] [rbp+8h] BYREF

  DeviceRegKey = 0;
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 184) + 40LL));
  v7 = DeviceAttachmentBaseRef;
  if ( !DeviceAttachmentBaseRef )
    goto LABEL_7;
  if ( (DeviceAttachmentBaseRef->Flags & 0x1000) == 0 )
  {
    ObfDereferenceObject(DeviceAttachmentBaseRef);
LABEL_7:
    DeviceNodeNameValue = ReadDeviceNodeNameValue(a1, a2, 0, a3);
    goto LABEL_8;
  }
  DeviceNodeNameValue = IoOpenDeviceRegistryKey(DeviceAttachmentBaseRef, 2u, 0x20019u, &DeviceRegKey);
  if ( DeviceNodeNameValue >= 0 )
  {
    DeviceNodeNameValue = ReadDeviceNodeNameValue(a1, a2, DeviceRegKey, a3);
    ZwClose(DeviceRegKey);
  }
  ObfDereferenceObject(v7);
  if ( DeviceNodeNameValue == -1073741772 || DeviceNodeNameValue == -1073740951 )
    goto LABEL_7;
LABEL_8:
  if ( DeviceNodeNameValue < 0 )
  {
    if ( a2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_DDDDDDDDDDDD(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          *(unsigned __int8 *)(a2 + 13),
          *(unsigned __int8 *)(a2 + 12),
          *(unsigned __int8 *)(a2 + 11),
          v11);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        12,
        (__int64)WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids,
        DeviceNodeNameValue);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_DDDDDDDDDDDS(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      *(unsigned __int8 *)(a2 + 13),
      *(unsigned __int8 *)(a2 + 12),
      *(unsigned __int8 *)(a2 + 11),
      v11,
      *(_DWORD *)a2,
      *(_WORD *)(a2 + 4),
      *(_WORD *)(a2 + 6),
      *(_BYTE *)(a2 + 8),
      *(_BYTE *)(a2 + 9),
      *(_BYTE *)(a2 + 10),
      *(_BYTE *)(a2 + 11),
      *(_BYTE *)(a2 + 12),
      *(_BYTE *)(a2 + 13),
      *(_BYTE *)(a2 + 14),
      *(_BYTE *)(a2 + 15),
      a3);
  }
  return (unsigned int)DeviceNodeNameValue;
}

```

## disassembly

```asm
0x18004ce70  mov     [rsp+arg_10], rbx
0x18004ce75  mov     [rsp+arg_18], rsi
0x18004ce7a  push    rdi
0x18004ce7b  push    r14
0x18004ce7d  push    r15
0x18004ce7f  sub     rsp, 90h
0x18004ce86  mov     rsi, rcx
0x18004ce89  mov     [rsp+0A8h+DeviceRegKey], 0
0x18004ce95  mov     rcx, [rcx+0B8h]
0x18004ce9c  mov     r15, r8
0x18004ce9f  mov     r14, rdx
0x18004cea2  mov     rcx, [rcx+28h]; DeviceObject
0x18004cea6  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x18004cead  nop     dword ptr [rax+rax+00h]
0x18004ceb2  mov     rdi, rax
0x18004ceb5  test    rax, rax
0x18004ceb8  jz      loc_18004CF3E
0x18004cebe  test    dword ptr [rax+30h], 1000h
0x18004cec5  mov     rcx, rax; Object
0x18004cec8  jz      loc_18004D0B1
0x18004cece  lea     r9, [rsp+0A8h+DeviceRegKey]; DeviceRegKey
0x18004ced6  mov     edx, 2; DevInstKeyType
0x18004cedb  mov     r8d, 20019h; DesiredAccess
0x18004cee1  call    cs:__imp_IoOpenDeviceRegistryKey
0x18004cee8  nop     dword ptr [rax+rax+00h]
0x18004ceed  mov     ebx, eax
0x18004ceef  test    eax, eax
0x18004cef1  js      short loc_18004CF1F
0x18004cef3  mov     r8, [rsp+0A8h+DeviceRegKey]
0x18004cefb  mov     r9, r15
0x18004cefe  mov     rdx, r14
0x18004cf01  mov     rcx, rsi
0x18004cf04  call    ReadDeviceNodeNameValue
0x18004cf09  mov     rcx, [rsp+0A8h+DeviceRegKey]; Handle
0x18004cf11  mov     ebx, eax
0x18004cf13  call    cs:__imp_ZwClose
0x18004cf1a  nop     dword ptr [rax+rax+00h]
0x18004cf1f  mov     rcx, rdi; Object
0x18004cf22  call    cs:__imp_ObfDereferenceObject
0x18004cf29  nop     dword ptr [rax+rax+00h]
0x18004cf2e  cmp     ebx, 0C0000034h
0x18004cf34  jz      short loc_18004CF3E
0x18004cf36  cmp     ebx, 0C0000369h
0x18004cf3c  jnz     short loc_18004CF51
0x18004cf3e  mov     r9, r15
0x18004cf41  xor     r8d, r8d
0x18004cf44  mov     rdx, r14
0x18004cf47  mov     rcx, rsi
0x18004cf4a  call    ReadDeviceNodeNameValue
0x18004cf4f  mov     ebx, eax
0x18004cf51  mov     [rsp+0A8h+arg_8], rbp
0x18004cf59  test    ebx, ebx
0x18004cf5b  js      short loc_18004CF95
0x18004cf5d  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cf64  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cf6b  jnz     loc_18004D02F
0x18004cf71  mov     rbp, [rsp+0A8h+arg_8]
0x18004cf79  lea     r11, [rsp+0A8h+var_18]
0x18004cf81  mov     rsi, [r11+38h]
0x18004cf85  mov     eax, ebx
0x18004cf87  mov     rbx, [r11+30h]
0x18004cf8b  mov     rsp, r11
0x18004cf8e  pop     r15
0x18004cf90  pop     r14
0x18004cf92  pop     rdi
0x18004cf93  retn
0x18004cf95  test    r14, r14
0x18004cf98  jz      loc_18004D0C2
0x18004cf9e  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cfa5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cfac  jz      short loc_18004CF71
0x18004cfae  movzx   eax, byte ptr [r14+0Fh]
0x18004cfb3  movzx   ecx, byte ptr [r14+0Eh]
0x18004cfb8  movzx   edx, byte ptr [r14+0Dh]
0x18004cfbd  movzx   r8d, byte ptr [r14+0Ch]
0x18004cfc2  movzx   r9d, byte ptr [r14+0Bh]
0x18004cfc7  movzx   r10d, byte ptr [r14+0Ah]
0x18004cfcc  movzx   r11d, byte ptr [r14+9]
0x18004cfd1  movzx   edi, byte ptr [r14+8]
0x18004cfd6  movzx   esi, word ptr [r14+6]
0x18004cfdb  movzx   ebp, word ptr [r14+4]
0x18004cfe0  mov     dword ptr [rsp+0A8h+var_28], ebx
0x18004cfe7  mov     [rsp+0A8h+var_30], eax
0x18004cfeb  mov     eax, [r14]
0x18004cfee  mov     [rsp+0A8h+var_38], ecx
0x18004cff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cff9  mov     [rsp+0A8h+var_40], edx
0x18004cffd  mov     [rsp+0A8h+var_48], r8d
0x18004d002  mov     [rsp+0A8h+var_50], r9d
0x18004d007  mov     rcx, [rcx+40h]
0x18004d00b  mov     [rsp+0A8h+var_58], r10d
0x18004d010  mov     [rsp+0A8h+var_60], r11d
0x18004d015  mov     [rsp+0A8h+var_68], edi
0x18004d019  mov     [rsp+0A8h+var_70], esi
0x18004d01d  mov     [rsp+0A8h+var_78], ebp
0x18004d021  mov     [rsp+0A8h+var_80], eax
0x18004d025  call    WPP_RECORDER_SF_DDDDDDDDDDDD
0x18004d02a  jmp     loc_18004CF71
0x18004d02f  movzx   eax, byte ptr [r14+0Fh]
0x18004d034  movzx   ecx, byte ptr [r14+0Eh]
0x18004d039  movzx   edx, byte ptr [r14+0Dh]
0x18004d03e  movzx   r8d, byte ptr [r14+0Ch]
0x18004d043  movzx   r9d, byte ptr [r14+0Bh]
0x18004d048  movzx   r10d, byte ptr [r14+0Ah]
0x18004d04d  movzx   r11d, byte ptr [r14+9]
0x18004d052  movzx   edi, byte ptr [r14+8]
0x18004d057  movzx   esi, word ptr [r14+6]
0x18004d05c  movzx   ebp, word ptr [r14+4]
0x18004d061  mov     [rsp+0A8h+var_28], r15
0x18004d069  mov     [rsp+0A8h+var_30], eax
0x18004d06d  mov     eax, [r14]
0x18004d070  mov     [rsp+0A8h+var_38], ecx
0x18004d074  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d07b  mov     [rsp+0A8h+var_40], edx
0x18004d07f  mov     [rsp+0A8h+var_48], r8d
0x18004d084  mov     [rsp+0A8h+var_50], r9d
0x18004d089  mov     rcx, [rcx+40h]
0x18004d08d  mov     [rsp+0A8h+var_58], r10d
0x18004d092  mov     [rsp+0A8h+var_60], r11d
0x18004d097  mov     [rsp+0A8h+var_68], edi
0x18004d09b  mov     [rsp+0A8h+var_70], esi
0x18004d09f  mov     [rsp+0A8h+var_78], ebp
0x18004d0a3  mov     [rsp+0A8h+var_80], eax
0x18004d0a7  call    WPP_RECORDER_SF_DDDDDDDDDDDS
0x18004d0ac  jmp     loc_18004CF71
0x18004d0b1  call    cs:__imp_ObfDereferenceObject
0x18004d0b8  nop     dword ptr [rax+rax+00h]
0x18004d0bd  jmp     loc_18004CF3E
0x18004d0c2  lea     rax, WPP_RECORDER_INITIALIZED
0x18004d0c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004d0d0  jz      loc_18004CF71
0x18004d0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0dd  lea     rax, WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids
0x18004d0e4  mov     r9d, 0Ch
0x18004d0ea  mov     [rsp+0A8h+var_80], ebx
0x18004d0ee  mov     r8d, 1
0x18004d0f4  mov     [rsp+0A8h+var_88], rax
0x18004d0f9  mov     dl, 2
0x18004d0fb  mov     rcx, [rcx+40h]
0x18004d0ff  call    WPP_RECORDER_SF_D
0x18004d104  jmp     loc_18004CF71
```
