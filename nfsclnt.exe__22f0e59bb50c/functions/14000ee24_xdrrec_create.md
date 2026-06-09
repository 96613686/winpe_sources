# xdrrec_create

- ea: `0x14000ee24`
- end: `0x14000ef60`
- name: `xdrrec_create`
- size: `316`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dcf0`

## callees

- `0x140001b2c`
- `0x14000ee24`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000ee47`
- `KERNEL32!GlobalAlloc` at `0x14000eeb4`
- `KERNEL32!GlobalAlloc` at `0x14000ee47`
- `KERNEL32!GlobalAlloc` at `0x14000eeb4`
- `KERNEL32!GlobalFree` at `0x14000eec6`
- `KERNEL32!GlobalFree` at `0x14000eec6`
- `msvcrt!fprintf` at `0x14000ee71`
- `msvcrt!fprintf` at `0x14000ee71`

## string_xrefs

- `0x14000ee6a`: `xdrrec_create: out of memory\n`

## pseudocode

```c
__int64 __fastcall xdrrec_create(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  FILE *v10; // rax
  __int64 result; // rax
  int v12; // edi
  int v13; // ebp
  __int64 v14; // rbp
  unsigned int v15; // edi
  char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx

  v8 = GlobalAlloc(0x40u, 0x78u);
  *(_QWORD *)(a1 + 24) = 0;
  v9 = v8;
  if ( !v8 )
    goto LABEL_2;
  v12 = 4000;
  v13 = 4000;
  if ( a2 >= 0x64 )
    v13 = a2;
  v14 = (v13 + 3) & 0xFFFFFFFC;
  *((_DWORD *)v8 + 28) = v14;
  if ( a3 >= 0x64 )
    v12 = a3;
  v15 = (v12 + 3) & 0xFFFFFFFC;
  *((_DWORD *)v8 + 29) = v15;
  v16 = (char *)GlobalAlloc(0x40u, v15 + (_DWORD)v14 + 4);
  v9[1] = v16;
  if ( !v16 )
  {
    GlobalFree(v9);
LABEL_2:
    v10 = _acrt_iob_func(2u);
    fprintf(v10, "xdrrec_create: out of memory\n");
    return 0;
  }
  v9[3] = v16;
  if ( ((unsigned __int8)v16 & 3) != 0 )
  {
    do
      ++v16;
    while ( ((unsigned __int8)v16 & 3) != 0 );
    v9[3] = v16;
  }
  v9[10] = &v16[(unsigned int)v14];
  *(_QWORD *)(a1 + 8) = off_1400200D0;
  *(_QWORD *)(a1 + 24) = v9;
  v17 = v9[3];
  v18 = v9[10] + v15;
  v9[8] = readtcp;
  v9[2] = writetcp;
  *v9 = a4;
  v9[4] = v17 + 4;
  v9[5] = v17 + v14;
  result = 1;
  *((_DWORD *)v9 + 27) = 1;
  v9[6] = v17;
  *((_DWORD *)v9 + 14) = 0;
  *((_DWORD *)v9 + 18) = v15;
  v9[12] = v18;
  v9[11] = v18;
  *((_DWORD *)v9 + 26) = 0;
  return result;
}

```

## disassembly

