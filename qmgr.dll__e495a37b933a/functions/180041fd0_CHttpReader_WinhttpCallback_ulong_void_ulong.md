# CHttpReader::WinhttpCallback(ulong,void *,ulong)

- ea: `0x180041fd0`
- end: `0x180042552`
- name: `?WinhttpCallback@CHttpReader@@UEAAXKPEAXK@Z`
- size: `1410`
- prototype: `void __fastcall(CHttpReader *__hidden this, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180033480`
- `0x180041fd0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a7558`
- `0x1800ab7fc`
- `0x1800bd044`
- `0x1800beaec`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800420d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004222e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800420d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004222e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800420e0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004223c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800420e0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004223c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004242c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004242c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004203b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004203b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042093`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004229a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004229a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800420c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800420f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800420c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800420f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall CHttpReader::WinhttpCallback(HANDLE *this, int a2, unsigned int *a3, unsigned int a4)
{
  EVENT_LOG *v8; // rcx
  __int64 v9; // r8
  HANDLE *v10; // r14
  EVENT_LOG *v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  char v13; // bl
  HANDLE CurrentThread; // rax
  int v15; // eax
  EVENT_LOG *v16; // rcx
  HANDLE v17; // rax
  DWORD v18; // eax
  DWORD LastError; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  unsigned int *v24; // rdx
  __int64 v25; // rdx
  char v26[8]; // [rsp+30h] [rbp-A8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-A0h]
  ULONGLONG TickCount64; // [rsp+40h] [rbp-98h]

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, this - 38, a2);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 == 2048 )
  {
    if ( v8 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 )
      WPP_SF_q(*((_QWORD *)v8 + 2), 61, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, this - 38);
    if ( !SetEvent(this[54]) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, LastError);
    }
    return;
  }
  v26[0] = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(this - 37);
  if ( *((_BYTE *)this - 256) && v8 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)v8 + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, this - 37);
  EnterCriticalSection((LPCRITICAL_SECTION)(this - 37));
  v26[0] = 1;
  if ( a2 == 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, *a3);
    *((_DWORD *)this + 65706) = MapSecureHttpErrorCode(*a3);
    HoldCritSec::~HoldCritSec((HoldCritSec *)v26);
    return;
  }
  v10 = this - 38;
  if ( !this[45] || *((_BYTE *)this + 262829) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = lpCriticalSection;
    if ( !LOBYTE(lpCriticalSection[1].DebugInfo)
      || v11 == (EVENT_LOG *)&WPP_GLOBAL_Control
      || (*((_DWORD *)v11 + 7) & 0x100) == 0 )
    {
      goto LABEL_9;
    }
LABEL_77:
    WPP_SF_q(*((_QWORD *)v11 + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v12);
LABEL_9:
    LeaveCriticalSection(v12);
    return;
  }
  v13 = 0;
  if ( *((_BYTE *)this - 184) )
  {
    TickCount64 = GetTickCount64();
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      v13 = 1;
      v15 = GetTickCount64();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = v15 - TickCount64;
      v22 = 51;
LABEL_62:
      WPP_SF_d(*((_QWORD *)v16 + 2), v22, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v21);
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = GetLastError();
      v22 = 50;
      v16 = WPP_GLOBAL_Control;
      goto LABEL_62;
    }
  }
LABEL_14:
  if ( a2 != 0x80000 )
  {
    switch ( a2 )
    {
      case 0x40000:
        (*((void (__fastcall **)(char *, _QWORD))*v10 + 66))((char *)this - 304, *a3);
        goto LABEL_24;
      case 0x20000:
        (*((void (__fastcall **)(char *))*v10 + 63))((char *)this - 304);
        goto LABEL_24;
      case 0x10:
        (*((void (__fastcall **)(char *, char *))this[27] + 1))((char *)this + 216, v26);
        goto LABEL_24;
      case 0x4000:
        (*((void (__fastcall **)(char *, unsigned int *))*v10 + 65))((char *)this - 304, a3);
        goto LABEL_24;
    }
    if ( a2 != 0x200000 )
    {
      if ( a2 == 0x400000 && !(*(unsigned int (__fastcall **)(HANDLE))(*(_QWORD *)v10[83] + 72LL))(v10[83]) )
      {
        v20 = GetLastError();
        CHttpReader::DealWithSendError((CHttpReader *)(this - 38), v20);
      }
      goto LABEL_24;
    }
    v23 = a3[2];
    if ( v23 == 12017 )
    {
      v23 = 12002;
    }
    else if ( v23 == 12175 )
    {
      v24 = (unsigned int *)(this + 32853);
LABEL_69:
      v25 = *v24;
      if ( *((_DWORD *)this + 82) == 1 )
      {
        CHttpReader::DealWithSendError((CHttpReader *)(this - 38), v25);
      }
      else
      {
        if ( (int)v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        (*((void (__fastcall **)(char *, __int64, _QWORD, __int64))v10[65] + 7))((char *)this + 216, v25, 0, 5);
      }
      goto LABEL_24;
    }
    v24 = (unsigned int *)(this + 32853);
    *((_DWORD *)this + 65706) = v23;
    goto LABEL_69;
  }
  if ( !a4 )
    *((_BYTE *)this + 262793) = 1;
  LOBYTE(v9) = 1;
  (*((void (__fastcall **)(char *, _QWORD, __int64))*v10 + 67))((char *)this - 304, a4, v9);
LABEL_24:
  (*((void (__fastcall **)(char *))*v10 + 73))((char *)this - 304);
  if ( !v13 )
    goto LABEL_25;
  v17 = GetCurrentThread();
  if ( SetThreadPriority(v17, 0x20000) )
    goto LABEL_25;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v18 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v18);
LABEL_25:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v26[0] )
  {
    v12 = lpCriticalSection;
    if ( !LOBYTE(lpCriticalSection[1].DebugInfo)
      || v11 == (EVENT_LOG *)&WPP_GLOBAL_Control
      || (*((_DWORD *)v11 + 7) & 0x100) == 0 )
    {
      goto LABEL_9;
    }
    goto LABEL_77;
  }
}

```

