# CHHSysSort::CompareSz(void const *,long,void const *,long,long *,int)

- ea: `0x1800360f8`
- end: `0x1800363a3`
- name: `?CompareSz@CHHSysSort@@AEAAJPEBXJ0JPEAJH@Z`
- size: `683`
- prototype: `__int64 __fastcall(CHHSysSort *__hidden this, PCNZWCH lpString1, int, PCNZWCH lpString2, int, int *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035d10`
- `0x180036600`

## callees

- `0x18000c02c`
- `0x1800360f8`
- `0x1800367c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180036180`
- `KERNEL32!CompareStringW` at `0x180036180`
- `KERNEL32!CompareStringA` at `0x18003633f`
- `KERNEL32!CompareStringA` at `0x18003633f`
- `KERNEL32!GlobalLock` at `0x18003628a`
- `KERNEL32!GlobalLock` at `0x180036296`
- `KERNEL32!GlobalLock` at `0x18003628a`
- `KERNEL32!GlobalLock` at `0x180036296`
- `KERNEL32!GlobalUnlock` at `0x180036365`
- `KERNEL32!GlobalUnlock` at `0x180036373`
- `KERNEL32!GlobalUnlock` at `0x180036365`
- `KERNEL32!GlobalUnlock` at `0x180036373`
- `KERNEL32!LeaveCriticalSection` at `0x180036152`
- `KERNEL32!LeaveCriticalSection` at `0x180036383`
- `KERNEL32!LeaveCriticalSection` at `0x180036152`
- `KERNEL32!LeaveCriticalSection` at `0x180036383`
- `KERNEL32!EnterCriticalSection` at `0x180036132`
- `KERNEL32!EnterCriticalSection` at `0x1800361a8`
- `KERNEL32!EnterCriticalSection` at `0x180036132`
- `KERNEL32!EnterCriticalSection` at `0x1800361a8`

## pseudocode

