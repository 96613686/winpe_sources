# WriteGeneric

- ea: `0x18001a808`
- end: `0x18001a9b7`
- name: `WriteGeneric`
- size: `431`
- prototype: ``
- caller_count: `45`
- callee_count: `5`
- tags: ``

## callers

- `0x1800075f4`
- `0x1800079b8`
- `0x1800087e8`
- `0x180009010`
- `0x180009978`
- `0x18000b040`
- `0x18000b334`
- `0x18000b498`
- `0x18000b5d0`
- `0x18000b760`
- `0x18000b888`
- `0x18000bad4`
- `0x18000bc9c`
- `0x18000bdd4`
- `0x18000c1d0`
- `0x18000c350`
- `0x18000c708`
- `0x18000c874`
- `0x18000d108`
- `0x18000d45c`
- `0x18000e34c`
- `0x18000f364`
- `0x18000f86c`
- `0x18000f928`
- `0x18000fad8`
- `0x18000fd08`
- `0x180010284`
- `0x180010454`
- `0x18001077c`
- `0x1800108e4`
- `0x1800109fc`
- `0x180010fd4`
- `0x1800115ac`
- `0x180011f48`
- `0x180013364`
- `0x180013c38`
- `0x180013ee0`
- `0x180014dc0`
- `0x1800154a4`
- `0x180016e9c`
- `0x1800198f8`
- `0x180019c00`
- `0x180019ec0`
- `0x180019f90`
- `0x18001a9c0`

## callees

- `0x18001a76c`
- `0x18001a7b8`
- `0x18001a808`
- `0x18001aa68`
- `0x18001aadc`

## pseudocode

```c
__int16 __fastcall WriteGeneric(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        _WORD *a6)
{
  unsigned int v6; // ebx
  unsigned __int16 v7; // di
  unsigned __int16 v8; // r13
  unsigned __int64 v10; // rsi
  unsigned __int16 i; // bp
  unsigned __int8 v13; // dl
  __int16 result; // ax
  __int16 v15; // ax
  __int64 v16; // rdx
  int v17; // ecx
  unsigned __int8 *v18; // [rsp+68h] [rbp+20h]

  v18 = a4;
  v6 = a5;
  v7 = 0;
  v8 = *a4;
  v10 = a3;
  for ( i = 1; i <= v8; ++i )
  {
    v13 = a4[i];
    if ( (v13 & 7) == 1 )
    {
      if ( (v13 & 0x10) == 0 )
      {
        v16 = v7;
        if ( (unsigned __int64)v7 + 1 > v10 )
          return 1004;
        LOBYTE(v16) = *(_BYTE *)(v7 + a2);
        result = WriteByte(a1, v16, v6);
        if ( result )
          return result;
        a4 = v18;
        ++v6;
      }
      v15 = 1;
    }
    else if ( (a4[i] & 7) == 2 )
    {
      if ( (v13 & 0x10) == 0 )
      {
        if ( (unsigned __int64)v7 + 2 > v10 )
          return 1004;
        if ( (v13 & 0x20) != 0 )
          result = WriteBytes(a1, v7 + a2, v6, 2);
        else
          result = WriteWord(a1, *(unsigned __int16 *)(v7 + a2), v6);
        if ( result )
          return result;
        a4 = v18;
        v6 += 2;
      }
      v15 = 2;
    }
    else
    {
      if ( (a4[i] & 7) != 4 )
        return 1004;
      if ( (v13 & 0x10) == 0 )
      {
        if ( (unsigned __int64)v7 + 4 > v10 )
          return 1004;
        if ( (v13 & 0x20) != 0 )
          result = WriteBytes(a1, v7 + a2, v6, 4);
        else
          result = WriteLong(a1, *(unsigned int *)(v7 + a2), v6);
        if ( result )
          return result;
        a4 = v18;
        v6 += 4;
      }
      v15 = 4;
    }
    v7 += v15;
  }
  if ( v7 < (unsigned __int16)v10 )
    return 1004;
  v17 = (unsigned __int16)(v6 - a5);
  *a6 = v17;
  return v17 != v6 - a5 ? 0x3EE : 0;
}

```

## disassembly

