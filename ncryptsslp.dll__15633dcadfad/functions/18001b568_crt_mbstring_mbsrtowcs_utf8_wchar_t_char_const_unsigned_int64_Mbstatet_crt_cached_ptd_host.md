# __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x18001b568`
- end: `0x18001b707`
- name: `?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `415`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, wchar_t *, const char **, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c26c`

## callees

- `0x18001b378`
- `0x18001b568`

## pseudocode

```c
__int64 __fastcall __crt_mbstring::__mbsrtowcs_utf8(
        __crt_mbstring *this,
        wchar_t *a2,
        const char **a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 v5; // rdi
  const char **v7; // rsi
  __crt_mbstring *v10; // rbx
  struct _Mbstatet *v11; // r15
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  __int16 v14; // cx
  unsigned int v15; // ecx
  __int64 i; // rbx
  struct _Mbstatet *v18; // rsi
  __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a3;
  if ( !this )
  {
    v18 = a5;
    for ( i = 0; ; i = v21 + 1 )
    {
      if ( *(_BYTE *)v5 )
        v19 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v19 = 1;
      v20 = __crt_mbstring::__mbrtoc32_utf8(0, (char32_t *)v5, (struct __crt_cached_ptd_host *)v19, a4, v18);
      if ( v20 == -1 )
        break;
      if ( !v20 )
        return i;
      v21 = i + 1;
      v5 += v20;
      if ( v20 != 4 )
        v21 = i;
    }
    LOBYTE(v18[6]._Wchar) = 1;
    *(_DWORD *)&v18[5]._Byte = 42;
    return -1;
  }
  v10 = this;
  if ( a3 )
  {
    v11 = a5;
    while ( 1 )
    {
      if ( *(_BYTE *)v5 )
        v12 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v12 = 1;
      v22 = 0;
      v13 = __crt_mbstring::__mbrtoc32_utf8(
              (unsigned __int64)&v22,
              (char32_t *)v5,
              (struct __crt_cached_ptd_host *)v12,
              a4,
              v11);
      if ( v13 == -1 )
        break;
      if ( !v13 )
      {
        v5 = 0;
        *(_WORD *)v10 = 0;
        goto LABEL_15;
      }
      v14 = v22;
      if ( v22 > 0xFFFF )
      {
        if ( (unsigned __int64)v7 <= 1 )
          goto LABEL_15;
        v15 = v22 - 0x10000;
        v7 = (const char **)((char *)v7 - 1);
        v22 = v15;
        *(_WORD *)v10 = (v15 >> 10) | 0xD800;
        v10 = (__crt_mbstring *)((char *)v10 + 2);
        v14 = v15 & 0x3FF | 0xDC00;
      }
      *(_WORD *)v10 = v14;
      v5 += v13;
      v10 = (__crt_mbstring *)((char *)v10 + 2);
      v7 = (const char **)((char *)v7 - 1);
      if ( !v7 )
        goto LABEL_15;
    }
    *(_QWORD *)a2 = v5;
    LOBYTE(v11[6]._Wchar) = 1;
    *(_DWORD *)&v11[5]._Byte = 42;
    return -1;
  }
LABEL_15:
  *(_QWORD *)a2 = v5;
  return (v10 - this) >> 1;
}

```

## disassembly

