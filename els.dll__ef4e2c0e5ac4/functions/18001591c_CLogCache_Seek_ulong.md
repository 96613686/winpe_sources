# CLogCache::Seek(ulong)

- ea: `0x18001591c`
- end: `0x180015a0c`
- name: `?Seek@CLogCache@@QEAAJK@Z`
- size: `240`
- prototype: `__int64 __fastcall(CLogCache *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180014eb8`
- `0x180015870`
- `0x18001a2d0`
- `0x18001a330`
- `0x18001a3d0`
- `0x18001a50c`

## callees

- `0x18001591c`
- `0x180015abc`
- `0x180015afc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180015942`
- `KERNEL32!EnterCriticalSection` at `0x180015942`
- `KERNEL32!LeaveCriticalSection` at `0x1800159f1`
- `KERNEL32!LeaveCriticalSection` at `0x1800159f1`

## pseudocode

```c
__int64 __fastcall CLogCache::Seek(CLogCache *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct _EVENTLOGRECORD *v5; // rax
  int v6; // esi
  unsigned int v7; // ebp
  unsigned int v8; // r8d
  unsigned int v9; // eax
  struct _EVENTLOGRECORD *v10; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v5 = CLogCache::_SearchCache(this, a2);
  *((_QWORD *)this + 7) = v5;
  if ( v5 )
  {
    v6 = 0;
  }
  else
  {
    v7 = a2;
    v8 = *((_DWORD *)this + 18);
    if ( *((_DWORD *)this + 20) == 4 )
    {
      if ( a2 < v8 )
      {
        v9 = (*((_DWORD *)this + 19) - v8) >> 1;
        if ( v9 > a2 || (v7 = a2 - v9, a2 - v9 < *((_DWORD *)this + 17)) )
          v7 = *((_DWORD *)this + 17);
      }
    }
    else if ( a2 > v8 )
    {
      v7 = ((v8 - *((_DWORD *)this + 19)) >> 1) + a2;
      if ( v7 > *((_DWORD *)this + 17) + *((_DWORD *)this + 16) - 1 )
        v7 = *((_DWORD *)this + 17) + *((_DWORD *)this + 16) - 1;
    }
    v6 = CLogCache::_SeekRead(this, v7);
    if ( v6 >= 0 )
    {
      v10 = CLogCache::_SearchCache(this, a2);
      *((_QWORD *)this + 7) = v10;
      if ( !v10 && v7 != a2 )
      {
        v6 = CLogCache::_SeekRead(this, a2);
        if ( v6 >= 0 )
          *((_QWORD *)this + 7) = CLogCache::_SearchCache(this, a2);
      }
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001591c  mov     [rsp+arg_8], rbx
0x180015921  mov     [rsp+arg_10], rbp
0x180015926  push    rsi
0x180015927  push    rdi
0x180015928  push    r14
0x18001592a  sub     rsp, 20h
0x18001592e  mov     edi, edx
0x180015930  mov     rbx, rcx
0x180015933  lea     r14, [rcx+260h]
0x18001593a  mov     [rsp+38h+arg_0], r14
0x18001593f  mov     rcx, r14; lpCriticalSection
0x180015942  call    cs:__imp_EnterCriticalSection
0x180015948  nop
0x180015949  mov     edx, edi; unsigned int
0x18001594b  mov     rcx, rbx; this
0x18001594e  call    ?_SearchCache@CLogCache@@AEAAPEAU_EVENTLOGRECORD@@K@Z; CLogCache::_SearchCache(ulong)
0x180015953  mov     [rbx+38h], rax
0x180015957  test    rax, rax
0x18001595a  jz      short loc_180015963
0x18001595c  xor     esi, esi
0x18001595e  jmp     loc_1800159EE
0x180015963  mov     ebp, edi
0x180015965  mov     r8d, [rbx+48h]
0x180015969  cmp     dword ptr [rbx+50h], 4
0x18001596d  jnz     short loc_18001598C
0x18001596f  cmp     edi, r8d
0x180015972  jnb     short loc_1800159A9
0x180015974  mov     eax, [rbx+4Ch]
0x180015977  sub     eax, r8d
0x18001597a  shr     eax, 1
0x18001597c  cmp     eax, edi
0x18001597e  ja      short loc_180015987
0x180015980  sub     ebp, eax
0x180015982  cmp     ebp, [rbx+44h]
0x180015985  jnb     short loc_1800159A9
0x180015987  mov     ebp, [rbx+44h]
0x18001598a  jmp     short loc_1800159A9
0x18001598c  cmp     edi, r8d
0x18001598f  jbe     short loc_1800159A9
0x180015991  mov     edx, [rbx+40h]
0x180015994  dec     edx
0x180015996  add     edx, [rbx+44h]
0x180015999  sub     r8d, [rbx+4Ch]
0x18001599d  shr     r8d, 1
0x1800159a0  lea     ebp, [r8+rdi]
0x1800159a4  cmp     ebp, edx
0x1800159a6  cmova   ebp, edx
0x1800159a9  mov     edx, ebp; unsigned int
0x1800159ab  mov     rcx, rbx; this
0x1800159ae  call    ?_SeekRead@CLogCache@@AEAAJK@Z; CLogCache::_SeekRead(ulong)
0x1800159b3  mov     esi, eax
0x1800159b5  test    eax, eax
0x1800159b7  js      short loc_1800159EE
0x1800159b9  mov     edx, edi; unsigned int
0x1800159bb  mov     rcx, rbx; this
0x1800159be  call    ?_SearchCache@CLogCache@@AEAAPEAU_EVENTLOGRECORD@@K@Z; CLogCache::_SearchCache(ulong)
0x1800159c3  mov     [rbx+38h], rax
0x1800159c7  test    rax, rax
0x1800159ca  jnz     short loc_1800159EE
0x1800159cc  cmp     ebp, edi
0x1800159ce  jz      short loc_1800159EE
0x1800159d0  mov     edx, edi; unsigned int
0x1800159d2  mov     rcx, rbx; this
0x1800159d5  call    ?_SeekRead@CLogCache@@AEAAJK@Z; CLogCache::_SeekRead(ulong)
0x1800159da  mov     esi, eax
0x1800159dc  test    eax, eax
0x1800159de  js      short loc_1800159EE
0x1800159e0  mov     edx, edi; unsigned int
0x1800159e2  mov     rcx, rbx; this
0x1800159e5  call    ?_SearchCache@CLogCache@@AEAAPEAU_EVENTLOGRECORD@@K@Z; CLogCache::_SearchCache(ulong)
0x1800159ea  mov     [rbx+38h], rax
0x1800159ee  mov     rcx, r14; lpCriticalSection
0x1800159f1  call    cs:__imp_LeaveCriticalSection
0x1800159f7  mov     eax, esi
0x1800159f9  mov     rbx, [rsp+38h+arg_8]
0x1800159fe  mov     rbp, [rsp+38h+arg_10]
0x180015a03  add     rsp, 20h
0x180015a07  pop     r14
0x180015a09  pop     rdi
0x180015a0a  pop     rsi
0x180015a0b  retn
```
