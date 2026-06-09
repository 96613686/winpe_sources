# CPropertySymbolCache::_HrOpenSymbolWithLockOption(char const *,int,tagPROPSYMBOL * *,int)

- ea: `0x18000b270`
- end: `0x18000b728`
- name: `?_HrOpenSymbolWithLockOption@CPropertySymbolCache@@AEAAJPEBDHPEAPEAUtagPROPSYMBOL@@H@Z`
- size: `1208`
- prototype: `__int64 __usercall@<rax>(CPropertySymbolCache *__hidden this@<rcx>, const char *@<rdx>, int@<r8d>, struct tagPROPSYMBOL **@<r9>, int)`
- caller_count: `28`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180009198`
- `0x1800099bc`
- `0x180009e60`
- `0x18000a200`
- `0x18000ba28`
- `0x18001e72c`
- `0x180020ab8`
- `0x180023258`
- `0x180032970`
- `0x1800329d0`
- `0x180032b10`
- `0x180032c10`
- `0x180032ce0`
- `0x18004e90c`
- `0x1800525d0`
- `0x180052880`
- `0x180052fe0`
- `0x1800535a0`
- `0x180053df0`
- `0x18005403c`
- `0x1800540d0`
- `0x180054da0`
- `0x180055930`
- `0x180055cd4`
- `0x180055d80`
- `0x180055ea0`
- `0x180056e94`
- `0x180061ef4`

## callees

- `0x18000b270`
- `0x18000d350`
- `0x18000ddf4`
- `0x18000de4c`
- `0x1800124a0`
- `0x180019dd8`
- `0x180019f98`
- `0x18001fee4`
- `0x180020ab8`
- `0x1800cc9a2`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!StrCmpNIA` at `0x18000b472`
- `SHLWAPI!StrCmpNIA` at `0x18000b472`
- `KERNEL32!WaitForSingleObject` at `0x18000b5af`
- `KERNEL32!WaitForSingleObject` at `0x18000b5af`
- `KERNEL32!ReleaseSemaphore` at `0x18000b71d`
- `KERNEL32!ReleaseSemaphore` at `0x18000b71d`
- `KERNEL32!CompareStringA` at `0x18000b457`
- `KERNEL32!CompareStringA` at `0x18000b457`

## pseudocode

