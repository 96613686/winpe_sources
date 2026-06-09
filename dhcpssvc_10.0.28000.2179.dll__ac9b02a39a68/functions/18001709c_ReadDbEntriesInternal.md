# ReadDbEntriesInternal

- ea: `0x18001709c`
- end: `0x180017591`
- name: `ReadDbEntriesInternal`
- size: `1269`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180016a74`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x180015578`
- `0x1800165a0`
- `0x18001709c`
- `0x180017598`
- `0x18008f2a0`
- `0x180094a7c`
- `0x180094b48`
- `0x1800962b0`
- `0x1800cda7a`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800170ea`
- `ESENT!JetSetCurrentIndex` at `0x1800170ea`
- `ESENT!JetMove` at `0x18001714c`
- `ESENT!JetMove` at `0x18001735f`
- `ESENT!JetMove` at `0x18001714c`
- `ESENT!JetMove` at `0x18001735f`
- `KERNEL32!HeapAlloc` at `0x1800171e4`
- `KERNEL32!HeapAlloc` at `0x180017285`
- `KERNEL32!HeapAlloc` at `0x1800171e4`
- `KERNEL32!HeapAlloc` at `0x180017285`
- `KERNEL32!HeapFree` at `0x1800171c6`
- `KERNEL32!HeapFree` at `0x180017342`
- `KERNEL32!HeapFree` at `0x180017466`
- `KERNEL32!HeapFree` at `0x1800174c3`
- `KERNEL32!HeapFree` at `0x1800174db`
- `KERNEL32!HeapFree` at `0x1800171c6`
- `KERNEL32!HeapFree` at `0x180017342`
- `KERNEL32!HeapFree` at `0x180017466`
- `KERNEL32!HeapFree` at `0x1800174c3`
- `KERNEL32!HeapFree` at `0x1800174db`

## string_xrefs

- `0x18001715a`: `C:JetMoveFirst2`
- `0x18001736d`: `C:JetMove2`

## pseudocode

```c
__int64 __fastcall ReadDbEntriesInternal(JET_SESID sesid, __int64 a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  void *v9; // rdi
  unsigned int v10; // r12d
  void *v11; // rax
  unsigned int DbEntry; // eax
  _OWORD *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r13
  void *v17; // rcx
  int v18; // esi
  int v19; // r12d
  _QWORD *v20; // rdi
  unsigned int v21; // eax
  void *v22; // r8
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v28[9]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 lpMem; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  int v32; // [rsp+160h] [rbp+60h]
  int v33; // [rsp+168h] [rbp+68h]

  memset_0(v28, 0, 0xA8u);
  v33 = 0;
  v32 = 0;
  v27 = 0;
  v3 = JetSetCurrentIndex(sesid, DbcfgTbl, 0);
  v4 = DhcpMapJetError(v3, "C:SetIndex2");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return v4;
    v6 = 36;
    goto LABEL_65;
  }
  v7 = JetMove(sesid, DbcfgTbl, 0x80000000, 0);
  v8 = DhcpMapJetError(v7, "C:JetMoveFirst2");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v8);
  v24 = 0;
  v25 = 0;
  do
  {
    v9 = 0;
    v10 = 512;
    do
    {
      if ( v9 )
        HeapFree(gDhcpHeap, 0, v9);
      v10 *= 2;
      v11 = HeapAlloc(gDhcpHeap, 8u, v10);
      v9 = v11;
      if ( !v11 )
      {
        v4 = 8;
        goto LABEL_62;
      }
      DbEntry = ReadDbEntry(sesid, v28, v11, v10);
      v4 = DbEntry;
    }
    while ( DbEntry == 122 );
    if ( (v28[0] & 1) == 0 || (v28[0] & 2) == 0 )
    {
      if ( !DbEntry )
        v4 = 1359;
LABEL_44:
      HeapFree(gDhcpHeap, 0, v9);
      if ( v4 == 259 )
      {
LABEL_45:
        v16 = a2;
        v4 = 0;
        *(_DWORD *)(a2 + 152) = DWORD1(v28[0]);
        goto LABEL_30;
      }
LABEL_62:
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
        return v4;
      v6 = 38;
LABEL_65:
      WPP_SF_D(v5[2], v6, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v4);
      return v4;
    }
    if ( DbEntry )
      goto LABEL_44;
    *(_QWORD *)&lpMem = v9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids);
    if ( (unsigned int)AddDbEntryEx(a2, v28) == 2 )
    {
      v4 = 8;
      v13 = HeapAlloc(gDhcpHeap, 8u, 0xA8u);
      v27 = v13;
      if ( !v13 )
        return v4;
      *v13 = v28[0];
      v13[1] = v28[1];
      v13[2] = v28[2];
      v13[3] = v28[3];
      v13[4] = v28[4];
      v13[5] = v28[5];
      v13[6] = v28[6];
      v13[7] = v28[7];
      v13[8] = v28[8];
      v13[9] = lpMem;
      *((_QWORD *)v13 + 20) = v30;
      v4 = MemArrayAddElement(&v24, v13);
      if ( v4 )
      {
LABEL_23:
        if ( v25 )
          MemFree(v25);
        return v4;
      }
    }
    else if ( (_QWORD)lpMem )
    {
      HeapFree(gDhcpHeap, 0, (LPVOID)lpMem);
    }
    v14 = JetMove(sesid, DbcfgTbl, 1, 0);
    v15 = DhcpMapJetError(v14, "C:JetMove2");
    v4 = v15;
  }
  while ( !v15 );
  if ( v15 == 259 )
    goto LABEL_45;
  v16 = a2;
