# MountMgrTracelogCache

- ea: `0x14000d3ac`
- end: `0x14000d48d`
- name: `MountMgrTracelogCache`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400147a0`

## callees

- `0x140001b30`
- `0x14000d0bc`
- `0x14000d148`
- `0x14000d3ac`

## pseudocode

```c
__int64 __fastcall MountMgrTracelogCache(__int64 a1)
{
  _QWORD *i; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 337);
  }
  MountMgrTraceDeviceExtension(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 338);
  }
  for ( i = *(_QWORD **)(a1 + 16); i != (_QWORD *)(a1 + 16); i = (_QWORD *)*i )
    MountMgrTraceMountedDevice(a1, (__int64)i);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 339);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 340);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d3ac  push    rbx
0x14000d3ae  push    rsi
0x14000d3af  push    rdi
0x14000d3b0  push    r15
0x14000d3b2  sub     rsp, 28h
0x14000d3b6  mov     rsi, rcx
0x14000d3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3c0  lea     r15, WPP_GLOBAL_Control
0x14000d3c7  cmp     rcx, r15
0x14000d3ca  jz      short loc_14000D3E7
0x14000d3cc  mov     eax, [rcx+2Ch]
0x14000d3cf  test    al, 8
0x14000d3d1  jz      short loc_14000D3E7
0x14000d3d3  cmp     byte ptr [rcx+29h], 2
0x14000d3d7  jb      short loc_14000D3E7
0x14000d3d9  mov     rcx, [rcx+18h]
0x14000d3dd  mov     edx, 151h
0x14000d3e2  call    WPP_SF_
0x14000d3e7  mov     rcx, rsi
0x14000d3ea  call    MountMgrTraceDeviceExtension
0x14000d3ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3f6  cmp     rcx, r15
0x14000d3f9  jz      short loc_14000D416
0x14000d3fb  mov     eax, [rcx+2Ch]
0x14000d3fe  test    al, 8
0x14000d400  jz      short loc_14000D416
0x14000d402  cmp     byte ptr [rcx+29h], 2
0x14000d406  jb      short loc_14000D416
0x14000d408  mov     rcx, [rcx+18h]
0x14000d40c  mov     edx, 152h
0x14000d411  call    WPP_SF_
0x14000d416  lea     rdi, [rsi+10h]
0x14000d41a  mov     rbx, [rdi]
0x14000d41d  jmp     short loc_14000D42D
0x14000d41f  mov     rdx, rbx
0x14000d422  mov     rcx, rsi
0x14000d425  call    MountMgrTraceMountedDevice
0x14000d42a  mov     rbx, [rbx]
0x14000d42d  cmp     rbx, rdi
0x14000d430  jnz     short loc_14000D41F
0x14000d432  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d439  cmp     rcx, r15
0x14000d43c  jz      short loc_14000D459
0x14000d43e  mov     eax, [rcx+2Ch]
0x14000d441  test    al, 8
0x14000d443  jz      short loc_14000D459
0x14000d445  cmp     byte ptr [rcx+29h], 2
0x14000d449  jb      short loc_14000D459
0x14000d44b  mov     rcx, [rcx+18h]
0x14000d44f  mov     edx, 153h
0x14000d454  call    WPP_SF_
0x14000d459  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d460  cmp     rcx, r15
0x14000d463  jz      short loc_14000D480
0x14000d465  mov     eax, [rcx+2Ch]
0x14000d468  test    al, 8
0x14000d46a  jz      short loc_14000D480
0x14000d46c  cmp     byte ptr [rcx+29h], 2
0x14000d470  jb      short loc_14000D480
0x14000d472  mov     rcx, [rcx+18h]
0x14000d476  mov     edx, 154h
0x14000d47b  call    WPP_SF_
0x14000d480  xor     eax, eax
0x14000d482  add     rsp, 28h
0x14000d486  pop     r15
0x14000d488  pop     rdi
0x14000d489  pop     rsi
0x14000d48a  pop     rbx
0x14000d48b  retn
```
