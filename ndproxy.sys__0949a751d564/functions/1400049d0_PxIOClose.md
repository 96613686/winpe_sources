# PxIOClose

- ea: `0x1400049d0`
- end: `0x140004a30`
- name: `PxIOClose`
- size: `96`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x1400049d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004a1b`
- `ntoskrnl!IofCompleteRequest` at `0x140004a1b`

## pseudocode

```c
__int64 __fastcall PxIOClose(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1400049d0  push    rbx
0x1400049d2  sub     rsp, 20h
0x1400049d6  mov     rbx, rdx
0x1400049d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049e0  lea     rax, WPP_GLOBAL_Control
0x1400049e7  cmp     rcx, rax
0x1400049ea  jz      short loc_140004A07
0x1400049ec  cmp     byte ptr [rcx+29h], 5
0x1400049f0  jb      short loc_140004A07
0x1400049f2  mov     rcx, [rcx+18h]
0x1400049f6  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x1400049fd  mov     edx, 0Eh
0x140004a02  call    WPP_SF_
0x140004a07  xor     edx, edx; PriorityBoost
0x140004a09  mov     dword ptr [rbx+30h], 0
0x140004a10  mov     rcx, rbx; Irp
0x140004a13  mov     qword ptr [rbx+38h], 0
0x140004a1b  call    cs:__imp_IofCompleteRequest
0x140004a22  nop     dword ptr [rax+rax+00h]
0x140004a27  xor     eax, eax
0x140004a29  add     rsp, 20h
0x140004a2d  pop     rbx
0x140004a2e  retn
```
