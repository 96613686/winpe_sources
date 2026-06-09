# CGlobalPipeMgr::CreatePipeHandlePair(void * *,void * *,char const *)

- ea: `0x180074230`
- end: `0x1800746a2`
- name: `?CreatePipeHandlePair@CGlobalPipeMgr@@UEAAJPEAPEAX0PEBD@Z`
- size: `1138`
- prototype: `__int64 __fastcall(CGlobalPipeMgr *this, void **, void **, char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800091a8`
- `0x180012200`
- `0x18002e600`
- `0x180059838`
- `0x1800598d0`
- `0x180074230`
- `0x1800746a8`
- `0x180074990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007450d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007450d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007457b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007457b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800745dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800745dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007440a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007440a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074484`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180074565`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180074565`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeServerProcessId` at `0x1800745b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeServerProcessId` at `0x1800745b1`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180074273`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180074273`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180074526`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180074526`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180074599`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180074599`

## pseudocode

```c
__int64 __fastcall CGlobalPipeMgr::CreatePipeHandlePair(CGlobalPipeMgr *this, void **a2, void **a3, char *a4)
{
  __int64 v4; // rsi
  CGlobalPipeMgr *v5; // r14
  char *v6; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  signed int UniqueName; // ebx
  unsigned int v13; // eax
  __int64 FileW; // r15
  unsigned int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  signed int LastError; // eax
  DWORD CurrentProcessId; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+40h] [rbp-40h]
  HANDLE hNamedPipe; // [rsp+48h] [rbp-38h] BYREF
  char *v25; // [rsp+50h] [rbp-30h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-28h] BYREF
  DWORD Mode; // [rsp+D0h] [rbp+50h] BYREF
  char *v29; // [rsp+D8h] [rbp+58h]

  v29 = a4;
  v4 = 0;
  v5 = this;
  v6 = (char *)this + 16;
  hNamedPipe = 0;
  v25 = v6;
  if ( *((_DWORD *)v6 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v6, a2, a3);
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 36;
    v11 = "phClientPipe";
LABEL_8:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v11);
LABEL_9:
    UniqueName = -2147467261;
    goto LABEL_67;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 37;
    v11 = "phServerPipe";
    goto LABEL_8;
  }
  *a3 = (void *)-1LL;
  *a2 = (void *)-1LL;
  if ( !*((_DWORD *)v5 + 2) )
  {
    UniqueName = -2147024884;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v13,
        (__int64)"!_bInited",
        12);
    }
    goto LABEL_67;
  }
  FileW = 0;
  v23 = 0;
  UniqueName = -2147467259;
  while ( UniqueName < 0 )
  {
    UniqueName = CGlobalPipeMgr::CreateUniqueName((CGlobalPipeMgr *)((char *)v5 - 48));
    if ( UniqueName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v15);
      }
LABEL_27:
      v5 = this;
      goto LABEL_28;
    }
    v16 = CGlobalPipeMgr::CreatePipeServer((CGlobalPipeMgr *)((char *)v5 - 48), v29, &hNamedPipe);
    UniqueName = v16;
    if ( v16 < 0 )
    {
      if ( v16 == -2147024891
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v17);
      }
      v4 = (__int64)hNamedPipe;
      goto LABEL_27;
    }
    v5 = this;
    memset(&Overlapped, 0, sizeof(Overlapped));
    ResetEvent(*((HANDLE *)this + 4));
    v4 = (__int64)hNamedPipe;
    Overlapped.hEvent = (HANDLE)*((_QWORD *)this + 4);
    if ( !ConnectNamedPipe(hNamedPipe, &Overlapped) && GetLastError() != 997
      || (FileW = (__int64)CreateFileW((LPCWSTR)this + 20, 0xC0000000, 0, 0, 3u, 0x40000000u, 0), FileW == -1)
      || WaitForSingleObject(*((HANDLE *)this + 4), 0xFFFFFFFF)
      || (Mode = 2, !SetNamedPipeHandleState((HANDLE)FileW, &Mode, 0, 0))
      || (Mode = 0, !GetNamedPipeServerProcessId((HANDLE)FileW, &Mode)) )
    {
      LastError = GetLastError();
      UniqueName = LastError;
      if ( LastError > 0 )
        UniqueName = (unsigned __int16)LastError | 0x80070000;
      if ( UniqueName >= 0 )
        goto LABEL_32;
      goto LABEL_28;
    }
    CurrentProcessId = GetCurrentProcessId();
    if ( !CurrentProcessId )
      goto LABEL_57;
    if ( CurrentProcessId != Mode )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v20);
      }
LABEL_57:
      UniqueName = -2147467259;
