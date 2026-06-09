# StSecpPackageFamilyNameFromFullName

- ea: `0x14000dff8`
- end: `0x14000e0fc`
- name: `StSecpPackageFamilyNameFromFullName`
- size: `260`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d7a8`
- `0x14000dd14`
- `0x140010500`

## callees

- `0x14000dff8`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e020`
- `ntoskrnl!ExAllocatePool2` at `0x14000e020`

## pseudocode

```c
__int64 __fastcall StSecpPackageFamilyNameFromFullName(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v3; // ebx
  _WORD *Pool2; // r10
  unsigned int v6; // ebx
  __int64 v7; // r8
  _QWORD *v8; // r11
  bool v9; // cf
  bool v10; // zf
  __int16 v11; // dx
  unsigned int v12; // r9d
  int v13; // ecx
  bool v14; // cf
  __int16 v15; // r8

  v3 = *a1 >> 1;
  Pool2 = (_WORD *)ExAllocatePool2(256, 130, 1884517459);
  if ( Pool2 )
  {
    v7 = 0;
    v8 = a1 + 4;
    while ( 1 )
    {
      v9 = (unsigned int)v7 < v3;
      v10 = (_DWORD)v7 == v3;
      if ( (unsigned int)v7 >= v3 )
        break;
      v8 = a1 + 4;
      v11 = *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v7);
      if ( v11 == 95 )
      {
        v9 = (unsigned int)v7 < v3;
        v10 = (_DWORD)v7 == v3;
        break;
      }
      if ( (unsigned int)v7 >= 0x40 )
        goto LABEL_16;
      Pool2[v7] = v11;
      v7 = (unsigned int)(v7 + 1);
    }
    if ( v10 )
      goto LABEL_16;
    v12 = v7;
    if ( v9 )
    {
      v13 = 0;
      do
      {
        if ( *(_WORD *)(*v8 + 2LL * v12) == 95 && ++v13 == 4 )
          break;
        ++v12;
      }
      while ( v12 < v3 );
    }
    v14 = v12 < v3;
    if ( v12 == v3 )
    {
LABEL_16:
      v6 = -1073739509;
      StSecFree(Pool2);
      return v6;
    }
    while ( v14 )
    {
      if ( (unsigned int)v7 >= 0x40 )
        goto LABEL_16;
      Pool2[v7] = *(_WORD *)(*v8 + 2LL * v12);
      v7 = (unsigned int)(v7 + 1);
      v14 = ++v12 < v3;
    }
    Pool2[v7] = 0;
    v15 = 2 * v7;
    *(_WORD *)a2 = v15;
    *(_WORD *)(a2 + 2) = v15 + 2;
    v6 = 0;
    *(_QWORD *)(a2 + 8) = Pool2;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v6;
}

```

## disassembly

```asm
0x14000dff8  mov     [rsp+arg_0], rbx
0x14000dffd  mov     [rsp+arg_8], rsi
0x14000e002  push    rdi
0x14000e003  sub     rsp, 20h
0x14000e007  movzx   ebx, word ptr [rcx]
0x14000e00a  mov     rsi, rdx
0x14000e00d  mov     edx, 82h
0x14000e012  shr     ebx, 1
0x14000e014  mov     rdi, rcx
0x14000e017  mov     r8d, 70537453h
0x14000e01d  lea     ecx, [rdx+7Eh]
0x14000e020  call    cs:__imp_ExAllocatePool2
0x14000e027  nop     dword ptr [rax+rax+00h]
0x14000e02c  mov     r10, rax
0x14000e02f  test    rax, rax
0x14000e032  jnz     short loc_14000E03E
0x14000e034  mov     ebx, 0C0000017h
0x14000e039  jmp     loc_14000E0E9
0x14000e03e  xor     r8d, r8d
0x14000e041  lea     r11, [rdi+8]
0x14000e045  cmp     r8d, ebx
0x14000e048  jnb     short loc_14000E06F
0x14000e04a  lea     r11, [rdi+8]
0x14000e04e  mov     rax, [r11]
0x14000e051  movzx   edx, word ptr [rax+r8*2]
0x14000e056  cmp     dx, 5Fh ; '_'
0x14000e05a  jz      short loc_14000E06C
0x14000e05c  cmp     r8d, 40h ; '@'
0x14000e060  jnb     short loc_14000E099
0x14000e062  mov     [r10+r8*2], dx
0x14000e067  inc     r8d
0x14000e06a  jmp     short loc_14000E045
0x14000e06c  cmp     r8d, ebx
0x14000e06f  jz      short loc_14000E099
0x14000e071  mov     r9d, r8d
0x14000e074  jnb     short loc_14000E094
0x14000e076  mov     rdx, [r11]
0x14000e079  xor     ecx, ecx
0x14000e07b  mov     eax, r9d
0x14000e07e  cmp     word ptr [rdx+rax*2], 5Fh ; '_'
0x14000e083  jnz     short loc_14000E08C
0x14000e085  inc     ecx
0x14000e087  cmp     ecx, 4
0x14000e08a  jz      short loc_14000E094
0x14000e08c  inc     r9d
0x14000e08f  cmp     r9d, ebx
0x14000e092  jb      short loc_14000E07B
0x14000e094  cmp     r9d, ebx
0x14000e097  jnz     short loc_14000E0AB
0x14000e099  mov     rcx, r10
0x14000e09c  mov     ebx, 0C000090Bh
0x14000e0a1  call    StSecFree
0x14000e0a6  jmp     short loc_14000E0E9
0x14000e0a8  cmp     r9d, ebx
0x14000e0ab  jnb     short loc_14000E0CA
0x14000e0ad  cmp     r8d, 40h ; '@'
0x14000e0b1  jnb     short loc_14000E099
0x14000e0b3  mov     rax, [r11]
0x14000e0b6  mov     edx, r9d
0x14000e0b9  movzx   eax, word ptr [rax+rdx*2]
0x14000e0bd  mov     [r10+r8*2], ax
0x14000e0c2  inc     r8d
0x14000e0c5  inc     r9d
0x14000e0c8  jmp     short loc_14000E0A8
0x14000e0ca  xor     eax, eax
0x14000e0cc  mov     [r10+r8*2], ax
0x14000e0d1  add     r8w, r8w
0x14000e0d5  mov     [rsi], r8w
0x14000e0d9  add     r8w, 2
0x14000e0de  mov     [rsi+2], r8w
0x14000e0e3  xor     ebx, ebx
0x14000e0e5  mov     [rsi+8], r10
0x14000e0e9  mov     rsi, [rsp+28h+arg_8]
0x14000e0ee  mov     eax, ebx
0x14000e0f0  mov     rbx, [rsp+28h+arg_0]
0x14000e0f5  add     rsp, 20h
0x14000e0f9  pop     rdi
0x14000e0fa  retn
```
