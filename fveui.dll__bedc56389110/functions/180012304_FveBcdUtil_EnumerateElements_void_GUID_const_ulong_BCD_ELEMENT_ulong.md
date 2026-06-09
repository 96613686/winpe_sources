# FveBcdUtil::EnumerateElements(void *,_GUID const *,ulong,_BCD_ELEMENT * *,ulong *)

- ea: `0x180012304`
- end: `0x18001265a`
- name: `?EnumerateElements@FveBcdUtil@@CAJPEAXPEBU_GUID@@KPEAPEAU_BCD_ELEMENT@@PEAK@Z`
- size: `854`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, __int64, struct _BCD_ELEMENT **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800132c8`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x18000ff64`
- `0x180012304`
- `0x1800138d4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800125fa`
- `KERNEL32!HeapFree` at `0x1800125fa`
- `KERNEL32!HeapAlloc` at `0x180012489`
- `KERNEL32!HeapAlloc` at `0x180012489`
- `KERNEL32!GetProcessHeap` at `0x180012478`
- `KERNEL32!GetProcessHeap` at `0x1800125ec`
- `KERNEL32!GetProcessHeap` at `0x180012478`
- `KERNEL32!GetProcessHeap` at `0x1800125ec`
- `bcd!BcdOpenObject` at `0x180012383`
- `bcd!BcdOpenObject` at `0x180012383`
- `bcd!BcdCloseObject` at `0x180012613`
- `bcd!BcdCloseObject` at `0x180012613`
- `bcd!BcdEnumerateAndUnpackElements` at `0x180012416`
- `bcd!BcdEnumerateAndUnpackElements` at `0x180012510`
- `bcd!BcdEnumerateAndUnpackElements` at `0x180012416`
- `bcd!BcdEnumerateAndUnpackElements` at `0x180012510`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::EnumerateElements(
        void *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct _BCD_ELEMENT **a4,
        unsigned int *a5)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // eax
  HANDLE ProcessHeap; // rax
  struct _BCD_ELEMENT *v16; // rsi
  int v17; // eax
  int v18; // eax
  PVOID *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // r8d
  HANDLE v22; // rax
  unsigned int *v24; // [rsp+20h] [rbp-30h]
  unsigned int *v25; // [rsp+28h] [rbp-28h]
  unsigned int v26; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-Ch] BYREF
  __int64 v28; // [rsp+48h] [rbp-8h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids);
  v8 = BcdOpenObject(a1, a2, &v28);
  v9 = FromNtStatus(v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)v9);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
      {
        v12 = 26;
LABEL_11:
        WPP_SF_d(v11[2], v12, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
LABEL_44:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_45;
      }
    }
    goto LABEL_45;
  }
  v13 = BcdEnumerateAndUnpackElements(a1, v28, 28);
  if ( v13 == -1073741789 )
  {
    ProcessHeap = GetProcessHeap();
    v16 = (struct _BCD_ELEMENT *)HeapAlloc(ProcessHeap, 8u, 0);
    if ( !v16 )
    {
      v10 = -2147024882;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
            2147942414LL);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
        {
          v12 = 30;
          goto LABEL_11;
        }
      }
      goto LABEL_45;
    }
    v26 = 0;
    v25 = &v27;
    v24 = &v26;
    v17 = BcdEnumerateAndUnpackElements(a1, v28, 28);
    v18 = FromNtStatus(v17);
    v10 = v18;
    if ( v18 >= 0 )
    {
      v21 = v27;
      if ( !v26 && !v27 )
      {
        *a4 = v16;
        *a5 = v21;
        goto LABEL_44;
      }
      v10 = -2147418113;
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_43;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LODWORD(v25) = v27;
        LODWORD(v24) = 0;
        WPP_SF_LLLd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v27, v26, v24, v25);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 0x40) == 0 )
      {
LABEL_43:
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v16);
        goto LABEL_44;
      }
      v20 = 34;
    }
    else
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_43;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          (unsigned int)v18);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 0x40) == 0 )
        goto LABEL_43;
      v20 = 32;
    }
    WPP_SF_d(v19[2], v20, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
    goto LABEL_43;
  }
  v14 = FromNtStatus(v13);
  v10 = v14;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v14);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
    {
      v12 = 28;
      goto LABEL_11;
    }
  }
