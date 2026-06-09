# Imapi2Utility::WaitForLongOperationToComplete(IDiscRecorder2Ex *,ulong,ulong,void *,void (*)(void *,ulong))

- ea: `0x1800481e8`
- end: `0x1800486dc`
- name: `?WaitForLongOperationToComplete@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KKPEAXP6AX1K@Z@Z`
- size: `1268`
- prototype: `int(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned int, unsigned int, void *, void (*)(void *, unsigned int))`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180039320`

## callees

- `0x18000ae3c`
- `0x18000f76c`
- `0x1800140f4`
- `0x180014180`
- `0x180016778`
- `0x1800236b4`
- `0x180023790`
- `0x18003a784`
- `0x1800481e8`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180048274`
- `KERNEL32!Sleep` at `0x180048274`
- `KERNEL32!GetTickCount` at `0x180048231`
- `KERNEL32!GetTickCount` at `0x180048314`
- `KERNEL32!GetTickCount` at `0x180048231`
- `KERNEL32!GetTickCount` at `0x180048314`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::WaitForLongOperationToComplete(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        __int64 a3,
        CMsftDiscFormat2TrackAtOnce *a4)
{
  CMsftDiscFormat2TrackAtOnce *v4; // rsi
  Imapi2Utility *v5; // r15
  unsigned int v6; // r13d
  int v7; // ebx
  int v8; // r14d
  int v9; // edi
  char v10; // al
  int v11; // r12d
  __int64 (__fastcall *v12)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, __int128 *, int, _BYTE *); // rax
  struct _SENSE_DATA *v13; // r9
  int *v14; // r9
  DWORD v15; // r15d
  unsigned int v16; // r14d
  unsigned int v17; // edi
  unsigned int v18; // ebx
  __int64 v19; // rax
  unsigned int v20; // esi
  PVOID *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // ecx
  PVOID *v25; // rcx
  PVOID v26; // rcx
  char v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[20]; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+72h] [rbp-8Eh]
  __int16 v31; // [rsp+76h] [rbp-8Ah]
  union _CDB *v32; // [rsp+78h] [rbp-88h]
  _OWORD v33[2]; // [rsp+80h] [rbp-80h] BYREF
  Imapi2Utility *v34; // [rsp+A0h] [rbp-60h]
  union _CDB v35; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v38; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[26]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&v28[4] = a4;
  memset(v33, 0, sizeof(v33));
  v4 = a4;
  v5 = this;
  v34 = this;
  v6 = 0;
  v7 = 0;
  *(_DWORD *)&v28[16] = GetTickCount();
  v8 = *(_DWORD *)&v28[16];
  v9 = 270;
  v10 = 0;
  *(_DWORD *)v28 = 270;
  memset(v39, 0, sizeof(v39));
  v27 = 0;
  v11 = 0;
  v38 = 0;
  while ( !v10 && v9 )
  {
    Sleep(0x3E8u);
    *(_DWORD *)&v28[12] = 0;
    v36 = 0;
    v12 = *(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, __int128 *, int, _BYTE *))(*(_QWORD *)v5 + 40LL);
    v37 = 0;
    LOBYTE(v37) = 81;
    memset(v39, 0, sizeof(v39));
    *(_WORD *)((char *)&v37 + 7) = 10752;
    v35 = 0;
    v38 = 0;
    v7 = v12(v5, &v37, 10, &v35, 10, &v38, 42, &v28[12]);
    if ( v7 == 11141632 )
    {
      if ( Imapi2Utility::IsSenseDataInTable(
             (Imapi2Utility *)&Imapi2Utility::AllowedSenseForLongOperations,
             (struct Imapi2Utility::_SENSE_STUFF *)3,
             (int)&v35,
             v13) )
      {
        v15 = (GetTickCount() - v8) / 0x3E8;
        if ( v15 >= 0x78 )
          v16 = 1;
        else
          v16 = 120 - v15;
        if ( (v35.CDB16.Control & 0x80u) == 0 )
          --v11;
        else
          *((_DWORD *)v33 + (v11 & 7)) = HIBYTE(v36) | ((unsigned __int8)v36 << 8);
        if ( v6 <= 1 )
        {
          v17 = *((_DWORD *)v33 + (v11 & 7));
          v18 = *((_DWORD *)v33 + (((_BYTE)v11 - 1) & 7));
          v19 = ((_BYTE)v11 - 2) & 7;
          v20 = *((_DWORD *)v33 + v19);
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_ddD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              42,
              &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
              v17,
              v18,
              *((_DWORD *)v33 + v19));
            v21 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 && v17 != 0xFFFF )
          {
            if ( v17 == v18 )
            {
              if ( v18 == v20 )
              {
                if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 3u )
                  WPP_SF_ddD(v21[2], 43, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v17, v18, v20);
                v6 = 255;
              }
            }
            else if ( v17 >= v18 )
            {
              if ( v17 > v18 )
              {
                if ( v18 >= v20 )
                {
                  v6 = 1;
                }
                else if ( v20 > 0x6000
                       && v18 < 0x2000
                       && (v20 != 0xFFFF || *((_DWORD *)v33 + (((_BYTE)v11 - 3) & 7)) != 0xFFFF) )
                {
                  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 3u )
                    WPP_SF_ddD(v21[2], 45, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v17, v18, v20);
                  v6 = 3;
                }
              }
            }
            else if ( v18 < v20 )
            {
              if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 3u )
                WPP_SF_ddD(v21[2], 44, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v17, v18, v20);
              v6 = 2;
            }
          }
          v4 = *(CMsftDiscFormat2TrackAtOnce **)&v28[4];
          v9 = *(_DWORD *)v28;
        }
        v22 = v11 & 7;
        v23 = 0x10000 - *((_DWORD *)v33 + v22);
        if ( v6 != 2 )
          v23 = *((_DWORD *)v33 + v22);
        if ( v6 - 1 <= 1 )
          v16 = (v15 << 16) / v23 - v15;
        WaitForLongOperationCallbackHelper(v4, v16);
        v8 = *(_DWORD *)&v28[16];
        v7 = 0;
        v5 = v34;
      }
      else
      {
        *(_DWORD *)v28 = -2147467259;
        Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v37, &v35, (const struct _SENSE_DATA *)v28, v14);
        v25 = (PVOID *)WPP_GLOBAL_Control;
        v7 = *(_DWORD *)v28;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 && *((_BYTE *)v25 + 25) >= 3u )
          {
            v26 = v25[2];
            v30 = 0;
            v29 = 18;
            v31 = 0;
            v32 = &v35;
            WPP_SF__HEX_(v26, 47, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, &v29);
          }
        }
      }
    }
    else
    {
      if ( v7 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
        }
        v10 = 1;
        v27 = 1;
        goto LABEL_52;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          (unsigned int)v7);
      }
    }
    v10 = v27;
