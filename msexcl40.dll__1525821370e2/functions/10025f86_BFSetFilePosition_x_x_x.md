# BFSetFilePosition(x,x,x)

- ea: `0x10025f86`
- end: `0x1002602a`
- name: `_BFSetFilePosition@12`
- size: `164`
- prototype: `int __fastcall(int *, int, int)`
- caller_count: `28`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100082d0`
- `0x100094b0`
- `0x1000d760`
- `0x1000dc30`
- `0x1000dd90`
- `0x1000df70`
- `0x1000e400`
- `0x1000eec0`
- `0x1000fdf0`
- `0x100102c0`
- `0x10010700`
- `0x10010790`
- `0x10011010`
- `0x10011a70`
- `0x10011e70`
- `0x10012270`
- `0x10013490`
- `0x10013d10`
- `0x10014020`
- `0x10014320`
- `0x10014710`
- `0x10016240`
- `0x100163d0`
- `0x10017110`
- `0x10017b00`
- `0x100181b0`
- `0x10018550`
- `0x1001b770`

## callees

- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x10025f86`

## pseudocode

```c
int __fastcall BFSetFilePosition(int *a1, int a2, int a3)
{
  int v3; // esi
  int v5; // ecx
  int v6; // ebx
  int result; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  int FileBlock; // eax
  int v12; // ecx
  int v13; // [esp+10h] [ebp-4h]

  v3 = a3;
  v5 = a1[21];
  v13 = v5 - a1[1];
  v6 = a1[2] + v13;
  if ( a2 )
    v3 = a3 + v6;
  if ( v3 == v6 )
    return 0;
  if ( v3 >= v5 && v3 <= v5 + *a1 - 1 )
  {
    a1[2] += v3 - v6;
    return 0;
  }
  if ( v5 + *a1 == a1[22] && v3 >= v5 && v3 <= v5 + a1[16] - 1 )
  {
    v8 = v3 - v6 + a1[2];
    v9 = v8 + v13;
    a1[2] = v8;
    v10 = v8 - a1[1];
    a1[22] = v9;
    *a1 = v10;
    return 0;
  }
  if ( a1[23] != 1 || (result = WriteFileBlock(a1), result >= 0) )
  {
    a1[20] = v3;
    OSSetFilePosition(a1, 0, v3);
    FileBlock = ReadFileBlock(a1);
    v12 = 0;
    if ( FileBlock < 0 )
      return FileBlock;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x10025f86  mov     edi, edi
0x10025f88  push    ebp
0x10025f89  mov     ebp, esp
0x10025f8b  push    ecx
0x10025f8c  push    ecx
0x10025f8d  push    ebx
0x10025f8e  push    esi
0x10025f8f  mov     esi, [ebp+arg_0]
0x10025f92  push    edi
0x10025f93  mov     edi, ecx
0x10025f95  mov     ecx, [edi+54h]
0x10025f98  mov     ebx, ecx
0x10025f9a  sub     ebx, [edi+4]
0x10025f9d  mov     [ebp+var_4], ebx
0x10025fa0  add     ebx, [edi+8]
0x10025fa3  test    edx, edx
0x10025fa5  lea     eax, [esi+ebx]
0x10025fa8  cmovnz  esi, eax
0x10025fab  cmp     esi, ebx
0x10025fad  jz      short loc_10025FC1
0x10025faf  cmp     esi, ecx
0x10025fb1  jl      short loc_10025FCA
0x10025fb3  mov     eax, [edi]
0x10025fb5  dec     eax
0x10025fb6  add     eax, ecx
0x10025fb8  cmp     esi, eax
0x10025fba  jg      short loc_10025FCA
0x10025fbc  sub     esi, ebx
0x10025fbe  add     [edi+8], esi
0x10025fc1  xor     eax, eax
0x10025fc3  pop     edi
0x10025fc4  pop     esi
0x10025fc5  pop     ebx
0x10025fc6  leave
0x10025fc7  retn    4
0x10025fca  mov     eax, [edi]
0x10025fcc  add     eax, ecx
0x10025fce  cmp     eax, [edi+58h]
0x10025fd1  jnz     short loc_10025FFA
0x10025fd3  cmp     esi, ecx
0x10025fd5  jl      short loc_10025FFA
0x10025fd7  mov     eax, [edi+40h]
0x10025fda  dec     eax
0x10025fdb  add     eax, ecx
0x10025fdd  cmp     esi, eax
0x10025fdf  jg      short loc_10025FFA
0x10025fe1  mov     ecx, [edi+8]
0x10025fe4  sub     esi, ebx
0x10025fe6  mov     eax, [ebp+var_4]
0x10025fe9  add     ecx, esi
0x10025feb  add     eax, ecx
0x10025fed  mov     [edi+8], ecx
0x10025ff0  sub     ecx, [edi+4]
0x10025ff3  mov     [edi+58h], eax
0x10025ff6  mov     [edi], ecx
0x10025ff8  jmp     short loc_10025FC1
0x10025ffa  cmp     dword ptr [edi+5Ch], 1
0x10025ffe  jnz     short loc_1002600B
0x10026000  mov     ecx, edi
0x10026002  call    WriteFileBlock
0x10026007  test    eax, eax
0x10026009  js      short loc_10025FC3
0x1002600b  push    esi
0x1002600c  xor     edx, edx
0x1002600e  mov     [edi+50h], esi
0x10026011  mov     ecx, edi
0x10026013  call    OSSetFilePosition
0x10026018  mov     ecx, edi
0x1002601a  call    ReadFileBlock
0x1002601f  xor     ecx, ecx
0x10026021  test    eax, eax
0x10026023  cmovs   ecx, eax
0x10026026  mov     eax, ecx
0x10026028  jmp     short loc_10025FC3
```
