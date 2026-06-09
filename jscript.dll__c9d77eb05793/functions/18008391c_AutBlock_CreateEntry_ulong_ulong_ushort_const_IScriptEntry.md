# AutBlock::CreateEntry(ulong,ulong,ushort const *,IScriptEntry * *)

- ea: `0x18008391c`
- end: `0x180083c94`
- name: `?CreateEntry@AutBlock@@IEAAJKKPEBGPEAPEAUIScriptEntry@@@Z`
- size: `888`
- prototype: `__int64 __usercall@<rax>(AutBlock *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct IScriptEntry **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180083640`
- `0x180083720`

## callees

- `0x18000441c`
- `0x180004470`
- `0x18000895c`
- `0x1800304c0`
- `0x1800576a0`
- `0x180073958`
- `0x180082e88`
- `0x1800833fc`
- `0x18008391c`
- `0x180094282`
- `0x18009428e`
- `0x180096010`

## import_xrefs

- `msvcrt!wcschr` at `0x180083b12`
- `msvcrt!wcschr` at `0x180083b12`
- `msvcrt!free` at `0x180083c01`
- `msvcrt!free` at `0x180083c01`

## pseudocode

```c
__int64 __fastcall AutBlock::CreateEntry(
        AutBlock *this,
        int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct IScriptEntry **a5)
{
  int v8; // r13d
  int *v9; // r9
  int v10; // r14d
  int appended; // ebx
  int v12; // r15d
  int v13; // r12d
  int v14; // r8d
  struct AutEntry *v15; // rbx
  wchar_t *v16; // rax
  int v17; // eax
  __int64 v18; // r15
  size_t v19; // r13
  int v20; // r14d
  char *v21; // rax
  int v22; // r15d
  unsigned __int16 *v23; // r14
  void *v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // esi
  int v27; // r12d
  AutEntry *v28; // rcx
  int v30; // [rsp+20h] [rbp-30h]
  struct AutEntry *Src; // [rsp+28h] [rbp-28h] BYREF
  AutEntry *v32; // [rsp+30h] [rbp-20h] BYREF
  __int64 v33; // [rsp+38h] [rbp-18h] BYREF
  __int64 v34; // [rsp+40h] [rbp-10h]
  int v35; // [rsp+48h] [rbp-8h]
  int v36; // [rsp+90h] [rbp+40h]
  char *v37; // [rsp+90h] [rbp+40h]

  v33 = 0;
  v34 = 0;
  v30 = 0;
  *a5 = 0;
  v8 = 0;
  v9 = (int *)*((_QWORD *)this + 4);
  v35 = 0;
  Src = 0;
  v32 = 0;
  if ( !v9 )
  {
    v9 = (int *)operator new(0x20u);
    if ( !v9 )
    {
      *((_QWORD *)this + 4) = 0;
LABEL_20:
      appended = -2147024882;
      goto LABEL_38;
    }
    v9[2] = 1;
    *(_QWORD *)v9 = &GL::`vftable';
    v9[3] = 8;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)this + 4) = v9;
  }
  if ( a2 < (unsigned int)v9[7] )
  {
    memcpy_0(&Src, (const void *)(*((_QWORD *)v9 + 2) + a2 * v9[3]), v9[3]);
    if ( !Src )
    {
      appended = -2147467259;
      goto LABEL_38;
    }
    v10 = *((_DWORD *)Src + 8);
  }
  else
  {
    v10 = *((_DWORD *)this + 16);
    a2 = v9[7];
  }
  if ( v10 > 0 )
  {
    appended = BuildString::AppendSz((BuildString *)&v33, *((const unsigned __int16 **)this + 7), v10);
    if ( appended < 0 )
      goto LABEL_38;
    v8 = HIDWORD(v34);
    v30 = HIDWORD(v34);
  }
  appended = BuildString::AppendSz((BuildString *)&v33, L"function ", -1);
  if ( appended >= 0 )
  {
    v36 = HIDWORD(v34);
    appended = BuildString::AppendSz((BuildString *)&v33, a4, -1);
    if ( appended >= 0 )
    {
      v12 = HIDWORD(v34);
      appended = BuildString::AppendSz((BuildString *)&v33, L" {\n\n}", -1);
      if ( appended >= 0 )
      {
        v13 = HIDWORD(v34);
        appended = BuildString::AppendSz((BuildString *)&v33, L"\n\n", -1);
        if ( appended >= 0 )
        {
          v14 = *((_DWORD *)this + 16);
          if ( v10 >= v14
            || (appended = BuildString::AppendSz(
                             (BuildString *)&v33,
                             (const unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * v10),
                             v14 - v10),
                appended >= 0) )
          {
            if ( v35 )
              goto LABEL_20;
            appended = AutEntry::Create(&Src, this, a3);
            if ( appended < 0 )
              goto LABEL_38;
            v15 = Src;
            *((_DWORD *)Src + 8) = v8;
            *((_DWORD *)v15 + 9) = v13;
            *((_DWORD *)v15 + 18) = v12;
            *((_DWORD *)v15 + 19) = v13;
            v16 = wcschr(a4, 0x28u);
            if ( v16 )
              v17 = v36 + v16 - a4;
            else
              v17 = v12;
            *((_DWORD *)v15 + 10) = v36;
            *((_DWORD *)v15 + 11) = v17;
            v18 = *((_QWORD *)this + 4);
            v19 = *(int *)(v18 + 12);
            v20 = v19 * (*(_DWORD *)(v18 + 28) + 1);
            if ( v20 > *(_DWORD *)(v18 + 24) && !(unsigned int)GL::FEnsureSize(*((GL **)this + 4), v20) )
            {
LABEL_27:
              (*(void (__fastcall **)(struct AutEntry *))(*(_QWORD *)v15 + 192LL))(v15);
              (*(void (__fastcall **)(struct AutEntry *))(*(_QWORD *)v15 + 16LL))(v15);
              goto LABEL_20;
            }
            v21 = (char *)(a2 * (int)v19 + *(_QWORD *)(v18 + 16));
            v37 = v21;
            if ( a2 < *(_DWORD *)(v18 + 28) )
            {
              memmove_0(&v21[v19], v21, v20 - (int)v19 - a2 * (int)v19);
              v21 = v37;
            }
            memcpy_0(v21, &Src, v19);
            ++*(_DWORD *)(v18 + 28);
            v22 = HIDWORD(v34);
            *((_DWORD *)v15 + 7) = a2;
            v23 = BuildString::PszReset((BuildString *)&v33);
            if ( !v23 )
            {
              GL::Delete(*((GL **)this + 4), a2, 1);
              goto LABEL_27;
            }
            v24 = (void *)*((_QWORD *)this + 7);
            if ( v24 )
              free(v24);
            v25 = *((_QWORD *)this + 4);
            v26 = a2 + 1;
            *((_QWORD *)this + 7) = v23;
            *((_DWORD *)this + 16) = v22;
            if ( v26 < *(_DWORD *)(v25 + 28) )
            {
              v27 = v13 - v30;
              do
              {
                memcpy_0(
                  &v32,
                  (const void *)(*(_QWORD *)(v25 + 16) + (int)(v26 * *(_DWORD *)(v25 + 12))),
                  *(int *)(v25 + 12));
                v28 = v32;
                *((_DWORD *)v32 + 7) = v26;
                AutEntry::AdjustOffsets(v28, v27 + 2);
                v25 = *((_QWORD *)this + 4);
                ++v26;
              }
              while ( v26 < *(_DWORD *)(v25 + 28) );
            }
            appended = (**(__int64 (__fastcall ***)(struct AutEntry *, GUID *, struct IScriptEntry **))v15)(
                         v15,
                         &IID_IScriptEntry,
                         a5);
          }
        }
      }
    }
  }
