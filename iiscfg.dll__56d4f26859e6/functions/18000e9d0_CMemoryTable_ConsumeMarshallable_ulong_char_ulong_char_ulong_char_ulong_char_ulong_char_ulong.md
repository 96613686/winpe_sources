# CMemoryTable::ConsumeMarshallable(ulong,char *,ulong,char *,ulong,char *,ulong,char *,ulong,char *,ulong)

- ea: `0x18000e9d0`
- end: `0x18000ecb0`
- name: `?ConsumeMarshallable@CMemoryTable@@UEAAJKPEADK0K0K0K0K@Z`
- size: `736`
- prototype: `int(CMemoryTable *__hidden this, unsigned int, char *, unsigned int, char *, unsigned int, char *, unsigned int, char *, unsigned int, char *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000e870`
- `0x18000e8d8`
- `0x18000e948`
- `0x18000e9d0`
- `0x18002e0b2`
- `0x18002e0be`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000eb3b`
- `ole32!CoTaskMemRealloc` at `0x18000eb3b`

## pseudocode

```c
__int64 __fastcall CMemoryTable::ConsumeMarshallable(
        CMemoryTable *this,
        int a2,
        char *a3,
        unsigned int a4,
        char *a5,
        unsigned int a6,
        char *a7,
        unsigned int a8)
{
  char *v8; // r13
  size_t v9; // r15
  _DWORD *v13; // rbx
  unsigned int v14; // r14d
  _DWORD *v15; // r12
  _DWORD *v16; // rsi
  char *v17; // rax
  size_t v18; // r8
  char *v19; // rdx
  int v20; // ebx
  int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r11
  unsigned int v25; // r10d
  __int64 i; // rdx
  __int64 j; // r8
  __int64 v28; // rcx
  __int64 v29; // rax
  _DWORD *v30; // [rsp+20h] [rbp-48h]
  _DWORD *v31; // [rsp+28h] [rbp-40h]

  v8 = (char *)this - 24;
  v9 = a4;
  if ( (*((_BYTE *)this + 68) & 2) != 0 || (v8[92] & 1) == 0 )
    return 2149648405LL;
  if ( (a2 & 0xFFE0FFFF) != 0 )
    return 2147942487LL;
  v13 = (_DWORD *)((char *)this + 20);
  v14 = a4 - a6;
  v31 = (_DWORD *)((char *)this + 20);
  v15 = (_DWORD *)((char *)this + 24);
  v30 = (_DWORD *)((char *)this + 16);
  v16 = (_DWORD *)((char *)this + 68);
  if ( (a2 & 0x10000) != 0 )
  {
    CMemoryTable::CleanupReadCache((CMemoryTable *)((char *)this - 24));
    *((_DWORD *)this + 20) = a6;
    *((_QWORD *)this + 12) = a3;
    *((_DWORD *)this + 26) = v9;
    *((_DWORD *)this + 27) = v9;
    *((_DWORD *)this + 19) = v14 / (8 * (*((_DWORD *)this + 4) + *v13 + *v15) + 8);
    *v16 |= 0x10000u;
    *((_QWORD *)this + 11) = &a3[v14];
  }
  else
  {
    v31 = (_DWORD *)((char *)this + 20);
    v30 = (_DWORD *)((char *)this + 16);
  }
  if ( (a2 & 0x20000) != 0 || (a2 & 0x80000) != 0 )
  {
    if ( (a2 & 0x100000) != 0 )
    {
      v17 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 16), (unsigned int)(v9 + *((_DWORD *)v8 + 40)));
      *((_QWORD *)this + 16) = v17;
      if ( !v17 )
        return 2147942414LL;
      v18 = *((unsigned int *)this + 29);
      v19 = &v17[(unsigned int)(*((_DWORD *)this + 34) - v18)];
      *((_QWORD *)this + 15) = v19;
      memmove_0(&v19[v9], v19, v18);
      memcpy_0(*((void **)this + 15), a3, v9);
      *((_DWORD *)this + 34) += v9;
      v20 = *((_DWORD *)this + 29);
      v21 = *((_DWORD *)this + 34);
      *((_DWORD *)this + 35) = v21;
      v22 = v21 - v20 - a6;
      v23 = *((_QWORD *)this + 16);
      *((_DWORD *)this + 29) = v20 + a6;
      v24 = (unsigned int)(8 * (*v30 + *v15 + *v31) + 8);
      *((_DWORD *)this + 28) = (unsigned int)v22 / (unsigned int)v24;
      *((_QWORD *)this + 15) = v23 + v22;
      v25 = v14 / (unsigned int)v24;
      for ( i = v23 + (unsigned int)v24 * ((unsigned int)v22 / (unsigned int)v24 - v14 / (unsigned int)v24); v25; i += v24 )
      {
        --v25;
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 3); j = (unsigned int)(j + 1) )
        {
          if ( (*(_DWORD *)(*((_QWORD *)this + 4) + 12 * j + 8) & 0x10000000) != 0 )
          {
            v28 = *((_QWORD *)this + 5);
            if ( (*(_BYTE *)(*(unsigned __int16 *)(v28 + 8 * j) + i) & 2) != 0 )
            {
              v29 = *(unsigned int *)(v28 + 8 * j + 4);
              *(_DWORD *)(i + 8 * v29) += v20;
            }
          }
        }
      }
    }
    else
    {
      CMemoryTable::CleanupWriteCache((CMemoryTable *)v8);
      *((_DWORD *)this + 29) = a6;
      *((_QWORD *)this + 16) = a3;
      *((_DWORD *)v8 + 40) = v9;
      *((_DWORD *)this + 35) = v9;
      *((_DWORD *)this + 28) = v14 / (8 * (*v30 + *v15 + *v13) + 8);
      *((_QWORD *)this + 15) = &a3[v14];
      if ( (a2 & 0x20000) != 0 )
        *v16 |= 0x20000u;
    }
  }
  if ( (a2 & 0x40000) != 0 )
  {
    CMemoryTable::CleanupErrorCache((CMemoryTable *)v8);
    *((_QWORD *)this + 19) = a7;
    *v16 |= 0x40000u;
    *((_DWORD *)this + 36) = a8 / 0xC;
    *((_DWORD *)this + 37) = a8 / 0xC;
  }
  *v16 |= 4u;
  return 0;
}

