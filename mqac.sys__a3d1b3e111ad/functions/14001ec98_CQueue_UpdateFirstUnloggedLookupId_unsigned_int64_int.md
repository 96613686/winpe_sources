# CQueue::UpdateFirstUnloggedLookupId(unsigned __int64,int)

- ea: `0x14001ec98`
- end: `0x14001ed2d`
- name: `?UpdateFirstUnloggedLookupId@CQueue@@AEAAX_KH@Z`
- size: `149`
- prototype: `void __fastcall(CQueue *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001e0c0`

## callees

- `0x14001ec98`
- `0x14001ed54`
- `0x14002155c`

## pseudocode

```c
void __fastcall CQueue::UpdateFirstUnloggedLookupId(CQueue *this, unsigned __int64 a2, int a3)
{
  unsigned __int64 v3; // rax
  __int64 v4; // r11
  struct CAVLNode *v5; // rax
  struct CAVLNode *v6; // rdx
  struct CAVLNode *v7; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 44);
  if ( a3 )
  {
    if ( a2 < v3 )
      *((_QWORD *)this + 44) = a2;
  }
  else if ( a2 >= v3 )
  {
    *((_QWORD *)this + 44) = -1;
    v8 = v3;
    CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72>::lower_bound(
      (char *)this + 160,
      &v7,
      &v8);
    v5 = v7;
    while ( v5 )
    {
      do
      {
        if ( _bittest16((const signed __int16 *)v5 - 10, 0xBu) )
        {
          *(_QWORD *)(v4 + 352) = *((_QWORD *)v5 - 2);
          return;
        }
        v5 = CAVLNode::Lmost(*((struct CAVLNode **)v5 + 1));
      }
      while ( v5 );
      while ( 1 )
      {
        v5 = *(struct CAVLNode **)v6;
        if ( !*(_QWORD *)v6 || *((struct CAVLNode **)v5 + 2) == v6 )
          break;
        v6 = *(struct CAVLNode **)v6;
      }
    }
  }
}

```

## disassembly

```asm
0x14001ec98  sub     rsp, 38h
0x14001ec9c  mov     rax, [rcx+160h]
0x14001eca3  mov     r11, rcx
0x14001eca6  test    r8d, r8d
0x14001eca9  jz      short loc_14001ECB9
0x14001ecab  cmp     rdx, rax
0x14001ecae  jnb     short loc_14001ED27
0x14001ecb0  mov     [rcx+160h], rdx
0x14001ecb7  jmp     short loc_14001ED27
0x14001ecb9  cmp     rdx, rax
0x14001ecbc  jb      short loc_14001ED27
0x14001ecbe  mov     qword ptr [rcx+160h], 0FFFFFFFFFFFFFFFFh
0x14001ecc9  lea     r8, [rsp+38h+arg_18]
0x14001ecce  add     rcx, 0A0h
0x14001ecd5  mov     [rsp+38h+arg_18], rax
0x14001ecda  lea     rdx, [rsp+38h+var_18]
0x14001ecdf  call    ?lower_bound@?$CAVLTree1@VCPacket@@_KVCGetLookupId@1@V?$Less@_K@@$0EI@@@QEBA?AVIterator@1@AEB_K@Z; CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72>::lower_bound(unsigned __int64 const &)
0x14001ece4  mov     rax, [rsp+38h+var_18]
0x14001ece9  test    rax, rax
0x14001ecec  jz      short loc_14001ED27
0x14001ecee  bt      word ptr [rax-14h], 0Bh
0x14001ecf4  jb      short loc_14001ED1C
0x14001ecf6  mov     rcx, [rax+8]; struct CAVLNode *
0x14001ecfa  mov     rdx, rax
0x14001ecfd  call    ?Lmost@CAVLNode@@SAPEAV1@PEAV1@@Z; CAVLNode::Lmost(CAVLNode *)
0x14001ed02  test    rax, rax
0x14001ed05  jnz     short loc_14001ECEE
0x14001ed07  mov     rax, [rdx]
0x14001ed0a  test    rax, rax
0x14001ed0d  jz      short loc_14001ED1A
0x14001ed0f  cmp     [rax+10h], rdx
0x14001ed13  jz      short loc_14001ECE9
0x14001ed15  mov     rdx, rax
0x14001ed18  jmp     short loc_14001ED07
0x14001ed1a  jmp     short loc_14001ECE9
0x14001ed1c  mov     rcx, [rax-10h]
0x14001ed20  mov     [r11+160h], rcx
0x14001ed27  add     rsp, 38h
0x14001ed2b  retn
```
