# stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::operator()(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800109b0`
- end: `0x180010a5f`
- name: `??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`
- `0x1800107bc`
- `0x1800116a0`
- `0x180017e94`
- `0x18001d6ac`
- `0x180023d60`
- `0x180023ed4`

## callees

- `0x1800109b0`

## pseudocode

```c
__int64 __fastcall stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // r8
  int i; // r9d
  int v6; // eax
  unsigned int v7; // r9d
  signed int v8; // ecx
  __int64 result; // rax

  v2 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v3 = 2 * v2;
  v4 = 0;
  for ( i = -2078137563; v4 < v3; i = 435 * (v6 ^ i) )
    v6 = *((unsigned __int8 *)a2 + v4++);
  v7 = i & 0x7FFFFFFF;
  v8 = 16807 * (v7 % 0x1F31D) - 2836 * (v7 / 0x1F31D);
  LODWORD(result) = v8 + 0x7FFFFFFF;
  if ( v8 >= 0 )
    LODWORD(result) = 16807 * (v7 % 0x1F31D) - 2836 * (v7 / 0x1F31D);
  return (int)result;
}

```

## disassembly

```asm
0x1800109b0  cmp     qword ptr [rdx+18h], 7
0x1800109b5  mov     rax, [rdx+10h]
0x1800109b9  mov     [rsp+arg_0], rcx
0x1800109be  jbe     short loc_1800109C3
0x1800109c0  mov     rdx, [rdx]
0x1800109c3  lea     rcx, [rax+rax]
0x1800109c7  xor     r8d, r8d
0x1800109ca  mov     r9, 0CBF29CE484222325h
0x1800109d4  test    rcx, rcx
0x1800109d7  jz      short loc_1800109F7
0x1800109d9  mov     r10, 100000001B3h
0x1800109e3  movzx   eax, byte ptr [rdx+r8]
0x1800109e8  inc     r8
0x1800109eb  xor     r9, rax
0x1800109ee  imul    r9, r10
0x1800109f2  cmp     r8, rcx
0x1800109f5  jb      short loc_1800109E3
0x1800109f7  btr     r9d, 1Fh
0x1800109fc  mov     eax, 69C16BDh
0x180010a01  mul     r9d
0x180010a04  mov     ecx, r9d
0x180010a07  mov     eax, 69C16BDh
0x180010a0c  sub     ecx, edx
0x180010a0e  mov     r8d, r9d
0x180010a11  shr     ecx, 1
0x180010a13  add     ecx, edx
0x180010a15  mul     r9d
0x180010a18  shr     ecx, 10h
0x180010a1b  sub     r8d, edx
0x180010a1e  mov     dword ptr [rsp+arg_0], ecx
0x180010a22  shr     r8d, 1
0x180010a25  add     r8d, edx
0x180010a28  shr     r8d, 10h
0x180010a2c  imul    eax, r8d, 1F31Dh
0x180010a33  sub     r9d, eax
0x180010a36  mov     dword ptr [rsp+arg_0+4], r9d
0x180010a3b  mov     rax, [rsp+arg_0]
0x180010a40  shr     rax, 20h
0x180010a44  imul    ecx, eax, 41A7h
0x180010a4a  imul    eax, r8d, 0B14h
0x180010a51  sub     ecx, eax
0x180010a53  lea     eax, [rcx+7FFFFFFFh]
0x180010a59  cmovns  eax, ecx
0x180010a5c  cdqe
0x180010a5e  retn
```
