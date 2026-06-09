# PrjfCreateFileContext

- ea: `0x140001658`
- end: `0x140001b33`
- name: `PrjfCreateFileContext`
- size: `1243`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, char, __int128 *, __int16 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140021550`

## callees

- `0x140001658`
- `0x14000b1d0`
- `0x14000bb80`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x14003775c`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x1400018ae`
- `ntoskrnl!RtlCreateHashTable` at `0x1400018ae`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14000183c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14000186f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14000183c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14000186f`
- `ntoskrnl!KeInitializeEvent` at `0x140001828`
- `ntoskrnl!KeInitializeEvent` at `0x140001858`
- `ntoskrnl!KeInitializeEvent` at `0x14000188b`
- `ntoskrnl!KeInitializeEvent` at `0x140001ae5`
- `ntoskrnl!KeInitializeEvent` at `0x140001828`
- `ntoskrnl!KeInitializeEvent` at `0x140001858`
- `ntoskrnl!KeInitializeEvent` at `0x14000188b`
- `ntoskrnl!KeInitializeEvent` at `0x140001ae5`
- `ntoskrnl!ExInitializeResourceLite` at `0x140001802`
- `ntoskrnl!ExInitializeResourceLite` at `0x140001802`
- `FLTMGR!FltReferenceContext` at `0x1400017c4`
- `FLTMGR!FltReferenceContext` at `0x1400017c4`
- `FLTMGR!FltAllocateContext` at `0x14000173b`
- `FLTMGR!FltAllocateContext` at `0x14000173b`
- `FLTMGR!FltReleaseContext` at `0x140001b13`
- `FLTMGR!FltReleaseContext` at `0x140001b13`

## pseudocode

