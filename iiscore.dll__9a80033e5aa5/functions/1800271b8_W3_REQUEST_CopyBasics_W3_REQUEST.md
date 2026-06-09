# W3_REQUEST::CopyBasics(W3_REQUEST *)

- ea: `0x1800271b8`
- end: `0x180027322`
- name: `?CopyBasics@W3_REQUEST@@QEAAJPEAV1@@Z`
- size: `362`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, struct W3_REQUEST *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002701c`

## callees

- `0x1800271b8`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800272ea`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800272ea`

## pseudocode

```c
int __fastcall W3_REQUEST::CopyBasics(W3_REQUEST *this, struct W3_REQUEST *a2)
{
  __int64 v4; // rdx
  int result; // eax
  __int64 v6; // rcx

  if ( a2 )
  {
    ++*((_DWORD *)a2 + 12);
    v4 = *((_QWORD *)a2 + 5);
    *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) = *(_DWORD *)(v4 + 36);
    *(_WORD *)(*((_QWORD *)this + 5) + 40LL) = *(_WORD *)(v4 + 40);
    *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = *(_QWORD *)(v4 + 48);
    *(_WORD *)(*((_QWORD *)this + 5) + 42LL) = *(_WORD *)(v4 + 42);
    *(_QWORD *)(*((_QWORD *)this + 5) + 56LL) = *(_QWORD *)(v4 + 56);
    *(_WORD *)(*((_QWORD *)this + 5) + 64LL) = *(_WORD *)(v4 + 64);
    *(_QWORD *)(*((_QWORD *)this + 5) + 72LL) = *(_QWORD *)(v4 + 72);
    *(_WORD *)(*((_QWORD *)this + 5) + 66LL) = *(_WORD *)(v4 + 66);
    *(_QWORD *)(*((_QWORD *)this + 5) + 80LL) = *(_QWORD *)(v4 + 80);
    *(_WORD *)(*((_QWORD *)this + 5) + 68LL) = *(_WORD *)(v4 + 68);
    *(_QWORD *)(*((_QWORD *)this + 5) + 88LL) = *(_QWORD *)(v4 + 88);
    *(_WORD *)(*((_QWORD *)this + 5) + 70LL) = *(_WORD *)(v4 + 70);
    *(_QWORD *)(*((_QWORD *)this + 5) + 96LL) = *(_QWORD *)(v4 + 96);
    result = STRU::Copy((W3_REQUEST *)((char *)this + 56), (struct W3_REQUEST *)((char *)a2 + 56));
    if ( result < 0 )
      return result;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 40LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 42LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 56LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 64LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 72LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 66LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 80LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 68LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 88LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 70LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 96LL) = 0;
  }
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 28) = *(_QWORD *)(v6 + 72);
  *((_QWORD *)this + 29) = *(_QWORD *)(v6 + 88);
  *((_DWORD *)this + 60) = *(unsigned __int16 *)(v6 + 64) >> 1;
  return 0;
}