```c
__int64 __fastcall CPropertySymbolCache::_HrOpenSymbolWithLockOption(
        CPropertySymbolCache *this,
        const char *a2,
        int a3,
        struct tagPROPSYMBOL **a4,
        int a5)
{
  int v8; // r13d
  unsigned int v9; // r15d
  int v10; // r11d
  int v11; // r10d
  const char *v12; // r8
  __int64 v13; // rbp
  struct tagPROPSYMBOL *v14; // rbx
  _BYTE *v15; // r9
  __int64 v16; // rax
  unsigned __int8 v17; // dl
  __int64 v18; // rax
  unsigned int v20; // eax
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rbx
  unsigned int v23; // r8d
  int v24; // ebp
  unsigned int v25; // eax
  const char *v26; // rcx
  __int64 v27; // rdx
  unsigned __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // r8d
  int v31; // r8d
  CPropertySymbolCache *v32; // rcx
  unsigned int v33; // edx
  __int64 v34; // rax
  __int64 v35; // r14
  void *v36; // rax
  int lpString2; // [rsp+20h] [rbp-58h]
  int v38; // [rsp+30h] [rbp-48h]
  struct tagPROPSYMBOL *v39; // [rsp+38h] [rbp-40h] BYREF
  int PreviousCount; // [rsp+88h] [rbp+10h] BYREF
  int v41; // [rsp+90h] [rbp+18h]

  v41 = a3;
  v39 = 0;
  if ( !a2 || !a4 )
    return 2147942487LL;
  v8 = a5;
  v9 = 0;
  PreviousCount = 0;
  v38 = 0;
  *a4 = 0;
  if ( v8 == 1 && _InterlockedAdd((volatile signed __int32 *)this + 168, 1u) <= 0 )
  {
    WaitForSingleObject(*((HANDLE *)this + 91), 0xFFFFFFFF);
    a3 = v41;
  }
  if ( WORD1(a2) )
  {
    v10 = 0;
    v11 = *((_DWORD *)this + 6) - 1;
    while ( 1 )
    {
LABEL_8:
      if ( v10 > v11 )
      {
        a3 = v41;
        goto LABEL_27;
      }
      v12 = a2;
      v13 = (v10 + v11) / 2;
      v14 = *(struct tagPROPSYMBOL **)(*((_QWORD *)this + 4)
                                     + 8LL * *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8 * v13) + 28LL));
      v15 = *(_BYTE **)v14;
      if ( *(_QWORD *)v14 )
        break;
LABEL_15:
      v10 = v13 + 1;
    }
    while ( 1 )
    {
      v16 = *(unsigned __int8 *)v12;
      if ( !(_BYTE)v16 && !*v15 )
        break;
      v17 = *((_BYTE *)&g_achOEMtoupper + v16);
      v18 = (unsigned __int8)*v15;
      if ( v17 < *((_BYTE *)&g_achOEMtoupper + v18) )
      {
        v11 = v13 - 1;
        goto LABEL_8;
      }
      if ( v17 > *((_BYTE *)&g_achOEMtoupper + v18) )
        goto LABEL_15;
      ++v12;
      ++v15;
    }
    a3 = v41;
  }
  else
  {
    v20 = (unsigned __int16)a2 - 2;
    if ( v20 > 0x4C )
    {
      if ( v20 < *((_DWORD *)this + 4) || v20 >= *((_DWORD *)this + 6) )
        goto LABEL_27;
      v14 = *(struct tagPROPSYMBOL **)(*((_QWORD *)this + 4) + 8LL * v20);
    }
    else
    {
      v14 = (struct tagPROPSYMBOL *)*((_QWORD *)this + (unsigned int)a2 + 5);
    }
  }
  if ( v14 )
  {
    *a4 = v14;
LABEL_23:
    if ( v8 != 1 )
      return v9;
    v21 = (volatile signed __int32 *)((char *)this + 672);
    if ( v38 != 1 )
    {
      if ( _InterlockedDecrement(v21) < 0 )
      {
        PreviousCount = _InterlockedIncrement(v21);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 169, 0xFFFFFFFF) == 1 )
          ReleaseSemaphore(*((HANDLE *)this + 90), 1, &PreviousCount);
      }
      return v9;
    }
LABEL_53:
    CExShareLock::ExclusiveUnlock((CExShareLock *)v21);
    return v9;
  }
LABEL_27:
  if ( !a3 || !WORD1(a2) )
  {
    v9 = -2146644475;
    goto LABEL_23;
  }
  if ( v8 == 1 )
  {
    v21 = (volatile signed __int32 *)((char *)this + 672);
    v38 = 1;
    CExShareLock::ShareUnlock((CPropertySymbolCache *)((char *)this + 672));
    CExShareLock::ExclusiveLock((CPropertySymbolCache *)((char *)this + 672));
    if ( (int)CPropertySymbolCache::_HrFindSymbol(this, a2, a4) >= 0 )
      goto LABEL_53;
  }
  v22 = -1;
  do
    ++v22;
  while ( a2[v22] );
  if ( CompareStringA(0x7Fu, 1u, a2, 4, "par:", 4) == 2 )
  {
    PreviousCount = CPropertySymbolCache::_HrGetParameterLinkSymbolWithLockOption(this, a2, v23, &v39, lpString2);
    v9 = PreviousCount;
    if ( PreviousCount < 0 )
      goto LABEL_23;
    v24 = 0x20000000;
  }
  else if ( StrCmpNIA(a2, "att:", 4) )
  {
    v24 = 0x10000000;
    v26 = a2;
    v27 = 0x400400100002600LL;
    while ( 1 )
    {
      v28 = *v26;
      if ( !(_BYTE)v28 )
        break;
      if ( (unsigned __int8)v28 <= 0x3Au && _bittest64(&v27, v28) )
      {
        v9 = -2146644447;
        goto LABEL_23;
      }
      ++v26;
    }
  }
  else
  {
    v24 = 0x40000000;
  }
  v25 = *((_DWORD *)this + 6);
  if ( v25 + 1 >= v25 )
  {
    v33 = *((_DWORD *)this + 7);
    if ( v25 + 1 > v33 )
    {
      if ( v33 > 0x1FFFFFF5 )
        return 2147942414LL;
      PreviousCount = HrRealloc((void **)this + 4, 8 * v33 + 80);
      v9 = PreviousCount;
      if ( PreviousCount < 0 )
        goto LABEL_23;
      *((_DWORD *)this + 7) += 10;
    }
    v34 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 56);
    v35 = v34;
    if ( !v34 )
    {
      v9 = -2147024882;
      goto LABEL_23;
    }
    *(_OWORD *)v34 = 0;
    *(_OWORD *)(v34 + 16) = 0;
    *(_OWORD *)(v34 + 32) = 0;
    *(_QWORD *)(v34 + 48) = 0;
    v36 = (void *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(
                    g_pMalloc,
                    (unsigned int)(v22 + 1));
    *(_QWORD *)v35 = v36;
    if ( v36 )
    {
      memcpy_0(v36, a2, (unsigned int)(v22 + 1));
      *(_DWORD *)(v35 + 8) = v22;
      *(_DWORD *)(v35 + 16) = v24;
      *(_DWORD *)(v35 + 28) = *((_DWORD *)this + 6);
      v29 = *((_DWORD *)this + 6) + 1;
      *(_WORD *)(v35 + 36) = 30;
      *(_DWORD *)(v35 + 32) = v29;
      *(_DWORD *)(v35 + 20) = 0;
      *(_QWORD *)(v35 + 40) = v39;
      v30 = *((_DWORD *)this + 3);
      *((_DWORD *)this + 3) = v30 + 1;
      *(_DWORD *)(v35 + 12) = v30;
      *(_WORD *)(v35 + 24) = v30 % 0x19;
      *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * *((unsigned int *)this + 6)) = v35;
      v31 = *((_DWORD *)this + 6);
      *((_DWORD *)this + 6) = v31 + 1;
      CPropertySymbolCache::_SortTableElements(this, 0, v31);
      *a4 = (struct tagPROPSYMBOL *)v35;
      v9 = PreviousCount;
      if ( PreviousCount >= 0 )
        goto LABEL_23;
    }
    else
    {
      v9 = -2147024882;
    }
    CPropertySymbolCache::_FreeSymbol(v32, (struct tagPROPSYMBOL *)v35);
    goto LABEL_23;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000b270  mov     [rsp+arg_10], r8d
0x18000b275  push    rsi
0x18000b276  push    rdi
0x18000b277  push    r12
0x18000b279  sub     rsp, 60h
0x18000b27d  xor     eax, eax
0x18000b27f  mov     r12, r9
0x18000b282  mov     [rsp+78h+var_40], rax
0x18000b287  mov     rdi, rdx
0x18000b28a  mov     rsi, rcx
0x18000b28d  test    rdx, rdx
0x18000b290  jz      loc_18000B38B
0x18000b296  test    r9, r9
0x18000b299  jz      loc_18000B38B
0x18000b29f  mov     [rsp+78h+var_20], rbp
0x18000b2a4  mov     [rsp+78h+var_28], r13
0x18000b2a9  mov     r13d, [rsp+78h+arg_20]
0x18000b2b1  mov     [rsp+78h+var_30], r14
0x18000b2b6  mov     [rsp+78h+var_38], r15
0x18000b2bb  mov     r15d, eax
0x18000b2be  mov     [rsp+78h+PreviousCount], eax
0x18000b2c5  mov     [rsp+78h+var_48], eax
0x18000b2c9  mov     [r9], rax
0x18000b2cc  cmp     r13d, 1
0x18000b2d0  jnz     short loc_18000B2E0
0x18000b2d2  lock add [rcx+2A0h], r13d
0x18000b2da  jle     loc_18000B5A3
0x18000b2e0  mov     r14, rdi
0x18000b2e3  mov     [rsp+78h+arg_0], rbx
0x18000b2eb  shr     r14, 10h
0x18000b2ef  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000b2f6  test    r14w, r14w
0x18000b2fa  jz      loc_18000B399
0x18000b300  mov     r10d, [rsi+18h]
0x18000b304  mov     r11d, eax
0x18000b307  dec     r10d
0x18000b30a  cmp     r11d, r10d
0x18000b30d  jg      loc_18000B5E5
0x18000b313  lea     eax, [r11+r10]
0x18000b317  mov     r8, rdi
0x18000b31a  cdq
0x18000b31b  sub     eax, edx
0x18000b31d  mov     rdx, [rsi+20h]
0x18000b321  sar     eax, 1
0x18000b323  movsxd  rbp, eax
0x18000b326  mov     rcx, [rdx+rbp*8]
0x18000b32a  mov     eax, [rcx+1Ch]
0x18000b32d  mov     rbx, [rdx+rax*8]
0x18000b331  mov     r9, [rbx]
0x18000b334  test    r9, r9
0x18000b337  jz      short loc_18000B36F
0x18000b339  movzx   eax, byte ptr [r8]
0x18000b33d  test    al, al
0x18000b33f  jz      short loc_18000B375
0x18000b341  mov     rcx, rax
0x18000b344  lea     rax, ?g_achOEMtoupper@@3PAEA; uchar near * g_achOEMtoupper
0x18000b34b  movzx   edx, byte ptr [rcx+rax]
0x18000b34f  lea     rcx, ?g_achOEMtoupper@@3PAEA; uchar near * g_achOEMtoupper
0x18000b356  movzx   eax, byte ptr [r9]
0x18000b35a  cmp     dl, [rax+rcx]
0x18000b35d  jb      short loc_18000B369
0x18000b35f  ja      short loc_18000B36F
0x18000b361  inc     r8
0x18000b364  inc     r9
0x18000b367  jmp     short loc_18000B339
0x18000b369  lea     r10d, [rbp-1]
0x18000b36d  jmp     short loc_18000B30A
0x18000b36f  lea     r11d, [rbp+1]
0x18000b373  jmp     short loc_18000B30A
0x18000b375  cmp     [r9], r15b
0x18000b378  jnz     short loc_18000B341
0x18000b37a  mov     r8d, [rsp+78h+arg_10]
0x18000b382  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000b389  jmp     short loc_18000B3AC
0x18000b38b  mov     eax, 80070057h
0x18000b390  add     rsp, 60h
0x18000b394  pop     r12
0x18000b396  pop     rdi
0x18000b397  pop     rsi
0x18000b398  retn
0x18000b399  lea     eax, [rdi-2]
0x18000b39c  cmp     eax, 4Ch ; 'L'
0x18000b39f  ja      loc_18000B5C4
0x18000b3a5  mov     eax, edi
0x18000b3a7  mov     rbx, [rsi+rax*8+28h]
0x18000b3ac  test    rbx, rbx
0x18000b3af  jz      short loc_18000B40B
0x18000b3b1  mov     [r12], rbx
0x18000b3b5  cmp     r13d, 1
0x18000b3b9  jnz     short loc_18000B3E3
0x18000b3bb  lea     rbx, [rsi+2A0h]
0x18000b3c2  cmp     [rsp+78h+var_48], r13d
0x18000b3c7  jz      loc_18000B62E
0x18000b3cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b3d4  mov     eax, ecx
0x18000b3d6  lock xadd [rbx], eax
0x18000b3da  cmp     eax, r13d
0x18000b3dd  js      loc_18000B6EF
0x18000b3e3  mov     eax, r15d
0x18000b3e6  mov     rbx, [rsp+78h+arg_0]
0x18000b3ee  mov     r13, [rsp+78h+var_28]
0x18000b3f3  mov     rbp, [rsp+78h+var_20]
0x18000b3f8  mov     r14, [rsp+78h+var_30]
0x18000b3fd  mov     r15, [rsp+78h+var_38]
0x18000b402  add     rsp, 60h
0x18000b406  pop     r12
0x18000b408  pop     rdi
0x18000b409  pop     rsi
0x18000b40a  retn
0x18000b40b  test    r8d, r8d
0x18000b40e  jz      loc_18000B499
0x18000b414  test    r14w, r14w
0x18000b418  jz      short loc_18000B499
0x18000b41a  cmp     r13d, 1
0x18000b41e  jz      loc_18000B5F9
0x18000b424  mov     rbx, rbp
0x18000b427  inc     rbx
0x18000b42a  cmp     [rdi+rbx], r15b
0x18000b42e  jnz     short loc_18000B427
0x18000b430  lea     rax, aPar; "par:"
0x18000b437  mov     [rsp+78h+cchCount2], 4; cchCount2
0x18000b43f  mov     r9d, 4; cchCount1
0x18000b445  mov     [rsp+78h+lpString2], rax; int
0x18000b44a  mov     r8, rdi; lpString1
0x18000b44d  mov     edx, 1; dwCmpFlags
0x18000b452  mov     ecx, 7Fh; Locale
0x18000b457  call    cs:__imp_CompareStringA
0x18000b45d  cmp     eax, 2
0x18000b460  jz      short loc_18000B4A4
0x18000b462  mov     r8d, 4; nChar
0x18000b468  lea     rdx, aAtt; "att:"
0x18000b46f  mov     rcx, rdi; psz1
0x18000b472  call    cs:__imp_StrCmpNIA
0x18000b478  test    eax, eax
0x18000b47a  jnz     short loc_18000B4CD
0x18000b47c  mov     ebp, 40000000h
0x18000b481  mov     eax, [rsi+18h]
0x18000b484  lea     ecx, [rax+1]
0x18000b487  cmp     ecx, eax
0x18000b489  jnb     loc_18000B63B
0x18000b48f  mov     eax, 8007000Eh
0x18000b494  jmp     loc_18000B3E6
0x18000b499  mov     r15d, 800CCE05h
0x18000b49f  jmp     loc_18000B3B5
0x18000b4a4  lea     r9, [rsp+78h+var_40]; struct tagPROPSYMBOL **
0x18000b4a9  mov     rdx, rdi; char *
0x18000b4ac  mov     rcx, rsi; this
0x18000b4af  call    ?_HrGetParameterLinkSymbolWithLockOption@CPropertySymbolCache@@AEAAJPEBDKPEAPEAUtagPROPSYMBOL@@H@Z; CPropertySymbolCache::_HrGetParameterLinkSymbolWithLockOption(char const *,ulong,tagPROPSYMBOL * *,int)
0x18000b4b4  mov     [rsp+78h+PreviousCount], eax
0x18000b4bb  mov     r15d, eax
0x18000b4be  test    eax, eax
0x18000b4c0  js      loc_18000B3B5
0x18000b4c6  mov     ebp, 20000000h
0x18000b4cb  jmp     short loc_18000B481
0x18000b4cd  mov     ebp, 10000000h
0x18000b4d2  mov     rcx, rdi
0x18000b4d5  mov     rdx, 400400100002600h
0x18000b4df  nop
0x18000b4e0  movsx   rax, byte ptr [rcx]
0x18000b4e4  test    al, al
0x18000b4e6  jz      short loc_18000B481
0x18000b4e8  cmp     al, 3Ah ; ':'
0x18000b4ea  ja      short loc_18000B4F2
0x18000b4ec  bt      rdx, rax
0x18000b4f0  jb      short loc_18000B4F7
0x18000b4f2  inc     rcx
0x18000b4f5  jmp     short loc_18000B4E0
0x18000b4f7  mov     r15d, 800CCE21h
0x18000b4fd  jmp     loc_18000B3B5
0x18000b502  mov     r8, r15; Size
0x18000b505  mov     rdx, rdi; Src
0x18000b508  mov     rcx, rax; void *
0x18000b50b  call    memcpy_0
0x18000b510  mov     [r14+8], ebx
0x18000b514  mov     [r14+10h], ebp
0x18000b518  mov     eax, [rsi+18h]
0x18000b51b  mov     [r14+1Ch], eax
0x18000b51f  mov     eax, [rsi+18h]
0x18000b522  inc     eax
0x18000b524  mov     word ptr [r14+24h], 1Eh
0x18000b52b  mov     [r14+20h], eax
0x18000b52f  mov     dword ptr [r14+14h], 0
0x18000b537  mov     rax, [rsp+78h+var_40]
0x18000b53c  mov     [r14+28h], rax
0x18000b540  mov     r8d, [rsi+0Ch]
0x18000b544  lea     eax, [r8+1]
0x18000b548  mov     [rsi+0Ch], eax
0x18000b54b  mov     eax, 51EB851Fh
0x18000b550  mul     r8d
0x18000b553  mov     [r14+0Ch], r8d
0x18000b557  shr     edx, 3
0x18000b55a  movzx   eax, dx
0x18000b55d  xor     edx, edx; int
0x18000b55f  imul    ecx, eax, 19h
0x18000b562  sub     r8w, cx
0x18000b566  mov     [r14+18h], r8w
0x18000b56b  mov     ecx, [rsi+18h]
0x18000b56e  mov     rax, [rsi+20h]
0x18000b572  mov     [rax+rcx*8], r14
0x18000b576  mov     rcx, rsi; this
0x18000b579  mov     r8d, [rsi+18h]; int
0x18000b57d  lea     eax, [r8+1]
0x18000b581  mov     [rsi+18h], eax
0x18000b584  call    ?_SortTableElements@CPropertySymbolCache@@AEAAXJJ@Z; CPropertySymbolCache::_SortTableElements(long,long)
0x18000b589  mov     [r12], r14
0x18000b58d  mov     r15d, [rsp+78h+PreviousCount]
0x18000b595  test    r15d, r15d
0x18000b598  jns     loc_18000B3B5
0x18000b59e  jmp     loc_18000B6E2
0x18000b5a3  mov     rcx, [rcx+2D8h]; hHandle
0x18000b5aa  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000b5af  call    cs:__imp_WaitForSingleObject
0x18000b5b5  mov     r8d, [rsp+78h+arg_10]
0x18000b5bd  xor     eax, eax
0x18000b5bf  jmp     loc_18000B2E0
0x18000b5c4  cmp     eax, [rsi+10h]
0x18000b5c7  jb      loc_18000B40B
0x18000b5cd  cmp     eax, [rsi+18h]
0x18000b5d0  jnb     loc_18000B40B
0x18000b5d6  mov     ecx, eax
0x18000b5d8  mov     rax, [rsi+20h]
0x18000b5dc  mov     rbx, [rax+rcx*8]
0x18000b5e0  jmp     loc_18000B3AC
0x18000b5e5  mov     r8d, [rsp+78h+arg_10]
0x18000b5ed  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000b5f4  jmp     loc_18000B40B
0x18000b5f9  lea     rbx, [rsi+2A0h]
0x18000b600  mov     [rsp+78h+var_48], 1
0x18000b608  mov     rcx, rbx; this
0x18000b60b  call    ?ShareUnlock@CExShareLock@@QEAAXXZ; CExShareLock::ShareUnlock(void)
0x18000b610  mov     rcx, rbx; this
0x18000b613  call    ?ExclusiveLock@CExShareLock@@QEAAXXZ; CExShareLock::ExclusiveLock(void)
0x18000b618  mov     r8, r12; struct tagPROPSYMBOL **
0x18000b61b  mov     rdx, rdi; char *
0x18000b61e  mov     rcx, rsi; this
0x18000b621  call    ?_HrFindSymbol@CPropertySymbolCache@@AEAAJPEBDPEAPEAUtagPROPSYMBOL@@@Z; CPropertySymbolCache::_HrFindSymbol(char const *,tagPROPSYMBOL * *)
0x18000b626  test    eax, eax
0x18000b628  js      loc_18000B424
0x18000b62e  mov     rcx, rbx; this
0x18000b631  call    ?ExclusiveUnlock@CExShareLock@@QEAAXXZ; CExShareLock::ExclusiveUnlock(void)
0x18000b636  jmp     loc_18000B3E3
0x18000b63b  mov     edx, [rsi+1Ch]
0x18000b63e  cmp     ecx, edx
0x18000b640  jbe     short loc_18000B674
0x18000b642  cmp     edx, 1FFFFFF5h
0x18000b648  ja      loc_18000B48F
0x18000b64e  lea     edx, ds:50h[rdx*8]; unsigned int
0x18000b655  lea     rcx, [rsi+20h]; void **
0x18000b659  call    ?HrRealloc@@YAJPEAPEAXK@Z; HrRealloc(void * *,ulong)
0x18000b65e  mov     [rsp+78h+PreviousCount], eax
0x18000b665  mov     r15d, eax
0x18000b668  test    eax, eax
0x18000b66a  js      loc_18000B3B5
0x18000b670  add     dword ptr [rsi+1Ch], 0Ah
0x18000b674  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000b67b  mov     edx, 38h ; '8'
0x18000b680  mov     rax, [rcx]
0x18000b683  mov     rax, [rax+18h]
0x18000b687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b68c  mov     r14, rax
0x18000b68f  test    rax, rax
0x18000b692  jnz     short loc_18000B69F
0x18000b694  mov     r15d, 8007000Eh
0x18000b69a  jmp     loc_18000B3B5
0x18000b69f  xorps   xmm0, xmm0
0x18000b6a2  lea     r15d, [rbx+1]
0x18000b6a6  movups  xmmword ptr [r14], xmm0
0x18000b6aa  xor     eax, eax
0x18000b6ac  mov     edx, r15d
0x18000b6af  movups  xmmword ptr [r14+10h], xmm0
0x18000b6b4  movups  xmmword ptr [r14+20h], xmm0
0x18000b6b9  mov     [r14+30h], rax
0x18000b6bd  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000b6c4  mov     rax, [rcx]
0x18000b6c7  mov     rax, [rax+18h]
0x18000b6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d0  mov     [r14], rax
0x18000b6d3  test    rax, rax
0x18000b6d6  jnz     loc_18000B502
0x18000b6dc  mov     r15d, 8007000Eh
0x18000b6e2  mov     rdx, r14; struct tagPROPSYMBOL *
0x18000b6e5  call    ?_FreeSymbol@CPropertySymbolCache@@AEAAXPEAUtagPROPSYMBOL@@@Z; CPropertySymbolCache::_FreeSymbol(tagPROPSYMBOL *)
0x18000b6ea  jmp     loc_18000B3B5
0x18000b6ef  mov     eax, 1
0x18000b6f4  lock xadd [rbx], eax
0x18000b6f8  inc     eax
0x18000b6fa  mov     [rsp+78h+PreviousCount], eax
0x18000b701  lock xadd [rbx+4], ecx
0x18000b706  cmp     ecx, 1
0x18000b709  jnz     loc_18000B3E3
0x18000b70f  mov     edx, ecx; lReleaseCount
0x18000b711  lea     r8, [rsp+78h+PreviousCount]; lpPreviousCount
0x18000b719  mov     rcx, [rbx+30h]; hSemaphore
0x18000b71d  call    cs:__imp_ReleaseSemaphore
0x18000b723  jmp     loc_18000B3E3
```