```asm
0x18001b568  mov     [rsp+arg_8], rbx
0x18001b56d  mov     [rsp+arg_10], rbp
0x18001b572  push    rsi
0x18001b573  push    rdi
0x18001b574  push    r12
0x18001b576  push    r14
0x18001b578  push    r15
0x18001b57a  sub     rsp, 30h
0x18001b57e  mov     rdi, [rdx]
0x18001b581  mov     r12, r9
0x18001b584  mov     rsi, r8
0x18001b587  mov     r14, rdx
0x18001b58a  mov     rbp, rcx
0x18001b58d  test    rcx, rcx
0x18001b590  jz      loc_18001B67B
0x18001b596  mov     rbx, rcx
0x18001b599  test    r8, r8
0x18001b59c  jz      loc_18001B64F
0x18001b5a2  mov     r15, [rsp+58h+arg_20]
0x18001b5aa  cmp     byte ptr [rdi], 0
0x18001b5ad  jnz     short loc_18001B5B7
0x18001b5af  mov     r8d, 1
0x18001b5b5  jmp     short loc_18001B5D4
0x18001b5b7  cmp     byte ptr [rdi+1], 0
0x18001b5bb  jnz     short loc_18001B5C5
0x18001b5bd  mov     r8d, 2
0x18001b5c3  jmp     short loc_18001B5D4
0x18001b5c5  mov     al, [rdi+2]
0x18001b5c8  neg     al
0x18001b5ca  sbb     r8, r8
0x18001b5cd  neg     r8
0x18001b5d0  add     r8, 3; char *
0x18001b5d4  mov     r9, r12; unsigned __int64
0x18001b5d7  mov     [rsp+58h+arg_0], 0
0x18001b5df  mov     rdx, rdi; char32_t *
0x18001b5e2  mov     [rsp+58h+var_38], r15; struct _Mbstatet *
0x18001b5e7  lea     rcx, [rsp+58h+arg_0]; this
0x18001b5ec  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b5f1  mov     rdx, rax
0x18001b5f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b5f8  jz      short loc_18001B669
0x18001b5fa  test    rax, rax
0x18001b5fd  jz      short loc_18001B660
0x18001b5ff  mov     ecx, [rsp+58h+arg_0]
0x18001b603  cmp     ecx, 0FFFFh
0x18001b609  jbe     short loc_18001B63B
0x18001b60b  cmp     rsi, 1
0x18001b60f  jbe     short loc_18001B64F
0x18001b611  add     ecx, 0FFFF0000h
0x18001b617  dec     rsi
0x18001b61a  mov     eax, ecx
0x18001b61c  mov     [rsp+58h+arg_0], ecx
0x18001b620  shr     eax, 0Ah
0x18001b623  or      ax, 0D800h
0x18001b627  mov     [rbx], ax
0x18001b62a  mov     eax, 3FFh
0x18001b62f  and     cx, ax
0x18001b632  add     rbx, 2
0x18001b636  or      cx, 0DC00h
0x18001b63b  mov     [rbx], cx
0x18001b63e  add     rdi, rdx
0x18001b641  add     rbx, 2
0x18001b645  sub     rsi, 1
0x18001b649  jnz     loc_18001B5AA
0x18001b64f  sub     rbx, rbp
0x18001b652  mov     [r14], rdi
0x18001b655  sar     rbx, 1
0x18001b658  mov     rax, rbx
0x18001b65b  jmp     loc_18001B6F0
0x18001b660  xor     edi, edi
0x18001b662  xor     eax, eax
0x18001b664  mov     [rbx], ax
0x18001b667  jmp     short loc_18001B64F
0x18001b669  mov     [r14], rdi
0x18001b66c  mov     byte ptr [r15+30h], 1
0x18001b671  mov     dword ptr [r15+2Ch], 2Ah ; '*'
0x18001b679  jmp     short loc_18001B6EC
0x18001b67b  mov     rsi, [rsp+58h+arg_20]
0x18001b683  xor     ebx, ebx
0x18001b685  cmp     byte ptr [rdi], 0
0x18001b688  jnz     short loc_18001B692
0x18001b68a  mov     r8d, 1
0x18001b690  jmp     short loc_18001B6AF
0x18001b692  cmp     byte ptr [rdi+1], 0
0x18001b696  jnz     short loc_18001B6A0
0x18001b698  mov     r8d, 2
0x18001b69e  jmp     short loc_18001B6AF
0x18001b6a0  mov     al, [rdi+2]
0x18001b6a3  neg     al
0x18001b6a5  sbb     r8, r8
0x18001b6a8  neg     r8
0x18001b6ab  add     r8, 3; char *
0x18001b6af  mov     r9, r12; unsigned __int64
0x18001b6b2  mov     [rsp+58h+var_38], rsi; struct _Mbstatet *
0x18001b6b7  mov     rdx, rdi; char32_t *
0x18001b6ba  xor     ecx, ecx; this
0x18001b6bc  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b6c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b6c5  jz      short loc_18001B6E1
0x18001b6c7  test    rax, rax
0x18001b6ca  jz      short loc_18001B658
0x18001b6cc  lea     rcx, [rbx+1]
0x18001b6d0  add     rdi, rax
0x18001b6d3  cmp     rax, 4
0x18001b6d7  cmovnz  rcx, rbx
0x18001b6db  lea     rbx, [rcx+1]
0x18001b6df  jmp     short loc_18001B685
0x18001b6e1  mov     byte ptr [rsi+30h], 1
0x18001b6e5  mov     dword ptr [rsi+2Ch], 2Ah ; '*'
0x18001b6ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b6f0  mov     rbx, [rsp+58h+arg_8]
0x18001b6f5  mov     rbp, [rsp+58h+arg_10]
0x18001b6fa  add     rsp, 30h
0x18001b6fe  pop     r15
0x18001b700  pop     r14
0x18001b702  pop     r12
0x18001b704  pop     rdi
0x18001b705  pop     rsi
0x18001b706  retn
```
