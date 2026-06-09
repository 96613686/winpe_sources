# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c0e8`
- end: `0x18000c198`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bfec`
- `0x18000c6a0`

## callees

- `0x18000c0e8`
- `0x18000cacc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c166`
- `msvcrt!memcpy_s` at `0x18000c166`

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
0x18000c0e8  mov     [rsp+arg_0], rbx
0x18000c0ed  push    rdi
0x18000c0ee  sub     rsp, 30h
0x18000c0f2  lea     rbx, [rcx+28h]
0x18000c0f6  mov     qword ptr [rdx], 0
0x18000c0fd  mov     rcx, [rbx]
0x18000c100  xor     eax, eax
0x18000c102  mov     r10, [rbx+8]
0x18000c106  mov     rdi, rdx
0x18000c109  sub     r10, rcx
0x18000c10c  shr     r10, 4
0x18000c110  test    r10, r10
0x18000c113  jz      short loc_18000C12B
0x18000c115  lea     rdx, [rax+1]
0x18000c119  add     rax, rax
0x18000c11c  cmp     qword ptr [rcx+rax*8], 0
0x18000c121  jz      short loc_18000C18A
0x18000c123  mov     rax, rdx
0x18000c126  cmp     rdx, r10
0x18000c129  jb      short loc_18000C115
0x18000c12b  mov     edx, 10h; unsigned __int64
0x18000c130  mov     [rsp+38h+Source], r8
0x18000c135  mov     rcx, rbx; this
0x18000c138  mov     [rsp+38h+var_10], r9
0x18000c13d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c142  test    al, al
0x18000c144  jz      short loc_18000C17F
0x18000c146  mov     rcx, [rbx+8]; Destination
0x18000c14a  lea     r8, [rsp+38h+Source]; Source
0x18000c14f  mov     rax, [rbx+10h]
0x18000c153  mov     r9d, 10h; SourceSize
0x18000c159  sub     rax, rcx
0x18000c15c  cmp     rcx, [rbx+10h]
0x18000c160  sbb     rdx, rdx
0x18000c163  and     rdx, rax; DestinationSize
0x18000c166  call    cs:__imp_memcpy_s
0x18000c16c  add     qword ptr [rbx+8], 10h
0x18000c171  mov     rax, [rbx+8]
0x18000c175  sub     rax, [rbx]
0x18000c178  shr     rax, 4
0x18000c17c  mov     [rdi], rax
0x18000c17f  mov     rbx, [rsp+38h+arg_0]
0x18000c184  add     rsp, 30h
0x18000c188  pop     rdi
0x18000c189  retn
0x18000c18a  mov     [rcx+rax*8], r8
0x18000c18e  mov     [rcx+rax*8+8], r9
0x18000c193  mov     [rdi], rdx
0x18000c196  jmp     short loc_18000C17F
```
