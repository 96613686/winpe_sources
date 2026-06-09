# CPersistStreamInit::WriteData(CRowInfo &,unsigned __int64)

- ea: `0x18001e3c0`
- end: `0x18001e9fb`
- name: `?WriteData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z`
- size: `1595`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x18001c400`
- `0x18001ee64`

## callees

- `0x180001e24`
- `0x18001c1dc`
- `0x18001c394`
- `0x18001e3c0`
- `0x18001ed5c`
- `0x18001ee64`
- `0x18001fcec`
- `0x18001fe94`
- `0x18002f092`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001e70a`
- `ole32!CoTaskMemFree` at `0x18001e7d8`
- `ole32!CoTaskMemFree` at `0x18001e7e9`
- `ole32!CoTaskMemFree` at `0x18001e87f`
- `ole32!CoTaskMemFree` at `0x18001e89f`
- `ole32!CoTaskMemFree` at `0x18001e8b0`
- `ole32!CoTaskMemFree` at `0x18001e8d2`
- `ole32!CoTaskMemFree` at `0x18001e957`
- `ole32!CoTaskMemFree` at `0x18001e968`
- `ole32!CoTaskMemFree` at `0x18001e70a`
- `ole32!CoTaskMemFree` at `0x18001e7d8`
- `ole32!CoTaskMemFree` at `0x18001e7e9`
- `ole32!CoTaskMemFree` at `0x18001e87f`
- `ole32!CoTaskMemFree` at `0x18001e89f`
- `ole32!CoTaskMemFree` at `0x18001e8b0`
- `ole32!CoTaskMemFree` at `0x18001e8d2`
- `ole32!CoTaskMemFree` at `0x18001e957`
- `ole32!CoTaskMemFree` at `0x18001e968`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPersistStreamInit::WriteData(CPersistStreamInit *this, struct CRowInfo *a2, void *a3)
{
  LPVOID v3; // r14
  unsigned int v6; // r15d
  int v7; // ebx
  int v8; // edx
  struct CBitMap *BitMap; // rax
  _QWORD *v10; // r13
  _QWORD *v11; // r12
  _QWORD *v12; // r14
  _DWORD *v13; // r15
  int v14; // edx
  struct CBitMap *v15; // rbx
  unsigned __int64 *v16; // rcx
  struct CBitMap *v17; // rax
  unsigned int *v18; // rdx
  unsigned int v19; // ecx
  void *v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // r14
  unsigned __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  unsigned __int64 *v29; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v30; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-10h] BYREF
  __int64 v32; // [rsp+58h] [rbp-8h] BYREF
  char v33; // [rsp+A8h] [rbp+48h]
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp+58h] BYREF

  pv = a3;
  v3 = a3;
  v6 = 0;
  v7 = 0;
  v31 = 0;
  v32 = 0;
  v29 = (unsigned __int64 *)&v32;
  v35 = 0;
  if ( a3 && !*((_QWORD *)a2 + 30) && !CPersistStreamInit::IsTopLevel(this, a2) )
  {
    BitMap = MakeBitMap(1024, v8);
    *((_QWORD *)a2 + 30) = BitMap;
    if ( !BitMap )
    {
LABEL_5:
      v7 = -2147024882;
      goto LABEL_60;
    }
    *((_DWORD *)a2 + 62) = 1024;
  }
  if ( CPersistStreamInit::IsTopLevel(this, a2) )
  {
    v7 = CPersistStreamInit::WriteTag(this, 0x30u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteNamespace(this, 0x41u);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 2u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 0x31u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    v7 = CPersistStreamInit::WriteTag(this, 0x28u, &v35);
    if ( v7 < 0 )
      goto LABEL_60;
    ++*((_DWORD *)this + 12);
  }
  v33 = 0;
  v10 = (_QWORD *)((char *)a2 + 112);
  if ( !*((_QWORD *)a2 + 14) )
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))a2 + 13))(
      *((_QWORD *)a2 + 13),
      &IID_IRowsetUpdate,
      (char *)a2 + 112);
  v11 = (_QWORD *)((char *)a2 + 120);
  if ( !*((_QWORD *)a2 + 15) )
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))a2 + 13))(
      *((_QWORD *)a2 + 13),
      &IID_IUpdateInfo,
      (char *)a2 + 120);
  while ( v7 != 265926 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD, __int64, unsigned __int64 *, unsigned __int64 **))(**((_QWORD **)a2 + 13) + 40LL))(
           *((_QWORD *)a2 + 13),
           v3,
           0,
           1,
           &v31,
           &v29);
    if ( v7 < 0 )
      goto LABEL_60;
    v12 = (_QWORD *)((char *)a2 + 208);
    *((_QWORD *)a2 + 26) = 0;
    if ( !v31 )
      goto LABEL_18;
    if ( !*v10 )
      goto LABEL_32;
    v13 = (_DWORD *)((char *)a2 + 196);
    v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, __int64, unsigned __int64 *, char *))(*(_QWORD *)*v10 + 64LL))(
           *v10,
           pv,
           1,
           v29,
           (char *)a2 + 196);
    if ( v7 < 0 )
      goto LABEL_60;
    if ( *v13 != 4 )
    {
      if ( *v13 == 2 )
      {
        v7 = CPersistStreamInit::WriteRow(this, a2, *v29);
        if ( v7 < 0 )
          goto LABEL_60;
        *v12 = *((unsigned int *)a2 + 21);
        if ( *v11 )
          (*(void (__fastcall **)(_QWORD, unsigned __int64, char *, char *))(*(_QWORD *)*v11 + 24LL))(
            *v11,
            *v29,
            (char *)a2 + 208,
            (char *)a2 + 216);
        *v13 = 8;
LABEL_31:
        v6 = 0;
      }
      else
      {
        if ( *v13 != 1 )
          goto LABEL_31;
        v33 = 1;
        *v12 = *((unsigned int *)a2 + 21);
        v6 = 0;
        if ( *v11 )
          (*(void (__fastcall **)(_QWORD, unsigned __int64, char *, char *))(*(_QWORD *)*v11 + 24LL))(
            *v11,
            *v29,
            (char *)a2 + 208,
            (char *)a2 + 216);
      }
LABEL_32:
      v7 = CPersistStreamInit::WriteRow(this, a2, *v29);
      if ( v7 < 0 )
        goto LABEL_60;
      v15 = (struct CBitMap *)*((_QWORD *)a2 + 30);
      if ( v15 )
      {
        v16 = v29;
        if ( *v29 >= *((unsigned int *)a2 + 62) )
        {
          v17 = MakeBitMap(*(_DWORD *)v29 + 1024, v14);
          v15 = v17;
          if ( !v17 )
            goto LABEL_5;
          v18 = (unsigned int *)*((_QWORD *)a2 + 30);
          v19 = *(_DWORD *)v17;
          if ( *(_DWORD *)v17 >= *v18 )
            v19 = *v18;
          memcpy_0((char *)v17 + 4, v18 + 1, v19);
          MMMFree(*((unsigned __int8 **)a2 + 30));
          *((_QWORD *)a2 + 30) = v15;
          v16 = v29;
          *((_DWORD *)a2 + 62) = *(_DWORD *)v29 + 1024;
        }
        *((_BYTE *)v15 + ((__int64)*(int *)v16 >> 3) + 4) |= *((_BYTE *)bits + (*(_DWORD *)v16 & 7));
      }
      goto LABEL_40;
    }
    *v13 = *((_DWORD *)a2 + 50);
    v6 = 0;