```

## disassembly

```asm
0x1800271b8  push    rbx
0x1800271ba  sub     rsp, 20h
0x1800271be  mov     r8, rdx
0x1800271c1  mov     rbx, rcx
0x1800271c4  test    rdx, rdx
0x1800271c7  jnz     short loc_180027241
0x1800271c9  mov     rax, [rcx+28h]
0x1800271cd  mov     [rax+24h], edx
0x1800271d0  xor     eax, eax
0x1800271d2  mov     rdx, [rcx+28h]
0x1800271d6  mov     [rdx+28h], ax
0x1800271da  mov     rax, [rcx+28h]
0x1800271de  mov     [rax+30h], r8
0x1800271e2  xor     eax, eax
0x1800271e4  mov     rdx, [rcx+28h]
0x1800271e8  mov     [rdx+2Ah], ax
0x1800271ec  mov     rax, [rcx+28h]
0x1800271f0  mov     [rax+38h], r8
0x1800271f4  xor     eax, eax
0x1800271f6  mov     rcx, [rcx+28h]
0x1800271fa  mov     [rcx+40h], ax
0x1800271fe  mov     rax, [rbx+28h]
0x180027202  mov     [rax+48h], r8
0x180027206  xor     eax, eax
0x180027208  mov     rcx, [rbx+28h]
0x18002720c  mov     [rcx+42h], ax
0x180027210  mov     rax, [rbx+28h]
0x180027214  mov     [rax+50h], r8
0x180027218  xor     eax, eax
0x18002721a  mov     rcx, [rbx+28h]
0x18002721e  mov     [rcx+44h], ax
0x180027222  mov     rax, [rbx+28h]
0x180027226  mov     [rax+58h], r8
0x18002722a  xor     eax, eax
0x18002722c  mov     rcx, [rbx+28h]
0x180027230  mov     [rcx+46h], ax
0x180027234  mov     rax, [rbx+28h]
0x180027238  mov     [rax+60h], r8
0x18002723c  jmp     loc_1800272F4
0x180027241  inc     dword ptr [rdx+30h]
0x180027244  mov     rdx, [rdx+28h]
0x180027248  mov     rcx, [rcx+28h]
0x18002724c  mov     eax, [rdx+24h]
0x18002724f  mov     [rcx+24h], eax
0x180027252  movzx   eax, word ptr [rdx+28h]
0x180027256  mov     rcx, [rbx+28h]
0x18002725a  mov     [rcx+28h], ax
0x18002725e  mov     rax, [rdx+30h]
0x180027262  mov     rcx, [rbx+28h]
0x180027266  mov     [rcx+30h], rax
0x18002726a  movzx   eax, word ptr [rdx+2Ah]
0x18002726e  mov     rcx, [rbx+28h]
0x180027272  mov     [rcx+2Ah], ax
0x180027276  mov     rax, [rdx+38h]
0x18002727a  mov     rcx, [rbx+28h]
0x18002727e  mov     [rcx+38h], rax
0x180027282  movzx   eax, word ptr [rdx+40h]
0x180027286  mov     rcx, [rbx+28h]
0x18002728a  mov     [rcx+40h], ax
0x18002728e  mov     rax, [rdx+48h]
0x180027292  mov     rcx, [rbx+28h]
0x180027296  mov     [rcx+48h], rax
0x18002729a  movzx   eax, word ptr [rdx+42h]
0x18002729e  mov     rcx, [rbx+28h]
0x1800272a2  mov     [rcx+42h], ax
0x1800272a6  mov     rax, [rdx+50h]
0x1800272aa  mov     rcx, [rbx+28h]
0x1800272ae  mov     [rcx+50h], rax
0x1800272b2  movzx   eax, word ptr [rdx+44h]
0x1800272b6  mov     rcx, [rbx+28h]
0x1800272ba  mov     [rcx+44h], ax
0x1800272be  mov     rax, [rdx+58h]
0x1800272c2  mov     rcx, [rbx+28h]
0x1800272c6  mov     [rcx+58h], rax
0x1800272ca  movzx   eax, word ptr [rdx+46h]
0x1800272ce  mov     rcx, [rbx+28h]
0x1800272d2  mov     [rcx+46h], ax
0x1800272d6  mov     rcx, [rbx+28h]
0x1800272da  mov     rax, [rdx+60h]
0x1800272de  lea     rdx, [r8+38h]
0x1800272e2  mov     [rcx+60h], rax
0x1800272e6  lea     rcx, [rbx+38h]
0x1800272ea  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800272f0  test    eax, eax
0x1800272f2  js      short loc_18002731C
0x1800272f4  mov     rcx, [rbx+28h]
0x1800272f8  mov     rax, [rcx+48h]
0x1800272fc  mov     [rbx+0E0h], rax
0x180027303  mov     rax, [rcx+58h]
0x180027307  mov     [rbx+0E8h], rax
0x18002730e  movzx   eax, word ptr [rcx+40h]
0x180027312  shr     eax, 1
0x180027314  mov     [rbx+0F0h], eax
0x18002731a  xor     eax, eax
0x18002731c  add     rsp, 20h
0x180027320  pop     rbx
0x180027321  retn
```
