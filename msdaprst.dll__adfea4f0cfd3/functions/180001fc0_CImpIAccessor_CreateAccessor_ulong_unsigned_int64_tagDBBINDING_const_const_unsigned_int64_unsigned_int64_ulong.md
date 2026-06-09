# CImpIAccessor::CreateAccessor(ulong,unsigned __int64,tagDBBINDING const * const,unsigned __int64,unsigned __int64 *,ulong * const)

- ea: `0x180001fc0`
- end: `0x1800023b8`
- name: `?CreateAccessor@CImpIAccessor@@UEAAJK_KQEBUtagDBBINDING@@0PEA_KQEAK@Z`
- size: `1016`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned __int64, const struct tagDBBINDING *const, unsigned __int64, unsigned __int64 *, unsigned int *const)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180001fc0`
- `0x1800023c0`
- `0x180004384`
- `0x180016584`
- `0x18001b008`
- `0x18002f092`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002004`
- `KERNEL32!GetCurrentThreadId` at `0x180002004`
- `KERNEL32!LeaveCriticalSection` at `0x1800020ab`
- `KERNEL32!LeaveCriticalSection` at `0x180002335`
- `KERNEL32!LeaveCriticalSection` at `0x180002391`
- `KERNEL32!LeaveCriticalSection` at `0x1800020ab`
- `KERNEL32!LeaveCriticalSection` at `0x180002335`
- `KERNEL32!LeaveCriticalSection` at `0x180002391`
- `KERNEL32!VirtualAlloc` at `0x1800022b8`
- `KERNEL32!VirtualAlloc` at `0x1800022b8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002026`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002026`
- `MSDART!UMSEnterCSWraper` at `0x180001fee`
- `MSDART!UMSEnterCSWraper` at `0x180001fee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::CreateAccessor(
        CImpIAccessor *this,
        int a2,
        unsigned __int64 a3,
        const struct tagDBBINDING *const a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        unsigned int *const a7)
{
  char v9; // bl
  __int64 v11; // rdi
  DWORD *v12; // rsi
  unsigned int v13; // edx
  unsigned __int64 *v14; // r13
  unsigned int v15; // ebx
  bool v16; // zf
  __int64 v17; // rcx
  __int64 i; // rbx
  __int64 v20; // r8
  unsigned int iOrdinal; // eax
  __int64 v22; // r10
  unsigned __int16 Type; // ax
  CMetaData *v24; // r9
  unsigned __int16 v25; // ax
  __int64 v26; // r10
  unsigned int v27; // eax
  unsigned int BidObjectID; // eax
  wchar_t *v29; // r8
  char *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // edx
  int v33; // ecx
  unsigned int v34; // r15d
  unsigned __int8 *v35; // r14
  unsigned int *v36; // rbx
  unsigned int v37; // ebp
  __int64 v38; // rcx
  SIZE_T v39; // rdx
  unsigned __int64 v40; // rbx
  __int64 v41; // rcx
  __int64 v42; // rcx
  unsigned __int8 *Src; // [rsp+80h] [rbp+8h] BYREF
  int v44; // [rsp+88h] [rbp+10h]
  __int64 v45; // [rsp+90h] [rbp+18h]

  v44 = a2;
  v9 = a2;
  v11 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v11);
  v12 = (DWORD *)(v11 + 8);
  if ( !*(_DWORD *)(v11 + 12) )
    *v12 = GetCurrentThreadId();
  ++*(_DWORD *)(v11 + 12);
  ++*(_DWORD *)(v11 + 16);
  SetErrorInfo(0, 0);
  if ( a3 && !a4 || (v14 = a6) == 0 || (*a6 = 0, (v9 & 5) != 0) )
  {
    v33 = -2147024809;
LABEL_46:
    v32 = 0;
LABEL_47:
    v15 = Exit(v33, v32);
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
    goto LABEL_48;
  }
  if ( (v9 & 2) == 0 )
  {
    v15 = Exit(-2147024809, 0);
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
LABEL_48:
    if ( v16 )
      *v12 = -1;
LABEL_50:
    v42 = *(_QWORD *)v11;
    --*(_DWORD *)(v42 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v42 + 8));
    return v15;
  }
  v45 = (unsigned int)a3;
  if ( (unsigned int)a3 != a3 )
  {
    --*(_DWORD *)(v11 + 16);
    v16 = (*(_DWORD *)(v11 + 12))-- == 1;
    if ( v16 )
      *v12 = -1;
    v17 = *(_QWORD *)v11;
    --*(_DWORD *)(v17 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    return 2147500037LL;
  }
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v20 = (unsigned int)i;
    iOrdinal = a4[v20].iOrdinal;
    if ( !iOrdinal || (v22 = *((_QWORD *)this + 3), iOrdinal > *(_DWORD *)(v22 + 152)) )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800493B8[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
        v29 = off_1800493B8[0];
        v30 = off_1800491B0[0];
        v31 = 143360;
LABEL_32:
        bidTraceW(v30, v31, v29, BidObjectID, -2147217887);
      }
LABEL_33:
      v32 = 114;
      v33 = -2147217887;
      goto LABEL_47;
    }
    if ( (a4[v20].dwPart & 7) == 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800493B0[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
        v29 = off_1800493B0[0];
        v30 = off_1800491A8[0];
        v31 = 158720;
        goto LABEL_32;
      }
      goto LABEL_33;
    }
    LOWORD(Src) = a4[v20].wType;
    Type = CMetaData::mdGetType((CMetaData *)(v22 + 304), iOrdinal - 1);
    if ( (_WORD)Src != Type )
    {
      v25 = CMetaData::mdGetType(v24, v13);
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(
             v26,
             v25,
             (unsigned __int16)Src) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800493A8[0] )
        {
          v27 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_1800491A0[0], 181248, off_1800493A8[0], v27, -2147217887);
        }
        if ( a7 )
          a7[i] = 2;
        goto LABEL_33;
      }
    }
  }
  v34 = 88 * v45;
  v35 = MMMAlloc(88 * (int)v45 + 16, v13);
  Src = v35;
  if ( !v35 )
  {
    v33 = -2147024882;
    goto LABEL_46;
  }
  v36 = *(unsigned int **)(*((_QWORD *)this + 3) + 192LL);
  v37 = v36[1] * *v36;
  v38 = v36[3];
  if ( v37 + *v36 > (unsigned int)v38 )
  {
    v39 = v36[4];
    if ( (int)v39 + (int)v38 > v36[2] || !VirtualAlloc((LPVOID)(*((_QWORD *)v36 + 3) + v38), v39, 0x1000u, 4u) )
    {
      operator delete(v35);
      v15 = Exit(-2147024882, 0);
      --*(_DWORD *)(v11 + 16);
      v16 = (*(_DWORD *)(v11 + 12))-- == 1;
      if ( v16 )
        *v12 = -1;
      goto LABEL_50;
    }
    v36[3] += v36[4];
  }
  memcpy_0((void *)(*((_QWORD *)v36 + 3) + v37), &Src, *v36);
  v40 = ++v36[1];
  *(_DWORD *)v35 = v44;
  *((_DWORD *)v35 + 2) = v45;
  *((_DWORD *)v35 + 1) = 1;
  memcpy_0(v35 + 16, a4, v34);
  *v14 = v40;
  --*(_DWORD *)(v11 + 16);
  v16 = (*(_DWORD *)(v11 + 12))-- == 1;
  if ( v16 )
    *v12 = -1;
  v41 = *(_QWORD *)v11;
  --*(_DWORD *)(v41 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v41 + 8));
  return 0;
}

