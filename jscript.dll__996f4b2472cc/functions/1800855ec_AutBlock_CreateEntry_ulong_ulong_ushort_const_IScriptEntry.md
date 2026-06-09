# AutBlock::CreateEntry(ulong,ulong,ushort const *,IScriptEntry * *)

- ea: `0x1800855ec`
- end: `0x180085971`
- name: `?CreateEntry@AutBlock@@IEAAJKKPEBGPEAPEAUIScriptEntry@@@Z`
- size: `901`
- prototype: `__int64 __usercall@<rax>(AutBlock *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct IScriptEntry **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180085310`
- `0x1800853f0`

## callees

- `0x180032664`
- `0x1800326c0`
- `0x18003557c`
- `0x180041fdc`
- `0x1800585d0`
- `0x180074e18`
- `0x180084b38`
- `0x1800850c0`
- `0x1800855ec`
- `0x180096692`
- `0x18009669e`
- `0x180098010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800857e2`
- `msvcrt!wcschr` at `0x1800857e2`
- `msvcrt!free` at `0x1800858d7`
- `msvcrt!free` at `0x1800858d7`

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
0x1800855ec  mov     [rsp-38h+arg_8], rbx
0x1800855f1  mov     [rsp-38h+Str], r9
0x1800855f6  mov     [rsp-38h+arg_10], r8d
0x1800855fb  push    rbp
0x1800855fc  push    rsi
0x1800855fd  push    rdi
0x1800855fe  push    r12
0x180085600  push    r13
0x180085602  push    r14
0x180085604  push    r15
0x180085606  mov     rbp, rsp
0x180085609  sub     rsp, 50h
0x18008560d  mov     rax, [rbp+arg_20]
0x180085611  xor     r12d, r12d
0x180085614  mov     r15, r9
0x180085617  mov     [rbp+var_18], r12
0x18008561b  mov     esi, edx
0x18008561d  mov     [rbp+var_10], r12
0x180085621  mov     rdi, rcx
0x180085624  mov     [rbp+var_30], r12d
0x180085628  mov     [rax], r12
0x18008562b  mov     r13d, r12d
0x18008562e  mov     r9, [rcx+20h]
0x180085632  mov     [rbp+var_8], r12d
0x180085636  mov     [rbp+Src], r12
0x18008563a  mov     [rbp+var_20], r12
0x18008563e  test    r9, r9
0x180085641  jnz     short loc_18008567B
0x180085643  lea     ecx, [r12+20h]; Size
0x180085648  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008564d  mov     r9, rax
0x180085650  test    rax, rax
0x180085653  jz      short loc_18008568B
0x180085655  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18008565c  mov     dword ptr [r9+8], 1
0x180085664  mov     [r9], rax
0x180085667  mov     dword ptr [r9+0Ch], 8
0x18008566f  mov     [r9+10h], r12
0x180085673  mov     [r9+18h], r12
0x180085677  mov     [rdi+20h], r9
0x18008567b  mov     eax, [r9+1Ch]
0x18008567f  cmp     esi, eax
0x180085681  jb      short loc_180085694
0x180085683  mov     r14d, [rdi+40h]
0x180085687  mov     esi, eax
0x180085689  jmp     short loc_1800856C5
0x18008568b  mov     [rdi+20h], r12
0x18008568f  jmp     loc_18008579E
0x180085694  movsxd  rax, dword ptr [r9+0Ch]
0x180085698  lea     rcx, [rbp+Src]; void *
0x18008569c  mov     r8, rax; Size
0x18008569f  imul    eax, esi
0x1800856a2  movsxd  rdx, eax
0x1800856a5  add     rdx, [r9+10h]; Src
0x1800856a9  call    memcpy_0
0x1800856ae  mov     r14, [rbp+Src]
0x1800856b2  test    r14, r14
0x1800856b5  jnz     short loc_1800856C1
0x1800856b7  mov     ebx, 80004005h
0x1800856bc  jmp     loc_18008594D
0x1800856c1  mov     r14d, [r14+20h]
0x1800856c5  test    r14d, r14d
0x1800856c8  jle     short loc_1800856EC
0x1800856ca  mov     rdx, [rdi+38h]; unsigned __int16 *
0x1800856ce  lea     rcx, [rbp+var_18]; this
0x1800856d2  mov     r8d, r14d; int
0x1800856d5  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x1800856da  mov     ebx, eax
0x1800856dc  test    eax, eax
0x1800856de  js      loc_18008594D
0x1800856e4  mov     r13d, dword ptr [rbp+var_10+4]
0x1800856e8  mov     [rbp+var_30], r13d
0x1800856ec  or      r8d, 0FFFFFFFFh; int
0x1800856f0  lea     rdx, aFunction_0; "function "
0x1800856f7  lea     rcx, [rbp+var_18]; this
0x1800856fb  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180085700  mov     ebx, eax
0x180085702  test    eax, eax
0x180085704  js      loc_18008594D
0x18008570a  mov     eax, dword ptr [rbp+var_10+4]
0x18008570d  lea     rcx, [rbp+var_18]; this
0x180085711  or      r8d, 0FFFFFFFFh; int
0x180085715  mov     dword ptr [rbp+arg_0], eax
0x180085718  mov     rdx, r15; unsigned __int16 *
0x18008571b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180085720  mov     ebx, eax
0x180085722  test    eax, eax
0x180085724  js      loc_18008594D
0x18008572a  mov     r15d, dword ptr [rbp+var_10+4]
0x18008572e  lea     rdx, asc_1800A8218; " {\n\n}"
0x180085735  or      r8d, 0FFFFFFFFh; int
0x180085739  lea     rcx, [rbp+var_18]; this
0x18008573d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180085742  mov     ebx, eax
0x180085744  test    eax, eax
0x180085746  js      loc_18008594D
0x18008574c  mov     r12d, dword ptr [rbp+var_10+4]
0x180085750  lea     rdx, asc_1800A8268; "\n\n"
0x180085757  or      r8d, 0FFFFFFFFh; int
0x18008575b  lea     rcx, [rbp+var_18]; this
0x18008575f  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180085764  mov     ebx, eax
0x180085766  test    eax, eax
0x180085768  js      loc_18008594D
0x18008576e  mov     r8d, [rdi+40h]
0x180085772  cmp     r14d, r8d
0x180085775  jge     short loc_180085798
0x180085777  mov     rax, [rdi+38h]
0x18008577b  sub     r8d, r14d; int
0x18008577e  movsxd  rcx, r14d
0x180085781  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x180085785  lea     rcx, [rbp+var_18]; this
0x180085789  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18008578e  mov     ebx, eax
0x180085790  test    eax, eax
0x180085792  js      loc_18008594D
0x180085798  cmp     [rbp+var_8], 0
0x18008579c  jz      short loc_1800857A8
0x18008579e  mov     ebx, 8007000Eh
0x1800857a3  jmp     loc_18008594D
0x1800857a8  mov     r8d, [rbp+arg_10]; unsigned int
0x1800857ac  lea     rcx, [rbp+Src]; struct AutEntry **
0x1800857b0  mov     rdx, rdi; struct AutBlock *
0x1800857b3  call    ?Create@AutEntry@@SAJPEAPEAV1@PEAVAutBlock@@K@Z; AutEntry::Create(AutEntry * *,AutBlock *,ulong)
0x1800857b8  mov     ebx, eax
0x1800857ba  test    eax, eax
0x1800857bc  js      loc_18008594D
0x1800857c2  mov     rbx, [rbp+Src]
0x1800857c6  mov     edx, 28h ; '('; Ch
0x1800857cb  mov     r14, [rbp+Str]
0x1800857cf  mov     rcx, r14; Str
0x1800857d2  mov     [rbx+20h], r13d
0x1800857d6  mov     [rbx+24h], r12d
0x1800857da  mov     [rbx+48h], r15d
0x1800857de  mov     [rbx+4Ch], r12d
0x1800857e2  call    cs:__imp_wcschr
0x1800857e9  nop     dword ptr [rax+rax+00h]
0x1800857ee  mov     ecx, dword ptr [rbp+arg_0]
0x1800857f1  test    rax, rax
0x1800857f4  jz      short loc_180085800
0x1800857f6  sub     rax, r14
0x1800857f9  sar     rax, 1
0x1800857fc  add     eax, ecx
0x1800857fe  jmp     short loc_180085803
0x180085800  mov     eax, r15d
0x180085803  mov     [rbx+28h], ecx
0x180085806  mov     [rbx+2Ch], eax
0x180085809  mov     r15, [rdi+20h]
0x18008580d  mov     r14d, [r15+1Ch]
0x180085811  movsxd  r13, dword ptr [r15+0Ch]
0x180085815  inc     r14d
0x180085818  imul    r14d, r13d
0x18008581c  cmp     r14d, [r15+18h]
0x180085820  jle     short loc_180085857
0x180085822  mov     edx, r14d; int
0x180085825  mov     rcx, r15; this
0x180085828  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18008582d  test    eax, eax
0x18008582f  jnz     short loc_180085857
0x180085831  mov     rax, [rbx]
0x180085834  mov     rcx, rbx
0x180085837  mov     rax, [rax+0C0h]
0x18008583e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085843  mov     rax, [rbx]
0x180085846  mov     rcx, rbx
0x180085849  mov     rax, [rax+10h]
0x18008584d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085852  jmp     loc_18008579E
0x180085857  mov     rax, [r15+10h]
0x18008585b  mov     edx, r13d
0x18008585e  imul    edx, esi
0x180085861  movsxd  rcx, edx
0x180085864  add     rax, rcx
0x180085867  mov     [rbp+arg_0], rax
0x18008586b  cmp     esi, [r15+1Ch]
0x18008586f  jge     short loc_18008588A
0x180085871  sub     r14d, r13d
0x180085874  lea     rcx, [rax+r13]; void *
0x180085878  sub     r14d, edx
0x18008587b  mov     rdx, rax; Src
0x18008587e  movsxd  r8, r14d; Size
0x180085881  call    memmove_0
0x180085886  mov     rax, [rbp+arg_0]
0x18008588a  mov     r8, r13; Size
0x18008588d  lea     rdx, [rbp+Src]; Src
0x180085891  mov     rcx, rax; void *
0x180085894  call    memcpy_0
0x180085899  mov     r13d, 1
0x18008589f  lea     rcx, [rbp+var_18]; this
0x1800858a3  add     [r15+1Ch], r13d
0x1800858a7  mov     r15d, dword ptr [rbp+var_10+4]
0x1800858ab  mov     [rbx+1Ch], esi
0x1800858ae  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x1800858b3  mov     r14, rax
0x1800858b6  test    rax, rax
0x1800858b9  jnz     short loc_1800858CE
0x1800858bb  mov     rcx, [rdi+20h]; this
0x1800858bf  mov     r8d, r13d; int
0x1800858c2  mov     edx, esi; int
0x1800858c4  call    ?Delete@GL@@QEAAXJJ@Z; GL::Delete(long,long)
0x1800858c9  jmp     loc_180085831
0x1800858ce  mov     rcx, [rdi+38h]; Block
0x1800858d2  test    rcx, rcx
0x1800858d5  jz      short loc_1800858E3
0x1800858d7  call    cs:__imp_free
0x1800858de  nop     dword ptr [rax+rax+00h]
0x1800858e3  mov     rcx, [rdi+20h]
0x1800858e7  add     esi, r13d
0x1800858ea  mov     [rdi+38h], r14
0x1800858ee  mov     [rdi+40h], r15d
0x1800858f2  cmp     esi, [rcx+1Ch]
0x1800858f5  jnb     short loc_180085932
0x1800858f7  sub     r12d, [rbp+var_30]
0x1800858fb  movsxd  rax, dword ptr [rcx+0Ch]
0x1800858ff  mov     r8, rax; Size
0x180085902  imul    eax, esi
0x180085905  movsxd  rdx, eax
0x180085908  add     rdx, [rcx+10h]; Src
0x18008590c  lea     rcx, [rbp+var_20]; void *
0x180085910  call    memcpy_0
0x180085915  mov     rcx, [rbp+var_20]; this
0x180085919  lea     edx, [r12+2]; int
0x18008591e  mov     [rcx+1Ch], esi
0x180085921  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x180085926  mov     rcx, [rdi+20h]
0x18008592a  add     esi, r13d
0x18008592d  cmp     esi, [rcx+1Ch]
0x180085930  jb      short loc_1800858FB
0x180085932  mov     rax, [rbx]
0x180085935  lea     rdx, IID_IScriptEntry
0x18008593c  mov     r8, [rbp+arg_20]
0x180085940  mov     rcx, rbx
0x180085943  mov     rax, [rax]
0x180085946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008594b  mov     ebx, eax
0x18008594d  lea     rcx, [rbp+var_18]; this
0x180085951  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x180085956  mov     eax, ebx
0x180085958  mov     rbx, [rsp+50h+arg_8]
0x180085960  add     rsp, 50h
0x180085964  pop     r15
0x180085966  pop     r14
0x180085968  pop     r13
0x18008596a  pop     r12
0x18008596c  pop     rdi
0x18008596d  pop     rsi
0x18008596e  pop     rbp
0x18008596f  retn
```
