# CImplMediaEvent::WaitForCompletion(long,long *)

- ea: `0x1800712d0`
- end: `0x1800714d3`
- name: `?WaitForCompletion@CImplMediaEvent@@UEAAJJPEAJ@Z`
- size: `515`
- prototype: `__int64 __fastcall(CImplMediaEvent *__hidden this, int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004530`
- `0x180013ea0`
- `0x18001d3b0`
- `0x18001ef90`
- `0x18002388c`
- `0x1800274d0`
- `0x1800712d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180071345`
- `KERNEL32!GetTickCount` at `0x1800713f6`
- `KERNEL32!GetTickCount` at `0x180071345`
- `KERNEL32!GetTickCount` at `0x1800713f6`
- `KERNEL32!LeaveCriticalSection` at `0x180071479`
- `KERNEL32!LeaveCriticalSection` at `0x180071479`
- `KERNEL32!EnterCriticalSection` at `0x18007144c`
- `KERNEL32!EnterCriticalSection` at `0x18007144c`
- `USER32!GetWindowThreadProcessId` at `0x180071305`
- `USER32!GetWindowThreadProcessId` at `0x180071305`

## pseudocode

```c
__int64 __fastcall CImplMediaEvent::WaitForCompletion(CImplMediaEvent *this, signed int a2, int *a3)
{
  __int64 result; // rax
  int v6; // ebx
  _QWORD *v7; // r15
  LPVOID *v8; // r12
  unsigned int v9; // r13d
  int v10; // eax
  BOOL v11; // r14d
  unsigned int v12; // eax
  DWORD TickCount; // [rsp+30h] [rbp-20h]
  __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  char v16[8]; // [rsp+48h] [rbp-8h] BYREF
  int v17; // [rsp+90h] [rbp+40h] BYREF
  int *v18; // [rsp+A0h] [rbp+50h]
  unsigned int v19; // [rsp+A8h] [rbp+58h]

  v18 = a3;
  *a3 = 0;
  if ( GetWindowThreadProcessId(*(HWND *)(*((_QWORD *)this + 6) + 504LL), 0) != g_dwObjectThreadId )
    return 2147500033LL;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v19 = 0;
  while ( *(_DWORD *)(*((_QWORD *)this + 6) + 136LL) == 2 )
  {
    TickCount = GetTickCount();
    v10 = WaitDispatchingMessages(*((void **)this + 10), v9, 0, 0, 0);
    if ( (*((_BYTE *)this + 88) & 1) != 0 )
    {
      if ( v10 != 258 )
        goto LABEL_9;
    }
    else
    {
      v14 = 0;
      v15 = 0;
      v17 = 0;
      result = CImplMediaEvent::CEventStore::Collect((CImplMediaEvent *)((char *)this + 56), &v17, &v14, &v15, 0);
      if ( (_DWORD)result != -2147467260 )
      {
        if ( (int)result < 0 )
          return result;
        v6 = v17;
        v7 = (_QWORD *)v14;
        v8 = (LPVOID *)v15;
LABEL_9:
        if ( (*((_BYTE *)this + 88) & 1) != 0 )
          return 0;
        CImplMediaEvent::RealFreeEventParams(v6, v7, v8);
        if ( v6 == 1 || (unsigned int)(v6 - 2) < 2 )
        {
          *v18 = v6;
          return 0;
        }
        goto LABEL_12;
      }
      v6 = v17;
      v7 = (_QWORD *)v14;
      v8 = (LPVOID *)v15;
    }
    CAutoMsgMutex::CAutoMsgMutex((CAutoMsgMutex *)v16, *(struct CMsgMutex **)(*((_QWORD *)this + 6) + 16LL), 0xFFFFFFFF);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    v11 = (int)CFGControl::OutstandingEC_COMPLETEs(*((CFGControl **)this + 6)) > 0 || *((int *)this + 28) > 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)v16);
    if ( !v11 )
      return 2147746343LL;
    v12 = a2;
    if ( v19 )
      v12 = v19;
    v9 = v12;
    v19 = v12;
LABEL_12:
    if ( a2 != -1 )
    {
      a2 = TickCount + a2 - GetTickCount();
      if ( a2 <= 0 )
        return 2147500036LL;
    }
  }
  return 2147746343LL;
}

```

