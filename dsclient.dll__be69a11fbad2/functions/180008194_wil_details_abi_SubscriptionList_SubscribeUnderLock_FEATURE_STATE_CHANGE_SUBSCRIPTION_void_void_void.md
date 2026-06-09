# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008194`
- end: `0x18000821f`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `139`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005398`
- `0x18000806c`
- `0x180008104`

## callees

- `0x180008194`
- `0x180008c9c`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  char *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v8; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rdx
  __int64 v10; // rax
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (char *)this + 40;
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
    if ( wil::details_abi::heap_buffer::push_back((void **)v4, v11, 0x10u) )
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
  }
}

```

## disassembly

```asm
0x180008194  mov     [rsp+arg_0], rbx
0x180008199  push    rdi
0x18000819a  sub     rsp, 30h
0x18000819e  lea     rbx, [rcx+28h]
0x1800081a2  mov     qword ptr [rdx], 0
0x1800081a9  mov     rcx, [rbx]
0x1800081ac  xor     eax, eax
0x1800081ae  mov     r10, [rbx+8]
0x1800081b2  mov     rdi, rdx
0x1800081b5  sub     r10, rcx
0x1800081b8  shr     r10, 4
0x1800081bc  test    r10, r10
0x1800081bf  jz      short loc_1800081D7
0x1800081c1  lea     rdx, [rax+1]
0x1800081c5  add     rax, rax
0x1800081c8  cmp     qword ptr [rcx+rax*8], 0
0x1800081cd  jz      short loc_180008211
0x1800081cf  mov     rax, rdx
0x1800081d2  cmp     rdx, r10
0x1800081d5  jb      short loc_1800081C1
0x1800081d7  mov     [rsp+38h+var_18], r8
0x1800081dc  lea     rdx, [rsp+38h+var_18]; void *
0x1800081e1  mov     r8d, 10h; unsigned __int64
0x1800081e7  mov     [rsp+38h+var_10], r9
0x1800081ec  mov     rcx, rbx; this
0x1800081ef  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800081f4  test    al, al
0x1800081f6  jz      short loc_180008206
0x1800081f8  mov     rax, [rbx+8]
0x1800081fc  sub     rax, [rbx]
0x1800081ff  shr     rax, 4
0x180008203  mov     [rdi], rax
0x180008206  mov     rbx, [rsp+38h+arg_0]
0x18000820b  add     rsp, 30h
0x18000820f  pop     rdi
0x180008210  retn
0x180008211  mov     [rcx+rax*8], r8
0x180008215  mov     [rcx+rax*8+8], r9
0x18000821a  mov     [rdi], rdx
0x18000821d  jmp     short loc_180008206
```
