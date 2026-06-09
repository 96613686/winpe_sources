# I8xManuallyRemoveDevice

- ea: `0x14001ce6c`
- end: `0x14001cf54`
- name: `I8xManuallyRemoveDevice`
- size: `232`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140019490`
- `0x1400198e0`
- `0x14001b924`
- `0x14001bce0`
- `0x14001c068`
- `0x14001e950`
- `0x14001eea0`

## callees

- `0x140004530`
- `0x14001ce6c`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceState` at `0x14001cf3a`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001cf3a`

## pseudocode

```c
__int64 __fastcall I8xManuallyRemoveDevice(__int64 a1, int a2)
{
  int v3; // ebx

  if ( *(_BYTE *)(a1 + 565) )
  {
    v3 = _InterlockedDecrement((volatile signed __int32 *)&WPP_MAIN_CB.AlignmentRequirement);
    if ( v3 < 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          16,
          23,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFEFE;
    }
  }
  else
  {
    v3 = _InterlockedDecrement((volatile signed __int32 *)(&WPP_MAIN_CB.AlignmentRequirement + 1));
    if ( v3 < 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          16,
          24,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels &= 0xFFFFFDF5;
    }
  }
  *(_DWORD *)(a1 + 556) |= 0xAu;
  IoInvalidateDeviceState(*(PDEVICE_OBJECT *)(a1 + 32));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001ce6c  mov     [rsp+arg_0], rbx
0x14001ce71  push    rdi
0x14001ce72  sub     rsp, 30h
0x14001ce76  or      ebx, 0FFFFFFFFh
0x14001ce79  mov     rdi, rcx
0x14001ce7c  cmp     byte ptr [rcx+235h], 0
0x14001ce83  jz      short loc_14001CEDD
0x14001ce85  lock xadd cs:WPP_MAIN_CB.AlignmentRequirement, ebx
0x14001ce8d  dec     ebx
0x14001ce8f  cmp     ebx, 1
0x14001ce92  jge     loc_14001CF2F
0x14001ce98  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ce9f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cea6  jz      short loc_14001CECE
0x14001cea8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ceaf  lea     rax, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14001ceb6  mov     r9d, 17h
0x14001cebc  mov     [rsp+38h+var_18], rax
0x14001cec1  mov     rcx, [rcx+40h]
0x14001cec5  lea     r8d, [r9-7]
0x14001cec9  call    WPP_RECORDER_SF_
0x14001cece  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001ced5  and     dword ptr [rax], 0FFFFFEFEh
0x14001cedb  jmp     short loc_14001CF2F
0x14001cedd  lock xadd dword ptr cs:WPP_MAIN_CB+9Ch, ebx
0x14001cee5  dec     ebx
0x14001cee7  cmp     ebx, 1
0x14001ceea  jge     short loc_14001CF2F
0x14001ceec  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cef3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cefa  jz      short loc_14001CF22
0x14001cefc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf03  lea     rax, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14001cf0a  mov     r9d, 18h
0x14001cf10  mov     [rsp+38h+var_18], rax
0x14001cf15  mov     rcx, [rcx+40h]
0x14001cf19  lea     r8d, [r9-8]
0x14001cf1d  call    WPP_RECORDER_SF_
0x14001cf22  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001cf29  and     dword ptr [rcx], 0FFFFFDF5h
0x14001cf2f  or      dword ptr [rdi+22Ch], 0Ah
0x14001cf36  mov     rcx, [rdi+20h]; PhysicalDeviceObject
0x14001cf3a  call    cs:__imp_IoInvalidateDeviceState
0x14001cf41  nop     dword ptr [rax+rax+00h]
0x14001cf46  mov     eax, ebx
0x14001cf48  mov     rbx, [rsp+38h+arg_0]
0x14001cf4d  add     rsp, 30h
0x14001cf51  pop     rdi
0x14001cf52  retn
```
