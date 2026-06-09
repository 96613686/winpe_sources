# CMyLockBytes::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x180021020`
- end: `0x180021164`
- name: `?ReadAt@CMyLockBytes@@UEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `324`
- prototype: `__int64 __usercall@<rax>(CMyLockBytes *__hidden this@<rcx>, union _ULARGE_INTEGER@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005430`
- `0x180020e04`
- `0x180021020`
- `0x180027372`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180021100`
- `KERNEL32!LeaveCriticalSection` at `0x180021123`
- `KERNEL32!LeaveCriticalSection` at `0x180021142`
- `KERNEL32!LeaveCriticalSection` at `0x180021100`
- `KERNEL32!LeaveCriticalSection` at `0x180021123`
- `KERNEL32!LeaveCriticalSection` at `0x180021142`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMyLockBytes::ReadAt(
        CMyLockBytes *this,
        union _ULARGE_INTEGER a2,
        char *a3,
        unsigned int a4,
        unsigned int *a5)
{
  ULONGLONG v5; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  union _ULARGE_INTEGER v10; // rax
  ULONGLONG v11; // rax
  __int64 v12; // r12
  char *v13; // rcx
  struct CMyMemNode *v14; // rdi
  unsigned int v15; // r8d
  unsigned int v16; // edx
  __int64 v17; // rax
  int v18; // r15d
  char *v19; // rbp
  struct CMyMemNode *v21; // [rsp+30h] [rbp-38h]
  unsigned int v22; // [rsp+70h] [rbp+8h] BYREF
  struct CMyMemNode *v23; // [rsp+78h] [rbp+10h] BYREF

  v5 = a4;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  CCriticalSection::Lock((CMyLockBytes *)((char *)this + 8));
  v10 = *(union _ULARGE_INTEGER *)((char *)this + 56);
  if ( a2.QuadPart < v10.QuadPart && (_DWORD)v5 )
  {
    v11 = v10.QuadPart - a2.QuadPart;
    v12 = (unsigned int)v5;
    if ( v5 > v11 )
      LODWORD(v5) = v11;
    v23 = 0;
    v22 = 0;
    CMyLockBytes::AdvanceInBlocks(this, *((struct CMyMemNode **)this + 8), 0, a2.QuadPart, &v23, &v22, v21, 0);
    v13 = a3;
    v14 = v23;
    v15 = v22;
    while ( (_DWORD)v5 )
    {
      v16 = *((_DWORD *)v14 + 2) - v15;
      v17 = (unsigned int)v5;
      if ( (unsigned int)v5 > v16 )
        v17 = v16;
      v18 = v17;
      v19 = &v13[v17];
      if ( &v13[v17] > &a3[v12] )
      {
        LeaveCriticalSection(v9);
        return 3222142977LL;
      }
      memcpy_0(v13, (char *)v14 + v15 + 16, (unsigned int)v17);
      v13 = v19;
      LODWORD(v5) = v5 - v18;
      v14 = *(struct CMyMemNode **)v14;
      v15 = 0;
    }
    if ( a5 )
      *a5 = (_DWORD)v13 - (_DWORD)a3;
  }
  else if ( a5 )
  {
    *a5 = 0;
  }
  LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x180021020  mov     [rsp+arg_10], rbx
0x180021025  mov     [rsp+arg_18], rbp
0x18002102a  push    rsi
0x18002102b  push    rdi
0x18002102c  push    r12
0x18002102e  push    r14
0x180021030  push    r15
0x180021032  sub     rsp, 40h
0x180021036  mov     esi, r9d
0x180021039  mov     r14, r8
0x18002103c  mov     rdi, rdx
0x18002103f  mov     rbp, rcx
0x180021042  lea     rbx, [rcx+8]
0x180021046  mov     rcx, rbx; this
0x180021049  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18002104e  mov     rax, [rbp+38h]
0x180021052  cmp     rdi, rax
0x180021055  jnb     loc_18002112C
0x18002105b  test    esi, esi
0x18002105d  jz      loc_18002112C
0x180021063  sub     rax, rdi
0x180021066  mov     r12d, esi
0x180021069  cmp     rsi, rax
0x18002106c  cmova   esi, eax
0x18002106f  mov     [rsp+68h+arg_8], 0
0x180021078  mov     [rsp+68h+arg_0], 0
0x180021080  mov     [rsp+68h+var_30], 0; struct CMyMemNode **
0x180021089  lea     rax, [rsp+68h+arg_0]
0x18002108e  mov     [rsp+68h+var_40], rax; unsigned int *
0x180021093  lea     rax, [rsp+68h+arg_8]
0x180021098  mov     [rsp+68h+var_48], rax; struct CMyMemNode **
0x18002109d  mov     r9, rdi; unsigned __int64
0x1800210a0  xor     r8d, r8d; unsigned int
0x1800210a3  mov     rdx, [rbp+40h]; struct CMyMemNode *
0x1800210a7  mov     rcx, rbp; this
0x1800210aa  call    ?AdvanceInBlocks@CMyLockBytes@@AEAAXPEAUCMyMemNode@@K_KPEAPEAU2@PEAK02@Z; CMyLockBytes::AdvanceInBlocks(CMyMemNode *,ulong,unsigned __int64,CMyMemNode * *,ulong *,CMyMemNode *,CMyMemNode * *)
0x1800210af  mov     rcx, r14; void *
0x1800210b2  mov     rdi, [rsp+68h+arg_8]
0x1800210b7  mov     r8d, [rsp+68h+arg_0]
0x1800210bc  test    esi, esi
0x1800210be  jz      short loc_18002110E
0x1800210c0  mov     edx, [rdi+8]
0x1800210c3  sub     edx, r8d
0x1800210c6  mov     eax, esi
0x1800210c8  cmp     esi, edx
0x1800210ca  cmova   eax, edx
0x1800210cd  mov     r15d, eax
0x1800210d0  lea     rbp, [rax+rcx]
0x1800210d4  lea     rax, [r12+r14]
0x1800210d8  cmp     rbp, rax
0x1800210db  ja      short loc_1800210FD
0x1800210dd  mov     edx, r8d
0x1800210e0  add     rdx, 10h
0x1800210e4  add     rdx, rdi; Src
0x1800210e7  mov     r8d, r15d; Size
0x1800210ea  call    memcpy_0
0x1800210ef  mov     rcx, rbp
0x1800210f2  sub     esi, r15d
0x1800210f5  mov     rdi, [rdi]
0x1800210f8  xor     r8d, r8d
0x1800210fb  jmp     short loc_1800210BC
0x1800210fd  mov     rcx, rbx; lpCriticalSection
0x180021100  call    cs:__imp_LeaveCriticalSection
0x180021106  nop
0x180021107  mov     eax, 0C00E0001h
0x18002110c  jmp     short loc_18002114B
0x18002110e  mov     rax, [rsp+68h+arg_20]
0x180021116  test    rax, rax
0x180021119  jz      short loc_180021120
0x18002111b  sub     ecx, r14d
0x18002111e  mov     [rax], ecx
0x180021120  mov     rcx, rbx; lpCriticalSection
0x180021123  call    cs:__imp_LeaveCriticalSection
0x180021129  nop
0x18002112a  jmp     short loc_180021149
0x18002112c  mov     rax, [rsp+68h+arg_20]
0x180021134  test    rax, rax
0x180021137  jz      short loc_18002113F
0x180021139  mov     dword ptr [rax], 0
0x18002113f  mov     rcx, rbx; lpCriticalSection
0x180021142  call    cs:__imp_LeaveCriticalSection
0x180021148  nop
0x180021149  xor     eax, eax
0x18002114b  lea     r11, [rsp+68h+var_28]
0x180021150  mov     rbx, [r11+40h]
0x180021154  mov     rbp, [r11+48h]
0x180021158  mov     rsp, r11
0x18002115b  pop     r15
0x18002115d  pop     r14
0x18002115f  pop     r12
0x180021161  pop     rdi
0x180021162  pop     rsi
0x180021163  retn
```