LABEL_28:
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)FileW);
        FileW = -1;
        *a3 = (void *)-1LL;
      }
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)v4);
        v4 = -1;
        hNamedPipe = (HANDLE)-1LL;
        *a2 = (void *)-1LL;
      }
    }
LABEL_32:
    if ( ++v23 > 5 )
    {
      if ( UniqueName < 0 )
      {
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle((HANDLE)FileW);
          *a3 = (void *)-1LL;
        }
        if ( v4 && v4 != -1 )
        {
          CloseHandle((HANDLE)v4);
          *a2 = (void *)-1LL;
        }
        goto LABEL_67;
      }
      break;
    }
  }
  *a3 = (void *)FileW;
  *a2 = (void *)v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v21);
  }
LABEL_67:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v25);
  return (unsigned int)UniqueName;
}

```

## disassembly

```asm
0x180074230  mov     [rsp-38h+arg_8], rbx
0x180074235  mov     [rsp-38h+arg_18], r9
0x18007423a  mov     [rsp-38h+arg_0], rcx
0x18007423f  push    rbp
0x180074240  push    rsi
0x180074241  push    rdi
0x180074242  push    r12
0x180074244  push    r13
0x180074246  push    r14
0x180074248  push    r15
0x18007424a  mov     rbp, rsp
0x18007424d  sub     rsp, 80h
0x180074254  xor     esi, esi
0x180074256  mov     r14, rcx
0x180074259  add     rcx, 10h
0x18007425d  mov     [rbp+hNamedPipe], rsi
0x180074261  mov     r12, r8
0x180074264  mov     [rbp+var_30], rcx
0x180074268  mov     r13, rdx
0x18007426b  cmp     [rcx+8], esi
0x18007426e  jz      short loc_180074279
0x180074270  mov     rcx, [rcx]
0x180074273  call    cs:__imp_PAL_System_CritSecEnter
0x180074279  test    r12, r12
0x18007427c  jnz     short loc_1800742D7
0x18007427e  mov     rax, cs:WPP_GLOBAL_Control
0x180074285  lea     rdi, WPP_GLOBAL_Control
0x18007428c  cmp     rax, rdi
0x18007428f  jz      short loc_1800742CD
0x180074291  test    byte ptr [rax+1Ch], 8
0x180074295  jz      short loc_1800742CD
0x180074297  cmp     byte ptr [rax+19h], 2
0x18007429b  jb      short loc_1800742CD
0x18007429d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800742a2  lea     edx, [r12+24h]
0x1800742a7  lea     rcx, aPhclientpipe; "phClientPipe"
0x1800742ae  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x1800742b3  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800742ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800742c1  mov     r9d, eax
0x1800742c4  mov     rcx, [rcx+10h]
0x1800742c8  call    WPP_SF_Ds
0x1800742cd  mov     ebx, 80004003h
0x1800742d2  jmp     loc_18007467C
0x1800742d7  test    r13, r13
0x1800742da  jnz     short loc_18007430D
0x1800742dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800742e3  lea     rdi, WPP_GLOBAL_Control
0x1800742ea  cmp     rax, rdi
0x1800742ed  jz      short loc_1800742CD
0x1800742ef  test    byte ptr [rax+1Ch], 8
0x1800742f3  jz      short loc_1800742CD
0x1800742f5  cmp     byte ptr [rax+19h], 2
0x1800742f9  jb      short loc_1800742CD
0x1800742fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074300  lea     edx, [r13+25h]
0x180074304  lea     rcx, aPhserverpipe; "phServerPipe"
0x18007430b  jmp     short loc_1800742AE
0x18007430d  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180074315  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x18007431d  cmp     [r14+8], esi
0x180074321  jnz     short loc_180074390
0x180074323  mov     ebx, 8007000Ch
0x180074328  mov     rax, cs:WPP_GLOBAL_Control
0x18007432f  lea     rdi, WPP_GLOBAL_Control
0x180074336  cmp     rax, rdi
0x180074339  jz      loc_18007467C
0x18007433f  test    byte ptr [rax+1Ch], 8
0x180074343  jz      loc_18007467C
0x180074349  cmp     byte ptr [rax+19h], 2
0x18007434d  jb      loc_18007467C
0x180074353  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074358  lea     rcx, aBinited; "!_bInited"
0x18007435f  mov     [rsp+80h+dwFlagsAndAttributes], 8007000Ch
0x180074367  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x18007436c  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074373  mov     rcx, cs:WPP_GLOBAL_Control
0x18007437a  mov     edx, 26h ; '&'
0x18007437f  mov     r9d, eax
0x180074382  mov     rcx, [rcx+10h]
0x180074386  call    WPP_SF_DsD
0x18007438b  jmp     loc_18007467C
0x180074390  xor     r15d, r15d
0x180074393  mov     [rbp+var_40], esi
0x180074396  mov     ebx, 80004005h
0x18007439b  lea     rdi, WPP_GLOBAL_Control
0x1800743a2  test    ebx, ebx
0x1800743a4  jns     loc_180074638
0x1800743aa  lea     rcx, [r14-30h]; this
0x1800743ae  call    ?CreateUniqueName@CGlobalPipeMgr@@AEAAJXZ; CGlobalPipeMgr::CreateUniqueName(void)
0x1800743b3  mov     ebx, eax
0x1800743b5  test    eax, eax
0x1800743b7  jns     loc_180074497
0x1800743bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800743c4  cmp     rax, rdi
0x1800743c7  jz      short loc_1800743F9
0x1800743c9  test    byte ptr [rax+1Ch], 1
0x1800743cd  jz      short loc_1800743F9
0x1800743cf  cmp     byte ptr [rax+19h], 2
0x1800743d3  jb      short loc_1800743F9
0x1800743d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800743da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743e1  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800743e8  mov     edx, 27h ; '''
0x1800743ed  mov     r9d, eax
0x1800743f0  mov     rcx, [rcx+10h]
0x1800743f4  call    WPP_SF_d
0x1800743f9  mov     r14, [rbp+arg_0]
0x1800743fd  lea     rax, [r15-1]
0x180074401  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180074405  ja      short loc_18007441B
0x180074407  mov     rcx, r15; hObject
0x18007440a  call    cs:__imp_CloseHandle
0x180074410  or      rax, 0FFFFFFFFFFFFFFFFh
0x180074414  mov     r15, rax
0x180074417  mov     [r12], rax
0x18007441b  lea     rax, [rsi-1]
0x18007441f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180074423  ja      short loc_18007443A
0x180074425  mov     rcx, rsi; hObject
0x180074428  call    cs:__imp_CloseHandle
0x18007442e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180074432  mov     [rbp+hNamedPipe], rsi
0x180074436  mov     [r13+0], rsi
0x18007443a  mov     eax, [rbp+var_40]
0x18007443d  inc     eax
0x18007443f  mov     [rbp+var_40], eax
0x180074442  cmp     eax, 5
0x180074445  jle     loc_1800743A2
0x18007444b  test    ebx, ebx
0x18007444d  jns     loc_180074638
0x180074453  lea     rax, [r15-1]
0x180074457  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007445b  ja      short loc_18007446E
0x18007445d  mov     rcx, r15; hObject
0x180074460  call    cs:__imp_CloseHandle
0x180074466  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18007446e  test    rsi, rsi
0x180074471  jz      loc_18007467C
0x180074477  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007447b  jz      loc_18007467C
0x180074481  mov     rcx, rsi; hObject
0x180074484  call    cs:__imp_CloseHandle
0x18007448a  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x180074492  jmp     loc_18007467C
0x180074497  mov     rdx, [rbp+arg_18]; char *
0x18007449b  lea     r8, [rbp+hNamedPipe]; void **
0x18007449f  lea     rcx, [r14-30h]; this
0x1800744a3  call    ?CreatePipeServer@CGlobalPipeMgr@@AEAAJPEBDPEAPEAX@Z; CGlobalPipeMgr::CreatePipeServer(char const *,void * *)
0x1800744a8  mov     ebx, eax
0x1800744aa  test    eax, eax
0x1800744ac  jns     short loc_1800744FA
0x1800744ae  cmp     eax, 80070005h
0x1800744b3  jnz     short loc_1800744F1
0x1800744b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800744bc  cmp     rax, rdi
0x1800744bf  jz      short loc_1800744F1
0x1800744c1  test    byte ptr [rax+1Ch], 1
0x1800744c5  jz      short loc_1800744F1
0x1800744c7  cmp     byte ptr [rax+19h], 4
0x1800744cb  jb      short loc_1800744F1
0x1800744cd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800744d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800744d9  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800744e0  mov     edx, 28h ; '('
0x1800744e5  mov     r9d, eax
0x1800744e8  mov     rcx, [rcx+10h]
0x1800744ec  call    WPP_SF_d
0x1800744f1  mov     rsi, [rbp+hNamedPipe]
0x1800744f5  jmp     loc_1800743F9
0x1800744fa  mov     r14, [rbp+arg_0]
0x1800744fe  xorps   xmm0, xmm0
0x180074501  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180074505  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180074509  mov     rcx, [r14+20h]; hEvent
0x18007450d  call    cs:__imp_ResetEvent
0x180074513  mov     rax, [r14+20h]
0x180074517  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18007451b  mov     rsi, [rbp+hNamedPipe]
0x18007451f  mov     rcx, rsi; hNamedPipe
0x180074522  mov     [rbp+Overlapped.hEvent], rax
0x180074526  call    cs:__imp_ConnectNamedPipe
0x18007452c  test    eax, eax
0x18007452e  jnz     short loc_18007453D
0x180074530  call    cs:__imp_GetLastError
0x180074536  cmp     eax, 3E5h
0x18007453b  jnz     short loc_1800745BB
0x18007453d  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180074546  lea     rcx, [r14+28h]; lpFileName
0x18007454a  mov     [rsp+80h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180074552  xor     r9d, r9d; lpSecurityAttributes
0x180074555  xor     r8d, r8d; dwShareMode
0x180074558  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180074560  mov     edx, 0C0000000h; dwDesiredAccess
0x180074565  call    cs:__imp_CreateFileW
0x18007456b  mov     r15, rax
0x18007456e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180074572  jz      short loc_1800745BB
0x180074574  mov     rcx, [r14+20h]; hHandle
0x180074578  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007457b  call    cs:__imp_WaitForSingleObject
0x180074581  test    eax, eax
0x180074583  jnz     short loc_1800745BB
0x180074585  xor     r9d, r9d; lpCollectDataTimeout
0x180074588  mov     [rbp+Mode], 2
0x18007458f  xor     r8d, r8d; lpMaxCollectionCount
0x180074592  lea     rdx, [rbp+Mode]; lpMode
0x180074596  mov     rcx, r15; hNamedPipe
0x180074599  call    cs:__imp_SetNamedPipeHandleState
0x18007459f  test    eax, eax
0x1800745a1  jz      short loc_1800745BB
0x1800745a3  lea     rdx, [rbp+Mode]; ServerProcessId
0x1800745a7  mov     [rbp+Mode], 0
0x1800745ae  mov     rcx, r15; Pipe
0x1800745b1  call    cs:__imp_GetNamedPipeServerProcessId
0x1800745b7  test    eax, eax
0x1800745b9  jnz     short loc_1800745DD
0x1800745bb  call    cs:__imp_GetLastError
0x1800745c1  mov     ebx, eax
0x1800745c3  test    eax, eax
0x1800745c5  jle     short loc_1800745D0
0x1800745c7  movzx   ebx, ax
0x1800745ca  or      ebx, 80070000h
0x1800745d0  test    ebx, ebx
0x1800745d2  jns     loc_18007443A
0x1800745d8  jmp     loc_1800743FD
0x1800745dd  call    cs:__imp_GetCurrentProcessId
0x1800745e3  test    eax, eax
0x1800745e5  jnz     short loc_1800745F1
0x1800745e7  mov     ebx, 80004005h
0x1800745ec  jmp     loc_1800743FD
0x1800745f1  cmp     eax, [rbp+Mode]
0x1800745f4  jz      loc_18007443A
0x1800745fa  mov     rax, cs:WPP_GLOBAL_Control
0x180074601  cmp     rax, rdi
0x180074604  jz      short loc_1800745E7
0x180074606  test    byte ptr [rax+1Ch], 1
0x18007460a  jz      short loc_1800745E7
0x18007460c  cmp     byte ptr [rax+19h], 4
0x180074610  jb      short loc_1800745E7
0x180074612  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074617  mov     rcx, cs:WPP_GLOBAL_Control
0x18007461e  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074625  mov     edx, 29h ; ')'
0x18007462a  mov     r9d, eax
0x18007462d  mov     rcx, [rcx+10h]
0x180074631  call    WPP_SF_d
0x180074636  jmp     short loc_1800745E7
0x180074638  mov     [r12], r15
0x18007463c  mov     [r13+0], rsi
0x180074640  mov     rax, cs:WPP_GLOBAL_Control
0x180074647  cmp     rax, rdi
0x18007464a  jz      short loc_18007467C
0x18007464c  test    byte ptr [rax+1Ch], 1
0x180074650  jz      short loc_18007467C
0x180074652  cmp     byte ptr [rax+19h], 4
0x180074656  jb      short loc_18007467C
0x180074658  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007465d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074664  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18007466b  mov     edx, 2Ah ; '*'
0x180074670  mov     r9d, eax
0x180074673  mov     rcx, [rcx+10h]
0x180074677  call    WPP_SF_d
0x18007467c  lea     rcx, [rbp+var_30]; this
0x180074680  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180074685  mov     eax, ebx
0x180074687  mov     rbx, [rsp+80h+arg_8]
0x18007468f  add     rsp, 80h
0x180074696  pop     r15
0x180074698  pop     r14
0x18007469a  pop     r13
0x18007469c  pop     r12
0x18007469e  pop     rdi
0x18007469f  pop     rsi
0x1800746a0  pop     rbp
0x1800746a1  retn
```
