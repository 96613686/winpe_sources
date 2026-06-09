# DetailsView::CompareItems(void *,void *,__int64)

- ea: `0x180008f80`
- end: `0x1800092ee`
- name: `?CompareItems@DetailsView@@CAHPEAX0_J@Z`
- size: `878`
- prototype: `int __stdcall(void *p1, void *p2, LPARAM lParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001510`
- `0x180008ee0`
- `0x180008f80`
- `0x18000b478`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800091e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000926f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000929c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800091e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000926f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000929c`

## pseudocode

```c
__int64 __fastcall DetailsView::CompareItems(struct IDiskQuotaUser *p1, struct IDiskQuotaUser *p2, int *lParam)
{
  __int64 v3; // rdi
  __int64 v4; // r9
  int v5; // ebx
  int v7; // r8d
  int v9; // ebx
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 result; // rax
  __int64 v20; // rsi
  __int64 v21; // rdi
  int v22; // eax
  _BYTE *v23; // rax
  _BYTE *v24; // r8
  _BYTE *v25; // r8
  _BYTE *v26; // rax
  int v27; // ecx
  int UserQuotaState; // ebx
  DetailsView *v29; // rcx
  struct IDiskQuotaUser *v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[520]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[520]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v35[520]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v36[520]; // [rsp+678h] [rbp+578h] BYREF
  _BYTE v37[520]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v38[520]; // [rsp+A88h] [rbp+988h] BYREF

  v3 = lParam[1];
  v4 = 0;
  v5 = lParam[1];
  v30[0] = p1;
  v30[1] = p2;
  v7 = *lParam;
  v9 = v5 ^ 1;
  if ( !v7 )
  {
    UserQuotaState = DetailsView::GetUserQuotaState((DetailsView *)p1, v30[v9]);
    v4 = (int)(DetailsView::GetUserQuotaState(v29, v30[v3]) - UserQuotaState);
    goto LABEL_33;
  }
  v11 = v7 - 1;
  if ( !v11 || (v12 = v11 - 1) == 0 || (v13 = v12 - 1) == 0 )
  {
    ((void (__fastcall *)(struct IDiskQuotaUser *, struct IDiskQuotaUser **))p1->lpVtbl[1].GetSidLength)(p1, v30);
    ((void (__fastcall *)(struct IDiskQuotaUser *, char *))p2->lpVtbl[1].GetSidLength)(p2, (char *)v30 + 4);
    if ( v30[0] )
    {
      v27 = *((_DWORD *)v30 + v3) - *((_DWORD *)v30 + v9);
      goto LABEL_31;
    }
    ((void (__fastcall *)(struct IDiskQuotaUser *, _BYTE *, __int64, _BYTE *, int, _BYTE *, int))p1->lpVtbl->GetQuotaThreshold)(
      p1,
      v33,
      260,
      v35,
      260,
      v37,
      260);
    ((void (__fastcall *)(struct IDiskQuotaUser *, _BYTE *, __int64, _BYTE *, int, _BYTE *, int))p2->lpVtbl->GetQuotaThreshold)(
      p2,
      v34,
      260,
      v36,
      260,
      v38,
      260);
    if ( *lParam == 1 )
    {
      v20 = 520LL * v9;
      v21 = 520 * v3;
      v22 = CompareStringW(0x400u, 1u, (PCNZWCH)&v33[v21], -1, (PCNZWCH)&v33[v20], -1);
      if ( v22 == 2 )
      {
        v23 = v35;
        v24 = v35;
LABEL_28:
        v22 = CompareStringW(0x400u, 1u, (PCNZWCH)&v24[v21], -1, (PCNZWCH)&v23[v20], -1);
      }
    }
    else
    {
      if ( *lParam == 2 )
      {
        v25 = v37;
        v20 = 520LL * v9;
        v26 = v37;
      }
      else
      {
        v22 = 2;
        if ( *lParam != 3 )
          goto LABEL_29;
        v25 = v35;
        v20 = 520LL * v9;
        v26 = v35;
      }
      v21 = 520 * v3;
      v22 = CompareStringW(0x400u, 1u, (PCNZWCH)&v25[v21], -1, (PCNZWCH)&v26[v20], -1);
      if ( v22 == 2 )
      {
        v24 = v33;
        v23 = v33;
        goto LABEL_28;
      }
    }
LABEL_29:
    v27 = v22 - 2;
LABEL_31:
    v4 = v27;
    goto LABEL_33;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))p1->lpVtbl->SetQuotaThreshold)(p1, &v31);
    ((void (__fastcall *)(struct IDiskQuotaUser *, _BYTE *))p2->lpVtbl->SetQuotaThreshold)(p2, v32);
    v17 = *(_QWORD *)&v32[8 * v3 - 8];
    v18 = v9;
