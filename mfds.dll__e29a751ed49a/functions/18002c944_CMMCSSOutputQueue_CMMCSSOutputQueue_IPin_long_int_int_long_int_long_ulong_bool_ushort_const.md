# CMMCSSOutputQueue::CMMCSSOutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool,ushort const *)

- ea: `0x18002c944`
- end: `0x18002cca5`
- name: `??0CMMCSSOutputQueue@@QEAA@PEAUIPin@@PEAJHHJHJK_NPEBG@Z`
- size: `865`
- prototype: `CMMCSSOutputQueue *__usercall@<rax>(CMMCSSOutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, DWORD ThreadId, int, int, unsigned int, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c6f0`

## callees

- `0x180002820`
- `0x1800140b0`
- `0x18002c944`
- `0x18002d514`
- `0x180037a10`
- `0x180073d0c`
- `0x180073d58`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002c95f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002c95f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c9ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c9ae`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002cbae`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002cbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc59`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002cc1f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002cc1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002cc39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002cc39`

## pseudocode

```c
CMMCSSOutputQueue *__fastcall CMMCSSOutputQueue::CMMCSSOutputQueue(
        CMMCSSOutputQueue *this,
        struct IPin *a2,
        DWORD *a3,
        int a4,
        int a5,
        DWORD ThreadId,
        int a7,
        int a8,
        unsigned int a9,
        bool a10,
        unsigned __int16 *a11)
{
  int v15; // ecx
  BOOL v16; // esi
  int v17; // eax
  HANDLE EventW; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  void *v27; // rax
  HANDLE Semaphore; // rax
  _QWORD *v29; // rax
  int v30; // ecx
  HANDLE v31; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  v15 = ThreadId;
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  v16 = 1;
  if ( !a7 || (v17 = 1, v15 <= 1) )
    v17 = 0;
  *((_DWORD *)this + 15) = v15;
  *((_DWORD *)this + 14) = v17;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = EventW;
  if ( !EventW && a3 && (*a3 & 0x80000000) == 0 )
    *a3 = -2147024882;
  v19 = CallStackTracing::s_wpInstance;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  if ( !v19 )
  {
    CallStackTracing::InitInstance();
    v19 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
    v21 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v21 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v22 = 2 * v21;
      *((_QWORD *)ThreadRelativeContext + v22) = "CMMCSSOutputQueue::CMMCSSOutputQueue";
      *((_DWORD *)ThreadRelativeContext + 2 * v22 + 2) = 85;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids, this);
  if ( (*a3 & 0x80000000) == 0 )
  {
    v24 = StringCchCopyW((unsigned __int16 *)this + 76, 0x100u, a11);
    *a3 = v24;
    if ( v24 >= 0 )
    {
      v25 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IMemInputPin,
              (char *)this + 48);
      *a3 = v25;
      if ( v25 >= 0 )
      {
        if ( a4 )
        {
          v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
          if ( v26 >= 0 )
            v16 = v26 == 0;
        }
        v27 = operator new[](saturated_mul(*((int *)this + 15), 8u));
        *((_QWORD *)this + 12) = v27;
        if ( !v27 )
          goto LABEL_33;
        if ( v16 )
        {
          if ( (unsigned __int8)byte_1800EACCB >= 8u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 11, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids, this);
          Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
          *((_QWORD *)this + 9) = Semaphore;
          if ( !Semaphore )
            goto LABEL_34;
          v29 = operator new(0x28u);
          if ( v29 )
          {
            v30 = a8;
            *v29 = 0;
            v29[1] = 0;
            *((_DWORD *)v29 + 4) = 0;
            *((_DWORD *)v29 + 6) = v30;
            *((_DWORD *)v29 + 7) = 0;
            v29[4] = 0;
            *((_QWORD *)this + 8) = v29;
            ThreadId = 0;
            v31 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CMMCSSOutputQueue::InitialThreadProc, this, 0, &ThreadId);
            *((_QWORD *)this + 11) = v31;
            if ( v31 )
            {
              SetThreadPriority(v31, 0);
              goto LABEL_13;
            }
LABEL_34:
            *a3 = GetLastError() | 0x80070000;
            goto LABEL_13;
          }
          *((_QWORD *)this + 8) = 0;
LABEL_33:
          *a3 = -2147024882;
          goto LABEL_13;
        }
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 12, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids, this);
      }
    }
  }
LABEL_13:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&a10);
  return this;
}

```

## disassembly

