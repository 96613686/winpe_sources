# RAXferWorker::Initialize(IRDPSRAPIVirtualChannel *,ushort const *)

- ea: `0x140046008`
- end: `0x140046304`
- name: `?Initialize@RAXferWorker@@QEAAJPEAUIRDPSRAPIVirtualChannel@@PEBG@Z`
- size: `764`
- prototype: `__int64 __fastcall(RAXferWorker *__hidden this, struct IRDPSRAPIVirtualChannel *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003c2dc`

## callees

- `0x140001cc4`
- `0x140034ce4`
- `0x140045010`
- `0x140045150`
- `0x140046008`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400462ce`
- `KERNEL32!GetLastError` at `0x1400462ce`
- `KERNEL32!CreateTimerQueue` at `0x14004611f`
- `KERNEL32!CreateTimerQueue` at `0x14004611f`
- `KERNEL32!DeleteTimerQueueEx` at `0x1400462be`
- `KERNEL32!DeleteTimerQueueEx` at `0x1400462be`
- `msvcrt!??3@YAXPEAX@Z` at `0x14004629d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14004629d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RAXferWorker::Initialize(
        RAXferWorker *this,
        struct IRDPSRAPIVirtualChannel *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r14
  unsigned int v6; // ebx
  signed int v7; // ebp
  CEventLogger *v8; // rcx
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // r8
  CEventLogger *v13; // r9
  unsigned __int16 v14; // cx
  CEventLogger *v15; // rcx
  HANDLE TimerQueue; // rax
  CEventLogger *v17; // rcx
  __int16 *v18; // rax
  CEventLogger *v19; // rdx
  __int16 v20; // cx
  CEventLogger *v21; // rcx
  ChannelInfoList *v22; // rax
  CEventLogger *v23; // rcx
  signed int v24; // eax
  CEventLogger *v25; // rcx
  void *v26; // rsi
  void *v27; // rcx
  signed int LastError; // eax

  v3 = a3;
  if ( a2 )
  {
    if ( a3 )
    {
      ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))a2->lpVtbl->AddRef)(a2);
      v6 = -2147467261;
      if ( this )
      {
        *(_QWORD *)this = a2;
        ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))a2->lpVtbl->AddRef)(a2);
        v7 = 0;
      }
      else
      {
        v7 = -2147467261;
      }
      ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))a2->lpVtbl->Release)(a2);
      if ( v7 >= 0 )
      {
        v9 = 2147483646;
        v10 = 2147483646;
        v11 = 261;
        v12 = 261;
        v13 = (RAXferWorker *)((char *)this + 8);
        do
        {
          if ( !v10 )
            break;
          v14 = *v3;
          if ( !*v3 )
            break;
          ++v3;
          *(_WORD *)v13 = v14;
          v13 = (CEventLogger *)((char *)v13 + 2);
          --v10;
          --v12;
        }
        while ( v12 );
        v15 = (CEventLogger *)((char *)v13 - 2);
        if ( v12 )
          v15 = v13;
        *(_WORD *)v15 = 0;
        if ( v12 )
        {
          TimerQueue = CreateTimerQueue();
          *((_QWORD *)this + 75) = TimerQueue;
          if ( TimerQueue )
          {
            *((_QWORD *)this + 70) = (char *)this + 552;
            *((_QWORD *)this + 69) = (char *)this + 552;
            *((_QWORD *)this + 72) = (char *)this + 568;
            *((_QWORD *)this + 71) = (char *)this + 568;
            *((_QWORD *)this + 74) = (char *)this + 584;
            *((_QWORD *)this + 73) = (char *)this + 584;
            if ( this != (RAXferWorker *)-624LL )
            {
              v17 = *(CEventLogger **)this;
              *((_QWORD *)this + 78) = *(_QWORD *)this;
              if ( v17 )
                (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v17 + 8LL))(v17);
              v6 = 0;
            }
            if ( (v6 & 0x80000000) == 0 )
            {
              v18 = (__int16 *)((char *)this + 8);
              v19 = (RAXferWorker *)((char *)this + 632);
              do
              {
                if ( !v9 )
                  break;
                v20 = *v18;
                if ( !*v18 )
                  break;
                ++v18;
                *(_WORD *)v19 = v20;
                v19 = (CEventLogger *)((char *)v19 + 2);
                --v9;
                --v11;
              }
              while ( v11 );
              v6 = v11 == 0 ? 0x8007007A : 0;
              v21 = (CEventLogger *)((char *)v19 - 2);
              if ( v11 )
                v21 = v19;
              *(_WORD *)v21 = 0;
              if ( v11 )
              {
                v22 = (ChannelInfoList *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v22 )
                {
                  *((_QWORD *)v22 + 1) = v22;
                  *(_QWORD *)v22 = v22;
                }
                else
                {
                  v22 = 0;
                }
                *((_QWORD *)this + 67) = v22;
                if ( v22 )
                {
                  v24 = ChannelInfoList::Append(
                          v22,
                          (const unsigned __int16 *)this + 4,
                          *(struct IRDPSRAPIVirtualChannel **)this);
                  v6 = v24;
                  if ( v24 >= 0 )
                    return v6;
                  CEventLogger::LogError(
                    v25,
                    &Recoverable_Error,
                    L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                    0x89u,
                    L"RAXferWorker::Initialize",
                    v24);
                }
                else
                {
                  v6 = -2147024882;
                  CEventLogger::LogError(
                    v23,
                    &Recoverable_Error,
                    L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                    0x85u,
                    L"RAXferWorker::Initialize",
                    0x8007000E);
                }
              }
              else
              {
                CEventLogger::LogError(
                  v21,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                  0x7Fu,
                  L"RAXferWorker::Initialize",
                  v6);
              }
            }
            else
            {
              CEventLogger::LogError(
                v17,
                &Recoverable_Error,
                L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                0x7Bu,
                L"RAXferWorker::Initialize",
                v6);
            }
          }
          else
          {
            v6 = -2147024890;
          }
        }
        else
        {
          v6 = -2147024774;
          CEventLogger::LogError(
            v15,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
            0x66u,
            L"RAXferWorker::Initialize",
            0x8007007A);
        }
      }
      else
      {
        v6 = v7;
        CEventLogger::LogError(
          v8,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
          0x60u,
          L"RAXferWorker::Initialize",
          v7);
      }
    }
    else
    {
      v6 = -2147467261;
      CEventLogger::LogError(
        this,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x5Du,
        L"RAXferWorker::Initialize",
        0x80004003);
    }
  }
  else
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      this,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x5Cu,
      L"RAXferWorker::Initialize",
      0x80004003);
  }
  v26 = (void *)*((_QWORD *)this + 67);
  if ( v26 )
  {
    ChannelInfoList::~ChannelInfoList(*((ChannelInfoList **)this + 67));
    operator delete(v26);
    *((_QWORD *)this + 67) = 0;
  }
  v27 = (void *)*((_QWORD *)this + 75);
  if ( v27 )
  {
    if ( DeleteTimerQueueEx(v27, 0) )
    {
      *((_QWORD *)this + 75) = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140046008  push    rbx
0x14004600a  push    rbp
0x14004600b  push    rsi
0x14004600c  push    rdi
0x14004600d  push    r12
0x14004600f  push    r14
0x140046011  push    r15
0x140046013  sub     rsp, 30h
0x140046017  mov     r14, r8
0x14004601a  mov     rsi, rdx
0x14004601d  mov     rdi, rcx
0x140046020  xor     r12d, r12d
0x140046023  test    rdx, rdx
0x140046026  jnz     short loc_14004603E
0x140046028  mov     ebx, 80004003h
0x14004602d  mov     [rsp+68h+var_40], 80004003h
0x140046035  lea     r9d, [rdx+5Ch]
0x140046039  jmp     loc_140046267
0x14004603e  test    r8, r8
0x140046041  jnz     short loc_140046059
0x140046043  mov     ebx, 80004003h
0x140046048  mov     [rsp+68h+var_40], 80004003h
0x140046050  lea     r9d, [r8+5Dh]
0x140046054  jmp     loc_140046267
0x140046059  mov     rax, [rdx]
0x14004605c  mov     rcx, rsi
0x14004605f  mov     rax, [rax+8]
0x140046063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046068  nop
0x140046069  mov     ebx, 80004003h
0x14004606e  test    rdi, rdi
0x140046071  jnz     short loc_140046077
0x140046073  mov     ebp, ebx
0x140046075  jmp     short loc_14004608C
0x140046077  mov     [rdi], rsi
0x14004607a  mov     rax, [rsi]
0x14004607d  mov     rcx, rsi
0x140046080  mov     rax, [rax+8]
0x140046084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046089  mov     ebp, r12d
0x14004608c  mov     rax, [rsi]
0x14004608f  mov     rcx, rsi
0x140046092  mov     rax, [rax+10h]
0x140046096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004609b  nop
0x14004609c  test    ebp, ebp
0x14004609e  jns     short loc_1400460B1
0x1400460a0  mov     ebx, ebp
0x1400460a2  mov     [rsp+68h+var_40], ebp
0x1400460a6  mov     r9d, 60h ; '`'
0x1400460ac  jmp     loc_140046267
0x1400460b1  lea     r15, [rdi+8]
0x1400460b5  mov     ebp, 7FFFFFFEh
0x1400460ba  mov     eax, ebp
0x1400460bc  mov     esi, 105h
0x1400460c1  mov     r8d, esi
0x1400460c4  mov     r9, r15
0x1400460c7  test    rax, rax
0x1400460ca  jz      short loc_1400460EA
0x1400460cc  movzx   ecx, word ptr [r14]
0x1400460d0  test    cx, cx
0x1400460d3  jz      short loc_1400460EA
0x1400460d5  add     r14, 2
0x1400460d9  mov     [r9], cx
0x1400460dd  add     r9, 2
0x1400460e1  dec     rax
0x1400460e4  sub     r8, 1
0x1400460e8  jnz     short loc_1400460C7
0x1400460ea  mov     rax, r8
0x1400460ed  neg     rax
0x1400460f0  sbb     edx, edx
0x1400460f2  not     edx
0x1400460f4  mov     r14d, 8007007Ah
0x1400460fa  and     edx, r14d
0x1400460fd  lea     rcx, [r9-2]
0x140046101  test    r8, r8
0x140046104  cmovnz  rcx, r9
0x140046108  mov     [rcx], r12w
0x14004610c  jnz     short loc_14004611F
0x14004610e  mov     ebx, edx
0x140046110  mov     [rsp+68h+var_40], edx
0x140046114  mov     r9d, 66h ; 'f'
0x14004611a  jmp     loc_140046267
0x14004611f  call    cs:__imp_CreateTimerQueue
0x140046126  nop     dword ptr [rax+rax+00h]
0x14004612b  mov     [rdi+258h], rax
0x140046132  test    rax, rax
0x140046135  jnz     short loc_140046141
0x140046137  mov     ebx, 80070006h
0x14004613c  jmp     loc_140046286
0x140046141  lea     rax, [rdi+228h]
0x140046148  mov     [rdi+230h], rax
0x14004614f  mov     [rax], rax
0x140046152  lea     rax, [rdi+238h]
0x140046159  mov     [rdi+240h], rax
0x140046160  mov     [rax], rax
0x140046163  lea     rax, [rdi+248h]
0x14004616a  mov     [rdi+250h], rax
0x140046171  mov     [rax], rax
0x140046174  lea     rax, [rdi+270h]
0x14004617b  test    rax, rax
0x14004617e  jz      short loc_14004619A
0x140046180  mov     rcx, [rdi]
0x140046183  mov     [rax], rcx
0x140046186  test    rcx, rcx
0x140046189  jz      short loc_140046197
0x14004618b  mov     rax, [rcx]
0x14004618e  mov     rax, [rax+8]
0x140046192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046197  mov     ebx, r12d
0x14004619a  test    ebx, ebx
0x14004619c  jns     short loc_1400461AD
0x14004619e  mov     [rsp+68h+var_40], ebx
0x1400461a2  mov     r9d, 7Bh ; '{'
0x1400461a8  jmp     loc_140046267
0x1400461ad  mov     rax, r15
0x1400461b0  lea     rdx, [rdi+278h]
0x1400461b7  test    rbp, rbp
0x1400461ba  jz      short loc_1400461D8
0x1400461bc  movzx   ecx, word ptr [rax]
0x1400461bf  test    cx, cx
0x1400461c2  jz      short loc_1400461D8
0x1400461c4  add     rax, 2
0x1400461c8  mov     [rdx], cx
0x1400461cb  add     rdx, 2
0x1400461cf  dec     rbp
0x1400461d2  sub     rsi, 1
0x1400461d6  jnz     short loc_1400461B7
0x1400461d8  mov     rax, rsi
0x1400461db  neg     rax
0x1400461de  sbb     ebx, ebx
0x1400461e0  not     ebx
0x1400461e2  and     ebx, r14d
0x1400461e5  lea     rcx, [rdx-2]
0x1400461e9  test    rsi, rsi
0x1400461ec  cmovnz  rcx, rdx
0x1400461f0  mov     [rcx], r12w
0x1400461f4  jnz     short loc_140046202
0x1400461f6  mov     [rsp+68h+var_40], ebx
0x1400461fa  mov     r9d, 7Fh
0x140046200  jmp     short loc_140046267
0x140046202  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046209  mov     ecx, 10h; unsigned __int64
0x14004620e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140046213  test    rax, rax
0x140046216  jz      short loc_140046221
0x140046218  mov     [rax+8], rax
0x14004621c  mov     [rax], rax
0x14004621f  jmp     short loc_140046224
0x140046221  mov     rax, r12
0x140046224  mov     [rdi+218h], rax
0x14004622b  test    rax, rax
0x14004622e  jnz     short loc_140046245
0x140046230  mov     ebx, 8007000Eh
0x140046235  mov     [rsp+68h+var_40], 8007000Eh
0x14004623d  mov     r9d, 85h
0x140046243  jmp     short loc_140046267
0x140046245  mov     r8, [rdi]; struct IRDPSRAPIVirtualChannel *
0x140046248  mov     rdx, r15; unsigned __int16 *
0x14004624b  mov     rcx, rax; this
0x14004624e  call    ?Append@ChannelInfoList@@QEAAJPEBGPEAUIRDPSRAPIVirtualChannel@@@Z; ChannelInfoList::Append(ushort const *,IRDPSRAPIVirtualChannel *)
0x140046253  mov     ebx, eax
0x140046255  test    eax, eax
0x140046257  jns     loc_1400462F2
0x14004625d  mov     [rsp+68h+var_40], eax; unsigned int
0x140046261  mov     r9d, 89h; unsigned int
0x140046267  lea     rax, aRaxferworkerIn; "RAXferWorker::Initialize"
0x14004626e  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140046273  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x14004627a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140046281  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140046286  mov     rsi, [rdi+218h]
0x14004628d  test    rsi, rsi
0x140046290  jz      short loc_1400462B0
0x140046292  mov     rcx, rsi; this
0x140046295  call    ??1ChannelInfoList@@QEAA@XZ; ChannelInfoList::~ChannelInfoList(void)
0x14004629a  mov     rcx, rsi
0x14004629d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400462a4  nop     dword ptr [rax+rax+00h]
0x1400462a9  mov     [rdi+218h], r12
0x1400462b0  mov     rcx, [rdi+258h]; TimerQueue
0x1400462b7  test    rcx, rcx
0x1400462ba  jz      short loc_1400462F2
0x1400462bc  xor     edx, edx; CompletionEvent
0x1400462be  call    cs:__imp_DeleteTimerQueueEx
0x1400462c5  nop     dword ptr [rax+rax+00h]
0x1400462ca  test    eax, eax
0x1400462cc  jnz     short loc_1400462EB
0x1400462ce  call    cs:__imp_GetLastError
0x1400462d5  nop     dword ptr [rax+rax+00h]
0x1400462da  mov     ebx, eax
0x1400462dc  test    eax, eax
0x1400462de  jle     short loc_1400462F2
0x1400462e0  movzx   ebx, ax
0x1400462e3  or      ebx, 80070000h
0x1400462e9  jmp     short loc_1400462F2
0x1400462eb  mov     [rdi+258h], r12
0x1400462f2  mov     eax, ebx
0x1400462f4  add     rsp, 30h
0x1400462f8  pop     r15
0x1400462fa  pop     r14
0x1400462fc  pop     r12
0x1400462fe  pop     rdi
0x1400462ff  pop     rsi
0x140046300  pop     rbp
0x140046301  pop     rbx
0x140046302  retn
```
