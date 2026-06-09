# ATL::CComBSTR::Append(ushort const *)

- ea: `0x180014f64`
- end: `0x180014f83`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `31`
- prototype: `__int64 __fastcall(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015040`
- `0x1800150e0`

## callees

- `0x180014f64`
- `0x180014f8c`

## pseudocode

```c
int __fastcall ATL::CComBSTR::Append(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  __int64 v2; // r8

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a2[v2] );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  return ATL::CComBSTR::Append(this, a2, v2);
}

```

## disassembly

```asm
0x180014f64  xor     eax, eax
0x180014f66  test    rdx, rdx
0x180014f69  jnz     short loc_180014F70
0x180014f6b  mov     r8d, eax
0x180014f6e  jmp     short loc_180014F7E
0x180014f70  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014f74  inc     r8; int
0x180014f77  cmp     [rdx+r8*2], ax
0x180014f7c  jnz     short loc_180014F74
0x180014f7e  jmp     ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
```
