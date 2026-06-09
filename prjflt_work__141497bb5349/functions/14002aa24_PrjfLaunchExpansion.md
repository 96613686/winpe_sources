# PrjfLaunchExpansion

- ea: `0x14002aa24`
- end: `0x14002aec3`
- name: `PrjfLaunchExpansion`
- size: `1183`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, __int64 FileObject, __int64 Context, int, PFLT_CALLBACK_DATA CallbackData, int, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140029088`
- `0x140029214`

## callees

- `0x140003480`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000d754`
- `0x14001141c`
- `0x140021c5c`
- `0x140028d9c`
- `0x14002aa24`
- `0x14002b4ec`
- `0x140037250`
- `0x14003b600`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ac42`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ac42`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002adad`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002adad`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002ad86`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002ad86`
- `FLTMGR!FltCbdqInsertIo` at `0x14002ad3c`
- `FLTMGR!FltCbdqInsertIo` at `0x14002ad3c`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14002ac86`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14002ac86`
- `FLTMGR!FltGetStreamContext` at `0x14002abd9`
- `FLTMGR!FltGetStreamContext` at `0x14002abd9`
- `FLTMGR!FltReleaseContext` at `0x14002ae8b`
- `FLTMGR!FltReleaseContext` at `0x14002aea0`
- `FLTMGR!FltReleaseContext` at `0x14002ae8b`
- `FLTMGR!FltReleaseContext` at `0x14002aea0`

## pseudocode