```

## disassembly

```asm
0x180001fc0  mov     [rsp+arg_18], rbx
0x180001fc5  mov     [rsp+arg_8], edx
0x180001fc9  push    rbp
0x180001fca  push    rsi
0x180001fcb  push    rdi
0x180001fcc  push    r12
0x180001fce  push    r13
0x180001fd0  push    r14
0x180001fd2  push    r15
0x180001fd4  sub     rsp, 40h
0x180001fd8  mov     r12, r9
0x180001fdb  mov     r14, r8
0x180001fde  mov     ebx, edx
0x180001fe0  mov     rbp, rcx
0x180001fe3  mov     rdi, [rcx+18h]
0x180001fe7  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180001feb  mov     rcx, rdi
0x180001fee  call    cs:__imp_UMSEnterCSWraper
0x180001ff5  nop     dword ptr [rax+rax+00h]
0x180001ffa  lea     rsi, [rdi+8]
0x180001ffe  cmp     dword ptr [rdi+0Ch], 0
0x180002002  jnz     short loc_180002012
0x180002004  call    cs:__imp_GetCurrentThreadId
0x18000200b  nop     dword ptr [rax+rax+00h]
0x180002010  mov     [rsi], eax
0x180002012  mov     eax, 1
0x180002017  add     [rdi+0Ch], eax
0x18000201a  add     [rdi+10h], eax
0x18000201d  mov     [rsp+78h+var_48], rdi
0x180002022  xor     edx, edx; perrinfo
0x180002024  xor     ecx, ecx; dwReserved
0x180002026  call    cs:__imp_SetErrorInfo
0x18000202d  nop     dword ptr [rax+rax+00h]
0x180002032  test    r14, r14
0x180002035  jz      short loc_180002040
0x180002037  test    r12, r12
0x18000203a  jz      loc_18000236C
0x180002040  mov     r13, [rsp+78h+arg_28]
0x180002048  test    r13, r13
0x18000204b  jz      loc_18000236C
0x180002051  mov     qword ptr [r13+0], 0
0x180002059  test    bl, 5
0x18000205c  jnz     loc_18000236C
0x180002062  test    bl, 2
0x180002065  jnz     short loc_180002084
0x180002067  xor     edx, edx; unsigned int
0x180002069  mov     ecx, 80070057h; int
0x18000206e  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002073  mov     ebx, eax
0x180002075  or      edx, 0FFFFFFFFh
0x180002078  add     [rdi+10h], edx
0x18000207b  sub     dword ptr [rdi+0Ch], 1
0x18000207f  jmp     loc_180002383
0x180002084  mov     eax, r14d
0x180002087  mov     [rsp+78h+arg_10], rax
0x18000208f  cmp     rax, r14
0x180002092  jz      short loc_1800020C1
0x180002094  or      edx, 0FFFFFFFFh
0x180002097  add     [rdi+10h], edx
0x18000209a  add     [rdi+0Ch], edx
0x18000209d  jnz     short loc_1800020A1
0x18000209f  mov     [rsi], edx
0x1800020a1  mov     rcx, [rdi]
0x1800020a4  dec     dword ptr [rcx+30h]
0x1800020a7  add     rcx, 8; lpCriticalSection
0x1800020ab  call    cs:__imp_LeaveCriticalSection
0x1800020b2  nop     dword ptr [rax+rax+00h]
0x1800020b7  mov     eax, 80004005h
0x1800020bc  jmp     loc_18000239F
0x1800020c1  xor     ebx, ebx
0x1800020c3  mov     r15d, ebx
0x1800020c6  cmp     r15, r14
0x1800020c9  jnb     loc_180002251
0x1800020cf  imul    r8, r15, 58h ; 'X'
0x1800020d3  mov     eax, [r8+r12]
0x1800020d7  test    eax, eax
0x1800020d9  jz      loc_1800021F9
0x1800020df  mov     r10, [rbp+18h]
0x1800020e3  cmp     eax, [r10+98h]
0x1800020ea  ja      loc_1800021F9
0x1800020f0  test    byte ptr [r8+r12+38h], 7
0x1800020f6  jz      loc_1800021C2
0x1800020fc  lea     r9, [r10+130h]
0x180002103  lea     r11d, [rax-1]
0x180002107  movzx   eax, word ptr [r8+r12+54h]
0x18000210d  mov     word ptr [rsp+78h+Src], ax
0x180002115  movzx   edx, r11w; unsigned __int16
0x180002119  mov     rcx, r9; this
0x18000211c  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180002121  cmp     word ptr [rsp+78h+Src], ax
0x180002129  jz      short loc_180002155
0x18000212b  mov     rcx, r9; this
0x18000212e  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180002133  mov     rdx, [r10]
0x180002136  mov     r9, [rdx+40h]
0x18000213a  movzx   r8d, word ptr [rsp+78h+Src]
0x180002143  movzx   edx, ax
0x180002146  mov     rcx, r10
0x180002149  mov     rax, r9
0x18000214c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002151  test    eax, eax
0x180002153  jnz     short loc_18000215C
0x180002155  inc     ebx
0x180002157  jmp     loc_1800020C3
0x18000215c  test    byte ptr cs:_bidGblFlags, 2
0x180002163  jz      short loc_1800021A5
0x180002165  mov     rax, cs:off_1800493A8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x18000216c  test    rax, rax
0x18000216f  jz      short loc_1800021A5
0x180002171  mov     rcx, [rbp+18h]
0x180002175  add     rcx, 70h ; 'p'; this
0x180002179  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000217e  mov     r8, cs:off_1800493A8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x180002185  mov     rcx, cs:off_1800491A0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000218c  mov     [rsp+78h+var_50], ebx
0x180002190  mov     [rsp+78h+var_58], 80040E21h
0x180002198  mov     r9d, eax
0x18000219b  mov     edx, 2C400h
0x1800021a0  call    _bidTraceW
0x1800021a5  mov     rax, [rsp+78h+arg_30]
0x1800021ad  test    rax, rax
0x1800021b0  jz      loc_180002242
0x1800021b6  mov     dword ptr [rax+rbx*4], 2
0x1800021bd  jmp     loc_180002242
0x1800021c2  test    byte ptr cs:_bidGblFlags, 2
0x1800021c9  jz      short loc_180002242
0x1800021cb  mov     rax, cs:off_1800493B0; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x1800021d2  test    rax, rax
0x1800021d5  jz      short loc_180002242
0x1800021d7  mov     rcx, [rbp+18h]
0x1800021db  add     rcx, 70h ; 'p'; this
0x1800021df  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800021e4  mov     r8, cs:off_1800493B0; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x1800021eb  mov     rcx, cs:off_1800491A8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800021f2  mov     edx, 26C00h
0x1800021f7  jmp     short loc_18000222E
0x1800021f9  test    byte ptr cs:_bidGblFlags, 2
0x180002200  jz      short loc_180002242
0x180002202  mov     rax, cs:off_1800493B8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x180002209  test    rax, rax
0x18000220c  jz      short loc_180002242
0x18000220e  mov     rcx, [rbp+18h]
0x180002212  add     rcx, 70h ; 'p'; this
0x180002216  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000221b  mov     r8, cs:off_1800493B8; "<CImpIAccessor::CreateAccessor|ERR|PERS"...
0x180002222  mov     rcx, cs:off_1800491B0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002229  mov     edx, 23000h
0x18000222e  mov     [rsp+78h+var_50], ebx
0x180002232  mov     [rsp+78h+var_58], 80040E21h
0x18000223a  mov     r9d, eax
0x18000223d  call    _bidTraceW
0x180002242  mov     edx, 72h ; 'r'
0x180002247  mov     ecx, 80040E21h
0x18000224c  jmp     loc_180002373
0x180002251  imul    r15d, dword ptr [rsp+78h+arg_10], 58h ; 'X'
0x18000225a  lea     ecx, [r15+10h]; unsigned int
0x18000225e  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180002263  mov     r14, rax
0x180002266  mov     [rsp+78h+Src], rax
0x18000226e  test    rax, rax
0x180002271  jnz     short loc_18000227D
0x180002273  mov     ecx, 8007000Eh
0x180002278  jmp     loc_180002371
0x18000227d  mov     rax, [rbp+18h]
0x180002281  mov     rbx, [rax+0C0h]
0x180002288  mov     eax, [rbx]
0x18000228a  mov     ebp, eax
0x18000228c  imul    ebp, [rbx+4]
0x180002290  mov     ecx, [rbx+0Ch]
0x180002293  add     eax, ebp
0x180002295  cmp     eax, ecx
0x180002297  jbe     short loc_1800022CF
0x180002299  mov     edx, [rbx+10h]; dwSize
0x18000229c  lea     eax, [rdx+rcx]
0x18000229f  cmp     eax, [rbx+8]
0x1800022a2  ja      loc_180002345
0x1800022a8  add     rcx, [rbx+18h]; lpAddress
0x1800022ac  mov     r9d, 4; flProtect
0x1800022b2  mov     r8d, 1000h; flAllocationType
0x1800022b8  call    cs:__imp_VirtualAlloc
0x1800022bf  nop     dword ptr [rax+rax+00h]
0x1800022c4  test    rax, rax
0x1800022c7  jz      short loc_180002345
0x1800022c9  mov     eax, [rbx+10h]
0x1800022cc  add     [rbx+0Ch], eax
0x1800022cf  mov     r8d, [rbx]; Size
0x1800022d2  mov     ecx, ebp
0x1800022d4  add     rcx, [rbx+18h]; void *
0x1800022d8  lea     rdx, [rsp+78h+Src]; Src
0x1800022e0  call    memcpy_0
0x1800022e5  mov     ebp, 1
0x1800022ea  add     [rbx+4], ebp
0x1800022ed  mov     ebx, [rbx+4]
0x1800022f0  mov     eax, [rsp+78h+arg_8]
0x1800022f7  mov     [r14], eax
0x1800022fa  mov     rax, [rsp+78h+arg_10]
0x180002302  mov     [r14+8], eax
0x180002306  mov     [r14+4], ebp
0x18000230a  mov     r8d, r15d; Size
0x18000230d  lea     rcx, [r14+10h]; void *
0x180002311  mov     rdx, r12; Src
0x180002314  call    memcpy_0
0x180002319  mov     [r13+0], rbx
0x18000231d  sub     [rdi+10h], ebp
0x180002320  sub     [rdi+0Ch], ebp
0x180002323  jnz     short loc_18000232B
0x180002325  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000232b  mov     rcx, [rdi]
0x18000232e  dec     dword ptr [rcx+30h]
0x180002331  add     rcx, 8; lpCriticalSection
0x180002335  call    cs:__imp_LeaveCriticalSection
0x18000233c  nop     dword ptr [rax+rax+00h]
0x180002341  xor     eax, eax
0x180002343  jmp     short loc_18000239F
0x180002345  mov     rcx, r14; void *
0x180002348  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000234d  xor     edx, edx; unsigned int
0x18000234f  mov     ecx, 8007000Eh; int
0x180002354  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002359  mov     ebx, eax
0x18000235b  dec     dword ptr [rdi+10h]
0x18000235e  sub     dword ptr [rdi+0Ch], 1
0x180002362  jnz     short loc_180002387
0x180002364  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000236a  jmp     short loc_180002387
0x18000236c  mov     ecx, 80070057h; int
0x180002371  xor     edx, edx; unsigned int
0x180002373  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002378  mov     ebx, eax
0x18000237a  or      edx, 0FFFFFFFFh
0x18000237d  add     [rdi+10h], edx
0x180002380  add     [rdi+0Ch], edx
0x180002383  jnz     short loc_180002387
0x180002385  mov     [rsi], edx
0x180002387  mov     rcx, [rdi]
0x18000238a  dec     dword ptr [rcx+30h]
0x18000238d  add     rcx, 8; lpCriticalSection
0x180002391  call    cs:__imp_LeaveCriticalSection
0x180002398  nop     dword ptr [rax+rax+00h]
0x18000239d  mov     eax, ebx
0x18000239f  mov     rbx, [rsp+78h+arg_18]
0x1800023a7  add     rsp, 40h
0x1800023ab  pop     r15
0x1800023ad  pop     r14
0x1800023af  pop     r13
0x1800023b1  pop     r12
0x1800023b3  pop     rdi
0x1800023b4  pop     rsi
0x1800023b5  pop     rbp
0x1800023b6  retn
```