LABEL_17:
    v4 = v17 - *(_QWORD *)&v32[8 * v18 - 8];
    goto LABEL_33;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))p1->lpVtbl->GetQuotaUsedText)(p1, &v31);
    ((void (__fastcall *)(struct IDiskQuotaUser *, _BYTE *))p2->lpVtbl->GetQuotaUsedText)(p2, v32);
LABEL_12:
    v17 = *(_QWORD *)&v32[8 * v3 - 8];
    if ( v17 == -1 )
      return 1;
    v18 = v9;
    if ( *(_QWORD *)&v32[8 * v9 - 8] == -1 )
      return 0xFFFFFFFFLL;
    goto LABEL_17;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    ((void (__fastcall *)(struct IDiskQuotaUser *, __int64 *))p1->lpVtbl->GetQuotaLimitText)(p1, &v31);
    ((void (__fastcall *)(struct IDiskQuotaUser *, _BYTE *))p2->lpVtbl->GetQuotaLimitText)(p2, v32);
    goto LABEL_12;
  }
  if ( v16 == 1 )
  {
    DetailsView::CalcPctQuotaUsed(p1, (unsigned int *)v30);
    DetailsView::CalcPctQuotaUsed(p2, (unsigned int *)v30 + 1);
    v4 = *((_DWORD *)v30 + v3) - *((_DWORD *)v30 + v9);
  }
