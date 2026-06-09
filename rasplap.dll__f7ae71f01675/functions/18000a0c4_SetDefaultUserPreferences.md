# SetDefaultUserPreferences

- ea: `0x18000a0c4`
- end: `0x18000a2a9`
- name: `SetDefaultUserPreferences`
- size: `485`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009368`
- `0x180009918`

## callees

- `0x180008854`
- `0x18000929c`
- `0x18000a0c4`
- `0x18000aad0`
- `0x18000ab10`

## pseudocode

```c
__int64 __fastcall SetDefaultUserPreferences(_OWORD *a1, int a2)
{
  _QWORD *List; // rax
  bool v6; // zf
  __int64 PszNode; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax

  if ( !a1 )
    return 87;
  *a1 = xmmword_18000F560;
  a1[1] = xmmword_18000F570;
  a1[2] = xmmword_18000F580;
  a1[3] = xmmword_18000F590;
  a1[4] = xmmword_18000F5A0;
  a1[5] = xmmword_18000F5B0;
  a1[6] = xmmword_18000F5C0;
  a1[7] = xmmword_18000F5D0;
  a1[8] = xmmword_18000F5E0;
  a1[9] = xmmword_18000F5F0;
  a1[10] = xmmword_18000F600;
  *((_QWORD *)a1 + 22) = 0;
  *((_QWORD *)a1 + 9) = DtlCreateList();
  *((_QWORD *)a1 + 14) = DtlCreateList();
  *((_QWORD *)a1 + 15) = DtlCreateList();
  *((_QWORD *)a1 + 17) = DtlCreateList();
  *((_QWORD *)a1 + 18) = DtlCreateList();
  List = DtlCreateList();
  v6 = *((_QWORD *)a1 + 9) == 0;
  *((_QWORD *)a1 + 19) = List;
  if ( !v6 && *((_QWORD *)a1 + 14) && *((_QWORD *)a1 + 15) && *((_QWORD *)a1 + 17) && *((_QWORD *)a1 + 18) && List )
  {
    PszNode = CreatePszNode(L"0,");
    if ( PszNode )
      DtlAddNodeLast(*((_QWORD *)a1 + 17), PszNode);
    v8 = CreatePszNode(L"9,");
    if ( v8 )
      DtlAddNodeLast(*((_QWORD *)a1 + 17), v8);
    v9 = CreatePszNode(L"8,");
    if ( v9 )
      DtlAddNodeLast(*((_QWORD *)a1 + 17), v9);
    v10 = CreatePszNode(L"70#");
    if ( v10 )
      DtlAddNodeLast(*((_QWORD *)a1 + 17), v10);
    if ( a2 == 1 )
    {
      *((_DWORD *)a1 + 3) = 0;
      *((_DWORD *)a1 + 8) = 1;
    }
    *((_DWORD *)a1 + 44) = 1;
    return 0;
  }
  else
  {
    DestroyUserPreferences(a1);
    return 8;
  }
}

