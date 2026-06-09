# PrjfExpansionWorker

- ea: `0x140029f60`
- end: `0x14002a258`
- name: `PrjfExpansionWorker`
- size: `760`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, struct _FLT_INSTANCE *FltObject, struct _FILE_OBJECT *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002d9c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14002208c`
- `0x140029650`
- `0x140029f60`
- `0x140037418`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x14002a16a`
- `ntoskrnl!IoClearActivityIdThread` at `0x14002a16a`
- `ntoskrnl!KeSetEvent` at `0x14002a1a6`
- `ntoskrnl!KeSetEvent` at `0x14002a1a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a224`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a224`
- `HAL!KeQueryPerformanceCounter` at `0x14002a00a`
- `HAL!KeQueryPerformanceCounter` at `0x14002a03e`
- `HAL!KeQueryPerformanceCounter` at `0x14002a00a`
- `HAL!KeQueryPerformanceCounter` at `0x14002a03e`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14002a085`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14002a085`
- `FLTMGR!FltPropagateActivityIdToThread` at `0x14002a0b0`
- `FLTMGR!FltPropagateActivityIdToThread` at `0x14002a0b0`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14002a155`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14002a155`
- `FLTMGR!FltCompletePendedPostOperation` at `0x14002a0f9`
- `FLTMGR!FltCompletePendedPostOperation` at `0x14002a0f9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140029fb9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140029fb9`
- `FLTMGR!FltReleaseContext` at `0x14002a1e8`
- `FLTMGR!FltReleaseContext` at `0x14002a1fc`
- `FLTMGR!FltReleaseContext` at `0x14002a210`
- `FLTMGR!FltReleaseContext` at `0x14002a1e8`
- `FLTMGR!FltReleaseContext` at `0x14002a1fc`
- `FLTMGR!FltReleaseContext` at `0x14002a210`

## pseudocode

```c
void __fastcall PrjfExpansionWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Context)
{
  struct _FILE_OBJECT *v3; // r15
  char ContextFileObject; // al
  _DWORD *v6; // rsi
  _QWORD *v7; // rdi
  bool v8; // zf
  FLT_PREOP_CALLBACK_STATUS v9; // r12d
  __int64 v10; // r13
  LARGE_INTEGER v11; // rdx
  LARGE_INTEGER v12; // rcx
  LARGE_INTEGER v13; // rbx
  int v14; // eax
  int v15; // r14d
  char v16; // r15
  PFLT_CALLBACK_DATA v17; // rax
  __int64 v18; // rcx
  struct _FLT_CALLBACK_DATA *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  int v23; // ecx
  char v24; // [rsp+40h] [rbp-49h]
  PFLT_CONTEXT v25; // [rsp+48h] [rbp-41h] BYREF
  PFLT_CONTEXT v26; // [rsp+50h] [rbp-39h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+58h] [rbp-31h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp-29h] BYREF
  __int64 v29; // [rsp+68h] [rbp-21h] BYREF
  LONGLONG v30; // [rsp+70h] [rbp-19h]
  __int64 v31; // [rsp+78h] [rbp-11h] BYREF
  struct _FLT_INSTANCE *v32; // [rsp+80h] [rbp-9h]
  struct _FILE_OBJECT *v33; // [rsp+88h] [rbp-1h]
  __int128 v34; // [rsp+90h] [rbp+7h] BYREF

  v33 = Context;
  v26 = 0;
  v25 = 0;
  v3 = Context;
  Contexta = 0;
  v34 = 0;
  v29 = 0;
  v31 = 0;
  PerformanceFrequency.QuadPart = 0;
  v32 = FltObject;
  FltFreeGenericWorkItem(FltWorkItem);
  ContextFileObject = PrjfGetContextFileObjectEx(FltObject, v3, &v25, &v26, &Contexta);
  v6 = v26;
  v7 = v25;
  if ( ContextFileObject )
  {
    v8 = *((_DWORD *)v25 + 16) == 3;
    v9 = FLT_PREOP_SUCCESS_NO_CALLBACK;
    LOBYTE(v26) = 0;
    v10 = 0;
    if ( v8 )
    {
      v15 = 0;
      v30 = 0;
      LODWORD(v25) = 0;
      v24 = 1;
    }
    else
    {
      v24 = 0;
      v13 = KeQueryPerformanceCounter(&PerformanceFrequency);
      if ( *v6 )
        ((void (__fastcall *)(_QWORD, _QWORD))MicrosoftTelemetryAssertTriggeredNoArgsKM)(
          (LARGE_INTEGER)v12.QuadPart,
          (LARGE_INTEGER)v11.QuadPart);
      v14 = PrjfExpandFile(FltObject, v3, (__int64)v6, &v31);
      LODWORD(v25) = 1;
      v15 = v14;
      v30 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v13.QuadPart) / PerformanceFrequency.QuadPart;
    }
    v16 = (char)v26;
    do
    {
      while ( 1 )
      {
        _InterlockedExchange((volatile __int32 *)(v7[11] + 64LL), 1);
        v17 = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(v7[11] + 72LL), 0);
        v18 = v7[11];
        v19 = v17;
        if ( !v17 )
          break;
        _InterlockedDecrement((volatile signed __int32 *)(v18 + 68));
        if ( (int)FltPropagateActivityIdToThread(v17, &v34, &v29) >= 0 )
          v16 = 1;
        if ( (v19->Flags & 0x80000) != 0 )
        {
          if ( v15 < 0 )
          {
            Iopb = v19->Iopb;
            if ( !Iopb->MajorFunction )
              PrjfCancelFileOpen((__int64)v19, v32, Iopb->TargetFileObject, v15);
          }
          FltCompletePendedPostOperation(v19);
        }
        else
        {
          if ( v15 >= 0 )
          {
            if ( v19->Iopb->MajorFunction == 4 && v6 && (v6[10] & 0x400) != 0 && Contexta )
            {
              if ( *(_DWORD *)(v7[11] + 300LL) != 17 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20);
              v9 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
            }
          }
          else
          {
            v19->IoStatus.Status = v15;
            v9 = FLT_PREOP_COMPLETE;
          }
          FltCompletePendedPreOperation(v19, v9, 0);
        }
        if ( v16 )
          IoClearActivityIdThread(v29);
        ++v10;
      }
    }
    while ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 64), 0xFFFFFFFF) != 1 );
    KeSetEvent((PRKEVENT)(v7[11] + 16LL), 0, 0);
    LOBYTE(v23) = v24;
    PrjfTelemetryPostExpansionComplete(v23, (_DWORD)v25, v7[11], v15, v10, v31, v30);
    v3 = v33;
  }
  if ( Contexta )
    FltReleaseContext(Contexta);
  if ( v6 )
    FltReleaseContext(v6);
  if ( v7 )
    FltReleaseContext(v7);
  if ( v3 )
    ObfDereferenceObject(v3);
}

