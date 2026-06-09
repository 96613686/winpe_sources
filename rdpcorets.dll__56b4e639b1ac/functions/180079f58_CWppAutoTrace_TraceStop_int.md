# CWppAutoTrace::TraceStop(int)

- ea: `0x180079f58`
- end: `0x18007a3a2`
- name: `?TraceStop@CWppAutoTrace@@AEAAJH@Z`
- size: `1098`
- prototype: `__int64 __fastcall(CWppAutoTrace *__hidden this, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800323ac`
- `0x180078544`
- `0x1800798dc`

## callees

- `0x1800091a8`
- `0x18000e420`
- `0x180012200`
- `0x18001569c`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x180063160`
- `0x180072abc`
- `0x180073258`
- `0x1800789fc`
- `0x180079f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a303`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18007a035`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18007a035`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007a2ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007a2ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18007a1e5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18007a1e5`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180079fa2`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180079fa2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18007a0a3`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18007a0a3`

## string_xrefs

- `0x18007a1a4`: `Create completed filename`

## pseudocode

```c
__int64 __fastcall CWppAutoTrace::TraceStop(CWppAutoTrace *this, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  int v5; // esi
  PVOID *v6; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v8; // rdx
  unsigned int v9; // eax
  TRACEHANDLE v10; // rcx
  CWppAutoTrace *v11; // rcx
  ULONG v12; // edi
  unsigned int v13; // r9d
  unsigned int v14; // eax
  int v15; // ebx
  const WCHAR *v16; // rsi
  WCHAR v17; // ax
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r11
  unsigned int v20; // eax
  unsigned int v21; // eax
  const WCHAR *v22; // rdi
  DWORD LastError; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  char *v27; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR NewFileName[264]; // [rsp+310h] [rbp+210h] BYREF

  v4 = (char *)this + 592;
  v5 = a2;
  v27 = v4;
  if ( *((_DWORD *)v4 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v4, a2, a3);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      CurrentThreadActivityIdPrefix);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 72) )
    goto LABEL_52;
  memset_0(&Properties, 0, 0x2D0u);
  v8 = (void *)*((_QWORD *)this + 77);
  *((_BYTE *)this + 72) = 0;
  if ( v8 != (void *)-1LL
    && !ChangeTimerQueueTimer(0, v8, 0x3B9ACA00u, 0x3B9ACA00u)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v9);
  }
  memset_0(&Properties, 0, 0x2D0u);
  v10 = *((_QWORD *)this + 8);
  Properties.Wnode.BufferSize = 720;
  Properties.Wnode.Flags = 0x20000;
  v12 = ControlTraceW(v10, 0, &Properties, 1u);
  if ( v12 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v14, v12);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v15 = -2147467259;
    goto LABEL_53;
  }
  if ( !v5 )
  {
    v22 = (const WCHAR *)((char *)&Properties + Properties.LogFileNameOffset);
    if ( DeleteFileW(v22) )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_52;
      }
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)this + 624, (__int64)v22);
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      LastError = GetLastError();
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v24,
        (__int64)v22,
        LastError,
        v27);
    }
    goto LABEL_51;
  }
  if ( !*((_WORD *)this + 612) )
  {
LABEL_51:
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_52:
    v15 = 0;
    goto LABEL_53;
  }
  v16 = (const WCHAR *)((char *)&Properties + Properties.LogFileNameOffset);
  CWppAutoTrace::DeleteOldFiles(v11, (const unsigned __int16 *)this + 612, (const unsigned __int16 *)this + 312, v13);
  StringCchCopyW(NewFileName, 0x104u, (const unsigned __int16 *)this + 612);
  v17 = *v16;
  v18 = v16;
  v19 = v16;
  while ( v17 )
  {
    ++v19;
    if ( v17 == 92 )
      v18 = v19;
    v17 = *v19;
  }
  v15 = StringCchCatW(NewFileName, 0x104u, v18);
  if ( v15 >= 0 )
  {
    if ( MoveFileW(v16, NewFileName) )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_52;
      }
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v21,
        (__int64)NewFileName);
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v16, (__int64)NewFileName);
    }
    goto LABEL_51;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_57;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v20,
      (__int64)"Create completed filename",
      v15,
      v27);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_53:
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x400) != 0 && *((_BYTE *)v6 + 25) >= 5u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v25, v15);
  }