```asm
0x18002c944  push    rbx
0x18002c946  push    rbp
0x18002c947  push    rsi
0x18002c948  push    rdi
0x18002c949  push    r12
0x18002c94b  push    r14
0x18002c94d  push    r15
0x18002c94f  sub     rsp, 30h
0x18002c953  mov     ebp, r9d
0x18002c956  mov     rdi, r8
0x18002c959  mov     r15, rdx
0x18002c95c  mov     rbx, rcx
0x18002c95f  call    cs:__imp_InitializeCriticalSection
0x18002c966  nop     dword ptr [rax+rax+00h]
0x18002c96b  mov     ecx, [rsp+68h+ThreadId]
0x18002c972  lea     r14, [rbx+30h]
0x18002c976  xor     r12d, r12d
0x18002c979  mov     [rbx+28h], r15
0x18002c97d  mov     [r14], r12
0x18002c980  lea     esi, [r12+1]
0x18002c985  cmp     [rsp+68h+arg_30], r12d
0x18002c98d  jnz     loc_18002CA6E
0x18002c993  mov     eax, r12d
0x18002c996  mov     [rbx+3Ch], ecx
0x18002c999  xor     r9d, r9d; lpName
0x18002c99c  xor     ecx, ecx; lpEventAttributes
0x18002c99e  mov     [rbx+38h], eax
0x18002c9a1  xor     r8d, r8d; bInitialState
0x18002c9a4  mov     [rbx+40h], r12
0x18002c9a8  xor     edx, edx; bManualReset
0x18002c9aa  mov     [rbx+48h], r12
0x18002c9ae  call    cs:__imp_CreateEventW
0x18002c9b5  nop     dword ptr [rax+rax+00h]
0x18002c9ba  mov     [rbx+50h], rax
0x18002c9be  test    rax, rax
0x18002c9c1  jz      loc_18002CA7D
0x18002c9c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002c9ce  mov     [rbx+58h], r12
0x18002c9d2  mov     [rbx+60h], r12
0x18002c9d6  mov     [rbx+68h], r12
0x18002c9da  mov     [rbx+70h], r12d
0x18002c9de  mov     [rbx+74h], esi
0x18002c9e1  mov     [rbx+78h], r12b
0x18002c9e5  mov     [rbx+7Ch], r12
0x18002c9e9  mov     [rbx+84h], r12d
0x18002c9f0  mov     [rbx+88h], r12
0x18002c9f7  mov     [rbx+90h], r12
0x18002c9fe  test    rcx, rcx
0x18002ca01  jz      loc_18002CA9A
0x18002ca07  cmp     [rcx+8], r12b
0x18002ca0b  jz      short loc_18002CA3C
0x18002ca0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002ca12  mov     ecx, [rax+7C4h]
0x18002ca18  cmp     ecx, [rax+7C8h]
0x18002ca1e  jnb     short loc_18002CA36
0x18002ca20  add     rcx, rcx
0x18002ca23  lea     rdx, aCmmcssoutputqu_4; "CMMCSSOutputQueue::CMMCSSOutputQueue"
0x18002ca2a  mov     [rax+rcx*8], rdx
0x18002ca2e  mov     dword ptr [rax+rcx*8+8], 55h ; 'U'
0x18002ca36  add     [rax+7C4h], esi
0x18002ca3c  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18002ca43  jnb     short loc_18002CAAB
0x18002ca45  cmp     [rdi], r12d
0x18002ca48  jge     loc_18002CAD2
0x18002ca4e  lea     rcx, [rsp+68h+arg_48]; this
0x18002ca56  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002ca5b  mov     rax, rbx
0x18002ca5e  add     rsp, 30h
0x18002ca62  pop     r15
0x18002ca64  pop     r14
0x18002ca66  pop     r12
0x18002ca68  pop     rdi
0x18002ca69  pop     rsi
0x18002ca6a  pop     rbp
0x18002ca6b  pop     rbx
0x18002ca6c  retn
0x18002ca6e  mov     eax, esi
0x18002ca70  cmp     ecx, esi
0x18002ca72  jg      loc_18002C996
0x18002ca78  jmp     loc_18002C993
0x18002ca7d  test    rdi, rdi
0x18002ca80  jz      loc_18002C9C7
0x18002ca86  cmp     [rdi], r12d
0x18002ca89  jl      loc_18002C9C7
0x18002ca8f  mov     dword ptr [rdi], 8007000Eh
0x18002ca95  jmp     loc_18002C9C7
0x18002ca9a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ca9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002caa6  jmp     loc_18002CA07
0x18002caab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cab2  lea     r8, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids
0x18002cab9  mov     edx, 0Ah
0x18002cabe  mov     r9, rbx
0x18002cac1  mov     rcx, [rcx+88h]
0x18002cac8  call    WPP_SF_q
0x18002cacd  jmp     loc_18002CA45
0x18002cad2  mov     r8, [rsp+68h+arg_50]; unsigned __int16 *
0x18002cada  lea     rcx, [rbx+98h]; unsigned __int16 *
0x18002cae1  mov     edx, 100h; unsigned __int64
0x18002cae6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002caeb  mov     [rdi], eax
0x18002caed  test    eax, eax
0x18002caef  js      loc_18002CA4E
0x18002caf5  mov     rax, [r15]
0x18002caf8  lea     rdx, IID_IMemInputPin
0x18002caff  mov     r8, r14
0x18002cb02  mov     rcx, r15
0x18002cb05  mov     rax, [rax]
0x18002cb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb0d  mov     [rdi], eax
0x18002cb0f  test    eax, eax
0x18002cb11  js      loc_18002CA4E
0x18002cb17  test    ebp, ebp
0x18002cb19  jz      short loc_18002CB35
0x18002cb1b  mov     rcx, [r14]
0x18002cb1e  mov     rax, [rcx]
0x18002cb21  mov     rax, [rax+40h]
0x18002cb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb2a  test    eax, eax
0x18002cb2c  js      short loc_18002CB35
0x18002cb2e  mov     esi, r12d
0x18002cb31  setz    sil
0x18002cb35  movsxd  rcx, dword ptr [rbx+3Ch]
0x18002cb39  mov     eax, 8
0x18002cb3e  mul     rcx
0x18002cb41  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cb48  cmovb   rax, rcx
0x18002cb4c  mov     rcx, rax; unsigned __int64
0x18002cb4f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002cb54  mov     [rbx+60h], rax
0x18002cb58  test    rax, rax
0x18002cb5b  jz      loc_18002CC4E
0x18002cb61  test    esi, esi
0x18002cb63  jz      loc_18002CC71
0x18002cb69  cmp     cs:byte_1800EACCB, 8
0x18002cb70  jb      short loc_18002CB94
0x18002cb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb79  lea     r8, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids
0x18002cb80  mov     edx, 0Bh
0x18002cb85  mov     r9, rbx
0x18002cb88  mov     rcx, [rcx+88h]
0x18002cb8f  call    WPP_SF_q
0x18002cb94  mov     [rsp+68h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002cb9c  xor     r9d, r9d; lpName
0x18002cb9f  xor     edx, edx; lInitialCount
0x18002cba1  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x18002cba6  xor     ecx, ecx; lpSemaphoreAttributes
0x18002cba8  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002cbae  call    cs:__imp_CreateSemaphoreExW
0x18002cbb5  nop     dword ptr [rax+rax+00h]
0x18002cbba  mov     [rbx+48h], rax
0x18002cbbe  test    rax, rax
0x18002cbc1  jz      loc_18002CC59
0x18002cbc7  mov     ecx, 28h ; '('; Size
0x18002cbcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cbd1  test    rax, rax
0x18002cbd4  jz      short loc_18002CC4A
0x18002cbd6  mov     ecx, [rsp+68h+arg_38]
0x18002cbdd  lea     r8, ?InitialThreadProc@CMMCSSOutputQueue@@KAKPEAX@Z; lpStartAddress
0x18002cbe4  mov     [rax], r12
0x18002cbe7  mov     r9, rbx; lpParameter
0x18002cbea  mov     [rax+8], r12
0x18002cbee  xor     edx, edx; dwStackSize
0x18002cbf0  mov     [rax+10h], r12d
0x18002cbf4  mov     [rax+18h], ecx
0x18002cbf7  xor     ecx, ecx; lpThreadAttributes
0x18002cbf9  mov     [rax+1Ch], r12d
0x18002cbfd  mov     [rax+20h], r12
0x18002cc01  mov     [rbx+40h], rax
0x18002cc05  lea     rax, [rsp+68h+ThreadId]
0x18002cc0d  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpThreadId
0x18002cc12  mov     [rsp+68h+dwFlags], r12d; dwCreationFlags
0x18002cc17  mov     [rsp+68h+ThreadId], r12d
0x18002cc1f  call    cs:__imp_CreateThread
0x18002cc26  nop     dword ptr [rax+rax+00h]
0x18002cc2b  mov     [rbx+58h], rax
0x18002cc2f  test    rax, rax
0x18002cc32  jz      short loc_18002CC59
0x18002cc34  xor     edx, edx; nPriority
0x18002cc36  mov     rcx, rax; hThread
0x18002cc39  call    cs:__imp_SetThreadPriority
0x18002cc40  nop     dword ptr [rax+rax+00h]
0x18002cc45  jmp     loc_18002CA4E
0x18002cc4a  mov     [rbx+40h], r12
0x18002cc4e  mov     dword ptr [rdi], 8007000Eh
0x18002cc54  jmp     loc_18002CA4E
0x18002cc59  call    cs:__imp_GetLastError
0x18002cc60  nop     dword ptr [rax+rax+00h]
0x18002cc65  or      eax, 80070000h
0x18002cc6a  mov     [rdi], eax
0x18002cc6c  jmp     loc_18002CA4E
0x18002cc71  cmp     cs:byte_1800EACCB, 8
0x18002cc78  jb      loc_18002CA4E
0x18002cc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc85  lea     r8, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids
0x18002cc8c  mov     edx, 0Ch
0x18002cc91  mov     r9, rbx
0x18002cc94  mov     rcx, [rcx+88h]
0x18002cc9b  call    WPP_SF_q
0x18002cca0  jmp     loc_18002CA4E
```