```c
__int64 __fastcall PrjfLaunchExpansion(
        PFLT_INSTANCE Instance,
        __int64 FileObject,
        __int64 Context,
        int a4,
        PFLT_CALLBACK_DATA CallbackData,
        int a6,
        unsigned int a7)
{
  struct _FILE_OBJECT *v9; // r13
  int v11; // esi
  __int128 v12; // xmm0
  int v13; // r8d
  PVOID v14; // rbx
  int ExpansionContext; // ebx
  unsigned int v16; // r12d
  char v17; // r15
  __int64 v18; // r14
  __int64 v19; // rcx
  char IsZeroAllocatedRange; // al
  __int64 v21; // rcx
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  int v27; // [rsp+20h] [rbp-91h]
  int v28; // [rsp+28h] [rbp-89h]
  int v29; // [rsp+30h] [rbp-81h]
  int v30; // [rsp+38h] [rbp-79h]
  int v31; // [rsp+40h] [rbp-71h]
  int v32; // [rsp+48h] [rbp-69h]
  PFLT_CONTEXT Contexta; // [rsp+70h] [rbp-41h] BYREF
  PVOID Entry[2]; // [rsp+78h] [rbp-39h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-21h] BYREF
  PFLT_CONTEXT v36[10]; // [rsp+A0h] [rbp-11h] BYREF

  v9 = (struct _FILE_OBJECT *)FileObject;
  P[0] = 0;
  v11 = 0;
  Contexta = 0;
  v36[0] = 0;
  if ( !*(_QWORD *)(Context + 88) )
  {
    v12 = *(_OWORD *)(Context + 96);
    Entry[0] = 0;
    *(_OWORD *)P = v12;
    P[0] = PrjfGetUnionContext(Instance, P);
    v14 = P[0];
    if ( !P[0] )
    {
      ExpansionContext = -1073689084;
      if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(FileObject) = BYTE1(xmmword_14001A3D0) & 4;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          FileObject,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          28,
          (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          28,
          4,
          (__int64)&v9->FileName);
      }
      goto LABEL_6;
    }
    IsZeroAllocatedRange = PrjfIsZeroAllocatedRange(Instance, v9);
    ExpansionContext = PrjfCreateExpansionContext(Instance, (__int64)v14, Context, a4, IsZeroAllocatedRange, Entry);
    if ( ExpansionContext < 0
      || (ExpansionContext = FltGetStreamContext(Instance, v9, &Contexta), ExpansionContext < 0)
      || (ExpansionContext = PrjfGetSetStreamHandleContext(Instance, v9, (PFLT_CONTEXT)Context, Contexta, 0, v36),
          ExpansionContext < 0) )
    {
LABEL_6:
      v16 = a7;
LABEL_7:
      v17 = 0;
      goto LABEL_8;
    }
    v22 = Entry[0];
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(Context + 88), (signed __int64)Entry[0], 0) )
    {
      if ( (_QWORD *)v22[25] != v22 + 25 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, FileObject);
      ExFreeToNPagedLookasideList(&stru_14001AB40, v22);
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Context + 88) + 68LL));
  v23 = a7;
  *(_DWORD *)(*(_QWORD *)(Context + 88) + 300LL) = a7;
  v24 = *(_QWORD *)(Context + 88);
  if ( *(_DWORD *)(v24 + 4) < a4 )
  {
    *(_DWORD *)(v24 + 4) = a4;
    ExpansionContext = FltCancellableWaitForSingleObject((PVOID)(*(_QWORD *)(Context + 88) + 16LL), 0, CallbackData);
    if ( ExpansionContext < 0 )
    {
      if ( (BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(FileObject) = BYTE9(xmmword_14001A3D0) & 4;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          778,
          FileObject,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          10,
          29,
          (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          148,
          ExpansionContext,
          (__int64)&v9->FileName);
      }
      goto LABEL_6;
    }
  }
  v16 = a7;
  if ( a7 == 19 )
    **(_DWORD **)(Context + 88) |= 2u;
  if ( CallbackData )
  {
    if ( (CallbackData->Flags & 1) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, FileObject);
    ExpansionContext = FltCbdqInsertIo(
                         (PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(Context + 88) + 72LL),
                         CallbackData,
                         0,
                         v9);
    v25 = *(_QWORD *)(Context + 88);
    if ( ExpansionContext >= 0 )
    {
      v17 = 1;
      v11 = _InterlockedIncrement((volatile signed __int32 *)(v25 + 280));
      goto LABEL_8;
    }
LABEL_31:
    _InterlockedDecrement((volatile signed __int32 *)(v25 + 68));
    goto LABEL_7;
  }
  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(Context + 88) + 216LL));
  ExpansionContext = PrjfScheduleExpansionWorkItem(Instance, v9);
  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(Context + 88) + 216LL));
  v25 = *(_QWORD *)(Context + 88);
  if ( ExpansionContext < 0 )
    goto LABEL_31;
  v17 = 0;
  v11 = _InterlockedIncrement((volatile signed __int32 *)(v25 + 280));
LABEL_8:
  v18 = *(_QWORD *)(Context + 88);
  *(_OWORD *)Entry = 0;
  if ( ExpansionContext < 0 )
  {
    LOBYTE(FileObject) = BYTE1(xmmword_14001A3D0) & 4;
    if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        522,
        FileObject,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        12,
        (__int64)WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\telemetry.c",
        16,
        ExpansionContext,
        (__int64)&v9->FileName);
    }
  }
  else
  {
    v19 = *(_QWORD *)(*(_QWORD *)(v18 + 272) + 72LL);
    WORD1(Entry[0]) = *(_WORD *)(v19 + 288);
    LOWORD(Entry[0]) = WORD1(Entry[0]);
    Entry[1] = (PVOID)(v19 + 290);
    LOBYTE(FileObject) = BYTE1(xmmword_14001A3E0) & 4;
    if ( (BYTE1(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDZLL(
        v19,
        FileObject,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        (__int64)Entry,
        a6,
        v16);
    }
  }
  if ( a6 == 2 && v11 <= 1 )
    PrjfTelemetryPostDirectoryExpansionTrigger(v16, v18, v11, ExpansionContext, v17);
  if ( P[0] )
    PrjfReleaseUnionContext((char *)P[0], FileObject);
  if ( Contexta )
    FltReleaseContext(Contexta);
  if ( v36[0] )
    FltReleaseContext(v36[0]);
  return (unsigned int)ExpansionContext;
}

```

