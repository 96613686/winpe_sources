# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000c564`
- end: `0x14000c5ef`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `139`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b3a4`
- `0x14000c43c`
- `0x14000c4d4`

## callees

- `0x14000c564`
- `0x14000ca78`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  wil::details_abi::heap_buffer *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v8; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rdx
  __int64 v10; // rax
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (wil::details_abi::SubscriptionList *)((char *)this + 40);
  *a2 = 0;
  v5 = *((_QWORD *)this + 5);
  v6 = 0;
  v8 = (unsigned __int64)(*((_QWORD *)v4 + 1) - v5) >> 4;
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((char *)v6 + 1);
      v10 = 2LL * (_QWORD)v6;
      if ( !*(_QWORD *)(v5 + 8 * v10) )
        break;
      v6 = v9;
      if ( (unsigned __int64)v9 >= v8 )
        goto LABEL_4;
    }
    *(_QWORD *)(v5 + 8 * v10) = a3;
    *(_QWORD *)(v5 + 8 * v10 + 8) = a4;
    *a2 = v9;
  }
  else
  {
LABEL_4:
    v11[0] = a3;
    v11[1] = a4;
    if ( wil::details_abi::heap_buffer::push_back(v4, v11, 0x10u) )
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
  }
}

```

## disassembly

```asm
0x14000c564  mov     [rsp+arg_0], rbx
0x14000c569  push    rdi
0x14000c56a  sub     rsp, 30h
0x14000c56e  lea     rbx, [rcx+28h]
0x14000c572  mov     qword ptr [rdx], 0
0x14000c579  mov     rcx, [rbx]
0x14000c57c  xor     eax, eax
0x14000c57e  mov     r10, [rbx+8]
0x14000c582  mov     rdi, rdx
0x14000c585  sub     r10, rcx
0x14000c588  shr     r10, 4
0x14000c58c  test    r10, r10
0x14000c58f  jz      short loc_14000C5A7
0x14000c591  lea     rdx, [rax+1]
0x14000c595  add     rax, rax
0x14000c598  cmp     qword ptr [rcx+rax*8], 0
0x14000c59d  jz      short loc_14000C5E1
0x14000c59f  mov     rax, rdx
0x14000c5a2  cmp     rdx, r10
0x14000c5a5  jb      short loc_14000C591
0x14000c5a7  mov     [rsp+38h+var_18], r8
0x14000c5ac  lea     rdx, [rsp+38h+var_18]; void *
0x14000c5b1  mov     r8d, 10h; unsigned __int64
0x14000c5b7  mov     [rsp+38h+var_10], r9
0x14000c5bc  mov     rcx, rbx; this
0x14000c5bf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c5c4  test    al, al
0x14000c5c6  jz      short loc_14000C5D6
0x14000c5c8  mov     rax, [rbx+8]
0x14000c5cc  sub     rax, [rbx]
0x14000c5cf  shr     rax, 4
0x14000c5d3  mov     [rdi], rax
0x14000c5d6  mov     rbx, [rsp+38h+arg_0]
0x14000c5db  add     rsp, 30h
0x14000c5df  pop     rdi
0x14000c5e0  retn
0x14000c5e1  mov     [rcx+rax*8], r8
0x14000c5e5  mov     [rcx+rax*8+8], r9
0x14000c5ea  mov     [rdi], rdx
0x14000c5ed  jmp     short loc_14000C5D6
```
