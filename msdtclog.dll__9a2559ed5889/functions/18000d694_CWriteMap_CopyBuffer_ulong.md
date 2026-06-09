# CWriteMap::_CopyBuffer(ulong)

- ea: `0x18000d694`
- end: `0x18000d86c`
- name: `?_CopyBuffer@CWriteMap@@AEAAXK@Z`
- size: `472`
- prototype: `void __fastcall(CWriteMap *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d3ec`

## callees

- `0x180005a7c`
- `0x18000d694`
- `0x18001266c`
- `0x1800127fe`

## pseudocode

```c
void __fastcall CWriteMap::_CopyBuffer(CWriteMap *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdi
  __int64 v5; // rdi
  int v6; // ebp
  const void *v7; // r13
  char *i; // r12
  unsigned int v9; // r14d
  int v10; // r15d
  unsigned int v11; // r9d
  __int64 v12; // rcx
  unsigned int v13; // ecx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdi
  int pExceptionObject; // [rsp+78h] [rbp+10h] BYREF

  v2 = 32LL * a2;
  v4 = *(_QWORD *)((char *)this + v2 + 104);
  if ( *(_DWORD *)(v4 + 64) )
    return;
  v5 = *(_QWORD *)(v4 + 56);
  if ( !v5 )
    return;
  v6 = 1;
  v7 = (const void *)*((_QWORD *)this + 8);
  for ( i = (char *)(v5 + *(unsigned int *)((char *)this + v2 + 84) + 32LL); ; i += v9 )
  {
    while ( 1 )
    {
      v9 = *((_DWORD *)this + 14);
      if ( *(_DWORD *)(v5 + 24) <= v9 )
      {
        v9 = *(_DWORD *)(v5 + 24);
        v10 = 0;
      }
      else
      {
        v10 = 1;
      }
      memmove_0(i, v7, v9);
      v12 = *(unsigned int *)(v5 + 24);
      if ( v10 )
        break;
      *(_DWORD *)(v5 + 24) = 0;
      *((_QWORD *)this + 8) += v12;
      *((_DWORD *)this + 14) -= v12;
      CBuffer::FreePage(*(CBuffer **)((char *)this + v2 + 104), (struct _RECORDPAGE *)v5, 1, v11);
      v21 = *(_QWORD *)((char *)this + v2 + 104);
      if ( *(_DWORD *)(v21 + 64) )
        return;
      v5 = *(_QWORD *)(v21 + 56);
      if ( !v5 )
        return;
      i = (char *)(v5 + 32);
      *(_DWORD *)(v5 + 28) = 0;
    }
    v13 = v12 - v9;
    *(_DWORD *)(v5 + 24) = v13;
    if ( v13 > 0x2000 )
    {
      pExceptionObject = -2147418113;
      throw (long *)&pExceptionObject;
    }
    if ( *(_DWORD *)this )
    {
      v16 = (unsigned int)++*((_DWORD *)this + 10);
      if ( (_DWORD)v16 != *(_DWORD *)this )
      {
        v20 = *((_QWORD *)this + 1);
        *((_DWORD *)this + 14) = *(_DWORD *)(v20 + 16 * v16 + 8);
        *((_QWORD *)this + 8) = *(_QWORD *)(v20 + 16 * v16);
        goto LABEL_17;
      }
    }
    else
    {
      v14 = (__int64 *)*((_QWORD *)this + 6);
      v15 = *v14;
      *((_QWORD *)this + 6) = *v14;
      if ( !v15 )
      {
        *((_DWORD *)this + 14) = MEMORY[8];
        *((_QWORD *)this + 8) = 12;
LABEL_17:
        v18 = 1;
        goto LABEL_18;
      }
    }
    v17 = *(_DWORD *)(v5 + 24);
    v18 = 0;
    if ( v17 < *((_DWORD *)this + 19) )
    {
      pExceptionObject = -2147418113;
      throw (long *)&pExceptionObject;
    }
    v19 = v17 - *((_DWORD *)this + 19);
    *(_DWORD *)(v5 + 24) = v19;
    if ( v19 > 0x2000 )
    {
      pExceptionObject = -2147418113;
      throw (long *)&pExceptionObject;
    }
LABEL_18:
    if ( !v18 )
      break;
    v7 = (const void *)*((_QWORD *)this + 8);
  }
  if ( !*(_DWORD *)((char *)this + v2 + 112) )
  {
    if ( *(_DWORD *)(v5 + 24) )
      v6 = 0;
  }
  CBuffer::FreePage(*(CBuffer **)((char *)this + v2 + 104), (struct _RECORDPAGE *)v5, v6, v11);
}

```

