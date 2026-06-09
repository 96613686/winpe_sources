# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009b40`
- end: `0x180009bf0`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `176`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a44`
- `0x18000a170`

## callees

- `0x180009b40`
- `0x18000a5e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009bbe`
- `msvcrt!memcpy_s` at `0x180009bbe`

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
0x180009b40  mov     [rsp+arg_0], rbx
0x180009b45  push    rdi
0x180009b46  sub     rsp, 30h
0x180009b4a  lea     rbx, [rcx+28h]
0x180009b4e  mov     qword ptr [rdx], 0
0x180009b55  mov     rcx, [rbx]
0x180009b58  xor     eax, eax
0x180009b5a  mov     r10, [rbx+8]
0x180009b5e  mov     rdi, rdx
0x180009b61  sub     r10, rcx
0x180009b64  shr     r10, 4
0x180009b68  test    r10, r10
0x180009b6b  jz      short loc_180009B83
0x180009b6d  lea     rdx, [rax+1]
0x180009b71  add     rax, rax
0x180009b74  cmp     qword ptr [rcx+rax*8], 0
0x180009b79  jz      short loc_180009BE2
0x180009b7b  mov     rax, rdx
0x180009b7e  cmp     rdx, r10
0x180009b81  jb      short loc_180009B6D
0x180009b83  mov     edx, 10h; unsigned __int64
0x180009b88  mov     [rsp+38h+Source], r8
0x180009b8d  mov     rcx, rbx; this
0x180009b90  mov     [rsp+38h+var_10], r9
0x180009b95  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009b9a  test    al, al
0x180009b9c  jz      short loc_180009BD7
0x180009b9e  mov     rcx, [rbx+8]; Destination
0x180009ba2  lea     r8, [rsp+38h+Source]; Source
0x180009ba7  mov     rax, [rbx+10h]
0x180009bab  mov     r9d, 10h; SourceSize
0x180009bb1  sub     rax, rcx
0x180009bb4  cmp     rcx, [rbx+10h]
0x180009bb8  sbb     rdx, rdx
0x180009bbb  and     rdx, rax; DestinationSize
0x180009bbe  call    cs:__imp_memcpy_s
0x180009bc4  add     qword ptr [rbx+8], 10h
0x180009bc9  mov     rax, [rbx+8]
0x180009bcd  sub     rax, [rbx]
0x180009bd0  shr     rax, 4
0x180009bd4  mov     [rdi], rax
0x180009bd7  mov     rbx, [rsp+38h+arg_0]
0x180009bdc  add     rsp, 30h
0x180009be0  pop     rdi
0x180009be1  retn
0x180009be2  mov     [rcx+rax*8], r8
0x180009be6  mov     [rcx+rax*8+8], r9
0x180009beb  mov     [rdi], rdx
0x180009bee  jmp     short loc_180009BD7
```
