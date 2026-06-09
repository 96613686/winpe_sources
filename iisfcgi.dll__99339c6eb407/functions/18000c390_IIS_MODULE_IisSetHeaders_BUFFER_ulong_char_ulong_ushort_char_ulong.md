# IIS_MODULE::IisSetHeaders(BUFFER *,ulong,char *,ulong,ushort,char *,ulong)

- ea: `0x18000c390`
- end: `0x18000c62f`
- name: `?IisSetHeaders@IIS_MODULE@@UEAAJPEAVBUFFER@@KPEADKG1K@Z`
- size: `671`
- prototype: `__int64 __fastcall(IIS_MODULE *this, struct BUFFER *, __int64, char *, unsigned int, unsigned __int16, char *, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180006034`
- `0x18000c390`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000c502`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000c502`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c4db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c4db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c599`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c591`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c599`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c5f8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c5f8`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::IisSetHeaders(
        IIS_MODULE *this,
        struct BUFFER *a2,
        __int64 a3,
        char *a4,
        unsigned int a5,
        unsigned __int16 a6,
        char *a7,
        unsigned __int16 a8)
{
  __int64 v11; // rax
  char *v12; // rcx
  __int64 v13; // rdi
  int v14; // ebx
  char *v15; // rdx
  __int64 v16; // r9
  char *v17; // r8
  __int64 v18; // rbx
  char v19; // al
  char *v20; // r8
  __int64 v21; // rax
  int v22; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  char *v27; // [rsp+48h] [rbp-B8h] BYREF
  char *v28; // [rsp+50h] [rbp-B0h] BYREF
  char *Str; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[32]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+90h] [rbp-70h]
  unsigned __int16 v33[64]; // [rsp+A0h] [rbp-60h] BYREF

  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 32LL))(*((_QWORD *)this + 21));
  v12 = (char *)*((_QWORD *)a2 + 4);
  v13 = v11;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 0;
  Str = 0;
  v14 = APPLICATION::NextHeader(v12, &v27, &v26, &v28, &v25, &Str, 0);
  if ( v14 >= 0 )
  {
    do
    {
      if ( !v27 )
        break;
      v15 = v27;
      v16 = v25;
      v17 = v28;
      v27[v26] = 0;
      v17[v16] = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 40LL))(v13, v15);
      if ( v14 < 0 )
        goto LABEL_25;
      v14 = APPLICATION::NextHeader(Str, &v27, &v26, &v28, &v25, &Str, 0);
    }
    while ( v14 >= 0 );
    if ( a4 )
    {
      memset_0(v33, 0, sizeof(v33));
      STRU::STRU((STRU *)v30, v33, 0x40u);
      v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 272LL))(*((_QWORD *)this + 21));
      if ( (int)STRU::CopyA((STRU *)v30, a4) < 0 )
      {
        *v31 = 0;
        v32 = 0;
      }
      LOBYTE(v24) = 4;
      (*(void (__fastcall **)(__int64, const wchar_t *, _WORD *, _QWORD, int))(*(_QWORD *)v18 + 32LL))(
        v18,
        L"FASTCGI_SETSTATUS",
        v31,
        0,
        v24);
      v19 = *a4;
      v20 = a4;
      while ( v19 && v19 != 32 )
        v19 = *++v20;
      while ( *v20 == 32 )
        ++v20;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD, _DWORD, _QWORD, int))(*(_QWORD *)v13 + 24LL))(
              v13,
              a6,
              v20,
              0,
              0,
              0,
              1);
      if ( v14 < 0 )
      {
        STRU::~STRU((STRU *)v30);
        goto LABEL_25;
      }
      STRU::~STRU((STRU *)v30);
    }
    if ( !a7
      || ((v21 = *(_QWORD *)v13, a4)
        ? (v22 = (*(__int64 (__fastcall **)(__int64, const char *, char *, _QWORD, _DWORD))(v21 + 40))(
                   v13,
                   "Location",
                   a7,
                   a8,
                   0))
        : (v22 = (*(__int64 (__fastcall **)(__int64, char *, __int64, _QWORD))(v21 + 152))(v13, a7, 1, 0)),
          v14 = v22,
          v22 >= 0) )
    {
      *((_DWORD *)this + 28) = 1;
    }
  }
LABEL_25:
  BUFFER::~BUFFER(a2);
  operator delete(a2);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000c390  mov     [rsp-8+arg_10], rbx
