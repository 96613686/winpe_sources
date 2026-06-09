# CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72>::remove(CPacket &)

- ea: `0x14001ed8c`
- end: `0x14001edf5`
- name: `?remove@?$CAVLTree1@VCPacket@@_KVCGetLookupId@1@V?$Less@_K@@$0EI@@@QEAAXAEAVCPacket@@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140012bd4`
- `0x14001ca00`

## callees

- `0x14001ed8c`
- `0x140021798`

## pseudocode

```c
struct CAVLNode *__fastcall CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72>::remove(
        struct CAVLNode ***a1,
        __int64 a2)
{
  __int64 v2; // rbx
  struct CAVLNode *result; // rax
  _QWORD *v4; // r11
  struct CAVLNode *v5; // rcx
  int v6; // edx
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // eax

  v2 = a2 + 72;
  result = CAVLNode::remove_node(*a1, (struct CAVLNode *)(a2 + 72));
  *v4 = result;
  v5 = result;
  if ( result )
  {
    *(_QWORD *)result = 0;
    v6 = 0;
    v7 = *((_QWORD *)result + 2);
    if ( v7 )
      v6 = *(_DWORD *)(v7 + 24);
    v8 = *((_QWORD *)v5 + 1);
    if ( v8 )
      v9 = *(_DWORD *)(v8 + 24);
    else
      v9 = 0;
    if ( v6 >= v9 )
      v9 = v6;
    result = (struct CAVLNode *)(unsigned int)(v9 + 1);
    *((_DWORD *)v5 + 6) = (_DWORD)result;
  }
  *(_DWORD *)(v2 + 24) = 0;
  *(_QWORD *)v2 = 0;
  *(_QWORD *)(v2 + 8) = 0;
  *(_QWORD *)(v2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x14001ed8c  push    rbx
0x14001ed8e  sub     rsp, 20h
0x14001ed92  lea     rbx, [rdx+48h]
0x14001ed96  mov     r11, rcx
0x14001ed99  mov     rcx, [rcx]; this
0x14001ed9c  mov     rdx, rbx; struct CAVLNode *
0x14001ed9f  call    ?remove_node@CAVLNode@@QEAAPEAV1@PEAV1@@Z; CAVLNode::remove_node(CAVLNode *)
0x14001eda4  xor     r8d, r8d
0x14001eda7  mov     [r11], rax
0x14001edaa  mov     rcx, rax
0x14001edad  test    rax, rax
0x14001edb0  jz      short loc_14001EDDF
0x14001edb2  mov     [rax], r8
0x14001edb5  mov     edx, r8d
0x14001edb8  mov     rax, [rax+10h]
0x14001edbc  test    rax, rax
0x14001edbf  jz      short loc_14001EDC4
0x14001edc1  mov     edx, [rax+18h]
0x14001edc4  mov     rax, [rcx+8]
0x14001edc8  test    rax, rax
0x14001edcb  jnz     short loc_14001EDD2
0x14001edcd  mov     eax, r8d
0x14001edd0  jmp     short loc_14001EDD5
0x14001edd2  mov     eax, [rax+18h]
0x14001edd5  cmp     edx, eax
0x14001edd7  cmovge  eax, edx
0x14001edda  inc     eax
0x14001eddc  mov     [rcx+18h], eax
0x14001eddf  mov     [rbx+18h], r8d
0x14001ede3  mov     [rbx], r8
0x14001ede6  mov     [rbx+8], r8
0x14001edea  mov     [rbx+10h], r8
0x14001edee  add     rsp, 20h
0x14001edf2  pop     rbx
0x14001edf3  retn
```
