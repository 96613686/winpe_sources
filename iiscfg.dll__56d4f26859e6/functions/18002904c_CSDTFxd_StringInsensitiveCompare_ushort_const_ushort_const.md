# CSDTFxd::StringInsensitiveCompare(ushort const *,ushort const *)

- ea: `0x18002904c`
- end: `0x180029087`
- name: `?StringInsensitiveCompare@CSDTFxd@@AEBAHPEBG0@Z`
- size: `59`
- prototype: `__int64 __fastcall(CSDTFxd *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025cc4`
- `0x18002637c`
- `0x1800265e0`
- `0x1800267b8`
- `0x180026d6c`
- `0x180027334`
- `0x1800274a0`
- `0x180027900`
- `0x180028010`
- `0x1800283a8`
- `0x1800289c0`

## callees

- `0x18002904c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002907d`

## pseudocode

```c
int __fastcall CSDTFxd::StringInsensitiveCompare(CSDTFxd *this, char *a2, char *a3)
{
  char *v4; // rax
  signed __int64 v5; // rcx
  int v6; // edx
  int v7; // r9d

  if ( a2 == a3 )
    return 0;
  v4 = a2;
  v5 = a3 - a2;
  do
  {
    v6 = *(unsigned __int16 *)&v4[v5];
    v7 = *(unsigned __int16 *)v4 - v6;
    if ( v7 )
      break;
    v4 += 2;
  }
  while ( v6 );
  if ( !v7 )
    return 0;
  else
    return _wcsicmp((const wchar_t *)a2, (const wchar_t *)a3);
}

```

## disassembly

```asm
0x18002904c  mov     r10, rdx
0x18002904f  cmp     rdx, r8
0x180029052  jz      short loc_180029084
0x180029054  mov     rcx, r8
0x180029057  mov     rax, rdx
0x18002905a  sub     rcx, rdx
0x18002905d  movzx   r9d, word ptr [rax]
0x180029061  movzx   edx, word ptr [rax+rcx]
0x180029065  sub     r9d, edx
0x180029068  jnz     short loc_180029072
0x18002906a  add     rax, 2
0x18002906e  test    edx, edx
0x180029070  jnz     short loc_18002905D
0x180029072  test    r9d, r9d
0x180029075  jz      short loc_180029084
0x180029077  mov     rdx, r8
0x18002907a  mov     rcx, r10
0x18002907d  jmp     cs:__imp__wcsicmp
0x180029084  xor     eax, eax
0x180029086  retn
```
