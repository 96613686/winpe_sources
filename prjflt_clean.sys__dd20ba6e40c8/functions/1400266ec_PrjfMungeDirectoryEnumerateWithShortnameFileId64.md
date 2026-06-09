# PrjfMungeDirectoryEnumerateWithShortnameFileId64

- ea: `0x1400266ec`
- end: `0x140026d8e`
- name: `PrjfMungeDirectoryEnumerateWithShortnameFileId64`
- size: `1698`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
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
- `0x1400266ec`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithShortnameFileId64(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        _DWORD *a6,
        unsigned int a7,
        char a8,
        _QWORD *a9,
        unsigned int *a10)
{
  char v10; // r12
  __int64 v11; // rbx
  char v12; // r15
  int v13; // esi
  unsigned int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  size_t v21; // r8
  void *v22; // rdx
  void *v23; // rcx
  _UNKNOWN **v24; // rcx
  __int64 v25; // rdx
  unsigned int *v26; // r15
  unsigned int ULongFromUser; // eax
  unsigned int v28; // eax
  void *v29; // rdx
  void *v30; // rcx
  unsigned int v31; // r13d
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rdx
  unsigned int *v36; // rcx
  unsigned int v37; // eax
  unsigned int *v38; // r15
  unsigned int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // rdx
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  size_t v44; // r8
  void *v45; // rdx
  void *v46; // rcx
  _UNKNOWN **v47; // rcx
  void *v48; // rcx
  unsigned int v49; // eax
  unsigned int *v50; // rcx
  void *v51; // rdx
  void *v52; // rcx
  int v53; // eax
  unsigned int v55; // [rsp+C0h] [rbp+8h]
  char v56; // [rsp+D8h] [rbp+20h]

  v56 = a4;
  v10 = a4;
  v11 = a3;
  v12 = a2;
  v13 = a1;
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)a1 != 37 && (_DWORD)a1 != 79 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( v13 != 37 )
  {
    if ( v13 != 79 )
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
          17,
          (__int64)&WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          85,
          v13);
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Invalid FileInformationClass");
      v14 = -1073741637;
      goto LABEL_139;
    }
    v16 = *(_DWORD *)(v11 + 60);
    v17 = v16 + 106;
    if ( a7 < v16 + 106 && (a7 < 0x6A || !v12) )
      goto LABEL_139;
    if ( v16 >= a7 - 106 )
      v16 = a7 - 106;
    if ( a8 )
      RtlCopyToUser(a6, (void *)v11, 0x50u);
    else
      RtlCopyVolatileMemory(a6, (const void *)v11, 0x50u);
    if ( v56 )
    {
      v20 = (unsigned int)*(char *)(v11 + 80);
      if ( *(_BYTE *)(v11 + 80) <= 0x18u )
      {
        if ( a8 )
          RtlWriteUCharToUser(a6 + 20, v20);
        else
          *((_BYTE *)a6 + 80) = *(_BYTE *)(v11 + 80);
        v21 = *(char *)(v11 + 80);
        v22 = (void *)(v11 + 82);
        v23 = (char *)a6 + 82;
        if ( a8 )
          RtlCopyToUser(v23, v22, v21);
        else
          RtlCopyVolatileMemory(v23, v22, v21);
        goto LABEL_34;
      }
      v24 = &WPP_RECORDER_INITIALIZED;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDL(
          530,
          BYTE2(xmmword_14001A3D0) & 4,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          18,
          16,
          (__int64)&WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          43,
          *(_BYTE *)(v11 + 80));
      if ( *(_BYTE *)(v11 + 80) > 0x18u )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v20, v18, v19);
    }
    if ( a8 )
      RtlWriteUCharToUser(a6 + 20, 0);
    else
      *((_BYTE *)a6 + 80) = 0;
