# FveBcdUtil::GetUniqueBcdDevicePaths(void *,PathBuffer *,ulong *)

- ea: `0x1800132c8`
- end: `0x18001365a`
- name: `?GetUniqueBcdDevicePaths@FveBcdUtil@@CAJPEAXPEAVPathBuffer@@PEAK@Z`
- size: `914`
- prototype: `__int64 __fastcall(void *, LPCWCH *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012be8`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180012048`
- `0x180012304`
- `0x180012660`
- `0x1800132c8`
- `0x180013660`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800133d0`
- `KERNEL32!HeapFree` at `0x1800135f3`
- `KERNEL32!HeapFree` at `0x180013617`
- `KERNEL32!HeapFree` at `0x1800133d0`
- `KERNEL32!HeapFree` at `0x1800135f3`
- `KERNEL32!HeapFree` at `0x180013617`
- `KERNEL32!GetProcessHeap` at `0x1800133c2`
- `KERNEL32!GetProcessHeap` at `0x1800135e5`
- `KERNEL32!GetProcessHeap` at `0x180013609`
- `KERNEL32!GetProcessHeap` at `0x1800133c2`
- `KERNEL32!GetProcessHeap` at `0x1800135e5`
- `KERNEL32!GetProcessHeap` at `0x180013609`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetUniqueBcdDevicePaths(void *a1, LPCWCH *a2, unsigned int *a3)
{
  unsigned int v3; // r14d
  void *v4; // rdi
  LPCWCH *v5; // r15
  void *v6; // r13
  int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  unsigned int v11; // esi
  __int64 v12; // r12
  HANDLE ProcessHeap; // rax
  int v14; // eax
  unsigned int i; // r14d
  __int64 v16; // rax
  const unsigned __int16 *v17; // r13
  int v18; // eax
  __int64 v19; // rdx
  HANDLE v20; // rax
  struct _BCD_OBJECT *v21; // rdi
  HANDLE v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-24h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-20h]
  LPVOID lpMem; // [rsp+40h] [rbp-18h] BYREF
  struct _BCD_OBJECT *v28; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v32; // [rsp+B8h] [rbp+60h]

  v3 = *a3;
  v4 = 0;
  lpMem = 0;
  v5 = a2;
  v24 = 0;
  v6 = a1;
  v28 = 0;
  v26 = v3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids);
  v7 = FveBcdUtil::EnumerateApplicationObjects(v6, &v28, &v24);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)v7);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
      {
        WPP_SF_d(v10[2], 38, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v9);
        goto LABEL_53;
      }
    }
    goto LABEL_54;
  }
  v11 = 0;
  v32 = 0;
  v12 = 0;
LABEL_12:
  if ( (unsigned int)v12 >= v24 )
  {
    *a3 = v11;
    if ( v5 && v11 > v26 )
    {
      v9 = -2147024774;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_51;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          2147942522LL);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
        goto LABEL_51;
      v19 = 44;
LABEL_49:
      WPP_SF_d(v10[2], v19, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v9);
    }
LABEL_50:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    lpMem = 0;
  }
  v25 = 0;
  v14 = FveBcdUtil::EnumerateElements(
          v6,
          (const struct _GUID *)((char *)v28 + 24 * v12),
          v8,
          (struct _BCD_ELEMENT **)&lpMem,
          &v25);
  v9 = v14;
  if ( v14 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_40;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v14);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
    {
LABEL_40:
      v4 = lpMem;
      goto LABEL_51;
    }
    WPP_SF_d(v10[2], 40, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v9);
    v4 = lpMem;
    goto LABEL_50;
  }
  v4 = lpMem;
  for ( i = 0; ; ++i )
  {
    if ( i >= v25 )
    {
      v6 = a1;
      v12 = (unsigned int)(v12 + 1);
      goto LABEL_12;
    }
    if ( (*(_DWORD *)(*((_QWORD *)v4 + 2 * i) + 4LL) & 0xF000000) == 0x1000000 )
    {
      v16 = *((_QWORD *)v4 + 2 * i + 1);
      if ( *(_DWORD *)v16 == 2 )
      {
        v17 = (const unsigned __int16 *)(v16 + 20);
        if ( !v5 || !FveBcdUtil::FindExistingPath(v5, v32, (const unsigned __int16 *)(v16 + 20)) )
          break;
      }
    }
LABEL_26:
    ;
  }
  if ( v11 + 1 >= v26 )
  {
LABEL_25:
    ++v11;
    v5 = a2;
    goto LABEL_26;
  }
  v18 = PathBuffer::Initialize((PathBuffer *)&a2[v11], v17);
  v9 = v18;
  if ( v18 >= 0 )
  {
    ++v32;
    goto LABEL_25;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
        (unsigned int)v18);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
    {
      v19 = 42;
      goto LABEL_49;
    }
  }
