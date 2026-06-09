# PrjfMungeDirectoryEnumerateWithShortname

- ea: `0x1400260a4`
- end: `0x1400266e6`
- name: `PrjfMungeDirectoryEnumerateWithShortname`
- size: `1602`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char, unsigned int *, unsigned int, char, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
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
- `0x140021108`
- `0x140021150`
- `0x140021198`
- `0x1400260a4`
- `0x1400266ec`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithShortname(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        unsigned int *a6,
        unsigned int a7,
        char a8,
        unsigned int **a9,
        unsigned int *a10)
{
  __int64 v11; // rbx
  char v12; // r15
  int v13; // esi
  unsigned int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  int v18; // r8d
  __int64 v19; // rdx
  size_t v20; // r8
  void *v21; // rdx
  void *v22; // rcx
  _UNKNOWN **v23; // rcx
  __int64 v24; // rdx
  unsigned int *v25; // r15
  unsigned int ULongFromUser; // eax
  unsigned int v27; // eax
  void *v28; // rcx
  void *v29; // rdx
  void *v30; // rcx
  unsigned int v31; // r13d
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // rdx
  unsigned int *v35; // rcx
  unsigned int v36; // eax
  unsigned int *v37; // r15
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // rdx
  size_t v41; // r8
  void *v42; // rdx
  void *v43; // rcx
  _UNKNOWN **v44; // rcx
  unsigned int v45; // eax
  unsigned int *v46; // rcx
  void *v47; // rdx
  void *v48; // rcx
  int v49; // eax
  unsigned int v51; // [rsp+C0h] [rbp+8h]

  v11 = a3;
  v12 = a2;
  v13 = a1;
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)a1 != 3 && (_DWORD)a1 != 63 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( v13 != 3 )
  {
    if ( v13 != 63 )
    {
      if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = BYTE10(xmmword_14001A3D0) & 4;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          786,
          a2,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          18,
          13,
          (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          105,
          v13);
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Invalid FileInformationClass");
      v14 = -1073741637;
      goto LABEL_126;
    }
    v16 = *(_DWORD *)(v11 + 60);
    v17 = v16 + 114;
    if ( a7 < v16 + 114 && (a7 < 0x72 || !v12) )
      goto LABEL_126;
    if ( v16 >= a7 - 114 )
      v16 = a7 - 114;
    if ( a8 )
      RtlCopyToUser(a6, (void *)v11, 0x58u);
    else
      RtlCopyVolatileMemory(a6, (const void *)v11, 0x58u);
    if ( a4 )
    {
      v19 = (unsigned int)*(char *)(v11 + 88);
      if ( *(_BYTE *)(v11 + 88) <= 0x18u )
      {
        if ( a8 )
          RtlWriteUCharToUser(a6 + 22, v19);
        else
          *((_BYTE *)a6 + 88) = *(_BYTE *)(v11 + 88);
        v20 = *(char *)(v11 + 88);
        v21 = (void *)(v11 + 90);
        v22 = (char *)a6 + 90;
        if ( a8 )
          RtlCopyToUser(v22, v21, v20);
        else
          RtlCopyVolatileMemory(v22, v21, v20);
        goto LABEL_34;
      }
      v23 = &WPP_RECORDER_INITIALIZED;
      if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          530,
          BYTE2(xmmword_14001A3D0) & 4,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          18,
          12,
          (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          62,
          *(_BYTE *)(v11 + 88));
      }
      if ( *(_BYTE *)(v11 + 88) > 0x18u )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, v19);
    }
    if ( a8 )
      RtlWriteUCharToUser(a6 + 22, 0);
    else
      *((_BYTE *)a6 + 88) = 0;