LABEL_30:
  v17 = WPP_GLOBAL_Control;
  v18 = v24;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids,
      (unsigned int)v24);
LABEL_33:
  if ( v18 )
  {
    v19 = v32;
    v26 = 0;
    while ( 1 )
    {
      --v18;
      MemArrayDelElement(&v24, &v26, &v27);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids);
      }
      v20 = v27;
      v21 = AddDbEntryEx(v16, v27);
      v4 = v21;
      if ( v21 == 2 )
      {
        if ( v32 != 4 )
        {
          v4 = MemArrayAddElement(&v24, v20);
          if ( v4 )
            goto LABEL_23;
          goto LABEL_52;
        }
      }
      else if ( !v21 )
      {
        goto LABEL_49;
      }
      v33 = 1;
      if ( v20 )
      {
        v4 = DeleteRecord(*((unsigned int *)v20 + 1));
LABEL_49:
        v22 = (void *)v20[18];
        if ( v22 )
          HeapFree(gDhcpHeap, 0, v22);
        HeapFree(gDhcpHeap, 0, v20);
      }
LABEL_52:
      if ( !v18 )
      {
        ++v32;
        if ( (unsigned int)(v19 + 1) < 5 )
        {
          v18 = v24;
          goto LABEL_33;
        }
        break;
      }
    }
  }
  if ( v33 )
    DhcpReportEventW(v17, 1065, 1, 0, 0, 0, 0);
  if ( v4 == 2 )
  {
    if ( v25 )
      MemFree(v25);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001709c  mov     [rsp-8+arg_8], rdx
0x1800170a1  push    rbp
0x1800170a2  push    rbx
0x1800170a3  push    rsi
0x1800170a4  push    rdi
0x1800170a5  push    r12
0x1800170a7  push    r13
0x1800170a9  push    r14
0x1800170ab  lea     rbp, [rsp-10h]
0x1800170b0  sub     rsp, 110h
0x1800170b7  mov     r13, rcx
0x1800170ba  xor     edx, edx; Val
0x1800170bc  lea     rcx, [rsp+140h+var_E0]; void *
0x1800170c1  mov     r8d, 0A8h; Size
0x1800170c7  call    memset_0
0x1800170cc  mov     rdx, cs:DbcfgTbl
0x1800170d3  xor     eax, eax
0x1800170d5  xor     r8d, r8d
0x1800170d8  mov     [rbp+40h+arg_18], eax
0x1800170db  mov     rcx, r13
0x1800170de  mov     [rbp+40h+arg_10], eax
0x1800170e1  mov     [rsp+140h+var_E8], 0
0x1800170ea  call    cs:__imp_JetSetCurrentIndex
0x1800170f1  nop     dword ptr [rax+rax+00h]
0x1800170f6  mov     ecx, eax
0x1800170f8  lea     rdx, aCSetindex2; "C:SetIndex2"
0x1800170ff  call    DhcpMapJetError
0x180017104  mov     ebx, eax
0x180017106  test    eax, eax
0x180017108  jz      short loc_180017139
0x18001710a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017111  lea     r14, WPP_GLOBAL_Control
0x180017118  cmp     rcx, r14
0x18001711b  jz      loc_18001757C
0x180017121  mov     esi, 800h
0x180017126  test    [rcx+1Ch], esi
0x180017129  jz      loc_18001757C
0x18001712f  mov     edx, 24h ; '$'
0x180017134  jmp     loc_180017569
0x180017139  mov     rdx, cs:DbcfgTbl; tableid
0x180017140  xor     r9d, r9d; grbit
0x180017143  mov     r8d, 80000000h; cRow
0x180017149  mov     rcx, r13; sesid
0x18001714c  call    cs:__imp_JetMove
0x180017153  nop     dword ptr [rax+rax+00h]
0x180017158  mov     ecx, eax
0x18001715a  lea     rdx, aCJetmovefirst2; "C:JetMoveFirst2"
0x180017161  call    DhcpMapJetError
0x180017166  mov     rcx, cs:WPP_GLOBAL_Control
0x18001716d  lea     r14, WPP_GLOBAL_Control
0x180017174  mov     esi, 800h
0x180017179  cmp     rcx, r14
0x18001717c  jz      short loc_18001719B
0x18001717e  test    [rcx+1Ch], esi
0x180017181  jz      short loc_18001719B
0x180017183  mov     rcx, [rcx+10h]
0x180017187  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x18001718e  mov     edx, 25h ; '%'
0x180017193  mov     r9d, eax
0x180017196  call    WPP_SF_D
0x18001719b  mov     [rsp+140h+var_100], 0
0x1800171a4  mov     [rsp+140h+var_F8], 0
0x1800171ad  xor     edi, edi
0x1800171af  mov     r12d, 200h
0x1800171b5  test    rdi, rdi
0x1800171b8  jz      short loc_1800171D2
0x1800171ba  mov     rcx, cs:gDhcpHeap; hHeap
0x1800171c1  mov     r8, rdi; lpMem
0x1800171c4  xor     edx, edx; dwFlags
0x1800171c6  call    cs:__imp_HeapFree
0x1800171cd  nop     dword ptr [rax+rax+00h]
0x1800171d2  mov     rcx, cs:gDhcpHeap; hHeap
0x1800171d9  add     r12d, r12d
0x1800171dc  mov     r8d, r12d; dwBytes
0x1800171df  mov     edx, 8; dwFlags
0x1800171e4  call    cs:__imp_HeapAlloc
0x1800171eb  nop     dword ptr [rax+rax+00h]
0x1800171f0  mov     rdi, rax
0x1800171f3  test    rax, rax
0x1800171f6  jz      loc_18001754E
0x1800171fc  mov     r9d, r12d; cbData
0x1800171ff  lea     rdx, [rsp+140h+var_E0]; void *
0x180017204  mov     r8, rax; void *
0x180017207  mov     rcx, r13; sesid
0x18001720a  call    ReadDbEntry
0x18001720f  mov     ebx, eax
0x180017211  cmp     eax, 7Ah ; 'z'
0x180017214  jz      short loc_1800171B5
0x180017216  test    [rsp+140h+var_E0], 1
0x18001721b  jz      loc_180017450
0x180017221  test    [rsp+140h+var_E0], 2
0x180017226  jz      loc_180017450
0x18001722c  test    eax, eax
0x18001722e  jnz     loc_18001745A
0x180017234  mov     qword ptr [rbp+40h+lpMem], rdi
0x180017238  mov     rcx, cs:WPP_GLOBAL_Control
0x18001723f  cmp     rcx, r14
0x180017242  jz      short loc_18001725C
0x180017244  test    [rcx+1Ch], esi
0x180017247  jz      short loc_18001725C
0x180017249  mov     rcx, [rcx+10h]
0x18001724d  lea     edx, [rax+20h]
0x180017250  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017257  call    WPP_SF_
0x18001725c  mov     rcx, [rbp+40h+arg_8]
0x180017260  lea     rdx, [rsp+140h+var_E0]
0x180017265  call    AddDbEntryEx
0x18001726a  cmp     eax, 2
0x18001726d  jnz     loc_180017330
0x180017273  mov     rcx, cs:gDhcpHeap; hHeap
0x18001727a  lea     ebx, [rax+6]
0x18001727d  mov     edx, ebx; dwFlags
0x18001727f  mov     r8d, 0A8h; dwBytes
0x180017285  call    cs:__imp_HeapAlloc
0x18001728c  nop     dword ptr [rax+rax+00h]
0x180017291  mov     [rsp+140h+var_E8], rax
0x180017296  mov     rdx, rax
0x180017299  test    rax, rax
0x18001729c  jz      loc_18001757C
0x1800172a2  lea     rax, [rsp+140h+var_E0]
0x1800172a7  movups  xmm0, xmmword ptr [rax]
0x1800172aa  lea     r8d, [rbx+78h]
0x1800172ae  lea     rcx, [r8+rdx]
0x1800172b2  movups  xmmword ptr [rdx], xmm0
0x1800172b5  movups  xmm1, xmmword ptr [rax+10h]
0x1800172b9  movups  xmmword ptr [rdx+10h], xmm1
0x1800172bd  movups  xmm0, xmmword ptr [rax+20h]
0x1800172c1  movups  xmmword ptr [rdx+20h], xmm0
0x1800172c5  movups  xmm1, xmmword ptr [rax+30h]
0x1800172c9  movups  xmmword ptr [rdx+30h], xmm1
0x1800172cd  movups  xmm0, xmmword ptr [rax+40h]
0x1800172d1  movups  xmmword ptr [rdx+40h], xmm0
0x1800172d5  movups  xmm1, xmmword ptr [rax+50h]
0x1800172d9  movups  xmmword ptr [rdx+50h], xmm1
0x1800172dd  movups  xmm0, xmmword ptr [rax+60h]
0x1800172e1  movups  xmmword ptr [rdx+60h], xmm0
0x1800172e5  movups  xmm1, xmmword ptr [rax+70h]
0x1800172e9  movups  xmmword ptr [rcx-10h], xmm1
0x1800172ed  movups  xmm0, xmmword ptr [rax+r8]
0x1800172f2  movups  xmmword ptr [rcx], xmm0
0x1800172f5  movups  xmm1, xmmword ptr [rax+r8+10h]
0x1800172fb  movups  xmmword ptr [rcx+10h], xmm1
0x1800172ff  mov     rax, [rax+r8+20h]
0x180017304  mov     [rcx+20h], rax
0x180017308  lea     rcx, [rsp+140h+var_100]
0x18001730d  call    MemArrayAddElement
0x180017312  mov     ebx, eax
0x180017314  test    eax, eax
0x180017316  jz      short loc_18001734E
0x180017318  mov     rcx, [rsp+140h+var_F8]; lpMem
0x18001731d  test    rcx, rcx
0x180017320  jz      loc_18001757C
0x180017326  call    MemFree
0x18001732b  jmp     loc_18001757C
0x180017330  mov     r8, qword ptr [rbp+40h+lpMem]; lpMem
0x180017334  test    r8, r8
0x180017337  jz      short loc_18001734E
0x180017339  mov     rcx, cs:gDhcpHeap; hHeap
0x180017340  xor     edx, edx; dwFlags
0x180017342  call    cs:__imp_HeapFree
0x180017349  nop     dword ptr [rax+rax+00h]
0x18001734e  mov     rdx, cs:DbcfgTbl; tableid
0x180017355  xor     r9d, r9d; grbit
0x180017358  mov     rcx, r13; sesid
0x18001735b  lea     r8d, [r9+1]; cRow
0x18001735f  call    cs:__imp_JetMove
0x180017366  nop     dword ptr [rax+rax+00h]
0x18001736b  mov     ecx, eax
0x18001736d  lea     rdx, aCJetmove2; "C:JetMove2"
0x180017374  call    DhcpMapJetError
0x180017379  mov     ebx, eax
0x18001737b  test    eax, eax
0x18001737d  jz      loc_1800171AD
0x180017383  cmp     eax, 103h
0x180017388  jz      loc_18001747E
0x18001738e  mov     r13, [rbp+40h+arg_8]
0x180017392  mov     rcx, cs:WPP_GLOBAL_Control
0x180017399  mov     esi, dword ptr [rsp+140h+var_100]
0x18001739d  cmp     rcx, r14
0x1800173a0  jz      short loc_1800173C3
0x1800173a2  test    dword ptr [rcx+1Ch], 10000000h
0x1800173a9  jz      short loc_1800173C3
0x1800173ab  mov     rcx, [rcx+10h]
0x1800173af  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x1800173b6  mov     edx, 27h ; '''
0x1800173bb  mov     r9d, esi
0x1800173be  call    WPP_SF_D
0x1800173c3  test    esi, esi
0x1800173c5  jz      loc_180017505
0x1800173cb  mov     r12d, [rbp+40h+arg_10]
0x1800173cf  mov     [rsp+140h+var_F0], 0
0x1800173d7  dec     esi
0x1800173d9  lea     r8, [rsp+140h+var_E8]
0x1800173de  lea     rdx, [rsp+140h+var_F0]
0x1800173e3  lea     rcx, [rsp+140h+var_100]
0x1800173e8  call    MemArrayDelElement
0x1800173ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173f4  cmp     rcx, r14
0x1800173f7  jz      short loc_180017417
0x1800173f9  test    dword ptr [rcx+1Ch], 10000000h
0x180017400  jz      short loc_180017417
0x180017402  mov     rcx, [rcx+10h]
0x180017406  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x18001740d  mov     edx, 28h ; '('
0x180017412  call    WPP_SF_
0x180017417  mov     rdi, [rsp+140h+var_E8]
0x18001741c  mov     rcx, r13
0x18001741f  mov     rdx, rdi
0x180017422  call    AddDbEntryEx
0x180017427  mov     ebx, eax
0x180017429  cmp     eax, 2
0x18001742c  jnz     short loc_180017494
0x18001742e  cmp     r12d, 4
0x180017432  jz      short loc_180017498
0x180017434  mov     rdx, rdi
0x180017437  lea     rcx, [rsp+140h+var_100]
0x18001743c  call    MemArrayAddElement
0x180017441  mov     ebx, eax
0x180017443  test    eax, eax
0x180017445  jnz     loc_180017318
0x18001744b  jmp     loc_1800174E7
0x180017450  test    ebx, ebx
0x180017452  mov     eax, 54Fh
0x180017457  cmovz   ebx, eax
0x18001745a  mov     rcx, cs:gDhcpHeap; hHeap
0x180017461  mov     r8, rdi; lpMem
0x180017464  xor     edx, edx; dwFlags
0x180017466  call    cs:__imp_HeapFree
0x18001746d  nop     dword ptr [rax+rax+00h]
0x180017472  cmp     ebx, 103h
0x180017478  jnz     loc_180017553
0x18001747e  mov     r13, [rbp+40h+arg_8]
0x180017482  xor     ebx, ebx
0x180017484  mov     eax, [rsp+140h+var_DC]
0x180017488  mov     [r13+98h], eax
0x18001748f  jmp     loc_180017392
0x180017494  test    eax, eax
0x180017496  jz      short loc_1800174AE
0x180017498  mov     [rbp+40h+arg_18], 1
0x18001749f  test    rdi, rdi
0x1800174a2  jz      short loc_1800174E7
0x1800174a4  mov     ecx, [rdi+4]
0x1800174a7  call    DeleteRecord
0x1800174ac  mov     ebx, eax
0x1800174ae  mov     r8, [rdi+90h]; lpMem
0x1800174b5  test    r8, r8
0x1800174b8  jz      short loc_1800174CF
0x1800174ba  mov     rcx, cs:gDhcpHeap; hHeap
0x1800174c1  xor     edx, edx; dwFlags
0x1800174c3  call    cs:__imp_HeapFree
0x1800174ca  nop     dword ptr [rax+rax+00h]
0x1800174cf  mov     rcx, cs:gDhcpHeap; hHeap
0x1800174d6  mov     r8, rdi; lpMem
0x1800174d9  xor     edx, edx; dwFlags
0x1800174db  call    cs:__imp_HeapFree
0x1800174e2  nop     dword ptr [rax+rax+00h]
0x1800174e7  test    esi, esi
0x1800174e9  jnz     loc_1800173D7
0x1800174ef  lea     eax, [r12+1]
0x1800174f4  mov     [rbp+40h+arg_10], eax
0x1800174f7  cmp     eax, 5
0x1800174fa  jnb     short loc_180017505
0x1800174fc  mov     esi, dword ptr [rsp+140h+var_100]
0x180017500  jmp     loc_1800173C3
0x180017505  cmp     [rbp+40h+arg_18], 0
0x180017509  jz      short loc_180017536
0x18001750b  xor     r9d, r9d
0x18001750e  mov     [rsp+140h+var_110], 0
0x180017517  mov     [rsp+140h+var_118], 0
0x180017520  mov     edx, 429h
0x180017525  mov     [rsp+140h+var_120], 0
0x18001752d  lea     r8d, [r9+1]
0x180017531  call    DhcpReportEventW
0x180017536  cmp     ebx, 2
0x180017539  jnz     short loc_18001757C
0x18001753b  mov     rcx, [rsp+140h+var_F8]; lpMem
0x180017540  test    rcx, rcx
0x180017543  jz      short loc_18001754A
0x180017545  call    MemFree
0x18001754a  xor     ebx, ebx
0x18001754c  jmp     short loc_18001757C
0x18001754e  mov     ebx, 8
0x180017553  mov     rcx, cs:WPP_GLOBAL_Control
0x18001755a  cmp     rcx, r14
0x18001755d  jz      short loc_18001757C
0x18001755f  test    [rcx+1Ch], esi
0x180017562  jz      short loc_18001757C
0x180017564  mov     edx, 26h ; '&'
0x180017569  mov     rcx, [rcx+10h]
0x18001756d  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017574  mov     r9d, ebx
0x180017577  call    WPP_SF_D
0x18001757c  mov     eax, ebx
0x18001757e  add     rsp, 110h
0x180017585  pop     r14
0x180017587  pop     r13
0x180017589  pop     r12
0x18001758b  pop     rdi
0x18001758c  pop     rsi
0x18001758d  pop     rbx
  ... truncated ...
```