LABEL_34:
    if ( *(_DWORD *)(v11 + 68) == -1879048164 )
    {
      v25 = *(_DWORD *)(v11 + 56) & 0xFFFFE9FF;
      if ( (*(_DWORD *)(v11 + 56) & 0xFFFFE9FF) == 0 )
        v25 = 128;
      if ( a8 )
        RtlWriteULongToUser(a6 + 14, v25);
      else
        a6[14] = v25;
      if ( a8 )
        RtlWriteULongToUser(a6 + 17, 0);
      else
        a6[17] = 0;
    }
    if ( a5 )
    {
      v26 = a6 + 14;
      if ( a8 )
        ULongFromUser = RtlReadULongFromUser(a6 + 14);
      else
        ULongFromUser = *v26;
      v28 = ULongFromUser | 0x440000;
      if ( a8 )
        RtlWriteULongToUser(a6 + 14, v28);
      else
        *v26 = v28;
      if ( a8 )
        RtlWriteULong64ToUser(a6 + 12, 0);
      else
        *((_QWORD *)a6 + 6) = 0;
      if ( a8 )
        RtlWriteULong64ToUser(a6 + 18, -1);
      else
        *((_QWORD *)a6 + 9) = -1;
    }
    v29 = (void *)(v11 + 106);
    v30 = (char *)a6 + 106;
    if ( a8 )
      RtlCopyToUser(v30, v29, v16);
    else
      RtlCopyVolatileMemory(v30, v29, v16);
    if ( a8 )
      RtlWriteULongToUser(a6, 0);
    else
      *a6 = 0;
    *a9 = a6;
    v15 = v16 + 106;
    if ( v16 + 106 < v17 )
      v14 = -2147483643;
    goto LABEL_139;
  }
  v31 = *(_DWORD *)(v11 + 60);
  v55 = v31 + 104;
  if ( a7 < v31 + 104 && (a7 < 0x68 || !v12) )
    goto LABEL_139;
  if ( v31 >= a7 - 104 )
    v31 = a7 - 104;
  if ( a8 )
    RtlCopyToUser(a6, (void *)v11, 0x38u);
  else
    RtlCopyVolatileMemory(a6, (const void *)v11, 0x38u);
  v34 = *(unsigned int *)(v11 + 56);
  if ( *(_DWORD *)(v11 + 68) == -1879048164 )
  {
    v35 = (unsigned int)v34 & 0xFFFFE9FF;
    if ( !(_DWORD)v35 )
      v35 = 128;
    if ( a8 )
      RtlWriteULongToUser(a6 + 14, v35);
    else
      a6[14] = v35;
    v36 = a6 + 16;
    goto LABEL_79;
  }
  if ( a8 )
    RtlWriteULongToUser(a6 + 14, v34);
  else
    a6[14] = v34;
  v36 = a6 + 16;
  if ( (*(_DWORD *)(v11 + 56) & 0x400) == 0 )
  {
LABEL_79:
    v37 = *(_DWORD *)(v11 + 64);
    goto LABEL_80;
  }
  v37 = *(_DWORD *)(v11 + 68);
LABEL_80:
  if ( a8 )
    RtlWriteULongToUser(v36, v37);
  else
    *v36 = v37;
  if ( !a5 )
  {
    v42 = a6 + 24;
    if ( !a8 )
    {
      *v42 = *(_QWORD *)(v11 + 72);
      goto LABEL_105;
    }
    v41 = *(_QWORD *)(v11 + 72);
    goto LABEL_103;
  }
  v38 = a6 + 14;
  if ( a8 )
    v39 = RtlReadULongFromUser(a6 + 14);
  else
    v39 = *v38;
  v40 = v39 | 0x440000;
  if ( a8 )
    RtlWriteULongToUser(a6 + 14, v40);
  else
    *v38 = v40;
  if ( a8 )
    RtlWriteULong64ToUser(a6 + 12, 0);
  else
    *((_QWORD *)a6 + 6) = 0;
  if ( a8 )
  {
    v41 = -1;
    v42 = a6 + 24;
LABEL_103:
    RtlWriteULong64ToUser(v42, v41);
    goto LABEL_105;
  }
  *((_QWORD *)a6 + 12) = -1;
