# PrjfPrepareForDelete

- ea: `0x14003cc14`
- end: `0x14003d2c1`
- name: `PrjfPrepareForDelete`
- size: `1709`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002bf00`
- `0x140040670`

## callees

- `0x140002d9c`
- `0x1400035d4`
- `0x140003e6c`
- `0x1400047cc`
- `0x1400081f0`
- `0x14000d128`
- `0x14000d960`
- `0x140021550`
- `0x14002a6b4`
- `0x140039de8`
- `0x14003cc14`
- `0x140043b24`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14003d0f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003d0f3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003d0dc`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003d0dc`
- `FLTMGR!FltReleaseContext` at `0x14003d1f7`
- `FLTMGR!FltReleaseContext` at `0x14003d20b`
- `FLTMGR!FltReleaseContext` at `0x14003d220`
- `FLTMGR!FltReleaseContext` at `0x14003d1f7`
- `FLTMGR!FltReleaseContext` at `0x14003d20b`
- `FLTMGR!FltReleaseContext` at `0x14003d220`

## pseudocode

```c
__int64 __fastcall PrjfPrepareForDelete(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  struct _FILE_OBJECT *v4; // rdx
  struct _FLT_INSTANCE *v6; // rcx
  __int128 *UnionContextByFileName; // r15
  char ContextFileObject; // al
  __int64 v9; // r9
  _DWORD *v10; // r13
  char *v11; // rsi
  int v12; // edi
  int IsDirectoryEmpty; // eax
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int DoesNameExistInLayer; // eax
  int v20; // edx
  int SetFileContext; // eax
  int v22; // r8d
  struct _FILE_OBJECT *v23; // r8
  struct _FLT_INSTANCE *v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  char v30; // [rsp+28h] [rbp-41h]
  __int16 v31; // [rsp+30h] [rbp-39h]
  char v32; // [rsp+48h] [rbp-21h]
  char v33; // [rsp+50h] [rbp-19h]
  PFLT_CONTEXT Context[2]; // [rsp+60h] [rbp-9h] BYREF
  PFLT_CONTEXT v35[2]; // [rsp+70h] [rbp+7h] BYREF
  PFLT_CONTEXT v36; // [rsp+80h] [rbp+17h] BYREF
  char v37; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v38; // [rsp+E0h] [rbp+77h]
  char v39; // [rsp+E8h] [rbp+7Fh] BYREF

  v38 = a3;
  v35[0] = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context[0] = 0;
  v36 = 0;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  UnionContextByFileName = 0;
  v39 = 0;
  v37 = 0;
  ContextFileObject = PrjfGetContextFileObjectEx(v6, v4, Context, v35, &v36);
  v10 = v35[0];
  if ( !ContextFileObject )
  {
    DoesNameExistInLayer = PrjfDoesNameExistInLayer(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), &v37);
    v12 = DoesNameExistInLayer;
    if ( DoesNameExistInLayer >= 0 )
    {
      if ( !v37 )
      {
        v11 = (char *)Context[0];
        goto LABEL_49;
      }
      UnionContextByFileName = (__int128 *)PrjfGetUnionContextByFileName(
                                             CallbackData,
                                             *(PFLT_INSTANCE *)(a2 + 24),
                                             0,
                                             0);
      if ( UnionContextByFileName )
      {
        SetFileContext = PrjfGetSetFileContext(
                           *(PFLT_INSTANCE *)(a2 + 24),
                           *(PFILE_OBJECT *)(a2 + 32),
                           0,
                           0,
                           UnionContextByFileName,
                           0,
                           0,
                           Context);
        v12 = SetFileContext;
        if ( SetFileContext < 0 )
        {
          LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
          if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              525,
              v14,
              v22,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              13,
              102,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              231,
              SetFileContext);
          }
          v11 = (char *)Context[0];
          goto LABEL_55;
        }
        v11 = (char *)Context[0];
        goto LABEL_47;
      }
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = xmmword_14001A3D0 & 0x20;
        WPP_RECORDER_AND_TRACE_SF_sDq(
          517,
          v20,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          101,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          215,
          *(_QWORD *)(a2 + 32));
      }
      v12 = -1073689087;
    }
    else
    {
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v14,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          100,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          195,
          DoesNameExistInLayer);
      }
    }
    v11 = (char *)Context[0];
    goto LABEL_56;
  }
  v11 = (char *)Context[0];
  if ( !Context[0] || *((_DWORD *)Context[0] + 16) == 3 )
  {
    v18 = PrjfDoesNameExistInLayer(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), &v37);
    v12 = v18;
    if ( v18 < 0 )
    {
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v33 = v18;
        v32 = -83;
        v31 = 99;
        goto LABEL_9;
      }
      goto LABEL_56;
    }
    goto LABEL_24;
  }
  v12 = 0;
  if ( *(_DWORD *)v35[0] != 1 )
    goto LABEL_19;
  IsDirectoryEmpty = PrjfIsDirectoryEmpty(
                       (__int64)CallbackData,
                       *(struct _FLT_INSTANCE **)(a2 + 24),
                       *(struct _FILE_OBJECT **)(a2 + 32),
                       v9,
                       &v39);
  v12 = IsDirectoryEmpty;
  if ( IsDirectoryEmpty < 0 )
  {
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
    if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v33 = IsDirectoryEmpty;
      v32 = 88;
      v31 = 95;
LABEL_9:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        525,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        13,
        v31,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        v32,
        v33);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  if ( !v39 )
  {
    v12 = -1073741567;
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (BYTE1(xmmword_14001A3E0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = BYTE1(xmmword_14001A3E0) & 0x20;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        1037,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        13,
        96,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        99,
        1);
    }
    goto LABEL_56;
  }
  v16 = PrjfRemoveTombstonesFromDirectory(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  v12 = v16;
  if ( v16 >= 0 )
  {
LABEL_19:
    if ( (*(_DWORD *)(*((_QWORD *)v11 + 9) + 12LL) & 8) == 0 )
      goto LABEL_47;
    v17 = PrjfDoesNameExistInLayer(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), &v37);
    v12 = v17;
    if ( v17 < 0 )
    {
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v33 = v17;
        v32 = -111;
        v31 = 98;
        goto LABEL_9;
      }
      goto LABEL_56;
    }
