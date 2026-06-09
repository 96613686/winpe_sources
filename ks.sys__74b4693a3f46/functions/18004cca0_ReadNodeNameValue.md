# ReadNodeNameValue

- ea: `0x18004cca0`
- end: `0x18004cf39`
- name: `ReadNodeNameValue`
- size: `665`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18004ba40`
- `0x18004bd50`
- `0x18004c1f0`

## callees

- `0x1800074e0`
- `0x18000a660`
- `0x18000c630`
- `0x18004cca0`
- `0x18004cf40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18004cd52`
- `ntoskrnl!ObfDereferenceObject` at `0x18004cee1`
- `ntoskrnl!ObfDereferenceObject` at `0x18004cd52`
- `ntoskrnl!ObfDereferenceObject` at `0x18004cee1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004cd11`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004cd11`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18004ccd6`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18004ccd6`
- `ntoskrnl!ZwClose` at `0x18004cd43`
- `ntoskrnl!ZwClose` at `0x18004cd43`

## pseudocode

```c
__int64 __fastcall ReadNodeNameValue(__int64 a1, const GUID *a2, void *a3)
{
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  PDEVICE_OBJECT v7; // rdi
  NTSTATUS DeviceNodeNameValue; // ebx
  int v9; // edx
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
        WPP_RECORDER_SF_DDDDDDDDDDDD(WPP_GLOBAL_Control->DeviceExtension, a2->Data4[5], a2->Data4[4], a2->Data4[3]);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        12,
        (__int64)WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids,
        DeviceNodeNameValue);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_DDDDDDDDDDDS(WPP_GLOBAL_Control->DeviceExtension, a2->Data4[5], a2->Data4[4], a2->Data4[3]);
  }
  return (unsigned int)DeviceNodeNameValue;
}

```

## disassembly