```

## disassembly

```asm
0x18000e9d0  mov     [rsp+arg_8], rbx
0x18000e9d5  mov     [rsp+Src], r8
0x18000e9da  push    rbp
0x18000e9db  push    rsi
0x18000e9dc  push    rdi
0x18000e9dd  push    r12
0x18000e9df  push    r13
0x18000e9e1  push    r14
0x18000e9e3  push    r15
0x18000e9e5  sub     rsp, 30h
0x18000e9e9  lea     r13, [rcx-18h]
0x18000e9ed  mov     r15d, r9d
0x18000e9f0  test    byte ptr [r13+5Ch], 2
0x18000e9f5  mov     ebp, edx
0x18000e9f7  mov     rdi, rcx
0x18000e9fa  jnz     loc_18000EC96
0x18000ea00  test    byte ptr [r13+5Ch], 1
0x18000ea05  jz      loc_18000EC96
0x18000ea0b  test    edx, 0FFE0FFFFh
0x18000ea11  jz      short loc_18000EA1D
0x18000ea13  mov     eax, 80070057h
0x18000ea18  jmp     loc_18000EC9B
0x18000ea1d  mov     r14d, r15d
0x18000ea20  lea     rbx, [rcx+14h]
0x18000ea24  sub     r14d, [rsp+68h+arg_28]
0x18000ea2c  lea     rax, [rcx+10h]
0x18000ea30  mov     [rsp+68h+var_40], rbx
0x18000ea35  lea     r12, [rcx+18h]
0x18000ea39  mov     [rsp+68h+var_48], rax
0x18000ea3e  lea     rsi, [rcx+44h]
0x18000ea42  bt      ebp, 10h
0x18000ea46  jnb     short loc_18000EA98
0x18000ea48  mov     rcx, r13; this
0x18000ea4b  call    ?CleanupReadCache@CMemoryTable@@AEAAXXZ; CMemoryTable::CleanupReadCache(void)
0x18000ea50  mov     eax, [rsp+68h+arg_28]
0x18000ea57  xor     edx, edx
0x18000ea59  mov     r8, [rsp+68h+Src]
0x18000ea61  mov     [rdi+50h], eax
0x18000ea64  mov     eax, r14d
0x18000ea67  mov     [rdi+60h], r8
0x18000ea6b  mov     [rdi+68h], r15d
0x18000ea6f  mov     [rdi+6Ch], r15d
0x18000ea73  mov     ecx, [r12]
0x18000ea77  add     ecx, [rbx]
0x18000ea79  add     ecx, [rdi+10h]
0x18000ea7c  lea     ecx, ds:8[rcx*8]
0x18000ea83  div     ecx
0x18000ea85  mov     [rdi+4Ch], eax
0x18000ea88  mov     eax, r14d
0x18000ea8b  add     rax, r8
0x18000ea8e  bts     dword ptr [rsi], 10h
0x18000ea92  mov     [rdi+58h], rax
0x18000ea96  jmp     short loc_18000EAA2
0x18000ea98  mov     [rsp+68h+var_40], rbx
0x18000ea9d  mov     [rsp+68h+var_48], rax
0x18000eaa2  mov     eax, ebp
0x18000eaa4  and     eax, 20000h
0x18000eaa9  mov     [rsp+68h+arg_0], eax
0x18000eaad  jnz     short loc_18000EAB9
0x18000eaaf  bt      ebp, 13h
0x18000eab3  jnb     loc_18000EC49
0x18000eab9  bt      ebp, 14h
0x18000eabd  jb      short loc_18000EB2A
0x18000eabf  mov     rcx, r13; this
0x18000eac2  call    ?CleanupWriteCache@CMemoryTable@@AEAAXXZ; CMemoryTable::CleanupWriteCache(void)
0x18000eac7  mov     r9, [rsp+68h+Src]
0x18000eacf  xor     edx, edx
0x18000ead1  mov     eax, [rsp+68h+arg_28]
0x18000ead8  mov     [rdi+74h], eax
0x18000eadb  mov     rax, [rsp+68h+var_48]
0x18000eae0  mov     [rdi+80h], r9
0x18000eae7  mov     [r13+0A0h], r15d
0x18000eaee  mov     [rdi+8Ch], r15d
0x18000eaf5  mov     ecx, [rbx]
0x18000eaf7  add     ecx, [r12]
0x18000eafb  add     ecx, [rax]
0x18000eafd  mov     eax, r14d
0x18000eb00  lea     ecx, ds:8[rcx*8]
0x18000eb07  div     ecx
0x18000eb09  mov     [rdi+70h], eax
0x18000eb0c  mov     eax, r14d
0x18000eb0f  add     rax, r9
0x18000eb12  cmp     [rsp+68h+arg_0], 0
0x18000eb17  mov     [rdi+78h], rax
0x18000eb1b  jz      loc_18000EC49
0x18000eb21  bts     dword ptr [rsi], 11h
0x18000eb25  jmp     loc_18000EC49
0x18000eb2a  mov     edx, [r13+0A0h]
0x18000eb31  mov     rcx, [rdi+80h]; pv
0x18000eb38  add     edx, r15d; cb
0x18000eb3b  call    cs:__imp_CoTaskMemRealloc
0x18000eb41  mov     [rdi+80h], rax
0x18000eb48  test    rax, rax
0x18000eb4b  jnz     short loc_18000EB57
0x18000eb4d  mov     eax, 8007000Eh
0x18000eb52  jmp     loc_18000EC9B
0x18000eb57  mov     edx, [rdi+88h]
0x18000eb5d  mov     r8d, [rdi+74h]; Size
0x18000eb61  sub     edx, r8d
0x18000eb64  add     rdx, rax; Src
0x18000eb67  mov     [rdi+78h], rdx
0x18000eb6b  lea     rcx, [r15+rdx]; void *
0x18000eb6f  call    memmove_0
0x18000eb74  mov     rdx, [rsp+68h+Src]; Src
0x18000eb7c  mov     r8, r15; Size
0x18000eb7f  mov     rcx, [rdi+78h]; void *
0x18000eb83  call    memcpy_0
0x18000eb88  add     [rdi+88h], r15d
0x18000eb8f  mov     r8d, [rsp+68h+arg_28]
0x18000eb97  mov     ebx, [rdi+74h]
0x18000eb9a  mov     ecx, [rdi+88h]
0x18000eba0  mov     rdx, [rsp+68h+var_48]
0x18000eba5  mov     [rdi+8Ch], ecx
0x18000ebab  sub     ecx, ebx
0x18000ebad  sub     ecx, r8d
0x18000ebb0  lea     eax, [rbx+r8]
0x18000ebb4  mov     r8, [rdi+80h]
0x18000ebbb  mov     [rdi+74h], eax
0x18000ebbe  mov     rax, [rsp+68h+var_40]
0x18000ebc3  mov     eax, [rax]
0x18000ebc5  add     eax, [r12]
0x18000ebc9  add     eax, [rdx]
0x18000ebcb  xor     edx, edx
0x18000ebcd  lea     r11d, ds:8[rax*8]
0x18000ebd5  mov     eax, ecx
0x18000ebd7  div     r11d
0x18000ebda  xor     edx, edx
0x18000ebdc  add     rcx, r8
0x18000ebdf  mov     r9d, eax
0x18000ebe2  mov     [rdi+70h], eax
0x18000ebe5  mov     eax, r14d
0x18000ebe8  mov     [rdi+78h], rcx
0x18000ebec  div     r11d
0x18000ebef  sub     r9d, eax
0x18000ebf2  mov     r10d, eax
0x18000ebf5  imul    r9d, r11d
0x18000ebf9  mov     edx, r9d
0x18000ebfc  add     rdx, r8
0x18000ebff  test    eax, eax
0x18000ec01  jz      short loc_18000EC49
0x18000ec03  dec     r10d
0x18000ec06  xor     r8d, r8d
0x18000ec09  cmp     [rdi+0Ch], r8d
0x18000ec0d  jbe     short loc_18000EC41
0x18000ec0f  mov     rax, [rdi+20h]
0x18000ec13  lea     rcx, [r8+r8*2]
0x18000ec17  test    dword ptr [rax+rcx*4+8], 10000000h
0x18000ec1f  jz      short loc_18000EC38
0x18000ec21  mov     rcx, [rdi+28h]
0x18000ec25  movzx   eax, word ptr [rcx+r8*8]
0x18000ec2a  test    byte ptr [rax+rdx], 2
0x18000ec2e  jz      short loc_18000EC38
0x18000ec30  mov     eax, [rcx+r8*8+4]
0x18000ec35  add     [rdx+rax*8], ebx
0x18000ec38  inc     r8d
0x18000ec3b  cmp     r8d, [rdi+0Ch]
0x18000ec3f  jb      short loc_18000EC0F
0x18000ec41  add     rdx, r11
0x18000ec44  test    r10d, r10d
0x18000ec47  jnz     short loc_18000EC03
0x18000ec49  mov     ebx, 40000h
0x18000ec4e  test    ebx, ebp
0x18000ec50  jz      short loc_18000EC8F
0x18000ec52  mov     rcx, r13; this
0x18000ec55  call    ?CleanupErrorCache@CMemoryTable@@AEAAXXZ; CMemoryTable::CleanupErrorCache(void)
0x18000ec5a  mov     rax, [rsp+68h+arg_30]
0x18000ec62  mov     ecx, [rsp+68h+arg_38]
0x18000ec69  mov     [rdi+98h], rax
0x18000ec70  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ec7a  mul     rcx
0x18000ec7d  shr     rdx, 3
0x18000ec81  or      [rsi], ebx
0x18000ec83  mov     [rdi+90h], edx
0x18000ec89  mov     [rdi+94h], edx
0x18000ec8f  or      dword ptr [rsi], 4
0x18000ec92  xor     eax, eax
0x18000ec94  jmp     short loc_18000EC9B
0x18000ec96  mov     eax, 80210815h
0x18000ec9b  mov     rbx, [rsp+68h+arg_8]
0x18000eca0  add     rsp, 30h
0x18000eca4  pop     r15
0x18000eca6  pop     r14
0x18000eca8  pop     r13
0x18000ecaa  pop     r12
0x18000ecac  pop     rdi
0x18000ecad  pop     rsi
0x18000ecae  pop     rbp
0x18000ecaf  retn
```