LABEL_24:
    if ( !v37 )
    {
LABEL_49:
      if ( v10 )
      {
        if ( (v10[10] & 0x10) != 0 )
        {
          v23 = *(struct _FILE_OBJECT **)(a2 + 32);
          v24 = *(struct _FLT_INSTANCE **)(a2 + 24);
          v30 = *v10 == 1;
          *(_OWORD *)v35 = *((_OWORD *)v11 + 6);
          v25 = PrjfSendNotifyOperationCommand(CallbackData, v24, v23, (__int128 *)v35, v38, v30, 16, 0, 0, 0, 0);
          v12 = v25;
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v14) = BYTE1(xmmword_14001A3E0) & 0x20;
          if ( (BYTE1(xmmword_14001A3E0) & 0x20) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_sDL(
              1037,
              v14,
              v15,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              4,
              13,
              103,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              12,
              v25);
          }
        }
      }
      if ( !UnionContextByFileName )
        goto LABEL_56;
LABEL_55:
      PrjfReleaseUnionContext((char *)UnionContextByFileName, v14);
      goto LABEL_56;
    }
LABEL_47:
    ExAcquireFastMutex((PFAST_MUTEX)(v11 + 8));
    v11[280] = 1;
    ExReleaseFastMutex((PFAST_MUTEX)(v11 + 8));
    goto LABEL_49;
  }
  LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
  if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v33 = v16;
    v32 = 115;
    v31 = 97;
    goto LABEL_9;
  }
LABEL_56:
  if ( v11 )
    FltReleaseContext(v11);
  if ( v10 )
    FltReleaseContext(v10);
  if ( v36 )
    FltReleaseContext(v36);
  if ( v12 >= 0 )
  {
    v26 = PrjfSetParentPlaceHolderFlagsSynchronized(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), v15);
    v12 = v26;
    if ( v26 < 0
      && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v27) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v27,
        v28,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        104,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        47,
        v26);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003cc14  mov     [rsp-8+arg_0], rbx