## disassembly

```asm
0x180041fd0  mov     [rsp+arg_10], rbx
0x180041fd5  mov     [rsp+arg_18], rsi
0x180041fda  mov     [rsp+arg_0], rcx
0x180041fdf  push    rdi
0x180041fe0  push    r12
0x180041fe2  push    r13
0x180041fe4  push    r14
0x180041fe6  push    r15
0x180041fe8  sub     rsp, 0B0h
0x180041fef  mov     r12d, r9d
0x180041ff2  mov     r13, r8
0x180041ff5  mov     esi, edx
0x180041ff7  mov     rdi, rcx
0x180041ffa  lea     r15, WPP_GLOBAL_Control
0x180042001  mov     rcx, cs:WPP_GLOBAL_Control
0x180042008  cmp     rcx, r15
0x18004200b  jnz     loc_180042155
0x180042011  cmp     esi, 800h
0x180042017  jz      loc_18004228A
0x18004201d  mov     [rsp+0D8h+var_A8], 0
0x180042022  lea     rbx, [rdi-128h]
0x180042029  mov     [rsp+0D8h+lpCriticalSection], rbx
0x18004202e  cmp     byte ptr [rbx+28h], 0
0x180042032  jnz     loc_180042396
0x180042038  mov     rcx, rbx; lpCriticalSection
0x18004203b  call    cs:__imp_EnterCriticalSection
0x180042041  mov     al, 1
0x180042043  mov     [rsp+0D8h+var_A8], al
0x180042047  cmp     esi, 10000h
0x18004204d  jz      loc_1800423C9
0x180042053  lea     r14, [rdi-130h]
0x18004205a  cmp     qword ptr [r14+298h], 0
0x180042062  jz      short loc_18004206D
0x180042064  cmp     byte ptr [rdi+402ADh], 0
0x18004206b  jz      short loc_1800420B6
0x18004206d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042074  cmp     rcx, r15
0x180042077  jnz     loc_1800424EC
0x18004207d  test    al, al
0x18004207f  jz      short loc_180042099
0x180042081  mov     rbx, [rsp+0D8h+lpCriticalSection]
0x180042086  cmp     byte ptr [rbx+28h], 0
0x18004208a  jnz     loc_18004251F
0x180042090  mov     rcx, rbx; lpCriticalSection
0x180042093  call    cs:__imp_LeaveCriticalSection
0x180042099  lea     r11, [rsp+0D8h+var_28]
0x1800420a1  mov     rbx, [r11+40h]
0x1800420a5  mov     rsi, [r11+48h]
0x1800420a9  mov     rsp, r11
0x1800420ac  pop     r15
0x1800420ae  pop     r14
0x1800420b0  pop     r13
0x1800420b2  pop     r12
0x1800420b4  pop     rdi
0x1800420b5  retn
0x1800420b6  xor     bl, bl
0x1800420b8  mov     [rsp+0D8h+arg_8], bl
0x1800420bf  cmp     [rdi-0B8h], bl
0x1800420c5  jz      short loc_180042112
0x1800420c7  call    cs:__imp_GetTickCount64
0x1800420cd  mov     [rsp+0D8h+var_98], rax
0x1800420d2  call    cs:__imp_GetCurrentThread
0x1800420d8  mov     rcx, rax; hThread
0x1800420db  mov     edx, 10000h; nPriority
0x1800420e0  call    cs:__imp_SetThreadPriority
0x1800420e6  test    eax, eax
0x1800420e8  jz      loc_180042412
0x1800420ee  mov     bl, 1
0x1800420f0  mov     [rsp+0D8h+arg_8], bl
0x1800420f7  call    cs:__imp_GetTickCount64
0x1800420fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180042104  cmp     rcx, r15
0x180042107  jz      short loc_180042112
0x180042109  test    [rcx+1Ch], bl
0x18004210c  jnz     loc_180042440
0x180042112  cmp     esi, 80000h
0x180042118  jz      short loc_18004218E
0x18004211a  cmp     esi, 40000h
0x180042120  jz      loc_180042202
0x180042126  cmp     esi, 20000h
0x18004212c  jz      loc_18004221A
0x180042132  cmp     esi, 10h
0x180042135  jnz     loc_1800422E5
0x18004213b  lea     rcx, [rdi+0D8h]
0x180042142  mov     rax, [rcx]
0x180042145  lea     rdx, [rsp+0D8h+var_A8]
0x18004214a  mov     rax, [rax+8]
0x18004214e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042153  jmp     short loc_1800421AF
0x180042155  test    dword ptr [rcx+1Ch], 800h
0x18004215c  jz      loc_180042011
0x180042162  lea     r9, [rdi-130h]
0x180042169  mov     edx, 3Ch ; '<'
0x18004216e  mov     [rsp+0D8h+var_B8], esi
0x180042172  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180042179  mov     rcx, [rcx+10h]
0x18004217d  call    WPP_SF_qD
0x180042182  mov     rcx, cs:WPP_GLOBAL_Control
0x180042189  jmp     loc_180042011
0x18004218e  test    r12d, r12d
0x180042191  jz      loc_1800424CD
0x180042197  mov     rax, [r14]
0x18004219a  mov     r8b, 1
0x18004219d  mov     edx, r12d
0x1800421a0  mov     rcx, r14
0x1800421a3  mov     rax, [rax+218h]
0x1800421aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421af  mov     rax, [r14]
0x1800421b2  mov     rcx, r14
0x1800421b5  mov     rax, [rax+248h]
0x1800421bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421c1  nop
0x1800421c2  test    bl, bl
0x1800421c4  jnz     short loc_18004222E
0x1800421c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421cd  cmp     [rsp+0D8h+var_A8], 0
0x1800421d2  jz      loc_180042099
0x1800421d8  mov     rbx, [rsp+0D8h+lpCriticalSection]
0x1800421dd  cmp     byte ptr [rbx+28h], 0
0x1800421e1  jz      loc_180042090
0x1800421e7  cmp     rcx, r15
0x1800421ea  jz      loc_180042090
0x1800421f0  test    dword ptr [rcx+1Ch], 100h
0x1800421f7  jz      loc_180042090
0x1800421fd  jmp     loc_180042535
0x180042202  mov     rax, [r14]
0x180042205  mov     edx, [r13+0]
0x180042209  mov     rcx, r14
0x18004220c  mov     rax, [rax+210h]
0x180042213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042218  jmp     short loc_1800421AF
0x18004221a  mov     rax, [r14]
0x18004221d  mov     rcx, r14
0x180042220  mov     rax, [rax+1F8h]
0x180042227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004222c  jmp     short loc_1800421AF
0x18004222e  call    cs:__imp_GetCurrentThread
0x180042234  mov     rcx, rax; hThread
0x180042237  mov     edx, 20000h; nPriority
0x18004223c  call    cs:__imp_SetThreadPriority
0x180042242  test    eax, eax
0x180042244  jnz     short loc_1800421C6
0x180042246  mov     rcx, cs:WPP_GLOBAL_Control
0x18004224d  cmp     rcx, r15
0x180042250  jz      loc_1800421CD
0x180042256  test    byte ptr [rcx+1Ch], 2
0x18004225a  jz      loc_1800421CD
0x180042260  call    cs:__imp_GetLastError
0x180042266  mov     edx, 34h ; '4'
0x18004226b  mov     r9d, eax
0x18004226e  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180042275  mov     rcx, cs:WPP_GLOBAL_Control
0x18004227c  mov     rcx, [rcx+10h]
0x180042280  call    WPP_SF_d
0x180042285  jmp     loc_1800421C6
0x18004228a  cmp     rcx, r15
0x18004228d  jnz     loc_180042368
0x180042293  mov     rcx, [rdi+1B0h]; hEvent
0x18004229a  call    cs:__imp_SetEvent
0x1800422a0  test    eax, eax
0x1800422a2  jnz     loc_180042099
0x1800422a8  call    cs:__imp_GetLastError
0x1800422ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422b5  cmp     rcx, r15
0x1800422b8  jz      loc_180042099
0x1800422be  test    byte ptr [rcx+1Ch], 4
0x1800422c2  jz      loc_180042099
0x1800422c8  mov     edx, 0Ah
0x1800422cd  mov     r9d, eax
0x1800422d0  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800422d7  mov     rcx, [rcx+10h]
0x1800422db  call    WPP_SF_d
0x1800422e0  jmp     loc_180042099
0x1800422e5  cmp     esi, 4000h
0x1800422eb  jnz     loc_180042461
0x1800422f1  mov     rax, [r14]
0x1800422f4  mov     rdx, r13
0x1800422f7  mov     rcx, r14
0x1800422fa  mov     rax, [rax+208h]
0x180042301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042306  jmp     loc_1800421AF
0x18004230b  mov     rcx, [r14+298h]
0x180042312  mov     rax, [rcx]
0x180042315  mov     rax, [rax+48h]
0x180042319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004231e  test    eax, eax
0x180042320  jnz     loc_1800421AF
0x180042326  call    cs:__imp_GetLastError
0x18004232c  mov     edx, eax; unsigned int
0x18004232e  mov     rcx, r14; this
0x180042331  call    ?DealWithSendError@CHttpReader@@IEAAXK@Z; CHttpReader::DealWithSendError(ulong)
0x180042336  jmp     loc_1800421AF
0x18004233b  mov     rax, [r14+208h]
0x180042342  test    edx, edx
0x180042344  jg      loc_1800424BF
0x18004234a  lea     rcx, [rdi+0D8h]
0x180042351  mov     r9d, 5
0x180042357  xor     r8d, r8d
0x18004235a  mov     rax, [rax+38h]
0x18004235e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042363  jmp     loc_1800421AF
0x180042368  test    dword ptr [rcx+1Ch], 800h
0x18004236f  jz      loc_180042293
0x180042375  lea     r9, [rdi-130h]
0x18004237c  mov     edx, 3Dh ; '='
0x180042381  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180042388  mov     rcx, [rcx+10h]
0x18004238c  call    WPP_SF_q
0x180042391  jmp     loc_180042293
0x180042396  cmp     rcx, r15
0x180042399  jz      loc_180042038
0x18004239f  test    dword ptr [rcx+1Ch], 100h
0x1800423a6  jz      loc_180042038
0x1800423ac  mov     edx, 0Fh
0x1800423b1  mov     r9, rbx
0x1800423b4  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800423bb  mov     rcx, [rcx+10h]
0x1800423bf  call    WPP_SF_q
0x1800423c4  jmp     loc_180042038
0x1800423c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423d0  cmp     rcx, r15
0x1800423d3  jz      short loc_1800423F4
0x1800423d5  test    byte ptr [rcx+1Ch], 2
0x1800423d9  jz      short loc_1800423F4
0x1800423db  mov     edx, 3Eh ; '>'
0x1800423e0  mov     r9d, [r13+0]
0x1800423e4  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800423eb  mov     rcx, [rcx+10h]
0x1800423ef  call    WPP_SF_d
0x1800423f4  mov     ecx, [r13+0]; unsigned int
0x1800423f8  call    ?MapSecureHttpErrorCode@@YAKK@Z; MapSecureHttpErrorCode(ulong)
0x1800423fd  mov     [rdi+402A8h], eax
0x180042403  lea     rcx, [rsp+0D8h+var_A8]; this
0x180042408  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18004240d  jmp     loc_180042099
0x180042412  mov     rax, cs:WPP_GLOBAL_Control
0x180042419  cmp     rax, r15
0x18004241c  jz      loc_180042112
0x180042422  test    byte ptr [rax+1Ch], 2
0x180042426  jz      loc_180042112
0x18004242c  call    cs:__imp_GetLastError
0x180042432  mov     edx, 32h ; '2'
0x180042437  mov     rcx, cs:WPP_GLOBAL_Control
0x18004243e  jmp     short loc_180042449
0x180042440  sub     eax, dword ptr [rsp+0D8h+var_98]
0x180042444  mov     edx, 33h ; '3'
0x180042449  mov     r9d, eax
0x18004244c  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180042453  mov     rcx, [rcx+10h]
0x180042457  call    WPP_SF_d
0x18004245c  jmp     loc_180042112
0x180042461  cmp     esi, 200000h
0x180042467  jz      short loc_18004247A
0x180042469  cmp     esi, 400000h
0x18004246f  jnz     loc_1800421AF
0x180042475  jmp     loc_18004230B
0x18004247a  mov     eax, [r13+8]
0x18004247e  cmp     eax, 2EF1h
0x180042483  jnz     short loc_1800424AF
0x180042485  mov     eax, 2EE2h
0x18004248a  lea     rdx, [rdi+402A8h]
0x180042491  mov     [rdx], eax
0x180042493  mov     edx, [rdx]; unsigned int
0x180042495  cmp     dword ptr [rdi+148h], 1
0x18004249c  jnz     loc_18004233B
0x1800424a2  mov     rcx, r14; this
0x1800424a5  call    ?DealWithSendError@CHttpReader@@IEAAXK@Z; CHttpReader::DealWithSendError(ulong)
0x1800424aa  jmp     loc_1800421AF
0x1800424af  cmp     eax, 2F8Fh
0x1800424b4  jnz     short loc_18004248A
0x1800424b6  lea     rdx, [rdi+402A8h]
0x1800424bd  jmp     short loc_180042493
0x1800424bf  movzx   edx, dx
0x1800424c2  or      edx, 80070000h
0x1800424c8  jmp     loc_18004234A
0x1800424cd  mov     byte ptr [rdi+40289h], 1
0x1800424d4  jmp     loc_180042197
0x1800424d9  lea     r15, WPP_GLOBAL_Control
0x1800424e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424e7  jmp     loc_1800421CD
0x1800424ec  test    dword ptr [rcx+1Ch], 800h
0x1800424f3  jz      loc_18004207D
0x1800424f9  mov     edx, 3Fh ; '?'
0x1800424fe  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180042505  mov     rcx, [rcx+10h]
0x180042509  call    WPP_SF_
0x18004250e  movzx   eax, [rsp+0D8h+var_A8]
0x180042513  mov     rcx, cs:WPP_GLOBAL_Control
0x18004251a  jmp     loc_18004207D
0x18004251f  cmp     rcx, r15
0x180042522  jz      loc_180042090
0x180042528  test    dword ptr [rcx+1Ch], 100h
0x18004252f  jz      loc_180042090
0x180042535  mov     r9, rbx
0x180042538  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18004253f  mov     edx, 10h
0x180042544  mov     rcx, [rcx+10h]
0x180042548  call    WPP_SF_q
0x18004254d  jmp     loc_180042090
```
