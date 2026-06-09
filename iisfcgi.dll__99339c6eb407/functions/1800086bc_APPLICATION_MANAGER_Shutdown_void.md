# APPLICATION_MANAGER::Shutdown(void)

- ea: `0x1800086bc`
- end: `0x18000883d`
- name: `?Shutdown@APPLICATION_MANAGER@@QEAAJXZ`
- size: `385`
- prototype: `__int64 __fastcall(APPLICATION_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c00`

## callees

- `0x180005030`
- `0x180005f4c`
- `0x180008164`
- `0x1800086bc`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000879e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000879e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000873a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000873a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087f6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180008807`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180008807`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::Shutdown(APPLICATION_MANAGER *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // ebx
  bool v4; // zf
  char *v5; // r14
  __int64 *v6; // rbx
  __int64 v7; // rax
  _QWORD **v8; // r14
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  signed int LastError; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 36) )
  {
    v3 = -2147023901;
    LeaveCriticalSection(v1);
  }
  else
  {
    v4 = *((_DWORD *)this + 34) == 0;
    *((_DWORD *)this + 36) = 1;
    if ( !v4 )
    {
      v5 = (char *)this + 120;
      do
      {
        v6 = *(__int64 **)v5;
        if ( *(char **)(*(_QWORD *)v5 + 8LL) != v5 || (v7 = *v6, *(__int64 **)(*v6 + 8) != v6) )
LABEL_13:
          __fastfail(3u);
        *(_QWORD *)v5 = v7;
        *(_QWORD *)(v7 + 8) = v5;
        --*((_DWORD *)this + 34);
        _InterlockedDecrement(&APPLICATION_MANAGER::sm_lTotalQueueLength);
        LeaveCriticalSection(v1);
        (*(void (__fastcall **)(__int64 *, _QWORD, __int64, __int64))(*(v6 - 1) + 8))(v6 - 1, 0, 2147942438LL, 200008);
        (*(void (__fastcall **)(__int64 *))(*(v6 - 1) + 16))(v6 - 1);
        EnterCriticalSection(v1);
      }
      while ( *((_DWORD *)this + 34) );
    }
    LeaveCriticalSection(v1);
    APPLICATION_MANAGER::Recycle(this, 1, 1);
    EnterCriticalSection(v1);
    v8 = (_QWORD **)((char *)this + 104);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v9[1] != v8 )
        goto LABEL_13;
      v10 = (_QWORD *)*v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 )
        goto LABEL_13;
      *v8 = v10;
      v10[1] = v8;
      LeaveCriticalSection(v1);
      APPLICATION::Kill((APPLICATION *)(v9 - 3));
      APPLICATION::DereferenceApplication((APPLICATION *)(v9 - 3));
      EnterCriticalSection(v1);
    }
    LeaveCriticalSection(v1);
    if ( DeleteTimerQueueEx(*((HANDLE *)this + 19), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v3 = 0;
      *((_QWORD *)this + 19) = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800086bc  push    rbx
0x1800086be  push    rsi
0x1800086bf  push    rdi
0x1800086c0  push    r14
0x1800086c2  sub     rsp, 38h
0x1800086c6  lea     rsi, [rcx+10h]
0x1800086ca  mov     rdi, rcx
0x1800086cd  mov     rcx, rsi; lpCriticalSection
0x1800086d0  call    cs:__imp_EnterCriticalSection
0x1800086d6  cmp     dword ptr [rdi+90h], 0
0x1800086dd  jz      short loc_1800086F2
0x1800086df  mov     rcx, rsi; lpCriticalSection
0x1800086e2  mov     ebx, 800703E3h
0x1800086e7  call    cs:__imp_LeaveCriticalSection
0x1800086ed  jmp     loc_180008831
0x1800086f2  cmp     dword ptr [rdi+88h], 0
0x1800086f9  mov     dword ptr [rdi+90h], 1
0x180008703  jbe     short loc_180008782
0x180008705  lea     r14, [rdi+78h]
0x180008709  mov     rbx, [r14]
0x18000870c  cmp     [rbx+8], r14
0x180008710  jnz     loc_1800087EC
0x180008716  mov     rax, [rbx]
0x180008719  cmp     [rax+8], rbx
0x18000871d  jnz     loc_1800087EC
0x180008723  mov     [r14], rax
0x180008726  mov     rcx, rsi; lpCriticalSection
0x180008729  mov     [rax+8], r14
0x18000872d  dec     dword ptr [rdi+88h]
0x180008733  lock dec cs:?sm_lTotalQueueLength@APPLICATION_MANAGER@@0JA; long APPLICATION_MANAGER::sm_lTotalQueueLength
0x18000873a  call    cs:__imp_LeaveCriticalSection
0x180008740  mov     rax, [rbx-8]
0x180008744  lea     rcx, [rbx-8]
0x180008748  xor     edx, edx
0x18000874a  mov     r9d, 30D48h
0x180008750  mov     r8d, 80070026h
0x180008756  mov     rax, [rax+8]
0x18000875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875f  mov     rax, [rbx-8]
0x180008763  lea     rcx, [rbx-8]
0x180008767  mov     rax, [rax+10h]
0x18000876b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008770  mov     rcx, rsi; lpCriticalSection
0x180008773  call    cs:__imp_EnterCriticalSection
0x180008779  cmp     dword ptr [rdi+88h], 0
0x180008780  ja      short loc_180008709
0x180008782  mov     rcx, rsi; lpCriticalSection
0x180008785  call    cs:__imp_LeaveCriticalSection
0x18000878b  mov     edx, 1; int
0x180008790  mov     rcx, rdi; this
0x180008793  mov     r8d, edx; int
0x180008796  call    ?Recycle@APPLICATION_MANAGER@@AEAAXHH@Z; APPLICATION_MANAGER::Recycle(int,int)
0x18000879b  mov     rcx, rsi; lpCriticalSection
0x18000879e  call    cs:__imp_EnterCriticalSection
0x1800087a4  lea     r14, [rdi+68h]
0x1800087a8  mov     rbx, [r14]
0x1800087ab  cmp     rbx, r14
0x1800087ae  jz      short loc_1800087F3
0x1800087b0  cmp     [rbx+8], r14
0x1800087b4  jnz     short loc_1800087EC
0x1800087b6  mov     rax, [rbx]
0x1800087b9  cmp     [rax+8], rbx
0x1800087bd  jnz     short loc_1800087EC
0x1800087bf  mov     [r14], rax
0x1800087c2  mov     rcx, rsi; lpCriticalSection
0x1800087c5  mov     [rax+8], r14
0x1800087c9  call    cs:__imp_LeaveCriticalSection
0x1800087cf  lea     rcx, [rbx-18h]; this
0x1800087d3  call    ?Kill@APPLICATION@@QEAAXXZ; APPLICATION::Kill(void)
0x1800087d8  lea     rcx, [rbx-18h]; this
0x1800087dc  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x1800087e1  mov     rcx, rsi; lpCriticalSection
0x1800087e4  call    cs:__imp_EnterCriticalSection
0x1800087ea  jmp     short loc_1800087A8
0x1800087ec  mov     ecx, 3
0x1800087f1  int     29h; Win8: RtlFailFast(ecx)
0x1800087f3  mov     rcx, rsi; lpCriticalSection
0x1800087f6  call    cs:__imp_LeaveCriticalSection
0x1800087fc  mov     rcx, [rdi+98h]; TimerQueue
0x180008803  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180008807  call    cs:__imp_DeleteTimerQueueEx
0x18000880d  test    eax, eax
0x18000880f  jnz     short loc_180008828
0x180008811  call    cs:__imp_GetLastError
0x180008817  mov     ebx, eax
0x180008819  test    eax, eax
0x18000881b  jle     short loc_180008831
0x18000881d  movzx   ebx, ax
0x180008820  or      ebx, 80070000h
0x180008826  jmp     short loc_180008831
0x180008828  xor     ebx, ebx
0x18000882a  mov     [rdi+98h], rbx
0x180008831  mov     eax, ebx
0x180008833  add     rsp, 38h
0x180008837  pop     r14
0x180008839  pop     rdi
0x18000883a  pop     rsi
0x18000883b  pop     rbx
0x18000883c  retn
```