```asm
0x18001a808  mov     [rsp+arg_0], rbx
0x18001a80d  mov     [rsp+arg_8], rbp
0x18001a812  mov     [rsp+arg_18], r9
0x18001a817  push    rsi
0x18001a818  push    rdi
0x18001a819  push    r13
0x18001a81b  push    r14
0x18001a81d  push    r15
0x18001a81f  sub     rsp, 20h
0x18001a823  mov     ebx, [rsp+48h+arg_20]
0x18001a827  xor     edi, edi
0x18001a829  movzx   r13d, byte ptr [r9]
0x18001a82d  mov     r14, rdx
0x18001a830  movzx   esi, r8w
0x18001a834  mov     r15, rcx
0x18001a837  lea     r8d, [rdi+1]
0x18001a83b  movzx   ebp, r8w
0x18001a83f  lea     r10d, [rdi+4]
0x18001a843  cmp     bp, r13w
0x18001a847  ja      loc_18001A972
0x18001a84d  movzx   eax, bp
0x18001a850  movzx   edx, byte ptr [rax+r9]
0x18001a855  mov     ecx, edx
0x18001a857  and     ecx, 7
0x18001a85a  sub     ecx, 1
0x18001a85d  jz      loc_18001A92B
0x18001a863  sub     ecx, 1
0x18001a866  jz      short loc_18001A8CD
0x18001a868  cmp     ecx, 2
0x18001a86b  jnz     loc_18001A977
0x18001a871  test    dl, 10h
0x18001a874  jnz     short loc_18001A8C4
0x18001a876  movzx   r9d, di
0x18001a87a  lea     rcx, [r9+4]
0x18001a87e  cmp     rcx, rsi
0x18001a881  ja      loc_18001A977
0x18001a887  mov     r8d, ebx
0x18001a88a  mov     rcx, r15
0x18001a88d  test    dl, 20h
0x18001a890  jz      short loc_18001A8A0
0x18001a892  lea     rdx, [r9+r14]
0x18001a896  mov     r9, r10
0x18001a899  call    WriteBytes
0x18001a89e  jmp     short loc_18001A8A9
0x18001a8a0  mov     edx, [r9+r14]
0x18001a8a4  call    WriteLong
0x18001a8a9  test    ax, ax
0x18001a8ac  jnz     loc_18001A9A0
0x18001a8b2  mov     r9, [rsp+48h+arg_18]
0x18001a8b7  mov     r10d, 4
0x18001a8bd  add     ebx, r10d
0x18001a8c0  lea     r8d, [r10-3]
0x18001a8c4  movzx   eax, r10w
0x18001a8c8  jmp     loc_18001A966
0x18001a8cd  test    dl, 10h
0x18001a8d0  jnz     short loc_18001A924
0x18001a8d2  movzx   r9d, di
0x18001a8d6  lea     rcx, [r9+2]
0x18001a8da  cmp     rcx, rsi
0x18001a8dd  ja      loc_18001A977
0x18001a8e3  mov     r8d, ebx
0x18001a8e6  mov     rcx, r15
0x18001a8e9  test    dl, 20h
0x18001a8ec  jz      short loc_18001A8FF
0x18001a8ee  lea     rdx, [r9+r14]
0x18001a8f2  mov     r9d, 2
0x18001a8f8  call    WriteBytes
0x18001a8fd  jmp     short loc_18001A909
0x18001a8ff  movzx   edx, word ptr [r9+r14]
0x18001a904  call    WriteWord
0x18001a909  test    ax, ax
0x18001a90c  jnz     loc_18001A9A0
0x18001a912  mov     r9, [rsp+48h+arg_18]
0x18001a917  mov     r8d, 1
0x18001a91d  add     ebx, 2
0x18001a920  lea     r10d, [r8+3]
0x18001a924  mov     eax, 2
0x18001a929  jmp     short loc_18001A966
0x18001a92b  test    dl, 10h
0x18001a92e  jnz     short loc_18001A962
0x18001a930  movzx   edx, di
0x18001a933  lea     rcx, [rdx+1]
0x18001a937  cmp     rcx, rsi
0x18001a93a  ja      short loc_18001A977
0x18001a93c  mov     dl, [rdx+r14]
0x18001a940  mov     r8d, ebx
0x18001a943  mov     rcx, r15
0x18001a946  call    WriteByte
0x18001a94b  test    ax, ax
0x18001a94e  jnz     short loc_18001A9A0
0x18001a950  mov     r9, [rsp+48h+arg_18]
0x18001a955  mov     r8d, 1
0x18001a95b  add     ebx, r8d
0x18001a95e  lea     r10d, [r8+3]
0x18001a962  movzx   eax, r8w
0x18001a966  add     bp, r8w
0x18001a96a  add     di, ax
0x18001a96d  jmp     loc_18001A843
0x18001a972  cmp     di, si
0x18001a975  jnb     short loc_18001A97E
0x18001a977  mov     eax, 3ECh
0x18001a97c  jmp     short loc_18001A9A0
0x18001a97e  movzx   eax, bx
0x18001a981  sub     ebx, [rsp+48h+arg_20]
0x18001a985  sub     ax, word ptr [rsp+48h+arg_20]
0x18001a98a  movzx   ecx, ax
0x18001a98d  mov     rax, [rsp+48h+arg_28]
0x18001a992  sub     ebx, ecx
0x18001a994  neg     ebx
0x18001a996  mov     [rax], cx
0x18001a999  sbb     ax, ax
0x18001a99c  and     ax, 3EEh
0x18001a9a0  mov     rbx, [rsp+48h+arg_0]
0x18001a9a5  mov     rbp, [rsp+48h+arg_8]
0x18001a9aa  add     rsp, 20h
0x18001a9ae  pop     r15
0x18001a9b0  pop     r14
0x18001a9b2  pop     r13
0x18001a9b4  pop     rdi
0x18001a9b5  pop     rsi
0x18001a9b6  retn
```