LABEL_40:
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**((_QWORD **)a2 + 13) + 48LL))(
           *((_QWORD *)a2 + 13),
           1,
           v29);
    if ( v7 < 0 )
      goto LABEL_60;
    *v12 = 0;
    v20 = (void *)*((_QWORD *)a2 + 27);
    if ( v20 )
    {
      CoTaskMemFree(v20);
      *((_QWORD *)a2 + 27) = 0;
    }
    *v29 = 0;
LABEL_18:
    v3 = pv;
  }
  CPersistStreamInit::WriteStatusFooter(this, *((_DWORD *)a2 + 49));
  v21 = *((_QWORD *)a2 + 14);
  if ( !v21 )
    goto LABEL_67;
  v30 = 0;
  pv = 0;
  *((_DWORD *)a2 + 50) = 8;
  v7 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v21 + 56LL))(
         v21,
         v3,
         5 - (unsigned int)(v33 != 0),
         &v31,
         &pv,
         &v30);
  if ( v7 < 0 )
    goto LABEL_59;
  v22 = (_QWORD *)((char *)a2 + 208);
  while ( 1 )
  {
    v23 = v31;
    if ( v6 >= v31 )
      break;
    v24 = *((_DWORD *)v30 + v6);
    *((_DWORD *)a2 + 49) = v24;
    if ( v24 == 1 )
    {
      *v22 = *((unsigned int *)a2 + 21);
      v25 = *((_QWORD *)a2 + 15);
      if ( v25 )
        (*(void (__fastcall **)(__int64, _QWORD, char *, char *))(*(_QWORD *)v25 + 24LL))(
          v25,
          *((_QWORD *)pv + v6),
          (char *)a2 + 208,
          (char *)a2 + 216);
    }
    v7 = CPersistStreamInit::WriteRow(this, a2, *((_QWORD *)pv + v6));
    if ( v7 < 0 )
      goto LABEL_59;
    *v22 = 0;
    v26 = (void *)*((_QWORD *)a2 + 27);
    if ( v26 )
    {
      CoTaskMemFree(v26);
      *((_QWORD *)a2 + 27) = 0;
    }
    ++v6;
  }
  if ( v31 )
  {
    CPersistStreamInit::WriteStatusFooter(this, *((_DWORD *)a2 + 49));
    v23 = v31;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, LPVOID, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 13)
                                                                                           + 48LL))(
         *((_QWORD *)a2 + 13),
         v23,
         pv,
         0,
         0,
         0);
  if ( v7 < 0 )
  {
LABEL_59:
    CoTaskMemFree(pv);
    CoTaskMemFree(v30);
  }
  else
  {
    *((_DWORD *)a2 + 49) = 8;
    *((_DWORD *)a2 + 50) = 8;
    CoTaskMemFree(pv);
    CoTaskMemFree(v30);
LABEL_67:
    if ( CPersistStreamInit::IsTopLevel(this, a2) )
    {
      --*((_DWORD *)this + 12);
      v7 = CPersistStreamInit::WriteTag(this, 0x33u, &v35);
      if ( v7 >= 0 )
      {
        v7 = CPersistStreamInit::WriteNamespace(this, 0x41u);
        if ( v7 >= 0 )
        {
          v7 = CPersistStreamInit::WriteTag(this, 2u, &v35);
          if ( v7 >= 0 )
          {
            v7 = CPersistStreamInit::WriteTag(this, 0x31u, &v35);
            if ( v7 >= 0 )
              v7 = CPersistStreamInit::WriteTag(this, 0x28u, &v35);
          }
        }
      }
    }
  }
