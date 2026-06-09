# ISAMDBDeleteTask(x)

- ea: `0x10014320`
- end: `0x100143fa`
- name: `_ISAMDBDeleteTask@4`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10014ea0`

## callees

- `0x1000b200`
- `0x10014100`
- `0x10014320`

## pseudocode

```c
void __stdcall ISAMDBDeleteTask(_DWORD *a1)
{
  _DWORD *v1; // ebx
  _DWORD *v2; // edi
  _DWORD *v3; // eax
  _DWORD *v4; // esi
  _DWORD *v5; // ebp
  _DWORD *v6; // edi
  _DWORD *v7; // eax
  _DWORD *v8; // edi
  int v9; // eax
  _DWORD *v10; // eax
  _DWORD *v11; // esi
  _DWORD *v12; // [esp+8h] [ebp-8h]
  _DWORD *v13; // [esp+Ch] [ebp-4h]

  v1 = (_DWORD *)dword_10040FBC;
  v2 = 0;
  v12 = 0;
  if ( dword_10040FBC )
  {
    while ( v1 != a1 )
    {
      v2 = v1;
      v1 = (_DWORD *)*v1;
      v12 = v2;
      if ( !v1 )
        return;
    }
    v3 = (_DWORD *)a1[1];
    if ( v3 )
    {
      do
      {
        v4 = (_DWORD *)v1[1];
        v5 = 0;
        v6 = (_DWORD *)*v3;
        v13 = (_DWORD *)*v3;
        if ( v4 )
        {
          while ( v4 != v3 )
          {
            v5 = v4;
            v4 = (_DWORD *)*v4;
            if ( !v4 )
              goto LABEL_17;
          }
          v7 = (_DWORD *)v4[2];
          if ( v7 )
          {
            do
            {
              v8 = (_DWORD *)*v7;
              MemFree(v7);
              v7 = v8;
            }
            while ( v8 );
            v6 = v13;
          }
          v9 = *v4;
          if ( v5 )
            *v5 = v9;
          else
            v1[1] = v9;
          MemFree(v4);
        }
LABEL_17:
        v3 = v6;
      }
      while ( v6 );
      v2 = v12;
    }
    v10 = (_DWORD *)a1[2];
    if ( v10 )
    {
      do
      {
        v11 = (_DWORD *)*v10;
        ISAMDBDeleteDatabase((int)v1, v10);
        v10 = v11;
      }
      while ( v11 );
    }
    if ( v2 )
      *v2 = *v1;
    else
      dword_10040FBC = *v1;
    MemFree(v1);
  }
}

```

## disassembly

```asm
0x10014320  sub     esp, 8
0x10014323  push    ebx
0x10014324  mov     ebx, dword_10040FBC
0x1001432a  push    edi
0x1001432b  xor     edi, edi
0x1001432d  mov     [esp+10h+var_8], edi
0x10014331  test    ebx, ebx
0x10014333  jz      loc_100143F2
0x10014339  mov     eax, [esp+10h+arg_0]
0x1001433d  lea     ecx, [ecx+0]
0x10014340  cmp     ebx, eax
0x10014342  jz      short loc_10014358
0x10014344  mov     edi, ebx
0x10014346  mov     ebx, [ebx]
0x10014348  mov     [esp+10h+var_8], edi
0x1001434c  test    ebx, ebx
0x1001434e  jnz     short loc_10014340
0x10014350  pop     edi
0x10014351  pop     ebx
0x10014352  add     esp, 8
0x10014355  retn    4
0x10014358  mov     eax, [eax+4]
0x1001435b  push    esi
0x1001435c  test    eax, eax
0x1001435e  jz      short loc_100143B6
0x10014360  push    ebp
0x10014361  mov     esi, [ebx+4]
0x10014364  xor     ebp, ebp
0x10014366  mov     edi, [eax]
0x10014368  mov     [esp+18h+var_4], edi
0x1001436c  test    esi, esi
0x1001436e  jz      short loc_100143AB
0x10014370  cmp     esi, eax
0x10014372  jz      short loc_1001437E
0x10014374  mov     ebp, esi
0x10014376  mov     esi, [esi]
0x10014378  test    esi, esi
0x1001437a  jnz     short loc_10014370
0x1001437c  jmp     short loc_100143AB
0x1001437e  mov     eax, [esi+8]
0x10014381  test    eax, eax
0x10014383  jz      short loc_10014397
0x10014385  mov     edi, [eax]
0x10014387  push    eax
0x10014388  call    _MemFree@4; MemFree(x)
0x1001438d  mov     eax, edi
0x1001438f  test    edi, edi
0x10014391  jnz     short loc_10014385
0x10014393  mov     edi, [esp+18h+var_4]
0x10014397  mov     eax, [esi]
0x10014399  test    ebp, ebp
0x1001439b  jnz     short loc_100143A2
0x1001439d  mov     [ebx+4], eax
0x100143a0  jmp     short loc_100143A5
0x100143a2  mov     [ebp+0], eax
0x100143a5  push    esi
0x100143a6  call    _MemFree@4; MemFree(x)
0x100143ab  mov     eax, edi
0x100143ad  test    edi, edi
0x100143af  jnz     short loc_10014361
0x100143b1  mov     edi, [esp+18h+var_8]
0x100143b5  pop     ebp
0x100143b6  mov     eax, [esp+14h+arg_0]
0x100143ba  mov     eax, [eax+8]
0x100143bd  test    eax, eax
0x100143bf  jz      short loc_100143D0
0x100143c1  mov     esi, [eax]
0x100143c3  push    eax
0x100143c4  push    ebx
0x100143c5  call    _ISAMDBDeleteDatabase@8; ISAMDBDeleteDatabase(x,x)
0x100143ca  mov     eax, esi
0x100143cc  test    esi, esi
0x100143ce  jnz     short loc_100143C1
0x100143d0  mov     eax, [ebx]
0x100143d2  pop     esi
0x100143d3  test    edi, edi
0x100143d5  jnz     short loc_100143EA
0x100143d7  push    ebx
0x100143d8  mov     dword_10040FBC, eax
0x100143dd  call    _MemFree@4; MemFree(x)
0x100143e2  pop     edi
0x100143e3  pop     ebx
0x100143e4  add     esp, 8
0x100143e7  retn    4
0x100143ea  push    ebx
0x100143eb  mov     [edi], eax
0x100143ed  call    _MemFree@4; MemFree(x)
0x100143f2  pop     edi
0x100143f3  pop     ebx
0x100143f4  add     esp, 8
0x100143f7  retn    4
```
