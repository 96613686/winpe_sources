# _FindPESection

- ea: `0x180001580`
- end: `0x1800015c3`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015d0`

## callees

- `0x180001580`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  unsigned int v4; // r10d
  __int64 result; // rax
  unsigned __int64 v6; // r8

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
  v4 = *(unsigned __int16 *)(v3 + 6);
  result = v3 + *(unsigned __int16 *)(v3 + 20) + 24LL;
  if ( !*(_WORD *)(v3 + 6) )
    return 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(result + 12);
    if ( a2 >= v6 && a2 < (unsigned int)(v6 + *(_DWORD *)(result + 8)) )
      break;
    ++v2;
    result += 40;
    if ( v2 >= v4 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001580  movsxd  r8, dword ptr [rcx+3Ch]
0x180001584  xor     r9d, r9d
0x180001587  add     r8, rcx
0x18000158a  movzx   eax, word ptr [r8+14h]
0x18000158f  movzx   r10d, word ptr [r8+6]
0x180001594  add     rax, 18h
0x180001598  add     rax, r8
0x18000159b  test    r10d, r10d
0x18000159e  jz      short loc_1800015C0
0x1800015a0  mov     r8d, [rax+0Ch]
0x1800015a4  cmp     rdx, r8
0x1800015a7  jb      short loc_1800015B4
0x1800015a9  mov     ecx, [rax+8]
0x1800015ac  add     ecx, r8d
0x1800015af  cmp     rdx, rcx
0x1800015b2  jb      short locret_1800015C2
0x1800015b4  inc     r9d
0x1800015b7  add     rax, 28h ; '('
0x1800015bb  cmp     r9d, r10d
0x1800015be  jb      short loc_1800015A0
0x1800015c0  xor     eax, eax
0x1800015c2  retn
```
