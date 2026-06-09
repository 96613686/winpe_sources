# CBTree::Search(char *,SIdxKeyTable * *,ushort *,ulong * const,long &)

- ea: `0x180012590`
- end: `0x180012995`
- name: `?Search@CBTree@@AEAAKPEADPEAPEAVSIdxKeyTable@@PEAGQEAKAEAJ@Z`
- size: `1029`
- prototype: `unsigned int __fastcall(CBTree *__hidden this, char *, struct SIdxKeyTable **, unsigned __int16 *, unsigned int *const, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011904`
- `0x1800213c8`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000d7e0`
- `0x180012590`
- `0x1800129a0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001287a`
- `wbemcomn!GetMemLogObject` at `0x1800128c2`
- `wbemcomn!GetMemLogObject` at `0x180012911`
- `wbemcomn!GetMemLogObject` at `0x180012944`
- `wbemcomn!GetMemLogObject` at `0x18001287a`
- `wbemcomn!GetMemLogObject` at `0x1800128c2`
- `wbemcomn!GetMemLogObject` at `0x180012911`
- `wbemcomn!GetMemLogObject` at `0x180012944`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012885`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800128d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001291f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012952`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012885`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800128d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001291f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012952`

## pseudocode

```c
__int64 __fastcall CBTree::Search(
        CBTree *this,
        char *a2,
        struct SIdxKeyTable **a3,
        unsigned __int16 *a4,
        unsigned int *const a5,
        int *a6)
{
  char *v6; // rbp
  CBTree *v7; // r14
  struct SIdxKeyTable *v8; // rsi
  __int64 v9; // rcx
  unsigned int *v10; // r15
  int v11; // eax
  int v12; // r13d
  int v13; // ebx
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // r14
  char *v17; // rdx
  __int64 v18; // r11
  __int64 v19; // rcx
  __int16 v20; // r10
  unsigned __int16 v21; // r11
  __int64 v22; // rbp
  __int64 v23; // r15
  char *v24; // r8
  __int16 v25; // r10
  int v26; // ecx
  int v27; // eax
  int v28; // r9d
  int v29; // ecx
  unsigned __int16 v30; // ax
  unsigned int v31; // edi
  unsigned int v32; // ebx
  __int64 v33; // rcx
  unsigned int v34; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  CVarObjHeap *v39; // rcx
  __int64 v40; // rdx
  CMemoryLog *v41; // rax
  struct SIdxKeyTable *v42; // [rsp+20h] [rbp-58h] BYREF
  struct SIdxKeyTable **v45; // [rsp+90h] [rbp+18h]
  unsigned __int16 *v46; // [rsp+98h] [rbp+20h]

  v46 = a4;
  v45 = a3;
  v6 = a2;
  v7 = this;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
    a4 = v46;
    a3 = v45;
  }
  if ( v6 && *v6 && a4 && a3 )
  {
    *a3 = 0;
    v8 = (struct SIdxKeyTable *)*((_QWORD *)v7 + 1);
    _InterlockedIncrement((volatile signed __int32 *)v8);
    v9 = *a6;
    if ( (int)v9 >= 1023 )
      return 1168;
    v10 = a5;
    *a6 = v9 + 1;
    a5[v9 + 1] = 0;
    while ( 1 )
    {
      if ( *a6 >= 1023 )
      {
LABEL_32:
        *v45 = v8;
        return 1168;
      }
      if ( !*v6 )
        break;
      v11 = *((_DWORD *)v8 + 3);
      if ( v11 )
      {
        LOWORD(v12) = 0;
        v13 = v11 - 1;
        v14 = 0;
        while ( 2 )
        {
          if ( v14 <= v13 )
          {
            v15 = *((_QWORD *)v8 + 2);
            v16 = *((_QWORD *)v8 + 6);
            v17 = v6;
            v12 = (v13 + v14) / 2;
            v42 = (struct SIdxKeyTable *)(unsigned __int16)v12;
            v18 = *(unsigned __int16 *)(v15 + 2LL * (unsigned __int16)v12);
            v19 = *((_QWORD *)v8 + 8);
            v20 = *(_WORD *)(v16 + 2 * v18);
            v21 = v18 + 1;
            v22 = *(_QWORD *)(v19 + 24);
            v23 = *(_QWORD *)(v19 + 8);
            v24 = (char *)(v22 + *(unsigned __int16 *)(v23 + 2LL * *(unsigned __int16 *)(v16 + 2LL * v21)));
            v25 = v20 - 1;
            while ( 1 )
            {
              v26 = *v24++;
              v27 = *v17;
              v28 = v26;
              if ( !(_BYTE)v26 && v25 )
              {
                ++v21;
                v28 = 92;
                v24 = (char *)(v22 + *(unsigned __int16 *)(v23 + 2LL * *(unsigned __int16 *)(v16 + 2LL * v21)));
                --v25;
              }
              v29 = v27 - v28;
              if ( v27 != v28 )
                break;
              if ( !(_BYTE)v27 && !v28 )
                goto LABEL_29;
              ++v17;
            }
            if ( v29 < 0 )
            {
              v6 = a2;
              v13 = v12 - 1;
              continue;
            }
            if ( v29 > 0 )
            {
              v6 = a2;
              v14 = ++v12;
              continue;
            }
LABEL_29:
            *v46 = (unsigned __int16)v42;
            *v45 = v8;
            return 0;
          }
          break;
        }
        a4 = v46;
        v30 = v12;
        v7 = this;
        v10 = a5;
      }
      else
      {
        v30 = 0;
      }
      *a4 = v30;
      v31 = *(_DWORD *)(*((_QWORD *)v8 + 5) + 4LL * *a4);
      if ( v31 == -1 )
        goto LABEL_32;
      v32 = *((_DWORD *)v8 + 1);
      SIdxKeyTable::Release(v8);
      v33 = *a6;
      v42 = 0;
      *a6 = v33 + 1;
      v10[v33 + 1] = v32;
      v34 = CBTree::ReadIdxPage(v7, v31, 0, &v42);
      if ( v34 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v34);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v34);
        }
        return v34;
      }
      v8 = v42;
      a4 = v46;
    }
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    SIdxKeyTable::Release(v8);
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, 87);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = 114;
      goto LABEL_55;
    }
  }
  else
  {
    v41 = GetMemLogObject();
    CMemoryLog::Write(v41, 87);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = 113;
LABEL_55:
      WPP_SF_d(*((_QWORD *)v39 + 2), v40, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180012590  mov     [rsp+arg_18], r9
0x180012595  mov     [rsp+arg_10], r8
0x18001259a  mov     [rsp+arg_8], rdx
0x18001259f  mov     [rsp+arg_0], rcx
0x1800125a4  push    rbp
0x1800125a5  push    r13
0x1800125a7  push    r14
0x1800125a9  sub     rsp, 60h
0x1800125ad  mov     rbp, rdx
0x1800125b0  mov     r14, rcx
0x1800125b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125ba  lea     r13, WPP_GLOBAL_Control
0x1800125c1  cmp     rcx, r13
0x1800125c4  jz      short loc_1800125D0
0x1800125c6  test    byte ptr [rcx+1Ch], 1
0x1800125ca  jnz     loc_180012838
0x1800125d0  mov     [rsp+78h+var_20], rbx
0x1800125d5  mov     [rsp+78h+var_28], rsi
0x1800125da  mov     [rsp+78h+var_30], rdi
0x1800125df  mov     [rsp+78h+var_38], r12
0x1800125e4  mov     [rsp+78h+var_40], r15
0x1800125e9  test    rbp, rbp
0x1800125ec  jz      loc_180012944
0x1800125f2  cmp     byte ptr [rbp+0], 0
0x1800125f6  jz      loc_180012944
0x1800125fc  test    r9, r9
0x1800125ff  jz      loc_180012944
0x180012605  test    r8, r8
0x180012608  jz      loc_180012944
0x18001260e  mov     qword ptr [r8], 0
0x180012615  mov     rsi, [r14+8]
0x180012619  lock inc dword ptr [rsi]
0x18001261c  mov     r12, [rsp+78h+arg_28]
0x180012624  movsxd  rcx, dword ptr [r12]
0x180012628  cmp     ecx, 3FFh
0x18001262e  jge     loc_180012831
0x180012634  mov     r15, [rsp+78h+arg_20]
0x18001263c  lea     eax, [rcx+1]
0x18001263f  mov     [r12], eax
0x180012643  mov     dword ptr [r15+rcx*4+4], 0
0x18001264c  cmp     dword ptr [r12], 3FFh
0x180012654  jge     loc_180012826
0x18001265a  cmp     byte ptr [rbp+0], 0
0x18001265e  jz      loc_1800128C2
0x180012664  mov     eax, [rsi+0Ch]
0x180012667  test    eax, eax
0x180012669  jz      loc_18001281F
0x18001266f  xor     r13d, r13d
0x180012672  lea     ebx, [rax-1]
0x180012675  xor     edi, edi
0x180012677  cmp     edi, ebx
0x180012679  jg      loc_180012750
0x18001267f  mov     rcx, [rsi+10h]
0x180012683  lea     eax, [rbx+rdi]
0x180012686  mov     r14, [rsi+30h]
0x18001268a  cdq
0x18001268b  sub     eax, edx
0x18001268d  mov     rdx, rbp
0x180012690  sar     eax, 1
0x180012692  mov     r13d, eax
0x180012695  movzx   eax, ax
0x180012698  mov     [rsp+78h+var_58], rax
0x18001269d  movzx   r11d, word ptr [rcx+rax*2]
0x1800126a2  mov     rcx, [rsi+40h]
0x1800126a6  movzx   r10d, word ptr [r14+r11*2]
0x1800126ab  inc     r11w
0x1800126af  mov     rbp, [rcx+18h]
0x1800126b3  mov     r15, [rcx+8]
0x1800126b7  movzx   eax, r11w
0x1800126bb  movzx   ecx, word ptr [r14+rax*2]
0x1800126c0  mov     eax, 0FFFFh
0x1800126c5  movzx   r8d, word ptr [r15+rcx*2]
0x1800126ca  add     r8, rbp
0x1800126cd  add     r10w, ax
0x1800126d1  movsx   ecx, byte ptr [r8]
0x1800126d5  inc     r8
0x1800126d8  movsx   eax, byte ptr [rdx]
0x1800126db  mov     r9d, ecx
0x1800126de  test    cl, cl
0x1800126e0  jz      short loc_1800126F6
0x1800126e2  mov     ecx, eax
0x1800126e4  sub     ecx, r9d
0x1800126e7  jnz     short loc_180012722
0x1800126e9  test    al, al
0x1800126eb  jz      loc_18001286C
0x1800126f1  inc     rdx
0x1800126f4  jmp     short loc_1800126D1
0x1800126f6  test    r10w, r10w
0x1800126fa  jz      short loc_1800126E2
0x1800126fc  inc     r11w
0x180012700  mov     r9d, 5Ch ; '\'
0x180012706  movzx   ecx, r11w
0x18001270a  movzx   ecx, word ptr [r14+rcx*2]
0x18001270f  movzx   r8d, word ptr [r15+rcx*2]
0x180012714  mov     ecx, 0FFFFh
0x180012719  add     r8, rbp
0x18001271c  add     r10w, cx
0x180012720  jmp     short loc_1800126E2
0x180012722  test    ecx, ecx
0x180012724  jns     short loc_180012737
0x180012726  mov     rbp, [rsp+78h+arg_8]
0x18001272e  lea     ebx, [r13-1]
0x180012732  jmp     loc_180012677
0x180012737  jle     loc_1800127DF
0x18001273d  mov     rbp, [rsp+78h+arg_8]
0x180012745  inc     r13d
0x180012748  mov     edi, r13d
0x18001274b  jmp     loc_180012677
0x180012750  mov     r9, [rsp+78h+arg_18]
0x180012758  movzx   eax, r13w
0x18001275c  mov     r14, [rsp+78h+arg_0]
0x180012764  lea     r13, WPP_GLOBAL_Control
0x18001276b  mov     r15, [rsp+78h+arg_20]
0x180012773  mov     rcx, r9
0x180012776  mov     [rcx], ax
0x180012779  movzx   edx, word ptr [r9]
0x18001277d  mov     rax, [rsi+28h]
0x180012781  mov     edi, [rax+rdx*4]
0x180012784  cmp     edi, 0FFFFFFFFh
0x180012787  jz      loc_180012826
0x18001278d  mov     ebx, [rsi+4]
0x180012790  mov     rcx, rsi; this
0x180012793  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180012798  movsxd  rcx, dword ptr [r12]
0x18001279c  lea     r9, [rsp+78h+var_58]; struct SIdxKeyTable **
0x1800127a1  xor     r8d, r8d; bool
0x1800127a4  mov     [rsp+78h+var_58], 0
0x1800127ad  mov     edx, edi; unsigned int
0x1800127af  lea     eax, [rcx+1]
0x1800127b2  mov     [r12], eax
0x1800127b6  mov     [r15+rcx*4+4], ebx
0x1800127bb  mov     rcx, r14; this
0x1800127be  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x1800127c3  mov     ebx, eax
0x1800127c5  test    eax, eax
0x1800127c7  jnz     loc_18001287A
0x1800127cd  mov     rsi, [rsp+78h+var_58]
0x1800127d2  mov     r9, [rsp+78h+arg_18]
0x1800127da  jmp     loc_18001264C
0x1800127df  mov     rax, [rsp+78h+arg_18]
0x1800127e7  mov     rcx, [rsp+78h+var_58]
0x1800127ec  mov     [rax], cx
0x1800127ef  mov     rax, [rsp+78h+arg_10]
0x1800127f7  mov     [rax], rsi
0x1800127fa  xor     eax, eax
0x1800127fc  mov     r15, [rsp+78h+var_40]
0x180012801  mov     r12, [rsp+78h+var_38]
0x180012806  mov     rdi, [rsp+78h+var_30]
0x18001280b  mov     rsi, [rsp+78h+var_28]
0x180012810  mov     rbx, [rsp+78h+var_20]
0x180012815  add     rsp, 60h
0x180012819  pop     r14
0x18001281b  pop     r13
0x18001281d  pop     rbp
0x18001281e  retn
0x18001281f  xor     eax, eax
0x180012821  jmp     loc_180012773
0x180012826  mov     rax, [rsp+78h+arg_10]
0x18001282e  mov     [rax], rsi
0x180012831  mov     eax, 490h
0x180012836  jmp     short loc_1800127FC
0x180012838  cmp     byte ptr [rcx+19h], 5
0x18001283c  jb      loc_1800125D0
0x180012842  mov     rcx, [rcx+10h]
0x180012846  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18001284d  mov     edx, 70h ; 'p'
0x180012852  call    WPP_SF_
0x180012857  mov     r9, [rsp+78h+arg_18]
0x18001285f  mov     r8, [rsp+78h+arg_10]
0x180012867  jmp     loc_1800125D0
0x18001286c  test    r9d, r9d
0x18001286f  jz      loc_1800127DF
0x180012875  jmp     loc_1800126F1
0x18001287a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012880  mov     rcx, rax
0x180012883  mov     edx, ebx
0x180012885  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001288b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012892  cmp     rcx, r13
0x180012895  jz      short loc_1800128BB
0x180012897  test    byte ptr [rcx+1Ch], 1
0x18001289b  jz      short loc_1800128BB
0x18001289d  cmp     byte ptr [rcx+19h], 2
0x1800128a1  jb      short loc_1800128BB
0x1800128a3  mov     rcx, [rcx+10h]
0x1800128a7  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800128ae  mov     edx, 73h ; 's'
0x1800128b3  mov     r9d, ebx
0x1800128b6  call    WPP_SF_d
0x1800128bb  mov     eax, ebx
0x1800128bd  jmp     loc_1800127FC
0x1800128c2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800128c8  mov     rcx, rax
0x1800128cb  mov     edx, 57h ; 'W'
0x1800128d0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800128d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128dd  cmp     rcx, r13
0x1800128e0  jz      short loc_180012909
0x1800128e2  test    byte ptr [rcx+1Ch], 1
0x1800128e6  jz      short loc_180012909
0x1800128e8  cmp     byte ptr [rcx+19h], 2
0x1800128ec  jb      short loc_180012909
0x1800128ee  mov     rcx, [rcx+10h]
0x1800128f2  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800128f9  mov     edx, 5Eh ; '^'
0x1800128fe  mov     r9d, 57h ; 'W'
0x180012904  call    WPP_SF_d
0x180012909  mov     rcx, rsi; this
0x18001290c  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180012911  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012917  mov     rcx, rax
0x18001291a  mov     edx, 57h ; 'W'
0x18001291f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001292c  cmp     rcx, r13
0x18001292f  jz      short loc_18001298B
0x180012931  test    byte ptr [rcx+1Ch], 1
0x180012935  jz      short loc_18001298B
0x180012937  cmp     byte ptr [rcx+19h], 2
0x18001293b  jb      short loc_18001298B
0x18001293d  mov     edx, 72h ; 'r'
0x180012942  jmp     short loc_180012975
0x180012944  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001294a  mov     rcx, rax
0x18001294d  mov     edx, 57h ; 'W'
0x180012952  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012958  mov     rcx, cs:WPP_GLOBAL_Control
0x18001295f  cmp     rcx, r13
0x180012962  jz      short loc_18001298B
0x180012964  test    byte ptr [rcx+1Ch], 1
0x180012968  jz      short loc_18001298B
0x18001296a  cmp     byte ptr [rcx+19h], 2
0x18001296e  jb      short loc_18001298B
0x180012970  mov     edx, 71h ; 'q'
0x180012975  mov     rcx, [rcx+10h]
0x180012979  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180012980  mov     r9d, 57h ; 'W'
0x180012986  call    WPP_SF_d
0x18001298b  mov     eax, 57h ; 'W'
0x180012990  jmp     loc_1800127FC
```
