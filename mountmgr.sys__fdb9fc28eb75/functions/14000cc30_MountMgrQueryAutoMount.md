# MountMgrQueryAutoMount

- ea: `0x14000cc30`
- end: `0x14000ccab`
- name: `MountMgrQueryAutoMount`
- size: `123`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000cc30`

## pseudocode

```c
__int64 __fastcall MountMgrQueryAutoMount(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  __int64 v5; // rax

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) >= 4u )
  {
    v4 = 0;
    **(_DWORD **)(a2 + 24) = *(_BYTE *)(a1 + 192) != 0;
    v5 = 4;
  }
  else
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 330, a3, 3221225485LL);
    v5 = 0;
  }
  *(_QWORD *)(a2 + 56) = v5;
  return v4;
}

```

## disassembly

```asm
0x14000cc30  mov     [rsp+arg_0], rbx
0x14000cc35  push    rdi
0x14000cc36  sub     rsp, 20h
0x14000cc3a  mov     rax, [rdx+0B8h]
0x14000cc41  mov     rbx, rdx
0x14000cc44  cmp     dword ptr [rax+8], 4
0x14000cc48  jnb     short loc_14000CC81
0x14000cc4a  mov     edi, 0C000000Dh
0x14000cc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc56  lea     rax, WPP_GLOBAL_Control
0x14000cc5d  cmp     rcx, rax
0x14000cc60  jz      short loc_14000CC7D
0x14000cc62  mov     eax, [rcx+2Ch]
0x14000cc65  test    al, 1
0x14000cc67  jz      short loc_14000CC7D
0x14000cc69  mov     rcx, [rcx+18h]
0x14000cc6d  mov     edx, 14Ah
0x14000cc72  mov     r9d, 0C000000Dh
0x14000cc78  call    WPP_SF_L
0x14000cc7d  xor     eax, eax
0x14000cc7f  jmp     short loc_14000CC99
0x14000cc81  xor     eax, eax
0x14000cc83  cmp     [rcx+0C0h], al
0x14000cc89  mov     edi, eax
0x14000cc8b  mov     rcx, [rdx+18h]
0x14000cc8f  setnz   al
0x14000cc92  mov     [rcx], eax
0x14000cc94  mov     eax, 4
0x14000cc99  mov     [rbx+38h], rax
0x14000cc9d  mov     eax, edi
0x14000cc9f  mov     rbx, [rsp+28h+arg_0]
0x14000cca4  add     rsp, 20h
0x14000cca8  pop     rdi
0x14000cca9  retn
```
