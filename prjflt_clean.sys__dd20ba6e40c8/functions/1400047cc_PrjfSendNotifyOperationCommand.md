# PrjfSendNotifyOperationCommand

- ea: `0x1400047cc`
- end: `0x140005004`
- name: `PrjfSendNotifyOperationCommand`
- size: `2104`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009d20`
- `0x140024758`
- `0x140029650`
- `0x14003005c`
- `0x14003cc14`

## callees

- `0x140002b50`
- `0x140003480`
- `0x140003e6c`
- `0x1400047cc`
- `0x14000be80`
- `0x14000d128`
- `0x14000d754`
- `0x14000ef78`
- `0x14000fc3c`
- `0x14000fdd8`
- `0x140010360`
- `0x140032fd8`
- `0x140033bd0`
- `0x14003a5cc`
- `0x14003b380`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004f7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f7a`
- `ntoskrnl!PsGetProcessId` at `0x140004bb4`
- `ntoskrnl!PsGetProcessId` at `0x140004bb4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000492c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000492c`
- `FLTMGR!FltGetRequestorProcess` at `0x1400049d9`
- `FLTMGR!FltGetRequestorProcess` at `0x1400049d9`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400049a5`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400049a5`
- `FLTMGR!FltReleaseContext` at `0x140004fa3`
- `FLTMGR!FltReleaseContext` at `0x140004fb8`
- `FLTMGR!FltReleaseContext` at `0x140004fcd`
- `FLTMGR!FltReleaseContext` at `0x140004fa3`
- `FLTMGR!FltReleaseContext` at `0x140004fb8`
- `FLTMGR!FltReleaseContext` at `0x140004fcd`

## pseudocode