```asm
0x14000ee24  push    rbx
0x14000ee26  push    rbp
0x14000ee27  push    rsi
0x14000ee28  push    rdi
0x14000ee29  push    r12
0x14000ee2b  push    r14
0x14000ee2d  push    r15
0x14000ee2f  sub     rsp, 20h
0x14000ee33  mov     r15d, edx
0x14000ee36  mov     rsi, rcx
0x14000ee39  mov     edx, 78h ; 'x'; dwBytes
0x14000ee3e  mov     r12, r9
0x14000ee41  mov     r14d, r8d
0x14000ee44  lea     ecx, [rdx-38h]; uFlags
0x14000ee47  call    cs:__imp_GlobalAlloc
0x14000ee4d  mov     qword ptr [rsi+18h], 0
0x14000ee55  mov     rbx, rax
0x14000ee58  test    rax, rax
0x14000ee5b  jnz     short loc_14000EE7E
0x14000ee5d  mov     ecx, 2; Ix
0x14000ee62  call    __acrt_iob_func
0x14000ee67  mov     rcx, rax; Stream
0x14000ee6a  lea     rdx, aXdrrecCreateOu; "xdrrec_create: out of memory\n"
0x14000ee71  call    cs:__imp_fprintf
0x14000ee77  xor     eax, eax
0x14000ee79  jmp     loc_14000EF51
0x14000ee7e  mov     eax, 0FFFFFFFCh
0x14000ee83  mov     edi, 0FA0h
0x14000ee88  mov     ebp, edi
0x14000ee8a  cmp     r15d, 64h ; 'd'
0x14000ee8e  mov     ecx, 40h ; '@'; uFlags
0x14000ee93  cmovnb  ebp, r15d
0x14000ee97  add     ebp, 3
0x14000ee9a  and     ebp, eax
0x14000ee9c  cmp     r14d, 64h ; 'd'
0x14000eea0  mov     [rbx+70h], ebp
0x14000eea3  cmovnb  edi, r14d
0x14000eea7  lea     edx, [rbp+4]
0x14000eeaa  add     edi, 3
0x14000eead  and     edi, eax
0x14000eeaf  add     edx, edi; dwBytes
0x14000eeb1  mov     [rbx+74h], edi
0x14000eeb4  call    cs:__imp_GlobalAlloc
0x14000eeba  mov     [rbx+8], rax
0x14000eebe  test    rax, rax
0x14000eec1  jnz     short loc_14000EECE
0x14000eec3  mov     rcx, rbx; hMem
0x14000eec6  call    cs:__imp_GlobalFree
0x14000eecc  jmp     short loc_14000EE5D
0x14000eece  mov     [rbx+18h], rax
0x14000eed2  test    al, 3
0x14000eed4  jz      short loc_14000EEE1
0x14000eed6  inc     rax
0x14000eed9  test    al, 3
0x14000eedb  jnz     short loc_14000EED6
0x14000eedd  mov     [rbx+18h], rax
0x14000eee1  mov     edx, ebp
0x14000eee3  add     rax, rdx
0x14000eee6  mov     edx, edi
0x14000eee8  mov     [rbx+50h], rax
0x14000eeec  lea     rax, off_1400200D0
0x14000eef3  mov     [rsi+8], rax
0x14000eef7  lea     rax, readtcp
0x14000eefe  mov     [rsi+18h], rbx
0x14000ef02  mov     rcx, [rbx+18h]
0x14000ef06  add     rdx, [rbx+50h]
0x14000ef0a  mov     [rbx+40h], rax
0x14000ef0e  lea     rax, writetcp
0x14000ef15  mov     [rbx+10h], rax
0x14000ef19  lea     rax, [rcx+4]
0x14000ef1d  mov     [rbx], r12
0x14000ef20  mov     [rbx+20h], rax
0x14000ef24  lea     rax, [rcx+rbp]
0x14000ef28  mov     [rbx+28h], rax
0x14000ef2c  mov     eax, 1
0x14000ef31  mov     [rbx+6Ch], eax
0x14000ef34  mov     [rbx+30h], rcx
0x14000ef38  mov     dword ptr [rbx+38h], 0
0x14000ef3f  mov     [rbx+48h], edi
0x14000ef42  mov     [rbx+60h], rdx
0x14000ef46  mov     [rbx+58h], rdx
0x14000ef4a  mov     dword ptr [rbx+68h], 0
0x14000ef51  add     rsp, 20h
0x14000ef55  pop     r15
0x14000ef57  pop     r14
0x14000ef59  pop     r12
0x14000ef5b  pop     rdi
0x14000ef5c  pop     rsi
0x14000ef5d  pop     rbp
0x14000ef5e  pop     rbx
0x14000ef5f  retn
```