0x18000c395  push    rbp
0x18000c396  push    rsi
0x18000c397  push    rdi
0x18000c398  push    r12
0x18000c39a  push    r13
0x18000c39c  push    r14
0x18000c39e  push    r15
0x18000c3a0  lea     rbp, [rsp-30h]
0x18000c3a5  sub     rsp, 130h
0x18000c3ac  mov     rax, cs:__security_cookie
0x18000c3b3  xor     rax, rsp
0x18000c3b6  mov     [rbp+60h+var_40], rax
0x18000c3ba  mov     r14, [rbp+60h+arg_30]
0x18000c3c1  mov     r13, rcx
0x18000c3c4  mov     rcx, [rcx+0A8h]
0x18000c3cb  mov     rsi, r9
0x18000c3ce  mov     r15, rdx
0x18000c3d1  mov     rax, [rcx]
0x18000c3d4  mov     rax, [rax+20h]
0x18000c3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3dd  mov     rcx, [r15+20h]; Str
0x18000c3e1  lea     r9, [rsp+160h+var_110]; char **
0x18000c3e6  xor     r12d, r12d
0x18000c3e9  lea     r8, [rsp+160h+var_11C]; unsigned int *
0x18000c3ee  mov     rdi, rax
0x18000c3f1  mov     [rsp+160h+var_130], r12; int *
0x18000c3f6  lea     rax, [rsp+160h+Str]
0x18000c3fb  mov     [rsp+160h+var_118], r12
0x18000c400  mov     [rsp+160h+var_138], rax; char **
0x18000c405  lea     rdx, [rsp+160h+var_118]; char **
0x18000c40a  lea     rax, [rsp+160h+var_120]
0x18000c40f  mov     [rsp+160h+var_11C], r12d
0x18000c414  mov     [rsp+160h+var_140], rax; unsigned int *
0x18000c419  mov     [rsp+160h+var_110], r12
0x18000c41e  mov     [rsp+160h+var_120], r12d
0x18000c423  mov     [rsp+160h+Str], r12
0x18000c428  call    ?NextHeader@APPLICATION@@SAJPEADPEAPEADPEAK121PEAH@Z; APPLICATION::NextHeader(char *,char * *,ulong *,char * *,ulong *,char * *,int *)
0x18000c42d  mov     ebx, eax
0x18000c42f  test    eax, eax
0x18000c431  js      loc_18000C5F5
0x18000c437  jmp     short loc_18000C4A8
0x18000c439  mov     eax, [rsp+160h+var_11C]
0x18000c43d  mov     rdx, rcx
0x18000c440  mov     r9d, [rsp+160h+var_120]
0x18000c445  mov     r8, [rsp+160h+var_110]
0x18000c44a  mov     dword ptr [rsp+160h+var_140], r12d
0x18000c44f  mov     [rax+rcx], r12b
0x18000c453  mov     rcx, rdi
0x18000c456  mov     [r9+r8], r12b
0x18000c45a  mov     rax, [rdi]
0x18000c45d  mov     rax, [rax+28h]
0x18000c461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c466  mov     ebx, eax
0x18000c468  test    eax, eax
0x18000c46a  js      loc_18000C5F5
0x18000c470  mov     rcx, [rsp+160h+Str]; Str
0x18000c475  lea     rax, [rsp+160h+Str]
0x18000c47a  mov     [rsp+160h+var_130], r12; int *
0x18000c47f  lea     r9, [rsp+160h+var_110]; char **
0x18000c484  mov     [rsp+160h+var_138], rax; char **
0x18000c489  lea     r8, [rsp+160h+var_11C]; unsigned int *
0x18000c48e  lea     rax, [rsp+160h+var_120]
0x18000c493  lea     rdx, [rsp+160h+var_118]; char **
0x18000c498  mov     [rsp+160h+var_140], rax; unsigned int *
0x18000c49d  call    ?NextHeader@APPLICATION@@SAJPEADPEAPEADPEAK121PEAH@Z; APPLICATION::NextHeader(char *,char * *,ulong *,char * *,ulong *,char * *,int *)
0x18000c4a2  mov     ebx, eax
0x18000c4a4  test    eax, eax
0x18000c4a6  js      short loc_18000C4B2
0x18000c4a8  mov     rcx, [rsp+160h+var_118]
0x18000c4ad  test    rcx, rcx
0x18000c4b0  jnz     short loc_18000C439
0x18000c4b2  test    rsi, rsi
0x18000c4b5  jz      loc_18000C59F
0x18000c4bb  xor     edx, edx; Val
0x18000c4bd  lea     rcx, [rbp+60h+var_C0]; void *
0x18000c4c1  mov     r8d, 80h; Size
0x18000c4c7  call    memset_0
0x18000c4cc  mov     r8d, 40h ; '@'
0x18000c4d2  lea     rdx, [rbp+60h+var_C0]
0x18000c4d6  lea     rcx, [rsp+160h+var_100]
0x18000c4db  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c4e1  mov     rcx, [r13+0A8h]
0x18000c4e8  mov     rax, [rcx]
0x18000c4eb  mov     rax, [rax+110h]
0x18000c4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f7  mov     rdx, rsi
0x18000c4fa  lea     rcx, [rsp+160h+var_100]
0x18000c4ff  mov     rbx, rax
0x18000c502  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000c508  test    eax, eax
0x18000c50a  jns     short loc_18000C518
0x18000c50c  mov     rcx, [rbp+60h+var_E0]
0x18000c510  mov     [rcx], r12w
0x18000c514  mov     [rbp+60h+var_D0], r12d
0x18000c518  mov     rcx, [rbx]
0x18000c51b  lea     rdx, aFastcgiSetstat; "FASTCGI_SETSTATUS"
0x18000c522  mov     r8, [rbp+60h+var_E0]
0x18000c526  xor     r9d, r9d
0x18000c529  mov     byte ptr [rsp+160h+var_140], 4
0x18000c52e  mov     rax, [rcx+20h]
0x18000c532  mov     rcx, rbx
0x18000c535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53a  mov     al, [rsi]
0x18000c53c  mov     r8, rsi
0x18000c53f  mov     cl, 20h ; ' '
0x18000c541  jmp     short loc_18000C54D
0x18000c543  cmp     al, cl
0x18000c545  jz      short loc_18000C556
0x18000c547  inc     r8
0x18000c54a  mov     al, [r8]
0x18000c54d  test    al, al
0x18000c54f  jnz     short loc_18000C543
0x18000c551  jmp     short loc_18000C556
0x18000c553  inc     r8
0x18000c556  cmp     [r8], cl
0x18000c559  jz      short loc_18000C553
0x18000c55b  mov     rax, [rdi]
0x18000c55e  xor     r9d, r9d
0x18000c561  movzx   edx, [rbp+60h+arg_28]
0x18000c568  mov     rcx, rdi
0x18000c56b  mov     dword ptr [rsp+160h+var_130], 1
0x18000c573  mov     [rsp+160h+var_138], r12
0x18000c578  mov     rax, [rax+18h]
0x18000c57c  mov     dword ptr [rsp+160h+var_140], r12d
0x18000c581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c586  lea     rcx, [rsp+160h+var_100]
0x18000c58b  mov     ebx, eax
0x18000c58d  test    eax, eax
0x18000c58f  jns     short loc_18000C599
0x18000c591  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c597  jmp     short loc_18000C5F5
0x18000c599  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c59f  test    r14, r14
0x18000c5a2  jz      short loc_18000C5ED
0x18000c5a4  mov     rax, [rdi]
0x18000c5a7  mov     rcx, rdi
0x18000c5aa  test    rsi, rsi
0x18000c5ad  jnz     short loc_18000C5C7
0x18000c5af  mov     rax, [rax+98h]
0x18000c5b6  lea     r8d, [rsi+1]
0x18000c5ba  xor     r9d, r9d
0x18000c5bd  mov     rdx, r14
0x18000c5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5c5  jmp     short loc_18000C5E7
0x18000c5c7  movzx   r9d, word ptr [rbp+60h+arg_38]
0x18000c5cf  lea     rdx, aLocation_0; "Location"
0x18000c5d6  mov     rax, [rax+28h]
0x18000c5da  mov     r8, r14
0x18000c5dd  mov     dword ptr [rsp+160h+var_140], r12d
0x18000c5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5e7  mov     ebx, eax
0x18000c5e9  test    eax, eax
0x18000c5eb  js      short loc_18000C5F5
0x18000c5ed  mov     dword ptr [r13+70h], 1
0x18000c5f5  mov     rcx, r15
0x18000c5f8  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c5fe  mov     rcx, r15; Block
0x18000c601  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c606  mov     eax, ebx
0x18000c608  mov     rcx, [rbp+60h+var_40]
0x18000c60c  xor     rcx, rsp; StackCookie
0x18000c60f  call    __security_check_cookie
0x18000c614  mov     rbx, [rsp+160h+arg_10]
0x18000c61c  add     rsp, 130h
0x18000c623  pop     r15
0x18000c625  pop     r14
0x18000c627  pop     r13
0x18000c629  pop     r12
0x18000c62b  pop     rdi
0x18000c62c  pop     rsi
0x18000c62d  pop     rbp
0x18000c62e  retn
```