LABEL_60:
  *((_QWORD *)a2 + 26) = 0;
  v27 = (void *)*((_QWORD *)a2 + 27);
  if ( v27 )
  {
    CoTaskMemFree(v27);
    *((_QWORD *)a2 + 27) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e3c0  mov     [rsp-38h+arg_0], rbx
0x18001e3c5  mov     [rsp-38h+pv], r8
0x18001e3ca  push    rbp
0x18001e3cb  push    rsi
0x18001e3cc  push    rdi
0x18001e3cd  push    r12
0x18001e3cf  push    r13
0x18001e3d1  push    r14
0x18001e3d3  push    r15
0x18001e3d5  mov     rbp, rsp
0x18001e3d8  sub     rsp, 60h
0x18001e3dc  mov     r14, r8
0x18001e3df  mov     rdi, rdx
0x18001e3e2  mov     rsi, rcx
0x18001e3e5  xor     r15d, r15d
0x18001e3e8  mov     ebx, r15d
0x18001e3eb  mov     [rbp+var_10], r15
0x18001e3ef  mov     [rbp+var_8], r15
0x18001e3f3  lea     rax, [rbp+var_8]
0x18001e3f7  mov     [rbp+var_20], rax
0x18001e3fb  mov     [rbp+arg_18], r15d
0x18001e3ff  mov     r12d, 400h
0x18001e405  test    r8, r8
0x18001e408  jz      short loc_18001E441
0x18001e40a  cmp     [rdx+0F0h], r15
0x18001e411  jnz     short loc_18001E441
0x18001e413  call    ?IsTopLevel@CPersistStreamInit@@AEAA_NAEAVCRowInfo@@@Z; CPersistStreamInit::IsTopLevel(CRowInfo &)
0x18001e418  test    al, al
0x18001e41a  jnz     short loc_18001E441
0x18001e41c  mov     ecx, r12d; int
0x18001e41f  call    ?MakeBitMap@@YAPEAVCBitMap@@JH@Z; MakeBitMap(long,int)
0x18001e424  mov     [rdi+0F0h], rax
0x18001e42b  test    rax, rax
0x18001e42e  jnz     short loc_18001E43A
0x18001e430  mov     ebx, 8007000Eh
0x18001e435  jmp     loc_18001E8BF
0x18001e43a  mov     [rdi+0F8h], r12d
0x18001e441  mov     rdx, rdi; struct CRowInfo *
0x18001e444  mov     rcx, rsi; this
0x18001e447  call    ?IsTopLevel@CPersistStreamInit@@AEAA_NAEAVCRowInfo@@@Z; CPersistStreamInit::IsTopLevel(CRowInfo &)
0x18001e44c  test    al, al
0x18001e44e  jz      short loc_18001E4C7
0x18001e450  lea     r8, [rbp+arg_18]; unsigned int *
0x18001e454  mov     dl, 30h ; '0'; unsigned __int8
0x18001e456  mov     rcx, rsi; this
0x18001e459  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e45e  mov     ebx, eax
0x18001e460  test    eax, eax
0x18001e462  js      loc_18001E8BF
0x18001e468  mov     dl, 41h ; 'A'; unsigned __int8
0x18001e46a  mov     rcx, rsi; this
0x18001e46d  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001e472  mov     ebx, eax
0x18001e474  test    eax, eax
0x18001e476  js      loc_18001E8BF
0x18001e47c  lea     r8, [rbp+arg_18]; unsigned int *
0x18001e480  mov     dl, 2; unsigned __int8
0x18001e482  mov     rcx, rsi; this
0x18001e485  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e48a  mov     ebx, eax
0x18001e48c  test    eax, eax
0x18001e48e  js      loc_18001E8BF
0x18001e494  lea     r8, [rbp+arg_18]; unsigned int *
0x18001e498  mov     dl, 31h ; '1'; unsigned __int8
0x18001e49a  mov     rcx, rsi; this
0x18001e49d  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e4a2  mov     ebx, eax
0x18001e4a4  test    eax, eax
0x18001e4a6  js      loc_18001E8BF
0x18001e4ac  lea     r8, [rbp+arg_18]; unsigned int *
0x18001e4b0  mov     dl, 28h ; '('; unsigned __int8
0x18001e4b2  mov     rcx, rsi; this
0x18001e4b5  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001e4ba  mov     ebx, eax
0x18001e4bc  test    eax, eax
0x18001e4be  js      loc_18001E8BF
0x18001e4c4  inc     dword ptr [rsi+30h]
0x18001e4c7  mov     [rbp+arg_8], r15b
0x18001e4cb  lea     r13, [rdi+70h]
0x18001e4cf  cmp     [r13+0], r15
0x18001e4d3  jnz     short loc_18001E4EE
0x18001e4d5  mov     rcx, [rdi+68h]
0x18001e4d9  mov     rax, [rcx]
0x18001e4dc  mov     r8, r13
0x18001e4df  lea     rdx, IID_IRowsetUpdate
0x18001e4e6  mov     rax, [rax]
0x18001e4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ee  lea     r12, [rdi+78h]
0x18001e4f2  cmp     [r12], r15
0x18001e4f6  jnz     short loc_18001E517
0x18001e4f8  mov     rcx, [rdi+68h]
0x18001e4fc  mov     rax, [rcx]
0x18001e4ff  mov     r8, r12
0x18001e502  lea     rdx, ?IID_IUpdateInfo@@3U_GUID@@B; _GUID const IID_IUpdateInfo
0x18001e509  mov     rax, [rax]
0x18001e50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e511  jmp     short loc_18001E517
0x18001e513  mov     r14, [rbp+pv]
0x18001e517  cmp     ebx, 40EC6h
0x18001e51d  jz      loc_18001E76F
0x18001e523  mov     rcx, [rdi+68h]
0x18001e527  mov     rax, [rcx]
0x18001e52a  lea     rdx, [rbp+var_20]
0x18001e52e  mov     [rsp+60h+var_38], rdx
0x18001e533  lea     rdx, [rbp+var_10]
0x18001e537  mov     [rsp+60h+var_40], rdx
0x18001e53c  mov     r9d, 1
0x18001e542  xor     r8d, r8d
0x18001e545  mov     rdx, r14
0x18001e548  mov     rax, [rax+28h]
0x18001e54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e551  mov     ebx, eax
0x18001e553  test    eax, eax
0x18001e555  js      loc_18001E8BF
0x18001e55b  lea     r14, [rdi+0D0h]
0x18001e562  mov     [r14], r15
0x18001e565  cmp     [rbp+var_10], r15
0x18001e569  jz      short loc_18001E513
0x18001e56b  mov     rcx, [r13+0]
0x18001e56f  test    rcx, rcx
0x18001e572  jz      loc_18001E61B
0x18001e578  lea     r15, [rdi+0C4h]
0x18001e57f  mov     rax, [rcx]
0x18001e582  mov     [rsp+60h+var_40], r15
0x18001e587  mov     r9, [rbp+var_20]
0x18001e58b  mov     r8d, 1
0x18001e591  mov     rdx, [rbp+pv]
0x18001e595  mov     rax, [rax+40h]
0x18001e599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e59e  mov     ebx, eax
0x18001e5a0  test    eax, eax
0x18001e5a2  js      loc_18001E8BC
0x18001e5a8  cmp     dword ptr [r15], 4
0x18001e5ac  jnz     short loc_18001E5BF
0x18001e5ae  mov     eax, [rdi+0C8h]
0x18001e5b4  mov     [r15], eax
0x18001e5b7  xor     r15d, r15d
0x18001e5ba  jmp     loc_18001E6CC
0x18001e5bf  cmp     dword ptr [r15], 2
0x18001e5c3  jnz     loc_18001E729
0x18001e5c9  mov     r8, [rbp+var_20]
0x18001e5cd  mov     r8, [r8]; unsigned __int64
0x18001e5d0  mov     rdx, rdi; struct CRowInfo *
0x18001e5d3  mov     rcx, rsi; this
0x18001e5d6  call    ?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)
0x18001e5db  mov     ebx, eax
0x18001e5dd  test    eax, eax
0x18001e5df  js      loc_18001E8BC
0x18001e5e5  mov     eax, [rdi+54h]
0x18001e5e8  mov     [r14], rax
0x18001e5eb  mov     rcx, [r12]
0x18001e5ef  test    rcx, rcx
0x18001e5f2  jz      short loc_18001E611
0x18001e5f4  mov     rax, [rcx]
0x18001e5f7  lea     r9, [rdi+0D8h]
0x18001e5fe  mov     r8, r14
0x18001e601  mov     rdx, [rbp+var_20]
0x18001e605  mov     rdx, [rdx]
0x18001e608  mov     rax, [rax+18h]
0x18001e60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e611  mov     dword ptr [r15], 8
0x18001e618  xor     r15d, r15d
0x18001e61b  mov     r8, [rbp+var_20]
0x18001e61f  mov     r8, [r8]; unsigned __int64
0x18001e622  mov     rdx, rdi; struct CRowInfo *
0x18001e625  mov     rcx, rsi; this
0x18001e628  call    ?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)
0x18001e62d  mov     ebx, eax
0x18001e62f  test    eax, eax
0x18001e631  js      loc_18001E8BF
0x18001e637  mov     rbx, [rdi+0F0h]
0x18001e63e  test    rbx, rbx
0x18001e641  jz      loc_18001E6CC
0x18001e647  mov     eax, [rdi+0F8h]
0x18001e64d  mov     rcx, [rbp+var_20]
0x18001e651  cmp     [rcx], rax
0x18001e654  jb      short loc_18001E6B1
0x18001e656  mov     ecx, [rcx]
0x18001e658  add     ecx, 400h; int
0x18001e65e  call    ?MakeBitMap@@YAPEAVCBitMap@@JH@Z; MakeBitMap(long,int)
0x18001e663  mov     rbx, rax
0x18001e666  test    rax, rax
0x18001e669  jz      loc_18001E430
0x18001e66f  mov     rdx, [rdi+0F0h]
0x18001e676  mov     ecx, [rax]
0x18001e678  cmp     ecx, [rdx]
0x18001e67a  cmovnb  ecx, [rdx]
0x18001e67d  mov     r8d, ecx; Size
0x18001e680  add     rdx, 4; Src
0x18001e684  lea     rcx, [rax+4]; void *
0x18001e688  call    memcpy_0
0x18001e68d  mov     rcx, [rdi+0F0h]; unsigned __int8 *
0x18001e694  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001e699  mov     [rdi+0F0h], rbx
0x18001e6a0  mov     rcx, [rbp+var_20]
0x18001e6a4  mov     eax, [rcx]
0x18001e6a6  add     eax, 400h
0x18001e6ab  mov     [rdi+0F8h], eax
0x18001e6b1  movsxd  rax, dword ptr [rcx]
0x18001e6b4  mov     rcx, rax
0x18001e6b7  sar     rcx, 3
0x18001e6bb  and     eax, 7
0x18001e6be  lea     rdx, bits
0x18001e6c5  mov     al, [rax+rdx]
0x18001e6c8  or      [rcx+rbx+4], al
0x18001e6cc  mov     rcx, [rdi+68h]
0x18001e6d0  mov     rax, [rcx]
0x18001e6d3  mov     [rsp+60h+var_38], r15
0x18001e6d8  mov     [rsp+60h+var_40], r15
0x18001e6dd  xor     r9d, r9d
0x18001e6e0  mov     r8, [rbp+var_20]
0x18001e6e4  lea     edx, [r9+1]
0x18001e6e8  mov     rax, [rax+30h]
0x18001e6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f1  mov     ebx, eax
0x18001e6f3  test    eax, eax
0x18001e6f5  js      loc_18001E8BF
0x18001e6fb  mov     [r14], r15
0x18001e6fe  mov     rcx, [rdi+0D8h]; pv
0x18001e705  test    rcx, rcx
0x18001e708  jz      short loc_18001E71D
0x18001e70a  call    cs:__imp_CoTaskMemFree
0x18001e711  nop     dword ptr [rax+rax+00h]
0x18001e716  mov     [rdi+0D8h], r15
0x18001e71d  mov     rax, [rbp+var_20]
0x18001e721  mov     [rax], r15
0x18001e724  jmp     loc_18001E513
0x18001e729  cmp     dword ptr [r15], 1
0x18001e72d  jnz     loc_18001E618
0x18001e733  mov     [rbp+arg_8], 1
0x18001e737  mov     eax, [rdi+54h]
0x18001e73a  mov     [r14], rax
0x18001e73d  mov     rcx, [r12]
0x18001e741  xor     r15d, r15d
0x18001e744  test    rcx, rcx
0x18001e747  jz      loc_18001E61B
0x18001e74d  mov     rax, [rcx]
0x18001e750  lea     r9, [rdi+0D8h]
0x18001e757  mov     r8, r14
0x18001e75a  mov     rdx, [rbp+var_20]
0x18001e75e  mov     rdx, [rdx]
0x18001e761  mov     rax, [rax+18h]
0x18001e765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e76a  jmp     loc_18001E61B
0x18001e76f  mov     edx, [rdi+0C4h]; unsigned int
0x18001e775  mov     rcx, rsi; this
0x18001e778  call    ?WriteStatusFooter@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::WriteStatusFooter(ulong)
0x18001e77d  mov     rcx, [rdi+70h]
0x18001e781  test    rcx, rcx
0x18001e784  jz      loc_18001E974
0x18001e78a  mov     [rbp+var_18], r15
0x18001e78e  mov     [rbp+pv], r15
0x18001e792  mov     r13d, 8
0x18001e798  mov     [rdi+0C8h], r13d
0x18001e79f  mov     rax, [rcx]
0x18001e7a2  neg     [rbp+arg_8]
0x18001e7a5  sbb     r8d, r8d
0x18001e7a8  add     r8d, 5
0x18001e7ac  lea     rdx, [rbp+var_18]
0x18001e7b0  mov     [rsp+60h+var_38], rdx
0x18001e7b5  lea     rdx, [rbp+pv]
0x18001e7b9  mov     [rsp+60h+var_40], rdx
0x18001e7be  lea     r9, [rbp+var_10]
0x18001e7c2  mov     rdx, r14
0x18001e7c5  mov     rax, [rax+38h]
0x18001e7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7ce  mov     ebx, eax
0x18001e7d0  test    eax, eax
0x18001e7d2  jns     short loc_18001E7FA
0x18001e7d4  mov     rcx, [rbp+pv]; pv
0x18001e7d8  call    cs:__imp_CoTaskMemFree
0x18001e7df  nop     dword ptr [rax+rax+00h]
0x18001e7e4  nop
0x18001e7e5  mov     rcx, [rbp+var_18]; pv
0x18001e7e9  call    cs:__imp_CoTaskMemFree
0x18001e7f0  nop     dword ptr [rax+rax+00h]
0x18001e7f5  jmp     loc_18001E8BF
0x18001e7fa  lea     r12, [rdi+0D8h]
0x18001e801  lea     r14, [rdi+0D0h]
0x18001e808  mov     ebx, r15d
0x18001e80b  mov     rdx, [rbp+var_10]
0x18001e80f  cmp     rbx, rdx
0x18001e812  jnb     loc_18001E900
0x18001e818  mov     rax, [rbp+var_18]
0x18001e81c  mov     ecx, [rax+rbx*4]
0x18001e81f  mov     [rdi+0C4h], ecx
0x18001e825  cmp     ecx, 1
0x18001e828  jnz     short loc_18001E853
0x18001e82a  mov     eax, [rdi+54h]
0x18001e82d  mov     [r14], rax
0x18001e830  mov     rcx, [rdi+78h]
0x18001e834  test    rcx, rcx
0x18001e837  jz      short loc_18001E853
0x18001e839  mov     rax, [rcx]
0x18001e83c  mov     r9, r12
0x18001e83f  mov     r8, r14
0x18001e842  mov     rdx, [rbp+pv]
0x18001e846  mov     rdx, [rdx+rbx*8]
0x18001e84a  mov     rax, [rax+18h]
0x18001e84e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
