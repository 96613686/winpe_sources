# CLogState::AttemptWrite(_LOGRECHEADER *,CWriteMap &,int,int,ulong,ulong,_ULARGE_INTEGER *,ulong *)

- ea: `0x180009298`
- end: `0x180009554`
- name: `?AttemptWrite@CLogState@@QEAAKPEAU_LOGRECHEADER@@AEAVCWriteMap@@HHKKPEAT_ULARGE_INTEGER@@PEAK@Z`
- size: `700`
- prototype: `__int64 __fastcall(CLogState *this, struct _LOGRECHEADER *, struct CWriteMap *, unsigned int, int, unsigned int, unsigned int, union _ULARGE_INTEGER *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800084c8`
- `0x180008768`

## callees

- `0x180009298`
- `0x180009600`
- `0x180009754`
- `0x180009934`
- `0x18001266c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000949b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000949b`

## pseudocode

```c
__int64 __fastcall CLogState::AttemptWrite(
        CLogState *this,
        struct _LOGRECHEADER *a2,
        struct CWriteMap *a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        union _ULARGE_INTEGER *a8,
        unsigned int *a9)
{
  int v10; // ecx
  _WORD *v11; // r9
  int v14; // edx
  bool v15; // zf
  unsigned int v16; // edx
  BOOL v18; // r14d
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  _DWORD *v21; // rax
  DWORD *v22; // r15
  int v23; // ecx
  int v24; // r8d
  unsigned int v25; // eax
  union _ULARGE_INTEGER *v26; // rdi
  unsigned int v27; // eax
  int v28; // eax
  _DWORD v29[2]; // [rsp+30h] [rbp-28h] BYREF
  int v30; // [rsp+38h] [rbp-20h]
  int v31; // [rsp+3Ch] [rbp-1Ch]
  int v32; // [rsp+40h] [rbp-18h]
  __int64 v33; // [rsp+44h] [rbp-14h]
  int v34; // [rsp+4Ch] [rbp-Ch]
  unsigned int pExceptionObject; // [rsp+A8h] [rbp+50h] BYREF

  pExceptionObject = a4;
  v34 = 0;
  v10 = *((_DWORD *)this + 34);
  v11 = (_WORD *)((char *)a2 + 14);
  if ( v10 && *v11 == 1 )
  {
    pExceptionObject = -1073737699;
    throw &pExceptionObject;
  }
  *((_DWORD *)this + 5) = 0;
  v14 = *((_DWORD *)a3 + 6);
  v15 = v14 == -24;
  v16 = v14 + 24;
  pExceptionObject = v16;
  if ( v15 )
    return 0;
  v18 = *v11 == 4;
  if ( *v11 == 1 )
  {
    if ( v10 )
      v19 = a6;
    else
      v19 = a6 + *((_DWORD *)this + 33);
    v20 = v19 + *((_DWORD *)a3 + 18) + 8160;
  }
  else
  {
    v20 = *((_DWORD *)a3 + 18) + a6 + 24;
  }
  v21 = (_DWORD *)((char *)this + 104);
  if ( v20 > *((_DWORD *)this + 4) && *v21 )
  {
    *((_DWORD *)this + 34) = 1;
    pExceptionObject = -1073737699;
    throw &pExceptionObject;
  }
  if ( v16 > *((_DWORD *)this + 4) && *v21 )
  {
    pExceptionObject = -1073737699;
    throw &pExceptionObject;
  }
  v22 = a9;
  *a9 = *((_DWORD *)this + 7);
  *(_DWORD *)a2 = *((_DWORD *)this + 6);
  *((_DWORD *)this + 27) = *((_DWORD *)this + 6) & -*((_DWORD *)this + 20);
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 2);
  *((_DWORD *)this + 2) = *((_DWORD *)this + 6);
  v15 = *v11 == 3;
  *((_DWORD *)a2 + 2) = v16 - 24;
  v23 = *((_DWORD *)this + 7);
  v24 = v23;
  if ( v15 )
  {
    *((_DWORD *)this + 15) = *((_DWORD *)this + 6);
    *((_DWORD *)this + 16) = v23;
  }
  if ( *v11 == 4 )
  {
    v24 = v23;
    *((_DWORD *)this + 17) = *((_DWORD *)this + 6);
    *((_DWORD *)this + 18) = v23;
    *((_DWORD *)this + 5) = 1;
  }
  v15 = *((_DWORD *)this + 29) == 0;
  v29[0] = *((_DWORD *)this + 28);
  v30 = *((_DWORD *)this + 27);
  v31 = *((_DWORD *)this + 20);
  v29[1] = 0;
  v32 = v24;
  v33 = 0;
  if ( !v15 || v16 <= 0x1FE0 )
  {
    if ( (unsigned int)CLogState::_AllocateFromCurrent(this, a3, &pExceptionObject, (struct _RANGEENTRY *)v29, v18) )
      goto LABEL_27;
    if ( pExceptionObject <= 0x1FE0 )
    {
LABEL_26:
      CLogState::_AllocateFromCurrent(this, a3, &pExceptionObject, (struct _RANGEENTRY *)v29, v18);
      goto LABEL_27;
    }
  }
  if ( !(unsigned int)CLogState::_AllocatePages(this, a3, &pExceptionObject, (struct _RANGEENTRY *)v29)
    && (pExceptionObject <= 0x1FE0
     || !(unsigned int)CLogState::_AllocatePages(this, a3, &pExceptionObject, (struct _RANGEENTRY *)v29)) )
  {
    goto LABEL_26;
  }
LABEL_27:
  v25 = *((_DWORD *)this + 12);
  if ( *((_DWORD *)this + 2) < v25 && *((_DWORD *)this + 6) >= v25 )
  {
    pExceptionObject = -1073737699;
    throw &pExceptionObject;
  }
  v15 = v34 == 0;
  v26 = a8;
  a8->HighPart = *v22;
  v26->LowPart = *(_DWORD *)a2;
  if ( v15 )
  {
    v28 = *((_DWORD *)this + 28) + *((_DWORD *)this + 27) + 32;
  }
  else
  {
    v27 = v31 + v30;
    if ( *((_DWORD *)this + 26) && v27 >= *((_DWORD *)this + 14) )
      v27 = *(_DWORD *)this;
    if ( v27 == *(_DWORD *)this )
    {
      GetCurrentThreadId();
      CLogState::_DoWrapAround(this);
      v28 = *((_DWORD *)this + 6);
      goto LABEL_38;
    }
    v28 = v27 + 32;
  }
  *((_DWORD *)this + 6) = v28;
LABEL_38:
  *((_DWORD *)a2 + 5) = v28;
  if ( (*((_BYTE *)this + 24) & 7) != 0 || !v26->LowPart )
  {
    pExceptionObject = -1073737670;
    throw &pExceptionObject;
  }
  return *((unsigned int *)this + 4);
}

```

