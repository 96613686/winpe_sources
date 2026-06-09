# APPLICATION::RealShutdown(long,uint,int,int)

- ea: `0x180006480`
- end: `0x18000665e`
- name: `?RealShutdown@APPLICATION@@QEAAXJIHH@Z`
- size: `478`
- prototype: `void __usercall(APPLICATION *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003560`
- `0x180003590`
- `0x180003910`
- `0x180006180`
- `0x1800061b0`
- `0x180006670`
- `0x180006ef0`
- `0x180006f60`
- `0x180007180`
- `0x180008164`
- `0x18000bac0`

## callees

- `0x180001d50`
- `0x180002200`
- `0x1800033e0`
- `0x180006480`
- `0x180006c5c`
- `0x1800083d0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006542`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006500`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006566`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006619`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006566`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006619`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180006538`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180006538`

## pseudocode

```c
void __fastcall APPLICATION::RealShutdown(APPLICATION *this, unsigned int a2, unsigned int a3, int a4, int a5)
{
  __int64 v9; // rdi
  int v10; // ebp
  __int64 v11; // rcx
  __int64 v12; // rdi
  SEND_QUEUE *v13; // rcx
  SEND_QUEUE *v14; // rcx
  SEND_QUEUE *v15; // rcx
  SEND_QUEUE *v16; // rcx
  PROTOCOL *v17; // rcx

  if ( _InterlockedExchange((volatile __int32 *)this + 26, 1) != 1 )
  {
    v9 = *((_QWORD *)this + 10);
    v10 = 0;
    if ( v9 )
    {
      if ( *(_DWORD *)(v9 + 104) )
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 64));
      if ( !*(_DWORD *)(v9 + 108) )
      {
        v11 = *(_QWORD *)(v9 + 32);
        *(_DWORD *)(v9 + 108) = 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
      }
      if ( *(_DWORD *)(v9 + 104) )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 64));
    }
    if ( *((_DWORD *)this + 38) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      v10 = 1;
    }
    if ( *((_QWORD *)this + 29) )
    {
      if ( a4 == 1 && a3 != 200003 )
        APPLICATION::SendSignalBeforeTerminate(this, a2, 0);
      if ( !TerminateProcess(*((HANDLE *)this + 29), 0) )
        GetLastError();
      *((_DWORD *)this + 63) = -1;
    }
    v12 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    v13 = (SEND_QUEUE *)*((_QWORD *)this + 9);
    if ( v13 )
      SEND_QUEUE::Shutdown(v13);
    v14 = (SEND_QUEUE *)*((_QWORD *)this + 8);
    if ( v14 )
      SEND_QUEUE::Shutdown(v14);
    v15 = (SEND_QUEUE *)*((_QWORD *)this + 9);
    if ( v15 )
    {
      SEND_QUEUE::DereferenceSendQueue(v15);
      *((_DWORD *)this + 53) = 0;
    }
    v16 = (SEND_QUEUE *)*((_QWORD *)this + 8);
    if ( v16 )
    {
      SEND_QUEUE::DereferenceSendQueue(v16);
      *((_QWORD *)this + 8) = 0;
    }
    v17 = (PROTOCOL *)*((_QWORD *)this + 10);
    if ( v17 )
    {
      PROTOCOL::DereferenceProtocol(v17);
      *((_QWORD *)this + 10) = 0;
    }
    if ( *((_DWORD *)this + 12) != 3 )
      *((_DWORD *)this + 12) = 3;
    if ( a2 == -2147014842 || a2 == -2147023667 )
      a4 = 1;
    if ( a5 == 1 )
      APPLICATION_MANAGER::ReturnApplication(*((APPLICATION_MANAGER **)this + 12), this, a4, 1);
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 40LL))(
        v12,
        a2,
        a3,
        *((_QWORD *)this + 43));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
    }
  }
}

