# QuicPartitionUninitialize

- ea: `0x14002d7fc`
- end: `0x14002d923`
- name: `QuicPartitionUninitialize`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002818c`
- `0x140028728`

## callees

- `0x14002d7fc`
- `0x140034814`
- `0x140034d20`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d82d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d840`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d853`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d866`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d879`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d88c`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8a7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8c4`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8d7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8ea`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8fd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d82d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d840`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d853`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d866`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d879`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d88c`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8a7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8c4`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8d7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8ea`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14002d8fd`

## pseudocode

```c
__int64 __fastcall QuicPartitionUninitialize(__int64 a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rsi
  struct _LOOKASIDE_LIST_EX *v4; // rdi
  __int64 v5; // rsi

  v2 = (_QWORD *)(a1 + 64);
  v3 = 2;
  do
  {
    CxPlatKeyFree(*v2);
    v2 += 2;
    --v3;
  }
  while ( v3 );
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 96));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 192));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 288));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 384));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 480));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 576));
  v4 = (struct _LOOKASIDE_LIST_EX *)(a1 + 672);
  v5 = 12;
  do
  {
    ExDeleteLookasideListEx(v4++);
    --v5;
  }
  while ( v5 );
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 1824));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 1920));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 2016));
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 2112));
  return CxPlatHashFree(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x14002d7fc  mov     [rsp+arg_0], rbx
0x14002d801  mov     [rsp+arg_8], rsi
0x14002d806  push    rdi
0x14002d807  sub     rsp, 20h
0x14002d80b  mov     rbx, rcx
0x14002d80e  lea     rdi, [rcx+40h]
0x14002d812  mov     esi, 2
0x14002d817  mov     rcx, [rdi]
0x14002d81a  call    CxPlatKeyFree
0x14002d81f  lea     rdi, [rdi+10h]
0x14002d823  sub     rsi, 1
0x14002d827  jnz     short loc_14002D817
0x14002d829  lea     rcx, [rbx+60h]; Lookaside
0x14002d82d  call    cs:__imp_ExDeleteLookasideListEx
0x14002d834  nop     dword ptr [rax+rax+00h]
0x14002d839  lea     rcx, [rbx+0C0h]; Lookaside
0x14002d840  call    cs:__imp_ExDeleteLookasideListEx
0x14002d847  nop     dword ptr [rax+rax+00h]
0x14002d84c  lea     rcx, [rbx+120h]; Lookaside
0x14002d853  call    cs:__imp_ExDeleteLookasideListEx
0x14002d85a  nop     dword ptr [rax+rax+00h]
0x14002d85f  lea     rcx, [rbx+180h]; Lookaside
0x14002d866  call    cs:__imp_ExDeleteLookasideListEx
0x14002d86d  nop     dword ptr [rax+rax+00h]
0x14002d872  lea     rcx, [rbx+1E0h]; Lookaside
0x14002d879  call    cs:__imp_ExDeleteLookasideListEx
0x14002d880  nop     dword ptr [rax+rax+00h]
0x14002d885  lea     rcx, [rbx+240h]; Lookaside
0x14002d88c  call    cs:__imp_ExDeleteLookasideListEx
0x14002d893  nop     dword ptr [rax+rax+00h]
0x14002d898  lea     rdi, [rbx+2A0h]
0x14002d89f  mov     esi, 0Ch
0x14002d8a4  mov     rcx, rdi; Lookaside
0x14002d8a7  call    cs:__imp_ExDeleteLookasideListEx
0x14002d8ae  nop     dword ptr [rax+rax+00h]
0x14002d8b3  add     rdi, 60h ; '`'
0x14002d8b7  sub     rsi, 1
0x14002d8bb  jnz     short loc_14002D8A4
0x14002d8bd  lea     rcx, [rbx+720h]; Lookaside
0x14002d8c4  call    cs:__imp_ExDeleteLookasideListEx
0x14002d8cb  nop     dword ptr [rax+rax+00h]
0x14002d8d0  lea     rcx, [rbx+780h]; Lookaside
0x14002d8d7  call    cs:__imp_ExDeleteLookasideListEx
0x14002d8de  nop     dword ptr [rax+rax+00h]
0x14002d8e3  lea     rcx, [rbx+7E0h]; Lookaside
0x14002d8ea  call    cs:__imp_ExDeleteLookasideListEx
0x14002d8f1  nop     dword ptr [rax+rax+00h]
0x14002d8f6  lea     rcx, [rbx+840h]; Lookaside
0x14002d8fd  call    cs:__imp_ExDeleteLookasideListEx
0x14002d904  nop     dword ptr [rax+rax+00h]
0x14002d909  mov     rcx, [rbx+20h]
0x14002d90d  call    CxPlatHashFree
0x14002d912  mov     rbx, [rsp+28h+arg_0]
0x14002d917  mov     rsi, [rsp+28h+arg_8]
0x14002d91c  add     rsp, 20h
0x14002d920  pop     rdi
0x14002d921  retn
```