## disassembly

```asm
0x18000d694  push    rbx
0x18000d696  push    rbp
0x18000d697  push    rsi
0x18000d698  push    rdi
0x18000d699  push    r12
0x18000d69b  push    r13
0x18000d69d  push    r14
0x18000d69f  push    r15
0x18000d6a1  sub     rsp, 28h
0x18000d6a5  mov     esi, edx
0x18000d6a7  xor     r8d, r8d
0x18000d6aa  shl     rsi, 5
0x18000d6ae  mov     rbx, rcx
0x18000d6b1  mov     rdi, [rsi+rcx+68h]
0x18000d6b6  cmp     [rdi+40h], r8d
0x18000d6ba  jnz     loc_18000D80D
0x18000d6c0  mov     rdi, [rdi+38h]
0x18000d6c4  test    rdi, rdi
0x18000d6c7  jz      loc_18000D80D
0x18000d6cd  mov     r12d, [rsi+rcx+54h]
0x18000d6d2  lea     ebp, [r8+1]
0x18000d6d6  mov     r13, [rcx+40h]
0x18000d6da  add     r12, 20h ; ' '
0x18000d6de  add     r12, rdi
0x18000d6e1  mov     r14d, [rbx+38h]
0x18000d6e5  cmp     [rdi+18h], r14d
0x18000d6e9  jbe     short loc_18000D6F0
0x18000d6eb  mov     r15d, ebp
0x18000d6ee  jmp     short loc_18000D6F7
0x18000d6f0  mov     r14d, [rdi+18h]
0x18000d6f4  mov     r15d, r8d
0x18000d6f7  mov     r8d, r14d; Size
0x18000d6fa  mov     rdx, r13; Src
0x18000d6fd  mov     rcx, r12; void *
0x18000d700  call    memmove_0
0x18000d705  mov     ecx, [rdi+18h]
0x18000d708  xor     r8d, r8d
0x18000d70b  test    r15d, r15d
0x18000d70e  jz      loc_18000D7A9
0x18000d714  sub     ecx, r14d
0x18000d717  mov     [rdi+18h], ecx
0x18000d71a  cmp     ecx, 2000h
0x18000d720  ja      loc_18000D81E
0x18000d726  cmp     [rbx], r8d
0x18000d729  jnz     short loc_18000D74F
0x18000d72b  mov     rax, [rbx+30h]
0x18000d72f  mov     rcx, [rax]
0x18000d732  mov     [rbx+30h], rcx
0x18000d736  test    rcx, rcx
0x18000d739  jnz     short loc_18000D759
0x18000d73b  mov     eax, ds:8
0x18000d742  mov     [rbx+38h], eax
0x18000d745  mov     qword ptr [rbx+40h], 0Ch
0x18000d74d  jmp     short loc_18000D794
0x18000d74f  add     [rbx+28h], ebp
0x18000d752  mov     eax, [rbx+28h]
0x18000d755  cmp     eax, [rbx]
0x18000d757  jnz     short loc_18000D77B
0x18000d759  mov     eax, [rdi+18h]
0x18000d75c  mov     ecx, r8d
0x18000d75f  cmp     eax, [rbx+4Ch]
0x18000d762  jb      loc_18000D852
0x18000d768  sub     eax, [rbx+4Ch]
0x18000d76b  mov     [rdi+18h], eax
0x18000d76e  cmp     eax, 2000h
0x18000d773  ja      loc_18000D838
0x18000d779  jmp     short loc_18000D796
0x18000d77b  mov     rcx, [rbx+8]
0x18000d77f  mov     rdx, rax
0x18000d782  add     rdx, rdx
0x18000d785  mov     eax, [rcx+rdx*8+8]
0x18000d789  mov     [rbx+38h], eax
0x18000d78c  mov     rax, [rcx+rdx*8]
0x18000d790  mov     [rbx+40h], rax
0x18000d794  mov     ecx, ebp
0x18000d796  test    ecx, ecx
0x18000d798  jz      short loc_18000D7E8
0x18000d79a  mov     r13, [rbx+40h]
0x18000d79e  mov     eax, r14d
0x18000d7a1  add     r12, rax
0x18000d7a4  jmp     loc_18000D6E1
0x18000d7a9  mov     [rdi+18h], r8d
0x18000d7ad  mov     rdx, rdi; struct _RECORDPAGE *
0x18000d7b0  add     [rbx+40h], rcx
0x18000d7b4  mov     r8d, ebp; int
0x18000d7b7  sub     [rbx+38h], ecx
0x18000d7ba  mov     rcx, [rsi+rbx+68h]; this
0x18000d7bf  call    ?FreePage@CBuffer@@QEAAXPEAU_RECORDPAGE@@HK@Z; CBuffer::FreePage(_RECORDPAGE *,int,ulong)
0x18000d7c4  mov     rdi, [rsi+rbx+68h]
0x18000d7c9  xor     r8d, r8d
0x18000d7cc  cmp     [rdi+40h], r8d
0x18000d7d0  jnz     short loc_18000D80D
0x18000d7d2  mov     rdi, [rdi+38h]
0x18000d7d6  test    rdi, rdi
0x18000d7d9  jz      short loc_18000D80D
0x18000d7db  lea     r12, [rdi+20h]
0x18000d7df  mov     [rdi+1Ch], r8d
0x18000d7e3  jmp     loc_18000D6E1
0x18000d7e8  test    rdi, rdi
0x18000d7eb  jz      short loc_18000D80D
0x18000d7ed  cmp     [rsi+rbx+70h], r8d
0x18000d7f2  jnz     short loc_18000D7FD
0x18000d7f4  cmp     [rdi+18h], r8d
0x18000d7f8  jz      short loc_18000D7FD
0x18000d7fa  mov     ebp, r8d
0x18000d7fd  mov     rcx, [rsi+rbx+68h]; this
0x18000d802  mov     r8d, ebp; int
0x18000d805  mov     rdx, rdi; struct _RECORDPAGE *
0x18000d808  call    ?FreePage@CBuffer@@QEAAXPEAU_RECORDPAGE@@HK@Z; CBuffer::FreePage(_RECORDPAGE *,int,ulong)
0x18000d80d  add     rsp, 28h
0x18000d811  pop     r15
0x18000d813  pop     r14
0x18000d815  pop     r13
0x18000d817  pop     r12
0x18000d819  pop     rdi
0x18000d81a  pop     rsi
0x18000d81b  pop     rbp
0x18000d81c  pop     rbx
0x18000d81d  retn
0x18000d81e  lea     rdx, _TI1J; pThrowInfo
0x18000d825  mov     [rsp+68h+pExceptionObject], 8000FFFFh
0x18000d82d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d832  call    _CxxThrowException_0
0x18000d838  lea     rdx, _TI1J; pThrowInfo
0x18000d83f  mov     [rsp+68h+pExceptionObject], 8000FFFFh
0x18000d847  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d84c  call    _CxxThrowException_0
0x18000d852  lea     rdx, _TI1J; pThrowInfo
0x18000d859  mov     [rsp+68h+pExceptionObject], 8000FFFFh
0x18000d861  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d866  call    _CxxThrowException_0
```
