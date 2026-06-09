# FILTERING_RULE::QueryDependencyFlags(ushort const *)

- ea: `0x18000704c`
- end: `0x1800070e4`
- name: `?QueryDependencyFlags@FILTERING_RULE@@QEAAKPEBG@Z`
- size: `152`
- prototype: `unsigned int __fastcall(FILTERING_RULE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010c0`

## callees

- `0x18000704c`

## import_xrefs

- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007067`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007067`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800070a0`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800070a0`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800070cb`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800070cb`

## pseudocode

```c
__int64 __fastcall FILTERING_RULE::QueryDependencyFlags(FILTERING_RULE *this, char *a2)
{
  MULTISZ *v2; // rsi
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rax
  int v8; // r9d
  int v9; // ecx

  v2 = (FILTERING_RULE *)((char *)this + 128);
  v5 = 0;
  v6 = MULTISZ::First((FILTERING_RULE *)((char *)this + 128));
  if ( v6 )
  {
    while ( v6 )
    {
      v7 = v6;
      do
      {
        v8 = *(const unsigned __int16 *)((char *)v7 + a2 - (char *)v6);
        v9 = *v7 - v8;
        if ( v9 )
          break;
        ++v7;
      }
      while ( v8 );
      if ( !v9 )
        goto LABEL_8;
      v6 = MULTISZ::Next(v2, v6);
    }
  }
  else
  {
LABEL_8:
    v5 = (*((_DWORD *)this + 14) != 0 ? 2 : 0) | 4;
    if ( !*((_DWORD *)this + 15) )
      v5 = *((_DWORD *)this + 14) != 0 ? 2 : 0;
    if ( *((_DWORD *)this + 16) || MULTISZA::First((FILTERING_RULE *)((char *)this + 72)) )
      v5 |= 0x10u;
  }
  return v5;
}

```

## disassembly

```asm
0x18000704c  push    rbx
0x18000704e  push    rbp
0x18000704f  push    rsi
0x180007050  push    rdi
0x180007051  sub     rsp, 28h
0x180007055  lea     rsi, [rcx+80h]
0x18000705c  mov     rdi, rcx
0x18000705f  mov     rcx, rsi
0x180007062  mov     rbp, rdx
0x180007065  xor     ebx, ebx
0x180007067  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18000706d  mov     rdx, rax
0x180007070  test    rax, rax
0x180007073  jz      short loc_1800070AB
0x180007075  test    rdx, rdx
0x180007078  jz      short loc_1800070D9
0x18000707a  mov     r8, rbp
0x18000707d  mov     rax, rdx
0x180007080  sub     r8, rdx
0x180007083  movzx   ecx, word ptr [rax]
0x180007086  movzx   r9d, word ptr [rax+r8]
0x18000708b  sub     ecx, r9d
0x18000708e  jnz     short loc_180007099
0x180007090  add     rax, 2
0x180007094  test    r9d, r9d
0x180007097  jnz     short loc_180007083
0x180007099  test    ecx, ecx
0x18000709b  jz      short loc_1800070AB
0x18000709d  mov     rcx, rsi
0x1800070a0  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800070a6  mov     rdx, rax
0x1800070a9  jmp     short loc_180007075
0x1800070ab  mov     eax, [rdi+38h]
0x1800070ae  neg     eax
0x1800070b0  sbb     ecx, ecx
0x1800070b2  and     ecx, 2
0x1800070b5  mov     ebx, ecx
0x1800070b7  or      ebx, 4
0x1800070ba  cmp     dword ptr [rdi+3Ch], 0
0x1800070be  cmovz   ebx, ecx
0x1800070c1  cmp     dword ptr [rdi+40h], 0
0x1800070c5  jnz     short loc_1800070D6
0x1800070c7  lea     rcx, [rdi+48h]
0x1800070cb  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x1800070d1  test    rax, rax
0x1800070d4  jz      short loc_1800070D9
0x1800070d6  or      ebx, 10h
0x1800070d9  mov     eax, ebx
0x1800070db  add     rsp, 28h
0x1800070df  pop     rdi
0x1800070e0  pop     rsi
0x1800070e1  pop     rbp
0x1800070e2  pop     rbx
0x1800070e3  retn
```
