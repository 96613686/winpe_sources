# CdFindNameLink

- ea: `0x140017638`
- end: `0x1400176a1`
- name: `CdFindNameLink`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400176a8`

## callees

- `0x1400160f8`
- `0x140017638`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14001768d`
- `ntoskrnl!RtlSplay` at `0x14001768d`

## pseudocode

```c
struct _RTL_SPLAY_LINKS *__fastcall CdFindNameLink(__int64 a1, struct _RTL_SPLAY_LINKS **a2, const void **a3)
{
  struct _RTL_SPLAY_LINKS *i; // rbx
  int v6; // eax

  for ( i = *a2; ; i = i->RightChild )
  {
    while ( 1 )
    {
      if ( !i )
        return 0;
      v6 = CdFullCompareNames(a1, (const void **)&i[1].Parent, a3);
      if ( v6 != 1 )
        break;
      i = i->LeftChild;
    }
    if ( v6 != -1 )
      break;
  }
  *a2 = RtlSplay(i);
  return i;
}

```

## disassembly

```asm
0x140017638  mov     [rsp+arg_0], rbx
0x14001763d  mov     [rsp+arg_8], rsi
0x140017642  push    rdi
0x140017643  sub     rsp, 20h
0x140017647  mov     rbx, [rdx]
0x14001764a  mov     rsi, r8
0x14001764d  mov     rdi, rdx
0x140017650  jmp     short loc_140017672
0x140017652  lea     rdx, [rbx+18h]
0x140017656  mov     r8, rsi
0x140017659  call    CdFullCompareNames
0x14001765e  cmp     eax, 1
0x140017661  jnz     short loc_140017669
0x140017663  mov     rbx, [rbx+8]
0x140017667  jmp     short loc_140017672
0x140017669  cmp     eax, 0FFFFFFFFh
0x14001766c  jnz     short loc_14001768A
0x14001766e  mov     rbx, [rbx+10h]
0x140017672  test    rbx, rbx
0x140017675  jnz     short loc_140017652
0x140017677  xor     eax, eax
0x140017679  mov     rbx, [rsp+28h+arg_0]
0x14001767e  mov     rsi, [rsp+28h+arg_8]
0x140017683  add     rsp, 20h
0x140017687  pop     rdi
0x140017688  retn
0x14001768a  mov     rcx, rbx; Links
0x14001768d  call    cs:__imp_RtlSplay
0x140017694  nop     dword ptr [rax+rax+00h]
0x140017699  mov     [rdi], rax
0x14001769c  mov     rax, rbx
0x14001769f  jmp     short loc_140017679
```
