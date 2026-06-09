# FveCleanupOrDerefDriverCdo

- ea: `0x140073b5c`
- end: `0x140073ca5`
- name: `FveCleanupOrDerefDriverCdo`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x14006f658`

## callees

- `0x140008dc0`
- `0x140073b5c`
- `0x140086948`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140073c56`
- `ntoskrnl!IoDeleteDevice` at `0x140073c56`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140073c39`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140073c39`
- `ntoskrnl!RtlInitUnicodeString` at `0x140073c28`
- `ntoskrnl!RtlInitUnicodeString` at `0x140073c28`

## pseudocode

```c
__int64 __fastcall FveCleanupOrDerefDriverCdo(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  struct _DEVICE_OBJECT *v5; // rdi
  _QWORD *DeviceExtension; // rsi
  __int64 v7; // rbx
  _OWORD *v8; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
  if ( a1 )
  {
    BlDcbDeref(a1[2]);
    v3 = a1[3];
    a1[2] = 0;
    BlDcbDeref(v3);
    v4 = a1[4];
    a1[3] = 0;
    result = BlDcbDeref(v4);
    v5 = (struct _DEVICE_OBJECT *)a1[1];
    a1[4] = 0;
    if ( v5 )
    {
      DeviceExtension = v5->DeviceExtension;
      if ( DeviceExtension )
      {
        BlDcbDeref(DeviceExtension[3]);
        DeviceExtension[3] = 0;
        v5 = (struct _DEVICE_OBJECT *)a1[1];
        v7 = DeviceExtension[2];
      }
      else
      {
        v7 = 0;
      }
      DestinationString = 0;
      if ( v5 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\BitLocker");
        IoDeleteSymbolicLink(&DestinationString);
        v8 = v5->DeviceExtension;
        *v8 = 0;
        v8[1] = 0;
        IoDeleteDevice(v5);
      }
      result = BlDcbDeref(v7);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140073b5c  push    rbx
0x140073b5e  push    rsi
0x140073b5f  push    rdi
0x140073b60  push    r15
0x140073b62  sub     rsp, 38h
0x140073b66  mov     rbx, rcx
0x140073b69  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b70  lea     r15, WPP_GLOBAL_Control
0x140073b77  cmp     rcx, r15
0x140073b7a  jz      short loc_140073BA0
0x140073b7c  test    dword ptr [rcx+2Ch], 400h
0x140073b83  jz      short loc_140073BA0
0x140073b85  cmp     byte ptr [rcx+29h], 5
0x140073b89  jb      short loc_140073BA0
0x140073b8b  mov     rcx, [rcx+18h]
0x140073b8f  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140073b96  mov     edx, 17h
0x140073b9b  call    WPP_SF_
0x140073ba0  test    rbx, rbx
0x140073ba3  jz      loc_140073C6A
0x140073ba9  mov     rcx, [rbx+10h]
0x140073bad  call    BlDcbDeref
0x140073bb2  mov     rcx, [rbx+18h]
0x140073bb6  mov     qword ptr [rbx+10h], 0
0x140073bbe  call    BlDcbDeref
0x140073bc3  mov     rcx, [rbx+20h]
0x140073bc7  mov     qword ptr [rbx+18h], 0
0x140073bcf  call    BlDcbDeref
0x140073bd4  mov     rdi, [rbx+8]
0x140073bd8  mov     qword ptr [rbx+20h], 0
0x140073be0  test    rdi, rdi
0x140073be3  jz      loc_140073C6A
0x140073be9  mov     rsi, [rdi+40h]
0x140073bed  test    rsi, rsi
0x140073bf0  jz      short loc_140073C0D
0x140073bf2  mov     rcx, [rsi+18h]
0x140073bf6  call    BlDcbDeref
0x140073bfb  mov     qword ptr [rsi+18h], 0
0x140073c03  mov     rdi, [rbx+8]
0x140073c07  mov     rbx, [rsi+10h]
0x140073c0b  jmp     short loc_140073C0F
0x140073c0d  xor     ebx, ebx
0x140073c0f  xorps   xmm0, xmm0
0x140073c12  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140073c17  test    rdi, rdi
0x140073c1a  jz      short loc_140073C62
0x140073c1c  lea     rdx, aDosdevicesBitl; "\\DosDevices\\BitLocker"
0x140073c23  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140073c28  call    cs:__imp_RtlInitUnicodeString
0x140073c2f  nop     dword ptr [rax+rax+00h]
0x140073c34  lea     rcx, [rsp+58h+DestinationString]; SymbolicLinkName
0x140073c39  call    cs:__imp_IoDeleteSymbolicLink
0x140073c40  nop     dword ptr [rax+rax+00h]
0x140073c45  mov     rax, [rdi+40h]
0x140073c49  xorps   xmm0, xmm0
0x140073c4c  mov     rcx, rdi; DeviceObject
0x140073c4f  movups  xmmword ptr [rax], xmm0
0x140073c52  movups  xmmword ptr [rax+10h], xmm0
0x140073c56  call    cs:__imp_IoDeleteDevice
0x140073c5d  nop     dword ptr [rax+rax+00h]
0x140073c62  mov     rcx, rbx
0x140073c65  call    BlDcbDeref
0x140073c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140073c71  cmp     rcx, r15
0x140073c74  jz      short loc_140073C9A
0x140073c76  test    dword ptr [rcx+2Ch], 400h
0x140073c7d  jz      short loc_140073C9A
0x140073c7f  cmp     byte ptr [rcx+29h], 5
0x140073c83  jb      short loc_140073C9A
0x140073c85  mov     rcx, [rcx+18h]
0x140073c89  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140073c90  mov     edx, 18h
0x140073c95  call    WPP_SF_
0x140073c9a  add     rsp, 38h
0x140073c9e  pop     r15
0x140073ca0  pop     rdi
0x140073ca1  pop     rsi
0x140073ca2  pop     rbx
0x140073ca3  retn
```
