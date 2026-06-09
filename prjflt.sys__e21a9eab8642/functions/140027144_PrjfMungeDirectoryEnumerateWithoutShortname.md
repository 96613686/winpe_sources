# PrjfMungeDirectoryEnumerateWithoutShortname

- ea: `0x140027144`
- end: `0x1400277eb`
- name: `PrjfMungeDirectoryEnumerateWithoutShortname`
- size: `1703`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400287d4`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000ba50`
- `0x14000ba70`
- `0x14000d128`
- `0x140021008`
- `0x14002106c`
- `0x1400210a8`
- `0x140021150`
- `0x140021198`
- `0x140027144`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithoutShortname(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        char a4,
        unsigned int *a5,
        unsigned int a6,
        char a7,
        unsigned int **a8,
        unsigned int *a9)
{
  _DWORD *v9; // rbx
  char v10; // r15
  unsigned __int64 v11; // r14
  unsigned int v12; // edi
  unsigned int v13; // esi
  __int64 v14; // r9
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  __int64 v17; // rdx
  unsigned int *v18; // r15
  unsigned int ULongFromUser; // eax
  unsigned int v20; // eax
  void *v21; // rcx
  void *v22; // rdx
  void *v23; // rcx
  unsigned int v24; // r14d
  unsigned int v25; // eax
  unsigned int *v26; // rcx
  unsigned int v27; // eax
  unsigned int *v28; // rcx
  void *v29; // rdx
  void *v30; // rcx
  unsigned int v31; // r13d
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned int *v34; // rcx
  unsigned int v35; // eax
  unsigned int *v36; // r15
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int *v40; // rcx
  void *v41; // rdx
  void *v42; // rcx
  unsigned int v43; // r13d
  unsigned int v44; // r12d
  __int64 v45; // rdx
  unsigned int *v46; // r15
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int *v50; // rcx
  void *v51; // rdx
  void *v52; // rcx
  int v53; // eax

  v9 = a3;
  v10 = a2;
  v11 = (unsigned int)a1;
  v12 = 0;
  v13 = 0;
  if ( (unsigned int)a1 > 0x3C || (a1 = 0x1000000000001006LL, !_bittest64(&a1, v11)) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (_DWORD)v11 != 1 )
  {
    if ( (_DWORD)v11 != 2 )
    {
      v14 = 10;
      if ( (_DWORD)v11 == 12 )
      {
        v24 = v9[15];
        v16 = v24 + 12;
        if ( a6 < v24 + 12 && (a6 < 0xC || !v10) )
          goto LABEL_149;
        if ( v24 >= a6 - 12 )
          v24 = a6 - 12;
        v25 = v9[1];
        v26 = a5 + 1;
        if ( a7 )
          RtlWriteULongToUser(v26, v25);
        else
          *v26 = v25;
        v27 = v9[15];
        v28 = a5 + 2;
        if ( a7 )
          RtlWriteULongToUser(v28, v27);
        else
          *v28 = v27;
        v29 = v9 + 22;
        v30 = a5 + 3;
        if ( a7 )
          RtlCopyToUser(v30, v29, v24);
        else
          RtlCopyVolatileMemory(v30, v29, v24);
        if ( a7 )
          RtlWriteULongToUser(a5, 0);
        else
          *a5 = 0;
        *a8 = a5;
        v13 = v24 + 12;
      }
      else
      {
        if ( (_DWORD)v11 != 60 )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(a2) = BYTE10(xmmword_14001A3D0) & 4;
          if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_sDL(
              786,
              a2,
              (_DWORD)a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              3,
              18,
              10,
              (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
              90,
              v11);
          MicrosoftTelemetryAssertTriggeredMsgKM("Unsupported FileInformationClass", a2, a3, v14);
          v12 = -1073741637;
          goto LABEL_149;
        }
        v15 = v9[15];
        v16 = v15 + 88;
        if ( a6 < v15 + 88 && (a6 < 0x58 || !v10) )
          goto LABEL_149;
        if ( v15 >= a6 - 88 )
          v15 = a6 - 88;
        if ( a7 )
          RtlCopyToUser(a5, v9, 0x58u);
        else
          RtlCopyVolatileMemory(a5, v9, 0x58u);
        if ( v9[17] == -1879048164 )
        {
          v17 = v9[14] & 0xFFFFE9FF;
          if ( (v9[14] & 0xFFFFE9FF) == 0 )
            v17 = 128;
          if ( a7 )
            RtlWriteULongToUser(a5 + 14, v17);
          else
            a5[14] = v17;
          if ( a7 )
            RtlWriteULongToUser(a5 + 17, 0);
          else
            a5[17] = 0;
        }
        if ( a4 )
        {
          v18 = a5 + 14;
          if ( a7 )
            ULongFromUser = RtlReadULongFromUser(a5 + 14);
          else
            ULongFromUser = *v18;
          v20 = ULongFromUser | 0x440000;
          if ( a7 )
            RtlWriteULongToUser(a5 + 14, v20);
          else
            *v18 = v20;
          if ( a7 )
            RtlWriteULong64ToUser(a5 + 12, 0);
          else
            *((_QWORD *)a5 + 6) = 0;
          v21 = a5 + 18;
          if ( a7 )
            RtlSetUserMemory(v21);
          else
            RtlSetVolatileMemory(v21, 255, 0x10u);
        }
        v22 = v9 + 22;
        v23 = a5 + 22;
        if ( a7 )
          RtlCopyToUser(v23, v22, v15);
        else
          RtlCopyVolatileMemory(v23, v22, v15);
        if ( a7 )
          RtlWriteULongToUser(a5, 0);
        else
          *a5 = 0;
        *a8 = a5;
        v13 = v15 + 88;
      }
      goto LABEL_67;
    }
    v31 = v9[15];
    v16 = v31 + 68;
    if ( a6 < v31 + 68 && (a6 < 0x44 || !v10) )
      goto LABEL_149;
    if ( v31 >= a6 - 68 )
      v31 = a6 - 68;
    if ( a7 )
      RtlCopyToUser(a5, v9, 0x38u);
    else
      RtlCopyVolatileMemory(a5, v9, 0x38u);
    v32 = (unsigned int)v9[14];
    if ( v9[17] == -1879048164 )
    {
      v33 = (unsigned int)v32 & 0xFFFFE9FF;
      if ( !(_DWORD)v33 )
        v33 = 128;
      if ( a7 )
        RtlWriteULongToUser(a5 + 14, v33);
      else
        a5[14] = v33;
      v34 = a5 + 16;
    }
    else
    {
      if ( a7 )
        RtlWriteULongToUser(a5 + 14, v32);
      else
        a5[14] = v32;
      v34 = a5 + 16;
      if ( (v9[14] & 0x400) != 0 )
      {
        v35 = v9[17];
        goto LABEL_85;
      }
    }
    v35 = v9[16];
LABEL_85:
    if ( a7 )
      RtlWriteULongToUser(v34, v35);
    else
      *v34 = v35;
    if ( a4 )
    {
      v36 = a5 + 14;
      if ( a7 )
        v37 = RtlReadULongFromUser(a5 + 14);
      else
        v37 = *v36;
      v38 = v37 | 0x440000;
      if ( a7 )
        RtlWriteULongToUser(a5 + 14, v38);
      else
        *v36 = v38;
      if ( a7 )
        RtlWriteULong64ToUser(a5 + 12, 0);
      else
        *((_QWORD *)a5 + 6) = 0;
    }
    v39 = v9[15];
    v40 = a5 + 15;
    if ( a7 )
      RtlWriteULongToUser(v40, v39);
    else
      *v40 = v39;
    v41 = v9 + 22;
    v42 = a5 + 17;
    if ( a7 )
      RtlCopyToUser(v42, v41, v31);
    else
      RtlCopyVolatileMemory(v42, v41, v31);
    if ( a7 )
      RtlWriteULongToUser(a5, 0);
    else
      *a5 = 0;
    *a8 = a5;
    v13 = v31 + 68;
LABEL_67:
    if ( v13 < v16 )
      v12 = -2147483643;
    goto LABEL_149;
  }
  v43 = v9[15];
  v44 = v43 + 64;
  if ( a6 >= v43 + 64 || a6 >= 0x40 && v10 )
  {
    if ( v43 >= a6 - 64 )
      v43 = a6 - 64;
    if ( a7 )
      RtlCopyToUser(a5, v9, 0x38u);
    else
      RtlCopyVolatileMemory(a5, v9, 0x38u);
    v45 = (unsigned int)v9[14];
    if ( v9[17] == -1879048164 )
    {
      v45 = (unsigned int)v45 & 0xFFFFE9FF;
      if ( !(_DWORD)v45 )
        v45 = 128;
    }
    if ( a7 )
      RtlWriteULongToUser(a5 + 14, v45);
    else
      a5[14] = v45;
    if ( a4 )
    {
      v46 = a5 + 14;
      if ( a7 )
        v47 = RtlReadULongFromUser(a5 + 14);
      else
        v47 = *v46;
      v48 = v47 | 0x440000;
      if ( a7 )
        RtlWriteULongToUser(a5 + 14, v48);
      else
        *v46 = v48;
      if ( a7 )
        RtlWriteULong64ToUser(a5 + 12, 0);
      else
        *((_QWORD *)a5 + 6) = 0;
    }
    v49 = v9[15];
    v50 = a5 + 15;
    if ( a7 )
      RtlWriteULongToUser(v50, v49);
    else
      *v50 = v49;
    v51 = v9 + 22;
    v52 = a5 + 16;
    if ( a7 )
      RtlCopyToUser(v52, v51, v43);
    else
      RtlCopyVolatileMemory(v52, v51, v43);
    if ( a7 )
      RtlWriteULongToUser(a5, 0);
    else
      *a5 = 0;
    *a8 = a5;
    v13 = v43 + 64;
    v53 = 0;
    if ( v43 + 64 < v44 )
      v53 = -2147483643;
    v12 = v53;
  }
LABEL_149:
  *a9 = v13;
  return v12;
}