0x14003cc19  mov     [rsp-8+arg_10], r8
0x14003cc1e  push    rbp
0x14003cc1f  push    rsi
0x14003cc20  push    rdi
0x14003cc21  push    r12
0x14003cc23  push    r13
0x14003cc25  push    r14
0x14003cc27  push    r15
0x14003cc29  lea     rbp, [rsp-27h]
0x14003cc2e  sub     rsp, 90h
0x14003cc35  xor     ebx, ebx
0x14003cc37  lea     rax, [rbp+57h+var_40]
0x14003cc3b  mov     r14, rdx
0x14003cc3e  mov     [rbp+57h+var_50], rbx
0x14003cc42  mov     rdx, [rdx+20h]; FileObject
0x14003cc46  lea     r9, [rbp+57h+var_50]
0x14003cc4a  mov     r12, rcx
0x14003cc4d  mov     [rbp+57h+Context], rbx
0x14003cc51  lea     r8, [rbp+57h+Context]
0x14003cc55  mov     [rbp+57h+var_40], rbx
0x14003cc59  mov     rcx, [r14+18h]; Instance
0x14003cc5d  mov     r15d, ebx
0x14003cc60  mov     [rbp+57h+arg_18], bl
0x14003cc63  mov     [rbp+57h+arg_8], bl
0x14003cc66  mov     [rsp+0C0h+var_A0], rax; Context
0x14003cc6b  call    PrjfGetContextFileObjectEx
0x14003cc70  mov     r13, [rbp+57h+var_50]
0x14003cc74  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003cc7b  test    al, al
0x14003cc7d  jz      loc_14003CF0F
0x14003cc83  mov     rsi, [rbp+57h+Context]
0x14003cc87  test    rsi, rsi
0x14003cc8a  jz      loc_14003CEA3
0x14003cc90  cmp     dword ptr [rsi+40h], 3
0x14003cc94  jz      loc_14003CEA3
0x14003cc9a  cmp     dword ptr [r13+0], 1
0x14003cc9f  mov     edi, ebx
0x14003cca1  jnz     loc_14003CE19
0x14003cca7  mov     r8, [r14+20h]
0x14003ccab  lea     rax, [rbp+57h+arg_18]
0x14003ccaf  mov     rdx, [r14+18h]
0x14003ccb3  mov     rcx, r12
0x14003ccb6  mov     [rsp+0C0h+var_A0], rax
0x14003ccbb  call    PrjfIsDirectoryEmpty
0x14003ccc0  mov     edi, eax
0x14003ccc2  test    eax, eax
0x14003ccc4  jns     short loc_14003CD3E
0x14003ccc6  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003cccc  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003ccd3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ccda  setnz   r8b
0x14003ccde  and     dl, 20h
0x14003cce1  jnz     short loc_14003CCEC
0x14003cce3  test    r8b, r8b
0x14003cce6  jz      loc_14003D1E8
0x14003ccec  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003ccf0  lea     r15, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ccf7  mov     dword ptr [rsp+0C0h+var_78], 1158h
0x14003ccff  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003cd06  mov     [rsp+0C0h+var_80], r15
0x14003cd0b  mov     [rsp+0C0h+var_88], r9
0x14003cd10  mov     word ptr [rsp+0C0h+var_90], 5Fh ; '_'
0x14003cd17  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x14003cd1f  mov     ecx, 20Dh
0x14003cd24  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14003cd29  mov     r9, cs:WPP_GLOBAL_Control
0x14003cd30  mov     r9, [r9+40h]
0x14003cd34  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003cd39  jmp     loc_14003D1EF
0x14003cd3e  cmp     [rbp+57h+arg_18], bl
0x14003cd41  jnz     short loc_14003CDB0
0x14003cd43  mov     edi, 0C0000101h
0x14003cd48  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14003cd4e  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003cd55  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003cd5c  setnz   r8b
0x14003cd60  and     dl, 20h
0x14003cd63  jnz     short loc_14003CD6E
0x14003cd65  test    r8b, r8b
0x14003cd68  jz      loc_14003D1E8
0x14003cd6e  mov     dword ptr [rsp+0C0h+var_70], edi
0x14003cd72  lea     r15, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003cd79  mov     dword ptr [rsp+0C0h+var_78], 1163h
0x14003cd81  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003cd88  mov     [rsp+0C0h+var_80], r15
0x14003cd8d  mov     ecx, 40Dh
0x14003cd92  mov     [rsp+0C0h+var_88], r9
0x14003cd97  mov     word ptr [rsp+0C0h+var_90], 60h ; '`'
0x14003cd9e  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x14003cda6  mov     byte ptr [rsp+0C0h+var_A0], 4
0x14003cdab  jmp     loc_14003CD29
0x14003cdb0  mov     rdx, [r14+20h]; FileObject
0x14003cdb4  mov     rcx, [r14+18h]; Instance
0x14003cdb8  call    PrjfRemoveTombstonesFromDirectory
0x14003cdbd  mov     edi, eax
0x14003cdbf  test    eax, eax
0x14003cdc1  jns     short loc_14003CE19
0x14003cdc3  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003cdc9  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003cdd0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003cdd7  setnz   r8b
0x14003cddb  and     dl, 20h
0x14003cdde  jnz     short loc_14003CDE9
0x14003cde0  test    r8b, r8b
0x14003cde3  jz      loc_14003D1E8
0x14003cde9  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003cded  lea     r15, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003cdf4  mov     dword ptr [rsp+0C0h+var_78], 1173h
0x14003cdfc  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ce03  mov     [rsp+0C0h+var_80], r15
0x14003ce08  mov     [rsp+0C0h+var_88], r9
0x14003ce0d  mov     word ptr [rsp+0C0h+var_90], 61h ; 'a'
0x14003ce14  jmp     loc_14003CD17
0x14003ce19  mov     rax, [rsi+48h]
0x14003ce1d  mov     ecx, [rax+0Ch]
0x14003ce20  test    cl, 8
0x14003ce23  jz      loc_14003D0D8
0x14003ce29  mov     rdx, [r14+18h]; Instance
0x14003ce2d  lea     r8, [rbp+57h+arg_8]
0x14003ce31  mov     rcx, r12; CallbackData
0x14003ce34  call    PrjfDoesNameExistInLayer
0x14003ce39  mov     edi, eax
0x14003ce3b  test    eax, eax
0x14003ce3d  jns     short loc_14003CE95
0x14003ce3f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003ce45  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003ce4c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003ce53  setnz   r8b
0x14003ce57  and     dl, 20h
0x14003ce5a  jnz     short loc_14003CE65
0x14003ce5c  test    r8b, r8b
0x14003ce5f  jz      loc_14003D1E8
0x14003ce65  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003ce69  lea     r15, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ce70  mov     dword ptr [rsp+0C0h+var_78], 1191h
0x14003ce78  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003ce7f  mov     [rsp+0C0h+var_80], r15
0x14003ce84  mov     [rsp+0C0h+var_88], r9
0x14003ce89  mov     word ptr [rsp+0C0h+var_90], 62h ; 'b'
0x14003ce90  jmp     loc_14003CD17
0x14003ce95  cmp     [rbp+57h+arg_8], bl
0x14003ce98  jz      loc_14003D105
0x14003ce9e  jmp     loc_14003D0D8
0x14003cea3  mov     rdx, [r14+18h]; Instance
0x14003cea7  lea     r8, [rbp+57h+arg_8]
0x14003ceab  mov     rcx, r12; CallbackData
0x14003ceae  call    PrjfDoesNameExistInLayer
0x14003ceb3  mov     edi, eax
0x14003ceb5  test    eax, eax
0x14003ceb7  jns     short loc_14003CE95
0x14003ceb9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003cebf  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003cec6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003cecd  setnz   r8b
0x14003ced1  and     dl, 20h
0x14003ced4  jnz     short loc_14003CEDF
0x14003ced6  test    r8b, r8b
0x14003ced9  jz      loc_14003D1E8
0x14003cedf  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003cee3  lea     r15, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ceea  mov     dword ptr [rsp+0C0h+var_78], 11ADh
0x14003cef2  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003cef9  mov     [rsp+0C0h+var_80], r15
0x14003cefe  mov     [rsp+0C0h+var_88], r9
0x14003cf03  mov     word ptr [rsp+0C0h+var_90], 63h ; 'c'
0x14003cf0a  jmp     loc_14003CD17
0x14003cf0f  mov     rdx, [r14+18h]; Instance
0x14003cf13  lea     r8, [rbp+57h+arg_8]
0x14003cf17  mov     rcx, r12; CallbackData
0x14003cf1a  call    PrjfDoesNameExistInLayer
0x14003cf1f  mov     edi, eax
0x14003cf21  test    eax, eax
0x14003cf23  jns     short loc_14003CF98
0x14003cf25  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003cf2b  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003cf32  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003cf39  setnz   r8b
0x14003cf3d  and     dl, 20h
0x14003cf40  jnz     short loc_14003CF50
0x14003cf42  test    r8b, r8b
0x14003cf45  jnz     short loc_14003CF50
0x14003cf47  mov     rsi, [rbp+57h+Context]
0x14003cf4b  jmp     loc_14003D1E8
0x14003cf50  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003cf54  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003cf5b  mov     dword ptr [rsp+0C0h+var_78], 11C3h
0x14003cf63  mov     ecx, 20Dh
0x14003cf68  mov     [rsp+0C0h+var_80], rsi
0x14003cf6d  mov     [rsp+0C0h+var_88], r9
0x14003cf72  mov     r9, cs:WPP_GLOBAL_Control
0x14003cf79  mov     word ptr [rsp+0C0h+var_90], 64h ; 'd'
0x14003cf80  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x14003cf88  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14003cf8d  mov     r9, [r9+40h]
0x14003cf91  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003cf96  jmp     short loc_14003CF47
0x14003cf98  cmp     [rbp+57h+arg_8], bl
0x14003cf9b  jz      loc_14003D101
0x14003cfa1  mov     rdx, [r14+18h]; Instance
0x14003cfa5  xor     r9d, r9d
0x14003cfa8  xor     r8d, r8d; String2
0x14003cfab  mov     rcx, r12; CallbackData
0x14003cfae  call    PrjfGetUnionContextByFileName
0x14003cfb3  mov     r15, rax
0x14003cfb6  test    rax, rax
0x14003cfb9  jnz     short loc_14003D032
0x14003cfbb  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003cfc1  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003cfc8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003cfcf  setnz   r8b
0x14003cfd3  and     dl, 20h
0x14003cfd6  jnz     short loc_14003CFDD
0x14003cfd8  test    r8b, r8b
0x14003cfdb  jz      short loc_14003D028
0x14003cfdd  mov     rax, [r14+20h]
0x14003cfe1  mov     ecx, 205h
0x14003cfe6  mov     r9, cs:WPP_GLOBAL_Control
0x14003cfed  mov     qword ptr [rsp+0C0h+var_70], rax
0x14003cff2  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003cff9  mov     dword ptr [rsp+0C0h+var_78], 11D7h
0x14003d001  mov     [rsp+0C0h+var_80], rsi
0x14003d006  mov     r9, [r9+40h]
0x14003d00a  mov     [rsp+0C0h+var_88], rax
0x14003d00f  mov     word ptr [rsp+0C0h+var_90], 65h ; 'e'
0x14003d016  mov     dword ptr [rsp+0C0h+var_98], 5
0x14003d01e  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14003d023  call    WPP_RECORDER_AND_TRACE_SF_sDq
0x14003d028  mov     edi, 0C000CE01h
0x14003d02d  jmp     loc_14003CF47
0x14003d032  mov     rdx, [r14+20h]; FileObject
0x14003d036  lea     rax, [rbp+57h+Context]
0x14003d03a  mov     rcx, [r14+18h]; Instance
0x14003d03e  xor     r9d, r9d
0x14003d041  mov     [rsp+0C0h+var_88], rax; __int64
0x14003d046  xor     r8d, r8d
0x14003d049  mov     [rsp+0C0h+var_90], rbx; __int64
0x14003d04e  mov     [rsp+0C0h+var_98], rbx; __int64
0x14003d053  mov     [rsp+0C0h+var_A0], r15; __int64
0x14003d058  call    PrjfGetSetFileContext
0x14003d05d  mov     edi, eax
0x14003d05f  test    eax, eax
0x14003d061  jns     short loc_14003D0D4
0x14003d063  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003d069  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003d070  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003d077  setnz   r8b
0x14003d07b  and     dl, 20h
0x14003d07e  jnz     short loc_14003D085
0x14003d080  test    r8b, r8b
0x14003d083  jz      short loc_14003D0CB
0x14003d085  mov     dword ptr [rsp+0C0h+var_70], eax
0x14003d089  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003d090  mov     dword ptr [rsp+0C0h+var_78], 11E7h
0x14003d098  mov     ecx, 20Dh
0x14003d09d  mov     [rsp+0C0h+var_80], rsi
0x14003d0a2  mov     [rsp+0C0h+var_88], r9
0x14003d0a7  mov     r9, cs:WPP_GLOBAL_Control
0x14003d0ae  mov     word ptr [rsp+0C0h+var_90], 66h ; 'f'
0x14003d0b5  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x14003d0bd  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14003d0c2  mov     r9, [r9+40h]
0x14003d0c6  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003d0cb  mov     rsi, [rbp+57h+Context]
0x14003d0cf  jmp     loc_14003D1E0
0x14003d0d4  mov     rsi, [rbp+57h+Context]
0x14003d0d8  lea     rcx, [rsi+8]; FastMutex
0x14003d0dc  call    cs:__imp_ExAcquireFastMutex
0x14003d0e3  nop     dword ptr [rax+rax+00h]
0x14003d0e8  lea     rcx, [rsi+8]; FastMutex
0x14003d0ec  mov     byte ptr [rsi+118h], 1
0x14003d0f3  call    cs:__imp_ExReleaseFastMutex
0x14003d0fa  nop     dword ptr [rax+rax+00h]
0x14003d0ff  jmp     short loc_14003D105
0x14003d101  mov     rsi, [rbp+57h+Context]
0x14003d105  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003d10c  test    r13, r13
0x14003d10f  jz      loc_14003D1DB
0x14003d115  mov     eax, [r13+28h]
0x14003d119  test    al, 10h
0x14003d11b  jz      loc_14003D1DB
0x14003d121  cmp     dword ptr [r13+0], 1
0x14003d126  lea     r9, [rbp+57h+var_50]
0x14003d12a  movups  xmm0, xmmword ptr [rsi+60h]
0x14003d12e  mov     r8, [r14+20h]
0x14003d132  setz    al
0x14003d135  mov     rdx, [r14+18h]
0x14003d139  xor     edi, edi
0x14003d13b  mov     qword ptr [rsp+0C0h+var_70], rdi
0x14003d140  mov     rcx, r12
0x14003d143  mov     [rsp+0C0h+var_78], dil
0x14003d148  mov     [rsp+0C0h+var_80], rdi
0x14003d14d  mov     [rsp+0C0h+var_88], rdi
0x14003d152  mov     dword ptr [rsp+0C0h+var_90], 10h
0x14003d15a  mov     byte ptr [rsp+0C0h+var_98], al
0x14003d15e  mov     rax, [rbp+57h+arg_10]
0x14003d162  mov     [rsp+0C0h+var_A0], rax
0x14003d167  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x14003d16c  call    PrjfSendNotifyOperationCommand
0x14003d171  mov     edi, eax
  ... truncated ...
```
