# FveCleanupOrDerefDriverCdo

- ea: `0x140075b8c`
- end: `0x140075cd5`
- name: `FveCleanupOrDerefDriverCdo`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400716e8`

## callees

- `0x140008e80`
- `0x140075b8c`
- `0x1400889e8`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140075c86`
- `ntoskrnl!IoDeleteDevice` at `0x140075c86`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140075c69`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140075c69`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075c58`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075c58`

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
0x140075b8c  push    rbx
0x140075b8e  push    rsi
0x140075b8f  push    rdi
0x140075b90  push    r15
0x140075b92  sub     rsp, 38h
0x140075b96  mov     rbx, rcx
0x140075b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ba0  lea     r15, WPP_GLOBAL_Control
0x140075ba7  cmp     rcx, r15
0x140075baa  jz      short loc_140075BD0
0x140075bac  test    dword ptr [rcx+2Ch], 400h
0x140075bb3  jz      short loc_140075BD0
0x140075bb5  cmp     byte ptr [rcx+29h], 5
0x140075bb9  jb      short loc_140075BD0
0x140075bbb  mov     rcx, [rcx+18h]
0x140075bbf  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140075bc6  mov     edx, 17h
0x140075bcb  call    WPP_SF_
0x140075bd0  test    rbx, rbx
0x140075bd3  jz      loc_140075C9A
0x140075bd9  mov     rcx, [rbx+10h]
0x140075bdd  call    BlDcbDeref
0x140075be2  mov     rcx, [rbx+18h]
0x140075be6  mov     qword ptr [rbx+10h], 0
0x140075bee  call    BlDcbDeref
0x140075bf3  mov     rcx, [rbx+20h]
0x140075bf7  mov     qword ptr [rbx+18h], 0
0x140075bff  call    BlDcbDeref
0x140075c04  mov     rdi, [rbx+8]
0x140075c08  mov     qword ptr [rbx+20h], 0
0x140075c10  test    rdi, rdi
0x140075c13  jz      loc_140075C9A
0x140075c19  mov     rsi, [rdi+40h]
0x140075c1d  test    rsi, rsi
0x140075c20  jz      short loc_140075C3D
0x140075c22  mov     rcx, [rsi+18h]
0x140075c26  call    BlDcbDeref
0x140075c2b  mov     qword ptr [rsi+18h], 0
0x140075c33  mov     rdi, [rbx+8]
0x140075c37  mov     rbx, [rsi+10h]
0x140075c3b  jmp     short loc_140075C3F
0x140075c3d  xor     ebx, ebx
0x140075c3f  xorps   xmm0, xmm0
0x140075c42  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140075c47  test    rdi, rdi
0x140075c4a  jz      short loc_140075C92
0x140075c4c  lea     rdx, aDosdevicesBitl; "\\DosDevices\\BitLocker"
0x140075c53  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140075c58  call    cs:__imp_RtlInitUnicodeString
0x140075c5f  nop     dword ptr [rax+rax+00h]
0x140075c64  lea     rcx, [rsp+58h+DestinationString]; SymbolicLinkName
0x140075c69  call    cs:__imp_IoDeleteSymbolicLink
0x140075c70  nop     dword ptr [rax+rax+00h]
0x140075c75  mov     rax, [rdi+40h]
0x140075c79  xorps   xmm0, xmm0
0x140075c7c  mov     rcx, rdi; DeviceObject
0x140075c7f  movups  xmmword ptr [rax], xmm0
0x140075c82  movups  xmmword ptr [rax+10h], xmm0
0x140075c86  call    cs:__imp_IoDeleteDevice
0x140075c8d  nop     dword ptr [rax+rax+00h]
0x140075c92  mov     rcx, rbx
0x140075c95  call    BlDcbDeref
0x140075c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ca1  cmp     rcx, r15
0x140075ca4  jz      short loc_140075CCA
0x140075ca6  test    dword ptr [rcx+2Ch], 400h
0x140075cad  jz      short loc_140075CCA
0x140075caf  cmp     byte ptr [rcx+29h], 5
0x140075cb3  jb      short loc_140075CCA
0x140075cb5  mov     rcx, [rcx+18h]
0x140075cb9  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140075cc0  mov     edx, 18h
0x140075cc5  call    WPP_SF_
0x140075cca  add     rsp, 38h
0x140075cce  pop     r15
0x140075cd0  pop     rdi
0x140075cd1  pop     rsi
0x140075cd2  pop     rbx
0x140075cd3  retn
```