LABEL_105:
  if ( v10 )
  {
    v43 = (unsigned int)*(char *)(v11 + 80);
    if ( *(_BYTE *)(v11 + 80) > 0x18u )
    {
      v47 = &WPP_RECORDER_INITIALIZED;
      LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDL(
          530,
          BYTE2(xmmword_14001A3D0) & 4,
          v32,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          18,
          15,
          (__int64)&WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          238,
          *(_BYTE *)(v11 + 80));
      if ( *(_BYTE *)(v11 + 80) > 0x18u )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v47, v43, v32, v33);
      if ( a8 )
        RtlWriteUCharToUser(a6 + 17, 0);
      else
        *((_BYTE *)a6 + 68) = 0;
    }
    else
    {
      if ( a8 )
        RtlWriteUCharToUser(a6 + 17, v43);
      else
        *((_BYTE *)a6 + 68) = *(_BYTE *)(v11 + 80);
      v44 = *(char *)(v11 + 80);
      v45 = (void *)(v11 + 82);
      v46 = (char *)a6 + 70;
      if ( a8 )
        RtlCopyToUser(v46, v45, v44);
      else
        RtlCopyVolatileMemory(v46, v45, v44);
    }
  }
  else
  {
    if ( a8 )
      RtlWriteUCharToUser(a6 + 17, 0);
    else
      *((_BYTE *)a6 + 68) = 0;
    v48 = (char *)a6 + 70;
    if ( a8 )
      RtlSetUserMemory(v48);
    else
      RtlSetVolatileMemory(v48, 0, 0x18u);
  }
  v49 = *(_DWORD *)(v11 + 60);
  v50 = a6 + 15;
  if ( a8 )
    RtlWriteULongToUser(v50, v49);
  else
    *v50 = v49;
  v51 = (void *)(v11 + 106);
  v52 = a6 + 26;
  if ( a8 )
    RtlCopyToUser(v52, v51, v31);
  else
    RtlCopyVolatileMemory(v52, v51, v31);
  if ( a8 )
    RtlWriteULongToUser(a6, 0);
  else
    *a6 = 0;
  *a9 = a6;
  v15 = v31 + 104;
  v53 = 0;
  if ( v31 + 104 < v55 )
    v53 = -2147483643;
  v14 = v53;
LABEL_139:
  *a10 = v15;
  return v14;
}

