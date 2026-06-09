# SendPayloadSeqComplete

- ea: `0x140017af0`
- end: `0x140017b7c`
- name: `SendPayloadSeqComplete`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c6d0`

## callees

- `0x140003050`
- `0x14000f7c4`
- `0x140017af0`

## pseudocode

```c
__int64 __fastcall SendPayloadSeqComplete(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  *(_QWORD *)(a2 + 88) = 0;
  result = DereferencePayloadSent(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140017af0  mov     [rsp+arg_0], rbx
0x140017af5  push    rdi
0x140017af6  sub     rsp, 20h
0x140017afa  mov     rbx, rdx
0x140017afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b04  lea     rdi, WPP_GLOBAL_Control
0x140017b0b  cmp     rcx, rdi
0x140017b0e  jz      short loc_140017B32
0x140017b10  mov     eax, [rcx+2Ch]
0x140017b13  test    al, 10h
0x140017b15  jz      short loc_140017B32
0x140017b17  cmp     byte ptr [rcx+29h], 4
0x140017b1b  jb      short loc_140017B32
0x140017b1d  mov     rcx, [rcx+18h]
0x140017b21  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017b28  mov     edx, 26h ; '&'
0x140017b2d  call    WPP_SF_
0x140017b32  mov     rcx, rbx
0x140017b35  mov     qword ptr [rbx+58h], 0
0x140017b3d  call    DereferencePayloadSent
0x140017b42  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b49  cmp     rcx, rdi
0x140017b4c  jz      short loc_140017B70
0x140017b4e  mov     eax, [rcx+2Ch]
0x140017b51  test    al, 10h
0x140017b53  jz      short loc_140017B70
0x140017b55  cmp     byte ptr [rcx+29h], 4
0x140017b59  jb      short loc_140017B70
0x140017b5b  mov     rcx, [rcx+18h]
0x140017b5f  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017b66  mov     edx, 27h ; '''
0x140017b6b  call    WPP_SF_
0x140017b70  mov     rbx, [rsp+28h+arg_0]
0x140017b75  add     rsp, 20h
0x140017b79  pop     rdi
0x140017b7a  retn
```
