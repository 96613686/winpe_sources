# ExecuteCallbacks(_MINIDUMP_STATE *,_INTERNAL_PROCESS *)

- ea: `0x18000670c`
- end: `0x180006a20`
- name: `?ExecuteCallbacks@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f8e8`

## callees

- `0x1800021f4`
- `0x180003424`
- `0x18000670c`
- `0x18001f334`
- `0x180020268`
- `0x18002c010`

## string_xrefs

- `0x1800069a5`: `Thread(0x%x) callback returned FALSE`

## pseudocode

```c
__int64 __fastcall ExecuteCallbacks(struct _MINIDUMP_STATE *a1, struct _INTERNAL_PROCESS *a2)
{
  struct _INTERNAL_PROCESS *v4; // rdi
  __int64 *v5; // rsi
  _DWORD *v6; // r12
  struct _INTERNAL_PROCESS *v7; // r13
  __int64 v8; // rcx
  struct _INTERNAL_PROCESS *v9; // r12
  unsigned int *v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int (__fastcall *v14)(__int64, int *, unsigned int *); // rax
  __int64 v16; // rcx
  unsigned int (__fastcall *v17)(__int64, int *, unsigned int *); // rax
  unsigned int v18[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h]
  __int128 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+74h] [rbp-8Ch]
  int v24; // [rsp+7Ch] [rbp-84h]
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v26[3]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+9Ch] [rbp-64h]
  __int128 v28; // [rsp+ACh] [rbp-54h]
  __int128 v29; // [rsp+BCh] [rbp-44h]
  int v30; // [rsp+CCh] [rbp-34h]
  __int64 v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  __int64 v33; // [rsp+DCh] [rbp-24h]
  int v34; // [rsp+E4h] [rbp-1Ch]
  unsigned int v35; // [rsp+560h] [rbp+460h]
  __int64 v36; // [rsp+564h] [rbp+464h]
  __int64 v37; // [rsp+56Ch] [rbp+46Ch]
  __int64 v38; // [rsp+574h] [rbp+474h]
  __int64 v39; // [rsp+57Ch] [rbp+47Ch]

  memset_0(&v25, 0, 0x510u);
  v21 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( *((_QWORD *)a1 + 8) )
  {
    v4 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 15);
    v5 = (__int64 *)((char *)a1 + 80);
    v23 = *(_QWORD *)a1;
    v22 = *((_DWORD *)a1 + 2);
    v24 = 0;
    if ( v4 != (struct _INTERNAL_PROCESS *)((char *)a2 + 120) )
    {
      while ( 1 )
      {
        v6 = (_DWORD *)((char *)v4 - 8);
        v7 = *(struct _INTERNAL_PROCESS **)v4;
        v8 = *v5;
        *(_QWORD *)&v25 = *((_QWORD *)v4 - 3);
        *((_QWORD *)&v25 + 1) = *((_QWORD *)v4 - 17);
        v26[0] = *((_DWORD *)v4 - 32);
        v26[1] = *((_DWORD *)v4 - 31);
        v26[2] = *((_DWORD *)v4 - 30);
        v27 = *(_OWORD *)((char *)v4 - 116);
        v28 = *(_OWORD *)((char *)v4 - 100);
        v29 = *(_OWORD *)((char *)v4 - 84);
        v30 = *((_DWORD *)v4 - 17);
        v31 = *((_QWORD *)v4 - 8);
        v32 = *((_DWORD *)v4 - 14);
        v33 = *((_QWORD *)v4 - 6);
        v34 = *((_DWORD *)v4 - 10);
        v18[0] = *((_DWORD *)v4 - 2);
        if ( !(*((unsigned int (__fastcall **)(__int64, int *, unsigned int *))a1 + 8))(v8, &v22, v18) )
          break;
        v4 = v7;
        *v6 &= v18[0];
        if ( v7 == (struct _INTERNAL_PROCESS *)((char *)a2 + 120) )
          goto LABEL_5;
      }
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "Module(0x%I64x, %ws) callback returned FALSE",
        *((_QWORD *)v4 - 17),
        *((_QWORD *)v4 - 3));
      return 2147500036LL;
    }
LABEL_5:
    v9 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 13);
    v24 = (*((_DWORD *)a1 + 26) != 0) + 1;
    if ( v9 != (struct _INTERNAL_PROCESS *)((char *)a2 + 104) )
    {
      while ( 1 )
      {
        v10 = (unsigned int *)((char *)v9 - 184);
        v9 = *(struct _INTERNAL_PROCESS **)v9;
        LODWORD(v25) = *v10;
        *(_QWORD *)((char *)&v25 + 4) = *((_QWORD *)v10 + 1);
        v11 = *((_DWORD *)a1 + 35);
        if ( v11 > 0x4D0 )
          v11 = 1232;
        v35 = v11;
        memcpy_0(v26, *((const void **)v10 + 14), v11);
        v12 = *v5;
        v36 = *((_QWORD *)v10 + 16);
        v37 = *((_QWORD *)v10 + 17);
        v38 = *((_QWORD *)v10 + 19);
        v39 = *((_QWORD *)v10 + 19) + v10[40];
        v18[0] = v10[44];
        if ( !(*((unsigned int (__fastcall **)(__int64, int *, unsigned int *))a1 + 8))(v12, &v22, v18) )
          break;
        v10[44] &= v18[0];
        if ( v9 == (struct _INTERNAL_PROCESS *)((char *)a2 + 104) )
          goto LABEL_10;
      }
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "Thread(0x%x) callback returned FALSE",
        *v10);
      return 2147500036LL;
    }
LABEL_10:
    if ( (*((_DWORD *)a1 + 14) & 0x4000002) == 0 )
    {
      v24 = 5;
      while ( 1 )
      {
        v13 = *v5;
        v14 = (unsigned int (__fastcall *)(__int64, int *, unsigned int *))*((_QWORD *)a1 + 8);
        *(_QWORD *)v18 = 0;
        v18[2] = 0;
        if ( !v14(v13, &v22, v18) || !v18[2] )
          break;
        GenAddMemoryBlock(a1, (__int64)a2, 0xCu, 0, *(unsigned __int64 *)v18, v18[2]);
      }
      v24 = 9;
      while ( 1 )
      {
        v16 = *v5;
        v17 = (unsigned int (__fastcall *)(__int64, int *, unsigned int *))*((_QWORD *)a1 + 8);
        *(_QWORD *)v18 = 0;
        v18[2] = 0;
        if ( !v17(v16, &v22, v18) || !v18[2] )
          break;
        GenRemoveMemoryRange(a1, a2, *(unsigned __int64 *)v18, v18[2]);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000670c  push    rbp
0x18000670e  push    rbx
0x18000670f  push    rsi
0x180006710  push    rdi
0x180006711  push    r12
0x180006713  push    r13
0x180006715  push    r14
0x180006717  push    r15
0x180006719  lea     rbp, [rsp-498h]
0x180006721  sub     rsp, 598h
0x180006728  mov     r14, rdx
0x18000672b  mov     rbx, rcx
0x18000672e  xor     edx, edx; Val
0x180006730  lea     rcx, [rbp+4D0h+var_550]; void *
0x180006734  mov     r8d, 510h; Size
0x18000673a  call    memset_0
0x18000673f  xorps   xmm0, xmm0
0x180006742  xor     eax, eax
0x180006744  xor     r13d, r13d
0x180006747  mov     [rsp+5D0h+var_570], eax
0x18000674b  movups  xmmword ptr [rsp+5D0h+var_5A0], xmm0
0x180006750  movups  [rsp+5D0h+var_590], xmm0
0x180006755  movups  [rsp+5D0h+var_580], xmm0
0x18000675a  cmp     [rbx+40h], r13
0x18000675e  jz      loc_180006A0A
0x180006764  mov     rax, [rbx]
0x180006767  lea     r15, [r14+78h]
0x18000676b  mov     rdi, [r15]
0x18000676e  lea     rsi, [rbx+50h]
0x180006772  mov     [rsp+5D0h+var_55C], rax
0x180006777  mov     eax, [rbx+8]
0x18000677a  mov     [rsp+5D0h+var_560], eax
0x18000677e  mov     [rsp+5D0h+var_554], r13d
0x180006783  cmp     rdi, r15
0x180006786  jz      loc_18000682F
0x18000678c  mov     rax, [rdi-18h]
0x180006790  lea     r12, [rdi-8]
0x180006794  mov     r13, [rdi]
0x180006797  lea     r8, [rsp+5D0h+var_5A0]
0x18000679c  mov     rcx, [rsi]
0x18000679f  lea     rdx, [rsp+5D0h+var_560]
0x1800067a4  mov     [rbp+4D0h+var_550], rax
0x1800067a8  mov     rax, [rdi-88h]
0x1800067af  mov     [rbp+4D0h+var_548], rax
0x1800067b3  mov     eax, [rdi-80h]
0x1800067b6  mov     [rbp+4D0h+var_540], eax
0x1800067b9  mov     eax, [rdi-7Ch]
0x1800067bc  mov     [rbp+4D0h+var_53C], eax
0x1800067bf  mov     eax, [rdi-78h]
0x1800067c2  mov     [rbp+4D0h+var_538], eax
0x1800067c5  movups  xmm0, xmmword ptr [rdi-74h]
0x1800067c9  movups  [rbp+4D0h+var_534], xmm0
0x1800067cd  movups  xmm1, xmmword ptr [rdi-64h]
0x1800067d1  movups  [rbp+4D0h+var_524], xmm1
0x1800067d5  movups  xmm0, xmmword ptr [rdi-54h]
0x1800067d9  movups  [rbp+4D0h+var_514], xmm0
0x1800067dd  mov     eax, [rdi-44h]
0x1800067e0  mov     [rbp+4D0h+var_504], eax
0x1800067e3  mov     rax, [rdi-40h]
0x1800067e7  mov     [rbp+4D0h+var_500], rax
0x1800067eb  mov     eax, [rdi-38h]
0x1800067ee  mov     [rbp+4D0h+var_4F8], eax
0x1800067f1  mov     rax, [rdi-30h]
0x1800067f5  mov     [rbp+4D0h+var_4F4], rax
0x1800067f9  mov     eax, [rdi-28h]
0x1800067fc  mov     [rbp+4D0h+var_4EC], eax
0x1800067ff  mov     eax, [r12]
0x180006803  mov     [rsp+5D0h+var_5A0], eax
0x180006807  mov     rax, [rbx+40h]
0x18000680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006810  test    eax, eax
0x180006812  jz      loc_18000696E
0x180006818  mov     eax, [rsp+5D0h+var_5A0]
0x18000681c  mov     rdi, r13
0x18000681f  and     [r12], eax
0x180006823  cmp     r13, r15
0x180006826  jnz     loc_18000678C
0x18000682c  xor     r13d, r13d
0x18000682f  mov     eax, [rbx+68h]
0x180006832  lea     r15, [r14+68h]
0x180006836  mov     r12, [r15]
0x180006839  neg     eax
0x18000683b  sbb     ecx, ecx
0x18000683d  neg     ecx
0x18000683f  inc     ecx
0x180006841  mov     [rsp+5D0h+var_554], ecx
0x180006845  cmp     r12, r15
0x180006848  jz      loc_18000690B
0x18000684e  mov     ecx, 4D0h
0x180006853  lea     rdi, [r12-0B8h]
0x18000685b  mov     r12, [r12]
0x18000685f  mov     eax, [rdi]
0x180006861  mov     dword ptr [rbp+4D0h+var_550], eax
0x180006864  mov     rax, [rdi+8]
0x180006868  mov     [rbp+4D0h+var_550+4], rax
0x18000686c  mov     eax, [rbx+8Ch]
0x180006872  cmp     eax, ecx
0x180006874  cmova   eax, ecx
0x180006877  lea     rcx, [rbp+4D0h+var_540]; void *
0x18000687b  mov     [rbp+4D0h+var_70], eax
0x180006881  mov     rdx, [rdi+70h]; Src
0x180006885  mov     r8d, eax; Size
0x180006888  call    memcpy_0
0x18000688d  mov     rax, [rdi+80h]
0x180006894  lea     r8, [rsp+5D0h+var_5A0]
0x180006899  mov     rcx, [rsi]
0x18000689c  lea     rdx, [rsp+5D0h+var_560]
0x1800068a1  mov     [rbp+4D0h+var_6C], rax
0x1800068a8  mov     rax, [rdi+88h]
0x1800068af  mov     [rbp+4D0h+var_64], rax
0x1800068b6  mov     rax, [rdi+98h]
0x1800068bd  mov     [rbp+4D0h+var_5C], rax
0x1800068c4  mov     eax, [rdi+0A0h]
0x1800068ca  add     rax, [rdi+98h]
0x1800068d1  mov     [rbp+4D0h+var_54], rax
0x1800068d8  mov     eax, [rdi+0B0h]
0x1800068de  mov     [rsp+5D0h+var_5A0], eax
0x1800068e2  mov     rax, [rbx+40h]
0x1800068e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068eb  test    eax, eax
0x1800068ed  jz      loc_1800069A1
0x1800068f3  mov     eax, [rsp+5D0h+var_5A0]
0x1800068f7  mov     ecx, 4D0h
0x1800068fc  and     [rdi+0B0h], eax
0x180006902  cmp     r12, r15
0x180006905  jnz     loc_180006853
0x18000690b  test    dword ptr [rbx+38h], 4000002h
0x180006912  jnz     loc_180006A0A
0x180006918  mov     [rsp+5D0h+var_554], 5
0x180006920  mov     rcx, [rsi]
0x180006923  lea     r8, [rsp+5D0h+var_5A0]
0x180006928  mov     rax, [rbx+40h]
0x18000692c  lea     rdx, [rsp+5D0h+var_560]
0x180006931  mov     qword ptr [rsp+5D0h+var_5A0], r13
0x180006936  mov     [rsp+5D0h+var_5A0+8], r13d
0x18000693b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006940  test    eax, eax
0x180006942  jz      short loc_1800069C2
0x180006944  mov     eax, [rsp+5D0h+var_5A0+8]
0x180006948  test    eax, eax
0x18000694a  jz      short loc_1800069C2
0x18000694c  mov     [rsp+5D0h+var_5A8], eax
0x180006950  xor     r9d, r9d
0x180006953  mov     rax, qword ptr [rsp+5D0h+var_5A0]
0x180006958  mov     rdx, r14
0x18000695b  mov     rcx, rbx
0x18000695e  mov     [rsp+5D0h+var_5B0], rax
0x180006963  lea     r8d, [r9+0Ch]
0x180006967  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x18000696c  jmp     short loc_180006920
0x18000696e  mov     rdx, [rdi-18h]
0x180006972  lea     r8, aModule0xI64xWs; "Module(0x%I64x, %ws) callback returned "...
0x180006979  mov     rcx, [rbx+28h]
0x18000697d  mov     r9, [rdi-88h]
0x180006984  mov     [rsp+5D0h+var_5B0], rdx
0x180006989  mov     edx, 4
0x18000698e  mov     rax, [rcx]
0x180006991  mov     rax, [rax+8]
0x180006995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699a  mov     eax, 80004004h
0x18000699f  jmp     short loc_180006A0C
0x1800069a1  mov     rcx, [rbx+28h]
0x1800069a5  lea     r8, aThread0xXCallb; "Thread(0x%x) callback returned FALSE"
0x1800069ac  mov     r9d, [rdi]
0x1800069af  mov     edx, 4
0x1800069b4  mov     rax, [rcx]
0x1800069b7  mov     rax, [rax+8]
0x1800069bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c0  jmp     short loc_18000699A
0x1800069c2  mov     [rsp+5D0h+var_554], 9
0x1800069ca  mov     rcx, [rsi]
0x1800069cd  lea     r8, [rsp+5D0h+var_5A0]
0x1800069d2  mov     rax, [rbx+40h]
0x1800069d6  lea     rdx, [rsp+5D0h+var_560]
0x1800069db  mov     qword ptr [rsp+5D0h+var_5A0], r13
0x1800069e0  mov     [rsp+5D0h+var_5A0+8], r13d
0x1800069e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ea  test    eax, eax
0x1800069ec  jz      short loc_180006A0A
0x1800069ee  mov     r9d, [rsp+5D0h+var_5A0+8]; unsigned int
0x1800069f3  test    r9d, r9d
0x1800069f6  jz      short loc_180006A0A
0x1800069f8  mov     r8, qword ptr [rsp+5D0h+var_5A0]; unsigned __int64
0x1800069fd  mov     rdx, r14; struct _INTERNAL_PROCESS *
0x180006a00  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x180006a03  call    ?GenRemoveMemoryRange@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KK@Z; GenRemoveMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,ulong)
0x180006a08  jmp     short loc_1800069CA
0x180006a0a  xor     eax, eax
0x180006a0c  add     rsp, 598h
0x180006a13  pop     r15
0x180006a15  pop     r14
0x180006a17  pop     r13
0x180006a19  pop     r12
0x180006a1b  pop     rdi
0x180006a1c  pop     rsi
0x180006a1d  pop     rbx
0x180006a1e  pop     rbp
0x180006a1f  retn
```