```

## disassembly

```asm
0x180006480  push    rbx
0x180006482  push    rbp
0x180006483  push    rsi
0x180006484  push    rdi
0x180006485  push    r12
0x180006487  push    r14
0x180006489  push    r15
0x18000648b  sub     rsp, 30h
0x18000648f  mov     eax, 1
0x180006494  mov     r14d, r9d
0x180006497  xchg    eax, [rcx+68h]
0x18000649a  mov     r12d, r8d
0x18000649d  mov     r15d, edx
0x1800064a0  mov     rbx, rcx
0x1800064a3  cmp     eax, 1
0x1800064a6  jz      loc_18000664F
0x1800064ac  mov     rdi, [rcx+50h]
0x1800064b0  xor     ebp, ebp
0x1800064b2  test    rdi, rdi
0x1800064b5  jz      short loc_1800064F1
0x1800064b7  cmp     [rdi+68h], ebp
0x1800064ba  jz      short loc_1800064C6
0x1800064bc  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800064c0  call    cs:__imp_EnterCriticalSection
0x1800064c6  cmp     [rdi+6Ch], ebp
0x1800064c9  jnz     short loc_1800064E2
0x1800064cb  mov     rcx, [rdi+20h]
0x1800064cf  mov     dword ptr [rdi+6Ch], 1
0x1800064d6  mov     rax, [rcx]
0x1800064d9  mov     rax, [rax+18h]
0x1800064dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e2  cmp     [rdi+68h], ebp
0x1800064e5  jz      short loc_1800064F1
0x1800064e7  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800064eb  call    cs:__imp_LeaveCriticalSection
0x1800064f1  lea     rsi, [rbx+70h]
0x1800064f5  cmp     [rbx+98h], ebp
0x1800064fb  jz      short loc_18000650B
0x1800064fd  mov     rcx, rsi; lpCriticalSection
0x180006500  call    cs:__imp_EnterCriticalSection
0x180006506  mov     ebp, 1
0x18000650b  cmp     qword ptr [rbx+0E8h], 0
0x180006513  jz      short loc_180006552
0x180006515  cmp     r14d, 1
0x180006519  jnz     short loc_18000652F
0x18000651b  cmp     r12d, 30D43h
0x180006522  jz      short loc_18000652F
0x180006524  xor     r8d, r8d; void **
0x180006527  mov     rcx, rbx; this
0x18000652a  call    ?SendSignalBeforeTerminate@APPLICATION@@QEAAXHPEAPEAX@Z; APPLICATION::SendSignalBeforeTerminate(int,void * *)
0x18000652f  mov     rcx, [rbx+0E8h]; hProcess
0x180006536  xor     edx, edx; uExitCode
0x180006538  call    cs:__imp_TerminateProcess
0x18000653e  test    eax, eax
0x180006540  jnz     short loc_180006548
0x180006542  call    cs:__imp_GetLastError
0x180006548  mov     dword ptr [rbx+0FCh], 0FFFFFFFFh
0x180006552  mov     rdi, [rbx+58h]
0x180006556  mov     qword ptr [rbx+58h], 0
0x18000655e  test    ebp, ebp
0x180006560  jz      short loc_18000656E
0x180006562  lea     rcx, [rbx+70h]; lpCriticalSection
0x180006566  call    cs:__imp_LeaveCriticalSection
0x18000656c  xor     ebp, ebp
0x18000656e  mov     rcx, [rbx+48h]; this
0x180006572  test    rcx, rcx
0x180006575  jz      short loc_18000657C
0x180006577  call    ?Shutdown@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::Shutdown(void)
0x18000657c  mov     rcx, [rbx+40h]; this
0x180006580  test    rcx, rcx
0x180006583  jz      short loc_18000658A
0x180006585  call    ?Shutdown@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::Shutdown(void)
0x18000658a  mov     rcx, [rbx+48h]; this
0x18000658e  test    rcx, rcx
0x180006591  jz      short loc_1800065A2
0x180006593  call    ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
0x180006598  mov     dword ptr [rbx+0D4h], 0
0x1800065a2  mov     rcx, [rbx+40h]; this
0x1800065a6  test    rcx, rcx
0x1800065a9  jz      short loc_1800065B8
0x1800065ab  call    ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
0x1800065b0  mov     qword ptr [rbx+40h], 0
0x1800065b8  mov     rcx, [rbx+50h]; this
0x1800065bc  test    rcx, rcx
0x1800065bf  jz      short loc_1800065CE
0x1800065c1  call    ?DereferenceProtocol@PROTOCOL@@QEAAXXZ; PROTOCOL::DereferenceProtocol(void)
0x1800065c6  mov     qword ptr [rbx+50h], 0
0x1800065ce  cmp     dword ptr [rbx+30h], 3
0x1800065d2  jz      short loc_1800065DB
0x1800065d4  mov     dword ptr [rbx+30h], 3
0x1800065db  cmp     r15d, 80072746h
0x1800065e2  jz      short loc_1800065ED
0x1800065e4  cmp     r15d, 800704CDh
0x1800065eb  jnz     short loc_1800065F3
0x1800065ed  mov     r14d, 1
0x1800065f3  cmp     [rsp+68h+arg_20], 1
0x1800065fb  jnz     short loc_180006612
0x1800065fd  mov     rcx, [rbx+60h]; this
0x180006601  mov     r9d, 1; int
0x180006607  mov     r8d, r14d; int
0x18000660a  mov     rdx, rbx; struct APPLICATION *
0x18000660d  call    ?ReturnApplication@APPLICATION_MANAGER@@QEAAJPEAVAPPLICATION@@HH@Z; APPLICATION_MANAGER::ReturnApplication(APPLICATION *,int,int)
0x180006612  test    ebp, ebp
0x180006614  jz      short loc_18000661F
0x180006616  mov     rcx, rsi; lpCriticalSection
0x180006619  call    cs:__imp_LeaveCriticalSection
0x18000661f  test    rdi, rdi
0x180006622  jz      short loc_18000664F
0x180006624  mov     rax, [rdi]
0x180006627  mov     r8d, r12d
0x18000662a  mov     r9, [rbx+158h]
0x180006631  mov     edx, r15d
0x180006634  mov     rcx, rdi
0x180006637  mov     rax, [rax+28h]
0x18000663b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006640  mov     rax, [rdi]
0x180006643  mov     rcx, rdi
0x180006646  mov     rax, [rax+30h]
0x18000664a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664f  add     rsp, 30h
0x180006653  pop     r15
0x180006655  pop     r14
0x180006657  pop     r12
0x180006659  pop     rdi
0x18000665a  pop     rsi
0x18000665b  pop     rbp
0x18000665c  pop     rbx
0x18000665d  retn
```
