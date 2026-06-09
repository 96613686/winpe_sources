# MRxSmbBuildDeleteForRename

- ea: `0x14003c230`
- end: `0x14003c2df`
- name: `MRxSmbBuildDeleteForRename`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003c550`

## callees

- `0x14000dfa8`
- `0x14003c230`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildDeleteForRename(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int started; // edi
  __int64 v5; // [rsp+20h] [rbp-58h]
  __int128 v6; // [rsp+60h] [rbp-18h] BYREF

  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 456LL);
  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
  *((_QWORD *)&v6 + 1) = v2 + 20;
  LOWORD(v6) = *(_WORD *)(v2 + 16);
  started = MRxSmbStartSMBCommand(a1, 1, 6, 5, v5, 0x10000u);
  if ( !started )
    MRxSmbStuffSMB(a1, (__int64)"0wB4!", 6, (__int64)&v6);
  return started;
}

```

## disassembly

```asm
0x14003c230  mov     [rsp+arg_0], rbx
0x14003c235  push    rdi
0x14003c236  sub     rsp, 70h
0x14003c23a  mov     rax, [rcx+30h]
0x14003c23e  xorps   xmm0, xmm0
0x14003c241  mov     rbx, rcx
0x14003c244  mov     rdi, [rax+1C8h]
0x14003c24b  movups  [rsp+78h+var_18], xmm0
0x14003c250  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c257  lea     rax, WPP_GLOBAL_Control
0x14003c25e  cmp     rcx, rax
0x14003c261  jz      short loc_14003C281
0x14003c263  test    dword ptr [rcx+2Ch], 400h
0x14003c26a  jz      short loc_14003C281
0x14003c26c  mov     rcx, [rcx+18h]
0x14003c270  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c277  mov     edx, 0Eh
0x14003c27c  call    WPP_SF_
0x14003c281  lea     rax, [rdi+14h]
0x14003c285  mov     [rsp+78h+var_50], 10000h
0x14003c28d  mov     r9d, 5
0x14003c293  mov     qword ptr [rsp+78h+var_18+8], rax
0x14003c298  movzx   eax, word ptr [rdi+10h]
0x14003c29c  mov     r8b, 6
0x14003c29f  mov     rcx, rbx
0x14003c2a2  mov     word ptr [rsp+78h+var_18], ax
0x14003c2a7  lea     edx, [r9-4]
0x14003c2ab  call    MRxSmbStartSMBCommand
0x14003c2b0  mov     edi, eax
0x14003c2b2  test    eax, eax
0x14003c2b4  jnz     short loc_14003C2CE
0x14003c2b6  lea     r9, [rsp+78h+var_18]
0x14003c2bb  mov     rcx, rbx
0x14003c2be  lea     r8d, [rax+6]
0x14003c2c2  lea     rdx, a0wb4; "0wB4!"
0x14003c2c9  call    MRxSmbStuffSMB
0x14003c2ce  mov     rbx, [rsp+78h+arg_0]
0x14003c2d6  mov     eax, edi
0x14003c2d8  add     rsp, 70h
0x14003c2dc  pop     rdi
0x14003c2dd  retn
```