LABEL_38:
  BuildString::Reset((BuildString *)&v33);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18008391c  mov     [rsp-38h+arg_8], rbx
0x180083921  mov     [rsp-38h+Str], r9
0x180083926  mov     [rsp-38h+arg_10], r8d
0x18008392b  push    rbp
0x18008392c  push    rsi
0x18008392d  push    rdi
0x18008392e  push    r12
0x180083930  push    r13
0x180083932  push    r14
0x180083934  push    r15
0x180083936  mov     rbp, rsp
0x180083939  sub     rsp, 50h
0x18008393d  mov     rax, [rbp+arg_20]
0x180083941  xor     r12d, r12d
0x180083944  mov     r15, r9
0x180083947  mov     [rbp+var_18], r12
0x18008394b  mov     esi, edx
0x18008394d  mov     [rbp+var_10], r12
0x180083951  mov     rdi, rcx
0x180083954  mov     [rbp+var_30], r12d
0x180083958  mov     [rax], r12
0x18008395b  mov     r13d, r12d
0x18008395e  mov     r9, [rcx+20h]
0x180083962  mov     [rbp+var_8], r12d
0x180083966  mov     [rbp+Src], r12
0x18008396a  mov     [rbp+var_20], r12
0x18008396e  test    r9, r9
0x180083971  jnz     short loc_1800839AB
0x180083973  lea     ecx, [r12+20h]; Size
0x180083978  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008397d  mov     r9, rax
0x180083980  test    rax, rax
0x180083983  jz      short loc_1800839BB
0x180083985  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18008398c  mov     dword ptr [r9+8], 1
0x180083994  mov     [r9], rax
0x180083997  mov     dword ptr [r9+0Ch], 8
0x18008399f  mov     [r9+10h], r12
0x1800839a3  mov     [r9+18h], r12
0x1800839a7  mov     [rdi+20h], r9
0x1800839ab  mov     eax, [r9+1Ch]
0x1800839af  cmp     esi, eax
0x1800839b1  jb      short loc_1800839C4
0x1800839b3  mov     r14d, [rdi+40h]
0x1800839b7  mov     esi, eax
0x1800839b9  jmp     short loc_1800839F5
0x1800839bb  mov     [rdi+20h], r12
0x1800839bf  jmp     loc_180083ACE
0x1800839c4  movsxd  rax, dword ptr [r9+0Ch]
0x1800839c8  lea     rcx, [rbp+Src]; void *
0x1800839cc  mov     r8, rax; Size
0x1800839cf  imul    eax, esi
0x1800839d2  movsxd  rdx, eax
0x1800839d5  add     rdx, [r9+10h]; Src
0x1800839d9  call    memcpy_0
0x1800839de  mov     r14, [rbp+Src]
0x1800839e2  test    r14, r14
0x1800839e5  jnz     short loc_1800839F1
0x1800839e7  mov     ebx, 80004005h
0x1800839ec  jmp     loc_180083C71
0x1800839f1  mov     r14d, [r14+20h]
0x1800839f5  test    r14d, r14d
0x1800839f8  jle     short loc_180083A1C
0x1800839fa  mov     rdx, [rdi+38h]; unsigned __int16 *
0x1800839fe  lea     rcx, [rbp+var_18]; this
0x180083a02  mov     r8d, r14d; int
0x180083a05  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083a0a  mov     ebx, eax
0x180083a0c  test    eax, eax
0x180083a0e  js      loc_180083C71
0x180083a14  mov     r13d, dword ptr [rbp+var_10+4]
0x180083a18  mov     [rbp+var_30], r13d
0x180083a1c  or      r8d, 0FFFFFFFFh; int
0x180083a20  lea     rdx, aFunction_0; "function "
0x180083a27  lea     rcx, [rbp+var_18]; this
0x180083a2b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083a30  mov     ebx, eax
0x180083a32  test    eax, eax
0x180083a34  js      loc_180083C71
0x180083a3a  mov     eax, dword ptr [rbp+var_10+4]
0x180083a3d  lea     rcx, [rbp+var_18]; this
0x180083a41  or      r8d, 0FFFFFFFFh; int
0x180083a45  mov     dword ptr [rbp+arg_0], eax
0x180083a48  mov     rdx, r15; unsigned __int16 *
0x180083a4b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083a50  mov     ebx, eax
0x180083a52  test    eax, eax
0x180083a54  js      loc_180083C71
0x180083a5a  mov     r15d, dword ptr [rbp+var_10+4]
0x180083a5e  lea     rdx, asc_1800A6250; " {\n\n}"
0x180083a65  or      r8d, 0FFFFFFFFh; int
0x180083a69  lea     rcx, [rbp+var_18]; this
0x180083a6d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083a72  mov     ebx, eax
0x180083a74  test    eax, eax
0x180083a76  js      loc_180083C71
0x180083a7c  mov     r12d, dword ptr [rbp+var_10+4]
0x180083a80  lea     rdx, asc_1800A6248; "\n\n"
0x180083a87  or      r8d, 0FFFFFFFFh; int
0x180083a8b  lea     rcx, [rbp+var_18]; this
0x180083a8f  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083a94  mov     ebx, eax
0x180083a96  test    eax, eax
0x180083a98  js      loc_180083C71
0x180083a9e  mov     r8d, [rdi+40h]
0x180083aa2  cmp     r14d, r8d
0x180083aa5  jge     short loc_180083AC8
0x180083aa7  mov     rax, [rdi+38h]
0x180083aab  sub     r8d, r14d; int
0x180083aae  movsxd  rcx, r14d
0x180083ab1  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x180083ab5  lea     rcx, [rbp+var_18]; this
0x180083ab9  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180083abe  mov     ebx, eax
0x180083ac0  test    eax, eax
0x180083ac2  js      loc_180083C71
0x180083ac8  cmp     [rbp+var_8], 0
0x180083acc  jz      short loc_180083AD8
0x180083ace  mov     ebx, 8007000Eh
0x180083ad3  jmp     loc_180083C71
0x180083ad8  mov     r8d, [rbp+arg_10]; unsigned int
0x180083adc  lea     rcx, [rbp+Src]; struct AutEntry **
0x180083ae0  mov     rdx, rdi; struct AutBlock *
0x180083ae3  call    ?Create@AutEntry@@SAJPEAPEAV1@PEAVAutBlock@@K@Z; AutEntry::Create(AutEntry * *,AutBlock *,ulong)
0x180083ae8  mov     ebx, eax
0x180083aea  test    eax, eax
0x180083aec  js      loc_180083C71
0x180083af2  mov     rbx, [rbp+Src]
0x180083af6  mov     edx, 28h ; '('; Ch
0x180083afb  mov     r14, [rbp+Str]
0x180083aff  mov     rcx, r14; Str
0x180083b02  mov     [rbx+20h], r13d
0x180083b06  mov     [rbx+24h], r12d
0x180083b0a  mov     [rbx+48h], r15d
0x180083b0e  mov     [rbx+4Ch], r12d
0x180083b12  call    cs:__imp_wcschr
0x180083b18  mov     ecx, dword ptr [rbp+arg_0]
0x180083b1b  test    rax, rax
0x180083b1e  jz      short loc_180083B2A
0x180083b20  sub     rax, r14
0x180083b23  sar     rax, 1
0x180083b26  add     eax, ecx
0x180083b28  jmp     short loc_180083B2D
0x180083b2a  mov     eax, r15d
0x180083b2d  mov     [rbx+28h], ecx
0x180083b30  mov     [rbx+2Ch], eax
0x180083b33  mov     r15, [rdi+20h]
0x180083b37  mov     r14d, [r15+1Ch]
0x180083b3b  movsxd  r13, dword ptr [r15+0Ch]
0x180083b3f  inc     r14d
0x180083b42  imul    r14d, r13d
0x180083b46  cmp     r14d, [r15+18h]
0x180083b4a  jle     short loc_180083B81
0x180083b4c  mov     edx, r14d; int
0x180083b4f  mov     rcx, r15; this
0x180083b52  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180083b57  test    eax, eax
0x180083b59  jnz     short loc_180083B81
0x180083b5b  mov     rax, [rbx]
0x180083b5e  mov     rcx, rbx
0x180083b61  mov     rax, [rax+0C0h]
0x180083b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b6d  mov     rax, [rbx]
0x180083b70  mov     rcx, rbx
0x180083b73  mov     rax, [rax+10h]
0x180083b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b7c  jmp     loc_180083ACE
0x180083b81  mov     rax, [r15+10h]
0x180083b85  mov     edx, r13d
0x180083b88  imul    edx, esi
0x180083b8b  movsxd  rcx, edx
0x180083b8e  add     rax, rcx
0x180083b91  mov     [rbp+arg_0], rax
0x180083b95  cmp     esi, [r15+1Ch]
0x180083b99  jge     short loc_180083BB4
0x180083b9b  sub     r14d, r13d
0x180083b9e  lea     rcx, [rax+r13]; void *
0x180083ba2  sub     r14d, edx
0x180083ba5  mov     rdx, rax; Src
0x180083ba8  movsxd  r8, r14d; Size
0x180083bab  call    memmove_0
0x180083bb0  mov     rax, [rbp+arg_0]
0x180083bb4  mov     r8, r13; Size
0x180083bb7  lea     rdx, [rbp+Src]; Src
0x180083bbb  mov     rcx, rax; void *
0x180083bbe  call    memcpy_0
0x180083bc3  mov     r13d, 1
0x180083bc9  lea     rcx, [rbp+var_18]; this
0x180083bcd  add     [r15+1Ch], r13d
0x180083bd1  mov     r15d, dword ptr [rbp+var_10+4]
0x180083bd5  mov     [rbx+1Ch], esi
0x180083bd8  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x180083bdd  mov     r14, rax
0x180083be0  test    rax, rax
0x180083be3  jnz     short loc_180083BF8
0x180083be5  mov     rcx, [rdi+20h]; this
0x180083be9  mov     r8d, r13d; int
0x180083bec  mov     edx, esi; int
0x180083bee  call    ?Delete@GL@@QEAAXJJ@Z; GL::Delete(long,long)
0x180083bf3  jmp     loc_180083B5B
0x180083bf8  mov     rcx, [rdi+38h]; Block
0x180083bfc  test    rcx, rcx
0x180083bff  jz      short loc_180083C07
0x180083c01  call    cs:__imp_free
0x180083c07  mov     rcx, [rdi+20h]
0x180083c0b  add     esi, r13d
0x180083c0e  mov     [rdi+38h], r14
0x180083c12  mov     [rdi+40h], r15d
0x180083c16  cmp     esi, [rcx+1Ch]
0x180083c19  jnb     short loc_180083C56
0x180083c1b  sub     r12d, [rbp+var_30]
0x180083c1f  movsxd  rax, dword ptr [rcx+0Ch]
0x180083c23  mov     r8, rax; Size
0x180083c26  imul    eax, esi
0x180083c29  movsxd  rdx, eax
0x180083c2c  add     rdx, [rcx+10h]; Src
0x180083c30  lea     rcx, [rbp+var_20]; void *
0x180083c34  call    memcpy_0
0x180083c39  mov     rcx, [rbp+var_20]; this
0x180083c3d  lea     edx, [r12+2]; int
0x180083c42  mov     [rcx+1Ch], esi
0x180083c45  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x180083c4a  mov     rcx, [rdi+20h]
0x180083c4e  add     esi, r13d
0x180083c51  cmp     esi, [rcx+1Ch]
0x180083c54  jb      short loc_180083C1F
0x180083c56  mov     rax, [rbx]
0x180083c59  lea     rdx, IID_IScriptEntry
0x180083c60  mov     r8, [rbp+arg_20]
0x180083c64  mov     rcx, rbx
0x180083c67  mov     rax, [rax]
0x180083c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c6f  mov     ebx, eax
0x180083c71  lea     rcx, [rbp+var_18]; this
0x180083c75  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x180083c7a  mov     eax, ebx
0x180083c7c  mov     rbx, [rsp+50h+arg_8]
0x180083c84  add     rsp, 50h
0x180083c88  pop     r15
0x180083c8a  pop     r14
0x180083c8c  pop     r13
0x180083c8e  pop     r12
0x180083c90  pop     rdi
0x180083c91  pop     rsi
0x180083c92  pop     rbp
0x180083c93  retn
```
