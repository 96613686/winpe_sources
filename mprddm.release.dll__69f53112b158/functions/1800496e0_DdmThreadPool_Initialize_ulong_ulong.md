# DdmThreadPool::Initialize(ulong,ulong)

- ea: `0x1800496e0`
- end: `0x180049a94`
- name: `?Initialize@DdmThreadPool@@UEAAKKK@Z`
- size: `948`
- prototype: `unsigned int(DdmThreadPool *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007c0c`
- `0x1800496e0`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x1800497c9`
- `KERNEL32!CreateThreadpool` at `0x1800497c9`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180049875`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180049875`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180049935`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180049935`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180049948`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180049948`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180049a17`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180049a17`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180049a26`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180049a26`
- `KERNEL32!CloseThreadpool` at `0x180049a3e`
- `KERNEL32!CloseThreadpool` at `0x180049a3e`
- `KERNEL32!CloseHandle` at `0x180049a57`
- `KERNEL32!CloseHandle` at `0x180049a57`
- `KERNEL32!GetLastError` at `0x1800497e2`
- `KERNEL32!GetLastError` at `0x180049891`
- `KERNEL32!GetLastError` at `0x180049977`
- `KERNEL32!GetLastError` at `0x1800497e2`
- `KERNEL32!GetLastError` at `0x180049891`
- `KERNEL32!GetLastError` at `0x180049977`
- `KERNEL32!CreateEventW` at `0x18004995e`
- `KERNEL32!CreateEventW` at `0x18004995e`

## string_xrefs

- `0x18004973f`: `DdmThreadPool::Initialize() called when helper is already initialized`
- `0x180049802`: `Thread Pool Creation Failed with error = %!WINERROR!`
- `0x1800498b1`: `Thread Pool Cleanup Group creation Failed with error = %!WINERROR!`
- `0x18004999a`: `DdmThreadPool::Initialize: CreateEvent failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::Initialize(DdmThreadPool *this, DWORD a2, DWORD a3)
{
  DWORD v6; // esi
  __int64 v7; // r8
  __int64 v8; // rax
  PTP_POOL Threadpool; // rax
  DWORD v11; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  PTP_CLEANUP_GROUP *v14; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD v16; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  struct _TP_POOL *v19; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v22; // r8
  __int64 v23; // rax
  struct _TP_POOL *v24; // rcx
  void *v25; // rcx
  _BYTE v26[16]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v27; // [rsp+40h] [rbp-C0h]
  int v28; // [rsp+48h] [rbp-B8h]
  int v29; // [rsp+4Ch] [rbp-B4h]
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v30 = 0;
  v6 = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( !*((_DWORD *)this + 24) )
  {
    *((_DWORD *)this + 6) = 3;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    *((_DWORD *)this + 21) = 1;
    *((_DWORD *)this + 22) = 72;
    Threadpool = CreateThreadpool(0);
    *((_QWORD *)this + 1) = Threadpool;
    if ( Threadpool )
    {
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *((_QWORD *)this + 2) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        v19 = (struct _TP_POOL *)*((_QWORD *)this + 1);
        *((_QWORD *)this + 4) = v19;
        *((_QWORD *)this + 5) = ThreadpoolCleanupGroup;
        *((_QWORD *)this + 6) = 0;
        SetThreadpoolThreadMaximum(v19, a2);
        SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 1), a3);
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 13) = EventW;
        if ( EventW )
          goto LABEL_34;
        LastError = GetLastError();
        v14 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
        v6 = LastError;
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(&v30, L"DdmThreadPool::Initialize: CreateEvent failed with 0x%x", LastError);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)&v31[2 * v23 - 4] );
            v29 = 0;
            v28 = 2 * v23 + 2;
            v27 = (const wchar_t *)&v30;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v22, 2, v26);
          }
        }
      }
      else
      {
        v16 = GetLastError();
        v6 = v16;
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(&v30, L"Thread Pool Cleanup Group creation Failed with error = %!WINERROR!", v16);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)&v31[2 * v18 - 4] );
            v29 = 0;
            v28 = 2 * v18 + 2;
            v27 = (const wchar_t *)&v30;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v17, 2, v26);
          }
        }
        v14 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
      }
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v30, L"Thread Pool Creation Failed with error = %!WINERROR!", v11);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&v31[2 * v13 - 4] );
          v29 = 0;
          v28 = 2 * v13 + 2;
          v27 = (const wchar_t *)&v30;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v12, 2, v26);
        }
      }
      v14 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
    }
    if ( v6 )
    {
      if ( *v14 )
      {
        CloseThreadpoolCleanupGroupMembers(*v14, 1, 0);
        CloseThreadpoolCleanupGroup(*v14);
        *v14 = 0;
      }
      v24 = (struct _TP_POOL *)*((_QWORD *)this + 1);
      if ( v24 )
      {
        CloseThreadpool(v24);
        *((_QWORD *)this + 1) = 0;
      }
      v25 = (void *)*((_QWORD *)this + 13);
      if ( v25 )
      {
        CloseHandle(v25);
        *((_QWORD *)this + 13) = 0;
      }
      return v6;
    }