```

## disassembly

```asm
0x18000a0c4  mov     [rsp+arg_0], rbx
0x18000a0c9  push    rdi
0x18000a0ca  sub     rsp, 20h
0x18000a0ce  mov     edi, edx
0x18000a0d0  mov     rbx, rcx
0x18000a0d3  test    rcx, rcx
0x18000a0d6  jnz     short loc_18000A0E0
0x18000a0d8  lea     eax, [rcx+57h]
0x18000a0db  jmp     loc_18000A29E
0x18000a0e0  movaps  xmm0, cs:xmmword_18000F560
0x18000a0e7  movups  xmmword ptr [rcx], xmm0
0x18000a0ea  movaps  xmm1, cs:xmmword_18000F570
0x18000a0f1  movups  xmmword ptr [rcx+10h], xmm1
0x18000a0f5  movaps  xmm0, cs:xmmword_18000F580
0x18000a0fc  movups  xmmword ptr [rcx+20h], xmm0
0x18000a100  movaps  xmm1, cs:xmmword_18000F590
0x18000a107  movups  xmmword ptr [rcx+30h], xmm1
0x18000a10b  movaps  xmm0, cs:xmmword_18000F5A0
0x18000a112  movups  xmmword ptr [rcx+40h], xmm0
0x18000a116  movaps  xmm1, cs:xmmword_18000F5B0
0x18000a11d  movups  xmmword ptr [rcx+50h], xmm1
0x18000a121  movaps  xmm0, cs:xmmword_18000F5C0
0x18000a128  movups  xmmword ptr [rcx+60h], xmm0
0x18000a12c  movaps  xmm1, cs:xmmword_18000F5D0
0x18000a133  movups  xmmword ptr [rcx+70h], xmm1
0x18000a137  movaps  xmm0, cs:xmmword_18000F5E0
0x18000a13e  movups  xmmword ptr [rcx+80h], xmm0
0x18000a145  movaps  xmm1, cs:xmmword_18000F5F0
0x18000a14c  movups  xmmword ptr [rcx+90h], xmm1
0x18000a153  movaps  xmm0, cs:xmmword_18000F600
0x18000a15a  movups  xmmword ptr [rcx+0A0h], xmm0
0x18000a161  mov     rax, cs:qword_18000F610
0x18000a168  mov     [rcx+0B0h], rax
0x18000a16f  call    DtlCreateList
0x18000a174  mov     [rbx+48h], rax
0x18000a178  call    DtlCreateList
0x18000a17d  mov     [rbx+70h], rax
0x18000a181  call    DtlCreateList
0x18000a186  mov     [rbx+78h], rax
0x18000a18a  call    DtlCreateList
0x18000a18f  mov     [rbx+88h], rax
0x18000a196  call    DtlCreateList
0x18000a19b  mov     [rbx+90h], rax
0x18000a1a2  call    DtlCreateList
0x18000a1a7  cmp     qword ptr [rbx+48h], 0
0x18000a1ac  mov     [rbx+98h], rax
0x18000a1b3  jz      loc_18000A291
0x18000a1b9  cmp     qword ptr [rbx+70h], 0
0x18000a1be  jz      loc_18000A291
0x18000a1c4  cmp     qword ptr [rbx+78h], 0
0x18000a1c9  jz      loc_18000A291
0x18000a1cf  cmp     qword ptr [rbx+88h], 0
0x18000a1d7  jz      loc_18000A291
0x18000a1dd  cmp     qword ptr [rbx+90h], 0
0x18000a1e5  jz      loc_18000A291
0x18000a1eb  test    rax, rax
0x18000a1ee  jz      loc_18000A291
0x18000a1f4  lea     rcx, a0; "0,"
0x18000a1fb  call    CreatePszNode
0x18000a200  test    rax, rax
0x18000a203  jz      short loc_18000A214
0x18000a205  mov     rcx, [rbx+88h]
0x18000a20c  mov     rdx, rax
0x18000a20f  call    DtlAddNodeLast
0x18000a214  lea     rcx, a9; "9,"
0x18000a21b  call    CreatePszNode
0x18000a220  test    rax, rax
0x18000a223  jz      short loc_18000A234
0x18000a225  mov     rcx, [rbx+88h]
0x18000a22c  mov     rdx, rax
0x18000a22f  call    DtlAddNodeLast
0x18000a234  lea     rcx, a8; "8,"
0x18000a23b  call    CreatePszNode
0x18000a240  test    rax, rax
0x18000a243  jz      short loc_18000A254
0x18000a245  mov     rcx, [rbx+88h]
0x18000a24c  mov     rdx, rax
0x18000a24f  call    DtlAddNodeLast
0x18000a254  lea     rcx, a70; "70#"
0x18000a25b  call    CreatePszNode
0x18000a260  test    rax, rax
0x18000a263  jz      short loc_18000A274
0x18000a265  mov     rcx, [rbx+88h]
0x18000a26c  mov     rdx, rax
0x18000a26f  call    DtlAddNodeLast
0x18000a274  mov     eax, 1
0x18000a279  cmp     edi, eax
0x18000a27b  jnz     short loc_18000A287
0x18000a27d  mov     dword ptr [rbx+0Ch], 0
0x18000a284  mov     [rbx+20h], eax
0x18000a287  mov     [rbx+0B0h], eax
0x18000a28d  xor     eax, eax
0x18000a28f  jmp     short loc_18000A29E
0x18000a291  mov     rcx, rbx; void *
0x18000a294  call    DestroyUserPreferences
0x18000a299  mov     eax, 8
0x18000a29e  mov     rbx, [rsp+28h+arg_0]
0x18000a2a3  add     rsp, 20h
0x18000a2a7  pop     rdi
0x18000a2a8  retn
```
