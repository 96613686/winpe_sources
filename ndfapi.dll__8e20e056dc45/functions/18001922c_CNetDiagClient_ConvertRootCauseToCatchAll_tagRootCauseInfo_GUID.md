# CNetDiagClient::ConvertRootCauseToCatchAll(tagRootCauseInfo &,_GUID)

- ea: `0x18001922c`
- end: `0x18001958a`
- name: `?ConvertRootCauseToCatchAll@CNetDiagClient@@IEAAJAEAUtagRootCauseInfo@@U_GUID@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(CNetDiagClient *this, struct tagRootCauseInfo *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180018ed4`

## callees

- `0x180008b08`
- `0x18000f78c`
- `0x18001922c`
- `0x180019590`
- `0x18001f646`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180019381`
- `ole32!CoTaskMemAlloc` at `0x180019552`
- `ole32!CoTaskMemAlloc` at `0x180019381`
- `ole32!CoTaskMemAlloc` at `0x180019552`
- `ole32!CoTaskMemFree` at `0x18001936c`
- `ole32!CoTaskMemFree` at `0x18001952f`
- `ole32!CoTaskMemFree` at `0x18001936c`
- `ole32!CoTaskMemFree` at `0x18001952f`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ConvertRootCauseToCatchAll(
        CNetDiagClient *this,
        struct tagRootCauseInfo *a2,
        struct _GUID *a3)
{
  __int64 *v3; // rbx
  __int64 *v7; // r14
  __int64 *v8; // rdi
  __int64 *v9; // rsi
  __int64 v10; // rsi
  __int64 *i; // rax
  __int64 *v12; // rcx
  RepairInfoEx *pRepairs; // rdi
  unsigned int repairCount; // ebp
  unsigned int v15; // ebx
  RepairInfoEx *v16; // rax
  __int64 result; // rax
  __int64 *v18; // rbx
  __int64 *v19; // r14
  __int64 *v20; // rdi
  __int64 *v21; // rsi
  USHORT v22; // r8
  USHORT v23; // di
  RepairInfoEx *v24; // rcx
  const struct tagRepairInfo *v25; // rdx
  __int64 *j; // rax
  __int64 *v27; // rcx
  __int64 *v28; // rsi
  __int64 *v29; // rdi
  __int64 *v30; // rbx
  __int64 *v31; // rbx
  const unsigned __int16 *v32; // rdi
  unsigned __int64 v33; // rbx
  WCHAR *v34; // rax

  v3 = (__int64 *)*((_QWORD *)this + 12);
  v7 = v3;
  v8 = (__int64 *)v3[1];
  v9 = v8;
  while ( !*((_BYTE *)v9 + 25) )
  {
    if ( memcmp_0((char *)v9 + 28, a3, 0x10u) >= 0 )
    {
      if ( *((_BYTE *)v7 + 25) && memcmp_0(a3, (char *)v9 + 28, 0x10u) < 0 )
        v7 = v9;
      v3 = v9;
      v9 = (__int64 *)*v9;
    }
    else
    {
      v9 = (__int64 *)v9[2];
    }
  }
  if ( !*((_BYTE *)v7 + 25) )
    v8 = (__int64 *)*v7;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( memcmp_0(a3, (char *)v8 + 28, 0x10u) >= 0 )
    {
      v8 = (__int64 *)v8[2];
    }
    else
    {
      v7 = v8;
      v8 = (__int64 *)*v8;
    }
  }
  v10 = 0;
  while ( v3 != v7 )
  {
    ++v10;
    if ( !*((_BYTE *)v3 + 25) )
    {
      i = (__int64 *)v3[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v3 = i;
LABEL_26:
        v3 = i;
      }
      else
      {
        v12 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_26;
        do
        {
          v3 = v12;
          v12 = (__int64 *)*v12;
        }
        while ( !*((_BYTE *)v12 + 25) );
      }
    }
  }
  if ( !v10 )
    return 2147943568LL;
  pRepairs = a2->pRepairs;
  if ( pRepairs )
  {
    repairCount = a2->repairCount;
    if ( a2->repairCount )
    {
      v15 = 0;
      do
        FreeRepairInfos(&pRepairs[v15++].repair, 1u, 0);
      while ( v15 < repairCount );
      CoTaskMemFree(pRepairs);
    }
  }
  a2->pRepairs = 0;
  a2->repairCount = 0;
  v16 = (RepairInfoEx *)CoTaskMemAlloc(120 * v10);
  a2->pRepairs = v16;
  if ( !v16 )
    return 2147942414LL;
  v18 = (__int64 *)*((_QWORD *)this + 12);
  v19 = v18;
  v20 = (__int64 *)v18[1];
  v21 = v20;
  while ( !*((_BYTE *)v21 + 25) )
  {
    if ( memcmp_0((char *)v21 + 28, a3, 0x10u) >= 0 )
    {
      if ( *((_BYTE *)v19 + 25) && memcmp_0(a3, (char *)v21 + 28, 0x10u) < 0 )
        v19 = v21;
      v18 = v21;
      v21 = (__int64 *)*v21;
    }
    else
    {
      v21 = (__int64 *)v21[2];
    }
  }
  if ( !*((_BYTE *)v19 + 25) )
    v20 = (__int64 *)*v19;
  while ( !*((_BYTE *)v20 + 25) )
  {
    if ( memcmp_0(a3, (char *)v20 + 28, 0x10u) >= 0 )
    {
      v20 = (__int64 *)v20[2];
    }
    else
    {
      v19 = v20;
      v20 = (__int64 *)*v20;
    }
  }
  v22 = 0;
  while ( v18 != v19 )
  {
    v23 = v22 + 1;
    v24 = &a2->pRepairs[v22];
    v25 = (const struct tagRepairInfo *)((char *)this + 152 * *((int *)v18 + 11) + 168);
    v24->repairRank = v22 + 1;
    result = CopyRepairInfo(&v24->repair, v25);
    if ( (int)result < 0 )
      return result;
    v22 = v23;
    if ( !*((_BYTE *)v18 + 25) )
    {
      j = (__int64 *)v18[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( j = (__int64 *)v18[1]; !*((_BYTE *)j + 25) && v18 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v18 = j;
LABEL_61:
        v18 = j;
        continue;
      }
      v27 = (__int64 *)*j;
      if ( *(_BYTE *)(*j + 25) )
        goto LABEL_61;
      do
      {
        v18 = v27;
        v27 = (__int64 *)*v27;
      }
      while ( !*((_BYTE *)v27 + 25) );
    }
  }
  a2->rootCauseID = *a3;
  a2->repairCount = v22;
  v28 = (__int64 *)*((_QWORD *)this + 10);
  v29 = v28;
  v30 = (__int64 *)v28[1];
  if ( !*((_BYTE *)v30 + 25) )
  {
    do
    {
      if ( memcmp_0(v30 + 4, a3, 0x10u) >= 0 )
      {
        v29 = v30;
        v30 = (__int64 *)*v30;
      }
      else
      {
        v30 = (__int64 *)v30[2];
      }
    }
    while ( !*((_BYTE *)v30 + 25) );
    if ( v29 != v28 && memcmp_0(a3, v29 + 4, 0x10u) >= 0 )
    {
      v31 = v29 + 6;
      CoTaskMemFree(a2->pwszDescription);
      a2->pwszDescription = 0;
      if ( (unsigned __int64)v29[9] < 8 )
        v32 = (const unsigned __int16 *)(v29 + 6);
      else
        v32 = (const unsigned __int16 *)*v31;
      v33 = v31[2] + 1;
      v34 = (WCHAR *)CoTaskMemAlloc(2 * v33);
      a2->pwszDescription = v34;
      if ( v34 )
        return StringCchCopyW(v34, v33, v32);
      return 2147942414LL;
    }
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x18001922c  push    rbx
0x18001922e  push    rbp
0x18001922f  push    rsi
0x180019230  push    rdi
0x180019231  push    r12
0x180019233  push    r13
0x180019235  push    r14
0x180019237  push    r15
0x180019239  sub     rsp, 28h
0x18001923d  mov     rbx, [rcx+60h]
0x180019241  xor     ebp, ebp
0x180019243  mov     r12, r8
0x180019246  mov     r15, rdx
0x180019249  mov     r13, rcx
0x18001924c  mov     r14, rbx
0x18001924f  mov     rdi, [rbx+8]
0x180019253  mov     rsi, rdi
0x180019256  cmp     [rdi+19h], bpl
0x18001925a  jnz     short loc_1800192A5
0x18001925c  mov     r8d, 10h; Size
0x180019262  lea     rcx, [rsi+1Ch]; Buf1
0x180019266  mov     rdx, r12; Buf2
0x180019269  call    memcmp_0
0x18001926e  test    eax, eax
0x180019270  jns     short loc_180019278
0x180019272  mov     rsi, [rsi+10h]
0x180019276  jmp     short loc_18001929D
0x180019278  cmp     byte ptr [r14+19h], 0
0x18001927d  jz      short loc_180019297
0x18001927f  mov     r8d, 10h; Size
0x180019285  lea     rdx, [rsi+1Ch]; Buf2
0x180019289  mov     rcx, r12; Buf1
0x18001928c  call    memcmp_0
0x180019291  test    eax, eax
0x180019293  cmovs   r14, rsi
0x180019297  mov     rbx, rsi
0x18001929a  mov     rsi, [rsi]
0x18001929d  xor     ebp, ebp
0x18001929f  cmp     [rsi+19h], bpl
0x1800192a3  jz      short loc_18001925C
0x1800192a5  cmp     [r14+19h], bpl
0x1800192a9  jnz     short loc_1800192D2
0x1800192ab  mov     rdi, [r14]
0x1800192ae  jmp     short loc_1800192D2
0x1800192b0  lea     rdx, [rdi+1Ch]; Buf2
0x1800192b4  mov     r8d, 10h; Size
0x1800192ba  mov     rcx, r12; Buf1
0x1800192bd  call    memcmp_0
0x1800192c2  test    eax, eax
0x1800192c4  jns     short loc_1800192CE
0x1800192c6  mov     r14, rdi
0x1800192c9  mov     rdi, [rdi]
0x1800192cc  jmp     short loc_1800192D2
0x1800192ce  mov     rdi, [rdi+10h]
0x1800192d2  cmp     [rdi+19h], bpl
0x1800192d6  jz      short loc_1800192B0
0x1800192d8  mov     rsi, rbp
0x1800192db  mov     edx, 1; unsigned int
0x1800192e0  cmp     rbx, r14
0x1800192e3  jz      short loc_180019330
0x1800192e5  add     rsi, rdx
0x1800192e8  cmp     [rbx+19h], bpl
0x1800192ec  jnz     short loc_1800192E0
0x1800192ee  mov     rax, [rbx+10h]
0x1800192f2  cmp     [rax+19h], bpl
0x1800192f6  jnz     short loc_180019312
0x1800192f8  mov     rcx, [rax]
0x1800192fb  cmp     [rcx+19h], bpl
0x1800192ff  jnz     short loc_18001932B
0x180019301  mov     rax, [rcx]
0x180019304  mov     rbx, rcx
0x180019307  mov     rcx, rax
0x18001930a  cmp     [rax+19h], bpl
0x18001930e  jz      short loc_180019301
0x180019310  jmp     short loc_1800192E0
0x180019312  mov     rax, [rbx+8]
0x180019316  jmp     short loc_180019325
0x180019318  cmp     rbx, [rax+10h]
0x18001931c  jnz     short loc_18001932B
0x18001931e  mov     rbx, rax
0x180019321  mov     rax, [rax+8]
0x180019325  cmp     [rax+19h], bpl
0x180019329  jz      short loc_180019318
0x18001932b  mov     rbx, rax
0x18001932e  jmp     short loc_1800192E0
0x180019330  test    rsi, rsi
0x180019333  jz      loc_180019574
0x180019339  mov     rdi, [r15+30h]
0x18001933d  test    rdi, rdi
0x180019340  jz      short loc_180019374
0x180019342  movzx   ebp, word ptr [r15+38h]
0x180019347  test    ebp, ebp
0x180019349  jz      short loc_180019372
0x18001934b  xor     ebx, ebx
0x18001934d  mov     eax, ebx
0x18001934f  xor     r8d, r8d; int
0x180019352  imul    rcx, rax, 78h ; 'x'
0x180019356  add     rcx, rdi; pv
0x180019359  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18001935e  mov     edx, 1
0x180019363  add     ebx, edx
0x180019365  cmp     ebx, ebp
0x180019367  jb      short loc_18001934D
0x180019369  mov     rcx, rdi; pv
0x18001936c  call    cs:__imp_CoTaskMemFree
0x180019372  xor     ebp, ebp
0x180019374  imul    rcx, rsi, 78h ; 'x'; cb
0x180019378  mov     [r15+30h], rbp
0x18001937c  mov     [r15+38h], bp
0x180019381  call    cs:__imp_CoTaskMemAlloc
0x180019387  mov     [r15+30h], rax
0x18001938b  test    rax, rax
0x18001938e  jnz     short loc_18001939A
0x180019390  mov     eax, 8007000Eh
0x180019395  jmp     loc_180019579
0x18001939a  mov     rbx, [r13+60h]
0x18001939e  mov     r14, rbx
0x1800193a1  mov     rdi, [rbx+8]
0x1800193a5  mov     rsi, rdi
0x1800193a8  cmp     [rdi+19h], bpl
0x1800193ac  jnz     short loc_1800193F7
0x1800193ae  mov     r8d, 10h; Size
0x1800193b4  lea     rcx, [rsi+1Ch]; Buf1
0x1800193b8  mov     rdx, r12; Buf2
0x1800193bb  call    memcmp_0
0x1800193c0  test    eax, eax
0x1800193c2  jns     short loc_1800193CA
0x1800193c4  mov     rsi, [rsi+10h]
0x1800193c8  jmp     short loc_1800193EF
0x1800193ca  cmp     byte ptr [r14+19h], 0
0x1800193cf  jz      short loc_1800193E9
0x1800193d1  mov     r8d, 10h; Size
0x1800193d7  lea     rdx, [rsi+1Ch]; Buf2
0x1800193db  mov     rcx, r12; Buf1
0x1800193de  call    memcmp_0
0x1800193e3  test    eax, eax
0x1800193e5  cmovs   r14, rsi
0x1800193e9  mov     rbx, rsi
0x1800193ec  mov     rsi, [rsi]
0x1800193ef  xor     ebp, ebp
0x1800193f1  cmp     [rsi+19h], bpl
0x1800193f5  jz      short loc_1800193AE
0x1800193f7  cmp     [r14+19h], bpl
0x1800193fb  jnz     short loc_180019424
0x1800193fd  mov     rdi, [r14]
0x180019400  jmp     short loc_180019424
0x180019402  lea     rdx, [rdi+1Ch]; Buf2
0x180019406  mov     r8d, 10h; Size
0x18001940c  mov     rcx, r12; Buf1
0x18001940f  call    memcmp_0
0x180019414  test    eax, eax
0x180019416  jns     short loc_180019420
0x180019418  mov     r14, rdi
0x18001941b  mov     rdi, [rdi]
0x18001941e  jmp     short loc_180019424
0x180019420  mov     rdi, [rdi+10h]
0x180019424  cmp     [rdi+19h], bpl
0x180019428  jz      short loc_180019402
0x18001942a  mov     r8d, ebp
0x18001942d  mov     esi, 1
0x180019432  cmp     rbx, r14
0x180019435  jz      loc_1800194C0
0x18001943b  movsxd  rax, dword ptr [rbx+2Ch]
0x18001943f  lea     edi, [rsi+r8]
0x180019443  imul    rdx, rax, 98h
0x18001944a  movzx   eax, r8w
0x18001944e  imul    rcx, rax, 78h ; 'x'
0x180019452  add     rdx, 0A8h
0x180019459  add     rcx, [r15+30h]; struct tagRepairInfo *
0x18001945d  add     rdx, r13; struct tagRepairInfo *
0x180019460  mov     [rcx+70h], di
0x180019464  call    ?CopyRepairInfo@@YAJPEAUtagRepairInfo@@PEBU1@@Z; CopyRepairInfo(tagRepairInfo *,tagRepairInfo const *)
0x180019469  test    eax, eax
0x18001946b  js      loc_180019579
0x180019471  movzx   r8d, di
0x180019475  cmp     [rbx+19h], bpl
0x180019479  jnz     short loc_180019432
0x18001947b  mov     rax, [rbx+10h]
0x18001947f  cmp     [rax+19h], bpl
0x180019483  jnz     short loc_18001949F
0x180019485  mov     rcx, [rax]
0x180019488  cmp     [rcx+19h], bpl
0x18001948c  jnz     short loc_1800194B8
0x18001948e  mov     rax, [rcx]
0x180019491  mov     rbx, rcx
0x180019494  mov     rcx, rax
0x180019497  cmp     [rax+19h], bpl
0x18001949b  jz      short loc_18001948E
0x18001949d  jmp     short loc_180019432
0x18001949f  mov     rax, [rbx+8]
0x1800194a3  jmp     short loc_1800194B2
0x1800194a5  cmp     rbx, [rax+10h]
0x1800194a9  jnz     short loc_1800194B8
0x1800194ab  mov     rbx, rax
0x1800194ae  mov     rax, [rax+8]
0x1800194b2  cmp     [rax+19h], bpl
0x1800194b6  jz      short loc_1800194A5
0x1800194b8  mov     rbx, rax
0x1800194bb  jmp     loc_180019432
0x1800194c0  movaps  xmm0, xmmword ptr [r12]
0x1800194c5  movdqu  xmmword ptr [r15+8], xmm0
0x1800194cb  mov     [r15+38h], r8w
0x1800194d0  mov     rsi, [r13+50h]
0x1800194d4  mov     rdi, rsi
0x1800194d7  mov     rbx, [rsi+8]
0x1800194db  cmp     [rbx+19h], bpl
0x1800194df  jnz     loc_180019574
0x1800194e5  mov     r14d, 10h
0x1800194eb  lea     rcx, [rbx+20h]; Buf1
0x1800194ef  mov     r8, r14; Size
0x1800194f2  mov     rdx, r12; Buf2
0x1800194f5  call    memcmp_0
0x1800194fa  test    eax, eax
0x1800194fc  jns     short loc_180019504
0x1800194fe  mov     rbx, [rbx+10h]
0x180019502  jmp     short loc_18001950A
0x180019504  mov     rdi, rbx
0x180019507  mov     rbx, [rbx]
0x18001950a  cmp     [rbx+19h], bpl
0x18001950e  jz      short loc_1800194EB
0x180019510  cmp     rdi, rsi
0x180019513  jz      short loc_180019574
0x180019515  lea     rdx, [rdi+20h]; Buf2
0x180019519  mov     r8, r14; Size
0x18001951c  mov     rcx, r12; Buf1
0x18001951f  call    memcmp_0
0x180019524  test    eax, eax
0x180019526  js      short loc_180019574
0x180019528  mov     rcx, [r15]; pv
0x18001952b  lea     rbx, [rdi+30h]
0x18001952f  call    cs:__imp_CoTaskMemFree
0x180019535  mov     [r15], rbp
0x180019538  cmp     qword ptr [rbx+18h], 8
0x18001953d  jb      short loc_180019544
0x18001953f  mov     rdi, [rbx]
0x180019542  jmp     short loc_180019547
0x180019544  mov     rdi, rbx
0x180019547  mov     rbx, [rbx+10h]
0x18001954b  inc     rbx
0x18001954e  lea     rcx, [rbx+rbx]; cb
0x180019552  call    cs:__imp_CoTaskMemAlloc
0x180019558  mov     [r15], rax
0x18001955b  test    rax, rax
0x18001955e  jz      loc_180019390
0x180019564  mov     r8, rdi; unsigned __int16 *
0x180019567  mov     rdx, rbx; unsigned __int64
0x18001956a  mov     rcx, rax; unsigned __int16 *
0x18001956d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019572  jmp     short loc_180019579
0x180019574  mov     eax, 80070490h
0x180019579  add     rsp, 28h
0x18001957d  pop     r15
0x18001957f  pop     r14
0x180019581  pop     r13
0x180019583  pop     r12
0x180019585  pop     rdi
0x180019586  pop     rsi
0x180019587  pop     rbp
0x180019588  pop     rbx
0x180019589  retn
```