```c
__int64 __fastcall PrjfCreateFileContext(
        PFLT_CONTEXT Context,
        char a2,
        __int128 *a3,
        __int16 *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int128 *v7; // r15
  NTSTATUS UnicodeString; // edi
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  int v13; // r8d
  char *v14; // rcx
  int v15; // r8d
  __int64 v16; // rbx
  int v17; // eax
  __int128 v18; // xmm0
  __int16 v19; // cx
  __int16 v20; // cx
  PFLT_CONTEXT v21; // rax
  __int16 v23; // [rsp+30h] [rbp-48h]
  char v24; // [rsp+48h] [rbp-30h]
  char v25; // [rsp+50h] [rbp-28h]
  PFLT_CONTEXT Contexta; // [rsp+60h] [rbp-18h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+68h] [rbp-10h] BYREF

  Contexta = 0;
  HashTable = 0;
  v7 = a3;
  if ( a2 || a3 || a5 )
  {
    UnicodeString = FltAllocateContext(Globals, 4u, 0x170u, (POOL_TYPE)512, &Contexta);
    if ( UnicodeString < 0 )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 2;
      if ( (BYTE1(xmmword_14001A3D0) & 2) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v25 = UnicodeString;
      v24 = 77;
      v23 = 17;
      goto LABEL_12;
    }
    memset(Contexta, 0, 0x170u);
    FltReferenceContext(Context);
    *(_QWORD *)Contexta = Context;
    *((_QWORD *)Contexta + 11) = 0;
    *((_BYTE *)Contexta + 281) = a2;
    if ( a2 )
    {
LABEL_40:
      KeInitializeEvent((PRKEVENT)Contexta + 12, NotificationEvent, 1u);
      v21 = Contexta;
      v12 = a6;
      Contexta = 0;
      *a6 = v21;
      goto LABEL_41;
    }
    ExInitializeResourceLite((PERESOURCE)((char *)Contexta + 136));
    v14 = (char *)Contexta;
    *((_DWORD *)Contexta + 2) = 1;
    *((_QWORD *)v14 + 2) = 0;
    *((_DWORD *)v14 + 6) = 0;
    KeInitializeEvent((PRKEVENT)(v14 + 32), SynchronizationEvent, 0);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)Contexta + 10);
    KeInitializeEvent((PRKEVENT)Contexta + 13, NotificationEvent, 1u);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)Contexta + 42);
    KeInitializeEvent((PRKEVENT)((char *)Contexta + 344), NotificationEvent, 1u);
    HashTable = (PRTL_DYNAMIC_HASH_TABLE)((char *)Contexta + 240);
    if ( !RtlCreateHashTable(&HashTable, 0, 0) )
    {
      UnicodeString = -1073741670;
      LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 2;
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          521,
          v11,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          18,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          117);
      }
      goto LABEL_41;
    }
    if ( a5 && *a5 )
    {
      v16 = *a5 + 8LL;
      *((_QWORD *)Contexta + 14) = *a5 + 32LL;
      v17 = *(_DWORD *)(v16 + 4);
      if ( (v17 & 4) != 0 )
        *((_DWORD *)Contexta + 16) = 2;
      else
        *((_DWORD *)Contexta + 16) = ((v17 & 0x20) != 0) + 1;
      *((_QWORD *)Contexta + 9) = *a5;
      *a5 = 0;
    }
    else
    {
      v16 = 0;
      *((_DWORD *)Contexta + 16) = 3;
      *((_QWORD *)Contexta + 9) = 0;
      *((_QWORD *)Contexta + 14) = PRJFLT_VERSION_INFO_EMPTY;
    }
    if ( v7 )
    {
      v18 = *v7;
    }
    else
    {
      if ( !v16 )
        goto LABEL_30;
      v18 = *(_OWORD *)(v16 + 8);
    }
    *((_OWORD *)Contexta + 6) = v18;
LABEL_30:
    if ( a4 )
    {
      *((_QWORD *)Contexta + 16) = *((_QWORD *)a4 + 1);
      v19 = *a4;
      *((_WORD *)Contexta + 60) = *a4;
      *((_WORD *)Contexta + 61) = v19;
      *((_QWORD *)a4 + 1) = 0;
    }
    else if ( v16 )
    {
      v20 = *(_WORD *)(v16 + 280);
      if ( v20 )
      {
        *((_WORD *)Contexta + 61) = v20;
        UnicodeString = PrjfAllocateUnicodeString(1852197456, (char *)Contexta + 120);
        if ( UnicodeString < 0 )
        {
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 2;
          if ( (BYTE1(xmmword_14001A3D0) & 2) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_41;
          v25 = UnicodeString;
          v24 = -46;
          v23 = 19;
LABEL_12:
          WPP_RECORDER_AND_TRACE_SF_sDL(
            521,
            (_BYTE)v11,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            9,
            v23,
            (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
            v24,
            v25);
          goto LABEL_41;
        }
        *((_WORD *)Contexta + 60) = *(_WORD *)(v16 + 280);
        memmove(*((void **)Contexta + 16), (const void *)(v16 + 282), *(unsigned __int16 *)(v16 + 280));
      }
      else
      {
        *((_WORD *)Contexta + 60) = 0;
        *((_WORD *)Contexta + 61) = 0;
        *((_QWORD *)Contexta + 16) = 0;
      }
    }
    goto LABEL_40;
  }
  UnicodeString = -1073741790;
  if ( (xmmword_14001A3D0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (unsigned int)UnicodeString;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  WPP_RECORDER_AND_TRACE_SF_sDL(
    517,
    xmmword_14001A3D0 & 0x20,
    (_DWORD)a3,
    *((_QWORD *)WPP_GLOBAL_Control + 8),
    2,
    5,
    16,
    (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
    57,
    0);
LABEL_41:
  if ( Contexta )
  {
    if ( UnicodeString >= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11);
    FltReleaseContext(Contexta);
  }
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x140001658  push    rbp
0x14000165a  push    rbx
0x14000165b  push    rsi
0x14000165c  push    rdi
0x14000165d  push    r12
0x14000165f  push    r13
0x140001661  push    r14
0x140001663  push    r15
0x140001665  mov     rbp, rsp
0x140001668  sub     rsp, 78h
0x14000166c  mov     rsi, [rbp+arg_20]
0x140001670  xor     r13d, r13d
0x140001673  mov     [rbp+Context], r13
0x140001677  mov     r14, r9
0x14000167a  mov     [rbp+HashTable], r13
0x14000167e  mov     r15, r8
0x140001681  mov     bl, dl
0x140001683  mov     r12, rcx
0x140001686  test    dl, dl
0x140001688  jnz     loc_14000171A
0x14000168e  test    r8, r8
0x140001691  jnz     loc_14000171A
0x140001697  test    rsi, rsi
0x14000169a  jnz     short loc_14000171A
0x14000169c  mov     edi, 0C0000022h
0x1400016a1  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400016a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400016ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400016b5  setnz   r8b
0x1400016b9  and     dl, 20h
0x1400016bc  jnz     short loc_1400016C7
0x1400016be  test    r8b, r8b
0x1400016c1  jz      loc_140001B1F
0x1400016c7  mov     dword ptr [rsp+78h+var_28], r13d
0x1400016cc  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400016d3  mov     dword ptr [rsp+78h+var_30], 239h
0x1400016db  mov     ecx, 205h
0x1400016e0  mov     [rsp+78h+var_38], rax
0x1400016e5  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400016ec  mov     [rsp+78h+var_40], rax
0x1400016f1  mov     [rsp+78h+var_48], 10h
0x1400016f8  mov     [rsp+78h+var_50], 5
0x140001700  mov     r9, cs:WPP_GLOBAL_Control
0x140001707  mov     byte ptr [rsp+78h+ReturnedContext], 2
0x14000170c  mov     r9, [r9+40h]
0x140001710  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140001715  jmp     loc_140001B00
0x14000171a  mov     rcx, cs:Globals; Filter
0x140001721  lea     rax, [rbp+Context]
0x140001725  mov     edx, 4; ContextType
0x14000172a  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14000172f  mov     r9d, 200h; PoolType
0x140001735  mov     r8d, 170h; ContextSize
0x14000173b  call    cs:__imp_FltAllocateContext
0x140001742  nop     dword ptr [rax+rax+00h]
0x140001747  mov     edi, eax
0x140001749  test    eax, eax
0x14000174b  jns     short loc_1400017B0
0x14000174d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001753  lea     rax, WPP_RECORDER_INITIALIZED
0x14000175a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001761  setnz   r8b
0x140001765  and     dl, 2
0x140001768  jnz     short loc_140001773
0x14000176a  test    r8b, r8b
0x14000176d  jz      loc_140001B00
0x140001773  mov     dword ptr [rsp+78h+var_28], edi
0x140001777  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000177e  mov     dword ptr [rsp+78h+var_30], 24Dh
0x140001786  mov     [rsp+78h+var_38], rax
0x14000178b  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001792  mov     [rsp+78h+var_40], rax
0x140001797  mov     [rsp+78h+var_48], 11h
0x14000179e  mov     ecx, 209h
0x1400017a3  mov     [rsp+78h+var_50], 9
0x1400017ab  jmp     loc_140001700
0x1400017b0  mov     rcx, [rbp+Context]; void *
0x1400017b4  xor     edx, edx; Val
0x1400017b6  mov     r8d, 170h; Size
0x1400017bc  call    memset
0x1400017c1  mov     rcx, r12; Context
0x1400017c4  call    cs:__imp_FltReferenceContext
0x1400017cb  nop     dword ptr [rax+rax+00h]
0x1400017d0  mov     rax, [rbp+Context]
0x1400017d4  mov     [rax], r12
0x1400017d7  mov     r12d, 1
0x1400017dd  mov     rax, [rbp+Context]
0x1400017e1  mov     [rax+58h], r13
0x1400017e5  mov     rax, [rbp+Context]
0x1400017e9  mov     [rax+119h], bl
0x1400017ef  test    bl, bl
0x1400017f1  jnz     loc_140001AD5
0x1400017f7  mov     rcx, [rbp+Context]
0x1400017fb  add     rcx, 88h; Resource
0x140001802  call    cs:__imp_ExInitializeResourceLite
0x140001809  nop     dword ptr [rax+rax+00h]
0x14000180e  mov     rcx, [rbp+Context]
0x140001812  xor     r8d, r8d; State
0x140001815  mov     edx, r12d; Type
0x140001818  mov     [rcx+8], r12d
0x14000181c  mov     [rcx+10h], r13
0x140001820  mov     [rcx+18h], r13d
0x140001824  add     rcx, 20h ; ' '; Event
0x140001828  call    cs:__imp_KeInitializeEvent
0x14000182f  nop     dword ptr [rax+rax+00h]
0x140001834  mov     rcx, [rbp+Context]
0x140001838  add     rcx, 50h ; 'P'; RunRef
0x14000183c  call    cs:__imp_ExInitializeRundownProtection
0x140001843  nop     dword ptr [rax+rax+00h]
0x140001848  mov     rcx, [rbp+Context]
0x14000184c  mov     r8b, r12b; State
0x14000184f  add     rcx, 138h; Event
0x140001856  xor     edx, edx; Type
0x140001858  call    cs:__imp_KeInitializeEvent
0x14000185f  nop     dword ptr [rax+rax+00h]
0x140001864  mov     rcx, [rbp+Context]
0x140001868  add     rcx, 150h; RunRef
0x14000186f  call    cs:__imp_ExInitializeRundownProtection
0x140001876  nop     dword ptr [rax+rax+00h]
0x14000187b  mov     rcx, [rbp+Context]
0x14000187f  mov     r8b, r12b; State
0x140001882  add     rcx, 158h; Event
0x140001889  xor     edx, edx; Type
0x14000188b  call    cs:__imp_KeInitializeEvent
0x140001892  nop     dword ptr [rax+rax+00h]
0x140001897  mov     rax, [rbp+Context]
0x14000189b  lea     rcx, [rbp+HashTable]; HashTable
0x14000189f  add     rax, 0F0h
0x1400018a5  xor     r8d, r8d; Flags
0x1400018a8  xor     edx, edx; Shift
0x1400018aa  mov     [rbp+HashTable], rax
0x1400018ae  call    cs:__imp_RtlCreateHashTable
0x1400018b5  nop     dword ptr [rax+rax+00h]
0x1400018ba  test    al, al
0x1400018bc  jnz     short loc_140001937
0x1400018be  mov     edi, 0C000009Ah
0x1400018c3  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400018c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400018d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400018d7  setnz   r8b
0x1400018db  and     dl, 2
0x1400018de  jnz     short loc_1400018E9
0x1400018e0  test    r8b, r8b
0x1400018e3  jz      loc_140001B00
0x1400018e9  mov     r9, cs:WPP_GLOBAL_Control
0x1400018f0  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400018f7  mov     dword ptr [rsp+78h+var_30], 275h
0x1400018ff  mov     ecx, 209h
0x140001904  mov     [rsp+78h+var_38], rax
0x140001909  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001910  mov     [rsp+78h+var_40], rax
0x140001915  mov     r9, [r9+40h]
0x140001919  mov     [rsp+78h+var_48], 12h
0x140001920  mov     [rsp+78h+var_50], 9
0x140001928  mov     byte ptr [rsp+78h+ReturnedContext], 2
0x14000192d  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140001932  jmp     loc_140001B00
0x140001937  test    rsi, rsi
0x14000193a  jz      short loc_14000198A
0x14000193c  mov     rbx, [rsi]
0x14000193f  test    rbx, rbx
0x140001942  jz      short loc_14000198A
0x140001944  mov     rax, [rbp+Context]
0x140001948  add     rbx, 8
0x14000194c  lea     rcx, [rbx+18h]
0x140001950  mov     [rax+70h], rcx
0x140001954  mov     eax, [rbx+4]
0x140001957  test    al, 4
0x140001959  jz      short loc_140001968
0x14000195b  mov     rax, [rbp+Context]
0x14000195f  mov     dword ptr [rax+40h], 2
0x140001966  jmp     short loc_14000197A
0x140001968  and     al, 20h
0x14000196a  neg     al
0x14000196c  mov     rax, [rbp+Context]
0x140001970  sbb     ecx, ecx
0x140001972  neg     ecx
0x140001974  add     ecx, r12d
0x140001977  mov     [rax+40h], ecx
0x14000197a  mov     rcx, [rsi]
0x14000197d  mov     rax, [rbp+Context]
0x140001981  mov     [rax+48h], rcx
0x140001985  mov     [rsi], r13
0x140001988  jmp     short loc_1400019AF
0x14000198a  mov     rax, [rbp+Context]
0x14000198e  lea     rcx, PRJFLT_VERSION_INFO_EMPTY
0x140001995  mov     rbx, r13
0x140001998  mov     dword ptr [rax+40h], 3
0x14000199f  mov     rax, [rbp+Context]
0x1400019a3  mov     [rax+48h], r13
0x1400019a7  mov     rax, [rbp+Context]
0x1400019ab  mov     [rax+70h], rcx
0x1400019af  test    r15, r15
0x1400019b2  jz      short loc_1400019BA
0x1400019b4  movups  xmm0, xmmword ptr [r15]
0x1400019b8  jmp     short loc_1400019C3
0x1400019ba  test    rbx, rbx
0x1400019bd  jz      short loc_1400019CC
0x1400019bf  movups  xmm0, xmmword ptr [rbx+8]
0x1400019c3  mov     rax, [rbp+Context]
0x1400019c7  movdqu  xmmword ptr [rax+60h], xmm0
0x1400019cc  test    r14, r14
0x1400019cf  jz      short loc_1400019FD
0x1400019d1  mov     rcx, [r14+8]
0x1400019d5  mov     rax, [rbp+Context]
0x1400019d9  mov     [rax+80h], rcx
0x1400019e0  mov     rax, [rbp+Context]
0x1400019e4  movzx   ecx, word ptr [r14]
0x1400019e8  mov     [rax+78h], cx
0x1400019ec  mov     rax, [rbp+Context]
0x1400019f0  mov     [rax+7Ah], cx
0x1400019f4  mov     [r14+8], r13
0x1400019f8  jmp     loc_140001AD5
0x1400019fd  test    rbx, rbx
0x140001a00  jz      loc_140001AD5
0x140001a06  movzx   ecx, word ptr [rbx+118h]
0x140001a0d  mov     rax, [rbp+Context]
0x140001a11  test    cx, cx
0x140001a14  jz      loc_140001ABC
0x140001a1a  mov     [rax+7Ah], cx
0x140001a1e  mov     ecx, 6E664A50h
0x140001a23  mov     rdx, [rbp+Context]
0x140001a27  add     rdx, 78h ; 'x'
0x140001a2b  call    PrjfAllocateUnicodeString
0x140001a30  mov     edi, eax
0x140001a32  test    eax, eax
0x140001a34  jns     short loc_140001A8C
0x140001a36  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001a3c  lea     rax, WPP_RECORDER_INITIALIZED
0x140001a43  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001a4a  setnz   r8b
0x140001a4e  and     dl, 2
0x140001a51  jnz     short loc_140001A5C
0x140001a53  test    r8b, r8b
0x140001a56  jz      loc_140001B00
0x140001a5c  mov     dword ptr [rsp+78h+var_28], edi
0x140001a60  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140001a67  mov     dword ptr [rsp+78h+var_30], 2D2h
0x140001a6f  mov     [rsp+78h+var_38], rax
0x140001a74  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001a7b  mov     [rsp+78h+var_40], rax
0x140001a80  mov     [rsp+78h+var_48], 13h
0x140001a87  jmp     loc_14000179E
0x140001a8c  movzx   ecx, word ptr [rbx+118h]
0x140001a93  lea     rdx, [rbx+11Ah]; Src
0x140001a9a  mov     rax, [rbp+Context]
0x140001a9e  mov     [rax+78h], cx
0x140001aa2  mov     rcx, [rbp+Context]
0x140001aa6  movzx   r8d, word ptr [rbx+118h]; Size
0x140001aae  mov     rcx, [rcx+80h]; void *
0x140001ab5  call    memmove
0x140001aba  jmp     short loc_140001AD5
0x140001abc  mov     [rax+78h], r13w
0x140001ac1  mov     rax, [rbp+Context]
0x140001ac5  mov     [rax+7Ah], r13w
0x140001aca  mov     rax, [rbp+Context]
0x140001ace  mov     [rax+80h], r13
0x140001ad5  mov     rcx, [rbp+Context]
0x140001ad9  mov     r8b, r12b; State
0x140001adc  add     rcx, 120h; Event
0x140001ae3  xor     edx, edx; Type
0x140001ae5  call    cs:__imp_KeInitializeEvent
0x140001aec  nop     dword ptr [rax+rax+00h]
0x140001af1  mov     rax, [rbp+Context]
0x140001af5  mov     rcx, [rbp+arg_28]
0x140001af9  mov     [rbp+Context], r13
0x140001afd  mov     [rcx], rax
0x140001b00  cmp     [rbp+Context], r13
0x140001b04  jz      short loc_140001B1F
0x140001b06  test    edi, edi
0x140001b08  js      short loc_140001B0F
0x140001b0a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001b0f  mov     rcx, [rbp+Context]; Context
0x140001b13  call    cs:__imp_FltReleaseContext
0x140001b1a  nop     dword ptr [rax+rax+00h]
0x140001b1f  mov     eax, edi
0x140001b21  add     rsp, 78h
0x140001b25  pop     r15
0x140001b27  pop     r14
0x140001b29  pop     r13
0x140001b2b  pop     r12
0x140001b2d  pop     rdi
0x140001b2e  pop     rsi
0x140001b2f  pop     rbx
0x140001b30  pop     rbp
0x140001b31  retn
```