LABEL_34:
    if ( *(_DWORD *)(v11 + 68) == -1879048164 )
    {
      v24 = *(_DWORD *)(v11 + 56) & 0xFFFFE9FF;
      if ( (*(_DWORD *)(v11 + 56) & 0xFFFFE9FF) == 0 )
        v24 = 128;
      if ( a8 )
        RtlWriteULongToUser(a6 + 14, v24);
      else
        a6[14] = v24;
      if ( a8 )
        RtlWriteULongToUser(a6 + 17, 0);
      else
        a6[17] = 0;
    }
    if ( a5 )
    {
      v25 = a6 + 14;
      if ( a8 )
        ULongFromUser = RtlReadULongFromUser(a6 + 14);
      else
        ULongFromUser = *v25;
      v27 = ULongFromUser | 0x440000;
      if ( a8 )
        RtlWriteULongToUser(a6 + 14, v27);
      else
        *v25 = v27;
      if ( a8 )
        RtlWriteULong64ToUser(a6 + 12, 0);
      else
        *((_QWORD *)a6 + 6) = 0;
      v28 = a6 + 18;
      if ( a8 )
        RtlSetUserMemory(v28);
      else
        RtlSetVolatileMemory(v28, 255, 0x10u);
    }
    v29 = (void *)(v11 + 114);
    v30 = (char *)a6 + 114;
    if ( a8 )
      RtlCopyToUser(v30, v29, v16);
    else
      RtlCopyVolatileMemory(v30, v29, v16);
    if ( a8 )
      RtlWriteULongToUser(a6, 0);
    else
      *a6 = 0;
    *a9 = a6;
    v15 = v16 + 114;
    if ( v16 + 114 < v17 )
      v14 = -2147483643;
    goto LABEL_126;
  }
  v31 = *(_DWORD *)(v11 + 60);
  v51 = v31 + 94;
  if ( a7 < v31 + 94 && (a7 < 0x5E || !v12) )
    goto LABEL_126;
  if ( v31 >= a7 - 94 )
    v31 = a7 - 94;
  if ( a8 )
    RtlCopyToUser(a6, (void *)v11, 0x38u);
  else
    RtlCopyVolatileMemory(a6, (const void *)v11, 0x38u);
  v33 = *(unsigned int *)(v11 + 56);
  if ( *(_DWORD *)(v11 + 68) == -1879048164 )
  {
    v34 = (unsigned int)v33 & 0xFFFFE9FF;
    if ( !(_DWORD)v34 )
      v34 = 128;
    if ( a8 )
      RtlWriteULongToUser(a6 + 14, v34);
    else
      a6[14] = v34;
    v35 = a6 + 16;
    goto LABEL_79;
  }
  if ( a8 )
    RtlWriteULongToUser(a6 + 14, v33);
  else
    a6[14] = v33;
  v35 = a6 + 16;
  if ( (*(_DWORD *)(v11 + 56) & 0x400) == 0 )
  {
LABEL_79:
    v36 = *(_DWORD *)(v11 + 64);
    goto LABEL_80;
  }
  v36 = *(_DWORD *)(v11 + 68);
LABEL_80:
  if ( a8 )
    RtlWriteULongToUser(v35, v36);
  else
    *v35 = v36;
  if ( a5 )
  {
    v37 = a6 + 14;
    if ( a8 )
      v38 = RtlReadULongFromUser(a6 + 14);
    else
      v38 = *v37;
    v39 = v38 | 0x440000;
    if ( a8 )
      RtlWriteULongToUser(a6 + 14, v39);
    else
      *v37 = v39;
    if ( a8 )
      RtlWriteULong64ToUser(a6 + 12, 0);
    else
      *((_QWORD *)a6 + 6) = 0;
  }
  if ( a4 )
  {
    v40 = (unsigned int)*(char *)(v11 + 88);
    if ( *(_BYTE *)(v11 + 88) <= 0x18u )
    {
      if ( a8 )
        RtlWriteUCharToUser(a6 + 17, v40);
      else
        *((_BYTE *)a6 + 68) = *(_BYTE *)(v11 + 88);
      v41 = *(char *)(v11 + 88);
      v42 = (void *)(v11 + 90);
      v43 = (char *)a6 + 70;
      if ( a8 )
        RtlCopyToUser(v43, v42, v41);
      else
        RtlCopyVolatileMemory(v43, v42, v41);
      goto LABEL_114;
    }
    v44 = &WPP_RECORDER_INITIALIZED;
    if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        530,
        BYTE2(xmmword_14001A3D0) & 4,
        v32,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        11,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        1,
        *(_BYTE *)(v11 + 88));
    }
    if ( *(_BYTE *)(v11 + 88) > 0x18u )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v44, v40);
  }
  if ( a8 )
    RtlWriteUCharToUser(a6 + 17, 0);
  else
    *((_BYTE *)a6 + 68) = 0;
