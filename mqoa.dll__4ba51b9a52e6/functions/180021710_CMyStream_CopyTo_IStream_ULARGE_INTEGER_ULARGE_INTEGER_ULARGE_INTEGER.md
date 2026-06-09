# CMyStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x180021710`
- end: `0x1800218cf`
- name: `?CopyTo@CMyStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `447`
- prototype: `__int64 __fastcall(CMyStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x180005430`
- `0x180021710`
- `0x18002737e`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002178b`
- `KERNEL32!LeaveCriticalSection` at `0x1800217c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800217e7`
- `KERNEL32!LeaveCriticalSection` at `0x180021835`
- `KERNEL32!LeaveCriticalSection` at `0x180021876`
- `KERNEL32!LeaveCriticalSection` at `0x1800218a6`
- `KERNEL32!LeaveCriticalSection` at `0x18002178b`
- `KERNEL32!LeaveCriticalSection` at `0x1800217c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800217e7`
- `KERNEL32!LeaveCriticalSection` at `0x180021835`
- `KERNEL32!LeaveCriticalSection` at `0x180021876`
- `KERNEL32!LeaveCriticalSection` at `0x1800218a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMyStream::CopyTo(
        CMyStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // r14d
  DWORD LowPart; // r14d
  void *v13; // rdi
  ULONGLONG v14; // rax
  ULONGLONG v15; // rcx
  unsigned int v16; // [rsp+30h] [rbp-61h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-5Dh] BYREF
  char *v18; // [rsp+38h] [rbp-59h]
  _BYTE v19[16]; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-41h]

  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v18 = (char *)this + 8;
  CCriticalSection::Lock((CMyStream *)((char *)this + 8));
  memset_0(v19, 0, 0x50u);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 7) + 72LL))(
          *((_QWORD *)this + 7),
          v19,
          1);
  if ( v10 < 0 )
  {
    LeaveCriticalSection(v9);
    return (unsigned int)v10;
  }
  if ( *((_QWORD *)this + 8) >= v20 )
  {
    v14 = 0;
    v15 = 0;
  }
  else
  {
    if ( v20 - *((_QWORD *)this + 8) <= a3.QuadPart )
      a3.QuadPart = v20 - *((_QWORD *)this + 8);
    if ( a3.HighPart )
    {
      LeaveCriticalSection(v9);
      return 2147500037LL;
    }
    LowPart = a3.LowPart;
    v13 = operator new(a3.LowPart);
    if ( !v13 )
    {
      LeaveCriticalSection(v9);
      return 2147942414LL;
    }
    v16 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _QWORD, unsigned int *))(**((_QWORD **)this + 7) + 24LL))(
            *((_QWORD *)this + 7),
            *((_QWORD *)this + 8),
            v13,
            LowPart,
            &v16);
    if ( v10 < 0 )
    {
      operator delete(v13);
      LeaveCriticalSection(v9);
      return (unsigned int)v10;
    }
    v17 = 0;
    v10 = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a2->lpVtbl->Write)(
            a2,
            v13,
            v16,
            &v17);
    operator delete(v13);
    if ( v10 < 0 )
    {
      LeaveCriticalSection(v9);
      return (unsigned int)v10;
    }
    v14 = v16;
    v15 = v17;
  }
  *((_QWORD *)this + 8) += v14;
  if ( a4 )
    a4->QuadPart = v14;
  if ( a5 )
    a5->QuadPart = v15;
  LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x180021710  push    rbp
0x180021712  push    rbx
0x180021713  push    rsi
0x180021714  push    rdi
0x180021715  push    r12
0x180021717  push    r13
0x180021719  push    r14
0x18002171b  push    r15
0x18002171d  lea     rbp, [rsp-17h]
0x180021722  sub     rsp, 0A8h
0x180021729  mov     rax, cs:__security_cookie
0x180021730  xor     rax, rsp
0x180021733  mov     [rbp+4Fh+var_50], rax
0x180021737  mov     r12, r9
0x18002173a  mov     rdi, r8
0x18002173d  mov     r13, rdx
0x180021740  mov     rsi, rcx
0x180021743  mov     r15, [rbp+4Fh+arg_20]
0x180021747  lea     rbx, [rcx+8]
0x18002174b  mov     [rbp+4Fh+var_A8], rbx
0x18002174f  mov     rcx, rbx; this
0x180021752  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180021757  nop
0x180021758  xor     edx, edx; Val
0x18002175a  lea     r8d, [rdx+50h]; Size
0x18002175e  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180021762  call    memset_0
0x180021767  mov     rcx, [rsi+38h]
0x18002176b  mov     rax, [rcx]
0x18002176e  mov     r8d, 1
0x180021774  lea     rdx, [rbp+4Fh+var_A0]
0x180021778  mov     rax, [rax+48h]
0x18002177c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021781  mov     r14d, eax
0x180021784  test    eax, eax
0x180021786  jns     short loc_18002179A
0x180021788  mov     rcx, rbx; lpCriticalSection
0x18002178b  call    cs:__imp_LeaveCriticalSection
0x180021791  nop
0x180021792  mov     eax, r14d
0x180021795  jmp     loc_1800218AF
0x18002179a  mov     rax, [rbp+4Fh+var_90]
0x18002179e  cmp     [rsi+40h], rax
0x1800217a2  jnb     loc_18002188A
0x1800217a8  sub     rax, [rsi+40h]
0x1800217ac  cmp     rax, rdi
0x1800217af  cmovbe  rdi, rax
0x1800217b3  mov     rax, rdi
0x1800217b6  shr     rax, 20h
0x1800217ba  test    eax, eax
0x1800217bc  jz      short loc_1800217D2
0x1800217be  mov     rcx, rbx; lpCriticalSection
0x1800217c1  call    cs:__imp_LeaveCriticalSection
0x1800217c7  nop
0x1800217c8  mov     eax, 80004005h
0x1800217cd  jmp     loc_1800218AF
0x1800217d2  mov     r14d, edi
0x1800217d5  mov     ecx, edi; Size
0x1800217d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800217dc  mov     rdi, rax
0x1800217df  test    rax, rax
0x1800217e2  jnz     short loc_1800217F8
0x1800217e4  mov     rcx, rbx; lpCriticalSection
0x1800217e7  call    cs:__imp_LeaveCriticalSection
0x1800217ed  nop
0x1800217ee  mov     eax, 8007000Eh
0x1800217f3  jmp     loc_1800218AF
0x1800217f8  mov     [rbp+4Fh+var_B0], 0
0x1800217ff  mov     rcx, [rsi+38h]
0x180021803  mov     rax, [rcx]
0x180021806  lea     rdx, [rbp+4Fh+var_B0]
0x18002180a  mov     [rsp+0E0h+var_C0], rdx
0x18002180f  mov     r9d, r14d
0x180021812  mov     r8, rdi
0x180021815  mov     rdx, [rsi+40h]
0x180021819  mov     rax, [rax+18h]
0x18002181d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021822  mov     r14d, eax
0x180021825  test    eax, eax
0x180021827  jns     short loc_180021841
0x180021829  mov     rcx, rdi; Block
0x18002182c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021831  nop
0x180021832  mov     rcx, rbx; lpCriticalSection
0x180021835  call    cs:__imp_LeaveCriticalSection
0x18002183b  nop
0x18002183c  jmp     loc_180021792
0x180021841  mov     [rbp+4Fh+var_AC], 0
0x180021848  mov     rax, [r13+0]
0x18002184c  lea     r9, [rbp+4Fh+var_AC]
0x180021850  mov     r8d, [rbp+4Fh+var_B0]
0x180021854  mov     rdx, rdi
0x180021857  mov     rcx, r13
0x18002185a  mov     rax, [rax+20h]
0x18002185e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021863  mov     r14d, eax
0x180021866  mov     rcx, rdi; Block
0x180021869  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002186e  test    r14d, r14d
0x180021871  jns     short loc_180021882
0x180021873  mov     rcx, rbx; lpCriticalSection
0x180021876  call    cs:__imp_LeaveCriticalSection
0x18002187c  nop
0x18002187d  jmp     loc_180021792
0x180021882  mov     eax, [rbp+4Fh+var_B0]
0x180021885  mov     ecx, [rbp+4Fh+var_AC]
0x180021888  jmp     short loc_18002188E
0x18002188a  xor     eax, eax
0x18002188c  xor     ecx, ecx
0x18002188e  add     [rsi+40h], rax
0x180021892  test    r12, r12
0x180021895  jz      short loc_18002189B
0x180021897  mov     [r12], rax
0x18002189b  test    r15, r15
0x18002189e  jz      short loc_1800218A3
0x1800218a0  mov     [r15], rcx
0x1800218a3  mov     rcx, rbx; lpCriticalSection
0x1800218a6  call    cs:__imp_LeaveCriticalSection
0x1800218ac  nop
0x1800218ad  xor     eax, eax
0x1800218af  mov     rcx, [rbp+4Fh+var_50]
0x1800218b3  xor     rcx, rsp; StackCookie
0x1800218b6  call    __security_check_cookie
0x1800218bb  add     rsp, 0A8h
0x1800218c2  pop     r15
0x1800218c4  pop     r14
0x1800218c6  pop     r13
0x1800218c8  pop     r12
0x1800218ca  pop     rdi
0x1800218cb  pop     rsi
0x1800218cc  pop     rbx
0x1800218cd  pop     rbp
0x1800218ce  retn
```