```

## disassembly

```asm
0x140029f60  mov     [rsp-8+arg_18], rbx
0x140029f65  push    rbp
0x140029f66  push    rsi
0x140029f67  push    rdi
0x140029f68  push    r12
0x140029f6a  push    r13
0x140029f6c  push    r14
0x140029f6e  push    r15
0x140029f70  lea     rbp, [rsp-27h]
0x140029f75  sub     rsp, 0B0h
0x140029f7c  mov     rax, cs:__security_cookie
0x140029f83  xor     rax, rsp
0x140029f86  mov     [rbp+57h+var_40], rax
0x140029f8a  xor     ebx, ebx
0x140029f8c  mov     [rbp+57h+var_58], r8
0x140029f90  xorps   xmm0, xmm0
0x140029f93  mov     [rbp+57h+var_90], rbx
0x140029f97  mov     [rbp+57h+var_98], rbx
0x140029f9b  mov     r15, r8
0x140029f9e  mov     [rbp+57h+Context], rbx
0x140029fa2  mov     r14, rdx
0x140029fa5  movups  [rbp+57h+var_50], xmm0
0x140029fa9  mov     [rbp+57h+var_78], rbx
0x140029fad  mov     [rbp+57h+var_68], rbx
0x140029fb1  mov     qword ptr [rbp+57h+PerformanceFrequency], rbx
0x140029fb5  mov     [rbp+57h+var_60], rdx
0x140029fb9  call    cs:__imp_FltFreeGenericWorkItem
0x140029fc0  nop     dword ptr [rax+rax+00h]
0x140029fc5  lea     rax, [rbp+57h+Context]
0x140029fc9  mov     rdx, r15; FileObject
0x140029fcc  lea     r9, [rbp+57h+var_90]
0x140029fd0  mov     [rsp+0E0h+var_C0], rax; Context
0x140029fd5  lea     r8, [rbp+57h+var_98]
0x140029fd9  mov     rcx, r14; Instance
0x140029fdc  call    PrjfGetContextFileObjectEx
0x140029fe1  mov     rsi, [rbp+57h+var_90]
0x140029fe5  mov     rdi, [rbp+57h+var_98]
0x140029fe9  test    al, al
0x140029feb  jz      loc_14002A1DF
0x140029ff1  cmp     dword ptr [rdi+40h], 3
0x140029ff5  lea     eax, [rbx+1]
0x140029ff8  mov     r12d, eax
0x140029ffb  mov     byte ptr [rbp+57h+var_90], bl
0x140029ffe  mov     r13d, ebx
0x14002a001  jz      short loc_14002A063
0x14002a003  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14002a007  mov     [rbp+57h+var_A0], bl
0x14002a00a  call    cs:__imp_KeQueryPerformanceCounter
0x14002a011  nop     dword ptr [rax+rax+00h]
0x14002a016  mov     rbx, rax
0x14002a019  cmp     [rsi], r13d
0x14002a01c  jz      short loc_14002A023
0x14002a01e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002a023  lea     r9, [rbp+57h+var_68]
0x14002a027  mov     r8, rsi
0x14002a02a  mov     rdx, r15
0x14002a02d  mov     rcx, r14
0x14002a030  call    PrjfExpandFile
0x14002a035  xor     ecx, ecx; PerformanceFrequency
0x14002a037  mov     dword ptr [rbp+57h+var_98], r12d
0x14002a03b  mov     r14d, eax
0x14002a03e  call    cs:__imp_KeQueryPerformanceCounter
0x14002a045  nop     dword ptr [rax+rax+00h]
0x14002a04a  sub     rax, rbx
0x14002a04d  imul    rax, 3E8h
0x14002a054  cqo
0x14002a056  idiv    qword ptr [rbp+57h+PerformanceFrequency]
0x14002a05a  mov     [rbp+57h+var_70], rax
0x14002a05e  mov     rax, r12
0x14002a061  jmp     short loc_14002A070
0x14002a063  mov     r14d, ebx
0x14002a066  mov     [rbp+57h+var_70], rbx
0x14002a06a  mov     dword ptr [rbp+57h+var_98], ebx
0x14002a06d  mov     [rbp+57h+var_A0], al
0x14002a070  mov     r15d, dword ptr [rbp+57h+var_90]
0x14002a074  mov     rcx, [rdi+58h]
0x14002a078  xor     edx, edx; PeekContext
0x14002a07a  xchg    eax, [rcx+40h]
0x14002a07d  mov     rcx, [rdi+58h]
0x14002a081  add     rcx, 48h ; 'H'; Cbdq
0x14002a085  call    cs:__imp_FltCbdqRemoveNextIo
0x14002a08c  nop     dword ptr [rax+rax+00h]
0x14002a091  mov     rcx, [rdi+58h]
0x14002a095  mov     rbx, rax
0x14002a098  test    rax, rax
0x14002a09b  jz      loc_14002A183
0x14002a0a1  lock dec dword ptr [rcx+44h]
0x14002a0a5  lea     r8, [rbp+57h+var_78]
0x14002a0a9  mov     rcx, rax
0x14002a0ac  lea     rdx, [rbp+57h+var_50]
0x14002a0b0  call    cs:__imp_FltPropagateActivityIdToThread
0x14002a0b7  nop     dword ptr [rax+rax+00h]
0x14002a0bc  test    eax, eax
0x14002a0be  movzx   r15d, r15b
0x14002a0c2  mov     eax, 1
0x14002a0c7  cmovns  r15d, eax
0x14002a0cb  test    dword ptr [rbx], 80000h
0x14002a0d1  jz      short loc_14002A107
0x14002a0d3  test    r14d, r14d
0x14002a0d6  jns     short loc_14002A0F6
0x14002a0d8  mov     r8, [rbx+10h]
0x14002a0dc  cmp     byte ptr [r8+4], 0
0x14002a0e1  jnz     short loc_14002A0F6
0x14002a0e3  mov     r8, [r8+8]
0x14002a0e7  mov     r9d, r14d
0x14002a0ea  mov     rdx, [rbp+57h+var_60]
0x14002a0ee  mov     rcx, rbx
0x14002a0f1  call    PrjfCancelFileOpen
0x14002a0f6  mov     rcx, rbx; CallbackData
0x14002a0f9  call    cs:__imp_FltCompletePendedPostOperation
0x14002a100  nop     dword ptr [rax+rax+00h]
0x14002a105  jmp     short loc_14002A161
0x14002a107  test    r14d, r14d
0x14002a10a  jns     short loc_14002A118
0x14002a10c  mov     [rbx+18h], r14d
0x14002a110  mov     r12d, 4
0x14002a116  jmp     short loc_14002A14C
0x14002a118  mov     rax, [rbx+10h]
0x14002a11c  cmp     byte ptr [rax+4], 4
0x14002a120  jnz     short loc_14002A14C
0x14002a122  test    rsi, rsi
0x14002a125  jz      short loc_14002A14C
0x14002a127  test    dword ptr [rsi+28h], 400h
0x14002a12e  jz      short loc_14002A14C
0x14002a130  cmp     [rbp+57h+Context], 0
0x14002a135  jz      short loc_14002A14C
0x14002a137  mov     rax, [rdi+58h]
0x14002a13b  cmp     dword ptr [rax+12Ch], 11h
0x14002a142  jz      short loc_14002A149
0x14002a144  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002a149  xor     r12d, r12d
0x14002a14c  xor     r8d, r8d; Context
0x14002a14f  mov     edx, r12d; CallbackStatus
0x14002a152  mov     rcx, rbx; CallbackData
0x14002a155  call    cs:__imp_FltCompletePendedPreOperation
0x14002a15c  nop     dword ptr [rax+rax+00h]
0x14002a161  test    r15b, r15b
0x14002a164  jz      short loc_14002A176
0x14002a166  mov     rcx, [rbp+57h+var_78]
0x14002a16a  call    cs:__imp_IoClearActivityIdThread
0x14002a171  nop     dword ptr [rax+rax+00h]
0x14002a176  mov     eax, 1
0x14002a17b  add     r13, rax
0x14002a17e  jmp     loc_14002A074
0x14002a183  or      eax, 0FFFFFFFFh
0x14002a186  lock xadd [rcx+40h], eax
0x14002a18b  cmp     eax, 1
0x14002a18e  mov     eax, 1
0x14002a193  jnz     loc_14002A074
0x14002a199  mov     rcx, [rdi+58h]
0x14002a19d  xor     r8d, r8d; Wait
0x14002a1a0  add     rcx, 10h; Event
0x14002a1a4  xor     edx, edx; Increment
0x14002a1a6  call    cs:__imp_KeSetEvent
0x14002a1ad  nop     dword ptr [rax+rax+00h]
0x14002a1b2  mov     rax, [rbp+57h+var_70]
0x14002a1b6  mov     r9d, r14d
0x14002a1b9  mov     r8, [rdi+58h]
0x14002a1bd  mov     edx, dword ptr [rbp+57h+var_98]
0x14002a1c0  mov     cl, [rbp+57h+var_A0]
0x14002a1c3  mov     [rsp+0E0h+var_B0], rax
0x14002a1c8  mov     rax, [rbp+57h+var_68]
0x14002a1cc  mov     [rsp+0E0h+var_B8], rax
0x14002a1d1  mov     [rsp+0E0h+var_C0], r13
0x14002a1d6  call    PrjfTelemetryPostExpansionComplete
0x14002a1db  mov     r15, [rbp+57h+var_58]
0x14002a1df  mov     rcx, [rbp+57h+Context]; Context
0x14002a1e3  test    rcx, rcx
0x14002a1e6  jz      short loc_14002A1F4
0x14002a1e8  call    cs:__imp_FltReleaseContext
0x14002a1ef  nop     dword ptr [rax+rax+00h]
0x14002a1f4  test    rsi, rsi
0x14002a1f7  jz      short loc_14002A208
0x14002a1f9  mov     rcx, rsi; Context
0x14002a1fc  call    cs:__imp_FltReleaseContext
0x14002a203  nop     dword ptr [rax+rax+00h]
0x14002a208  test    rdi, rdi
0x14002a20b  jz      short loc_14002A21C
0x14002a20d  mov     rcx, rdi; Context
0x14002a210  call    cs:__imp_FltReleaseContext
0x14002a217  nop     dword ptr [rax+rax+00h]
0x14002a21c  test    r15, r15
0x14002a21f  jz      short loc_14002A230
0x14002a221  mov     rcx, r15; Object
0x14002a224  call    cs:__imp_ObfDereferenceObject
0x14002a22b  nop     dword ptr [rax+rax+00h]
0x14002a230  mov     rcx, [rbp+57h+var_40]
0x14002a234  xor     rcx, rsp; StackCookie
0x14002a237  call    __security_check_cookie
0x14002a23c  mov     rbx, [rsp+0E0h+arg_18]
0x14002a244  add     rsp, 0B0h
0x14002a24b  pop     r15
0x14002a24d  pop     r14
0x14002a24f  pop     r13
0x14002a251  pop     r12
0x14002a253  pop     rdi
0x14002a254  pop     rsi
0x14002a255  pop     rbp
0x14002a256  retn
```
