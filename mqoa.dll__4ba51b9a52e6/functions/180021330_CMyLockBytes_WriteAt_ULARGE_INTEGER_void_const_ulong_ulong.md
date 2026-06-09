# CMyLockBytes::WriteAt(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x180021330`
- end: `0x1800214e4`
- name: `?WriteAt@CMyLockBytes@@UEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `436`
- prototype: `__int64 __fastcall(CMyLockBytes *__hidden this, union _ULARGE_INTEGER, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005430`
- `0x180020e04`
- `0x180020ed0`
- `0x180021330`
- `0x1800214ec`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180021385`
- `KERNEL32!LeaveCriticalSection` at `0x1800213b7`
- `KERNEL32!LeaveCriticalSection` at `0x18002145b`
- `KERNEL32!LeaveCriticalSection` at `0x1800214cb`
- `KERNEL32!LeaveCriticalSection` at `0x180021385`
- `KERNEL32!LeaveCriticalSection` at `0x1800213b7`
- `KERNEL32!LeaveCriticalSection` at `0x18002145b`
- `KERNEL32!LeaveCriticalSection` at `0x1800214cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMyLockBytes::WriteAt(
        CMyLockBytes *this,
        union _ULARGE_INTEGER a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // r15
  struct _RTL_CRITICAL_SECTION *v9; // r14
  union _ULARGE_INTEGER v10; // r12
  struct CMyMemNode *v11; // r15
  unsigned int v13; // edx
  unsigned __int64 v14; // rbx
  unsigned __int8 *v15; // r8
  struct CMyMemNode *v16; // rcx
  int v17; // r15d
  struct CMyMemNode *v18; // [rsp+30h] [rbp-10h]
  char *v19; // [rsp+80h] [rbp+40h] BYREF
  struct CMyMemNode *v20; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int8 *v21; // [rsp+90h] [rbp+50h]

  v21 = a3;
  v5 = a4;
  v6 = a3;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v19 = (char *)this + 8;
  CCriticalSection::Lock((CMyLockBytes *)((char *)this + 8));
  v10 = *(union _ULARGE_INTEGER *)((char *)this + 56);
  if ( a2.QuadPart < v10.QuadPart )
  {
    if ( a2.QuadPart + v5 > v10.QuadPart )
    {
      v17 = CMyLockBytes::GrowBlocks(this, a2.QuadPart + v5 - v10.QuadPart);
      if ( v17 < 0 )
      {
        LeaveCriticalSection(v9);
        return (unsigned int)v17;
      }
      v6 = v21;
    }
    if ( !(_DWORD)v5 )
      goto LABEL_26;
    v20 = 0;
    LODWORD(v19) = 0;
    CMyLockBytes::AdvanceInBlocks(
      this,
      *((struct CMyMemNode **)this + 8),
      0,
      a2.QuadPart,
      &v20,
      (unsigned int *)&v19,
      v18,
      0);
    v15 = v6;
    v13 = (unsigned int)v19;
    v16 = v20;
    goto LABEL_25;
  }
  if ( a2.QuadPart != v10.QuadPart || (_DWORD)v5 )
  {
    v11 = (struct CMyMemNode *)*((_QWORD *)this + 9);
    LODWORD(v20) = *((_DWORD *)this + 20);
    LODWORD(v19) = CMyLockBytes::GrowBlocks(this, a2.QuadPart + v5 - v10.QuadPart);
    if ( (int)v19 < 0 )
    {
      LeaveCriticalSection(v9);
      return (unsigned int)v19;
    }
    if ( !(_DWORD)v5 )
      goto LABEL_26;
    if ( v11 )
    {
      if ( (_DWORD)v20 )
      {
        v13 = *((_DWORD *)v11 + 2) - (_DWORD)v20;
        goto LABEL_16;
      }
      v11 = *(struct CMyMemNode **)v11;
    }
    else
    {
      v11 = (struct CMyMemNode *)*((_QWORD *)this + 8);
    }
    v13 = 0;
LABEL_16:
    v14 = a2.QuadPart - v10.QuadPart;
    v20 = 0;
    LODWORD(v19) = 0;
    if ( v14 )
    {
      CMyLockBytes::AdvanceInBlocks(this, v11, v13, v14, &v20, (unsigned int *)&v19, v18, 0);
      v11 = v20;
      v13 = (unsigned int)v19;
    }
    v15 = v21;
    v16 = v11;
LABEL_25:
    WriteInBlocks(v16, v13, v15, v5);
LABEL_26:
    if ( a5 )
      *a5 = v5;
    goto LABEL_28;
  }
  if ( a5 )
    *a5 = 0;
LABEL_28:
  LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x180021330  mov     [rsp-38h+arg_10], r8
0x180021335  push    rbp
0x180021336  push    rbx
0x180021337  push    rsi
0x180021338  push    r12
0x18002133a  push    r13
0x18002133c  push    r14
0x18002133e  push    r15
0x180021340  mov     rbp, rsp
0x180021343  sub     rsp, 40h
0x180021347  mov     esi, r9d
0x18002134a  mov     r15, r8
0x18002134d  mov     rbx, rdx
0x180021350  mov     r13, rcx
0x180021353  lea     r14, [rcx+8]
0x180021357  mov     [rbp+arg_0], r14
0x18002135b  mov     rcx, r14; this
0x18002135e  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180021363  nop
0x180021364  mov     r12, [r13+38h]
0x180021368  cmp     rbx, r12
0x18002136b  jb      loc_18002143D
0x180021371  jnz     short loc_180021391
0x180021373  test    esi, esi
0x180021375  jnz     short loc_180021391
0x180021377  mov     rax, [rbp+arg_20]
0x18002137b  test    rax, rax
0x18002137e  jz      short loc_180021382
0x180021380  mov     [rax], esi
0x180021382  mov     rcx, r14; lpCriticalSection
0x180021385  call    cs:__imp_LeaveCriticalSection
0x18002138b  nop
0x18002138c  jmp     loc_1800214D2
0x180021391  mov     r15, [r13+48h]
0x180021395  mov     eax, [r13+50h]
0x180021399  mov     dword ptr [rbp+arg_8], eax
0x18002139c  mov     rdx, rsi
0x18002139f  sub     rdx, r12
0x1800213a2  add     rdx, rbx; unsigned __int64
0x1800213a5  mov     rcx, r13; this
0x1800213a8  call    ?GrowBlocks@CMyLockBytes@@AEAAJ_K@Z; CMyLockBytes::GrowBlocks(unsigned __int64)
0x1800213ad  mov     dword ptr [rbp+arg_0], eax
0x1800213b0  test    eax, eax
0x1800213b2  jns     short loc_1800213C6
0x1800213b4  mov     rcx, r14; lpCriticalSection
0x1800213b7  call    cs:__imp_LeaveCriticalSection
0x1800213bd  nop
0x1800213be  mov     eax, dword ptr [rbp+arg_0]
0x1800213c1  jmp     loc_1800214D4
0x1800213c6  test    esi, esi
0x1800213c8  jz      loc_1800214BD
0x1800213ce  test    r15, r15
0x1800213d1  jnz     short loc_1800213D9
0x1800213d3  mov     r15, [r13+40h]
0x1800213d7  jmp     short loc_1800213E3
0x1800213d9  mov     eax, dword ptr [rbp+arg_8]
0x1800213dc  test    eax, eax
0x1800213de  jnz     short loc_1800213E7
0x1800213e0  mov     r15, [r15]
0x1800213e3  xor     edx, edx
0x1800213e5  jmp     short loc_1800213ED
0x1800213e7  mov     edx, [r15+8]
0x1800213eb  sub     edx, eax
0x1800213ed  sub     rbx, r12
0x1800213f0  mov     [rbp+arg_8], 0
0x1800213f8  mov     dword ptr [rbp+arg_0], 0
0x1800213ff  jz      short loc_180021434
0x180021401  mov     [rsp+40h+var_8], 0; struct CMyMemNode **
0x18002140a  lea     rax, [rbp+arg_0]
0x18002140e  mov     [rsp+40h+var_18], rax; unsigned int *
0x180021413  lea     rax, [rbp+arg_8]
0x180021417  mov     [rsp+40h+var_20], rax; struct CMyMemNode **
0x18002141c  mov     r9, rbx; unsigned __int64
0x18002141f  mov     r8d, edx; unsigned int
0x180021422  mov     rdx, r15; struct CMyMemNode *
0x180021425  mov     rcx, r13; this
0x180021428  call    ?AdvanceInBlocks@CMyLockBytes@@AEAAXPEAUCMyMemNode@@K_KPEAPEAU2@PEAK02@Z; CMyLockBytes::AdvanceInBlocks(CMyMemNode *,ulong,unsigned __int64,CMyMemNode * *,ulong *,CMyMemNode *,CMyMemNode * *)
0x18002142d  mov     r15, [rbp+arg_8]
0x180021431  mov     edx, dword ptr [rbp+arg_0]
0x180021434  mov     r8, [rbp+arg_10]
0x180021438  mov     rcx, r15
0x18002143b  jmp     short loc_1800214B5
0x18002143d  lea     rdx, [rbx+rsi]
0x180021441  cmp     rdx, r12
0x180021444  jbe     short loc_18002146B
0x180021446  sub     rdx, r12; unsigned __int64
0x180021449  mov     rcx, r13; this
0x18002144c  call    ?GrowBlocks@CMyLockBytes@@AEAAJ_K@Z; CMyLockBytes::GrowBlocks(unsigned __int64)
0x180021451  mov     r15d, eax
0x180021454  test    eax, eax
0x180021456  jns     short loc_180021467
0x180021458  mov     rcx, r14; lpCriticalSection
0x18002145b  call    cs:__imp_LeaveCriticalSection
0x180021461  nop
0x180021462  mov     eax, r15d
0x180021465  jmp     short loc_1800214D4
0x180021467  mov     r15, [rbp+arg_10]
0x18002146b  test    esi, esi
0x18002146d  jz      short loc_1800214BD
0x18002146f  mov     [rbp+arg_8], 0
0x180021477  mov     dword ptr [rbp+arg_0], 0
0x18002147e  mov     [rsp+40h+var_8], 0; struct CMyMemNode **
0x180021487  lea     rax, [rbp+arg_0]
0x18002148b  mov     [rsp+40h+var_18], rax; unsigned int *
0x180021490  lea     rax, [rbp+arg_8]
0x180021494  mov     [rsp+40h+var_20], rax; struct CMyMemNode **
0x180021499  mov     r9, rbx; unsigned __int64
0x18002149c  xor     r8d, r8d; unsigned int
0x18002149f  mov     rdx, [r13+40h]; struct CMyMemNode *
0x1800214a3  mov     rcx, r13; this
0x1800214a6  call    ?AdvanceInBlocks@CMyLockBytes@@AEAAXPEAUCMyMemNode@@K_KPEAPEAU2@PEAK02@Z; CMyLockBytes::AdvanceInBlocks(CMyMemNode *,ulong,unsigned __int64,CMyMemNode * *,ulong *,CMyMemNode *,CMyMemNode * *)
0x1800214ab  mov     r8, r15; unsigned __int8 *
0x1800214ae  mov     edx, dword ptr [rbp+arg_0]; unsigned int
0x1800214b1  mov     rcx, [rbp+arg_8]; struct CMyMemNode *
0x1800214b5  mov     r9d, esi; unsigned int
0x1800214b8  call    ?WriteInBlocks@@YAXPEAUCMyMemNode@@KPEAEK@Z; WriteInBlocks(CMyMemNode *,ulong,uchar *,ulong)
0x1800214bd  mov     rax, [rbp+arg_20]
0x1800214c1  test    rax, rax
0x1800214c4  jz      short loc_1800214C8
0x1800214c6  mov     [rax], esi
0x1800214c8  mov     rcx, r14; lpCriticalSection
0x1800214cb  call    cs:__imp_LeaveCriticalSection
0x1800214d1  nop
0x1800214d2  xor     eax, eax
0x1800214d4  add     rsp, 40h
0x1800214d8  pop     r15
0x1800214da  pop     r14
0x1800214dc  pop     r13
0x1800214de  pop     r12
0x1800214e0  pop     rsi
0x1800214e1  pop     rbx
0x1800214e2  pop     rbp
0x1800214e3  retn
```
