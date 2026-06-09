# PrjfFindOrCreateTransactionContext

- ea: `0x140021368`
- end: `0x140021548`
- name: `PrjfFindOrCreateTransactionContext`
- size: `480`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PKTRANSACTION Transaction, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400237d0`

## callees

- `0x14000d128`
- `0x140021368`

## import_xrefs

- `FLTMGR!FltSetTransactionContext` at `0x140021480`
- `FLTMGR!FltSetTransactionContext` at `0x140021480`
- `FLTMGR!FltGetTransactionContext` at `0x14002139a`
- `FLTMGR!FltGetTransactionContext` at `0x14002139a`
- `FLTMGR!FltAllocateContext` at `0x1400213dd`
- `FLTMGR!FltAllocateContext` at `0x1400213dd`
- `FLTMGR!FltReleaseContext` at `0x140021496`
- `FLTMGR!FltReleaseContext` at `0x140021524`
- `FLTMGR!FltReleaseContext` at `0x140021496`
- `FLTMGR!FltReleaseContext` at `0x140021524`

## pseudocode

```c
__int64 __fastcall PrjfFindOrCreateTransactionContext(
        PFLT_INSTANCE Instance,
        PKTRANSACTION Transaction,
        PFLT_CONTEXT *a3)
{
  NTSTATUS TransactionContext; // ebx
  int v7; // edx
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  PFLT_CONTEXT v11; // rax
  PFLT_CONTEXT Context[2]; // [rsp+60h] [rbp-10h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+A8h] [rbp+38h] BYREF

  Context[0] = 0;
  NewContext = 0;
  TransactionContext = FltGetTransactionContext(Instance, Transaction, Context);
  if ( TransactionContext >= 0 )
  {
    *a3 = Context[0];
    Context[0] = 0;
    goto LABEL_16;
  }
  TransactionContext = FltAllocateContext(Globals, 0x20u, 4u, PagedPool, &NewContext);
  if ( TransactionContext < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        57,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        56,
        TransactionContext);
    }
    goto LABEL_16;
  }
  TransactionContext = FltSetTransactionContext(
                         Instance,
                         Transaction,
                         FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                         NewContext,
                         Context);
  if ( TransactionContext >= 0 )
  {
    v11 = NewContext;
    goto LABEL_15;
  }
  FltReleaseContext(NewContext);
  NewContext = 0;
  if ( TransactionContext == -1071906814 )
  {
    v11 = Context[0];
    TransactionContext = 0;
LABEL_15:
    *a3 = v11;
    NewContext = 0;
    goto LABEL_16;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 2) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (unsigned int)TransactionContext;
  LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 2;
  LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  WPP_RECORDER_AND_TRACE_SF_sDL(
    521,
    v9,
    v10,
    *((_QWORD *)WPP_GLOBAL_Control + 8),
    2,
    9,
    58,
    (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
    73,
    TransactionContext);
LABEL_16:
  if ( NewContext )
    FltReleaseContext(NewContext);
  return (unsigned int)TransactionContext;
}