## disassembly

```asm
0x1800712d0  mov     [rsp-38h+arg_8], rbx
0x1800712d5  mov     [rsp-38h+arg_10], r8
0x1800712da  push    rbp
0x1800712db  push    rsi
0x1800712dc  push    rdi
0x1800712dd  push    r12
0x1800712df  push    r13
0x1800712e1  push    r14
0x1800712e3  push    r15
0x1800712e5  mov     rbp, rsp
0x1800712e8  sub     rsp, 50h
0x1800712ec  mov     rdi, rcx
0x1800712ef  mov     dword ptr [r8], 0
0x1800712f6  mov     rcx, [rcx+30h]
0x1800712fa  mov     esi, edx
0x1800712fc  xor     edx, edx; lpdwProcessId
0x1800712fe  mov     rcx, [rcx+1F8h]; hWnd
0x180071305  call    cs:__imp_GetWindowThreadProcessId
0x18007130c  nop     dword ptr [rax+rax+00h]
0x180071311  cmp     eax, cs:?g_dwObjectThreadId@@3KA; ulong g_dwObjectThreadId
0x180071317  jz      short loc_180071323
0x180071319  mov     eax, 80004001h
0x18007131e  jmp     loc_1800714BA
0x180071323  xor     ebx, ebx
0x180071325  xor     r15d, r15d
0x180071328  xor     r12d, r12d
0x18007132b  xor     r13d, r13d
0x18007132e  mov     [rbp+arg_18], r13d
0x180071332  mov     rax, [rdi+30h]
0x180071336  mov     ecx, [rax+88h]
0x18007133c  cmp     ecx, 2
0x18007133f  jnz     loc_1800714B5
0x180071345  call    cs:__imp_GetTickCount
0x18007134c  nop     dword ptr [rax+rax+00h]
0x180071351  mov     rcx, [rdi+50h]; void *
0x180071355  xor     r9d, r9d; unsigned int
0x180071358  xor     r8d, r8d; HWND
0x18007135b  mov     [rbp+var_20], eax
0x18007135e  mov     edx, r13d; unsigned int
0x180071361  mov     qword ptr [rsp+50h+dwMilliseconds], 0; void *
0x18007136a  call    ?WaitDispatchingMessages@@YAKPEAXKPEAUHWND__@@I0@Z; WaitDispatchingMessages(void *,ulong,HWND__ *,uint,void *)
0x18007136f  test    byte ptr [rdi+58h], 1
0x180071373  jnz     loc_180071426
0x180071379  xor     eax, eax
0x18007137b  lea     r9, [rbp+var_10]; __int64 *
0x18007137f  lea     r8, [rbp+var_18]; __int64 *
0x180071383  mov     [rbp+var_18], rax
0x180071387  lea     rdx, [rbp+arg_0]; int *
0x18007138b  mov     [rbp+var_10], rax
0x18007138f  lea     rcx, [rdi+38h]; this
0x180071393  mov     [rbp+arg_0], eax
0x180071396  mov     [rsp+50h+dwMilliseconds], eax; dwMilliseconds
0x18007139a  call    ?Collect@CEventStore@CImplMediaEvent@@QEAAJPEAJPEA_J1J@Z; CImplMediaEvent::CEventStore::Collect(long *,__int64 *,__int64 *,long)
0x18007139f  cmp     eax, 80004004h
0x1800713a4  jz      short loc_180071419
0x1800713a6  test    eax, eax
0x1800713a8  js      loc_1800714BA
0x1800713ae  mov     ebx, [rbp+arg_0]
0x1800713b1  mov     r15, [rbp+var_18]
0x1800713b5  mov     r12, [rbp+var_10]
0x1800713b9  test    byte ptr [rdi+58h], 1
0x1800713bd  jnz     loc_1800714B1
0x1800713c3  mov     r8, r12; __int64
0x1800713c6  mov     rdx, r15; __int64
0x1800713c9  mov     ecx, ebx; int
0x1800713cb  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x1800713d0  mov     ecx, ebx
0x1800713d2  sub     ecx, 1
0x1800713d5  jz      loc_1800714AB
0x1800713db  sub     ecx, 1
0x1800713de  jz      loc_1800714AB
0x1800713e4  cmp     ecx, 1
0x1800713e7  jz      loc_1800714AB
0x1800713ed  cmp     esi, 0FFFFFFFFh
0x1800713f0  jz      loc_180071332
0x1800713f6  call    cs:__imp_GetTickCount
0x1800713fd  nop     dword ptr [rax+rax+00h]
0x180071402  add     esi, [rbp+var_20]
0x180071405  sub     esi, eax
0x180071407  test    esi, esi
0x180071409  jg      loc_180071332
0x18007140f  mov     eax, 80004004h
0x180071414  jmp     loc_1800714BA
0x180071419  mov     ebx, [rbp+arg_0]
0x18007141c  mov     r15, [rbp+var_18]
0x180071420  mov     r12, [rbp+var_10]
0x180071424  jmp     short loc_18007142D
0x180071426  cmp     eax, 102h
0x18007142b  jnz     short loc_1800713B9
0x18007142d  mov     rdx, [rdi+30h]
0x180071431  lea     rcx, [rbp+var_8]; this
0x180071435  or      r8d, 0FFFFFFFFh; unsigned int
0x180071439  mov     rdx, [rdx+10h]; struct CMsgMutex *
0x18007143d  call    ??0CAutoMsgMutex@@QEAA@PEAVCMsgMutex@@K@Z; CAutoMsgMutex::CAutoMsgMutex(CMsgMutex *,ulong)
0x180071442  lea     r13, [rdi+88h]
0x180071449  mov     rcx, r13; lpCriticalSection
0x18007144c  call    cs:__imp_EnterCriticalSection
0x180071453  nop     dword ptr [rax+rax+00h]
0x180071458  mov     rcx, [rdi+30h]; this
0x18007145c  call    ?OutstandingEC_COMPLETEs@CFGControl@@QEAAJXZ; CFGControl::OutstandingEC_COMPLETEs(void)
0x180071461  test    eax, eax
0x180071463  jg      short loc_180071470
0x180071465  cmp     dword ptr [rdi+70h], 0
0x180071469  jg      short loc_180071470
0x18007146b  xor     r14d, r14d
0x18007146e  jmp     short loc_180071476
0x180071470  mov     r14d, 1
0x180071476  mov     rcx, r13; lpCriticalSection
0x180071479  call    cs:__imp_LeaveCriticalSection
0x180071480  nop     dword ptr [rax+rax+00h]
0x180071485  lea     rcx, [rbp+var_8]; this
0x180071489  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x18007148e  test    r14d, r14d
0x180071491  jz      short loc_1800714B5
0x180071493  mov     r13d, [rbp+arg_18]
0x180071497  mov     eax, esi
0x180071499  test    r13d, r13d
0x18007149c  cmovnz  eax, r13d
0x1800714a0  mov     r13d, eax
0x1800714a3  mov     [rbp+arg_18], eax
0x1800714a6  jmp     loc_1800713ED
0x1800714ab  mov     rax, [rbp+arg_10]
0x1800714af  mov     [rax], ebx
0x1800714b1  xor     eax, eax
0x1800714b3  jmp     short loc_1800714BA
0x1800714b5  mov     eax, 80040227h
0x1800714ba  mov     rbx, [rsp+50h+arg_8]
0x1800714c2  add     rsp, 50h
0x1800714c6  pop     r15
0x1800714c8  pop     r14
0x1800714ca  pop     r13
0x1800714cc  pop     r12
0x1800714ce  pop     rdi
0x1800714cf  pop     rsi
0x1800714d0  pop     rbp
0x1800714d1  retn
```
