# WIN32ERRORtoHRESULT(ulong)

- ea: `0x180016184`
- end: `0x1800161fe`
- name: `?WIN32ERRORtoHRESULT@@YAJK@Z`
- size: `122`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180015ec0`
- `0x18001a2fc`
- `0x18001d940`
- `0x18001e230`
- `0x18001ef80`
- `0x18001f170`
- `0x18001f310`
- `0x18001f51c`
- `0x180020b40`
- `0x180020be0`

## callees

- `0x180016184`

## pseudocode

```c
__int64 __fastcall WIN32ERRORtoHRESULT(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx

  if ( a1 > 0x78 )
  {
    v8 = a1 - 122;
    if ( !v8 )
      return 2147942487LL;
    v9 = v8 - 5;
    if ( v9 )
    {
      v10 = v9 - 871;
      if ( !v10 )
        return 2147942487LL;
      v11 = v10 - 6;
      if ( !v11 )
        return 2147942487LL;
      v12 = v11 - 164;
      if ( v12 )
      {
        v13 = v12 - 282;
        if ( v13 && v13 - 1 >= 2 )
          return 2147500037LL;
        return 2147942414LL;
      }
    }
  }
  else if ( a1 != 120 )
  {
    if ( !a1 )
      return 0;
    v1 = a1 - 1;
    if ( !v1 )
      return 2147942487LL;
    v2 = v1 - 7;
    if ( v2 )
    {
      v3 = v2 - 5;
      if ( !v3 )
        return 2147942487LL;
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 8;
        if ( v5 )
        {
          v6 = v5 - 28;
          if ( v6 )
          {
            if ( v6 == 37 )
              return 2147942487LL;
            return 2147500037LL;
          }
          return 2147500033LL;
        }
        return 2147942487LL;
      }
    }
    return 2147942414LL;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180016184  cmp     ecx, 78h ; 'x'
0x180016187  ja      short loc_1800161BB
0x180016189  jz      short loc_1800161F8
0x18001618b  test    ecx, ecx
0x18001618d  jz      short loc_1800161B8
0x18001618f  sub     ecx, 1
0x180016192  jz      short loc_1800161B2
0x180016194  sub     ecx, 7
0x180016197  jz      short loc_1800161F2
0x180016199  sub     ecx, 5
0x18001619c  jz      short loc_1800161B2
0x18001619e  sub     ecx, 1
0x1800161a1  jz      short loc_1800161F2
0x1800161a3  sub     ecx, 8
0x1800161a6  jz      short loc_1800161B2
0x1800161a8  sub     ecx, 1Ch
0x1800161ab  jz      short loc_1800161F8
0x1800161ad  cmp     ecx, 25h ; '%'
0x1800161b0  jnz     short loc_1800161EC
0x1800161b2  mov     eax, 80070057h
0x1800161b7  retn
0x1800161b8  xor     eax, eax
0x1800161ba  retn
0x1800161bb  sub     ecx, 7Ah ; 'z'
0x1800161be  jz      short loc_1800161B2
0x1800161c0  sub     ecx, 5
0x1800161c3  jz      short loc_1800161F8
0x1800161c5  sub     ecx, 367h
0x1800161cb  jz      short loc_1800161B2
0x1800161cd  sub     ecx, 6
0x1800161d0  jz      short loc_1800161B2
0x1800161d2  sub     ecx, 0A4h
0x1800161d8  jz      short loc_1800161F8
0x1800161da  sub     ecx, 11Ah
0x1800161e0  jz      short loc_1800161F2
0x1800161e2  sub     ecx, 1
0x1800161e5  jz      short loc_1800161F2
0x1800161e7  cmp     ecx, 1
0x1800161ea  jz      short loc_1800161F2
0x1800161ec  mov     eax, 80004005h
0x1800161f1  retn
0x1800161f2  mov     eax, 8007000Eh
0x1800161f7  retn
0x1800161f8  mov     eax, 80004001h
0x1800161fd  retn
```