LABEL_45:
  if ( v28 )
  {
    BcdCloseObject(v28);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 )
    WPP_SF_d(v11[2], 35, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180012304  mov     [rsp-28h+arg_0], rbx
0x180012309  mov     [rsp-28h+arg_8], rsi
0x18001230e  mov     dword ptr [rsp-28h+dwBytes], r8d
0x180012313  push    rbp
0x180012314  push    rdi
0x180012315  push    r12
0x180012317  push    r14
0x180012319  push    r15
0x18001231b  mov     rbp, rsp
0x18001231e  sub     rsp, 50h
0x180012322  mov     r14, r9
0x180012325  mov     [rbp+var_10], 0
0x18001232c  mov     rbx, rdx
0x18001232f  mov     [rbp+var_C], 0
0x180012336  mov     rdi, rcx
0x180012339  mov     [rbp+var_8], 0
0x180012341  mov     dword ptr [rbp+dwBytes], 0
0x180012348  mov     rcx, cs:WPP_GLOBAL_Control
0x18001234f  lea     r15, WPP_GLOBAL_Control
0x180012356  lea     r12, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18001235d  cmp     rcx, r15
0x180012360  jz      short loc_180012379
0x180012362  test    byte ptr [rcx+1Ch], 20h
0x180012366  jz      short loc_180012379
0x180012368  mov     rcx, [rcx+10h]
0x18001236c  mov     edx, 18h
0x180012371  mov     r8, r12
0x180012374  call    WPP_SF_
0x180012379  lea     r8, [rbp+var_8]
0x18001237d  mov     rdx, rbx
0x180012380  mov     rcx, rdi
0x180012383  call    cs:__imp_BcdOpenObject
0x180012389  mov     ecx, eax; int
0x18001238b  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012390  mov     ebx, eax
0x180012392  test    eax, eax
0x180012394  jns     short loc_1800123F3
0x180012396  mov     rcx, cs:WPP_GLOBAL_Control
0x18001239d  cmp     rcx, r15
0x1800123a0  jz      loc_180012607
0x1800123a6  test    byte ptr [rcx+1Ch], 2
0x1800123aa  jz      short loc_1800123C7
0x1800123ac  mov     rcx, [rcx+10h]
0x1800123b0  mov     edx, 19h
0x1800123b5  mov     r9d, eax
0x1800123b8  mov     r8, r12
0x1800123bb  call    WPP_SF_d
0x1800123c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123c7  cmp     rcx, r15
0x1800123ca  jz      loc_180012607
0x1800123d0  test    byte ptr [rcx+1Ch], 40h
0x1800123d4  jz      loc_180012607
0x1800123da  mov     edx, 1Ah
0x1800123df  mov     rcx, [rcx+10h]
0x1800123e3  mov     r9d, ebx
0x1800123e6  mov     r8, r12
0x1800123e9  call    WPP_SF_d
0x1800123ee  jmp     loc_180012600
0x1800123f3  mov     rdx, [rbp+var_8]
0x1800123f7  lea     rax, [rbp+var_C]
0x1800123fb  mov     [rsp+50h+var_28], rax
0x180012400  xor     r9d, r9d
0x180012403  lea     rax, [rbp+dwBytes]
0x180012407  mov     rcx, rdi
0x18001240a  mov     [rsp+50h+var_30], rax
0x18001240f  lea     esi, [r9+1Ch]
0x180012413  mov     r8d, esi
0x180012416  call    cs:__imp_BcdEnumerateAndUnpackElements
0x18001241c  cmp     eax, 0C0000023h
0x180012421  jz      short loc_180012475
0x180012423  mov     ecx, eax; int
0x180012425  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001242a  mov     ebx, eax
0x18001242c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012433  cmp     rcx, r15
0x180012436  jz      loc_180012607
0x18001243c  test    byte ptr [rcx+1Ch], 2
0x180012440  jz      short loc_18001245B
0x180012442  mov     rcx, [rcx+10h]
0x180012446  lea     edx, [rsi-1]
0x180012449  mov     r9d, eax
0x18001244c  mov     r8, r12
0x18001244f  call    WPP_SF_d
0x180012454  mov     rcx, cs:WPP_GLOBAL_Control
0x18001245b  cmp     rcx, r15
0x18001245e  jz      loc_180012607
0x180012464  test    byte ptr [rcx+1Ch], 40h
0x180012468  jz      loc_180012607
0x18001246e  mov     edx, esi
0x180012470  jmp     loc_1800123DF
0x180012475  mov     ebx, dword ptr [rbp+dwBytes]
0x180012478  call    cs:__imp_GetProcessHeap
0x18001247e  mov     r8d, ebx; dwBytes
0x180012481  mov     edx, 8; dwFlags
0x180012486  mov     rcx, rax; hHeap
0x180012489  call    cs:__imp_HeapAlloc
0x18001248f  mov     rsi, rax
0x180012492  test    rax, rax
0x180012495  jnz     short loc_1800124E8
0x180012497  mov     ebx, 8007000Eh
0x18001249c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124a3  cmp     rcx, r15
0x1800124a6  jz      loc_180012607
0x1800124ac  test    byte ptr [rcx+1Ch], 2
0x1800124b0  jz      short loc_1800124CB
0x1800124b2  mov     rcx, [rcx+10h]
0x1800124b6  lea     edx, [rax+1Dh]
0x1800124b9  mov     r9d, ebx
0x1800124bc  mov     r8, r12
0x1800124bf  call    WPP_SF_d
0x1800124c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124cb  cmp     rcx, r15
0x1800124ce  jz      loc_180012607
0x1800124d4  test    byte ptr [rcx+1Ch], 40h
0x1800124d8  jz      loc_180012607
0x1800124de  mov     edx, 1Eh
0x1800124e3  jmp     loc_1800123DF
0x1800124e8  mov     eax, dword ptr [rbp+dwBytes]
0x1800124eb  mov     r9, rsi
0x1800124ee  mov     rdx, [rbp+var_8]
0x1800124f2  mov     r8d, 1Ch
0x1800124f8  mov     [rbp+var_10], eax
0x1800124fb  mov     rcx, rdi
0x1800124fe  lea     rax, [rbp+var_C]
0x180012502  mov     [rsp+50h+var_28], rax
0x180012507  lea     rax, [rbp+var_10]
0x18001250b  mov     [rsp+50h+var_30], rax
0x180012510  call    cs:__imp_BcdEnumerateAndUnpackElements
0x180012516  mov     ecx, eax; int
0x180012518  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001251d  mov     ebx, eax
0x18001251f  test    eax, eax
0x180012521  jns     short loc_18001256E
0x180012523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001252a  cmp     rcx, r15
0x18001252d  jz      loc_1800125EC
0x180012533  test    byte ptr [rcx+1Ch], 2
0x180012537  jz      short loc_180012554
0x180012539  mov     rcx, [rcx+10h]
0x18001253d  mov     edx, 1Fh
0x180012542  mov     r9d, eax
0x180012545  mov     r8, r12
0x180012548  call    WPP_SF_d
0x18001254d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012554  cmp     rcx, r15
0x180012557  jz      loc_1800125EC
0x18001255d  test    byte ptr [rcx+1Ch], 40h
0x180012561  jz      loc_1800125EC
0x180012567  mov     edx, 20h ; ' '
0x18001256c  jmp     short loc_1800125DD
0x18001256e  mov     r9d, dword ptr [rbp+dwBytes]
0x180012572  mov     r8d, [rbp+var_C]
0x180012576  cmp     [rbp+var_10], r9d
0x18001257a  ja      short loc_180012593
0x18001257c  mov     eax, r9d
0x18001257f  shr     eax, 4
0x180012582  cmp     r8d, eax
0x180012585  ja      short loc_180012593
0x180012587  mov     rax, [rbp+arg_20]
0x18001258b  mov     [r14], rsi
0x18001258e  mov     [rax], r8d
0x180012591  jmp     short loc_180012600
0x180012593  mov     ebx, 8000FFFFh
0x180012598  mov     rcx, cs:WPP_GLOBAL_Control
0x18001259f  cmp     rcx, r15
0x1800125a2  jz      short loc_1800125EC
0x1800125a4  test    byte ptr [rcx+1Ch], 2
0x1800125a8  jz      short loc_1800125CD
0x1800125aa  mov     rcx, [rcx+10h]
0x1800125ae  mov     edx, 21h ; '!'
0x1800125b3  mov     dword ptr [rsp+50h+var_28], r8d
0x1800125b8  mov     dword ptr [rsp+50h+var_30], r9d
0x1800125bd  mov     r9d, [rbp+var_10]
0x1800125c1  call    WPP_SF_LLLd
0x1800125c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125cd  cmp     rcx, r15
0x1800125d0  jz      short loc_1800125EC
0x1800125d2  test    byte ptr [rcx+1Ch], 40h
0x1800125d6  jz      short loc_1800125EC
0x1800125d8  mov     edx, 22h ; '"'
0x1800125dd  mov     rcx, [rcx+10h]
0x1800125e1  mov     r9d, ebx
0x1800125e4  mov     r8, r12
0x1800125e7  call    WPP_SF_d
0x1800125ec  call    cs:__imp_GetProcessHeap
0x1800125f2  mov     r8, rsi; lpMem
0x1800125f5  xor     edx, edx; dwFlags
0x1800125f7  mov     rcx, rax; hHeap
0x1800125fa  call    cs:__imp_HeapFree
0x180012600  mov     rcx, cs:WPP_GLOBAL_Control
0x180012607  mov     rax, [rbp+var_8]
0x18001260b  test    rax, rax
0x18001260e  jz      short loc_180012620
0x180012610  mov     rcx, rax
0x180012613  call    cs:__imp_BcdCloseObject
0x180012619  mov     rcx, cs:WPP_GLOBAL_Control
0x180012620  cmp     rcx, r15
0x180012623  jz      short loc_18001263F
0x180012625  test    byte ptr [rcx+1Ch], 20h
0x180012629  jz      short loc_18001263F
0x18001262b  mov     rcx, [rcx+10h]
0x18001262f  mov     edx, 23h ; '#'
0x180012634  mov     r9d, ebx
0x180012637  mov     r8, r12
0x18001263a  call    WPP_SF_d
0x18001263f  lea     r11, [rsp+50h+var_s0]
0x180012644  mov     eax, ebx
0x180012646  mov     rbx, [r11+30h]
0x18001264a  mov     rsi, [r11+38h]
0x18001264e  mov     rsp, r11
0x180012651  pop     r15
0x180012653  pop     r14
0x180012655  pop     r12
0x180012657  pop     rdi
0x180012658  pop     rbp
0x180012659  retn
```
