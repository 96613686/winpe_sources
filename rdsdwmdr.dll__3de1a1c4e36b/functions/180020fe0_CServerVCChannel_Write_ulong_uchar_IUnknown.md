# CServerVCChannel::Write(ulong,uchar *,IUnknown *)

- ea: `0x180020fe0`
- end: `0x18002135e`
- name: `?Write@CServerVCChannel@@UEAAJKPEAEPEAUIUnknown@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(CServerVCChannel *this, DWORD, unsigned __int8 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180012e60`
- `0x1800144c8`
- `0x18001d04c`
- `0x18001d114`
- `0x18001ef44`
- `0x180020fe0`
- `0x1800215b0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002133e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002133e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002104b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002104b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021174`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002117e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002128e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002117e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002128e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002113e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002113e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180021279`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180021279`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Write(CServerVCChannel *this, DWORD a2, unsigned __int8 *a3, struct IUnknown *a4)
{
  CTSCriticalSection *v4; // rbx
  HANDLE EventW; // rax
  void *v10; // r13
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edi
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  BOOL v17; // edi
  signed int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  BOOL OverlappedResult; // ebx
  unsigned int v22; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  char *v24; // [rsp+30h] [rbp-30h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+A0h] [rbp+40h] BYREF
  LPCVOID lpBuffer; // [rsp+B0h] [rbp+50h]

  lpBuffer = a3;
  v4 = (CServerVCChannel *)((char *)this + 56);
  v24 = (char *)this + 56;
  NumberOfBytesWritten = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
    return 2147943076LL;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v10 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
    return (unsigned int)LastError;
  }
  Overlapped.hEvent = EventW;
  Overlapped.Pointer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v13 = dword_180044CF8++;
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v16,
      v14,
      v13,
      a2,
      v24,
      Overlapped.Internal,
      Overlapped.InternalHigh,
      Overlapped.Pointer,
      Overlapped.hEvent);
  }
  v17 = WriteFile(*((HANDLE *)this + 43), lpBuffer, a2, &NumberOfBytesWritten, &Overlapped);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
  if ( v17 )
    goto LABEL_43;
  if ( GetLastError() != 997 )
    goto LABEL_34;
  if ( !WaitForSingleObject(v10, 0xFFFFFFFF) )
    goto LABEL_27;
  v18 = GetLastError();
  LastError = v18;
  if ( v18 > 0 )
    LastError = (unsigned __int16)v18 | 0x80070000;
  if ( LastError >= 0 )
  {
LABEL_27:
    v24 = (char *)v4;
    CTSCriticalSection::Lock(v4);
    if ( (*((_BYTE *)this + 36) & 4) != 0 )
    {
      LastError = -2147024220;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v20,
          (__int64)"ERROR_HANDLES_CLOSED",
          164);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
      goto LABEL_47;
    }
    OverlappedResult = GetOverlappedResult(*((HANDLE *)this + 43), &Overlapped, &NumberOfBytesWritten, 0);
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v24);
    if ( !OverlappedResult )
    {
LABEL_34:
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v22,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_47;
    }
LABEL_43:
    if ( a4 )
    {
      lpVtbl = a4->lpVtbl;
      v24 = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *, char **))lpVtbl->QueryInterface)(
             a4,
             &IID_IWTSWriteCallback,
             &v24) >= 0 )
      {
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, 0);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    LastError = 0;
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v19,
      (__int64)"WaitForSingleObject",
      LastError);
  }
LABEL_47:
  CloseHandle(v10);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180020fe0  mov     [rsp-38h+arg_8], rbx
