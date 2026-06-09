# QuickKey::Compare(QuickKey &)

- ea: `0x10010500`
- end: `0x10010574`
- name: `?Compare@QuickKey@@QBEHAAV1@@Z`
- size: `116`
- prototype: `int __thiscall(QuickKey *__hidden this, struct QuickKey *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10010d60`
- `0x10011f50`
- `0x10030380`
- `0x10031f50`
- `0x10032460`
- `0x1004c210`
- `0x1004d3a0`

## callees

- `0x10010500`

## pseudocode

```c
int __thiscall QuickKey::Compare(QuickKey *this, struct QuickKey *a2)
{
  unsigned int v2; // esi
  int v3; // ecx
  int v4; // edx
  unsigned int v5; // esi
  bool v6; // cf
  unsigned __int8 v7; // al
  unsigned __int8 v8; // al
  unsigned __int8 v9; // al

  v2 = *(_DWORD *)this;
  v3 = *((_DWORD *)this + 1);
  if ( v2 >= *(_DWORD *)a2 )
    v2 = *(_DWORD *)a2;
  v4 = *((_DWORD *)a2 + 1);
  v6 = v2 < 4;
  v5 = v2 - 4;
  if ( v6 )
  {
LABEL_6:
    if ( v5 == -4 )
      return 0;
  }
  else
  {
    while ( *(_DWORD *)v3 == *(_DWORD *)v4 )
    {
      v3 += 4;
      v4 += 4;
      v6 = v5 < 4;
      v5 -= 4;
      if ( v6 )
        goto LABEL_6;
    }
  }
  v6 = *(_BYTE *)v3 < *(_BYTE *)v4;
  if ( *(_BYTE *)v3 != *(_BYTE *)v4 )
    return v6 ? -1 : 1;
  if ( v5 != -3 )
  {
    v7 = *(_BYTE *)(v3 + 1);
    v6 = v7 < *(_BYTE *)(v4 + 1);
    if ( v7 != *(_BYTE *)(v4 + 1) )
      return v6 ? -1 : 1;
    if ( v5 != -2 )
    {
      v8 = *(_BYTE *)(v3 + 2);
      v6 = v8 < *(_BYTE *)(v4 + 2);
      if ( v8 != *(_BYTE *)(v4 + 2) )
        return v6 ? -1 : 1;
      if ( v5 != -1 )
      {
        v9 = *(_BYTE *)(v3 + 3);
        v6 = v9 < *(_BYTE *)(v4 + 3);
        if ( v9 != *(_BYTE *)(v4 + 3) )
          return v6 ? -1 : 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10010500  mov     edi, edi
0x10010502  push    ebp
0x10010503  mov     ebp, esp
0x10010505  mov     edx, [ebp+arg_0]
0x10010508  push    esi
0x10010509  mov     esi, [ecx]
0x1001050b  mov     ecx, [ecx+4]
0x1001050e  cmp     esi, [edx]
0x10010510  cmovnb  esi, [edx]
0x10010513  mov     edx, [edx+4]
0x10010516  sub     esi, 4
0x10010519  jb      short loc_10010531
0x1001051b  nop     dword ptr [eax+eax+00h]
0x10010520  mov     eax, [ecx]
0x10010522  cmp     eax, [edx]
0x10010524  jnz     short loc_10010536
0x10010526  add     ecx, 4
0x10010529  add     edx, 4
0x1001052c  sub     esi, 4
0x1001052f  jnb     short loc_10010520
0x10010531  cmp     esi, 0FFFFFFFCh
0x10010534  jz      short loc_1001056D
0x10010536  mov     al, [ecx]
0x10010538  cmp     al, [edx]
0x1001053a  jnz     short loc_10010563
0x1001053c  cmp     esi, 0FFFFFFFDh
0x1001053f  jz      short loc_1001056D
0x10010541  mov     al, [ecx+1]
0x10010544  cmp     al, [edx+1]
0x10010547  jnz     short loc_10010563
0x10010549  cmp     esi, 0FFFFFFFEh
0x1001054c  jz      short loc_1001056D
0x1001054e  mov     al, [ecx+2]
0x10010551  cmp     al, [edx+2]
0x10010554  jnz     short loc_10010563
0x10010556  cmp     esi, 0FFFFFFFFh
0x10010559  jz      short loc_1001056D
0x1001055b  mov     al, [ecx+3]
0x1001055e  cmp     al, [edx+3]
0x10010561  jz      short loc_1001056D
0x10010563  sbb     eax, eax
0x10010565  or      eax, 1
0x10010568  pop     esi
0x10010569  pop     ebp
0x1001056a  retn    4
0x1001056d  xor     eax, eax
0x1001056f  pop     esi
0x10010570  pop     ebp
0x10010571  retn    4
```