## disassembly

```asm
0x180009298  mov     [rsp-30h+pExceptionObject], r9d
0x18000929d  push    rbp
0x18000929e  push    rbx
0x18000929f  push    rsi
0x1800092a0  push    rdi
0x1800092a1  push    r14
0x1800092a3  push    r15
0x1800092a5  mov     rbp, rsp
0x1800092a8  sub     rsp, 58h
0x1800092ac  mov     rbx, rcx
0x1800092af  mov     [rbp+var_C], 0
0x1800092b6  mov     ecx, [rcx+88h]
0x1800092bc  lea     r9, [rdx+0Eh]
0x1800092c0  mov     rdi, r8
0x1800092c3  mov     rsi, rdx
0x1800092c6  mov     r10d, 1
0x1800092cc  test    ecx, ecx
0x1800092ce  jz      short loc_1800092DA
0x1800092d0  cmp     [r9], r10w
0x1800092d4  jz      loc_1800094ED
0x1800092da  mov     dword ptr [rbx+14h], 0
0x1800092e1  mov     edx, [r8+18h]
0x1800092e5  add     edx, 18h
0x1800092e8  mov     [rbp+pExceptionObject], edx
0x1800092eb  jnz     short loc_1800092FC
0x1800092ed  xor     eax, eax
0x1800092ef  add     rsp, 58h
0x1800092f3  pop     r15
0x1800092f5  pop     r14
0x1800092f7  pop     rdi
0x1800092f8  pop     rsi
0x1800092f9  pop     rbx
0x1800092fa  pop     rbp
0x1800092fb  retn
0x1800092fc  xor     r14d, r14d
0x1800092ff  cmp     word ptr [r9], 4
0x180009304  setz    r14b
0x180009308  cmp     [r9], r10w
0x18000930c  jnz     short loc_180009330
0x18000930e  test    ecx, ecx
0x180009310  jz      short loc_180009317
0x180009312  mov     ecx, [rbp+arg_28]
0x180009315  jmp     short loc_180009320
0x180009317  mov     ecx, [rbx+84h]
0x18000931d  add     ecx, [rbp+arg_28]
0x180009320  mov     r8d, [r8+48h]
0x180009324  add     r8d, 1FE0h
0x18000932b  add     r8d, ecx
0x18000932e  jmp     short loc_18000933C
0x180009330  mov     r8d, [rbp+arg_28]
0x180009334  add     r8d, 18h
0x180009338  add     r8d, [rdi+48h]
0x18000933c  lea     rax, [rbx+68h]
0x180009340  cmp     r8d, [rbx+10h]
0x180009344  jbe     short loc_18000934F
0x180009346  cmp     dword ptr [rax], 0
0x180009349  jnz     loc_180009505
0x18000934f  cmp     edx, [rbx+10h]
0x180009352  jbe     short loc_18000935D
0x180009354  cmp     dword ptr [rax], 0
0x180009357  jnz     loc_180009524
0x18000935d  mov     eax, [rbx+1Ch]
0x180009360  mov     r15, [rbp+arg_40]
0x180009364  mov     [r15], eax
0x180009367  mov     eax, [rbx+18h]
0x18000936a  mov     [rsi], eax
0x18000936c  mov     eax, [rbx+50h]
0x18000936f  neg     eax
0x180009371  and     eax, [rbx+18h]
0x180009374  mov     [rbx+6Ch], eax
0x180009377  mov     eax, [rbx+8]
0x18000937a  mov     [rsi+4], eax
0x18000937d  mov     eax, [rbx+18h]
0x180009380  mov     [rbx+8], eax
0x180009383  lea     eax, [rdx-18h]
0x180009386  cmp     word ptr [r9], 3
0x18000938b  mov     [rsi+8], eax
0x18000938e  mov     ecx, [rbx+1Ch]
0x180009391  mov     r8d, ecx
0x180009394  jnz     short loc_18000939F
0x180009396  mov     eax, [rbx+18h]
0x180009399  mov     [rbx+3Ch], eax
0x18000939c  mov     [rbx+40h], ecx
0x18000939f  cmp     word ptr [r9], 4
0x1800093a4  jnz     short loc_1800093B6
0x1800093a6  mov     eax, [rbx+18h]
0x1800093a9  mov     r8d, ecx
0x1800093ac  mov     [rbx+44h], eax
0x1800093af  mov     [rbx+48h], ecx
0x1800093b2  mov     [rbx+14h], r10d
0x1800093b6  cmp     dword ptr [rbx+74h], 0
0x1800093ba  mov     eax, [rbx+70h]
0x1800093bd  mov     [rbp+var_28], eax
0x1800093c0  mov     eax, [rbx+6Ch]
0x1800093c3  mov     [rbp+var_20], eax
0x1800093c6  mov     eax, [rbx+50h]
0x1800093c9  mov     [rbp+var_1C], eax
0x1800093cc  mov     [rbp+var_24], 0
0x1800093d3  mov     [rbp+var_18], r8d
0x1800093d7  mov     [rbp+var_14], 0
0x1800093df  jnz     short loc_1800093E9
0x1800093e1  cmp     edx, 1FE0h
0x1800093e7  ja      short loc_180009410
0x1800093e9  lea     r9, [rbp+var_28]; struct _RANGEENTRY *
0x1800093ed  mov     [rsp+58h+var_38], r14d; int
0x1800093f2  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x1800093f6  mov     rdx, rdi; struct CWriteMap *
0x1800093f9  mov     rcx, rbx; this
0x1800093fc  call    ?_AllocateFromCurrent@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@H@Z; CLogState::_AllocateFromCurrent(CWriteMap &,ulong *,_RANGEENTRY *,int)
0x180009401  test    eax, eax
0x180009403  jnz     short loc_18000945F
0x180009405  mov     edx, [rbp+pExceptionObject]
0x180009408  cmp     edx, 1FE0h
0x18000940e  jbe     short loc_180009447
0x180009410  lea     r9, [rbp+var_28]; struct _RANGEENTRY *
0x180009414  mov     rdx, rdi; struct CWriteMap *
0x180009417  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x18000941b  mov     rcx, rbx; this
0x18000941e  call    ?_AllocatePages@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@@Z; CLogState::_AllocatePages(CWriteMap &,ulong *,_RANGEENTRY *)
0x180009423  test    eax, eax
0x180009425  jnz     short loc_18000945F
0x180009427  cmp     [rbp+pExceptionObject], 1FE0h
0x18000942e  jbe     short loc_180009447
0x180009430  lea     r9, [rbp+var_28]; struct _RANGEENTRY *
0x180009434  mov     rdx, rdi; struct CWriteMap *
0x180009437  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x18000943b  mov     rcx, rbx; this
0x18000943e  call    ?_AllocatePages@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@@Z; CLogState::_AllocatePages(CWriteMap &,ulong *,_RANGEENTRY *)
0x180009443  test    eax, eax
0x180009445  jnz     short loc_18000945F
0x180009447  lea     r9, [rbp+var_28]; struct _RANGEENTRY *
0x18000944b  mov     [rsp+58h+var_38], r14d; int
0x180009450  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x180009454  mov     rdx, rdi; struct CWriteMap *
0x180009457  mov     rcx, rbx; this
0x18000945a  call    ?_AllocateFromCurrent@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@H@Z; CLogState::_AllocateFromCurrent(CWriteMap &,ulong *,_RANGEENTRY *,int)
0x18000945f  mov     eax, [rbx+30h]
0x180009462  cmp     [rbx+8], eax
0x180009465  jnb     short loc_180009470
0x180009467  cmp     [rbx+18h], eax
0x18000946a  jnb     loc_18000953C
0x180009470  cmp     [rbp+var_C], 0
0x180009474  mov     eax, [r15]
0x180009477  mov     rdi, [rbp+arg_38]
0x18000947b  mov     [rdi+4], eax
0x18000947e  mov     eax, [rsi]
0x180009480  mov     [rdi], eax
0x180009482  jz      short loc_1800094B3
0x180009484  mov     eax, [rbp+var_20]
0x180009487  add     eax, [rbp+var_1C]
0x18000948a  cmp     dword ptr [rbx+68h], 0
0x18000948e  jz      short loc_180009497
0x180009490  cmp     eax, [rbx+38h]
0x180009493  jb      short loc_180009497
0x180009495  mov     eax, [rbx]
0x180009497  cmp     eax, [rbx]
0x180009499  jnz     short loc_1800094AE
0x18000949b  call    cs:__imp_GetCurrentThreadId
0x1800094a1  mov     rcx, rbx; this
0x1800094a4  call    ?_DoWrapAround@CLogState@@AEAAXXZ; CLogState::_DoWrapAround(void)
0x1800094a9  mov     eax, [rbx+18h]
0x1800094ac  jmp     short loc_1800094BF
0x1800094ae  add     eax, 20h ; ' '
0x1800094b1  jmp     short loc_1800094BC
0x1800094b3  mov     eax, [rbx+6Ch]
0x1800094b6  add     eax, 20h ; ' '
0x1800094b9  add     eax, [rbx+70h]
0x1800094bc  mov     [rbx+18h], eax
0x1800094bf  mov     [rsi+14h], eax
0x1800094c2  test    byte ptr [rbx+18h], 7
0x1800094c6  jnz     short loc_1800094D5
0x1800094c8  cmp     dword ptr [rdi], 0
0x1800094cb  jz      short loc_1800094D5
0x1800094cd  mov     eax, [rbx+10h]
0x1800094d0  jmp     loc_1800092EF
0x1800094d5  lea     rdx, _TI1K; pThrowInfo
0x1800094dc  mov     [rbp+pExceptionObject], 0C000103Ah
0x1800094e3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800094e7  call    _CxxThrowException_0
0x1800094ed  lea     rdx, _TI1K; pThrowInfo
0x1800094f4  mov     [rbp+pExceptionObject], 0C000101Dh
0x1800094fb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800094ff  call    _CxxThrowException_0
0x180009505  lea     rdx, _TI1K; pThrowInfo
0x18000950c  mov     [rbx+88h], r10d
0x180009513  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009517  mov     [rbp+pExceptionObject], 0C000101Dh
0x18000951e  call    _CxxThrowException_0
0x180009524  lea     rdx, _TI1K; pThrowInfo
0x18000952b  mov     [rbp+pExceptionObject], 0C000101Dh
0x180009532  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009536  call    _CxxThrowException_0
0x18000953c  lea     rdx, _TI1K; pThrowInfo
0x180009543  mov     [rbp+pExceptionObject], 0C000101Dh
0x18000954a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000954e  call    _CxxThrowException_0
```
