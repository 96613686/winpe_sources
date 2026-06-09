# CsrDestroyProcessByPtr

- ea: `0x1800038c0`
- end: `0x18000391d`
- name: `CsrDestroyProcessByPtr`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800097f0`
- `0x18000a1f0`

## callees

- `0x1800038c0`
- `0x180003a20`

## pseudocode

```c
__int64 __fastcall CsrDestroyProcessByPtr(__int64 a1)
{
  int v1; // eax
  __int64 **v2; // rbx
  __int64 *v3; // rcx
  int v4; // eax

  v1 = *(_DWORD *)(a1 + 92);
  if ( (v1 & 8) != 0 )
    return 3221225547LL;
  v2 = (__int64 **)(a1 + 32);
  *(_DWORD *)(a1 + 92) = v1 | 8;
  v3 = *(__int64 **)(a1 + 32);
  while ( v3 != (__int64 *)v2 )
  {
    v4 = *((_DWORD *)v3 + 16);
    if ( (v4 & 4) != 0 )
    {
      v3 = (__int64 *)*v3;
    }
    else
    {
      *((_DWORD *)v3 + 16) = v4 | 4;
      CsrLockedDereferenceThread((char *)v3 - 8);
      v3 = *v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800038c0  sub     rsp, 28h
0x1800038c4  mov     eax, [rcx+5Ch]
0x1800038c7  test    al, 8
0x1800038c9  jnz     short loc_18000390D
0x1800038cb  or      eax, 8
0x1800038ce  mov     [rsp+28h+var_8], rbx
0x1800038d3  lea     rbx, [rcx+20h]
0x1800038d7  mov     [rcx+5Ch], eax
0x1800038da  mov     rcx, [rbx]
0x1800038dd  cmp     rcx, rbx
0x1800038e0  jz      short loc_180003900
0x1800038e2  mov     eax, [rcx+40h]
0x1800038e5  test    al, 4
0x1800038e7  jnz     short loc_180003918
0x1800038e9  or      eax, 4
0x1800038ec  mov     [rcx+40h], eax
0x1800038ef  add     rcx, 0FFFFFFFFFFFFFFF8h; BaseAddress
0x1800038f3  call    CsrLockedDereferenceThread
0x1800038f8  mov     rcx, [rbx]
0x1800038fb  cmp     rcx, rbx
0x1800038fe  jnz     short loc_1800038E2
0x180003900  mov     rbx, [rsp+28h+var_8]
0x180003905  xor     eax, eax
0x180003907  add     rsp, 28h
0x18000390b  retn
0x18000390d  mov     eax, 0C000004Bh
0x180003912  add     rsp, 28h
0x180003916  retn
0x180003918  mov     rcx, [rcx]
0x18000391b  jmp     short loc_1800038FB
```
