# CLogCache::_SeekRead(ulong)

- ea: `0x180015afc`
- end: `0x180015d45`
- name: `?_SeekRead@CLogCache@@AEAAJK@Z`
- size: `585`
- prototype: `__int64 __fastcall(CLogCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001591c`

## callees

- `0x180002bb8`
- `0x180015450`
- `0x18001549c`
- `0x18001556c`
- `0x180015a88`
- `0x180015afc`
- `0x18001e214`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015bc2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015c89`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015cbc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015bc2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015c89`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015cbc`

## pseudocode

```c
__int64 __fastcall CLogCache::_SeekRead(CLogCache *this, unsigned int a2)
{
  void **v2; // rsi
  _DWORD *v3; // r14
  unsigned __int64 v6; // rcx
  void *v7; // rax
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // ecx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  char *v15; // rdx
  __int64 v16; // rcx
  int v17; // r9d
  int v18; // r8d
  int v19; // eax
  int v20; // r8d
  unsigned int v21; // ebp
  void *v22; // rax
  void *v23; // rcx
  _DWORD *v24; // rsi
  int v25; // r12d
  _DWORD *v26; // r14
  int v27; // ebp
  unsigned int v28; // [rsp+80h] [rbp+8h] BYREF

  v2 = (void **)((char *)this + 24);
  v3 = (_DWORD *)((char *)this + 32);
  v28 = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    v6 = *((_DWORD *)this + 13) != 0 ? 0x8000 : 0x10000;
    *v3 = v6;
    v7 = operator new[](v6);
    *v2 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
  }
  v9 = CEventLog::SeekRead((char *)this + 8, a2, *((unsigned int *)this + 20), v2, v3, &v28);
  v8 = v9;
  if ( v9 < 0 )
  {
    v12 = 2147942438LL;
    if ( v9 == -2147024809 )
      goto LABEL_28;
    v8 = v9;
    switch ( v9 )
    {
      case -2147023396:
        goto LABEL_11;
      case -2147024858:
LABEL_28:
        if ( v8 == -2147024858 )
          goto LABEL_11;
        break;
      case -2147023393:
        break;
      default:
        goto LABEL_19;
    }
    v24 = (_DWORD *)((char *)this + 68);
    v25 = *((_DWORD *)this + 17);
    v26 = (_DWORD *)((char *)this + 64);
    v27 = *((_DWORD *)this + 16);
    CEventLog::GetOldestRecordNo((CLogCache *)((char *)this + 8), (unsigned int *)this + 17);
    CEventLog::GetNumberOfRecords((CLogCache *)((char *)this + 8), (unsigned int *)this + 16);
    if ( !*((_DWORD *)this + 16) || !*v24 )
    {
      *v24 = 0;
      v13 = 1;
      *v26 = 0;
      *((_QWORD *)this + 9) = 0;
      goto LABEL_13;
    }
    v13 = 1;
    if ( v25 != *v24 || v27 != *v26 )
      goto LABEL_13;
    *v24 = 0;
    *v26 = 0;
    *((_QWORD *)this + 9) = 0;
LABEL_12:
    v13 = 2;
LABEL_13:
    CSynchWindow::Post((CSynchWindow *)v12, 0x7E8u, v13, *((_QWORD *)this + 1));
    return v8;
  }
  v10 = *((_DWORD *)*v2 + 2);
  v11 = (unsigned __int64)*v2 + v28 - (unsigned __int64)*(unsigned int *)((char *)*v2 + v28 - 4);
  if ( *((_DWORD *)this + 20) != 4 )
  {
    v10 = *(_DWORD *)(v11 + 8);
    v11 = (unsigned __int64)*v2;
  }
  if ( v10 > *(_DWORD *)(v11 + 8) || a2 < v10 || a2 > *(_DWORD *)(v11 + 8) )
  {
    v8 = -2147023396;
    operator delete[](*v2);
    *v2 = 0;
    v28 = 0;
    *v3 = 0;
LABEL_11:
    *((_DWORD *)this + 16) = a2 - *((_DWORD *)this + 17);
    goto LABEL_12;
  }