```c
__int64 __fastcall PrjfSendNotifyOperationCommand(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int128 *a4,
        __int64 a5,
        char a6,
        int a7,
        __int64 a8,
        __int64 a9,
        char a10,
        _DWORD *a11)
{
  int inited; // ebx
  void *v14; // r13
  char *v15; // rsi
  __int64 v16; // xmm1_8
  void *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  NTSTATUS StreamHandleContext; // eax
  int v22; // r12d
  struct _KPROCESS *RequestorProcess; // rax
  PVOID *v24; // rdi
  __int64 UnionContext; // rax
  struct _KPROCESS *v26; // rcx
  char v27; // r10
  unsigned int ProcessId; // eax
  int v29; // ecx
  int Timeout; // [rsp+28h] [rbp-E0h]
  __int16 v32; // [rsp+38h] [rbp-D0h]
  char v33; // [rsp+50h] [rbp-B8h]
  char v34; // [rsp+60h] [rbp-A8h]
  __int64 v35; // [rsp+68h] [rbp-A0h]
  __int64 v36; // [rsp+78h] [rbp-90h] BYREF
  void *v37; // [rsp+80h] [rbp-88h] BYREF
  PFLT_CONTEXT v38; // [rsp+88h] [rbp-80h]
  PFLT_CONTEXT Context; // [rsp+90h] [rbp-78h] BYREF
  int v40; // [rsp+98h] [rbp-70h] BYREF
  PFLT_CONTEXT v41; // [rsp+A0h] [rbp-68h]
  PVOID P[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v44[74]; // [rsp+C8h] [rbp-40h] BYREF
  int v47; // [rsp+368h] [rbp+260h]

  v40 = 4;
  v37 = 0;
  v36 = 0;
  inited = 0;
  v14 = 0;
  memset(v44, 0, 0x220u);
  v15 = 0;
  LOBYTE(v44[0]) = a6;
  Context = 0;
  v38 = 0;
  v41 = 0;
  HIDWORD(v44[0]) = a7;
  *(_OWORD *)P = 0;
  if ( a9 )
  {
    v16 = *(_QWORD *)(a9 + 16);
    *(_OWORD *)&v44[1] = *(_OWORD *)a9;
    v44[3] = v16;
  }
  v17 = &EmptyPathFileName;
  if ( a8 )
    LODWORD(v17) = a8;
  v47 = (int)v17;
  if ( (unsigned __int8)PrjfGetContextFileObject(a2, a3) )
  {
    KeWaitForSingleObject((char *)v38 + 288, Executive, 0, 0, 0);
    if ( *((_BYTE *)v38 + 282) )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v18) = BYTE1(xmmword_14001A3E0) & 0x40;
      if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDDZ(1038, v18, v19, *((_QWORD *)WPP_GLOBAL_Control + 8), 4);
      goto LABEL_65;
    }
  }
  else if ( !a10 )
  {
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDDZ(526, v18, v19, *((_QWORD *)WPP_GLOBAL_Control + 8), 2);
    goto LABEL_65;
  }
  StreamHandleContext = FltGetStreamHandleContext(a2, a3, &Context);
  inited = StreamHandleContext;
  if ( StreamHandleContext >= 0 )
  {
    v22 = (int)a1;
    v24 = (PVOID *)((char *)Context + 72);
    goto LABEL_27;
  }
  if ( StreamHandleContext == -1073741275 && a10 )
  {
    v22 = (int)a1;
    RequestorProcess = FltGetRequestorProcess(a1);
    inited = PrjfInitProcessInfo(RequestorProcess);
    if ( inited < 0 )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDL(
          526,
          v18,
          v19,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          181,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          107,
          inited);
      goto LABEL_65;
    }
    v24 = P;
LABEL_27:
    v43 = *a4;
    UnionContext = PrjfGetUnionContext(a2, &v43);
    v15 = (char *)UnionContext;
    if ( !UnionContext || !*(_QWORD *)(UnionContext + 80) )
    {
      v18 = 3221278209LL;
      inited = -1073689087;
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v27 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_65;
      v35 = a5;
      v34 = a7;
      v33 = -112;
      v32 = 183;
LABEL_64:
      LOBYTE(v18) = v27;
      WPP_RECORDER_AND_TRACE_SF_sDdDZ(
        526,
        v18,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        v32,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        v33,
        1,
        v34,
        v35);
      goto LABEL_65;
    }
    if ( (*(_DWORD *)(UnionContext + 800) & 1) == 0 )
    {
      v26 = *(struct _KPROCESS **)(UnionContext + 32);
      if ( !v26 )
      {
        v18 = 3221278209LL;
        inited = -1073689087;
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v27 = BYTE1(xmmword_14001A3D0) & 0x40;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_65;
        v35 = a5;
        v34 = a7;
        v33 = -86;
        v32 = 184;
        goto LABEL_64;
      }
      ProcessId = (unsigned int)PsGetProcessId(v26);
      v29 = *((_DWORD *)v24 + 2);
      if ( ProcessId == v29 )
      {
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v18) = BYTE1(xmmword_14001A3E0) & 0x40;
        if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDDZDZ(v29, v18, v19, *((_QWORD *)WPP_GLOBAL_Control + 8), Timeout);
        goto LABEL_65;
      }
    }
    v43 = *a4;
    inited = PrjfPrepareCommandForFilePath(
               a5,
               (unsigned int)&v43,
               7,
               v47,
               (__int64)v44,
               (__int64)Context,
               (__int64)v24,
               (__int64)&v37,
               (__int64)&v36 + 4);
    if ( inited < 0 )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v18,
          v19,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          186,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          205,
          inited,
          a5);
      v14 = v37;
      goto LABEL_65;
    }
    v14 = v37;
    inited = PrjfSendCommand(v22, (_DWORD)a2, (_DWORD)v37, 0, (__int64)&v36, (__int64)&v40);
    if ( inited < 0 )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v18,
          v19,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          187,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          222,
          inited,
          a5);
      goto LABEL_65;
    }
    if ( !a11 )
      goto LABEL_65;
    v18 = (unsigned int)v36;
    if ( (_DWORD)v36 != -1 )
    {
      if ( (v36 & 0xFFFFE000) != 0 )
      {
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = BYTE9(xmmword_14001A3D0) & 0x40;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            782,
            v18,
            v19,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3,
            14,
            188,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            246,
            v36);
        }
        v18 = 0xFFFFFFFFLL;
LABEL_59:
        LODWORD(v36) = v18;
        goto LABEL_60;
      }
      if ( (v36 & 1) != 0 )
      {
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = BYTE1(xmmword_14001A3E0) & 0x40;
          WPP_RECORDER_AND_TRACE_SF_sDDd(
            1038,
            v18,
            v19,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            4,
            14,
            189,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            3,
            v36,
            1);
        }
        v18 = 1;
        goto LABEL_59;
      }
    }
LABEL_60:
    *a11 = v18;
    goto LABEL_65;
  }
  LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x20;
  if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sDdDZ(
      525,
      v18,
      v19,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      182,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      119,
      StreamHandleContext,
      a7,
      a5);
LABEL_65:
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0x68734A50u);
  if ( v14 )
    PrjfFreeCommandBuffer(v14);
  if ( v38 )
    FltReleaseContext(v38);
  if ( v41 )
    FltReleaseContext(v41);
  if ( Context )
    FltReleaseContext(Context);
  if ( v15 )
    PrjfReleaseUnionContext(v15, v18, v19, v20);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400047cc  mov     rax, rsp
0x1400047cf  mov     [rax+10h], rbx
0x1400047d3  mov     [rax+20h], r9
0x1400047d7  mov     [rax+8], rcx
0x1400047db  push    rbp
0x1400047dc  push    rsi
0x1400047dd  push    rdi
0x1400047de  push    r12
0x1400047e0  push    r13
0x1400047e2  push    r14
0x1400047e4  push    r15
0x1400047e6  lea     rbp, [rax-218h]
0x1400047ed  sub     rsp, 2E0h
0x1400047f4  xor     edi, edi
0x1400047f6  mov     [rbp+210h+var_280], 4
0x1400047fd  mov     r12, r8
0x140004800  mov     [rsp+310h+var_298], rdi
0x140004805  mov     r14, rdx
0x140004808  mov     dword ptr [rsp+310h+var_2A0+4], edi
0x14000480c  xor     edx, edx; Val
0x14000480e  mov     dword ptr [rsp+310h+var_2A0], edi
0x140004812  mov     r8d, 220h; Size
0x140004818  lea     rcx, [rbp+210h+var_250]; void *
0x14000481c  mov     ebx, edi
0x14000481e  mov     r13d, edi
0x140004821  call    memset
0x140004826  mov     al, [rbp+210h+arg_28]
0x14000482c  xorps   xmm0, xmm0
0x14000482f  mov     r15d, [rbp+210h+arg_30]
0x140004836  mov     esi, edi
0x140004838  mov     [rbp+210h+var_250], al
0x14000483b  mov     rax, [rbp+210h+arg_40]
0x140004842  mov     [rbp+210h+Context], rdi
0x140004846  mov     [rbp+210h+var_290], rdi
0x14000484a  mov     [rbp+210h+var_278], rdi
0x14000484e  mov     [rbp+210h+var_24C], r15d
0x140004852  movups  xmmword ptr [rbp+210h+P], xmm0
0x140004856  test    rax, rax
0x140004859  jz      short loc_14000486C
0x14000485b  movups  xmm0, xmmword ptr [rax]
0x14000485e  movsd   xmm1, qword ptr [rax+10h]
0x140004863  movups  [rbp+210h+var_248], xmm0
0x140004867  movsd   [rbp+210h+var_238], xmm1
0x14000486c  mov     rax, [rbp+210h+arg_38]
0x140004873  lea     rcx, EmptyPathFileName
0x14000487a  test    rax, rax
0x14000487d  lea     r9, [rbp+210h+var_278]
0x140004881  lea     r8, [rbp+210h+var_290]
0x140004885  mov     rdx, r12; FileObject
0x140004888  cmovnz  rcx, rax
0x14000488c  mov     [rbp+210h+arg_40], rcx
0x140004893  mov     rcx, r14; Instance
0x140004896  call    PrjfGetContextFileObject
0x14000489b  mov     dil, [rbp+210h+arg_48]
0x1400048a2  test    al, al
0x1400048a4  jnz     short loc_140004914
0x1400048a6  test    dil, dil
0x1400048a9  jnz     loc_14000499B
0x1400048af  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400048b5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400048bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400048c3  setnz   r8b
0x1400048c7  and     dl, 40h
0x1400048ca  jnz     short loc_1400048D5
0x1400048cc  test    r8b, r8b
0x1400048cf  jz      loc_140004F6C
0x1400048d5  mov     rax, [rbp+210h+arg_20]
0x1400048dc  mov     ecx, 20Eh
0x1400048e1  mov     [rsp+310h+var_2B8], rax
0x1400048e6  mov     dword ptr [rsp+310h+var_2C0], r15d
0x1400048eb  mov     dword ptr [rsp+310h+var_2C8], 1639h
0x1400048f3  mov     word ptr [rsp+310h+var_2E0], 0B3h
0x1400048fa  mov     byte ptr [rsp+310h+Timeout], 2
0x1400048ff  mov     r9, cs:WPP_GLOBAL_Control
0x140004906  mov     r9, [r9+40h]
0x14000490a  call    WPP_RECORDER_AND_TRACE_SF_sDDZ
0x14000490f  jmp     loc_140004F6C
0x140004914  mov     rcx, [rbp+210h+var_290]
0x140004918  xor     r9d, r9d; Alertable
0x14000491b  add     rcx, 120h; Object
0x140004922  mov     [rsp+310h+Timeout], rbx; Timeout
0x140004927  xor     r8d, r8d; WaitMode
0x14000492a  xor     edx, edx; WaitReason
0x14000492c  call    cs:__imp_KeWaitForSingleObject
0x140004933  nop     dword ptr [rax+rax+00h]
0x140004938  mov     rcx, [rbp+210h+var_290]
0x14000493c  mov     al, [rcx+11Ah]
0x140004942  test    al, al
0x140004944  jz      short loc_14000499B
0x140004946  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14000494c  lea     rax, WPP_RECORDER_INITIALIZED
0x140004953  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000495a  setnz   r8b
0x14000495e  and     dl, 40h
0x140004961  jnz     short loc_14000496C
0x140004963  test    r8b, r8b
0x140004966  jz      loc_140004F6C
0x14000496c  mov     rax, [rbp+210h+arg_20]
0x140004973  mov     ecx, 40Eh
0x140004978  mov     [rsp+310h+var_2B8], rax
0x14000497d  mov     dword ptr [rsp+310h+var_2C0], r15d
0x140004982  mov     dword ptr [rsp+310h+var_2C8], 164Fh
0x14000498a  mov     word ptr [rsp+310h+var_2E0], 0B4h
0x140004991  mov     byte ptr [rsp+310h+Timeout], 4
0x140004996  jmp     loc_1400048FF
0x14000499b  lea     r8, [rbp+210h+Context]; Context
0x14000499f  mov     rdx, r12; FileObject
0x1400049a2  mov     rcx, r14; Instance
0x1400049a5  call    cs:__imp_FltGetStreamHandleContext
0x1400049ac  nop     dword ptr [rax+rax+00h]
0x1400049b1  mov     ebx, eax
0x1400049b3  test    eax, eax
0x1400049b5  jns     loc_140004AEC
0x1400049bb  cmp     eax, 0C0000225h
0x1400049c0  jnz     loc_140004A78
0x1400049c6  test    dil, dil
0x1400049c9  jz      loc_140004A78
0x1400049cf  mov     r12, [rbp+210h+CallbackData]
0x1400049d6  mov     rcx, r12; CallbackData
0x1400049d9  call    cs:__imp_FltGetRequestorProcess
0x1400049e0  nop     dword ptr [rax+rax+00h]
0x1400049e5  mov     rcx, rax; Process
0x1400049e8  lea     rdx, [rbp+210h+P]
0x1400049ec  call    PrjfInitProcessInfo
0x1400049f1  mov     ebx, eax
0x1400049f3  test    eax, eax
0x1400049f5  jns     short loc_140004A6F
0x1400049f7  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400049fd  lea     rax, WPP_RECORDER_INITIALIZED
0x140004a04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004a0b  setnz   r8b
0x140004a0f  and     dl, 40h
0x140004a12  jnz     short loc_140004A1D
0x140004a14  test    r8b, r8b
0x140004a17  jz      loc_140004F6C
0x140004a1d  mov     r9, cs:WPP_GLOBAL_Control
0x140004a24  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140004a2b  mov     dword ptr [rsp+310h+var_2C0], ebx
0x140004a2f  mov     ecx, 20Eh
0x140004a34  mov     dword ptr [rsp+310h+var_2C8], 166Bh
0x140004a3c  mov     qword ptr [rsp+310h+var_2D0], rax
0x140004a41  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140004a48  mov     r9, [r9+40h]
0x140004a4c  mov     [rsp+310h+var_2D8], rax
0x140004a51  mov     word ptr [rsp+310h+var_2E0], 0B5h
0x140004a58  mov     dword ptr [rsp+310h+var_2E8], 0Eh
0x140004a60  mov     byte ptr [rsp+310h+Timeout], 2
0x140004a65  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140004a6a  jmp     loc_140004F6C
0x140004a6f  lea     rdi, [rbp+210h+P]
0x140004a73  jmp     loc_140004AFB
0x140004a78  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004a7e  lea     rax, WPP_RECORDER_INITIALIZED
0x140004a85  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004a8c  setnz   r8b
0x140004a90  and     dl, 20h
0x140004a93  jnz     short loc_140004A9E
0x140004a95  test    r8b, r8b
0x140004a98  jz      loc_140004F6C
0x140004a9e  mov     rax, [rbp+210h+arg_20]
0x140004aa5  mov     ecx, 20Dh
0x140004aaa  mov     [rsp+310h+var_2B0], rax
0x140004aaf  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140004ab6  mov     dword ptr [rsp+310h+var_2B8], r15d
0x140004abb  mov     dword ptr [rsp+310h+var_2C0], ebx
0x140004abf  mov     dword ptr [rsp+310h+var_2C8], 1677h
0x140004ac7  mov     qword ptr [rsp+310h+var_2D0], rax
0x140004acc  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140004ad3  mov     [rsp+310h+var_2D8], rax
0x140004ad8  mov     word ptr [rsp+310h+var_2E0], 0B6h
0x140004adf  mov     dword ptr [rsp+310h+var_2E8], 0Dh
0x140004ae7  jmp     loc_140004F57
0x140004aec  mov     rdi, [rbp+210h+Context]
0x140004af0  mov     r12, [rbp+210h+CallbackData]
0x140004af7  add     rdi, 48h ; 'H'
0x140004afb  mov     rax, [rbp+210h+arg_18]
0x140004b02  lea     rdx, [rbp+210h+var_260]
0x140004b06  mov     rcx, r14
0x140004b09  movaps  xmm0, xmmword ptr [rax]
0x140004b0c  movdqa  [rbp+210h+var_260], xmm0
0x140004b11  call    PrjfGetUnionContext
0x140004b16  mov     rsi, rax
0x140004b19  test    rax, rax
0x140004b1c  jz      loc_140004EE0
0x140004b22  cmp     [rax+50h], r13
0x140004b26  jz      loc_140004EE0
0x140004b2c  mov     ecx, [rax+320h]
0x140004b32  test    cl, 1
0x140004b35  jnz     loc_140004C1F
0x140004b3b  mov     rcx, [rax+20h]; Process
0x140004b3f  test    rcx, rcx
0x140004b42  jnz     short loc_140004BB4
0x140004b44  mov     edx, 0C000CE01h
0x140004b49  mov     ebx, edx
0x140004b4b  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x140004b52  lea     rax, WPP_RECORDER_INITIALIZED
0x140004b59  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004b60  setnz   r8b
0x140004b64  and     r10b, 40h
0x140004b68  jnz     short loc_140004B73
0x140004b6a  test    r8b, r8b
0x140004b6d  jz      loc_140004F6C
0x140004b73  mov     rax, [rbp+210h+arg_20]
0x140004b7a  mov     [rsp+310h+var_2B0], rax
0x140004b7f  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140004b86  mov     dword ptr [rsp+310h+var_2B8], r15d
0x140004b8b  mov     dword ptr [rsp+310h+var_2C0], edx
0x140004b8f  mov     dword ptr [rsp+310h+var_2C8], 16AAh
0x140004b97  mov     qword ptr [rsp+310h+var_2D0], rax
0x140004b9c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140004ba3  mov     [rsp+310h+var_2D8], rax
0x140004ba8  mov     word ptr [rsp+310h+var_2E0], 0B8h
0x140004baf  jmp     loc_140004F47
0x140004bb4  call    cs:__imp_PsGetProcessId
0x140004bbb  nop     dword ptr [rax+rax+00h]
0x140004bc0  mov     ecx, [rdi+8]
0x140004bc3  cmp     eax, ecx
0x140004bc5  jnz     short loc_140004C1F
0x140004bc7  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140004bcd  lea     rax, WPP_RECORDER_INITIALIZED
0x140004bd4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004bdb  setnz   r8b
0x140004bdf  and     dl, 40h
0x140004be2  jnz     short loc_140004BED
0x140004be4  test    r8b, r8b
0x140004be7  jz      loc_140004F6C
0x140004bed  mov     rax, [rdi]
0x140004bf0  mov     r9, cs:WPP_GLOBAL_Control
0x140004bf7  mov     qword ptr [rsp+310h+var_2A8], rax
0x140004bfc  mov     rax, [rbp+210h+arg_20]
0x140004c03  mov     dword ptr [rsp+310h+var_2B0], ecx
0x140004c07  mov     r9, [r9+40h]
0x140004c0b  mov     [rsp+310h+var_2B8], rax
0x140004c10  mov     dword ptr [rsp+310h+var_2C0], r15d
0x140004c15  call    WPP_RECORDER_AND_TRACE_SF_sDDZDZ
0x140004c1a  jmp     loc_140004F6C
0x140004c1f  mov     rax, [rbp+210h+arg_18]
0x140004c26  lea     rdx, [rbp+210h+var_260]
0x140004c2a  mov     r9, [rbp+210h+arg_40]
0x140004c31  mov     r8d, 7
0x140004c37  movaps  xmm0, xmmword ptr [rax]
0x140004c3a  lea     rax, [rsp+310h+var_2A0+4]
0x140004c3f  mov     qword ptr [rsp+310h+var_2D0], rax
0x140004c44  lea     rax, [rsp+310h+var_298]
0x140004c49  mov     [rsp+310h+var_2D8], rax
0x140004c4e  mov     rax, [rbp+210h+Context]
0x140004c52  mov     [rsp+310h+var_2E0], rdi
0x140004c57  mov     rdi, [rbp+210h+arg_20]
0x140004c5e  mov     [rsp+310h+var_2E8], rax
0x140004c63  mov     rcx, rdi
0x140004c66  lea     rax, [rbp+210h+var_250]
0x140004c6a  movdqa  [rbp+210h+var_260], xmm0
0x140004c6f  mov     [rsp+310h+Timeout], rax
0x140004c74  call    PrjfPrepareCommandForFilePath
0x140004c79  mov     ebx, eax
0x140004c7b  test    eax, eax
0x140004c7d  jns     short loc_140004CFD
0x140004c7f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004c85  lea     rax, WPP_RECORDER_INITIALIZED
0x140004c8c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004c93  setnz   r8b
0x140004c97  and     dl, 40h
0x140004c9a  jnz     short loc_140004CA1
0x140004c9c  test    r8b, r8b
0x140004c9f  jz      short loc_140004CF3
0x140004ca1  mov     r9, cs:WPP_GLOBAL_Control
0x140004ca8  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140004caf  mov     [rsp+310h+var_2B8], rdi
0x140004cb4  mov     ecx, 20Eh
0x140004cb9  mov     dword ptr [rsp+310h+var_2C0], ebx
0x140004cbd  mov     dword ptr [rsp+310h+var_2C8], 16CDh
0x140004cc5  mov     r9, [r9+40h]
0x140004cc9  mov     qword ptr [rsp+310h+var_2D0], rax
0x140004cce  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140004cd5  mov     [rsp+310h+var_2D8], rax
0x140004cda  mov     word ptr [rsp+310h+var_2E0], 0BAh
0x140004ce1  mov     dword ptr [rsp+310h+var_2E8], 0Eh
0x140004ce9  mov     byte ptr [rsp+310h+Timeout], 2
0x140004cee  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140004cf3  mov     r13, [rsp+310h+var_298]
0x140004cf8  jmp     loc_140004F6C
0x140004cfd  mov     r13, [rsp+310h+var_298]
0x140004d02  lea     rax, [rbp+210h+var_280]
0x140004d06  mov     [rsp+310h+var_2E8], rax
0x140004d0b  xor     r9d, r9d
0x140004d0e  lea     rax, [rsp+310h+var_2A0]
0x140004d13  mov     r8, r13
0x140004d16  mov     rdx, r14
0x140004d19  mov     [rsp+310h+Timeout], rax
0x140004d1e  mov     rcx, r12
0x140004d21  call    PrjfSendCommand
0x140004d26  mov     ebx, eax
0x140004d28  test    eax, eax
0x140004d2a  jns     short loc_140004DA9
0x140004d2c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004d32  lea     rax, WPP_RECORDER_INITIALIZED
0x140004d39  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004d40  setnz   r8b
0x140004d44  and     dl, 40h
0x140004d47  jnz     short loc_140004D52
  ... truncated ...
```
