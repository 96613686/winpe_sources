# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007ae8`
- end: `0x180007b98`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079ec`
- `0x1800080a0`

## callees

- `0x180007ae8`
- `0x1800084cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007b66`
- `msvcrt!memcpy_s` at `0x180007b66`

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
  _QWORD Source[3]; // [rsp+20h] [rbp-18h] BYREF

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
    Source[0] = a3;
    Source[1] = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v4, 0x10u) )
    {
      memcpy_s(
        *((void *const *)v4 + 1),
        (*((_QWORD *)v4 + 2) - *((_QWORD *)v4 + 1)) & -(__int64)(*((_QWORD *)v4 + 1) < *((_QWORD *)v4 + 2)),
        Source,
        0x10u);
      *((_QWORD *)v4 + 1) += 16LL;
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
    }
  }
}

```

## disassembly

```asm
0x180007ae8  mov     [rsp+arg_0], rbx
0x180007aed  push    rdi
0x180007aee  sub     rsp, 30h
0x180007af2  lea     rbx, [rcx+28h]
0x180007af6  mov     qword ptr [rdx], 0
0x180007afd  mov     rcx, [rbx]
0x180007b00  xor     eax, eax
0x180007b02  mov     r10, [rbx+8]
0x180007b06  mov     rdi, rdx
0x180007b09  sub     r10, rcx
0x180007b0c  shr     r10, 4
0x180007b10  test    r10, r10
0x180007b13  jz      short loc_180007B2B
0x180007b15  lea     rdx, [rax+1]
0x180007b19  add     rax, rax
0x180007b1c  cmp     qword ptr [rcx+rax*8], 0
0x180007b21  jz      short loc_180007B8A
0x180007b23  mov     rax, rdx
0x180007b26  cmp     rdx, r10
0x180007b29  jb      short loc_180007B15
0x180007b2b  mov     edx, 10h; unsigned __int64
0x180007b30  mov     [rsp+38h+Source], r8
0x180007b35  mov     rcx, rbx; this
0x180007b38  mov     [rsp+38h+var_10], r9
0x180007b3d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007b42  test    al, al
0x180007b44  jz      short loc_180007B7F
0x180007b46  mov     rcx, [rbx+8]; Destination
0x180007b4a  lea     r8, [rsp+38h+Source]; Source
0x180007b4f  mov     rax, [rbx+10h]
0x180007b53  mov     r9d, 10h; SourceSize
0x180007b59  sub     rax, rcx
0x180007b5c  cmp     rcx, [rbx+10h]
0x180007b60  sbb     rdx, rdx
0x180007b63  and     rdx, rax; DestinationSize
0x180007b66  call    cs:__imp_memcpy_s
0x180007b6c  add     qword ptr [rbx+8], 10h
0x180007b71  mov     rax, [rbx+8]
0x180007b75  sub     rax, [rbx]
0x180007b78  shr     rax, 4
0x180007b7c  mov     [rdi], rax
0x180007b7f  mov     rbx, [rsp+38h+arg_0]
0x180007b84  add     rsp, 30h
0x180007b88  pop     rdi
0x180007b89  retn
0x180007b8a  mov     [rcx+rax*8], r8
0x180007b8e  mov     [rcx+rax*8+8], r9
0x180007b93  mov     [rdi], rdx
0x180007b96  jmp     short loc_180007B7F
```