LABEL_19:
  if ( (v8 & 0x80000000) != 0 )
  {
    *((_QWORD *)this + 9) = 0;
    return v8;
  }
  v15 = (char *)*v2;
  v16 = v28;
  v17 = *((_DWORD *)*v2 + 2);
  *((_DWORD *)this + 18) = v17;
  v18 = *(_DWORD *)&v15[v16 - *(unsigned int *)&v15[v16 - 4] + 8];
  v19 = v17 - v18;
  *((_DWORD *)this + 19) = v18;
  v20 = v18 - v17;
  if ( *((_DWORD *)this + 20) != 4 )
    v20 = v19;
  v21 = v20 + 1;
  if ( (unsigned int)(v20 + 1) <= *((_DWORD *)this + 12) )
  {
LABEL_24:
    CLogCache::_GenerateRecIndex(this, v21);
    return v8;
  }
  operator delete[](*((void **)this + 5));
  v22 = operator new[](saturated_mul(v21, 8u));
  *((_QWORD *)this + 5) = v22;
  if ( v22 )
  {
    *((_DWORD *)this + 12) = v21;
    goto LABEL_24;
  }
  v23 = *v2;
  *((_DWORD *)this + 12) = 0;
  operator delete[](v23);
  *v2 = 0;
  *((_QWORD *)this + 9) = 0;
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180015afc  mov     rax, rsp
0x180015aff  push    rbx
0x180015b00  push    rbp
0x180015b01  push    rsi
0x180015b02  push    rdi
0x180015b03  push    r12
0x180015b05  push    r13
0x180015b07  push    r14
0x180015b09  push    r15
0x180015b0b  sub     rsp, 38h
0x180015b0f  xor     r13d, r13d
0x180015b12  lea     rsi, [rcx+18h]
0x180015b16  lea     r14, [rcx+20h]
0x180015b1a  mov     ebp, edx
0x180015b1c  mov     rbx, rcx
0x180015b1f  mov     [rax+8], r13d
0x180015b23  cmp     [rsi], r13
0x180015b26  jnz     short loc_180015B58
0x180015b28  mov     eax, [rcx+34h]
0x180015b2b  neg     eax
0x180015b2d  sbb     r8d, r8d
0x180015b30  and     r8d, 0FFFF8000h
0x180015b37  lea     ecx, [r8+10000h]; unsigned __int64
0x180015b3e  mov     [r14], ecx
0x180015b41  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015b46  mov     [rsi], rax
0x180015b49  test    rax, rax
0x180015b4c  jnz     short loc_180015B58
0x180015b4e  mov     edi, 8007000Eh
0x180015b53  jmp     loc_180015BEF
0x180015b58  mov     r8d, [rbx+50h]
0x180015b5c  lea     rax, [rsp+78h+arg_0]
0x180015b64  mov     [rsp+78h+var_50], rax
0x180015b69  lea     r15, [rbx+8]
0x180015b6d  mov     rcx, r15
0x180015b70  mov     [rsp+78h+var_58], r14
0x180015b75  mov     r9, rsi
0x180015b78  mov     edx, ebp
0x180015b7a  call    ?SeekRead@CEventLog@@QEAAJKW4DIRECTION@@PEAPEAEPEAK2@Z; CEventLog::SeekRead(ulong,DIRECTION,uchar * *,ulong *,ulong *)
0x180015b7f  mov     edi, eax
0x180015b81  test    eax, eax
0x180015b83  js      short loc_180015C02
0x180015b85  mov     rax, [rsi]
0x180015b88  mov     edx, [rsp+78h+arg_0]
0x180015b8f  mov     ecx, [rdx+rax-4]
0x180015b93  sub     rdx, rcx
0x180015b96  mov     ecx, [rax+8]
0x180015b99  cmp     dword ptr [rbx+50h], 4
0x180015b9d  lea     r8, [rdx+rax]
0x180015ba1  cmovnz  ecx, [r8+8]
0x180015ba6  cmovnz  r8, rax
0x180015baa  cmp     ecx, [r8+8]
0x180015bae  ja      short loc_180015BBA
0x180015bb0  cmp     ebp, ecx
0x180015bb2  jb      short loc_180015BBA
0x180015bb4  cmp     ebp, [r8+8]
0x180015bb8  jbe     short loc_180015C30
0x180015bba  mov     rcx, rax
0x180015bbd  mov     edi, 800705DCh
0x180015bc2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015bc8  mov     [rsi], r13
0x180015bcb  mov     [rsp+78h+arg_0], r13d
0x180015bd3  mov     [r14], r13d
0x180015bd6  sub     ebp, [rbx+44h]
0x180015bd9  mov     [rbx+40h], ebp
0x180015bdc  mov     r8d, 2; unsigned __int64
0x180015be2  mov     r9, [r15]; __int64
0x180015be5  mov     edx, 7E8h; unsigned int
0x180015bea  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x180015bef  mov     eax, edi
0x180015bf1  add     rsp, 38h
0x180015bf5  pop     r15
0x180015bf7  pop     r14
0x180015bf9  pop     r13
0x180015bfb  pop     r12
0x180015bfd  pop     rdi
0x180015bfe  pop     rsi
0x180015bff  pop     rbp
0x180015c00  pop     rbx
0x180015c01  retn
0x180015c02  mov     ecx, 80070026h
0x180015c07  cmp     eax, 80070057h
0x180015c0c  jz      loc_180015CD3
0x180015c12  mov     edi, 800705DCh
0x180015c17  cmp     eax, edi
0x180015c19  mov     edi, eax
0x180015c1b  jz      short loc_180015BD6
0x180015c1d  cmp     eax, ecx
0x180015c1f  jz      loc_180015CD3
0x180015c25  cmp     eax, 800705DFh
0x180015c2a  jz      loc_180015CDB
0x180015c30  test    edi, edi
0x180015c32  jns     short loc_180015C3A
0x180015c34  mov     [rbx+48h], r13
0x180015c38  jmp     short loc_180015BEF
0x180015c3a  mov     rdx, [rsi]
0x180015c3d  mov     ecx, [rsp+78h+arg_0]
0x180015c44  mov     r9d, [rdx+8]
0x180015c48  mov     [rbx+48h], r9d
0x180015c4c  mov     eax, [rcx+rdx-4]
0x180015c50  sub     rcx, rax
0x180015c53  mov     eax, r9d
0x180015c56  mov     r8d, [rcx+rdx+8]
0x180015c5b  sub     eax, r8d
0x180015c5e  mov     [rbx+4Ch], r8d
0x180015c62  sub     r8d, r9d
0x180015c65  cmp     dword ptr [rbx+50h], 4
0x180015c69  cmovnz  r8d, eax
0x180015c6d  lea     ebp, [r8+1]
0x180015c71  cmp     ebp, [rbx+30h]
0x180015c74  ja      short loc_180015C85
0x180015c76  mov     edx, ebp; unsigned int
0x180015c78  mov     rcx, rbx; this
0x180015c7b  call    ?_GenerateRecIndex@CLogCache@@AEAAXK@Z; CLogCache::_GenerateRecIndex(ulong)
0x180015c80  jmp     loc_180015BEF
0x180015c85  mov     rcx, [rbx+28h]
0x180015c89  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015c8f  mov     ecx, ebp
0x180015c91  mov     eax, 8
0x180015c96  mul     rcx
0x180015c99  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015ca0  cmovb   rax, rcx
0x180015ca4  mov     rcx, rax; unsigned __int64
0x180015ca7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015cac  mov     [rbx+28h], rax
0x180015cb0  test    rax, rax
0x180015cb3  jnz     short loc_180015CCE
0x180015cb5  mov     rcx, [rsi]
0x180015cb8  mov     [rbx+30h], r13d
0x180015cbc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015cc2  mov     [rsi], r13
0x180015cc5  mov     [rbx+48h], r13
0x180015cc9  jmp     loc_180015B4E
0x180015cce  mov     [rbx+30h], ebp
0x180015cd1  jmp     short loc_180015C76
0x180015cd3  cmp     edi, ecx
0x180015cd5  jz      loc_180015BD6
0x180015cdb  lea     rsi, [rbx+44h]
0x180015cdf  mov     rcx, r15; this
0x180015ce2  mov     r12d, [rsi]
0x180015ce5  lea     r14, [rbx+40h]
0x180015ce9  mov     ebp, [r14]
0x180015cec  mov     rdx, rsi; unsigned int *
0x180015cef  call    ?GetOldestRecordNo@CEventLog@@QEAAJPEAK@Z; CEventLog::GetOldestRecordNo(ulong *)
0x180015cf4  mov     rdx, r14; unsigned int *
0x180015cf7  mov     rcx, r15; this
0x180015cfa  call    ?GetNumberOfRecords@CEventLog@@QEAAJPEAK@Z; CEventLog::GetNumberOfRecords(ulong *)
0x180015cff  cmp     [r14], r13d
0x180015d02  jz      short loc_180015D30
0x180015d04  cmp     [rsi], r13d
0x180015d07  jz      short loc_180015D30
0x180015d09  mov     r8d, 1
0x180015d0f  cmp     r12d, [rsi]
0x180015d12  jnz     loc_180015BE2
0x180015d18  cmp     ebp, [r14]
0x180015d1b  jnz     loc_180015BE2
0x180015d21  mov     [rsi], r13d
0x180015d24  mov     [r14], r13d
0x180015d27  mov     [rbx+48h], r13
0x180015d2b  jmp     loc_180015BDC
0x180015d30  mov     [rsi], r13d
0x180015d33  mov     r8d, 1
0x180015d39  mov     [r14], r13d
0x180015d3c  mov     [rbx+48h], r13
0x180015d40  jmp     loc_180015BE2
```
