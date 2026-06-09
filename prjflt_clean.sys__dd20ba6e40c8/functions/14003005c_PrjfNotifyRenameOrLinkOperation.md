# PrjfNotifyRenameOrLinkOperation

- ea: `0x14003005c`
- end: `0x1400306ef`
- name: `PrjfNotifyRenameOrLinkOperation`
- size: `1683`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002c3f8`
- `0x14002c98c`

## callees

- `0x140002b50`
- `0x140002f3c`
- `0x1400047cc`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000d5e8`
- `0x14003005c`
- `0x14003a6e4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140030698`
- `ntoskrnl!ExReleaseFastMutex` at `0x140030698`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003066d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003066d`
- `FLTMGR!FltDeleteStreamHandleContext` at `0x1400305f0`
- `FLTMGR!FltDeleteStreamHandleContext` at `0x1400305f0`
- `FLTMGR!FltIsDirectory` at `0x14003013a`
- `FLTMGR!FltIsDirectory` at `0x14003013a`
- `FLTMGR!FltDeleteFileContext` at `0x14003061a`
- `FLTMGR!FltDeleteFileContext` at `0x14003061a`
- `FLTMGR!FltDeleteStreamContext` at `0x140030605`
- `FLTMGR!FltDeleteStreamContext` at `0x140030605`
- `FLTMGR!FltReleaseContext` at `0x1400306ac`
- `FLTMGR!FltReleaseContext` at `0x1400306c0`
- `FLTMGR!FltReleaseContext` at `0x1400306ac`
- `FLTMGR!FltReleaseContext` at `0x1400306c0`

## pseudocode

```c
__int64 __fastcall PrjfNotifyRenameOrLinkOperation(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        unsigned int a4,
        __int128 **a5)
{
  int v5; // esi
  char *v6; // r14
  __int128 *v7; // rcx
  _DWORD *v8; // r15
  __int128 *v9; // rdx
  char v10; // bl
  char v11; // al
  bool v12; // zf
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  char ContextFileObject; // al
  char v21; // al
  int NotificationMask; // eax
  void *v23; // r8
  char v24; // cl
  int v25; // eax
  __int64 v26; // rcx
  int SetContextFileObject; // eax
  struct _FILE_OBJECT *v28; // rdi
  struct _FLT_INSTANCE *v29; // rbx
  unsigned int v30; // eax
  int v32; // [rsp+20h] [rbp-A1h]
  int v33; // [rsp+28h] [rbp-99h]
  int v34; // [rsp+48h] [rbp-79h]
  char v35; // [rsp+60h] [rbp-61h]
  char v36; // [rsp+61h] [rbp-60h]
  unsigned __int8 IsDirectory; // [rsp+62h] [rbp-5Fh] BYREF
  char v38; // [rsp+63h] [rbp-5Eh]
  unsigned int v39; // [rsp+64h] [rbp-5Dh]
  unsigned int v40; // [rsp+68h] [rbp-59h] BYREF
  unsigned int v41; // [rsp+6Ch] [rbp-55h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-51h] BYREF
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-49h]
  PFLT_INSTANCE Instance; // [rsp+80h] [rbp-41h]
  PFLT_CONTEXT v45; // [rsp+88h] [rbp-39h] BYREF
  __int64 v46; // [rsp+90h] [rbp-31h]
  __int128 v47; // [rsp+A0h] [rbp-21h] BYREF
  __int128 v48; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-1h]

  FileObject = a3;
  v46 = a1;
  v5 = 0;
  Instance = a2;
  v6 = 0;
  v7 = *a5;
  v8 = 0;
  v9 = a5[7];
  v10 = 1;
  v39 = a4;
  Context = 0;
  v45 = 0;
  v41 = 0;
  v40 = 0;
  if ( v7 )
  {
    if ( !v9 )
    {
      v9 = 0;
LABEL_9:
      v11 = 0;
      goto LABEL_10;
    }
    if ( *(_QWORD *)v7 != *(_QWORD *)v9 || *((_QWORD *)v7 + 1) != *((_QWORD *)v9 + 1) )
      goto LABEL_9;
  }
  else if ( v9 )
  {
    goto LABEL_9;
  }
  v11 = 1;