```c
__int64 __fastcall CHHSysSort::CompareSz(
        CHHSysSort *this,
        unsigned __int16 *lpString1,
        int a3,
        unsigned __int16 *lpString2,
        int cchCount2,
        int *a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v7; // r12
  CHAR *v9; // r15
  int v13; // edi
  LCID v14; // r14d
  int v15; // eax
  HGLOBAL *v16; // rsi
  HGLOBAL *v17; // r14
  CHAR *v18; // rbx
  int v19; // ebp
  int v20; // eax
  __int64 v21; // r13
  int v22; // eax
  unsigned int v24; // [rsp+40h] [rbp-68h]
  DWORD dwCmpFlags; // [rsp+44h] [rbp-64h]
  int v26; // [rsp+48h] [rbp-60h]
  LCID Locale; // [rsp+50h] [rbp-58h]
  int *v28; // [rsp+58h] [rbp-50h]
  int *v29; // [rsp+60h] [rbp-48h]
  unsigned int v30; // [rsp+B0h] [rbp+8h] BYREF
  unsigned __int16 *v31; // [rsp+B8h] [rbp+10h]
  unsigned __int16 *v32; // [rsp+C8h] [rbp+20h]

  v32 = lpString2;
  v31 = lpString1;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v9 = 0;
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v14 = *((_DWORD *)this + 24);
  v24 = *((_DWORD *)this + 23);
  dwCmpFlags = *((_DWORD *)this + 26);
  Locale = v14;
  LeaveCriticalSection(v7);
  if ( *((_DWORD *)this + 22) )
  {
    v26 = 0;
    v15 = CompareStringW(v14, dwCmpFlags, lpString1, a3, lpString2, cchCount2);
    v16 = (HGLOBAL *)((char *)this + 112);
    v17 = (HGLOBAL *)((char *)this + 120);
    v18 = 0;
  }
  else
  {
    a7 = 0;
    v30 = 0;
    EnterCriticalSection(v7);
    if ( a3 >= 0 )
      a7 = 2 * a3 + 2;
    else
      v13 = (*(__int64 (__fastcall **)(CHHSysSort *, unsigned __int16 *, int *))(*(_QWORD *)this + 24LL))(
              this,
              lpString1,
              &a7);
    v19 = cchCount2;
    if ( cchCount2 >= 0 )
      v30 = 2 * cchCount2 + 2;
    else
      v13 = (*(__int64 (__fastcall **)(CHHSysSort *, unsigned __int16 *, unsigned int *))(*(_QWORD *)this + 24LL))(
              this,
              lpString2,
              &v30);
    if ( v13 < 0
      || (v16 = (HGLOBAL *)((char *)this + 112),
          v28 = (int *)((char *)this + 128),
          v13 = CHHSysSort::ReallocBuffer(this, (void **)this + 14, (unsigned int *)this + 32, a7),
          v13 < 0)
      || (v17 = (HGLOBAL *)((char *)this + 120),
          v29 = (int *)((char *)this + 132),
          v13 = CHHSysSort::ReallocBuffer(this, (void **)this + 15, (unsigned int *)this + 33, v30),
          v13 < 0) )
    {
LABEL_23:
      LeaveCriticalSection(v7);
      return (unsigned int)v13;
    }
    v26 = 1;
    v18 = (CHAR *)GlobalLock(*v16);
    v9 = (CHAR *)GlobalLock(*v17);
    v20 = HHWideCharToMultiByte(v24, 0, v31, a3, v18, *v28, 0, 0);
    v21 = v20;
    if ( !v20 || (v22 = HHWideCharToMultiByte(v24, 0, v32, v19, v9, *v29, 0, 0)) == 0 )
    {
      v13 = -2147418113;
      goto LABEL_18;
    }
    v18[v21] = 0;
    v9[v22] = 0;
    v15 = CompareStringA(Locale, dwCmpFlags, v18, v21, v9, v22);
  }
  if ( v15 )
    *a6 = v15 - 2;
LABEL_18:
  if ( v18 )
    GlobalUnlock(*v16);
  if ( v9 )
    GlobalUnlock(*v17);
  if ( v26 )
    goto LABEL_23;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800360f8  mov     [rsp+arg_10], rbx
0x1800360fd  mov     [rsp+arg_18], r9
0x180036102  mov     [rsp+arg_8], rdx
0x180036107  push    rbp
0x180036108  push    rsi
0x180036109  push    rdi
0x18003610a  push    r12
0x18003610c  push    r13
0x18003610e  push    r14
0x180036110  push    r15
0x180036112  sub     rsp, 70h
0x180036116  lea     r12, [rcx+88h]
0x18003611d  mov     rbx, rcx
0x180036120  xor     r15d, r15d
0x180036123  mov     rcx, r12; lpCriticalSection
0x180036126  mov     rsi, r9
0x180036129  mov     r13d, r8d
0x18003612c  mov     rbp, rdx
0x18003612f  mov     edi, r15d
0x180036132  call    cs:__imp_EnterCriticalSection
0x180036138  mov     eax, [rbx+5Ch]
0x18003613b  mov     rcx, r12; lpCriticalSection
0x18003613e  mov     r14d, [rbx+60h]
0x180036142  mov     [rsp+0A8h+var_68], eax
0x180036146  mov     eax, [rbx+68h]
0x180036149  mov     [rsp+0A8h+dwCmpFlags], eax
0x18003614d  mov     [rsp+0A8h+Locale], r14d
0x180036152  call    cs:__imp_LeaveCriticalSection
0x180036158  cmp     [rbx+58h], r15d
0x18003615c  jz      short loc_180036195
0x18003615e  mov     eax, [rsp+0A8h+arg_20]
0x180036165  mov     r9d, r13d; cchCount1
0x180036168  mov     edx, [rsp+0A8h+dwCmpFlags]; dwCmpFlags
0x18003616c  mov     r8, rbp; lpString1
0x18003616f  mov     [rsp+0A8h+cchCount2], eax; cchCount2
0x180036173  mov     ecx, r14d; Locale
0x180036176  mov     [rsp+0A8h+lpString2], rsi; lpString2
0x18003617b  mov     [rsp+0A8h+var_60], r15d
0x180036180  call    cs:__imp_CompareStringW
0x180036186  lea     rsi, [rbx+70h]
0x18003618a  lea     r14, [rbx+78h]
0x18003618e  mov     ebx, edi
0x180036190  jmp     loc_180036345
0x180036195  mov     rcx, r12; lpCriticalSection
0x180036198  mov     [rsp+0A8h+arg_30], r15d
0x1800361a0  mov     [rsp+0A8h+arg_0], r15d
0x1800361a8  call    cs:__imp_EnterCriticalSection
0x1800361ae  test    r13d, r13d
0x1800361b1  jns     short loc_1800361D1
0x1800361b3  mov     rax, [rbx]
0x1800361b6  lea     r8, [rsp+0A8h+arg_30]
0x1800361be  mov     rdx, rbp
0x1800361c1  mov     rcx, rbx
0x1800361c4  mov     rax, [rax+18h]
0x1800361c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361cd  mov     edi, eax
0x1800361cf  jmp     short loc_1800361E0
0x1800361d1  lea     eax, ds:2[r13*2]
0x1800361d9  mov     [rsp+0A8h+arg_30], eax
0x1800361e0  mov     ebp, [rsp+0A8h+arg_20]
0x1800361e7  test    ebp, ebp
0x1800361e9  jns     short loc_180036209
0x1800361eb  mov     rax, [rbx]
0x1800361ee  lea     r8, [rsp+0A8h+arg_0]
0x1800361f6  mov     rdx, rsi
0x1800361f9  mov     rcx, rbx
0x1800361fc  mov     rax, [rax+18h]
0x180036200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036205  mov     edi, eax
0x180036207  jmp     short loc_180036217
0x180036209  lea     eax, ds:2[rbp*2]
0x180036210  mov     [rsp+0A8h+arg_0], eax
0x180036217  test    edi, edi
0x180036219  js      loc_180036380
0x18003621f  mov     r9d, [rsp+0A8h+arg_30]; unsigned int
0x180036227  lea     rax, [rbx+80h]
0x18003622e  lea     rsi, [rbx+70h]
0x180036232  mov     [rsp+0A8h+var_50], rax
0x180036237  mov     r8, rax; unsigned int *
0x18003623a  mov     rdx, rsi; void **
0x18003623d  mov     rcx, rbx; this
0x180036240  call    ?ReallocBuffer@CHHSysSort@@AEAAJPEAPEAXPEAKK@Z; CHHSysSort::ReallocBuffer(void * *,ulong *,ulong)
0x180036245  mov     edi, eax
0x180036247  test    eax, eax
0x180036249  js      loc_180036380
0x18003624f  mov     r9d, [rsp+0A8h+arg_0]; unsigned int
0x180036257  lea     rax, [rbx+84h]
0x18003625e  lea     r14, [rbx+78h]
0x180036262  mov     [rsp+0A8h+var_48], rax
0x180036267  mov     r8, rax; unsigned int *
0x18003626a  mov     rdx, r14; void **
0x18003626d  mov     rcx, rbx; this
0x180036270  call    ?ReallocBuffer@CHHSysSort@@AEAAJPEAPEAXPEAKK@Z; CHHSysSort::ReallocBuffer(void * *,ulong *,ulong)
0x180036275  mov     edi, eax
0x180036277  test    eax, eax
0x180036279  js      loc_180036380
0x18003627f  mov     rcx, [rsi]; hMem
0x180036282  mov     [rsp+0A8h+var_60], 1
0x18003628a  call    cs:__imp_GlobalLock
0x180036290  mov     rcx, [r14]; hMem
0x180036293  mov     rbx, rax
0x180036296  call    cs:__imp_GlobalLock
0x18003629c  mov     rcx, [rsp+0A8h+var_50]
0x1800362a1  mov     r9d, r13d; int
0x1800362a4  mov     r8, [rsp+0A8h+arg_8]; unsigned __int16 *
0x1800362ac  xor     edx, edx; unsigned int
0x1800362ae  mov     [rsp+0A8h+var_70], 0; LPBOOL
0x1800362b7  mov     r15, rax
0x1800362ba  mov     [rsp+0A8h+var_78], 0; LPCCH
0x1800362c3  mov     ecx, [rcx]
0x1800362c5  mov     [rsp+0A8h+cchCount2], ecx; int
0x1800362c9  mov     ecx, [rsp+0A8h+var_68]; unsigned int
0x1800362cd  mov     [rsp+0A8h+lpString2], rbx; LPSTR
0x1800362d2  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x1800362d7  movsxd  r13, eax
0x1800362da  test    eax, eax
0x1800362dc  jz      short loc_180036358
0x1800362de  mov     rdx, [rsp+0A8h+var_48]
0x1800362e3  mov     r9d, ebp; int
0x1800362e6  mov     r8, [rsp+0A8h+arg_18]; unsigned __int16 *
0x1800362ee  mov     ecx, [rsp+0A8h+var_68]; unsigned int
0x1800362f2  mov     [rsp+0A8h+var_70], 0; LPBOOL
0x1800362fb  mov     edx, [rdx]
0x1800362fd  mov     [rsp+0A8h+var_78], 0; LPCCH
0x180036306  mov     [rsp+0A8h+cchCount2], edx; int
0x18003630a  xor     edx, edx; unsigned int
0x18003630c  mov     [rsp+0A8h+lpString2], r15; LPSTR
0x180036311  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180036316  test    eax, eax
0x180036318  jz      short loc_180036358
0x18003631a  mov     edx, [rsp+0A8h+dwCmpFlags]; dwCmpFlags
0x18003631e  mov     r9d, r13d; cchCount1
0x180036321  movsxd  rcx, eax
0x180036324  mov     r8, rbx; lpString1
0x180036327  mov     byte ptr [r13+rbx+0], 0
0x18003632d  mov     [rsp+0A8h+cchCount2], eax; cchCount2
0x180036331  mov     [rsp+0A8h+lpString2], r15; lpString2
0x180036336  mov     byte ptr [rcx+r15], 0
0x18003633b  mov     ecx, [rsp+0A8h+Locale]; Locale
0x18003633f  call    cs:__imp_CompareStringA
0x180036345  test    eax, eax
0x180036347  jz      short loc_18003635D
0x180036349  lea     ecx, [rax-2]
0x18003634c  mov     rax, [rsp+0A8h+arg_28]
0x180036354  mov     [rax], ecx
0x180036356  jmp     short loc_18003635D
0x180036358  mov     edi, 8000FFFFh
0x18003635d  test    rbx, rbx
0x180036360  jz      short loc_18003636B
0x180036362  mov     rcx, [rsi]; hMem
0x180036365  call    cs:__imp_GlobalUnlock
0x18003636b  test    r15, r15
0x18003636e  jz      short loc_180036379
0x180036370  mov     rcx, [r14]; hMem
0x180036373  call    cs:__imp_GlobalUnlock
0x180036379  cmp     [rsp+0A8h+var_60], 0
0x18003637e  jz      short loc_180036389
0x180036380  mov     rcx, r12; lpCriticalSection
0x180036383  call    cs:__imp_LeaveCriticalSection
0x180036389  mov     rbx, [rsp+0A8h+arg_10]
0x180036391  mov     eax, edi
0x180036393  add     rsp, 70h
0x180036397  pop     r15
0x180036399  pop     r14
0x18003639b  pop     r13
0x18003639d  pop     r12
0x18003639f  pop     rdi
0x1800363a0  pop     rsi
0x1800363a1  pop     rbp
0x1800363a2  retn
```
