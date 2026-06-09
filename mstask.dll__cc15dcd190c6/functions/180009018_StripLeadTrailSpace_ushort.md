# StripLeadTrailSpace(ushort *)

- ea: `0x180009018`
- end: `0x1800090ad`
- name: `?StripLeadTrailSpace@@YAXPEAG@Z`
- size: `149`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007860`
- `0x1800114b4`
- `0x180011568`
- `0x180011fc0`
- `0x180012a04`

## callees

- `0x180009018`
- `0x18001aa8e`

## import_xrefs

- `msvcrt!wcsspn` at `0x18000902c`
- `msvcrt!wcsspn` at `0x18000902c`

## pseudocode

```c
void __fastcall StripLeadTrailSpace(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  int v2; // eax
  __int64 v3; // rcx
  unsigned __int16 v4; // dx
  unsigned __int16 *v5; // rcx
  unsigned __int16 *v6; // rax

  v1 = a1;
  v2 = wcsspn(a1, L" \t");
  if ( v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v1[v3] );
    memmove_0(v1, &v1[v2], 2LL * (unsigned int)(v3 - v2 + 1));
  }
  v4 = *v1;
  if ( *v1 )
  {
    v5 = 0;
    do
    {
      if ( v4 == 32 || v4 == 9 )
      {
        if ( !v5 )
          v5 = v1;
      }
      else if ( v5 )
      {
        v5 = 0;
      }
      v6 = v1 + 1;
      if ( !v4 )
        v6 = v1;
      v1 = v6;
      v4 = *v6;
    }
    while ( *v6 );
    if ( v5 )
      *v5 = 0;
  }
}

```

## disassembly

```asm
0x180009018  mov     [rsp+arg_0], rbx
0x18000901d  push    rdi
0x18000901e  sub     rsp, 20h
0x180009022  lea     rdx, Control; " \t"
0x180009029  mov     rbx, rcx
0x18000902c  call    cs:__imp_wcsspn
0x180009032  xor     edi, edi
0x180009034  test    eax, eax
0x180009036  jz      short loc_18000905C
0x180009038  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000903c  inc     rcx
0x18000903f  cmp     [rbx+rcx*2], di
0x180009043  jnz     short loc_18000903C
0x180009045  sub     ecx, eax
0x180009047  mov     eax, eax
0x180009049  lea     r8d, [rcx+1]
0x18000904d  mov     rcx, rbx; void *
0x180009050  add     r8, r8; Size
0x180009053  lea     rdx, [rbx+rax*2]; Src
0x180009057  call    memmove_0
0x18000905c  movzx   edx, word ptr [rbx]
0x18000905f  test    dx, dx
0x180009062  jz      short loc_1800090A2
0x180009064  mov     rcx, rdi
0x180009067  cmp     dx, 20h ; ' '
0x18000906b  jz      short loc_18000907D
0x18000906d  cmp     dx, 9
0x180009071  jz      short loc_18000907D
0x180009073  test    rcx, rcx
0x180009076  jz      short loc_180009084
0x180009078  mov     rcx, rdi
0x18000907b  jmp     short loc_180009084
0x18000907d  test    rcx, rcx
0x180009080  cmovz   rcx, rbx
0x180009084  test    dx, dx
0x180009087  lea     rax, [rbx+2]
0x18000908b  cmovz   rax, rbx
0x18000908f  mov     rbx, rax
0x180009092  movzx   edx, word ptr [rax]
0x180009095  test    dx, dx
0x180009098  jnz     short loc_180009067
0x18000909a  test    rcx, rcx
0x18000909d  jz      short loc_1800090A2
0x18000909f  mov     [rcx], di
0x1800090a2  mov     rbx, [rsp+28h+arg_0]
0x1800090a7  add     rsp, 20h
0x1800090ab  pop     rdi
0x1800090ac  retn
```
