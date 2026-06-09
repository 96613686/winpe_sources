# CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::AddTail(AFX_DYNAMIC_LAYOUT_ITEM *)

- ea: `0x180018454`
- end: `0x1800184fa`
- name: `?AddTail@?$CList@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@PEAU1@@@QEAAPEAU__POSITION@@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018360`

## callees

- `0x180018454`

## import_xrefs

- `MFC42u!__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z` at `0x180018481`
- `MFC42u!__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z` at `0x180018481`

## pseudocode

```c
_QWORD *__fastcall CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::AddTail(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  struct CPlex *v5; // rax
  int v6; // r8d
  _QWORD *i; // rcx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  _QWORD *result; // rax

  v3 = *(_QWORD *)(a1 + 8);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v5 = CPlex::Create((struct CPlex **)(a1 + 32), *(_DWORD *)(a1 + 40), 0x18u);
    v6 = *(_DWORD *)(a1 + 40) - 1;
    for ( i = (_QWORD *)((char *)v5 + 24 * v6 + 16); v6 >= 0; --v6 )
    {
      *i = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = i;
      i -= 3;
    }
  }
  v8 = *(_QWORD **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = *v8;
  v8[1] = v3;
  *v8 = 0;
  ++*(_DWORD *)(a1 + 16);
  v8[2] = a2;
  v9 = *(_QWORD **)(a1 + 8);
  if ( v9 )
    *v9 = v8;
  else
    *(_QWORD *)a1 = v8;
  result = v8;
  *(_QWORD *)(a1 + 8) = v8;
  return result;
}

```

## disassembly

```asm
0x180018454  mov     [rsp+arg_0], rbx
0x180018459  mov     [rsp+arg_8], rsi
0x18001845e  push    rdi
0x18001845f  sub     rsp, 20h
0x180018463  cmp     qword ptr [rcx+18h], 0
0x180018468  mov     rdi, rdx
0x18001846b  mov     rsi, [rcx+8]
0x18001846f  mov     rbx, rcx
0x180018472  jnz     short loc_1800184B5
0x180018474  mov     edx, [rbx+28h]
0x180018477  add     rcx, 20h ; ' '
0x18001847b  mov     r8d, 18h
0x180018481  call    cs:__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z; CPlex::Create(CPlex * &,uint,uint)
0x180018487  mov     r8d, [rbx+28h]
0x18001848b  sub     r8d, 1
0x18001848f  movsxd  rcx, r8d
0x180018492  lea     rcx, [rcx+rcx*2]
0x180018496  lea     rcx, [rcx+2]
0x18001849a  lea     rcx, [rax+rcx*8]
0x18001849e  js      short loc_1800184B5
0x1800184a0  mov     rax, [rbx+18h]
0x1800184a4  mov     [rcx], rax
0x1800184a7  mov     [rbx+18h], rcx
0x1800184ab  sub     rcx, 18h
0x1800184af  sub     r8d, 1
0x1800184b3  jns     short loc_1800184A0
0x1800184b5  mov     rcx, [rbx+18h]
0x1800184b9  mov     rax, [rcx]
0x1800184bc  mov     [rbx+18h], rax
0x1800184c0  mov     [rcx+8], rsi
0x1800184c4  mov     qword ptr [rcx], 0
0x1800184cb  inc     dword ptr [rbx+10h]
0x1800184ce  mov     [rcx+10h], rdi
0x1800184d2  mov     rax, [rbx+8]
0x1800184d6  test    rax, rax
0x1800184d9  jz      short loc_1800184E0
0x1800184db  mov     [rax], rcx
0x1800184de  jmp     short loc_1800184E3
0x1800184e0  mov     [rbx], rcx
0x1800184e3  mov     rsi, [rsp+28h+arg_8]
0x1800184e8  mov     rax, rcx
0x1800184eb  mov     [rbx+8], rcx
0x1800184ef  mov     rbx, [rsp+28h+arg_0]
0x1800184f4  add     rsp, 20h
0x1800184f8  pop     rdi
0x1800184f9  retn
```