```

## disassembly

```asm
0x140027144  mov     rax, rsp
0x140027147  mov     [rax+8], rbx
0x14002714b  mov     [rax+10h], rsi
0x14002714f  mov     [rax+20h], r9b
0x140027153  push    rdi
0x140027154  push    r12
0x140027156  push    r13
0x140027158  push    r14
0x14002715a  push    r15
0x14002715c  sub     rsp, 90h
0x140027163  mov     rbx, r8
0x140027166  mov     r15b, dl
0x140027169  mov     r14d, ecx
0x14002716c  mov     byte ptr [rax-58h], 0
0x140027170  xor     edi, edi
0x140027172  xor     esi, esi
0x140027174  cmp     ecx, 3Ch ; '<'
0x140027177  ja      short loc_140027189
0x140027179  mov     rcx, 1000000000001006h
0x140027183  bt      rcx, r14
0x140027187  jb      short loc_14002718F
0x140027189  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002718e  nop
0x14002718f  mov     ecx, r14d
0x140027192  sub     ecx, 1
0x140027195  jz      loc_14002763B
0x14002719b  sub     ecx, 1
0x14002719e  jz      loc_14002749E
0x1400271a4  mov     r9d, 0Ah
0x1400271aa  sub     ecx, r9d
0x1400271ad  jz      loc_1400273CA
0x1400271b3  cmp     ecx, 30h ; '0'
0x1400271b6  jz      loc_140027245
0x1400271bc  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x1400271c2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400271c9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400271d0  setnz   r8b
0x1400271d4  and     dl, 4
0x1400271d7  jnz     short loc_1400271DE
0x1400271d9  test    r8b, r8b
0x1400271dc  jz      short loc_14002722B
0x1400271de  mov     ecx, 312h
0x1400271e3  mov     [rsp+0B8h+var_68], r14d
0x1400271e8  mov     [rsp+0B8h+var_70], 15Ah
0x1400271f0  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400271f7  mov     [rsp+0B8h+var_78], rax
0x1400271fc  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140027203  mov     [rsp+0B8h+var_80], rax
0x140027208  mov     [rsp+0B8h+var_88], r9w
0x14002720e  mov     [rsp+0B8h+var_90], 12h
0x140027216  mov     [rsp+0B8h+var_98], 3
0x14002721b  mov     r9, cs:WPP_GLOBAL_Control
0x140027222  mov     r9, [r9+40h]
0x140027226  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002722b  lea     rcx, aUnsupportedFil; "Unsupported FileInformationClass"
0x140027232  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140027237  mov     edi, 0C00000BBh
0x14002723c  mov     [rsp+0B8h+var_54], edi
0x140027240  jmp     loc_1400277B6
0x140027245  mov     r13d, [rbx+3Ch]
0x140027249  lea     r12d, [r13+58h]
0x14002724d  mov     eax, [rsp+0B8h+arg_28]
0x140027254  cmp     eax, r12d
0x140027257  jnb     short loc_14002726B
0x140027259  cmp     eax, 58h ; 'X'
0x14002725c  jb      loc_1400277B6
0x140027262  test    r15b, r15b
0x140027265  jz      loc_1400277B6
0x14002726b  add     eax, 0FFFFFFA8h
0x14002726e  cmp     r13d, eax
0x140027271  cmovnb  r13d, eax
0x140027275  mov     [rsp+0B8h+var_58], 1
0x14002727a  mov     r14b, [rsp+0B8h+arg_30]
0x140027282  mov     r8d, 58h ; 'X'; Size
0x140027288  mov     rdx, rbx; Src
0x14002728b  mov     rsi, [rsp+0B8h+arg_20]
0x140027293  mov     rcx, rsi; void *
0x140027296  test    r14b, r14b
0x140027299  jz      short loc_1400272A2
0x14002729b  call    RtlCopyToUser
0x1400272a0  jmp     short loc_1400272A7
0x1400272a2  call    RtlCopyVolatileMemory
0x1400272a7  cmp     dword ptr [rbx+44h], 9000001Ch
0x1400272ae  jnz     short loc_14002730E
0x1400272b0  mov     edx, [rbx+38h]
0x1400272b3  mov     [rsp+0B8h+var_50], edx
0x1400272b7  mov     eax, edx
0x1400272b9  btr     eax, 0Ah
0x1400272bd  mov     [rsp+0B8h+var_50], eax
0x1400272c1  mov     eax, edx
0x1400272c3  and     eax, 0FFFFEBFFh
0x1400272c8  mov     [rsp+0B8h+var_50], eax
0x1400272cc  and     edx, 0FFFFE9FFh
0x1400272d2  mov     [rsp+0B8h+var_50], edx
0x1400272d6  mov     eax, 80h
0x1400272db  cmovz   edx, eax
0x1400272de  mov     [rsp+0B8h+var_50], edx
0x1400272e2  test    r14b, r14b
0x1400272e5  jz      short loc_1400272F2
0x1400272e7  lea     rcx, [rsi+38h]
0x1400272eb  call    RtlWriteULongToUser
0x1400272f0  jmp     short loc_1400272F5
0x1400272f2  mov     [rsi+38h], edx
0x1400272f5  test    r14b, r14b
0x1400272f8  jz      short loc_140027307
0x1400272fa  xor     edx, edx
0x1400272fc  lea     rcx, [rsi+44h]
0x140027300  call    RtlWriteULongToUser
0x140027305  jmp     short loc_14002730E
0x140027307  mov     dword ptr [rsi+44h], 0
0x14002730e  cmp     [rsp+0B8h+arg_18], 0
0x140027316  jz      short loc_140027383
0x140027318  lea     r15, [rsi+38h]
0x14002731c  test    r14b, r14b
0x14002731f  jz      short loc_14002732B
0x140027321  mov     rcx, r15
0x140027324  call    RtlReadULongFromUser
0x140027329  jmp     short loc_14002732E
0x14002732b  mov     eax, [r15]
0x14002732e  or      eax, 440000h
0x140027333  test    r14b, r14b
0x140027336  jz      short loc_140027344
0x140027338  mov     edx, eax
0x14002733a  mov     rcx, r15
0x14002733d  call    RtlWriteULongToUser
0x140027342  jmp     short loc_140027347
0x140027344  mov     [r15], eax
0x140027347  test    r14b, r14b
0x14002734a  jz      short loc_140027359
0x14002734c  xor     edx, edx
0x14002734e  lea     rcx, [rsi+30h]
0x140027352  call    RtlWriteULong64ToUser
0x140027357  jmp     short loc_140027361
0x140027359  mov     qword ptr [rsi+30h], 0
0x140027361  lea     rcx, [rsi+48h]; void *
0x140027365  mov     r8d, 10h; Size
0x14002736b  test    r14b, r14b
0x14002736e  jz      short loc_140027379
0x140027370  mov     dl, 0FFh
0x140027372  call    RtlSetUserMemory
0x140027377  jmp     short loc_140027383
0x140027379  mov     edx, 0FFh; Val
0x14002737e  call    RtlSetVolatileMemory
0x140027383  lea     rdx, [rbx+58h]; Src
0x140027387  lea     rcx, [rsi+58h]; void *
0x14002738b  mov     r8d, r13d; Size
0x14002738e  test    r14b, r14b
0x140027391  jz      short loc_14002739A
0x140027393  call    RtlCopyToUser
0x140027398  jmp     short loc_14002739F
0x14002739a  call    RtlCopyVolatileMemory
0x14002739f  test    r14b, r14b
0x1400273a2  jz      short loc_1400273B0
0x1400273a4  xor     edx, edx
0x1400273a6  mov     rcx, rsi
0x1400273a9  call    RtlWriteULongToUser
0x1400273ae  jmp     short loc_1400273B6
0x1400273b0  mov     dword ptr [rsi], 0
0x1400273b6  mov     rax, [rsp+0B8h+arg_38]
0x1400273be  mov     [rax], rsi
0x1400273c1  lea     esi, [r13+58h]
0x1400273c5  jmp     loc_14002747F
0x1400273ca  mov     r14d, [rbx+3Ch]
0x1400273ce  lea     r12d, [r14+0Ch]
0x1400273d2  mov     eax, [rsp+0B8h+arg_28]
0x1400273d9  cmp     eax, r12d
0x1400273dc  jnb     short loc_1400273F0
0x1400273de  cmp     eax, 0Ch
0x1400273e1  jb      loc_1400277B6
0x1400273e7  test    r15b, r15b
0x1400273ea  jz      loc_1400277B6
0x1400273f0  add     eax, 0FFFFFFF4h
0x1400273f3  cmp     r14d, eax
0x1400273f6  cmovnb  r14d, eax
0x1400273fa  mov     [rsp+0B8h+var_58], 1
0x1400273ff  mov     eax, [rbx+4]
0x140027402  mov     rsi, [rsp+0B8h+arg_20]
0x14002740a  lea     rcx, [rsi+4]
0x14002740e  mov     r15b, [rsp+0B8h+arg_30]
0x140027416  test    r15b, r15b
0x140027419  jz      short loc_140027424
0x14002741b  mov     edx, eax
0x14002741d  call    RtlWriteULongToUser
0x140027422  jmp     short loc_140027426
0x140027424  mov     [rcx], eax
0x140027426  mov     eax, [rbx+3Ch]
0x140027429  lea     rcx, [rsi+8]
0x14002742d  test    r15b, r15b
0x140027430  jz      short loc_14002743B
0x140027432  mov     edx, eax
0x140027434  call    RtlWriteULongToUser
0x140027439  jmp     short loc_14002743D
0x14002743b  mov     [rcx], eax
0x14002743d  lea     rdx, [rbx+58h]; Src
0x140027441  lea     rcx, [rsi+0Ch]; void *
0x140027445  mov     r8d, r14d; Size
0x140027448  test    r15b, r15b
0x14002744b  jz      short loc_140027454
0x14002744d  call    RtlCopyToUser
0x140027452  jmp     short loc_140027459
0x140027454  call    RtlCopyVolatileMemory
0x140027459  test    r15b, r15b
0x14002745c  jz      short loc_14002746A
0x14002745e  xor     edx, edx
0x140027460  mov     rcx, rsi
0x140027463  call    RtlWriteULongToUser
0x140027468  jmp     short loc_140027470
0x14002746a  mov     dword ptr [rsi], 0
0x140027470  mov     rax, [rsp+0B8h+arg_38]
0x140027478  mov     [rax], rsi
0x14002747b  lea     esi, [r14+0Ch]
0x14002747f  mov     [rsp+0B8h+var_58], 0
0x140027484  mov     [rsp+0B8h+var_38], esi
0x14002748b  cmp     esi, r12d
0x14002748e  jnb     loc_1400277B6
0x140027494  mov     edi, 80000005h
0x140027499  jmp     loc_14002723C
0x14002749e  mov     r13d, [rbx+3Ch]
0x1400274a2  lea     r12d, [r13+44h]
0x1400274a6  mov     eax, [rsp+0B8h+arg_28]
0x1400274ad  cmp     eax, r12d
0x1400274b0  jnb     short loc_1400274C4
0x1400274b2  cmp     eax, 44h ; 'D'
0x1400274b5  jb      loc_1400277B6
0x1400274bb  test    r15b, r15b
0x1400274be  jz      loc_1400277B6
0x1400274c4  add     eax, 0FFFFFFBCh
0x1400274c7  cmp     r13d, eax
0x1400274ca  cmovnb  r13d, eax
0x1400274ce  mov     [rsp+0B8h+var_58], 1
0x1400274d3  mov     r14b, [rsp+0B8h+arg_30]
0x1400274db  mov     r8d, 38h ; '8'; Size
0x1400274e1  mov     rdx, rbx; Src
0x1400274e4  mov     rsi, [rsp+0B8h+arg_20]
0x1400274ec  mov     rcx, rsi; void *
0x1400274ef  test    r14b, r14b
0x1400274f2  jz      short loc_1400274FB
0x1400274f4  call    RtlCopyToUser
0x1400274f9  jmp     short loc_140027500
0x1400274fb  call    RtlCopyVolatileMemory
0x140027500  mov     edx, [rbx+38h]
0x140027503  cmp     dword ptr [rbx+44h], 9000001Ch
0x14002750a  jnz     short loc_140027563
0x14002750c  mov     [rsp+0B8h+var_48], edx
0x140027510  mov     eax, edx
0x140027512  btr     eax, 0Ah
0x140027516  mov     [rsp+0B8h+var_48], eax
0x14002751a  mov     eax, edx
0x14002751c  and     eax, 0FFFFEBFFh
0x140027521  mov     [rsp+0B8h+var_48], eax
0x140027525  and     edx, 0FFFFE9FFh
0x14002752b  mov     [rsp+0B8h+var_48], edx
0x14002752f  mov     eax, 80h
0x140027534  cmovz   edx, eax
0x140027537  mov     [rsp+0B8h+var_48], edx
0x14002753b  test    r14b, r14b
0x14002753e  jz      short loc_14002754B
0x140027540  lea     rcx, [rsi+38h]
0x140027544  call    RtlWriteULongToUser
0x140027549  jmp     short loc_14002754E
0x14002754b  mov     [rsi+38h], edx
0x14002754e  lea     rcx, [rsi+40h]
0x140027552  mov     eax, [rbx+40h]
0x140027555  test    r14b, r14b
0x140027558  jz      short loc_140027588
0x14002755a  mov     edx, eax
0x14002755c  call    RtlWriteULongToUser
0x140027561  jmp     short loc_14002758A
0x140027563  test    r14b, r14b
0x140027566  jz      short loc_140027573
0x140027568  lea     rcx, [rsi+38h]
0x14002756c  call    RtlWriteULongToUser
0x140027571  jmp     short loc_140027576
0x140027573  mov     [rsi+38h], edx
0x140027576  lea     rcx, [rsi+40h]
0x14002757a  test    dword ptr [rbx+38h], 400h
0x140027581  jz      short loc_140027552
0x140027583  mov     eax, [rbx+44h]
0x140027586  jmp     short loc_140027555
0x140027588  mov     [rcx], eax
0x14002758a  cmp     [rsp+0B8h+arg_18], 0
0x140027592  jz      short loc_1400275DD
0x140027594  lea     r15, [rsi+38h]
0x140027598  test    r14b, r14b
0x14002759b  jz      short loc_1400275A7
0x14002759d  mov     rcx, r15
0x1400275a0  call    RtlReadULongFromUser
0x1400275a5  jmp     short loc_1400275AA
0x1400275a7  mov     eax, [r15]
0x1400275aa  or      eax, 440000h
0x1400275af  test    r14b, r14b
0x1400275b2  jz      short loc_1400275C0
0x1400275b4  mov     edx, eax
0x1400275b6  mov     rcx, r15
0x1400275b9  call    RtlWriteULongToUser
0x1400275be  jmp     short loc_1400275C3
0x1400275c0  mov     [r15], eax
0x1400275c3  test    r14b, r14b
0x1400275c6  jz      short loc_1400275D5
0x1400275c8  xor     edx, edx
  ... truncated ...
```
