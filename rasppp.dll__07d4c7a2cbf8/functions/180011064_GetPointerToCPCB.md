# GetPointerToCPCB

- ea: `0x180011064`
- end: `0x1800110e1`
- name: `GetPointerToCPCB`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000419c`
- `0x180004304`
- `0x180004388`
- `0x180009560`
- `0x1800096e8`
- `0x18000aed4`
- `0x18000ba40`
- `0x18000bc28`
- `0x18000be0c`
- `0x18000bfc0`
- `0x18000c4ac`
- `0x18000c854`
- `0x18000c9a0`
- `0x18000cb10`
- `0x18000d020`
- `0x18000d284`
- `0x18000d480`
- `0x18000df18`
- `0x18000e100`
- `0x18000e364`
- `0x18000e750`
- `0x18000e86c`
- `0x1800109cc`
- `0x180011b08`
- `0x180013630`
- `0x1800139e0`
- `0x18001413c`
- `0x180014f20`
- `0x180014ff0`
- `0x1800155b8`
- `0x180017990`

## callees

- `0x180011064`

## pseudocode

```c
unsigned __int64 __fastcall GetPointerToCPCB(__int64 a1, unsigned int a2)
{
  unsigned __int64 result; // rax
  int v3; // edx

  if ( a2 == -1 )
    return 0;
  if ( !a2 )
    return a1 + 1456;
  if ( a2 < (unsigned int)PppConfigInfo )
    return ((unsigned __int64)(a2 - 1) << 6) + *(_QWORD *)(a1 + 8) + 4112LL;
  v3 = *((_DWORD *)CpTable + 44 * a2);
  if ( v3 == 49193 )
    return a1 + 1264;
  if ( v3 == *(_DWORD *)(a1 + 1332) )
    return a1 + 1328;
  result = 0;
  if ( v3 == *(_DWORD *)(a1 + 1396) )
    return a1 + 1392;
  return result;
}

```

## disassembly

```asm
0x180011064  mov     r8, rcx
0x180011067  cmp     edx, 0FFFFFFFFh
0x18001106a  jnz     short loc_18001106F
0x18001106c  xor     eax, eax
0x18001106e  retn
0x18001106f  test    edx, edx
0x180011071  jnz     short loc_18001107B
0x180011073  lea     rax, [rcx+5B0h]
0x18001107a  retn
0x18001107b  cmp     edx, dword ptr cs:PppConfigInfo
0x180011081  jb      short loc_1800110CC
0x180011083  mov     eax, edx
0x180011085  imul    rcx, rax, 0B0h
0x18001108c  mov     rax, cs:CpTable
0x180011093  mov     edx, [rcx+rax]
0x180011096  cmp     edx, 0C029h
0x18001109c  jnz     short loc_1800110A6
0x18001109e  lea     rax, [r8+4F0h]
0x1800110a5  retn
0x1800110a6  cmp     edx, [r8+534h]
0x1800110ad  jnz     short loc_1800110B7
0x1800110af  lea     rax, [r8+530h]
0x1800110b6  retn
0x1800110b7  xor     eax, eax
0x1800110b9  lea     rcx, [r8+570h]
0x1800110c0  cmp     edx, [r8+574h]
0x1800110c7  cmovz   rax, rcx
0x1800110cb  retn
0x1800110cc  mov     rax, [r8+8]
0x1800110d0  lea     ecx, [rdx-1]
0x1800110d3  shl     rcx, 6
0x1800110d7  add     rax, 1010h
0x1800110dd  add     rax, rcx
0x1800110e0  retn
```