```

## disassembly

```asm
0x140021368  mov     [rsp-18h+arg_0], rbx
0x14002136d  mov     [rsp-18h+arg_8], rsi
0x140021372  push    rbp
0x140021373  push    rdi
0x140021374  push    r14
0x140021376  mov     rbp, rsp
0x140021379  sub     rsp, 70h
0x14002137d  mov     rdi, r8
0x140021380  mov     [rbp+Context], 0
0x140021388  lea     r8, [rbp+Context]; Context
0x14002138c  mov     [rbp+NewContext], 0
0x140021394  mov     rsi, rdx
0x140021397  mov     r14, rcx
0x14002139a  call    cs:__imp_FltGetTransactionContext
0x1400213a1  nop     dword ptr [rax+rax+00h]
0x1400213a6  mov     ebx, eax
0x1400213a8  test    eax, eax
0x1400213aa  js      short loc_1400213C0
0x1400213ac  mov     rcx, [rbp+Context]
0x1400213b0  mov     [rdi], rcx
0x1400213b3  mov     [rbp+Context], 0
0x1400213bb  jmp     loc_14002151B
0x1400213c0  mov     rcx, cs:Globals; Filter
0x1400213c7  lea     rax, [rbp+NewContext]
0x1400213cb  mov     edx, 20h ; ' '; ContextType
0x1400213d0  mov     [rsp+70h+ReturnedContext], rax; ReturnedContext
0x1400213d5  lea     r9d, [rdx-1Fh]; PoolType
0x1400213d9  lea     r8d, [rdx-1Ch]; ContextSize
0x1400213dd  call    cs:__imp_FltAllocateContext
0x1400213e4  nop     dword ptr [rax+rax+00h]
0x1400213e9  mov     ebx, eax
0x1400213eb  test    eax, eax
0x1400213ed  jns     short loc_140021467
0x1400213ef  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400213f5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400213fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021403  setnz   r8b
0x140021407  and     dl, 2
0x14002140a  jnz     short loc_140021415
0x14002140c  test    r8b, r8b
0x14002140f  jz      loc_14002151B
0x140021415  mov     [rsp+70h+var_20], ebx
0x140021419  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021420  mov     [rsp+70h+var_28], 0C38h
0x140021428  mov     [rsp+70h+var_30], rax
0x14002142d  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021434  mov     [rsp+70h+var_38], rax
0x140021439  mov     [rsp+70h+var_40], 39h ; '9'
0x140021440  mov     r9, cs:WPP_GLOBAL_Control
0x140021447  mov     ecx, 209h
0x14002144c  mov     [rsp+70h+var_48], 9
0x140021454  mov     byte ptr [rsp+70h+ReturnedContext], 2
0x140021459  mov     r9, [r9+40h]
0x14002145d  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021462  jmp     loc_14002151B
0x140021467  mov     r9, [rbp+NewContext]; NewContext
0x14002146b  lea     rax, [rbp+Context]
0x14002146f  mov     r8d, 1; Operation
0x140021475  mov     [rsp+70h+ReturnedContext], rax; OldContext
0x14002147a  mov     rdx, rsi; Transaction
0x14002147d  mov     rcx, r14; Instance
0x140021480  call    cs:__imp_FltSetTransactionContext
0x140021487  nop     dword ptr [rax+rax+00h]
0x14002148c  mov     ebx, eax
0x14002148e  test    eax, eax
0x140021490  jns     short loc_14002150C
0x140021492  mov     rcx, [rbp+NewContext]; Context
0x140021496  call    cs:__imp_FltReleaseContext
0x14002149d  nop     dword ptr [rax+rax+00h]
0x1400214a2  mov     [rbp+NewContext], 0
0x1400214aa  cmp     ebx, 0C01C0002h
0x1400214b0  jz      short loc_140021504
0x1400214b2  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400214b8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400214bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400214c6  setnz   r8b
0x1400214ca  and     dl, 2
0x1400214cd  jnz     short loc_1400214D4
0x1400214cf  test    r8b, r8b
0x1400214d2  jz      short loc_140021530
0x1400214d4  mov     [rsp+70h+var_20], ebx
0x1400214d8  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400214df  mov     [rsp+70h+var_28], 0C49h
0x1400214e7  mov     [rsp+70h+var_30], rax
0x1400214ec  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400214f3  mov     [rsp+70h+var_38], rax
0x1400214f8  mov     [rsp+70h+var_40], 3Ah ; ':'
0x1400214ff  jmp     loc_140021440
0x140021504  mov     rax, [rbp+Context]
0x140021508  xor     ebx, ebx
0x14002150a  jmp     short loc_140021510
0x14002150c  mov     rax, [rbp+NewContext]
0x140021510  mov     [rdi], rax
0x140021513  mov     [rbp+NewContext], 0
0x14002151b  mov     rcx, [rbp+NewContext]; Context
0x14002151f  test    rcx, rcx
0x140021522  jz      short loc_140021530
0x140021524  call    cs:__imp_FltReleaseContext
0x14002152b  nop     dword ptr [rax+rax+00h]
0x140021530  lea     r11, [rsp+70h+var_s0]
0x140021535  mov     eax, ebx
0x140021537  mov     rbx, [r11+20h]
0x14002153b  mov     rsi, [r11+28h]
0x14002153f  mov     rsp, r11
0x140021542  pop     r14
0x140021544  pop     rdi
0x140021545  pop     rbp
0x140021546  retn
```