## disassembly

```asm
0x14002aa24  push    rbp
0x14002aa26  push    rbx
0x14002aa27  push    rsi
0x14002aa28  push    rdi
0x14002aa29  push    r12
0x14002aa2b  push    r13
0x14002aa2d  push    r14
0x14002aa2f  push    r15
0x14002aa31  lea     rbp, [rsp-7]
0x14002aa36  sub     rsp, 0B8h
0x14002aa3d  xor     r14d, r14d
0x14002aa40  mov     r12d, r9d
0x14002aa43  mov     rdi, r8
0x14002aa46  mov     r13, rdx
0x14002aa49  mov     r15, rcx
0x14002aa4c  mov     [rbp+3Fh+P], r14
0x14002aa50  mov     esi, r14d
0x14002aa53  mov     [rbp+3Fh+Context], r14
0x14002aa57  mov     [rbp+3Fh+var_50], r14
0x14002aa5b  mov     [rbp+3Fh+arg_10], r14b
0x14002aa5f  cmp     [r8+58h], r14
0x14002aa63  jnz     loc_14002AC4E
0x14002aa69  movups  xmm0, xmmword ptr [r8+60h]
0x14002aa6e  lea     rdx, [rbp+3Fh+P]
0x14002aa72  mov     [rbp+3Fh+Entry], r14
0x14002aa76  movdqu  xmmword ptr [rbp+3Fh+P], xmm0
0x14002aa7b  call    PrjfGetUnionContext
0x14002aa80  mov     [rbp+3Fh+P], rax
0x14002aa84  mov     rbx, rax
0x14002aa87  test    rax, rax
0x14002aa8a  jnz     loc_14002AB9C
0x14002aa90  mov     ebx, 0C000CE04h
0x14002aa95  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002aa9b  lea     r9, WPP_RECORDER_INITIALIZED
0x14002aaa2  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14002aaa9  setnz   r8b
0x14002aaad  and     dl, 4
0x14002aab0  jnz     short loc_14002AAB7
0x14002aab2  test    r8b, r8b
0x14002aab5  jz      short loc_14002AB14
0x14002aab7  lea     rax, [r13+58h]
0x14002aabb  mov     ecx, 20Ah
0x14002aac0  mov     [rsp+0F0h+var_98], rax
0x14002aac5  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002aacc  mov     dword ptr [rsp+0F0h+var_A0], ebx
0x14002aad0  mov     [rsp+0F0h+var_A8], 71Ch
0x14002aad8  mov     [rsp+0F0h+var_B0], rax
0x14002aadd  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002aae4  mov     [rsp+0F0h+var_B8], rax
0x14002aae9  mov     [rsp+0F0h+var_C0], 1Ch
0x14002aaf0  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14002aaf8  mov     [rsp+0F0h+var_D0], 2
0x14002aafd  mov     r9, cs:WPP_GLOBAL_Control
0x14002ab04  mov     r9, [r9+40h]
0x14002ab08  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002ab0d  lea     r9, WPP_RECORDER_INITIALIZED
0x14002ab14  mov     r12d, [rbp+3Fh+arg_30]
0x14002ab18  mov     r15b, sil
0x14002ab1b  mov     r14, [rdi+58h]
0x14002ab1f  xorps   xmm0, xmm0
0x14002ab22  mov     edi, [rbp+3Fh+arg_28]
0x14002ab25  movups  xmmword ptr [rbp+3Fh+Entry], xmm0
0x14002ab29  test    ebx, ebx
0x14002ab2b  js      loc_14002ADE0
0x14002ab31  mov     rax, [r14+110h]
0x14002ab38  mov     rcx, [rax+48h]
0x14002ab3c  movzx   eax, word ptr [rcx+120h]
0x14002ab43  mov     word ptr [rbp+3Fh+Entry+2], ax
0x14002ab47  mov     word ptr [rbp+3Fh+Entry], ax
0x14002ab4b  lea     rax, [rcx+122h]
0x14002ab52  mov     [rbp+3Fh+Entry+8], rax
0x14002ab56  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14002ab5d  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14002ab63  setnz   r8b
0x14002ab67  and     dl, 4
0x14002ab6a  jnz     short loc_14002AB75
0x14002ab6c  test    r8b, r8b
0x14002ab6f  jz      loc_14002AE51
0x14002ab75  mov     r9, cs:WPP_GLOBAL_Control
0x14002ab7c  lea     rax, [rbp+3Fh+Entry]
0x14002ab80  mov     [rsp+0F0h+var_90], r12d
0x14002ab85  mov     dword ptr [rsp+0F0h+var_98], edi
0x14002ab89  mov     [rsp+0F0h+var_A0], rax
0x14002ab8e  mov     r9, [r9+40h]
0x14002ab92  call    WPP_RECORDER_AND_TRACE_SF_sDZLL
0x14002ab97  jmp     loc_14002AE51
0x14002ab9c  mov     rdx, r13
0x14002ab9f  mov     rcx, r15
0x14002aba2  call    PrjfIsZeroAllocatedRange
0x14002aba7  lea     rcx, [rbp+3Fh+Entry]
0x14002abab  mov     r9d, r12d
0x14002abae  mov     [rsp+0F0h+var_C8], rcx; __int64
0x14002abb3  mov     r8, rdi
0x14002abb6  mov     rcx, r15; Instance
0x14002abb9  mov     [rsp+0F0h+var_D0], al; char
0x14002abbd  mov     rdx, rbx
0x14002abc0  call    PrjfCreateExpansionContext
0x14002abc5  mov     ebx, eax
0x14002abc7  test    eax, eax
0x14002abc9  js      loc_14002AB0D
0x14002abcf  lea     r8, [rbp+3Fh+Context]; Context
0x14002abd3  mov     rdx, r13; FileObject
0x14002abd6  mov     rcx, r15; Instance
0x14002abd9  call    cs:__imp_FltGetStreamContext
0x14002abe0  nop     dword ptr [rax+rax+00h]
0x14002abe5  mov     ebx, eax
0x14002abe7  test    eax, eax
0x14002abe9  js      loc_14002AB0D
0x14002abef  mov     r9, [rbp+3Fh+Context]
0x14002abf3  lea     rax, [rbp+3Fh+var_50]
0x14002abf7  mov     [rsp+0F0h+var_C8], rax; __int64
0x14002abfc  mov     r8, rdi; Context
0x14002abff  mov     rdx, r13; FileObject
0x14002ac02  mov     [rsp+0F0h+var_D0], r14b; char
0x14002ac07  mov     rcx, r15; Instance
0x14002ac0a  call    PrjfGetSetStreamHandleContext
0x14002ac0f  mov     ebx, eax
0x14002ac11  test    eax, eax
0x14002ac13  js      loc_14002AB0D
0x14002ac19  mov     rbx, [rbp+3Fh+Entry]
0x14002ac1d  xor     eax, eax
0x14002ac1f  lock cmpxchg [rdi+58h], rbx
0x14002ac25  jz      short loc_14002AC4E
0x14002ac27  lea     rax, [rbx+0C8h]
0x14002ac2e  cmp     [rax], rax
0x14002ac31  jz      short loc_14002AC38
0x14002ac33  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ac38  mov     rdx, rbx; Entry
0x14002ac3b  lea     rcx, stru_14001AB40; Lookaside
0x14002ac42  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002ac49  nop     dword ptr [rax+rax+00h]
0x14002ac4e  mov     rax, [rdi+58h]
0x14002ac52  lock inc dword ptr [rax+44h]
0x14002ac56  mov     rax, [rdi+58h]
0x14002ac5a  mov     ecx, [rbp+3Fh+arg_30]
0x14002ac5d  mov     r14, [rbp+3Fh+CallbackData]
0x14002ac61  mov     [rax+12Ch], ecx
0x14002ac67  mov     rax, [rdi+58h]
0x14002ac6b  cmp     [rax+4], r12d
0x14002ac6f  jge     loc_14002AD09
0x14002ac75  mov     [rax+4], r12d
0x14002ac79  mov     r8, r14; CallbackData
0x14002ac7c  mov     rcx, [rdi+58h]
0x14002ac80  xor     edx, edx; Timeout
0x14002ac82  add     rcx, 10h; Object
0x14002ac86  call    cs:__imp_FltCancellableWaitForSingleObject
0x14002ac8d  nop     dword ptr [rax+rax+00h]
0x14002ac92  mov     ebx, eax
0x14002ac94  test    eax, eax
0x14002ac96  jns     short loc_14002AD09
0x14002ac98  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x14002ac9e  lea     r9, WPP_RECORDER_INITIALIZED
0x14002aca5  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14002acac  setnz   r8b
0x14002acb0  and     dl, 4
0x14002acb3  jnz     short loc_14002ACBE
0x14002acb5  test    r8b, r8b
0x14002acb8  jz      loc_14002AB14
0x14002acbe  lea     rax, [r13+58h]
0x14002acc2  mov     ecx, 30Ah
0x14002acc7  mov     [rsp+0F0h+var_98], rax
0x14002accc  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002acd3  mov     dword ptr [rsp+0F0h+var_A0], ebx
0x14002acd7  mov     [rsp+0F0h+var_A8], 794h
0x14002acdf  mov     [rsp+0F0h+var_B0], rax
0x14002ace4  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002aceb  mov     [rsp+0F0h+var_B8], rax
0x14002acf0  mov     [rsp+0F0h+var_C0], 1Dh
0x14002acf7  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14002acff  mov     [rsp+0F0h+var_D0], 3
0x14002ad04  jmp     loc_14002AAFD
0x14002ad09  mov     r12d, [rbp+3Fh+arg_30]
0x14002ad0d  cmp     r12d, 13h
0x14002ad11  jnz     short loc_14002AD1A
0x14002ad13  mov     rax, [rdi+58h]
0x14002ad17  or      dword ptr [rax], 2
0x14002ad1a  test    r14, r14
0x14002ad1d  jz      short loc_14002AD79
0x14002ad1f  mov     eax, [r14]
0x14002ad22  test    al, 1
0x14002ad24  jnz     short loc_14002AD2B
0x14002ad26  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002ad2b  mov     rcx, [rdi+58h]
0x14002ad2f  mov     r9, r13; InsertContext
0x14002ad32  add     rcx, 48h ; 'H'; Cbdq
0x14002ad36  xor     r8d, r8d; Context
0x14002ad39  mov     rdx, r14; Cbd
0x14002ad3c  call    cs:__imp_FltCbdqInsertIo
0x14002ad43  nop     dword ptr [rax+rax+00h]
0x14002ad48  mov     ebx, eax
0x14002ad4a  lea     r9, WPP_RECORDER_INITIALIZED
0x14002ad51  mov     rax, [rdi+58h]
0x14002ad55  test    ebx, ebx
0x14002ad57  js      short loc_14002AD70
0x14002ad59  mov     r15b, 1
0x14002ad5c  mov     esi, 1
0x14002ad61  lock xadd [rax+118h], esi
0x14002ad69  inc     esi
0x14002ad6b  jmp     loc_14002AB1B
0x14002ad70  lock dec dword ptr [rax+44h]
0x14002ad74  jmp     loc_14002AB18
0x14002ad79  mov     rcx, [rdi+58h]
0x14002ad7d  mov     r14d, 0D8h
0x14002ad83  add     rcx, r14; FastMutex
0x14002ad86  call    cs:__imp_ExAcquireFastMutex
0x14002ad8d  nop     dword ptr [rax+rax+00h]
0x14002ad92  mov     r8, [rdi+58h]
0x14002ad96  xor     r9d, r9d
0x14002ad99  mov     rdx, r13; Object
0x14002ad9c  mov     rcx, r15; FltObject
0x14002ad9f  call    PrjfScheduleExpansionWorkItem
0x14002ada4  mov     rcx, [rdi+58h]
0x14002ada8  mov     ebx, eax
0x14002adaa  add     rcx, r14; FastMutex
0x14002adad  call    cs:__imp_ExReleaseFastMutex
0x14002adb4  nop     dword ptr [rax+rax+00h]
0x14002adb9  mov     rax, [rdi+58h]
0x14002adbd  lea     r9, WPP_RECORDER_INITIALIZED
0x14002adc4  test    ebx, ebx
0x14002adc6  js      short loc_14002AD70
0x14002adc8  mov     esi, 1
0x14002adcd  lock xadd [rax+118h], esi
0x14002add5  mov     r15b, [rbp+3Fh+arg_10]
0x14002add9  inc     esi
0x14002addb  jmp     loc_14002AB1B
0x14002ade0  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14002ade7  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002aded  setnz   r8b
0x14002adf1  and     dl, 4
0x14002adf4  jnz     short loc_14002ADFB
0x14002adf6  test    r8b, r8b
0x14002adf9  jz      short loc_14002AE51
0x14002adfb  mov     r9, cs:WPP_GLOBAL_Control
0x14002ae02  lea     rax, [r13+58h]
0x14002ae06  mov     [rsp+0F0h+var_98], rax
0x14002ae0b  mov     ecx, 20Ah
0x14002ae10  mov     dword ptr [rsp+0F0h+var_A0], ebx
0x14002ae14  lea     rax, aOnecoreBaseFsG_4; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002ae1b  mov     [rsp+0F0h+var_A8], 110h
0x14002ae23  mov     r9, [r9+40h]
0x14002ae27  mov     [rsp+0F0h+var_B0], rax
0x14002ae2c  lea     rax, WPP_cead7f9b79fe32a96920046e878d7ba9_Traceguids
0x14002ae33  mov     [rsp+0F0h+var_B8], rax
0x14002ae38  mov     [rsp+0F0h+var_C0], 0Ch
0x14002ae3f  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14002ae47  mov     [rsp+0F0h+var_D0], 2
0x14002ae4c  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002ae51  cmp     edi, 2
0x14002ae54  jnz     short loc_14002AE71
0x14002ae56  cmp     esi, 1
0x14002ae59  jg      short loc_14002AE71
0x14002ae5b  mov     r9d, ebx
0x14002ae5e  mov     [rsp+0F0h+var_D0], r15b
0x14002ae63  mov     r8d, esi
0x14002ae66  mov     rdx, r14
0x14002ae69  mov     ecx, r12d
0x14002ae6c  call    PrjfTelemetryPostDirectoryExpansionTrigger
0x14002ae71  mov     rax, [rbp+3Fh+P]
0x14002ae75  test    rax, rax
0x14002ae78  jz      short loc_14002AE82
0x14002ae7a  mov     rcx, rax; P
0x14002ae7d  call    PrjfReleaseUnionContext
0x14002ae82  mov     rcx, [rbp+3Fh+Context]; Context
0x14002ae86  test    rcx, rcx
0x14002ae89  jz      short loc_14002AE97
0x14002ae8b  call    cs:__imp_FltReleaseContext
0x14002ae92  nop     dword ptr [rax+rax+00h]
0x14002ae97  mov     rcx, [rbp+3Fh+var_50]; Context
0x14002ae9b  test    rcx, rcx
0x14002ae9e  jz      short loc_14002AEAC
0x14002aea0  call    cs:__imp_FltReleaseContext
0x14002aea7  nop     dword ptr [rax+rax+00h]
0x14002aeac  mov     eax, ebx
0x14002aeae  add     rsp, 0B8h
0x14002aeb5  pop     r15
0x14002aeb7  pop     r14
0x14002aeb9  pop     r13
0x14002aebb  pop     r12
0x14002aebd  pop     rdi
0x14002aebe  pop     rsi
0x14002aebf  pop     rbx
0x14002aec0  pop     rbp
0x14002aec1  retn
```