LABEL_10:
  v36 = v11;
  if ( !v9 || v11 )
  {
    v38 = 0;
    goto LABEL_23;
  }
  v12 = (*((_DWORD *)v9 + 14) & 0x10000) == 0;
  v38 = 1;
  if ( v12 || (PrjfGetNotificationMask(a5 + 8) & 1) != 0 )
    goto LABEL_23;
  IsDirectory = 0;
  v13 = FltIsDirectory(FileObject, Instance, &IsDirectory);
  v5 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        174,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        181,
        v13);
    }
    return (unsigned int)v5;
  }
  v47 = *a5[7];
  v5 = PrjfSendNotifyOperationCommand(
         v46,
         Instance,
         FileObject,
         &v47,
         &EmptyPathFileName,
         IsDirectory,
         v39,
         a5 + 8,
         0,
         1,
         &v40);
  if ( v5 >= 0 )
  {
LABEL_23:
    ContextFileObject = PrjfGetContextFileObject(Instance, FileObject);
    v8 = v45;
    v35 = ContextFileObject;
    if ( !ContextFileObject )
    {
LABEL_49:
      v6 = (char *)Context;
      goto LABEL_50;
    }
    v16 = v39;
    if ( !v45 || (v39 & *((_DWORD *)v45 + 10)) == 0 || (v21 = 1, !*a5) )
      v21 = 0;
    if ( v36 )
    {
      if ( v21 )
        goto LABEL_37;
      if ( !*a5 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v39, v18, v19);
      if ( !*a5 )
      {
        v6 = (char *)Context;
        v5 = -1073689087;
        goto LABEL_86;
      }
      NotificationMask = PrjfGetNotificationMask(a5 + 8);
      v16 = v39;
      if ( (NotificationMask & v39) != 0 )
        goto LABEL_37;
      v21 = 0;
    }
    if ( !v21 )
    {
LABEL_48:
      ContextFileObject = v35;
      goto LABEL_49;
    }
LABEL_37:
    v49 = 0;
    v48 = 0;
    if ( (_DWORD)v16 == 128 )
      LODWORD(v48) = v8[10];
    v23 = a5 + 8;
    if ( !v36 )
      v23 = &EmptyPathFileName;
    if ( !v8 || (v24 = 1, *v8 != 1) )
      v24 = 0;
    LOBYTE(v34) = 0;
    LOBYTE(v33) = v24;
    v47 = **a5;
    v25 = PrjfSendNotifyOperationCommand(v46, Instance, FileObject, &v47, a5 + 1, v33, v16, v23, &v48, v34, &v41);
    v5 = v25;
    if ( v25 < 0 )
    {
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x20;
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDdd(
          525,
          v16,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v32,
          13,
          176,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          35,
          v25,
          v39);
    }
    goto LABEL_48;
  }
  ContextFileObject = 0;
  LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x20;
  if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sDL(
      525,
      v16,
      v18,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      175,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      202,
      v5);
    ContextFileObject = 0;
  }
LABEL_50:
  if ( v39 == 128 )
  {
    if ( !ContextFileObject )
    {
      if ( !v38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
      v26 = v40;
      if ( v40 == 1 )
      {
        LOBYTE(v16) = BYTE9(xmmword_14001A3E0) & 0x20;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
          v10 = 0;
        if ( (_BYTE)v16 || v10 )
        {
          LOBYTE(v18) = v10;
          WPP_RECORDER_AND_TRACE_SF_sD(
            1293,
            v16,
            v18,
            PrjfTraceRecorder,
            5,
            13,
            177,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            60);
        }
        goto LABEL_86;
      }
      if ( v40 + 1 <= 1 )
      {
        LOBYTE(v16) = BYTE9(xmmword_14001A3E0) & 0x20;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v18) = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
        {
          LOBYTE(v18) = 0;
        }
        if ( (_BYTE)v16 || (_BYTE)v18 )
          WPP_RECORDER_AND_TRACE_SF_sD(
            1293,
            v16,
            v18,
            PrjfTraceRecorder,
            5,
            13,
            178,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            76);
        if ( *a5 || !a5[7] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v26, v16, v18, v19);
        if ( !a5[7] )
          goto LABEL_72;
        v40 = PrjfGetNotificationMask(a5 + 8);
      }
      SetContextFileObject = PrjfGetSetContextFileObject(
                               Instance,
                               FileObject,
                               0,
                               (__int64)a5[7],
                               (__int64)(a5 + 8),
                               (__int64)&Context,
                               (__int64)&v45);
      v6 = (char *)Context;
      v5 = SetContextFileObject;
      v8 = v45;
      goto LABEL_86;
    }
    if ( !a5[7] )
    {
      v28 = FileObject;
      v29 = Instance;
      FltDeleteStreamHandleContext(Instance, FileObject, 0);
      FltDeleteStreamContext(v29, v28, 0);
      FltDeleteFileContext(v29, v28, 0);
      goto LABEL_86;
    }
    if ( v36 )
    {
      if ( v41 + 1 <= 1 )
      {
        if ( !*a5 )
        {
LABEL_72:
          v5 = -1073689087;
          goto LABEL_86;
        }
        v41 = PrjfGetNotificationMask(a5 + 8);
      }
    }
    else if ( v40 + 1 <= 1 )
    {
      v40 = PrjfGetNotificationMask(a5 + 8);
    }
    ExAcquireFastMutex((PFAST_MUTEX)(v6 + 8));
    *((_OWORD *)v6 + 6) = *a5[7];
    v30 = v40;
    if ( v36 )
      v30 = v41;
    v8[10] = v30;
    ExReleaseFastMutex((PFAST_MUTEX)(v6 + 8));
  }
