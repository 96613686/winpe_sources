# WSTRemoveAuthSchemeFromArray(_GUID *,ushort *,ulong)

- ea: `0x18000706c`
- end: `0x1800070ca`
- name: `?WSTRemoveAuthSchemeFromArray@@YAXPEAU_GUID@@PEAGK@Z`
- size: `94`
- prototype: `void __fastcall(__int64, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001414`
- `0x1800070d0`
- `0x18001a020`
- `0x18001a3b4`

## callees

- `0x18000706c`

## pseudocode

```c
void __fastcall WSTRemoveAuthSchemeFromArray(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  struct _GUID *v3; // r10
  __int64 v4; // rax

  v3 = (struct _GUID *)a1;
  LODWORD(a1) = *a2;
  if ( a3 < (unsigned int)a1 && (_WORD)a1 )
  {
    if ( (_WORD)a1 == 1 )
    {
      *a2 = 0;
    }
    else
    {
      if ( a3 < (int)a1 - 1 )
      {
        do
        {
          v4 = a3;
          a1 = 2LL * ++a3;
          v3[v4] = *(struct _GUID *)((char *)v3 + 8 * a1);
          LOWORD(a1) = *a2;
        }
        while ( a3 < (unsigned int)*a2 - 1 );
      }
      *a2 = a1 - 1;
    }
  }
}

```

## disassembly

```asm
0x18000706c  mov     r10, rcx
0x18000706f  mov     r9, rdx
0x180007072  movzx   ecx, word ptr [rdx]
0x180007075  cmp     r8d, ecx
0x180007078  jnb     short locret_1800070C9
0x18000707a  xor     eax, eax
0x18000707c  test    cx, cx
0x18000707f  jz      short locret_1800070C9
0x180007081  lea     r11d, [rax+1]
0x180007085  cmp     cx, r11w
0x180007089  jnz     short loc_18000708F
0x18000708b  mov     [rdx], ax
0x18000708e  retn
0x18000708f  lea     eax, [rcx-1]
0x180007092  cmp     r8d, eax
0x180007095  jnb     short loc_1800070C1
0x180007097  lea     edx, [r8+1]
0x18000709b  mov     eax, r8d
0x18000709e  add     rax, rax
0x1800070a1  mov     ecx, edx
0x1800070a3  add     rcx, rcx
0x1800070a6  mov     r8d, edx
0x1800070a9  movups  xmm0, xmmword ptr [r10+rcx*8]
0x1800070ae  movdqu  xmmword ptr [r10+rax*8], xmm0
0x1800070b4  movzx   ecx, word ptr [r9]
0x1800070b8  mov     eax, ecx
0x1800070ba  sub     eax, r11d
0x1800070bd  cmp     edx, eax
0x1800070bf  jb      short loc_180007097
0x1800070c1  sub     cx, r11w
0x1800070c5  mov     [r9], cx
0x1800070c9  retn
```