```asm
0x18004cca0  mov     [rsp+arg_10], rbx
0x18004cca5  mov     [rsp+arg_18], rsi
0x18004ccaa  push    rdi
0x18004ccab  push    r14
0x18004ccad  push    r15
0x18004ccaf  sub     rsp, 90h
0x18004ccb6  mov     rsi, rcx
0x18004ccb9  mov     [rsp+0A8h+DeviceRegKey], 0
0x18004ccc5  mov     rcx, [rcx+0B8h]
0x18004cccc  mov     r15, r8
0x18004cccf  mov     r14, rdx
0x18004ccd2  mov     rcx, [rcx+28h]; DeviceObject
0x18004ccd6  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x18004ccdd  nop     dword ptr [rax+rax+00h]
0x18004cce2  mov     rdi, rax
0x18004cce5  test    rax, rax
0x18004cce8  jz      loc_18004CD6E
0x18004ccee  test    dword ptr [rax+30h], 1000h
0x18004ccf5  mov     rcx, rax; Object
0x18004ccf8  jz      loc_18004CEE1
0x18004ccfe  lea     r9, [rsp+0A8h+DeviceRegKey]; DeviceRegKey
0x18004cd06  mov     edx, 2; DevInstKeyType
0x18004cd0b  mov     r8d, 20019h; DesiredAccess
0x18004cd11  call    cs:__imp_IoOpenDeviceRegistryKey
0x18004cd18  nop     dword ptr [rax+rax+00h]
0x18004cd1d  mov     ebx, eax
0x18004cd1f  test    eax, eax
0x18004cd21  js      short loc_18004CD4F
0x18004cd23  mov     r8, [rsp+0A8h+DeviceRegKey]
0x18004cd2b  mov     r9, r15
0x18004cd2e  mov     rdx, r14
0x18004cd31  mov     rcx, rsi
0x18004cd34  call    ReadDeviceNodeNameValue
0x18004cd39  mov     rcx, [rsp+0A8h+DeviceRegKey]; Handle
0x18004cd41  mov     ebx, eax
0x18004cd43  call    cs:__imp_ZwClose
0x18004cd4a  nop     dword ptr [rax+rax+00h]
0x18004cd4f  mov     rcx, rdi; Object
0x18004cd52  call    cs:__imp_ObfDereferenceObject
0x18004cd59  nop     dword ptr [rax+rax+00h]
0x18004cd5e  cmp     ebx, 0C0000034h
0x18004cd64  jz      short loc_18004CD6E
0x18004cd66  cmp     ebx, 0C0000369h
0x18004cd6c  jnz     short loc_18004CD81
0x18004cd6e  mov     r9, r15
0x18004cd71  xor     r8d, r8d
0x18004cd74  mov     rdx, r14
0x18004cd77  mov     rcx, rsi
0x18004cd7a  call    ReadDeviceNodeNameValue
0x18004cd7f  mov     ebx, eax
0x18004cd81  mov     [rsp+0A8h+arg_8], rbp
0x18004cd89  test    ebx, ebx
0x18004cd8b  js      short loc_18004CDC5
0x18004cd8d  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cd94  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cd9b  jnz     loc_18004CE5F
0x18004cda1  mov     rbp, [rsp+0A8h+arg_8]
0x18004cda9  lea     r11, [rsp+0A8h+var_18]
0x18004cdb1  mov     rsi, [r11+38h]
0x18004cdb5  mov     eax, ebx
0x18004cdb7  mov     rbx, [r11+30h]
0x18004cdbb  mov     rsp, r11
0x18004cdbe  pop     r15
0x18004cdc0  pop     r14
0x18004cdc2  pop     rdi
0x18004cdc3  retn
0x18004cdc5  test    r14, r14
0x18004cdc8  jz      loc_18004CEF2
0x18004cdce  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cdd5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cddc  jz      short loc_18004CDA1
0x18004cdde  movzx   eax, byte ptr [r14+0Fh]
0x18004cde3  movzx   ecx, byte ptr [r14+0Eh]
0x18004cde8  movzx   edx, byte ptr [r14+0Dh]
0x18004cded  movzx   r8d, byte ptr [r14+0Ch]
0x18004cdf2  movzx   r9d, byte ptr [r14+0Bh]
0x18004cdf7  movzx   r10d, byte ptr [r14+0Ah]
0x18004cdfc  movzx   r11d, byte ptr [r14+9]
0x18004ce01  movzx   edi, byte ptr [r14+8]
0x18004ce06  movzx   esi, word ptr [r14+6]
0x18004ce0b  movzx   ebp, word ptr [r14+4]
0x18004ce10  mov     dword ptr [rsp+0A8h+var_28], ebx
0x18004ce17  mov     [rsp+0A8h+var_30], eax
0x18004ce1b  mov     eax, [r14]
0x18004ce1e  mov     [rsp+0A8h+var_38], ecx
0x18004ce22  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce29  mov     [rsp+0A8h+var_40], edx
0x18004ce2d  mov     [rsp+0A8h+var_48], r8d
0x18004ce32  mov     [rsp+0A8h+var_50], r9d
0x18004ce37  mov     rcx, [rcx+40h]
0x18004ce3b  mov     [rsp+0A8h+var_58], r10d
0x18004ce40  mov     [rsp+0A8h+var_60], r11d
0x18004ce45  mov     [rsp+0A8h+var_68], edi
0x18004ce49  mov     [rsp+0A8h+var_70], esi
0x18004ce4d  mov     [rsp+0A8h+var_78], ebp
0x18004ce51  mov     [rsp+0A8h+var_80], eax
0x18004ce55  call    WPP_RECORDER_SF_DDDDDDDDDDDD
0x18004ce5a  jmp     loc_18004CDA1
0x18004ce5f  movzx   eax, byte ptr [r14+0Fh]
0x18004ce64  movzx   ecx, byte ptr [r14+0Eh]
0x18004ce69  movzx   edx, byte ptr [r14+0Dh]
0x18004ce6e  movzx   r8d, byte ptr [r14+0Ch]
0x18004ce73  movzx   r9d, byte ptr [r14+0Bh]
0x18004ce78  movzx   r10d, byte ptr [r14+0Ah]
0x18004ce7d  movzx   r11d, byte ptr [r14+9]
0x18004ce82  movzx   edi, byte ptr [r14+8]
0x18004ce87  movzx   esi, word ptr [r14+6]
0x18004ce8c  movzx   ebp, word ptr [r14+4]
0x18004ce91  mov     [rsp+0A8h+var_28], r15
0x18004ce99  mov     [rsp+0A8h+var_30], eax
0x18004ce9d  mov     eax, [r14]
0x18004cea0  mov     [rsp+0A8h+var_38], ecx
0x18004cea4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ceab  mov     [rsp+0A8h+var_40], edx
0x18004ceaf  mov     [rsp+0A8h+var_48], r8d
0x18004ceb4  mov     [rsp+0A8h+var_50], r9d
0x18004ceb9  mov     rcx, [rcx+40h]
0x18004cebd  mov     [rsp+0A8h+var_58], r10d
0x18004cec2  mov     [rsp+0A8h+var_60], r11d
0x18004cec7  mov     [rsp+0A8h+var_68], edi
0x18004cecb  mov     [rsp+0A8h+var_70], esi
0x18004cecf  mov     [rsp+0A8h+var_78], ebp
0x18004ced3  mov     [rsp+0A8h+var_80], eax
0x18004ced7  call    WPP_RECORDER_SF_DDDDDDDDDDDS
0x18004cedc  jmp     loc_18004CDA1
0x18004cee1  call    cs:__imp_ObfDereferenceObject
0x18004cee8  nop     dword ptr [rax+rax+00h]
0x18004ceed  jmp     loc_18004CD6E
0x18004cef2  lea     rax, WPP_RECORDER_INITIALIZED
0x18004cef9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004cf00  jz      loc_18004CDA1
0x18004cf06  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf0d  lea     rax, WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids
0x18004cf14  mov     r9d, 0Ch
0x18004cf1a  mov     [rsp+0A8h+var_80], ebx
0x18004cf1e  mov     r8d, 1
0x18004cf24  mov     [rsp+0A8h+var_88], rax
0x18004cf29  mov     dl, 2
0x18004cf2b  mov     rcx, [rcx+40h]
0x18004cf2f  call    WPP_RECORDER_SF_D
0x18004cf34  jmp     loc_18004CDA1
```