LABEL_57:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v27);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180079f58  push    rbp
0x180079f5a  push    rbx
0x180079f5b  push    rsi
0x180079f5c  push    rdi
0x180079f5d  push    r12
0x180079f5f  push    r13
0x180079f61  push    r14
0x180079f63  push    r15
0x180079f65  lea     rbp, [rsp-438h]
0x180079f6d  sub     rsp, 538h
0x180079f74  mov     rax, cs:__security_cookie
0x180079f7b  xor     rax, rsp
0x180079f7e  mov     [rbp+470h+var_50], rax
0x180079f85  mov     rbx, rcx
0x180079f88  xor     r14d, r14d
0x180079f8b  add     rcx, 250h
0x180079f92  mov     esi, edx
0x180079f94  mov     [rsp+570h+var_540], rcx
0x180079f99  cmp     [rcx+8], r14d
0x180079f9d  jz      short loc_180079FA8
0x180079f9f  mov     rcx, [rcx]
0x180079fa2  call    cs:__imp_PAL_System_CritSecEnter
0x180079fa8  mov     rax, cs:WPP_GLOBAL_Control
0x180079faf  lea     r15, WPP_GLOBAL_Control
0x180079fb6  lea     r13, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x180079fbd  mov     r12d, 400h
0x180079fc3  cmp     rax, r15
0x180079fc6  jz      short loc_180079FFB
0x180079fc8  test    [rax+1Ch], r12d
0x180079fcc  jz      short loc_180079FFB
0x180079fce  cmp     byte ptr [rax+19h], 5
0x180079fd2  jb      short loc_180079FFB
0x180079fd4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180079fe0  mov     edx, 34h ; '4'
0x180079fe5  mov     r9d, eax
0x180079fe8  mov     r8, r13
0x180079feb  mov     rcx, [rcx+10h]
0x180079fef  call    WPP_SF_d
0x180079ff4  mov     rax, cs:WPP_GLOBAL_Control
0x180079ffb  cmp     [rbx+48h], r14b
0x180079fff  jz      loc_18007A33B
0x18007a005  mov     edi, 2D0h
0x18007a00a  lea     rcx, [rsp+570h+Properties]; void *
0x18007a00f  mov     r8d, edi; Size
0x18007a012  xor     edx, edx; Val
0x18007a014  call    memset_0
0x18007a019  mov     rdx, [rbx+268h]; Timer
0x18007a020  mov     [rbx+48h], r14b
0x18007a024  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18007a028  jz      short loc_18007A077
0x18007a02a  mov     r8d, 3B9ACA00h; DueTime
0x18007a030  xor     ecx, ecx; TimerQueue
0x18007a032  mov     r9d, r8d; Period
0x18007a035  call    cs:__imp_ChangeTimerQueueTimer
0x18007a03b  test    eax, eax
0x18007a03d  jnz     short loc_18007A077
0x18007a03f  mov     rax, cs:WPP_GLOBAL_Control
0x18007a046  cmp     rax, r15
0x18007a049  jz      short loc_18007A077
0x18007a04b  test    [rax+1Ch], r12d
0x18007a04f  jz      short loc_18007A077
0x18007a051  cmp     byte ptr [rax+19h], 3
0x18007a055  jb      short loc_18007A077
0x18007a057  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a063  mov     edx, 35h ; '5'
0x18007a068  mov     r9d, eax
0x18007a06b  mov     r8, r13
0x18007a06e  mov     rcx, [rcx+10h]
0x18007a072  call    WPP_SF_d
0x18007a077  mov     r8, rdi; Size
0x18007a07a  lea     rcx, [rsp+570h+Properties]; void *
0x18007a07f  xor     edx, edx; Val
0x18007a081  call    memset_0
0x18007a086  mov     rcx, [rbx+40h]; TraceHandle
0x18007a08a  lea     r8, [rsp+570h+Properties]; Properties
0x18007a08f  mov     r9d, 1; ControlCode
0x18007a095  mov     [rsp+570h+Properties.Wnode.BufferSize], edi
0x18007a099  xor     edx, edx; InstanceName
0x18007a09b  mov     [rsp+570h+Properties.Wnode.Flags], 20000h
0x18007a0a3  call    cs:__imp_ControlTraceW
0x18007a0a9  mov     edi, eax
0x18007a0ab  test    eax, eax
0x18007a0ad  jz      short loc_18007A0FC
0x18007a0af  mov     rax, cs:WPP_GLOBAL_Control
0x18007a0b6  cmp     rax, r15
0x18007a0b9  jz      short loc_18007A0F2
0x18007a0bb  test    [rax+1Ch], r12d
0x18007a0bf  jz      short loc_18007A0F2
0x18007a0c1  cmp     byte ptr [rax+19h], 2
0x18007a0c5  jb      short loc_18007A0F2
0x18007a0c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a0d3  mov     edx, 36h ; '6'
0x18007a0d8  mov     r9d, eax
0x18007a0db  mov     dword ptr [rsp+570h+var_550], edi
0x18007a0df  mov     r8, r13
0x18007a0e2  mov     rcx, [rcx+10h]
0x18007a0e6  call    WPP_SF_Dd
0x18007a0eb  mov     rax, cs:WPP_GLOBAL_Control
0x18007a0f2  mov     ebx, 80004005h
0x18007a0f7  jmp     loc_18007A33E
0x18007a0fc  test    esi, esi
0x18007a0fe  jz      loc_18007A29E
0x18007a104  lea     rdi, [rbx+4C8h]
0x18007a10b  cmp     [rdi], r14w
0x18007a10f  jz      loc_18007A334
0x18007a115  mov     eax, [rbp+470h+Properties.LogFileNameOffset]
0x18007a118  lea     rsi, [rsp+570h+Properties]
0x18007a11d  lea     r8, [rbx+270h]; unsigned __int16 *
0x18007a124  mov     rdx, rdi; unsigned __int16 *
0x18007a127  add     rsi, rax
0x18007a12a  call    ?DeleteOldFiles@CWppAutoTrace@@AEAAJPEBG0K@Z; CWppAutoTrace::DeleteOldFiles(ushort const *,ushort const *,ulong)
0x18007a12f  mov     ebx, 104h
0x18007a134  lea     rcx, [rbp+470h+NewFileName]; unsigned __int16 *
0x18007a13b  mov     edx, ebx; unsigned __int64
0x18007a13d  mov     r8, rdi; unsigned __int16 *
0x18007a140  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007a145  movzx   eax, word ptr [rsi]
0x18007a148  mov     r8, rsi
0x18007a14b  mov     r11, rsi
0x18007a14e  jmp     short loc_18007A161
0x18007a150  add     r11, 2
0x18007a154  cmp     ax, 5Ch ; '\'
0x18007a158  jnz     short loc_18007A15D
0x18007a15a  mov     r8, r11; unsigned __int16 *
0x18007a15d  movzx   eax, word ptr [r11]
0x18007a161  test    ax, ax
0x18007a164  jnz     short loc_18007A150
0x18007a166  mov     rdx, rbx; unsigned __int64
0x18007a169  lea     rcx, [rbp+470h+NewFileName]; unsigned __int16 *
0x18007a170  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007a175  mov     ebx, eax
0x18007a177  test    eax, eax
0x18007a179  jns     short loc_18007A1DB
0x18007a17b  mov     rax, cs:WPP_GLOBAL_Control
0x18007a182  cmp     rax, r15
0x18007a185  jz      loc_18007A373
0x18007a18b  test    byte ptr [rax+1Ch], 8
0x18007a18f  jz      loc_18007A33E
0x18007a195  cmp     byte ptr [rax+19h], 2
0x18007a199  jb      loc_18007A33E
0x18007a19f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a1a4  lea     rcx, aCreateComplete; "Create completed filename"
0x18007a1ab  mov     dword ptr [rsp+570h+var_548], ebx
0x18007a1af  mov     [rsp+570h+var_550], rcx
0x18007a1b4  mov     edx, 37h ; '7'
0x18007a1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a1c0  mov     r9d, eax
0x18007a1c3  mov     r8, r13
0x18007a1c6  mov     rcx, [rcx+10h]
0x18007a1ca  call    WPP_SF_DsD
0x18007a1cf  mov     rax, cs:WPP_GLOBAL_Control
0x18007a1d6  jmp     loc_18007A33E
0x18007a1db  lea     rdx, [rbp+470h+NewFileName]; lpNewFileName
0x18007a1e2  mov     rcx, rsi; lpExistingFileName
0x18007a1e5  call    cs:__imp_MoveFileW
0x18007a1eb  test    eax, eax
0x18007a1ed  jz      short loc_18007A244
0x18007a1ef  mov     rax, cs:WPP_GLOBAL_Control
0x18007a1f6  cmp     rax, r15
0x18007a1f9  jz      loc_18007A33B
0x18007a1ff  test    [rax+1Ch], r12d
0x18007a203  jz      loc_18007A33B
0x18007a209  cmp     byte ptr [rax+19h], 4
0x18007a20d  jb      loc_18007A33B
0x18007a213  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a218  lea     rcx, [rbp+470h+NewFileName]
0x18007a21f  mov     edx, 38h ; '8'
0x18007a224  mov     [rsp+570h+var_550], rcx
0x18007a229  mov     r9d, eax
0x18007a22c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a233  mov     r8, r13
0x18007a236  mov     rcx, [rcx+10h]
0x18007a23a  call    WPP_SF_DS
0x18007a23f  jmp     loc_18007A334
0x18007a244  mov     rax, cs:WPP_GLOBAL_Control
0x18007a24b  cmp     rax, r15
0x18007a24e  jz      loc_18007A33B
0x18007a254  test    [rax+1Ch], r12d
0x18007a258  jz      loc_18007A33B
0x18007a25e  cmp     byte ptr [rax+19h], 2
0x18007a262  jb      loc_18007A33B
0x18007a268  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a26d  lea     rcx, [rbp+470h+NewFileName]
0x18007a274  mov     edx, 39h ; '9'
0x18007a279  mov     [rsp+570h+var_548], rcx; __int64
0x18007a27e  mov     [rsp+570h+var_550], rsi; __int64
0x18007a283  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a28a  mov     r9d, eax
0x18007a28d  mov     r8, r13
0x18007a290  mov     rcx, [rcx+10h]; LoggerHandle
0x18007a294  call    WPP_SF_DSS
0x18007a299  jmp     loc_18007A334
0x18007a29e  mov     eax, [rbp+470h+Properties.LogFileNameOffset]
0x18007a2a1  lea     rdi, [rsp+570h+Properties]
0x18007a2a6  add     rdi, rax
0x18007a2a9  mov     rcx, rdi; lpFileName
0x18007a2ac  call    cs:__imp_DeleteFileW
0x18007a2b2  test    eax, eax
0x18007a2b4  jz      short loc_18007A2EB
0x18007a2b6  mov     rax, cs:WPP_GLOBAL_Control
0x18007a2bd  cmp     rax, r15
0x18007a2c0  jz      short loc_18007A33B
0x18007a2c2  test    [rax+1Ch], r12d
0x18007a2c6  jz      short loc_18007A33B
0x18007a2c8  cmp     byte ptr [rax+19h], 3
0x18007a2cc  jb      short loc_18007A33B
0x18007a2ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a2d3  lea     rcx, [rbx+270h]
0x18007a2da  mov     [rsp+570h+var_548], rdi
0x18007a2df  mov     [rsp+570h+var_550], rcx
0x18007a2e4  mov     edx, 3Ah ; ':'
0x18007a2e9  jmp     short loc_18007A283
0x18007a2eb  mov     rax, cs:WPP_GLOBAL_Control
0x18007a2f2  cmp     rax, r15
0x18007a2f5  jz      short loc_18007A33B
0x18007a2f7  test    [rax+1Ch], r12d
0x18007a2fb  jz      short loc_18007A33B
0x18007a2fd  cmp     byte ptr [rax+19h], 2
0x18007a301  jb      short loc_18007A33B
0x18007a303  call    cs:__imp_GetLastError
0x18007a309  mov     ebx, eax
0x18007a30b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a310  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a317  mov     edx, 3Bh ; ';'
0x18007a31c  mov     dword ptr [rsp+570h+var_548], ebx
0x18007a320  mov     r9d, eax
0x18007a323  mov     r8, r13
0x18007a326  mov     [rsp+570h+var_550], rdi
0x18007a32b  mov     rcx, [rcx+10h]
0x18007a32f  call    WPP_SF_DSd
0x18007a334  mov     rax, cs:WPP_GLOBAL_Control
0x18007a33b  mov     ebx, r14d
0x18007a33e  cmp     rax, r15
0x18007a341  jz      short loc_18007A373
0x18007a343  test    [rax+1Ch], r12d
0x18007a347  jz      short loc_18007A373
0x18007a349  cmp     byte ptr [rax+19h], 5
0x18007a34d  jb      short loc_18007A373
0x18007a34f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a354  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a35b  mov     edx, 3Ch ; '<'
0x18007a360  mov     r9d, eax
0x18007a363  mov     dword ptr [rsp+570h+var_550], ebx
0x18007a367  mov     r8, r13
0x18007a36a  mov     rcx, [rcx+10h]
0x18007a36e  call    WPP_SF_Dd
0x18007a373  lea     rcx, [rsp+570h+var_540]; this
0x18007a378  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18007a37d  mov     eax, ebx
0x18007a37f  mov     rcx, [rbp+470h+var_50]
0x18007a386  xor     rcx, rsp; StackCookie
0x18007a389  call    __security_check_cookie
0x18007a38e  add     rsp, 538h
0x18007a395  pop     r15
0x18007a397  pop     r14
0x18007a399  pop     r13
0x18007a39b  pop     r12
0x18007a39d  pop     rdi
0x18007a39e  pop     rsi
0x18007a39f  pop     rbx
0x18007a3a0  pop     rbp
0x18007a3a1  retn
```