```

## disassembly

```asm
0x1400266ec  mov     rax, rsp
0x1400266ef  mov     [rax+10h], rbx
0x1400266f3  mov     [rax+18h], rsi
0x1400266f7  mov     [rax+20h], r9b
0x1400266fb  push    rdi
0x1400266fc  push    r12
0x1400266fe  push    r13
0x140026700  push    r14
0x140026702  push    r15
0x140026704  sub     rsp, 90h
0x14002670b  mov     r12b, r9b
0x14002670e  mov     rbx, r8
0x140026711  mov     r15b, dl
0x140026714  mov     esi, ecx
0x140026716  mov     byte ptr [rax-58h], 0
0x14002671a  xor     r14d, r14d
0x14002671d  xor     edi, edi
0x14002671f  cmp     ecx, 25h ; '%'
0x140026722  jz      short loc_14002672F
0x140026724  cmp     ecx, 4Fh ; 'O'
0x140026727  jz      short loc_14002672F
0x140026729  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002672e  nop
0x14002672f  cmp     esi, 25h ; '%'
0x140026732  jz      loc_140026A4C
0x140026738  cmp     esi, 4Fh ; 'O'
0x14002673b  jz      loc_1400267D1
0x140026741  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x140026747  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002674e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026755  setnz   r8b
0x140026759  and     dl, 4
0x14002675c  jnz     short loc_140026763
0x14002675e  test    r8b, r8b
0x140026761  jz      short loc_1400267B5
0x140026763  mov     ecx, 312h
0x140026768  mov     r9d, 11h
0x14002676e  mov     [rsp+0B8h+var_68], esi
0x140026772  mov     [rsp+0B8h+var_70], 455h
0x14002677a  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140026781  mov     [rsp+0B8h+var_78], rax
0x140026786  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x14002678d  mov     [rsp+0B8h+var_80], rax
0x140026792  mov     [rsp+0B8h+var_88], r9w
0x140026798  mov     [rsp+0B8h+var_90], 12h
0x1400267a0  mov     [rsp+0B8h+var_98], 3
0x1400267a5  mov     r9, cs:WPP_GLOBAL_Control
0x1400267ac  mov     r9, [r9+40h]
0x1400267b0  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400267b5  lea     rcx, aInvalidFileinf; "Invalid FileInformationClass"
0x1400267bc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400267c1  mov     r14d, 0C00000BBh
0x1400267c7  mov     [rsp+0B8h+var_40], r14d
0x1400267cc  jmp     loc_140026D56
0x1400267d1  mov     r13d, [rbx+3Ch]
0x1400267d5  lea     r12d, [r13+6Ah]
0x1400267d9  mov     eax, [rsp+0B8h+arg_30]
0x1400267e0  cmp     eax, r12d
0x1400267e3  jnb     short loc_1400267F7
0x1400267e5  cmp     eax, 6Ah ; 'j'
0x1400267e8  jb      loc_140026D56
0x1400267ee  test    r15b, r15b
0x1400267f1  jz      loc_140026D56
0x1400267f7  add     eax, 0FFFFFF96h
0x1400267fa  cmp     r13d, eax
0x1400267fd  cmovnb  r13d, eax
0x140026801  mov     [rsp+0B8h+var_58], 1
0x140026806  mov     sil, [rsp+0B8h+arg_38]
0x14002680e  xor     r15d, r15d
0x140026811  lea     r8d, [r15+50h]; Size
0x140026815  mov     rdx, rbx; Src
0x140026818  mov     rdi, [rsp+0B8h+arg_28]
0x140026820  mov     rcx, rdi; void *
0x140026823  test    sil, sil
0x140026826  jz      short loc_14002682F
0x140026828  call    RtlCopyToUser
0x14002682d  jmp     short loc_140026834
0x14002682f  call    RtlCopyVolatileMemory
0x140026834  cmp     [rsp+0B8h+arg_18], r15b
0x14002683c  jz      loc_140026908
0x140026842  movsx   edx, byte ptr [rbx+50h]
0x140026846  cmp     dl, 18h
0x140026849  ja      short loc_140026884
0x14002684b  test    sil, sil
0x14002684e  jz      short loc_14002685B
0x140026850  lea     rcx, [rdi+50h]
0x140026854  call    RtlWriteUCharToUser
0x140026859  jmp     short loc_14002685E
0x14002685b  mov     [rdi+50h], dl
0x14002685e  movsx   r8, byte ptr [rbx+50h]; Size
0x140026863  lea     rdx, [rbx+52h]; Src
0x140026867  lea     rcx, [rdi+52h]; void *
0x14002686b  test    sil, sil
0x14002686e  jz      short loc_14002687A
0x140026870  call    RtlCopyToUser
0x140026875  jmp     loc_14002691E
0x14002687a  call    RtlCopyVolatileMemory
0x14002687f  jmp     loc_14002691E
0x140026884  mov     r10b, byte ptr cs:xmmword_14001A3D0+2
0x14002688b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026892  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026899  setnz   r8b
0x14002689d  and     r10b, 4
0x1400268a1  jnz     short loc_1400268A8
0x1400268a3  test    r8b, r8b
0x1400268a6  jz      short loc_1400268FD
0x1400268a8  mov     eax, edx
0x1400268aa  mov     edx, 10h
0x1400268af  mov     ecx, 212h
0x1400268b4  mov     [rsp+0B8h+var_68], eax
0x1400268b8  mov     [rsp+0B8h+var_70], 42Bh
0x1400268c0  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400268c7  mov     [rsp+0B8h+var_78], rax
0x1400268cc  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x1400268d3  mov     [rsp+0B8h+var_80], rax
0x1400268d8  mov     [rsp+0B8h+var_88], dx
0x1400268dd  mov     [rsp+0B8h+var_90], 12h
0x1400268e5  mov     [rsp+0B8h+var_98], 2
0x1400268ea  mov     r9, cs:WPP_GLOBAL_Control
0x1400268f1  mov     r9, [r9+40h]
0x1400268f5  mov     dl, r10b
0x1400268f8  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400268fd  cmp     byte ptr [rbx+50h], 18h
0x140026901  jbe     short loc_140026908
0x140026903  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140026908  test    sil, sil
0x14002690b  jz      short loc_14002691A
0x14002690d  xor     edx, edx
0x14002690f  lea     rcx, [rdi+50h]
0x140026913  call    RtlWriteUCharToUser
0x140026918  jmp     short loc_14002691E
0x14002691a  mov     [rdi+50h], r15b
0x14002691e  cmp     dword ptr [rbx+44h], 9000001Ch
0x140026925  jnz     short loc_140026982
0x140026927  mov     edx, [rbx+38h]
0x14002692a  mov     [rsp+0B8h+var_50], edx
0x14002692e  mov     eax, edx
0x140026930  btr     eax, 0Ah
0x140026934  mov     [rsp+0B8h+var_50], eax
0x140026938  mov     eax, edx
0x14002693a  and     eax, 0FFFFEBFFh
0x14002693f  mov     [rsp+0B8h+var_50], eax
0x140026943  and     edx, 0FFFFE9FFh
0x140026949  mov     [rsp+0B8h+var_50], edx
0x14002694d  mov     eax, 80h
0x140026952  cmovz   edx, eax
0x140026955  mov     [rsp+0B8h+var_50], edx
0x140026959  test    sil, sil
0x14002695c  jz      short loc_140026969
0x14002695e  lea     rcx, [rdi+38h]
0x140026962  call    RtlWriteULongToUser
0x140026967  jmp     short loc_14002696C
0x140026969  mov     [rdi+38h], edx
0x14002696c  test    sil, sil
0x14002696f  jz      short loc_14002697E
0x140026971  xor     edx, edx
0x140026973  lea     rcx, [rdi+44h]
0x140026977  call    RtlWriteULongToUser
0x14002697c  jmp     short loc_140026982
0x14002697e  mov     [rdi+44h], r15d
0x140026982  cmp     [rsp+0B8h+arg_20], r15b
0x14002698a  jz      short loc_1400269F0
0x14002698c  lea     r15, [rdi+38h]
0x140026990  test    sil, sil
0x140026993  jz      short loc_14002699F
0x140026995  mov     rcx, r15
0x140026998  call    RtlReadULongFromUser
0x14002699d  jmp     short loc_1400269A2
0x14002699f  mov     eax, [r15]
0x1400269a2  or      eax, 440000h
0x1400269a7  test    sil, sil
0x1400269aa  jz      short loc_1400269B8
0x1400269ac  mov     edx, eax
0x1400269ae  mov     rcx, r15
0x1400269b1  call    RtlWriteULongToUser
0x1400269b6  jmp     short loc_1400269BB
0x1400269b8  mov     [r15], eax
0x1400269bb  xor     r15d, r15d
0x1400269be  test    sil, sil
0x1400269c1  jz      short loc_1400269D0
0x1400269c3  xor     edx, edx
0x1400269c5  lea     rcx, [rdi+30h]
0x1400269c9  call    RtlWriteULong64ToUser
0x1400269ce  jmp     short loc_1400269D4
0x1400269d0  mov     [rdi+30h], r15
0x1400269d4  test    sil, sil
0x1400269d7  jz      short loc_1400269E8
0x1400269d9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400269dd  lea     rcx, [rdi+48h]
0x1400269e1  call    RtlWriteULong64ToUser
0x1400269e6  jmp     short loc_1400269F0
0x1400269e8  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x1400269f0  lea     rdx, [rbx+6Ah]; Src
0x1400269f4  lea     rcx, [rdi+6Ah]; void *
0x1400269f8  mov     r8d, r13d; Size
0x1400269fb  test    sil, sil
0x1400269fe  jz      short loc_140026A07
0x140026a00  call    RtlCopyToUser
0x140026a05  jmp     short loc_140026A0C
0x140026a07  call    RtlCopyVolatileMemory
0x140026a0c  test    sil, sil
0x140026a0f  jz      short loc_140026A1D
0x140026a11  xor     edx, edx
0x140026a13  mov     rcx, rdi
0x140026a16  call    RtlWriteULongToUser
0x140026a1b  jmp     short loc_140026A20
0x140026a1d  mov     [rdi], r15d
0x140026a20  mov     rax, [rsp+0B8h+arg_40]
0x140026a28  mov     [rax], rdi
0x140026a2b  mov     [rsp+0B8h+var_58], r15b
0x140026a30  lea     edi, [r13+6Ah]
0x140026a34  mov     [rsp+0B8h+var_3C], edi
0x140026a38  cmp     edi, r12d
0x140026a3b  jnb     loc_140026D56
0x140026a41  mov     r14d, 80000005h
0x140026a47  jmp     loc_1400267C7
0x140026a4c  mov     r13d, [rbx+3Ch]
0x140026a50  lea     ecx, [r13+68h]
0x140026a54  mov     [rsp+0B8h+arg_0], ecx
0x140026a5b  mov     eax, [rsp+0B8h+arg_30]
0x140026a62  cmp     eax, ecx
0x140026a64  jnb     short loc_140026A78
0x140026a66  cmp     eax, 68h ; 'h'
0x140026a69  jb      loc_140026D56
0x140026a6f  test    r15b, r15b
0x140026a72  jz      loc_140026D56
0x140026a78  add     eax, 0FFFFFF98h
0x140026a7b  cmp     r13d, eax
0x140026a7e  cmovnb  r13d, eax
0x140026a82  mov     [rsp+0B8h+var_58], 1
0x140026a87  mov     sil, [rsp+0B8h+arg_38]
0x140026a8f  xor     r15d, r15d
0x140026a92  lea     r8d, [r15+38h]; Size
0x140026a96  mov     rdx, rbx; Src
0x140026a99  mov     rdi, [rsp+0B8h+arg_28]
0x140026aa1  mov     rcx, rdi; void *
0x140026aa4  test    sil, sil
0x140026aa7  jz      short loc_140026AB0
0x140026aa9  call    RtlCopyToUser
0x140026aae  jmp     short loc_140026AB5
0x140026ab0  call    RtlCopyVolatileMemory
0x140026ab5  mov     edx, [rbx+38h]
0x140026ab8  cmp     dword ptr [rbx+44h], 9000001Ch
0x140026abf  jnz     short loc_140026B18
0x140026ac1  mov     [rsp+0B8h+var_48], edx
0x140026ac5  mov     eax, edx
0x140026ac7  btr     eax, 0Ah
0x140026acb  mov     [rsp+0B8h+var_48], eax
0x140026acf  mov     eax, edx
0x140026ad1  and     eax, 0FFFFEBFFh
0x140026ad6  mov     [rsp+0B8h+var_48], eax
0x140026ada  and     edx, 0FFFFE9FFh
0x140026ae0  mov     [rsp+0B8h+var_48], edx
0x140026ae4  mov     eax, 80h
0x140026ae9  cmovz   edx, eax
0x140026aec  mov     [rsp+0B8h+var_48], edx
0x140026af0  test    sil, sil
0x140026af3  jz      short loc_140026B00
0x140026af5  lea     rcx, [rdi+38h]
0x140026af9  call    RtlWriteULongToUser
0x140026afe  jmp     short loc_140026B03
0x140026b00  mov     [rdi+38h], edx
0x140026b03  lea     rcx, [rdi+40h]
0x140026b07  mov     eax, [rbx+40h]
0x140026b0a  test    sil, sil
0x140026b0d  jz      short loc_140026B3D
0x140026b0f  mov     edx, eax
0x140026b11  call    RtlWriteULongToUser
0x140026b16  jmp     short loc_140026B3F
0x140026b18  test    sil, sil
0x140026b1b  jz      short loc_140026B28
0x140026b1d  lea     rcx, [rdi+38h]
0x140026b21  call    RtlWriteULongToUser
0x140026b26  jmp     short loc_140026B2B
0x140026b28  mov     [rdi+38h], edx
0x140026b2b  lea     rcx, [rdi+40h]
0x140026b2f  test    dword ptr [rbx+38h], 400h
0x140026b36  jz      short loc_140026B07
0x140026b38  mov     eax, [rbx+44h]
0x140026b3b  jmp     short loc_140026B0A
0x140026b3d  mov     [rcx], eax
0x140026b3f  cmp     [rsp+0B8h+arg_20], r15b
0x140026b47  jz      short loc_140026BAA
0x140026b49  lea     r15, [rdi+38h]
0x140026b4d  test    sil, sil
0x140026b50  jz      short loc_140026B5C
0x140026b52  mov     rcx, r15
0x140026b55  call    RtlReadULongFromUser
0x140026b5a  jmp     short loc_140026B5F
0x140026b5c  mov     eax, [r15]
0x140026b5f  or      eax, 440000h
0x140026b64  test    sil, sil
0x140026b67  jz      short loc_140026B75
0x140026b69  mov     edx, eax
0x140026b6b  mov     rcx, r15
0x140026b6e  call    RtlWriteULongToUser
0x140026b73  jmp     short loc_140026B78
0x140026b75  mov     [r15], eax
0x140026b78  xor     r15d, r15d
0x140026b7b  test    sil, sil
  ... truncated ...
```