LABEL_51:
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v4);
LABEL_53:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_54:
  v21 = v28;
  if ( v28 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 45, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800132c8  mov     [rsp-40h+arg_10], r8
0x1800132cd  mov     [rsp-40h+arg_8], rdx
0x1800132d2  mov     [rsp-40h+arg_0], rcx
0x1800132d7  push    rbp
0x1800132d8  push    rbx
0x1800132d9  push    rsi
0x1800132da  push    rdi
0x1800132db  push    r12
0x1800132dd  push    r13
0x1800132df  push    r14
0x1800132e1  push    r15
0x1800132e3  mov     rbp, rsp
0x1800132e6  sub     rsp, 58h
0x1800132ea  mov     r14d, [r8]
0x1800132ed  xor     edi, edi
0x1800132ef  mov     [rbp+lpMem], rdi
0x1800132f3  mov     r15, rdx
0x1800132f6  mov     [rbp+var_28], edi
0x1800132f9  mov     r13, rcx
0x1800132fc  mov     [rbp+var_10], rdi
0x180013300  mov     [rbp+var_20], r14d
0x180013304  mov     rcx, cs:WPP_GLOBAL_Control
0x18001330b  lea     r14, WPP_GLOBAL_Control
0x180013312  cmp     rcx, r14
0x180013315  jz      short loc_180013330
0x180013317  test    byte ptr [rcx+1Ch], 20h
0x18001331b  jz      short loc_180013330
0x18001331d  mov     rcx, [rcx+10h]
0x180013321  lea     edx, [rdi+24h]
0x180013324  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001332b  call    WPP_SF_
0x180013330  lea     r8, [rbp+var_28]; unsigned int *
0x180013334  mov     rcx, r13; void *
0x180013337  lea     rdx, [rbp+var_10]; struct _BCD_OBJECT **
0x18001333b  call    ?EnumerateApplicationObjects@FveBcdUtil@@CAJPEAXPEAPEAU_BCD_OBJECT@@PEAK@Z; FveBcdUtil::EnumerateApplicationObjects(void *,_BCD_OBJECT * *,ulong *)
0x180013340  mov     ebx, eax
0x180013342  test    eax, eax
0x180013344  jns     short loc_1800133AB
0x180013346  mov     rcx, cs:WPP_GLOBAL_Control
0x18001334d  cmp     rcx, r14
0x180013350  jz      loc_180013600
0x180013356  test    byte ptr [rcx+1Ch], 2
0x18001335a  jz      short loc_18001337B
0x18001335c  mov     rcx, [rcx+10h]
0x180013360  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013367  mov     edx, 25h ; '%'
0x18001336c  mov     r9d, eax
0x18001336f  call    WPP_SF_d
0x180013374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001337b  cmp     rcx, r14
0x18001337e  jz      loc_180013600
0x180013384  test    byte ptr [rcx+1Ch], 40h
0x180013388  jz      loc_180013600
0x18001338e  mov     rcx, [rcx+10h]
0x180013392  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013399  mov     edx, 26h ; '&'
0x18001339e  mov     r9d, ebx
0x1800133a1  call    WPP_SF_d
0x1800133a6  jmp     loc_1800135F9
0x1800133ab  xor     esi, esi
0x1800133ad  mov     [rbp+arg_18], esi
0x1800133b0  xor     r12d, r12d
0x1800133b3  cmp     r12d, [rbp+var_28]
0x1800133b7  jnb     loc_180013560
0x1800133bd  test    rdi, rdi
0x1800133c0  jz      short loc_1800133DE
0x1800133c2  call    cs:__imp_GetProcessHeap
0x1800133c8  mov     r8, rdi; lpMem
0x1800133cb  xor     edx, edx; dwFlags
0x1800133cd  mov     rcx, rax; hHeap
0x1800133d0  call    cs:__imp_HeapFree
0x1800133d6  mov     [rbp+lpMem], 0
0x1800133de  mov     rax, [rbp+var_10]
0x1800133e2  lea     rcx, [r12+r12*2]
0x1800133e6  lea     r9, [rbp+lpMem]; struct _BCD_ELEMENT **
0x1800133ea  mov     [rbp+var_24], 0
0x1800133f1  lea     rdx, [rax+rcx*8]; struct _GUID *
0x1800133f5  mov     rcx, r13; void *
0x1800133f8  lea     rax, [rbp+var_24]
0x1800133fc  mov     [rsp+58h+var_38], rax; unsigned int *
0x180013401  call    ?EnumerateElements@FveBcdUtil@@CAJPEAXPEBU_GUID@@KPEAPEAU_BCD_ELEMENT@@PEAK@Z; FveBcdUtil::EnumerateElements(void *,_GUID const *,ulong,_BCD_ELEMENT * *,ulong *)
0x180013406  mov     ebx, eax
0x180013408  test    eax, eax
0x18001340a  js      loc_1800134F3
0x180013410  mov     rdi, [rbp+lpMem]
0x180013414  xor     r14d, r14d
0x180013417  cmp     r14d, [rbp+var_24]
0x18001341b  jnb     short loc_18001348E
0x18001341d  mov     edx, r14d
0x180013420  add     rdx, rdx
0x180013423  mov     rax, [rdi+rdx*8]
0x180013427  mov     ecx, [rax+4]
0x18001342a  and     ecx, 0F000000h
0x180013430  cmp     ecx, 1000000h
0x180013436  jnz     short loc_180013489
0x180013438  mov     rax, [rdi+rdx*8+8]
0x18001343d  cmp     dword ptr [rax], 2
0x180013440  jnz     short loc_180013489
0x180013442  lea     r13, [rax+14h]
0x180013446  test    r15, r15
0x180013449  jz      short loc_18001345D
0x18001344b  mov     edx, [rbp+arg_18]; unsigned int
0x18001344e  mov     r8, r13; unsigned __int16 *
0x180013451  mov     rcx, r15; struct PathBuffer *
0x180013454  call    ?FindExistingPath@FveBcdUtil@@SA_NPEAVPathBuffer@@KPEBG@Z; FveBcdUtil::FindExistingPath(PathBuffer *,ulong,ushort const *)
0x180013459  test    al, al
0x18001345b  jnz     short loc_180013489
0x18001345d  lea     r15d, [rsi+1]
0x180013461  cmp     r15d, [rbp+var_20]
0x180013465  jnb     short loc_180013482
0x180013467  mov     rcx, [rbp+arg_8]
0x18001346b  mov     rdx, r13; unsigned __int16 *
0x18001346e  mov     eax, esi
0x180013470  lea     rcx, [rcx+rax*8]; this
0x180013474  call    ?Initialize@PathBuffer@@QEAAJPEBG@Z; PathBuffer::Initialize(ushort const *)
0x180013479  mov     ebx, eax
0x18001347b  test    eax, eax
0x18001347d  js      short loc_18001349A
0x18001347f  inc     [rbp+arg_18]
0x180013482  mov     esi, r15d
0x180013485  mov     r15, [rbp+arg_8]
0x180013489  inc     r14d
0x18001348c  jmp     short loc_180013417
0x18001348e  mov     r13, [rbp+arg_0]
0x180013492  inc     r12d
0x180013495  jmp     loc_1800133B3
0x18001349a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134a1  lea     r14, WPP_GLOBAL_Control
0x1800134a8  cmp     rcx, r14
0x1800134ab  jz      loc_1800135E0
0x1800134b1  test    byte ptr [rcx+1Ch], 2
0x1800134b5  jz      short loc_1800134D6
0x1800134b7  mov     rcx, [rcx+10h]
0x1800134bb  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800134c2  mov     edx, 29h ; ')'
0x1800134c7  mov     r9d, ebx
0x1800134ca  call    WPP_SF_d
0x1800134cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134d6  cmp     rcx, r14
0x1800134d9  jz      loc_1800135E0
0x1800134df  test    byte ptr [rcx+1Ch], 40h
0x1800134e3  jz      loc_1800135E0
0x1800134e9  mov     edx, 2Ah ; '*'
0x1800134ee  jmp     loc_1800135BD
0x1800134f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134fa  lea     r14, WPP_GLOBAL_Control
0x180013501  cmp     rcx, r14
0x180013504  jz      short loc_180013557
0x180013506  test    byte ptr [rcx+1Ch], 2
0x18001350a  jz      short loc_18001352B
0x18001350c  mov     rcx, [rcx+10h]
0x180013510  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013517  mov     edx, 27h ; '''
0x18001351c  mov     r9d, ebx
0x18001351f  call    WPP_SF_d
0x180013524  mov     rcx, cs:WPP_GLOBAL_Control
0x18001352b  cmp     rcx, r14
0x18001352e  jz      short loc_180013557
0x180013530  test    byte ptr [rcx+1Ch], 40h
0x180013534  jz      short loc_180013557
0x180013536  mov     rcx, [rcx+10h]
0x18001353a  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013541  mov     edx, 28h ; '('
0x180013546  mov     r9d, ebx
0x180013549  call    WPP_SF_d
0x18001354e  mov     rdi, [rbp+lpMem]
0x180013552  jmp     loc_1800135D9
0x180013557  mov     rdi, [rbp+lpMem]
0x18001355b  jmp     loc_1800135E0
0x180013560  mov     rax, [rbp+arg_10]
0x180013564  mov     [rax], esi
0x180013566  test    r15, r15
0x180013569  jz      short loc_1800135D2
0x18001356b  cmp     esi, [rbp+var_20]
0x18001356e  jbe     short loc_1800135D2
0x180013570  mov     ebx, 8007007Ah
0x180013575  mov     rcx, cs:WPP_GLOBAL_Control
0x18001357c  lea     r14, WPP_GLOBAL_Control
0x180013583  cmp     rcx, r14
0x180013586  jz      short loc_1800135E0
0x180013588  test    byte ptr [rcx+1Ch], 2
0x18001358c  jz      short loc_1800135AD
0x18001358e  mov     rcx, [rcx+10h]
0x180013592  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180013599  mov     edx, 2Bh ; '+'
0x18001359e  mov     r9d, ebx
0x1800135a1  call    WPP_SF_d
0x1800135a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135ad  cmp     rcx, r14
0x1800135b0  jz      short loc_1800135E0
0x1800135b2  test    byte ptr [rcx+1Ch], 40h
0x1800135b6  jz      short loc_1800135E0
0x1800135b8  mov     edx, 2Ch ; ','
0x1800135bd  mov     rcx, [rcx+10h]
0x1800135c1  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x1800135c8  mov     r9d, ebx
0x1800135cb  call    WPP_SF_d
0x1800135d0  jmp     short loc_1800135D9
0x1800135d2  lea     r14, WPP_GLOBAL_Control
0x1800135d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135e0  test    rdi, rdi
0x1800135e3  jz      short loc_180013600
0x1800135e5  call    cs:__imp_GetProcessHeap
0x1800135eb  mov     r8, rdi; lpMem
0x1800135ee  xor     edx, edx; dwFlags
0x1800135f0  mov     rcx, rax; hHeap
0x1800135f3  call    cs:__imp_HeapFree
0x1800135f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013600  mov     rdi, [rbp+var_10]
0x180013604  test    rdi, rdi
0x180013607  jz      short loc_180013624
0x180013609  call    cs:__imp_GetProcessHeap
0x18001360f  mov     r8, rdi; lpMem
0x180013612  xor     edx, edx; dwFlags
0x180013614  mov     rcx, rax; hHeap
0x180013617  call    cs:__imp_HeapFree
0x18001361d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013624  cmp     rcx, r14
0x180013627  jz      short loc_180013647
0x180013629  test    byte ptr [rcx+1Ch], 20h
0x18001362d  jz      short loc_180013647
0x18001362f  mov     rcx, [rcx+10h]
0x180013633  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001363a  mov     edx, 2Dh ; '-'
0x18001363f  mov     r9d, ebx
0x180013642  call    WPP_SF_d
0x180013647  mov     eax, ebx
0x180013649  add     rsp, 58h
0x18001364d  pop     r15
0x18001364f  pop     r14
0x180013651  pop     r13
0x180013653  pop     r12
0x180013655  pop     rdi
0x180013656  pop     rsi
0x180013657  pop     rbx
0x180013658  pop     rbp
0x180013659  retn
```