LABEL_34:
    *((_DWORD *)this + 24) = 1;
    return v6;
  }
  if ( (byte_1800CF404 & 8) != 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( aDdmthreadpoolI[v8] );
    v27 = L"DdmThreadPool::Initialize() called when helper is already initialized";
    v28 = 2 * v8 + 2;
    v29 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v7, 2, v26);
  }
  return 4317;
}

```

## disassembly

```asm
0x1800496e0  push    rbp
0x1800496e2  push    rbx
0x1800496e3  push    rsi
0x1800496e4  push    rdi
0x1800496e5  push    r12
0x1800496e7  push    r14
0x1800496e9  push    r15
0x1800496eb  lea     rbp, [rsp-760h]
0x1800496f3  sub     rsp, 860h
0x1800496fa  mov     rax, cs:__security_cookie
0x180049701  xor     rax, rsp
0x180049704  mov     [rbp+790h+var_40], rax
0x18004970b  mov     r15d, r8d
0x18004970e  mov     edi, edx
0x180049710  mov     rbx, rcx
0x180049713  xor     r12d, r12d
0x180049716  xor     edx, edx; Val
0x180049718  mov     [rsp+890h+var_840], r12d
0x18004971d  mov     r8d, 7FCh; Size
0x180049723  lea     rcx, [rsp+890h+var_83C]; void *
0x180049728  mov     esi, r12d
0x18004972b  call    memset_0
0x180049730  cmp     [rbx+60h], r12d
0x180049734  jz      short loc_180049796
0x180049736  test    cs:byte_1800CF404, 8
0x18004973d  jz      short loc_18004978C
0x18004973f  lea     rcx, aDdmthreadpoolI; "DdmThreadPool::Initialize() called when"...
0x180049746  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004974a  inc     rax
0x18004974d  cmp     [rcx+rax*2], r12w
0x180049752  jnz     short loc_18004974A
0x180049754  lea     eax, ds:2[rax*2]
0x18004975b  mov     [rsp+890h+var_850], rcx
0x180049760  mov     [rsp+890h+var_848], eax
0x180049764  lea     rdx, RasDdmTraceError
0x18004976b  lea     rax, [rsp+890h+var_860]
0x180049770  mov     [rsp+890h+var_844], r12d
0x180049775  mov     r9d, 2
0x18004977b  mov     [rsp+890h+var_870], rax
0x180049780  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049787  call    McGenEventWrite_EventWriteTransfer
0x18004978c  mov     eax, 10DDh
0x180049791  jmp     loc_180049A72
0x180049796  xor     ecx, ecx; reserved
0x180049798  mov     dword ptr [rbx+18h], 3
0x18004979f  mov     [rbx+20h], r12
0x1800497a3  mov     [rbx+28h], r12
0x1800497a7  mov     [rbx+30h], r12
0x1800497ab  mov     [rbx+38h], r12
0x1800497af  mov     [rbx+40h], r12
0x1800497b3  mov     [rbx+48h], r12
0x1800497b7  mov     [rbx+50h], r12d
0x1800497bb  mov     dword ptr [rbx+54h], 1
0x1800497c2  mov     dword ptr [rbx+58h], 48h ; 'H'
0x1800497c9  call    cs:__imp_CreateThreadpool
0x1800497d0  nop     dword ptr [rax+rax+00h]
0x1800497d5  mov     [rbx+8], rax
0x1800497d9  test    rax, rax
0x1800497dc  jnz     loc_180049875
0x1800497e2  call    cs:__imp_GetLastError
0x1800497e9  nop     dword ptr [rax+rax+00h]
0x1800497ee  test    cs:byte_1800CF404, 8
0x1800497f5  mov     esi, eax
0x1800497f7  jz      short loc_18004986C
0x1800497f9  mov     r8d, eax
0x1800497fc  mov     word ptr [rsp+890h+var_840], r12w
0x180049802  lea     rdx, aThreadPoolCrea; "Thread Pool Creation Failed with error "...
0x180049809  lea     rcx, [rsp+890h+var_840]
0x18004980e  call    FormatRRASErrorString
0x180049813  test    cs:byte_1800CF404, 8
0x18004981a  jz      short loc_18004986C
0x18004981c  lea     rcx, [rsp+890h+var_840]
0x180049821  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049825  inc     rax
0x180049828  cmp     [rcx+rax*2], r12w
0x18004982d  jnz     short loc_180049825
0x18004982f  lea     eax, ds:2[rax*2]
0x180049836  mov     [rsp+890h+var_844], r12d
0x18004983b  lea     rcx, [rsp+890h+var_840]
0x180049840  mov     [rsp+890h+var_848], eax
0x180049844  lea     rax, [rsp+890h+var_860]
0x180049849  mov     [rsp+890h+var_850], rcx
0x18004984e  mov     r9d, 2
0x180049854  mov     [rsp+890h+var_870], rax
0x180049859  lea     rdx, RasDdmTraceError
0x180049860  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049867  call    McGenEventWrite_EventWriteTransfer
0x18004986c  lea     rdi, [rbx+10h]
0x180049870  jmp     loc_180049A04
0x180049875  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004987c  nop     dword ptr [rax+rax+00h]
0x180049881  lea     r14, [rbx+10h]
0x180049885  mov     [r14], rax
0x180049888  test    rax, rax
0x18004988b  jnz     loc_180049923
0x180049891  call    cs:__imp_GetLastError
0x180049898  nop     dword ptr [rax+rax+00h]
0x18004989d  test    cs:byte_1800CF404, 8
0x1800498a4  mov     esi, eax
0x1800498a6  jz      short loc_18004991B
0x1800498a8  mov     r8d, eax
0x1800498ab  mov     word ptr [rsp+890h+var_840], r12w
0x1800498b1  lea     rdx, aThreadPoolClea; "Thread Pool Cleanup Group creation Fail"...
0x1800498b8  lea     rcx, [rsp+890h+var_840]
0x1800498bd  call    FormatRRASErrorString
0x1800498c2  test    cs:byte_1800CF404, 8
0x1800498c9  jz      short loc_18004991B
0x1800498cb  lea     rcx, [rsp+890h+var_840]
0x1800498d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800498d4  inc     rax
0x1800498d7  cmp     [rcx+rax*2], r12w
0x1800498dc  jnz     short loc_1800498D4
0x1800498de  lea     eax, ds:2[rax*2]
0x1800498e5  mov     [rsp+890h+var_844], r12d
0x1800498ea  lea     rcx, [rsp+890h+var_840]
0x1800498ef  mov     [rsp+890h+var_848], eax
0x1800498f3  lea     rax, [rsp+890h+var_860]
0x1800498f8  mov     [rsp+890h+var_850], rcx
0x1800498fd  mov     r9d, 2
0x180049903  mov     [rsp+890h+var_870], rax
0x180049908  lea     rdx, RasDdmTraceError
0x18004990f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049916  call    McGenEventWrite_EventWriteTransfer
0x18004991b  mov     rdi, r14
0x18004991e  jmp     loc_180049A04
0x180049923  mov     rcx, [rbx+8]; ptpp
0x180049927  mov     edx, edi; cthrdMost
0x180049929  mov     [rbx+20h], rcx
0x18004992d  mov     [rbx+28h], rax
0x180049931  mov     [rbx+30h], r12
0x180049935  call    cs:__imp_SetThreadpoolThreadMaximum
0x18004993c  nop     dword ptr [rax+rax+00h]
0x180049941  mov     rcx, [rbx+8]; ptpp
0x180049945  mov     edx, r15d; cthrdMic
0x180049948  call    cs:__imp_SetThreadpoolThreadMinimum
0x18004994f  nop     dword ptr [rax+rax+00h]
0x180049954  xor     r9d, r9d; lpName
0x180049957  xor     r8d, r8d; bInitialState
0x18004995a  xor     edx, edx; bManualReset
0x18004995c  xor     ecx, ecx; lpEventAttributes
0x18004995e  call    cs:__imp_CreateEventW
0x180049965  nop     dword ptr [rax+rax+00h]
0x18004996a  mov     [rbx+68h], rax
0x18004996e  test    rax, rax
0x180049971  jnz     loc_180049A69
0x180049977  call    cs:__imp_GetLastError
0x18004997e  nop     dword ptr [rax+rax+00h]
0x180049983  test    cs:byte_1800CF404, 8
0x18004998a  mov     rdi, r14
0x18004998d  mov     esi, eax
0x18004998f  jz      short loc_180049A04
0x180049991  mov     r8d, eax
0x180049994  mov     word ptr [rsp+890h+var_840], r12w
0x18004999a  lea     rdx, aDdmthreadpoolI_0; "DdmThreadPool::Initialize: CreateEvent "...
0x1800499a1  lea     rcx, [rsp+890h+var_840]
0x1800499a6  call    FormatRRASErrorString
0x1800499ab  test    cs:byte_1800CF404, 8
0x1800499b2  jz      short loc_180049A04
0x1800499b4  lea     rcx, [rsp+890h+var_840]
0x1800499b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800499bd  inc     rax
0x1800499c0  cmp     [rcx+rax*2], r12w
0x1800499c5  jnz     short loc_1800499BD
0x1800499c7  lea     eax, ds:2[rax*2]
0x1800499ce  mov     [rsp+890h+var_844], r12d
0x1800499d3  lea     rcx, [rsp+890h+var_840]
0x1800499d8  mov     [rsp+890h+var_848], eax
0x1800499dc  lea     rax, [rsp+890h+var_860]
0x1800499e1  mov     [rsp+890h+var_850], rcx
0x1800499e6  mov     r9d, 2
0x1800499ec  mov     [rsp+890h+var_870], rax
0x1800499f1  lea     rdx, RasDdmTraceError
0x1800499f8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800499ff  call    McGenEventWrite_EventWriteTransfer
0x180049a04  test    esi, esi
0x180049a06  jz      short loc_180049A69
0x180049a08  mov     rcx, [rdi]; ptpcg
0x180049a0b  test    rcx, rcx
0x180049a0e  jz      short loc_180049A35
0x180049a10  xor     r8d, r8d; pvCleanupContext
0x180049a13  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180049a17  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180049a1e  nop     dword ptr [rax+rax+00h]
0x180049a23  mov     rcx, [rdi]; ptpcg
0x180049a26  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180049a2d  nop     dword ptr [rax+rax+00h]
0x180049a32  mov     [rdi], r12
0x180049a35  mov     rcx, [rbx+8]; ptpp
0x180049a39  test    rcx, rcx
0x180049a3c  jz      short loc_180049A4E
0x180049a3e  call    cs:__imp_CloseThreadpool
0x180049a45  nop     dword ptr [rax+rax+00h]
0x180049a4a  mov     [rbx+8], r12
0x180049a4e  mov     rcx, [rbx+68h]; hObject
0x180049a52  test    rcx, rcx
0x180049a55  jz      short loc_180049A70
0x180049a57  call    cs:__imp_CloseHandle
0x180049a5e  nop     dword ptr [rax+rax+00h]
0x180049a63  mov     [rbx+68h], r12
0x180049a67  jmp     short loc_180049A70
0x180049a69  mov     dword ptr [rbx+60h], 1
0x180049a70  mov     eax, esi
0x180049a72  mov     rcx, [rbp+790h+var_40]
0x180049a79  xor     rcx, rsp; StackCookie
0x180049a7c  call    __security_check_cookie
0x180049a81  add     rsp, 860h
0x180049a88  pop     r15
0x180049a8a  pop     r14
0x180049a8c  pop     r12
0x180049a8e  pop     rdi
0x180049a8f  pop     rsi
0x180049a90  pop     rbx
0x180049a91  pop     rbp
0x180049a92  retn
```