LABEL_114:
  v45 = *(_DWORD *)(v11 + 60);
  v46 = a6 + 15;
  if ( a8 )
    RtlWriteULongToUser(v46, v45);
  else
    *v46 = v45;
  v47 = (void *)(v11 + 114);
  v48 = (char *)a6 + 94;
  if ( a8 )
    RtlCopyToUser(v48, v47, v31);
  else
    RtlCopyVolatileMemory(v48, v47, v31);
  if ( a8 )
    RtlWriteULongToUser(a6, 0);
  else
    *a6 = 0;
  *a9 = a6;
  v15 = v31 + 94;
  v49 = 0;
  if ( v31 + 94 < v51 )
    v49 = -2147483643;
  v14 = v49;
LABEL_126:
  *a10 = v15;
  return v14;
}

```

## disassembly

```asm
0x1400260a4  mov     rax, rsp
0x1400260a7  mov     [rax+10h], rbx
0x1400260ab  mov     [rax+18h], rsi
0x1400260af  mov     [rax+20h], r9b
0x1400260b3  push    rdi
0x1400260b4  push    r12
0x1400260b6  push    r13
0x1400260b8  push    r14
0x1400260ba  push    r15
0x1400260bc  sub     rsp, 90h
0x1400260c3  mov     r12b, r9b
0x1400260c6  mov     rbx, r8
0x1400260c9  mov     r15b, dl
0x1400260cc  mov     esi, ecx
0x1400260ce  mov     byte ptr [rax-58h], 0
0x1400260d2  xor     r14d, r14d
0x1400260d5  xor     edi, edi
0x1400260d7  cmp     ecx, 3
0x1400260da  jz      short loc_1400260E7
0x1400260dc  cmp     ecx, 3Fh ; '?'
0x1400260df  jz      short loc_1400260E7
0x1400260e1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400260e6  nop
0x1400260e7  cmp     esi, 3
0x1400260ea  jz      loc_14002640A
0x1400260f0  cmp     esi, 3Fh ; '?'
0x1400260f3  jz      loc_140026189
0x1400260f9  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x1400260ff  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026106  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002610d  setnz   r8b
0x140026111  and     dl, 4
0x140026114  jnz     short loc_14002611B
0x140026116  test    r8b, r8b
0x140026119  jz      short loc_14002616D
0x14002611b  mov     ecx, 312h
0x140026120  mov     r9d, 0Dh
0x140026126  mov     [rsp+0B8h+var_68], esi
0x14002612a  mov     [rsp+0B8h+var_70], 269h
0x140026132  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140026139  mov     [rsp+0B8h+var_78], rax
0x14002613e  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140026145  mov     [rsp+0B8h+var_80], rax
0x14002614a  mov     [rsp+0B8h+var_88], r9w
0x140026150  mov     [rsp+0B8h+var_90], 12h
0x140026158  mov     [rsp+0B8h+var_98], 3
0x14002615d  mov     r9, cs:WPP_GLOBAL_Control
0x140026164  mov     r9, [r9+40h]
0x140026168  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002616d  lea     rcx, aInvalidFileinf; "Invalid FileInformationClass"
0x140026174  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140026179  mov     r14d, 0C00000BBh
0x14002617f  mov     [rsp+0B8h+var_40], r14d
0x140026184  jmp     loc_1400266AE
0x140026189  mov     r13d, [rbx+3Ch]
0x14002618d  lea     r12d, [r13+72h]
0x140026191  mov     eax, [rsp+0B8h+arg_30]
0x140026198  cmp     eax, r12d
0x14002619b  jnb     short loc_1400261AF
0x14002619d  cmp     eax, 72h ; 'r'
0x1400261a0  jb      loc_1400266AE
0x1400261a6  test    r15b, r15b
0x1400261a9  jz      loc_1400266AE
0x1400261af  add     eax, 0FFFFFF8Eh
0x1400261b2  cmp     r13d, eax
0x1400261b5  cmovnb  r13d, eax
0x1400261b9  mov     [rsp+0B8h+var_58], 1
0x1400261be  mov     sil, [rsp+0B8h+arg_38]
0x1400261c6  xor     r15d, r15d
0x1400261c9  lea     r8d, [r15+58h]; Size
0x1400261cd  mov     rdx, rbx; Src
0x1400261d0  mov     rdi, [rsp+0B8h+arg_28]
0x1400261d8  mov     rcx, rdi; void *
0x1400261db  test    sil, sil
0x1400261de  jz      short loc_1400261E7
0x1400261e0  call    RtlCopyToUser
0x1400261e5  jmp     short loc_1400261EC
0x1400261e7  call    RtlCopyVolatileMemory
0x1400261ec  cmp     [rsp+0B8h+arg_18], r15b
0x1400261f4  jz      loc_1400262C0
0x1400261fa  movsx   edx, byte ptr [rbx+58h]
0x1400261fe  cmp     dl, 18h
0x140026201  ja      short loc_14002623C
0x140026203  test    sil, sil
0x140026206  jz      short loc_140026213
0x140026208  lea     rcx, [rdi+58h]
0x14002620c  call    RtlWriteUCharToUser
0x140026211  jmp     short loc_140026216
0x140026213  mov     [rdi+58h], dl
0x140026216  movsx   r8, byte ptr [rbx+58h]; Size
0x14002621b  lea     rdx, [rbx+5Ah]; Src
0x14002621f  lea     rcx, [rdi+5Ah]; void *
0x140026223  test    sil, sil
0x140026226  jz      short loc_140026232
0x140026228  call    RtlCopyToUser
0x14002622d  jmp     loc_1400262D6
0x140026232  call    RtlCopyVolatileMemory
0x140026237  jmp     loc_1400262D6
0x14002623c  mov     r10b, byte ptr cs:xmmword_14001A3D0+2
0x140026243  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002624a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026251  setnz   r8b
0x140026255  and     r10b, 4
0x140026259  jnz     short loc_140026260
0x14002625b  test    r8b, r8b
0x14002625e  jz      short loc_1400262B5
0x140026260  mov     eax, edx
0x140026262  mov     edx, 0Ch
0x140026267  mov     ecx, 212h
0x14002626c  mov     [rsp+0B8h+var_68], eax
0x140026270  mov     [rsp+0B8h+var_70], 23Eh
0x140026278  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002627f  mov     [rsp+0B8h+var_78], rax
0x140026284  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x14002628b  mov     [rsp+0B8h+var_80], rax
0x140026290  mov     [rsp+0B8h+var_88], dx
0x140026295  mov     [rsp+0B8h+var_90], 12h
0x14002629d  mov     [rsp+0B8h+var_98], 2
0x1400262a2  mov     r9, cs:WPP_GLOBAL_Control
0x1400262a9  mov     r9, [r9+40h]
0x1400262ad  mov     dl, r10b
0x1400262b0  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400262b5  cmp     byte ptr [rbx+58h], 18h
0x1400262b9  jbe     short loc_1400262C0
0x1400262bb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400262c0  test    sil, sil
0x1400262c3  jz      short loc_1400262D2
0x1400262c5  xor     edx, edx
0x1400262c7  lea     rcx, [rdi+58h]
0x1400262cb  call    RtlWriteUCharToUser
0x1400262d0  jmp     short loc_1400262D6
0x1400262d2  mov     [rdi+58h], r15b
0x1400262d6  cmp     dword ptr [rbx+44h], 9000001Ch
0x1400262dd  jnz     short loc_14002633A
0x1400262df  mov     edx, [rbx+38h]
0x1400262e2  mov     [rsp+0B8h+var_50], edx
0x1400262e6  mov     eax, edx
0x1400262e8  btr     eax, 0Ah
0x1400262ec  mov     [rsp+0B8h+var_50], eax
0x1400262f0  mov     eax, edx
0x1400262f2  and     eax, 0FFFFEBFFh
0x1400262f7  mov     [rsp+0B8h+var_50], eax
0x1400262fb  and     edx, 0FFFFE9FFh
0x140026301  mov     [rsp+0B8h+var_50], edx
0x140026305  mov     eax, 80h
0x14002630a  cmovz   edx, eax
0x14002630d  mov     [rsp+0B8h+var_50], edx
0x140026311  test    sil, sil
0x140026314  jz      short loc_140026321
0x140026316  lea     rcx, [rdi+38h]
0x14002631a  call    RtlWriteULongToUser
0x14002631f  jmp     short loc_140026324
0x140026321  mov     [rdi+38h], edx
0x140026324  test    sil, sil
0x140026327  jz      short loc_140026336
0x140026329  xor     edx, edx
0x14002632b  lea     rcx, [rdi+44h]
0x14002632f  call    RtlWriteULongToUser
0x140026334  jmp     short loc_14002633A
0x140026336  mov     [rdi+44h], r15d
0x14002633a  cmp     [rsp+0B8h+arg_20], r15b
0x140026342  jz      short loc_1400263AE
0x140026344  lea     r15, [rdi+38h]
0x140026348  test    sil, sil
0x14002634b  jz      short loc_140026357
0x14002634d  mov     rcx, r15
0x140026350  call    RtlReadULongFromUser
0x140026355  jmp     short loc_14002635A
0x140026357  mov     eax, [r15]
0x14002635a  or      eax, 440000h
0x14002635f  test    sil, sil
0x140026362  jz      short loc_140026370
0x140026364  mov     edx, eax
0x140026366  mov     rcx, r15
0x140026369  call    RtlWriteULongToUser
0x14002636e  jmp     short loc_140026373
0x140026370  mov     [r15], eax
0x140026373  xor     r15d, r15d
0x140026376  test    sil, sil
0x140026379  jz      short loc_140026388
0x14002637b  xor     edx, edx
0x14002637d  lea     rcx, [rdi+30h]
0x140026381  call    RtlWriteULong64ToUser
0x140026386  jmp     short loc_14002638C
0x140026388  mov     [rdi+30h], r15
0x14002638c  lea     rcx, [rdi+48h]; void *
0x140026390  mov     r8d, 10h; Size
0x140026396  test    sil, sil
0x140026399  jz      short loc_1400263A4
0x14002639b  mov     dl, 0FFh
0x14002639d  call    RtlSetUserMemory
0x1400263a2  jmp     short loc_1400263AE
0x1400263a4  mov     edx, 0FFh; Val
0x1400263a9  call    RtlSetVolatileMemory
0x1400263ae  lea     rdx, [rbx+72h]; Src
0x1400263b2  lea     rcx, [rdi+72h]; void *
0x1400263b6  mov     r8d, r13d; Size
0x1400263b9  test    sil, sil
0x1400263bc  jz      short loc_1400263C5
0x1400263be  call    RtlCopyToUser
0x1400263c3  jmp     short loc_1400263CA
0x1400263c5  call    RtlCopyVolatileMemory
0x1400263ca  test    sil, sil
0x1400263cd  jz      short loc_1400263DB
0x1400263cf  xor     edx, edx
0x1400263d1  mov     rcx, rdi
0x1400263d4  call    RtlWriteULongToUser
0x1400263d9  jmp     short loc_1400263DE
0x1400263db  mov     [rdi], r15d
0x1400263de  mov     rax, [rsp+0B8h+arg_40]
0x1400263e6  mov     [rax], rdi
0x1400263e9  mov     [rsp+0B8h+var_58], r15b
0x1400263ee  lea     edi, [r13+72h]
0x1400263f2  mov     [rsp+0B8h+var_3C], edi
0x1400263f6  cmp     edi, r12d
0x1400263f9  jnb     loc_1400266AE
0x1400263ff  mov     r14d, 80000005h
0x140026405  jmp     loc_14002617F
0x14002640a  mov     r13d, [rbx+3Ch]
0x14002640e  lea     ecx, [r13+5Eh]
0x140026412  mov     [rsp+0B8h+arg_0], ecx
0x140026419  mov     eax, [rsp+0B8h+arg_30]
0x140026420  cmp     eax, ecx
0x140026422  jnb     short loc_140026436
0x140026424  cmp     eax, 5Eh ; '^'
0x140026427  jb      loc_1400266AE
0x14002642d  test    r15b, r15b
0x140026430  jz      loc_1400266AE
0x140026436  add     eax, 0FFFFFFA2h
0x140026439  cmp     r13d, eax
0x14002643c  cmovnb  r13d, eax
0x140026440  mov     [rsp+0B8h+var_58], 1
0x140026445  mov     sil, [rsp+0B8h+arg_38]
0x14002644d  xor     r15d, r15d
0x140026450  lea     r8d, [r15+38h]; Size
0x140026454  mov     rdx, rbx; Src
0x140026457  mov     rdi, [rsp+0B8h+arg_28]
0x14002645f  mov     rcx, rdi; void *
0x140026462  test    sil, sil
0x140026465  jz      short loc_14002646E
0x140026467  call    RtlCopyToUser
0x14002646c  jmp     short loc_140026473
0x14002646e  call    RtlCopyVolatileMemory
0x140026473  mov     edx, [rbx+38h]
0x140026476  cmp     dword ptr [rbx+44h], 9000001Ch
0x14002647d  jnz     short loc_1400264D6
0x14002647f  mov     [rsp+0B8h+var_48], edx
0x140026483  mov     eax, edx
0x140026485  btr     eax, 0Ah
0x140026489  mov     [rsp+0B8h+var_48], eax
0x14002648d  mov     eax, edx
0x14002648f  and     eax, 0FFFFEBFFh
0x140026494  mov     [rsp+0B8h+var_48], eax
0x140026498  and     edx, 0FFFFE9FFh
0x14002649e  mov     [rsp+0B8h+var_48], edx
0x1400264a2  mov     eax, 80h
0x1400264a7  cmovz   edx, eax
0x1400264aa  mov     [rsp+0B8h+var_48], edx
0x1400264ae  test    sil, sil
0x1400264b1  jz      short loc_1400264BE
0x1400264b3  lea     rcx, [rdi+38h]
0x1400264b7  call    RtlWriteULongToUser
0x1400264bc  jmp     short loc_1400264C1
0x1400264be  mov     [rdi+38h], edx
0x1400264c1  lea     rcx, [rdi+40h]
0x1400264c5  mov     eax, [rbx+40h]
0x1400264c8  test    sil, sil
0x1400264cb  jz      short loc_1400264FB
0x1400264cd  mov     edx, eax
0x1400264cf  call    RtlWriteULongToUser
0x1400264d4  jmp     short loc_1400264FD
0x1400264d6  test    sil, sil
0x1400264d9  jz      short loc_1400264E6
0x1400264db  lea     rcx, [rdi+38h]
0x1400264df  call    RtlWriteULongToUser
0x1400264e4  jmp     short loc_1400264E9
0x1400264e6  mov     [rdi+38h], edx
0x1400264e9  lea     rcx, [rdi+40h]
0x1400264ed  test    dword ptr [rbx+38h], 400h
0x1400264f4  jz      short loc_1400264C5
0x1400264f6  mov     eax, [rbx+44h]
0x1400264f9  jmp     short loc_1400264C8
0x1400264fb  mov     [rcx], eax
0x1400264fd  cmp     [rsp+0B8h+arg_20], r15b
0x140026505  jz      short loc_14002654F
0x140026507  lea     r15, [rdi+38h]
0x14002650b  test    sil, sil
0x14002650e  jz      short loc_14002651A
0x140026510  mov     rcx, r15
0x140026513  call    RtlReadULongFromUser
0x140026518  jmp     short loc_14002651D
0x14002651a  mov     eax, [r15]
0x14002651d  or      eax, 440000h
0x140026522  test    sil, sil
0x140026525  jz      short loc_140026533
0x140026527  mov     edx, eax
0x140026529  mov     rcx, r15
0x14002652c  call    RtlWriteULongToUser
0x140026531  jmp     short loc_140026536
0x140026533  mov     [r15], eax
  ... truncated ...
```
