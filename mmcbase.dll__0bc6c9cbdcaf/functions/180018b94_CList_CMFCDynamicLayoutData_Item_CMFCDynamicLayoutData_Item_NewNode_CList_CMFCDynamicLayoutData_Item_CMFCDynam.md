# CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::NewNode(CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::CNode *,CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::CNode *)

- ea: `0x180018b94`
- end: `0x180018c3b`
- name: `?NewNode@?$CList@UItem@CMFCDynamicLayoutData@@AEAU12@@@IEAAPEAUCNode@1@PEAU21@0@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018da0`

## callees

- `0x180018b94`

## import_xrefs

- `MFC42u!__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z` at `0x180018bb8`
- `MFC42u!__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z` at `0x180018bb8`

## pseudocode

```c
_QWORD *__fastcall CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::NewNode(__int64 a1, __int64 a2)
{
  struct CPlex *v4; // rax
  int v5; // r8d
  _QWORD *i; // rdx
  _QWORD *v7; // rdx
  _QWORD *v8; // rcx
  int v9; // eax

  if ( !*(_QWORD *)(a1 + 24) )
  {
    v4 = CPlex::Create((struct CPlex **)(a1 + 32), *(_DWORD *)(a1 + 40), 0x20u);
    v5 = *(_DWORD *)(a1 + 40) - 1;
    for ( i = (_QWORD *)((char *)v4 + 32 * v5 + 16); v5 >= 0; --v5 )
    {
      *i = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = i;
      i -= 4;
    }
  }
  v7 = *(_QWORD **)(a1 + 24);
  v8 = v7 + 2;
  *(_QWORD *)(a1 + 24) = *v7;
  v9 = 1;
  v7[1] = a2;
  *v7 = 0;
  ++*(_DWORD *)(a1 + 16);
  *((_OWORD *)v7 + 1) = 0;
  do
  {
    *v8 = 0;
    v8[1] = 0;
    v8 += 2;
    --v9;
  }
  while ( v9 );
  return v7;
}

```

## disassembly

```asm
0x180018b94  mov     [rsp+arg_0], rbx
0x180018b99  push    rdi
0x180018b9a  sub     rsp, 20h
0x180018b9e  cmp     qword ptr [rcx+18h], 0
0x180018ba3  mov     rdi, rdx
0x180018ba6  mov     rbx, rcx
0x180018ba9  jnz     short loc_180018BED
0x180018bab  mov     edx, [rbx+28h]
0x180018bae  add     rcx, 20h ; ' '
0x180018bb2  mov     r8d, 20h ; ' '
0x180018bb8  call    cs:__imp_?Create@CPlex@@SAPEAU1@AEAPEAU1@II@Z; CPlex::Create(CPlex * &,uint,uint)
0x180018bbe  mov     r8d, [rbx+28h]
0x180018bc2  dec     r8d
0x180018bc5  movsxd  rcx, r8d
0x180018bc8  shl     rcx, 5
0x180018bcc  lea     rdx, [rax+10h]
0x180018bd0  add     rdx, rcx
0x180018bd3  test    r8d, r8d
0x180018bd6  js      short loc_180018BED
0x180018bd8  mov     rax, [rbx+18h]
0x180018bdc  mov     [rdx], rax
0x180018bdf  mov     [rbx+18h], rdx
0x180018be3  sub     rdx, 20h ; ' '
0x180018be7  sub     r8d, 1
0x180018beb  jns     short loc_180018BD8
0x180018bed  mov     rdx, [rbx+18h]
0x180018bf1  xorps   xmm0, xmm0
0x180018bf4  mov     rax, [rdx]
0x180018bf7  lea     rcx, [rdx+10h]
0x180018bfb  mov     [rbx+18h], rax
0x180018bff  mov     eax, 1
0x180018c04  mov     [rdx+8], rdi
0x180018c08  mov     qword ptr [rdx], 0
0x180018c0f  inc     dword ptr [rbx+10h]
0x180018c12  movups  xmmword ptr [rcx], xmm0
0x180018c15  mov     qword ptr [rcx], 0
0x180018c1c  mov     qword ptr [rcx+8], 0
0x180018c24  lea     rcx, [rcx+10h]
0x180018c28  sub     eax, 1
0x180018c2b  jnz     short loc_180018C15
0x180018c2d  mov     rbx, [rsp+28h+arg_0]
0x180018c32  mov     rax, rdx
0x180018c35  add     rsp, 20h
0x180018c39  pop     rdi
0x180018c3a  retn
```