LABEL_52:
    --v9;
    ++v11;
    *(_DWORD *)v28 = v9;
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800481e8  mov     [rsp-8+arg_8], rbx
0x1800481ed  push    rbp
0x1800481ee  push    rsi
0x1800481ef  push    rdi
0x1800481f0  push    r12
0x1800481f2  push    r13
0x1800481f4  push    r14
0x1800481f6  push    r15
0x1800481f8  lea     rbp, [rsp-10h]
0x1800481fd  sub     rsp, 110h
0x180048204  mov     rax, cs:__security_cookie
0x18004820b  xor     rax, rsp
0x18004820e  mov     [rbp+40h+var_40], rax
0x180048212  xorps   xmm0, xmm0
0x180048215  mov     qword ptr [rsp+140h+var_EC+4], r9
0x18004821a  movups  [rbp+40h+var_C0], xmm0
0x18004821e  mov     rsi, r9
0x180048221  mov     r15, rcx
0x180048224  movups  [rbp+40h+var_B0], xmm0
0x180048228  mov     [rbp+40h+var_A0], rcx
0x18004822c  xor     r13d, r13d
0x18004822f  xor     ebx, ebx
0x180048231  call    cs:__imp_GetTickCount
0x180048237  xorps   xmm0, xmm0
0x18004823a  mov     dword ptr [rsp+140h+var_EC+10h], eax
0x18004823e  mov     r14d, eax
0x180048241  mov     edi, 10Eh
0x180048246  xor     eax, eax
0x180048248  mov     dword ptr [rsp+140h+var_EC], edi
0x18004824c  movups  xmmword ptr [rbp+40h+var_60], xmm0
0x180048250  mov     [rsp+140h+var_F0], al
0x180048254  xor     r12d, r12d
0x180048257  movups  [rbp+40h+var_70], xmm0
0x18004825b  movups  xmmword ptr [rbp+40h+var_60+0Ah], xmm0
0x18004825f  test    al, al
0x180048261  jnz     loc_18004854F
0x180048267  test    edi, edi
0x180048269  jz      loc_18004854F
0x18004826f  mov     ecx, 3E8h; dwMilliseconds
0x180048274  call    cs:__imp_Sleep
0x18004827a  xor     eax, eax
0x18004827c  mov     dword ptr [rsp+140h+var_EC+0Ch], 0
0x180048284  xorps   xmm1, xmm1
0x180048287  mov     [rbp+40h+var_88], ax
0x18004828b  mov     rax, [r15]
0x18004828e  lea     rcx, [rsp+140h+var_EC+0Ch]
0x180048293  mov     [rsp+140h+var_108], rcx
0x180048298  lea     r9, [rbp+40h+var_98]
0x18004829c  lea     rcx, [rbp+40h+var_70]
0x1800482a0  mov     [rsp+140h+var_110], 2Ah ; '*'
0x1800482a8  mov     [rsp+140h+var_118], rcx
0x1800482ad  lea     rdx, [rbp+40h+var_80]
0x1800482b1  mov     rax, [rax+28h]
0x1800482b5  mov     ecx, 0Ah
0x1800482ba  xorps   xmm0, xmm0
0x1800482bd  mov     [rsp+140h+var_120], ecx
0x1800482c1  movups  [rbp+40h+var_80], xmm0
0x1800482c5  mov     r8d, ecx
0x1800482c8  mov     byte ptr [rbp+40h+var_80], 51h ; 'Q'
0x1800482cc  movups  xmmword ptr [rbp+40h+var_60], xmm1
0x1800482d0  mov     rcx, r15
0x1800482d3  mov     word ptr [rbp+40h+var_80+7], 2A00h
0x1800482d9  movups  xmmword ptr [rbp+40h+var_98], xmm0
0x1800482dd  movups  [rbp+40h+var_70], xmm1
0x1800482e1  movups  xmmword ptr [rbp+40h+var_60+0Ah], xmm1
0x1800482e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482ea  mov     ebx, eax
0x1800482ec  cmp     eax, 0AA0200h
0x1800482f1  jnz     loc_180048651
0x1800482f7  lea     r8, [rbp+40h+var_98]; int
0x1800482fb  mov     edx, 3; struct Imapi2Utility::_SENSE_STUFF *
0x180048300  lea     rcx, ?AllowedSenseForLongOperations@Imapi2Utility@@3PAU_SENSE_STUFF@1@A; this
0x180048307  call    ?IsSenseDataInTable@Imapi2Utility@@YAEPEAU_SENSE_STUFF@1@JPEAU_SENSE_DATA@@@Z; Imapi2Utility::IsSenseDataInTable(Imapi2Utility::_SENSE_STUFF *,long,_SENSE_DATA *)
0x18004830c  test    al, al
0x18004830e  jz      loc_180048578
0x180048314  call    cs:__imp_GetTickCount
0x18004831a  mov     ecx, eax
0x18004831c  mov     eax, 10624DD3h
0x180048321  sub     ecx, r14d
0x180048324  mul     ecx
0x180048326  mov     r15d, edx
0x180048329  shr     r15d, 6
0x18004832d  cmp     r15d, 78h ; 'x'
0x180048331  jnb     short loc_18004833E
0x180048333  mov     r14d, 78h ; 'x'
0x180048339  sub     r14d, r15d
0x18004833c  jmp     short loc_180048344
0x18004833e  mov     r14d, 1
0x180048344  cmp     byte ptr [rbp+40h+var_98+0Fh], 0
0x180048348  jge     short loc_180048363
0x18004834a  movzx   eax, byte ptr [rbp+40h+var_88+1]
0x18004834e  movzx   ecx, byte ptr [rbp+40h+var_88]
0x180048352  shl     ecx, 8
0x180048355  or      ecx, eax
0x180048357  mov     eax, r12d
0x18004835a  and     eax, 7
0x18004835d  mov     dword ptr [rbp+rax*4+40h+var_C0], ecx
0x180048361  jmp     short loc_180048366
0x180048363  dec     r12d
0x180048366  cmp     r13d, 1
0x18004836a  ja      loc_1800484F3
0x180048370  mov     eax, r12d
0x180048373  and     eax, 7
0x180048376  mov     edi, dword ptr [rbp+rax*4+40h+var_C0]
0x18004837a  lea     eax, [r12-1]
0x18004837f  and     eax, 7
0x180048382  mov     ebx, dword ptr [rbp+rax*4+40h+var_C0]
0x180048386  lea     eax, [r12-2]
0x18004838b  and     eax, 7
0x18004838e  mov     esi, dword ptr [rbp+rax*4+40h+var_C0]
0x180048392  mov     rcx, cs:WPP_GLOBAL_Control
0x180048399  lea     rdx, WPP_GLOBAL_Control
0x1800483a0  cmp     rcx, rdx
0x1800483a3  jz      short loc_1800483DF
0x1800483a5  test    byte ptr [rcx+1Ch], 4
0x1800483a9  jz      short loc_1800483DF
0x1800483ab  cmp     byte ptr [rcx+19h], 5
0x1800483af  jb      short loc_1800483DF
0x1800483b1  mov     rcx, [rcx+10h]
0x1800483b5  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800483bc  mov     edx, 2Ah ; '*'
0x1800483c1  mov     dword ptr [rsp+140h+var_118], esi
0x1800483c5  mov     r9d, edi
0x1800483c8  mov     [rsp+140h+var_120], ebx
0x1800483cc  call    WPP_SF_ddD
0x1800483d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483d8  lea     rdx, WPP_GLOBAL_Control
0x1800483df  test    edi, edi
0x1800483e1  jz      loc_1800484EA
0x1800483e7  mov     r8d, 0FFFFh
0x1800483ed  cmp     edi, r8d
0x1800483f0  jz      loc_1800484EA
0x1800483f6  cmp     edi, ebx
0x1800483f8  jnz     short loc_18004843E
0x1800483fa  cmp     ebx, esi
0x1800483fc  jnz     loc_1800484EA
0x180048402  cmp     rcx, rdx
0x180048405  jz      short loc_180048433
0x180048407  test    byte ptr [rcx+1Ch], 4
0x18004840b  jz      short loc_180048433
0x18004840d  cmp     byte ptr [rcx+19h], 3
0x180048411  jb      short loc_180048433
0x180048413  mov     rcx, [rcx+10h]
0x180048417  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004841e  mov     edx, 2Bh ; '+'
0x180048423  mov     dword ptr [rsp+140h+var_118], esi
0x180048427  mov     r9d, edi
0x18004842a  mov     [rsp+140h+var_120], ebx
0x18004842e  call    WPP_SF_ddD
0x180048433  mov     r13d, 0FFh
0x180048439  jmp     loc_1800484EA
0x18004843e  jnb     short loc_180048481
0x180048440  cmp     ebx, esi
0x180048442  jnb     loc_1800484EA
0x180048448  cmp     rcx, rdx
0x18004844b  jz      short loc_180048479
0x18004844d  test    byte ptr [rcx+1Ch], 4
0x180048451  jz      short loc_180048479
0x180048453  cmp     byte ptr [rcx+19h], 3
0x180048457  jb      short loc_180048479
0x180048459  mov     rcx, [rcx+10h]
0x18004845d  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180048464  mov     edx, 2Ch ; ','
0x180048469  mov     dword ptr [rsp+140h+var_118], esi
0x18004846d  mov     r9d, edi
0x180048470  mov     [rsp+140h+var_120], ebx
0x180048474  call    WPP_SF_ddD
0x180048479  mov     r13d, 2
0x18004847f  jmp     short loc_1800484EA
0x180048481  jbe     short loc_1800484EA
0x180048483  cmp     ebx, esi
0x180048485  jnb     short loc_1800484E4
0x180048487  cmp     esi, 6000h
0x18004848d  jbe     short loc_1800484EA
0x18004848f  cmp     ebx, 2000h
0x180048495  jnb     short loc_1800484EA
0x180048497  cmp     esi, r8d
0x18004849a  jnz     short loc_1800484AB
0x18004849c  lea     eax, [r12-3]
0x1800484a1  and     eax, 7
0x1800484a4  cmp     dword ptr [rbp+rax*4+40h+var_C0], r8d
0x1800484a9  jz      short loc_1800484EA
0x1800484ab  cmp     rcx, rdx
0x1800484ae  jz      short loc_1800484DC
0x1800484b0  test    byte ptr [rcx+1Ch], 4
0x1800484b4  jz      short loc_1800484DC
0x1800484b6  cmp     byte ptr [rcx+19h], 3
0x1800484ba  jb      short loc_1800484DC
0x1800484bc  mov     rcx, [rcx+10h]
0x1800484c0  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800484c7  mov     edx, 2Dh ; '-'
0x1800484cc  mov     dword ptr [rsp+140h+var_118], esi
0x1800484d0  mov     r9d, edi
0x1800484d3  mov     [rsp+140h+var_120], ebx
0x1800484d7  call    WPP_SF_ddD
0x1800484dc  mov     r13d, 3
0x1800484e2  jmp     short loc_1800484EA
0x1800484e4  mov     r13d, 1
0x1800484ea  mov     rsi, qword ptr [rsp+140h+var_EC+4]
0x1800484ef  mov     edi, dword ptr [rsp+140h+var_EC]
0x1800484f3  mov     eax, r12d
0x1800484f6  mov     ecx, 10000h
0x1800484fb  and     eax, 7
0x1800484fe  sub     ecx, dword ptr [rbp+rax*4+40h+var_C0]
0x180048502  cmp     r13d, 2
0x180048506  cmovnz  ecx, dword ptr [rbp+rax*4+40h+var_C0]
0x18004850b  lea     eax, [r13-1]
0x18004850f  cmp     eax, 1
0x180048512  ja      short loc_180048524
0x180048514  xor     edx, edx
0x180048516  mov     eax, r15d
0x180048519  shl     eax, 10h
0x18004851c  div     ecx
0x18004851e  mov     r14d, eax
0x180048521  sub     r14d, r15d
0x180048524  mov     edx, r14d; unsigned int
0x180048527  mov     rcx, rsi; this
0x18004852a  call    ?WaitForLongOperationCallbackHelper@@YAXPEAXK@Z; WaitForLongOperationCallbackHelper(void *,ulong)
0x18004852f  mov     r14d, dword ptr [rsp+140h+var_EC+10h]
0x180048534  xor     ebx, ebx
0x180048536  mov     r15, [rbp+40h+var_A0]
0x18004853a  mov     al, [rsp+140h+var_F0]
0x18004853e  dec     edi
0x180048540  inc     r12d
0x180048543  mov     dword ptr [rsp+140h+var_EC], edi
0x180048547  test    ebx, ebx
0x180048549  jns     loc_18004825F
0x18004854f  mov     eax, ebx
0x180048551  mov     rcx, [rbp+40h+var_40]
0x180048555  xor     rcx, rsp; StackCookie
0x180048558  call    __security_check_cookie
0x18004855d  mov     rbx, [rsp+140h+arg_8]
0x180048565  add     rsp, 110h
0x18004856c  pop     r15
0x18004856e  pop     r14
0x180048570  pop     r13
0x180048572  pop     r12
0x180048574  pop     rdi
0x180048575  pop     rsi
0x180048576  pop     rbp
0x180048577  retn
0x180048578  lea     r8, [rsp+140h+var_EC]; struct _SENSE_DATA *
0x18004857d  mov     dword ptr [rsp+140h+var_EC], 80004005h
0x180048585  lea     rdx, [rbp+40h+var_98]; union _CDB *
0x180048589  lea     rcx, [rbp+40h+var_80]; this
0x18004858d  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180048592  mov     rcx, cs:WPP_GLOBAL_Control
0x180048599  lea     rax, WPP_GLOBAL_Control
0x1800485a0  mov     ebx, dword ptr [rsp+140h+var_EC]
0x1800485a4  cmp     rcx, rax
0x1800485a7  jz      short loc_18004853A
0x1800485a9  test    byte ptr [rcx+1Ch], 4
0x1800485ad  jz      short loc_1800485F7
0x1800485af  cmp     byte ptr [rcx+19h], 3
0x1800485b3  jb      short loc_1800485F7
0x1800485b5  movzx   r8d, byte ptr [rbp+40h+var_98+0Ch]
0x1800485ba  mov     edx, 2Eh ; '.'
0x1800485bf  movzx   eax, byte ptr [rbp+40h+var_98+0Dh]
0x1800485c3  movzx   r9d, byte ptr [rbp+40h+var_98+2]
0x1800485c8  mov     rcx, [rcx+10h]
0x1800485cc  and     r9d, 0Fh
0x1800485d0  mov     [rsp+140h+var_110], ebx
0x1800485d4  mov     dword ptr [rsp+140h+var_118], eax
0x1800485d8  mov     [rsp+140h+var_120], r8d
0x1800485dd  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800485e4  call    WPP_SF_DDDd
0x1800485e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485f0  lea     rax, WPP_GLOBAL_Control
0x1800485f7  cmp     rcx, rax
0x1800485fa  jz      loc_18004853A
0x180048600  test    byte ptr [rcx+1Ch], 4
0x180048604  jz      loc_18004853A
0x18004860a  cmp     byte ptr [rcx+19h], 3
0x18004860e  jb      loc_18004853A
0x180048614  mov     rcx, [rcx+10h]
0x180048618  lea     r9, [rsp+140h+var_D0]
0x18004861d  xor     edx, edx
0x18004861f  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180048626  mov     eax, 12h
0x18004862b  mov     [rsp+140h+var_CE], edx
0x18004862f  mov     [rsp+140h+var_D0], ax
0x180048634  lea     rax, [rbp+40h+var_98]
0x180048638  mov     [rsp+140h+var_CA], dx
0x18004863d  mov     edx, 2Fh ; '/'
0x180048642  mov     [rsp+140h+var_C8], rax
0x180048647  call    WPP_SF__HEX_
0x18004864c  jmp     loc_18004853A
0x180048651  test    ebx, ebx
0x180048653  jns     short loc_18004869D
0x180048655  mov     rcx, cs:WPP_GLOBAL_Control
0x18004865c  lea     rax, WPP_GLOBAL_Control
0x180048663  cmp     rcx, rax
0x180048666  jz      loc_18004853A
0x18004866c  test    byte ptr [rcx+1Ch], 4
0x180048670  jz      loc_18004853A
0x180048676  cmp     byte ptr [rcx+19h], 3
0x18004867a  jb      loc_18004853A
0x180048680  mov     rcx, [rcx+10h]
0x180048684  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004868b  mov     edx, 30h ; '0'
  ... truncated ...
```
