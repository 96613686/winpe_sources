# MountMgrFreeSiloDeviceExtension

- ea: `0x140001bec`
- end: `0x140001cfe`
- name: `MountMgrFreeSiloDeviceExtension`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ebc`
- `0x140002140`

## callees

- `0x140001ae0`
- `0x140001bec`
- `0x14000c7d8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140001ce8`
- `ntoskrnl!KeReleaseMutex` at `0x140001ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c0e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c3a`

## pseudocode

```c
void __fastcall MountMgrFreeSiloDeviceExtension(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // r8
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax

  if ( a1 )
  {
    v2 = *(void **)(a1 + 272);
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0);
      *(_QWORD *)(a1 + 272) = 0;
    }
    KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
    if ( *(_QWORD *)(a1 + 32) != a1 + 32
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 362, v3, 3221225860LL);
    }
    v4 = (_QWORD **)(a1 + 16);
    while ( 1 )
    {
      v5 = *v4;
      if ( *v4 == v4 )
        break;
      if ( (_QWORD **)v5[1] != v4 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
        __fastfail(3u);
      *v4 = v6;
      v6[1] = v4;
      MountMgrFreeMountedDeviceInfo(v5);
    }
    if ( *(_QWORD *)(a1 + 176) != a1 + 176
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 363, v3, 3221225860LL);
    }
    KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
  }
}

```

## disassembly

```asm
0x140001bec  test    rcx, rcx
0x140001bef  jz      locret_140001CFC
0x140001bf5  push    rbx
0x140001bf6  push    rbp
0x140001bf7  push    rsi
0x140001bf8  push    rdi
0x140001bf9  sub     rsp, 38h
0x140001bfd  mov     rbx, rcx
0x140001c00  mov     rcx, [rcx+110h]; P
0x140001c07  test    rcx, rcx
0x140001c0a  jz      short loc_140001C25
0x140001c0c  xor     edx, edx; Tag
0x140001c0e  call    cs:__imp_ExFreePoolWithTag
0x140001c15  nop     dword ptr [rax+rax+00h]
0x140001c1a  mov     qword ptr [rbx+110h], 0
0x140001c25  xor     r9d, r9d; Alertable
0x140001c28  mov     [rsp+58h+Timeout], 0; Timeout
0x140001c31  xor     r8d, r8d; WaitMode
0x140001c34  lea     rcx, [rbx+38h]; Object
0x140001c38  xor     edx, edx; WaitReason
0x140001c3a  call    cs:__imp_KeWaitForSingleObject
0x140001c41  nop     dword ptr [rax+rax+00h]
0x140001c46  lea     rax, [rbx+20h]
0x140001c4a  lea     rbp, WPP_GLOBAL_Control
0x140001c51  cmp     [rax], rax
0x140001c54  jz      short loc_140001C7D
0x140001c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c5d  cmp     rcx, rbp
0x140001c60  jz      short loc_140001C7D
0x140001c62  mov     eax, [rcx+2Ch]
0x140001c65  test    al, 1
0x140001c67  jz      short loc_140001C7D
0x140001c69  mov     rcx, [rcx+18h]
0x140001c6d  mov     edx, 16Ah
0x140001c72  mov     r9d, 0C0000184h
0x140001c78  call    WPP_SF_L
0x140001c7d  lea     rdi, [rbx+10h]
0x140001c81  mov     rcx, [rdi]; P
0x140001c84  cmp     rcx, rdi
0x140001c87  jz      short loc_140001CAF
0x140001c89  cmp     [rcx+8], rdi
0x140001c8d  jnz     short loc_140001CA8
0x140001c8f  mov     rax, [rcx]
0x140001c92  cmp     [rax+8], rcx
0x140001c96  jnz     short loc_140001CA8
0x140001c98  mov     [rdi], rax
0x140001c9b  mov     dl, 1
0x140001c9d  mov     [rax+8], rdi
0x140001ca1  call    MountMgrFreeMountedDeviceInfo
0x140001ca6  jmp     short loc_140001C81
0x140001ca8  mov     ecx, 3
0x140001cad  int     29h; Win8: RtlFailFast(ecx)
0x140001caf  lea     rax, [rbx+0B0h]
0x140001cb6  cmp     [rax], rax
0x140001cb9  jz      short loc_140001CE2
0x140001cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cc2  cmp     rcx, rbp
0x140001cc5  jz      short loc_140001CE2
0x140001cc7  mov     eax, [rcx+2Ch]
0x140001cca  test    al, 1
0x140001ccc  jz      short loc_140001CE2
0x140001cce  mov     rcx, [rcx+18h]
0x140001cd2  mov     edx, 16Bh
0x140001cd7  mov     r9d, 0C0000184h
0x140001cdd  call    WPP_SF_L
0x140001ce2  xor     edx, edx; Wait
0x140001ce4  lea     rcx, [rbx+38h]; Mutex
0x140001ce8  call    cs:__imp_KeReleaseMutex
0x140001cef  nop     dword ptr [rax+rax+00h]
0x140001cf4  add     rsp, 38h
0x140001cf8  pop     rdi
0x140001cf9  pop     rsi
0x140001cfa  pop     rbp
0x140001cfb  pop     rbx
0x140001cfc  retn
```