LABEL_86:
  if ( v6 )
    FltReleaseContext(v6);
  if ( v8 )
    FltReleaseContext(v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003005c  push    rbp
0x14003005e  push    rbx
0x14003005f  push    rsi
0x140030060  push    rdi
0x140030061  push    r12
0x140030063  push    r13
0x140030065  push    r14
0x140030067  push    r15
0x140030069  lea     rbp, [rsp-17h]
0x14003006e  sub     rsp, 0D8h
0x140030075  mov     rax, cs:__security_cookie
0x14003007c  xor     rax, rsp
0x14003007f  mov     [rbp+4Fh+var_48], rax
0x140030083  mov     rdi, [rbp+4Fh+arg_20]
0x140030087  mov     [rbp+4Fh+FileObject], r8
0x14003008b  xor     r8d, r8d
0x14003008e  mov     [rbp+4Fh+var_80], rcx
0x140030092  mov     esi, r8d
0x140030095  mov     [rbp+4Fh+Instance], rdx
0x140030099  mov     r14d, r8d
0x14003009c  mov     rcx, [rdi]
0x14003009f  mov     r15d, r8d
0x1400300a2  mov     rdx, [rdi+38h]
0x1400300a6  lea     ebx, [r8+1]
0x1400300aa  mov     [rbp+4Fh+var_AC], r9d
0x1400300ae  mov     [rbp+4Fh+Context], r8
0x1400300b2  mov     [rbp+4Fh+var_88], r8
0x1400300b6  mov     [rbp+4Fh+var_A4], r8d
0x1400300ba  mov     [rbp+4Fh+var_A8], r8d
0x1400300be  test    rcx, rcx
0x1400300c1  jnz     short loc_1400300CA
0x1400300c3  test    rdx, rdx
0x1400300c6  jz      short loc_1400300E1
0x1400300c8  jmp     short loc_1400300E8
0x1400300ca  test    rdx, rdx
0x1400300cd  jz      short loc_1400300E5
0x1400300cf  mov     rax, [rcx]
0x1400300d2  cmp     rax, [rdx]
0x1400300d5  jnz     short loc_1400300E8
0x1400300d7  mov     rax, [rcx+8]
0x1400300db  cmp     rax, [rdx+8]
0x1400300df  jnz     short loc_1400300E8
0x1400300e1  mov     al, bl
0x1400300e3  jmp     short loc_1400300EB
0x1400300e5  mov     rdx, r8
0x1400300e8  mov     al, r8b
0x1400300eb  mov     [rbp+4Fh+var_AF], al
0x1400300ee  mov     r12b, 20h ; ' '
0x1400300f1  lea     r13, WPP_RECORDER_INITIALIZED
0x1400300f8  test    rdx, rdx
0x1400300fb  jz      loc_14003029F
0x140030101  test    al, al
0x140030103  jnz     loc_14003029F
0x140030109  test    dword ptr [rdx+38h], 10000h
0x140030110  mov     [rbp+4Fh+var_AD], bl
0x140030113  jz      loc_1400302A3
0x140030119  lea     rcx, [rdi+40h]
0x14003011d  call    PrjfGetNotificationMask
0x140030122  test    bl, al
0x140030124  jnz     loc_1400302A3
0x14003012a  mov     rdx, [rbp+4Fh+Instance]; Instance
0x14003012e  lea     r8, [rbp+4Fh+IsDirectory]; IsDirectory
0x140030132  mov     rcx, [rbp+4Fh+FileObject]; FileObject
0x140030136  mov     [rbp+4Fh+IsDirectory], sil
0x14003013a  call    cs:__imp_FltIsDirectory
0x140030141  nop     dword ptr [rax+rax+00h]
0x140030146  xor     ecx, ecx
0x140030148  mov     esi, eax
0x14003014a  test    eax, eax
0x14003014c  jns     short loc_1400301C6
0x14003014e  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140030154  lea     r13, WPP_RECORDER_INITIALIZED
0x14003015b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140030162  setnz   r8b
0x140030166  and     dl, r12b
0x140030169  jnz     short loc_140030174
0x14003016b  test    r8b, r8b
0x14003016e  jz      loc_1400306CC
0x140030174  mov     r9, cs:WPP_GLOBAL_Control
0x14003017b  mov     ecx, 205h
0x140030180  mov     dword ptr [rsp+110h+var_C0], eax
0x140030184  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003018b  mov     [rsp+110h+var_C8], 14B5h
0x140030193  mov     [rsp+110h+var_D0], rax
0x140030198  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003019f  mov     r9, [r9+40h]
0x1400301a3  mov     [rsp+110h+var_D8], rax
0x1400301a8  mov     word ptr [rsp+110h+var_E0], 0AEh
0x1400301af  mov     dword ptr [rsp+110h+var_E8], 5
0x1400301b7  mov     [rsp+110h+var_F0], 2
0x1400301bc  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400301c1  jmp     loc_1400306CC
0x1400301c6  mov     rax, [rdi+38h]
0x1400301ca  lea     r9, [rbp+4Fh+var_70]
0x1400301ce  mov     r8, [rbp+4Fh+FileObject]
0x1400301d2  mov     rdx, [rbp+4Fh+Instance]
0x1400301d6  movups  xmm0, xmmword ptr [rax]
0x1400301d9  lea     rax, [rbp+4Fh+var_A8]
0x1400301dd  mov     [rsp+110h+var_C0], rax
0x1400301e2  lea     rax, [rdi+40h]
0x1400301e6  mov     byte ptr [rsp+110h+var_C8], bl
0x1400301ea  mov     [rsp+110h+var_D0], rcx
0x1400301ef  mov     rcx, [rbp+4Fh+var_80]
0x1400301f3  mov     [rsp+110h+var_D8], rax
0x1400301f8  mov     eax, [rbp+4Fh+var_AC]
0x1400301fb  mov     dword ptr [rsp+110h+var_E0], eax
0x1400301ff  mov     al, [rbp+4Fh+IsDirectory]
0x140030202  mov     byte ptr [rsp+110h+var_E8], al
0x140030206  lea     rax, EmptyPathFileName
0x14003020d  mov     qword ptr [rsp+110h+var_F0], rax
0x140030212  movdqu  [rbp+4Fh+var_70], xmm0
0x140030217  call    PrjfSendNotifyOperationCommand
0x14003021c  xor     r10d, r10d
0x14003021f  mov     esi, eax
0x140030221  test    eax, eax
0x140030223  jns     short loc_1400302A3
0x140030225  mov     al, r10b
0x140030228  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003022f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030235  setnz   r8b
0x140030239  and     dl, r12b
0x14003023c  jnz     short loc_140030247
0x14003023e  test    r8b, r8b
0x140030241  jz      loc_140030432
0x140030247  mov     r9, cs:WPP_GLOBAL_Control
0x14003024e  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140030255  mov     dword ptr [rsp+110h+var_C0], esi
0x140030259  mov     ecx, 20Dh
0x14003025e  mov     [rsp+110h+var_C8], 14CAh
0x140030266  mov     [rsp+110h+var_D0], rax
0x14003026b  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030272  mov     r9, [r9+40h]
0x140030276  mov     [rsp+110h+var_D8], rax
0x14003027b  mov     word ptr [rsp+110h+var_E0], 0AFh
0x140030282  mov     dword ptr [rsp+110h+var_E8], 0Dh
0x14003028a  mov     [rsp+110h+var_F0], 2
0x14003028f  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140030294  mov     al, r14b
0x140030297  xor     r10d, r10d
0x14003029a  jmp     loc_140030432
0x14003029f  mov     [rbp+4Fh+var_AD], r8b
0x1400302a3  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x1400302a7  lea     r9, [rbp+4Fh+var_88]
0x1400302ab  mov     rcx, [rbp+4Fh+Instance]; Instance
0x1400302af  lea     r8, [rbp+4Fh+Context]
0x1400302b3  call    PrjfGetContextFileObject
0x1400302b8  mov     r15, [rbp+4Fh+var_88]
0x1400302bc  xor     r10d, r10d
0x1400302bf  mov     [rbp+4Fh+var_B0], al
0x1400302c2  test    al, al
0x1400302c4  jz      loc_14003042E
0x1400302ca  mov     edx, [rbp+4Fh+var_AC]
0x1400302cd  test    r15, r15
0x1400302d0  jz      short loc_1400302DF
0x1400302d2  test    [r15+28h], edx
0x1400302d6  jz      short loc_1400302DF
0x1400302d8  mov     al, bl
0x1400302da  cmp     [rdi], r10
0x1400302dd  jnz     short loc_1400302E2
0x1400302df  mov     al, r10b
0x1400302e2  mov     r14b, [rbp+4Fh+var_AF]
0x1400302e6  test    r14b, r14b
0x1400302e9  jz      short loc_140030325
0x1400302eb  test    al, al
0x1400302ed  jnz     short loc_14003032D
0x1400302ef  cmp     [rdi], r10
0x1400302f2  jnz     short loc_1400302F9
0x1400302f4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400302f9  mov     rdx, [rdi]
0x1400302fc  test    rdx, rdx
0x1400302ff  jnz     short loc_14003030F
0x140030301  mov     r14, [rbp+4Fh+Context]
0x140030305  mov     esi, 0C000CE01h
0x14003030a  jmp     loc_1400306A4
0x14003030f  lea     rcx, [rdi+40h]
0x140030313  call    PrjfGetNotificationMask
0x140030318  mov     edx, [rbp+4Fh+var_AC]
0x14003031b  xor     r10d, r10d
0x14003031e  test    edx, eax
0x140030320  jnz     short loc_14003032D
0x140030322  mov     al, r10b
0x140030325  test    al, al
0x140030327  jz      loc_14003042B
0x14003032d  xor     eax, eax
0x14003032f  xorps   xmm0, xmm0
0x140030332  mov     [rbp+4Fh+var_50], rax
0x140030336  movups  [rbp+4Fh+var_60], xmm0
0x14003033a  cmp     edx, 80h
0x140030340  jnz     short loc_140030349
0x140030342  mov     eax, [r15+28h]
0x140030346  mov     dword ptr [rbp+4Fh+var_60], eax
0x140030349  lea     r8, [rdi+40h]
0x14003034d  test    r14b, r14b
0x140030350  jnz     short loc_140030359
0x140030352  lea     r8, EmptyPathFileName
0x140030359  test    r15, r15
0x14003035c  jz      short loc_140030365
0x14003035e  mov     cl, bl
0x140030360  cmp     [r15], ebx
0x140030363  jz      short loc_140030368
0x140030365  mov     cl, r10b
0x140030368  mov     rax, [rdi]
0x14003036b  lea     r9, [rbp+4Fh+var_A4]
0x14003036f  mov     [rsp+110h+var_C0], r9
0x140030374  lea     r9, [rbp+4Fh+var_60]
0x140030378  mov     byte ptr [rsp+110h+var_C8], r10b
0x14003037d  mov     [rsp+110h+var_D0], r9
0x140030382  lea     r9, [rbp+4Fh+var_70]
0x140030386  movups  xmm0, xmmword ptr [rax]
0x140030389  mov     [rsp+110h+var_D8], r8
0x14003038e  lea     rax, [rdi+8]
0x140030392  mov     r8, [rbp+4Fh+FileObject]
0x140030396  mov     dword ptr [rsp+110h+var_E0], edx
0x14003039a  mov     rdx, [rbp+4Fh+Instance]
0x14003039e  mov     byte ptr [rsp+110h+var_E8], cl
0x1400303a2  mov     rcx, [rbp+4Fh+var_80]
0x1400303a6  movdqu  [rbp+4Fh+var_70], xmm0
0x1400303ab  mov     qword ptr [rsp+110h+var_F0], rax
0x1400303b0  call    PrjfSendNotifyOperationCommand
0x1400303b5  xor     r10d, r10d
0x1400303b8  mov     esi, eax
0x1400303ba  test    eax, eax
0x1400303bc  jns     short loc_14003042B
0x1400303be  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400303c5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400303cb  setnz   r8b
0x1400303cf  and     dl, r12b
0x1400303d2  jnz     short loc_1400303D9
0x1400303d4  test    r8b, r8b
0x1400303d7  jz      short loc_14003042B
0x1400303d9  mov     eax, [rbp+4Fh+var_AC]
0x1400303dc  mov     ecx, 20Dh
0x1400303e1  mov     r9, cs:WPP_GLOBAL_Control
0x1400303e8  mov     [rsp+110h+var_B8], eax
0x1400303ec  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400303f3  mov     dword ptr [rsp+110h+var_C0], esi
0x1400303f7  mov     [rsp+110h+var_C8], 1523h
0x1400303ff  mov     r9, [r9+40h]
0x140030403  mov     [rsp+110h+var_D0], rax
0x140030408  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003040f  mov     [rsp+110h+var_D8], rax
0x140030414  mov     word ptr [rsp+110h+var_E0], 0B0h
0x14003041b  mov     dword ptr [rsp+110h+var_E8], 0Dh
0x140030423  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x140030428  xor     r10d, r10d
0x14003042b  mov     al, [rbp+4Fh+var_B0]
0x14003042e  mov     r14, [rbp+4Fh+Context]
0x140030432  cmp     [rbp+4Fh+var_AC], 80h
0x140030439  jnz     loc_1400306A4
0x14003043f  test    al, al
0x140030441  jnz     loc_1400305D6
0x140030447  cmp     [rbp+4Fh+var_AD], r10b
0x14003044b  jnz     short loc_140030455
0x14003044d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140030452  xor     r10d, r10d
0x140030455  mov     ecx, [rbp+4Fh+var_A8]
0x140030458  cmp     ecx, ebx
0x14003045a  jnz     short loc_1400304D8
0x14003045c  mov     dl, byte ptr cs:xmmword_14001A3E0+9
0x140030462  and     dl, r12b
0x140030465  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003046c  jz      short loc_14003047C
0x14003046e  mov     rax, cs:WPP_GLOBAL_Control
0x140030475  cmp     [rax+48h], r10w
0x14003047a  jnz     short loc_14003047F
0x14003047c  mov     bl, r10b
0x14003047f  test    dl, dl
0x140030481  jnz     short loc_14003048B
0x140030483  test    bl, bl
0x140030485  jz      loc_1400306A4
0x14003048b  mov     r9, cs:_PrjfTraceRecorder
0x140030492  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140030499  mov     [rsp+110h+var_C8], 153Ch
0x1400304a1  mov     ecx, 50Dh
0x1400304a6  mov     [rsp+110h+var_D0], rax
0x1400304ab  mov     r8b, bl
0x1400304ae  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400304b5  mov     [rsp+110h+var_D8], rax
0x1400304ba  mov     word ptr [rsp+110h+var_E0], 0B1h
0x1400304c1  mov     dword ptr [rsp+110h+var_E8], 0Dh
0x1400304c9  mov     [rsp+110h+var_F0], 5
0x1400304ce  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400304d3  jmp     loc_1400306A4
0x1400304d8  lea     eax, [rcx+1]
0x1400304db  cmp     eax, ebx
0x1400304dd  ja      loc_14003058B
0x1400304e3  mov     dl, byte ptr cs:xmmword_14001A3E0+9
0x1400304e9  and     dl, r12b
0x1400304ec  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400304f3  jz      short loc_140030506
0x1400304f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400304fc  mov     r8b, bl
0x1400304ff  cmp     [rax+48h], r10w
0x140030504  jnz     short loc_140030509
0x140030506  mov     r8b, r10b
0x140030509  test    dl, dl
0x14003050b  jnz     short loc_140030512
0x14003050d  test    r8b, r8b
0x140030510  jz      short loc_14003055A
0x140030512  mov     r9, cs:_PrjfTraceRecorder
  ... truncated ...
```
