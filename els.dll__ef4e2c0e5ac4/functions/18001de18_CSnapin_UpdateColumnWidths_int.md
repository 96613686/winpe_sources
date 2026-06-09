# CSnapin::_UpdateColumnWidths(int)

- ea: `0x18001de18`
- end: `0x18001de8d`
- name: `?_UpdateColumnWidths@CSnapin@@AEAAXH@Z`
- size: `117`
- prototype: `void __fastcall(CSnapin *__hidden this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001c680`
- `0x18001ce30`
- `0x18001daf4`

## callees

- `0x18001de18`
- `0x180024010`

## pseudocode

```c
void __fastcall CSnapin::_UpdateColumnWidths(CSnapin *this, int a2)
{
  int v3; // edi
  int v4; // esi
  _DWORD *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v4 = a2 != 0 ? 4 : 8;
  v5 = (_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 1488);
  do
  {
    v6 = *((_QWORD *)this + 204);
    v8 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v6 + 64LL))(v6, (unsigned int)v3, &v8) >= 0 )
    {
      v7 = v8;
      if ( v8 != *v5 )
      {
        *((_WORD *)this + 40) |= 2u;
        *v5 = v7;
      }
    }
    ++v3;
    ++v5;
  }
  while ( v3 < v4 );
}

```

## disassembly

```asm
0x18001de18  push    rbx
0x18001de1a  push    rbp
0x18001de1b  push    rsi
0x18001de1c  push    rdi
0x18001de1d  sub     rsp, 28h
0x18001de21  mov     eax, edx
0x18001de23  mov     rbp, rcx
0x18001de26  neg     eax
0x18001de28  sbb     esi, esi
0x18001de2a  xor     edi, edi
0x18001de2c  and     esi, 0FFFFFFFCh
0x18001de2f  add     esi, 8
0x18001de32  neg     edx
0x18001de34  sbb     rbx, rbx
0x18001de37  and     rbx, 0FFFFFFFFFFFFFFF0h
0x18001de3b  add     rbx, 5D0h
0x18001de42  add     rbx, rcx
0x18001de45  mov     rcx, [rbp+660h]
0x18001de4c  lea     r8, [rsp+48h+arg_8]
0x18001de51  mov     [rsp+48h+arg_8], 0
0x18001de59  mov     edx, edi
0x18001de5b  mov     rax, [rcx]
0x18001de5e  mov     rax, [rax+40h]
0x18001de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de67  test    eax, eax
0x18001de69  js      short loc_18001DE7A
0x18001de6b  mov     eax, [rsp+48h+arg_8]
0x18001de6f  cmp     eax, [rbx]
0x18001de71  jz      short loc_18001DE7A
0x18001de73  or      word ptr [rbp+50h], 2
0x18001de78  mov     [rbx], eax
0x18001de7a  inc     edi
0x18001de7c  add     rbx, 4
0x18001de80  cmp     edi, esi
0x18001de82  jl      short loc_18001DE45
0x18001de84  add     rsp, 28h
0x18001de88  pop     rdi
0x18001de89  pop     rsi
0x18001de8a  pop     rbp
0x18001de8b  pop     rbx
0x18001de8c  retn
```
