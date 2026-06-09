# OneXCreateDefaultUserProfile

- ea: `0x1800310cc`
- end: `0x1800311fe`
- name: `OneXCreateDefaultUserProfile`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003184c`

## callees

- `0x180030fd8`
- `0x180031004`
- `0x1800310cc`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x1800311e6`
- `MobileNetworking!FreeMemory` at `0x1800311e6`
- `MobileNetworking!AllocateMemory` at `0x1800310fe`
- `MobileNetworking!AllocateMemory` at `0x1800310fe`

## string_xrefs

- `0x1800310ef`: `OneXCreateDefaultUserProfile`
- `0x1800311db`: `OneXCreateDefaultUserProfile`

## pseudocode

```c
__int64 __fastcall OneXCreateDefaultUserProfile(_QWORD *a1)
{
  unsigned int AlignedSize; // ebx
  __int64 v3; // r8
  __int64 v4; // r8
  unsigned int v5; // r10d
  _DWORD *v6; // r8
  __int64 v7; // r9
  char *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // r10d
  int v12; // r11d
  _DWORD *v14; // [rsp+38h] [rbp+18h] BYREF

  v14 = 0;
  AlignedSize = AllocateMemory(64, &v14, "OneXCreateDefaultUserProfile", 48);
  if ( AlignedSize )
    goto LABEL_8;
  *v14 = 2;
  v14[1] = 64;
  AlignedSize = GetAlignedSize(28, v14 + 4, v3);
  if ( AlignedSize )
    goto LABEL_8;
  AlignedSize = GetAlignedSize(32, v14 + 3, v4);
  if ( AlignedSize )
    goto LABEL_8;
  v6 = v14;
  v7 = (unsigned int)v14[4];
  v8 = (char *)v14 + v7 + 28;
  *(_DWORD *)((char *)v14 + v7) &= ~1u;
  *(_DWORD *)((char *)v6 + v7 + 20) = 0;
  AlignedSize = GetAlignedSize(v5, v8, v6);
  if ( AlignedSize
    || (*(_DWORD *)(v10 + v9 + 24) = 0,
        *(_OWORD *)(v10 + v9 + 4) = 0,
        (AlignedSize = GetAlignedSize(28, v14 + 6, v9)) != 0)
    || (AlignedSize = IncrementDwordByAlignedSize(v11)) != 0 )
  {
LABEL_8:
    FreeMemory(&v14, "OneXCreateDefaultUserProfile", 77);
  }
  else
  {
    v14[5] = 0;
    v14[2] &= v12;
    *a1 = v14;
  }
  return AlignedSize;
}

```

## disassembly

```asm
0x1800310cc  mov     [rsp-8+arg_0], rbx
0x1800310d1  mov     [rsp-8+arg_10], rdi
0x1800310d6  push    rbp
0x1800310d7  mov     rbp, rsp
0x1800310da  sub     rsp, 20h
0x1800310de  mov     rdi, rcx
0x1800310e1  mov     [rbp+arg_8], 0
0x1800310e9  mov     r9d, 30h ; '0'
0x1800310ef  lea     r8, aOnexcreatedefa_0; "OneXCreateDefaultUserProfile"
0x1800310f6  lea     rdx, [rbp+arg_8]
0x1800310fa  lea     ecx, [r9+10h]
0x1800310fe  call    cs:__imp_AllocateMemory
0x180031104  mov     ebx, eax
0x180031106  test    eax, eax
0x180031108  jnz     loc_1800311D5
0x18003110e  mov     rax, [rbp+arg_8]
0x180031112  lea     ecx, [rbx+1Ch]
0x180031115  mov     dword ptr [rax], 2
0x18003111b  mov     rax, [rbp+arg_8]
0x18003111f  mov     dword ptr [rax+4], 40h ; '@'
0x180031126  mov     rdx, [rbp+arg_8]
0x18003112a  add     rdx, 10h
0x18003112e  call    GetAlignedSize
0x180031133  mov     ebx, eax
0x180031135  test    eax, eax
0x180031137  jnz     loc_1800311D5
0x18003113d  mov     rdx, [rbp+arg_8]
0x180031141  lea     r10d, [rax+20h]
0x180031145  add     rdx, 0Ch
0x180031149  mov     ecx, r10d
0x18003114c  call    GetAlignedSize
0x180031151  mov     ebx, eax
0x180031153  test    eax, eax
0x180031155  jnz     short loc_1800311D5
0x180031157  mov     r8, [rbp+arg_8]
0x18003115b  mov     r11d, 0FFFFFFFEh
0x180031161  mov     ecx, r10d
0x180031164  mov     r9d, [r8+10h]
0x180031168  lea     rdx, [r8+1Ch]
0x18003116c  add     rdx, r9
0x18003116f  and     [r9+r8], r11d
0x180031173  mov     [r9+r8+14h], eax
0x180031178  call    GetAlignedSize
0x18003117d  mov     ebx, eax
0x18003117f  test    eax, eax
0x180031181  jnz     short loc_1800311D5
0x180031183  mov     [r9+r8+18h], eax
0x180031188  lea     ecx, [rax+1Ch]
0x18003118b  xorps   xmm0, xmm0
0x18003118e  movups  xmmword ptr [r9+r8+4], xmm0
0x180031194  mov     rdx, [rbp+arg_8]
0x180031198  add     rdx, 18h
0x18003119c  call    GetAlignedSize
0x1800311a1  mov     ebx, eax
0x1800311a3  test    eax, eax
0x1800311a5  jnz     short loc_1800311D5
0x1800311a7  mov     rdx, [rbp+arg_8]
0x1800311ab  mov     ecx, r10d
0x1800311ae  add     rdx, 18h
0x1800311b2  call    IncrementDwordByAlignedSize
0x1800311b7  mov     ebx, eax
0x1800311b9  test    eax, eax
0x1800311bb  jnz     short loc_1800311D5
0x1800311bd  mov     rax, [rbp+arg_8]
0x1800311c1  mov     [rax+14h], ebx
0x1800311c4  mov     rax, [rbp+arg_8]
0x1800311c8  and     [rax+8], r11d
0x1800311cc  mov     rax, [rbp+arg_8]
0x1800311d0  mov     [rdi], rax
0x1800311d3  jmp     short loc_1800311EC
0x1800311d5  mov     r8d, 4Dh ; 'M'
0x1800311db  lea     rdx, aOnexcreatedefa_0; "OneXCreateDefaultUserProfile"
0x1800311e2  lea     rcx, [rbp+arg_8]
0x1800311e6  call    cs:__imp_FreeMemory
0x1800311ec  mov     rdi, [rsp+20h+arg_10]
0x1800311f1  mov     eax, ebx
0x1800311f3  mov     rbx, [rsp+20h+arg_0]
0x1800311f8  add     rsp, 20h
0x1800311fc  pop     rbp
0x1800311fd  retn
```