LABEL_33:
  result = 0;
  if ( v4 )
  {
    if ( v4 > 0 )
      return 1;
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x180008f80  push    rbp
0x180008f82  push    rbx
0x180008f83  push    rsi
0x180008f84  push    rdi
0x180008f85  push    r12
0x180008f87  push    r13
0x180008f89  push    r14
0x180008f8b  push    r15
0x180008f8d  lea     rbp, [rsp-0BA8h]
0x180008f95  sub     rsp, 0CA8h
0x180008f9c  mov     rax, cs:__security_cookie
0x180008fa3  xor     rax, rsp
0x180008fa6  mov     [rbp+0BE0h+var_50], rax
0x180008fad  movsxd  rdi, dword ptr [r8+4]
0x180008fb1  xor     r9d, r9d
0x180008fb4  mov     ebx, edi
0x180008fb6  mov     [rsp+0CE0h+var_CA0], rcx
0x180008fbb  mov     r15, r8
0x180008fbe  mov     [rsp+0CE0h+var_C98], rdx
0x180008fc3  mov     r8d, [r8]
0x180008fc6  or      r13, 0FFFFFFFFFFFFFFFFh
0x180008fca  lea     r12d, [r9+1]
0x180008fce  mov     rsi, rdx
0x180008fd1  xor     ebx, r12d
0x180008fd4  mov     r14, rcx
0x180008fd7  test    r8d, r8d
0x180008fda  jz      loc_1800092B7
0x180008fe0  sub     r8d, r12d
0x180008fe3  jz      loc_1800090F5
0x180008fe9  sub     r8d, r12d
0x180008fec  jz      loc_1800090F5
0x180008ff2  sub     r8d, r12d
0x180008ff5  jz      loc_1800090F5
0x180008ffb  sub     r8d, r12d
0x180008ffe  jz      loc_1800090BE
0x180009004  sub     r8d, r12d
0x180009007  jz      short loc_18000905B
0x180009009  sub     r8d, r12d
0x18000900c  jz      short loc_180009041
0x18000900e  cmp     r8d, r12d
0x180009011  jnz     loc_1800092D5
0x180009017  lea     rdx, [rsp+0CE0h+var_CA0]; unsigned int *
0x18000901c  call    ?CalcPctQuotaUsed@DetailsView@@CAJPEAUIDiskQuotaUser@@PEAK@Z; DetailsView::CalcPctQuotaUsed(IDiskQuotaUser *,ulong *)
0x180009021  lea     rdx, [rsp+0CE0h+var_CA0+4]; unsigned int *
0x180009026  mov     rcx, rsi; struct IDiskQuotaUser *
0x180009029  call    ?CalcPctQuotaUsed@DetailsView@@CAJPEAUIDiskQuotaUser@@PEAK@Z; DetailsView::CalcPctQuotaUsed(IDiskQuotaUser *,ulong *)
0x18000902e  mov     edx, dword ptr [rsp+rdi*4+0CE0h+var_CA0]
0x180009032  movsxd  rax, ebx
0x180009035  sub     edx, dword ptr [rsp+rax*4+0CE0h+var_CA0]
0x180009039  movsxd  r9, edx
0x18000903c  jmp     loc_1800092D5
0x180009041  mov     rax, [rcx]
0x180009044  lea     rdx, [rsp+0CE0h+var_C90]
0x180009049  mov     rax, [rax+38h]
0x18000904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009052  mov     rax, [rsi]
0x180009055  mov     rax, [rax+38h]
0x180009059  jmp     short loc_180009073
0x18000905b  mov     rax, [rcx]
0x18000905e  lea     rdx, [rsp+0CE0h+var_C90]
0x180009063  mov     rax, [rax+48h]
0x180009067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906c  mov     rax, [rsi]
0x18000906f  mov     rax, [rax+48h]
0x180009073  mov     rcx, rsi
0x180009076  lea     rdx, [rsp+0CE0h+var_C88]
0x18000907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009080  mov     r9, [rsp+rdi*8+0CE0h+var_C90]
0x180009085  cmp     r9, r13
0x180009088  jz      loc_1800092E6
0x18000908e  movsxd  rax, ebx
0x180009091  cmp     [rsp+rax*8+0CE0h+var_C90], r13
0x180009096  jnz     short loc_1800090EB
0x180009098  mov     eax, r13d
0x18000909b  mov     rcx, [rbp+0BE0h+var_50]
0x1800090a2  xor     rcx, rsp; StackCookie
0x1800090a5  call    __security_check_cookie
0x1800090aa  add     rsp, 0CA8h
0x1800090b1  pop     r15
0x1800090b3  pop     r14
0x1800090b5  pop     r13
0x1800090b7  pop     r12
0x1800090b9  pop     rdi
0x1800090ba  pop     rsi
0x1800090bb  pop     rbx
0x1800090bc  pop     rbp
0x1800090bd  retn
0x1800090be  mov     rax, [rcx]
0x1800090c1  lea     rdx, [rsp+0CE0h+var_C90]
0x1800090c6  mov     rax, [rax+58h]
0x1800090ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090cf  mov     rax, [rsi]
0x1800090d2  lea     rdx, [rsp+0CE0h+var_C88]
0x1800090d7  mov     rcx, rsi
0x1800090da  mov     rax, [rax+58h]
0x1800090de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e3  mov     r9, [rsp+rdi*8+0CE0h+var_C90]
0x1800090e8  movsxd  rax, ebx
0x1800090eb  sub     r9, [rsp+rax*8+0CE0h+var_C90]
0x1800090f0  jmp     loc_1800092D5
0x1800090f5  mov     rax, [rcx]
0x1800090f8  lea     rdx, [rsp+0CE0h+var_CA0]
0x1800090fd  mov     rax, [rax+88h]
0x180009104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009109  mov     rax, [rsi]
0x18000910c  lea     rdx, [rsp+0CE0h+var_CA0+4]
0x180009111  mov     rcx, rsi
0x180009114  mov     rax, [rax+88h]
0x18000911b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009120  cmp     dword ptr [rsp+0CE0h+var_CA0], 0
0x180009125  jnz     loc_1800092A7
0x18000912b  cmp     dword ptr [rsp+0CE0h+var_CA0+4], 0
0x180009130  jnz     loc_1800092A7
0x180009136  mov     rax, [r14]
0x180009139  lea     rcx, [rbp+0BE0h+var_460]
0x180009140  mov     r12d, 104h
0x180009146  lea     r9, [rbp+0BE0h+var_870]
0x18000914d  mov     [rsp+0CE0h+var_CB0], r12d
0x180009152  lea     rdx, [rsp+0CE0h+var_C80]
0x180009157  mov     qword ptr [rsp+0CE0h+cchCount2], rcx
0x18000915c  mov     r8d, r12d
0x18000915f  mov     rax, [rax+20h]
0x180009163  mov     rcx, r14
0x180009166  mov     dword ptr [rsp+0CE0h+lpString2], r12d
0x18000916b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009170  mov     rax, [rsi]
0x180009173  lea     rcx, [rbp+0BE0h+var_258]
0x18000917a  mov     [rsp+0CE0h+var_CB0], r12d
0x18000917f  lea     r9, [rbp+0BE0h+var_668]
0x180009186  mov     qword ptr [rsp+0CE0h+cchCount2], rcx
0x18000918b  lea     rdx, [rbp+0BE0h+var_A78]
0x180009192  mov     r8d, r12d
0x180009195  mov     dword ptr [rsp+0CE0h+lpString2], r12d
0x18000919a  mov     rax, [rax+20h]
0x18000919e  mov     rcx, rsi
0x1800091a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a6  mov     r12d, 1
0x1800091ac  cmp     [r15], r12d
0x1800091af  jnz     short loc_180009208
0x1800091b1  movsxd  rax, ebx
0x1800091b4  lea     r8, [rsp+0CE0h+var_C80]
0x1800091b9  imul    rsi, rax, 208h
0x1800091c0  imul    rdi, 208h
0x1800091c7  lea     rax, [rsp+0CE0h+var_C80]
0x1800091cc  mov     [rsp+0CE0h+cchCount2], r13d; cchCount2
0x1800091d1  add     rax, rsi
0x1800091d4  mov     ebx, 400h
0x1800091d9  mov     r9d, r13d; cchCount1
0x1800091dc  mov     [rsp+0CE0h+lpString2], rax; lpString2
0x1800091e1  mov     edx, r12d; dwCmpFlags
0x1800091e4  mov     ecx, ebx; Locale
0x1800091e6  add     r8, rdi; lpString1
0x1800091e9  call    cs:__imp_CompareStringW
0x1800091ef  cmp     eax, 2
0x1800091f2  jnz     loc_1800092A2
0x1800091f8  lea     rax, [rbp+0BE0h+var_870]
0x1800091ff  lea     r8, [rbp+0BE0h+var_870]
0x180009206  jmp     short loc_180009284
0x180009208  cmp     dword ptr [r15], 2
0x18000920c  jnz     short loc_180009228
0x18000920e  movsxd  rax, ebx
0x180009211  lea     r8, [rbp+0BE0h+var_460]
0x180009218  imul    rsi, rax, 208h
0x18000921f  lea     rax, [rbp+0BE0h+var_460]
0x180009226  jmp     short loc_18000924B
0x180009228  cmp     dword ptr [r15], 3
0x18000922c  mov     eax, 2
0x180009231  jnz     short loc_1800092A2
0x180009233  movsxd  rax, ebx
0x180009236  lea     r8, [rbp+0BE0h+var_870]
0x18000923d  imul    rsi, rax, 208h
0x180009244  lea     rax, [rbp+0BE0h+var_870]
0x18000924b  add     rax, rsi
0x18000924e  mov     [rsp+0CE0h+cchCount2], r13d; cchCount2
0x180009253  imul    rdi, 208h
0x18000925a  mov     ebx, 400h
0x18000925f  mov     [rsp+0CE0h+lpString2], rax; lpString2
0x180009264  add     r8, rdi; lpString1
0x180009267  mov     r9d, r13d; cchCount1
0x18000926a  mov     edx, r12d; dwCmpFlags
0x18000926d  mov     ecx, ebx; Locale
0x18000926f  call    cs:__imp_CompareStringW
0x180009275  cmp     eax, 2
0x180009278  jnz     short loc_1800092A2
0x18000927a  lea     r8, [rsp+0CE0h+var_C80]
0x18000927f  lea     rax, [rsp+0CE0h+var_C80]
0x180009284  add     rax, rsi
0x180009287  mov     [rsp+0CE0h+cchCount2], r13d; cchCount2
0x18000928c  mov     r9d, r13d; cchCount1
0x18000928f  mov     [rsp+0CE0h+lpString2], rax; lpString2
0x180009294  add     r8, rdi; lpString1
0x180009297  mov     edx, r12d; dwCmpFlags
0x18000929a  mov     ecx, ebx; Locale
0x18000929c  call    cs:__imp_CompareStringW
0x1800092a2  lea     ecx, [rax-2]
0x1800092a5  jmp     short loc_1800092B2
0x1800092a7  mov     ecx, dword ptr [rsp+rdi*4+0CE0h+var_CA0]
0x1800092ab  movsxd  rax, ebx
0x1800092ae  sub     ecx, dword ptr [rsp+rax*4+0CE0h+var_CA0]; this
0x1800092b2  movsxd  r9, ecx
0x1800092b5  jmp     short loc_1800092D5
0x1800092b7  movsxd  rdx, ebx
0x1800092ba  mov     rdx, [rsp+rdx*8+0CE0h+var_CA0]; struct IDiskQuotaUser *
0x1800092bf  call    ?GetUserQuotaState@DetailsView@@AEAAHPEAUIDiskQuotaUser@@@Z; DetailsView::GetUserQuotaState(IDiskQuotaUser *)
0x1800092c4  mov     rdx, [rsp+rdi*8+0CE0h+var_CA0]; struct IDiskQuotaUser *
0x1800092c9  mov     ebx, eax
0x1800092cb  call    ?GetUserQuotaState@DetailsView@@AEAAHPEAUIDiskQuotaUser@@@Z; DetailsView::GetUserQuotaState(IDiskQuotaUser *)
0x1800092d0  sub     eax, ebx
0x1800092d2  movsxd  r9, eax
0x1800092d5  xor     eax, eax
0x1800092d7  test    r9, r9
0x1800092da  jz      loc_18000909B
0x1800092e0  jle     loc_180009098
0x1800092e6  mov     eax, r12d
0x1800092e9  jmp     loc_18000909B
```