0x180020fe5  mov     [rsp-38h+lpBuffer], r8
0x180020fea  push    rbp
0x180020feb  push    rsi
0x180020fec  push    rdi
0x180020fed  push    r12
0x180020fef  push    r13
0x180020ff1  push    r14
0x180020ff3  push    r15
0x180020ff5  mov     rbp, rsp
0x180020ff8  sub     rsp, 60h
0x180020ffc  lea     rbx, [rcx+38h]
0x180021000  xorps   xmm0, xmm0
0x180021003  mov     r15, rcx
0x180021006  mov     [rbp+var_30], rbx
0x18002100a  xor     edi, edi
0x18002100c  mov     rcx, rbx; this
0x18002100f  mov     r12, r9
0x180021012  mov     [rbp+NumberOfBytesWritten], edi
0x180021015  mov     r14d, edx
0x180021018  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18002101c  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180021020  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180021025  test    byte ptr [r15+24h], 4
0x18002102a  jz      short loc_18002103F
0x18002102c  lea     rcx, [rbp+var_30]; this
0x180021030  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180021035  mov     eax, 800702A4h
0x18002103a  jmp     loc_180021346
0x18002103f  xor     r9d, r9d; lpName
0x180021042  xor     r8d, r8d; bInitialState
0x180021045  xor     ecx, ecx; lpEventAttributes
0x180021047  lea     edx, [r9+1]; bManualReset
0x18002104b  call    cs:__imp_CreateEventW
0x180021051  mov     r13, rax
0x180021054  test    rax, rax
0x180021057  jnz     short loc_1800210CC
0x180021059  call    cs:__imp_GetLastError
0x18002105f  mov     edi, eax
0x180021061  mov     rax, cs:WPP_GLOBAL_Control
0x180021068  lea     rsi, WPP_GLOBAL_Control
0x18002106f  cmp     rax, rsi
0x180021072  jz      short loc_1800210A7
0x180021074  test    byte ptr [rax+1Ch], 8
0x180021078  jz      short loc_1800210A7
0x18002107a  cmp     byte ptr [rax+19h], 2
0x18002107e  jb      short loc_1800210A7
0x180021080  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180021085  mov     rcx, cs:WPP_GLOBAL_Control
0x18002108c  lea     edx, [r13+1Ch]
0x180021090  mov     r9d, eax
0x180021093  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x180021097  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18002109e  mov     rcx, [rcx+10h]
0x1800210a2  call    WPP_SF_Dd
0x1800210a7  test    edi, edi
0x1800210a9  jle     short loc_1800210B4
0x1800210ab  movzx   edi, di
0x1800210ae  or      edi, 80070000h
0x1800210b4  test    edi, edi
0x1800210b6  lea     rcx, [rbp+var_30]; this
0x1800210ba  mov     eax, 80004005h
0x1800210bf  cmovns  edi, eax
0x1800210c2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800210c7  jmp     loc_180021344
0x1800210cc  mov     [rbp+Overlapped.hEvent], r13
0x1800210d0  mov     qword ptr [rbp+Overlapped.10h], rdi
0x1800210d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800210db  lea     rsi, WPP_GLOBAL_Control
0x1800210e2  cmp     rax, rsi
0x1800210e5  jz      short loc_180021123
0x1800210e7  test    byte ptr [rax+1Ch], 1
0x1800210eb  jz      short loc_180021123
0x1800210ed  cmp     byte ptr [rax+19h], 5
0x1800210f1  jb      short loc_180021123
0x1800210f3  mov     edi, cs:dword_180044CF8
0x1800210f9  lea     eax, [rdi+1]
0x1800210fc  mov     cs:dword_180044CF8, eax
0x180021102  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180021107  mov     rcx, cs:WPP_GLOBAL_Control
0x18002110e  mov     r9d, eax
0x180021111  mov     [rsp+60h+var_38], r14d
0x180021116  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x18002111a  mov     rcx, [rcx+10h]
0x18002111e  call    WPP_SF_Ddd
0x180021123  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180021127  lea     rax, [rbp+Overlapped]
0x18002112b  mov     rcx, [r15+158h]; hFile
0x180021132  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180021136  mov     r8d, r14d; nNumberOfBytesToWrite
0x180021139  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x18002113e  call    cs:__imp_WriteFile
0x180021144  lea     rcx, [rbp+var_30]; this
0x180021148  mov     edi, eax
0x18002114a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002114f  test    edi, edi
0x180021151  jnz     loc_1800212EC
0x180021157  call    cs:__imp_GetLastError
0x18002115d  mov     r14d, 80070000h
0x180021163  cmp     eax, 3E5h
0x180021168  jnz     loc_18002128E
0x18002116e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021171  mov     rcx, r13; hHandle
0x180021174  call    cs:__imp_WaitForSingleObject
0x18002117a  test    eax, eax
0x18002117c  jz      short loc_1800211F1
0x18002117e  call    cs:__imp_GetLastError
0x180021184  mov     edi, eax
0x180021186  test    eax, eax
0x180021188  jle     short loc_180021190
0x18002118a  movzx   edi, ax
0x18002118d  or      edi, r14d
0x180021190  test    edi, edi
0x180021192  jns     short loc_1800211F1
0x180021194  mov     rax, cs:WPP_GLOBAL_Control
0x18002119b  cmp     rax, rsi
0x18002119e  jz      loc_18002133B
0x1800211a4  test    byte ptr [rax+1Ch], 8
0x1800211a8  jz      loc_18002133B
0x1800211ae  cmp     byte ptr [rax+19h], 2
0x1800211b2  jb      loc_18002133B
0x1800211b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800211bd  lea     rcx, aWaitforsingleo_0; "WaitForSingleObject"
0x1800211c4  mov     [rsp+60h+var_38], edi
0x1800211c8  mov     [rsp+60h+lpOverlapped], rcx
0x1800211cd  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800211d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211db  mov     edx, 1Eh
0x1800211e0  mov     r9d, eax
0x1800211e3  mov     rcx, [rcx+10h]
0x1800211e7  call    WPP_SF_DsD
0x1800211ec  jmp     loc_18002133B
0x1800211f1  mov     rcx, rbx; this
0x1800211f4  mov     [rbp+var_30], rbx
0x1800211f8  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800211fd  test    byte ptr [r15+24h], 4
0x180021202  jz      short loc_180021267
0x180021204  mov     edi, 800702A4h
0x180021209  mov     rax, cs:WPP_GLOBAL_Control
0x180021210  cmp     rax, rsi
0x180021213  jz      short loc_180021259
0x180021215  test    byte ptr [rax+1Ch], 8
0x180021219  jz      short loc_180021259
0x18002121b  cmp     byte ptr [rax+19h], 2
0x18002121f  jb      short loc_180021259
0x180021221  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180021226  lea     rcx, aErrorHandlesCl; "ERROR_HANDLES_CLOSED"
0x18002122d  mov     [rsp+60h+var_38], 800702A4h
0x180021235  mov     [rsp+60h+lpOverlapped], rcx
0x18002123a  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180021241  mov     rcx, cs:WPP_GLOBAL_Control
0x180021248  mov     edx, 1Fh
0x18002124d  mov     r9d, eax
0x180021250  mov     rcx, [rcx+10h]
0x180021254  call    WPP_SF_DsD
0x180021259  lea     rcx, [rbp+var_30]; this
0x18002125d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180021262  jmp     loc_18002133B
0x180021267  mov     rcx, [r15+158h]; hFile
0x18002126e  lea     r8, [rbp+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x180021272  xor     r9d, r9d; bWait
0x180021275  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180021279  call    cs:__imp_GetOverlappedResult
0x18002127f  lea     rcx, [rbp+var_30]; this
0x180021283  mov     ebx, eax
0x180021285  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002128a  test    ebx, ebx
0x18002128c  jnz     short loc_1800212EC
0x18002128e  call    cs:__imp_GetLastError
0x180021294  mov     edi, eax
0x180021296  mov     rax, cs:WPP_GLOBAL_Control
0x18002129d  cmp     rax, rsi
0x1800212a0  jz      short loc_1800212D6
0x1800212a2  test    byte ptr [rax+1Ch], 8
0x1800212a6  jz      short loc_1800212D6
0x1800212a8  cmp     byte ptr [rax+19h], 2
0x1800212ac  jb      short loc_1800212D6
0x1800212ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800212b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212ba  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800212c1  mov     edx, 20h ; ' '
0x1800212c6  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x1800212ca  mov     r9d, eax
0x1800212cd  mov     rcx, [rcx+10h]
0x1800212d1  call    WPP_SF_Dd
0x1800212d6  test    edi, edi
0x1800212d8  jle     short loc_1800212E0
0x1800212da  movzx   edi, di
0x1800212dd  or      edi, r14d
0x1800212e0  test    edi, edi
0x1800212e2  mov     eax, 80004005h
0x1800212e7  cmovns  edi, eax
0x1800212ea  jmp     short loc_18002133B
0x1800212ec  test    r12, r12
0x1800212ef  jz      short loc_180021339
0x1800212f1  mov     rax, [r12]
0x1800212f5  lea     r8, [rbp+var_30]
0x1800212f9  lea     rdx, IID_IWTSWriteCallback
0x180021300  mov     [rbp+var_30], 0
0x180021308  mov     rcx, r12
0x18002130b  mov     rax, [rax]
0x18002130e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021313  test    eax, eax
0x180021315  js      short loc_180021339
0x180021317  mov     rcx, [rbp+var_30]
0x18002131b  xor     edx, edx
0x18002131d  mov     rax, [rcx]
0x180021320  mov     rax, [rax+18h]
0x180021324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021329  mov     rcx, [rbp+var_30]
0x18002132d  mov     rax, [rcx]
0x180021330  mov     rax, [rax+10h]
0x180021334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021339  xor     edi, edi
0x18002133b  mov     rcx, r13; hObject
0x18002133e  call    cs:__imp_CloseHandle
0x180021344  mov     eax, edi
0x180021346  mov     rbx, [rsp+60h+arg_8]
0x18002134e  add     rsp, 60h
0x180021352  pop     r15
0x180021354  pop     r14
0x180021356  pop     r13
0x180021358  pop     r12
0x18002135a  pop     rdi
0x18002135b  pop     rsi
0x18002135c  pop     rbp
0x18002135d  retn
```
