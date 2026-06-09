# CServerVCChannel::Write(ulong,uchar *,IUnknown *)

- ea: `0x140027280`
- end: `0x140027617`
- name: `?Write@CServerVCChannel@@UEAAJKPEAEPEAUIUnknown@@@Z`
- size: `919`
- prototype: `int(CServerVCChannel *__hidden this, unsigned int, unsigned __int8 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x14000cae0`
- `0x14000d350`
- `0x14000efb8`
- `0x140027280`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400272fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002740d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400272fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002740d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027545`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002742b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002742b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400272ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400272ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400275f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400275f6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400273f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400273f4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140027530`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140027530`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Write(CServerVCChannel *this, DWORD a2, unsigned __int8 *a3, struct IUnknown *a4)
{
  CTSCriticalSection *v4; // rbx
  HANDLE EventW; // rax
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edi
  unsigned int v13; // eax
  BOOL v14; // edi
  signed int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  BOOL OverlappedResult; // ebx
  unsigned int v19; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v21; // [rsp+28h] [rbp-38h]
  char *v22; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-28h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+30h] BYREF
  LPCVOID lpBuffer; // [rsp+A0h] [rbp+40h]

  lpBuffer = a3;
  v4 = (CServerVCChannel *)((char *)this + 56);
  NumberOfBytesWritten = 0;
  v22 = (char *)this + 56;
  memset(&Overlapped, 0, sizeof(Overlapped));
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
    return 2147943076LL;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  hHandle = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
    return (unsigned int)LastError;
  }
  Overlapped.hEvent = EventW;
  Overlapped.Pointer = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = dword_14008DB0C++;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids, v13, v12, a2);
  }
  v14 = WriteFile(*((HANDLE *)this + 43), lpBuffer, a2, &NumberOfBytesWritten, &Overlapped);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
  if ( v14 )
    goto LABEL_43;
  if ( GetLastError() != 997 )
    goto LABEL_34;
  if ( !WaitForSingleObject(hHandle, 0xFFFFFFFF) )
    goto LABEL_27;
  v15 = GetLastError();
  LastError = v15;
  if ( v15 > 0 )
    LastError = (unsigned __int16)v15 | 0x80070000;
  if ( LastError >= 0 )
  {
LABEL_27:
    v22 = (char *)v4;
    CTSCriticalSection::Lock(v4);
    if ( (*((_BYTE *)this + 36) & 4) != 0 )
    {
      LastError = -2147024220;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v21) = -2147024220;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v17,
          (__int64)"ERROR_HANDLES_CLOSED",
          v21);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
      goto LABEL_47;
    }
    OverlappedResult = GetOverlappedResult(*((HANDLE *)this + 43), &Overlapped, &NumberOfBytesWritten, 0);
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
    if ( !OverlappedResult )
    {
LABEL_34:
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v19,
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
      v22 = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *, char **))lpVtbl->QueryInterface)(
             a4,
             &IID_IWTSWriteCallback,
             &v22) >= 0 )
      {
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, 0);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    LastError = 0;
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v21) = LastError;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v16,
      (__int64)"WaitForSingleObject",
      v21,
      v22);
  }
LABEL_47:
  CloseHandle(hHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140027280  mov     [rsp-28h+arg_8], rbx
0x140027285  mov     [rsp-28h+arg_18], rsi
0x14002728a  mov     [rsp-28h+lpBuffer], r8
0x14002728f  push    rbp
0x140027290  push    rdi
0x140027291  push    r12
0x140027293  push    r13
0x140027295  push    r14
0x140027297  mov     rbp, rsp
0x14002729a  sub     rsp, 60h
0x14002729e  lea     rbx, [rcx+38h]
0x1400272a2  mov     [rbp+NumberOfBytesWritten], 0
0x1400272a9  xorps   xmm0, xmm0
0x1400272ac  mov     [rbp+var_30], rbx
0x1400272b0  mov     r13, rcx
0x1400272b3  mov     r12, r9
0x1400272b6  mov     rcx, rbx; this
0x1400272b9  mov     r14d, edx
0x1400272bc  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x1400272c0  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x1400272c4  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1400272c9  test    byte ptr [r13+24h], 4
0x1400272ce  jz      short loc_1400272E3
0x1400272d0  lea     rcx, [rbp+var_30]; this
0x1400272d4  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1400272d9  mov     eax, 800702A4h
0x1400272de  jmp     loc_1400275FE
0x1400272e3  xor     r9d, r9d; lpName
0x1400272e6  xor     r8d, r8d; bInitialState
0x1400272e9  xor     ecx, ecx; lpEventAttributes
0x1400272eb  lea     edx, [r9+1]; bManualReset
0x1400272ef  call    cs:__imp_CreateEventW
0x1400272f5  mov     [rbp+hHandle], rax
0x1400272f9  test    rax, rax
0x1400272fc  jnz     short loc_140027372
0x1400272fe  call    cs:__imp_GetLastError
0x140027304  mov     edi, eax
0x140027306  mov     rax, cs:WPP_GLOBAL_Control
0x14002730d  lea     rsi, WPP_GLOBAL_Control
0x140027314  cmp     rax, rsi
0x140027317  jz      short loc_14002734D
0x140027319  test    byte ptr [rax+1Ch], 8
0x14002731d  jz      short loc_14002734D
0x14002731f  cmp     byte ptr [rax+19h], 2
0x140027323  jb      short loc_14002734D
0x140027325  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002732a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027331  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140027338  mov     edx, 1Ch
0x14002733d  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x140027341  mov     r9d, eax
0x140027344  mov     rcx, [rcx+10h]
0x140027348  call    WPP_SF_Dd
0x14002734d  test    edi, edi
0x14002734f  jle     short loc_14002735A
0x140027351  movzx   edi, di
0x140027354  or      edi, 80070000h
0x14002735a  test    edi, edi
0x14002735c  lea     rcx, [rbp+var_30]; this
0x140027360  mov     eax, 80004005h
0x140027365  cmovns  edi, eax
0x140027368  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14002736d  jmp     loc_1400275FC
0x140027372  mov     [rbp+Overlapped.hEvent], rax
0x140027376  mov     qword ptr [rbp+Overlapped.10h], 0
0x14002737e  mov     rax, cs:WPP_GLOBAL_Control
0x140027385  lea     rsi, WPP_GLOBAL_Control
0x14002738c  cmp     rax, rsi
0x14002738f  jz      short loc_1400273D9
0x140027391  test    byte ptr [rax+1Ch], 1
0x140027395  jz      short loc_1400273D9
0x140027397  cmp     byte ptr [rax+19h], 5
0x14002739b  jb      short loc_1400273D9
0x14002739d  mov     edi, cs:dword_14008DB0C
0x1400273a3  lea     eax, [rdi+1]
0x1400273a6  mov     cs:dword_14008DB0C, eax
0x1400273ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400273b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400273b8  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1400273bf  mov     edx, 1Dh
0x1400273c4  mov     dword ptr [rsp+60h+var_38], r14d
0x1400273c9  mov     r9d, eax
0x1400273cc  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x1400273d0  mov     rcx, [rcx+10h]
0x1400273d4  call    WPP_SF_DdD
0x1400273d9  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1400273dd  lea     rax, [rbp+Overlapped]
0x1400273e1  mov     rcx, [r13+158h]; hFile
0x1400273e8  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400273ec  mov     r8d, r14d; nNumberOfBytesToWrite
0x1400273ef  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x1400273f4  call    cs:__imp_WriteFile
0x1400273fa  lea     rcx, [rbp+var_30]; this
0x1400273fe  mov     edi, eax
0x140027400  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140027405  test    edi, edi
0x140027407  jnz     loc_1400275A3
0x14002740d  call    cs:__imp_GetLastError
0x140027413  mov     r14d, 80070000h
0x140027419  cmp     eax, 3E5h
0x14002741e  jnz     loc_140027545
0x140027424  mov     rcx, [rbp+hHandle]; hHandle
0x140027428  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002742b  call    cs:__imp_WaitForSingleObject
0x140027431  test    eax, eax
0x140027433  jz      short loc_1400274A8
0x140027435  call    cs:__imp_GetLastError
0x14002743b  mov     edi, eax
0x14002743d  test    eax, eax
0x14002743f  jle     short loc_140027447
0x140027441  movzx   edi, ax
0x140027444  or      edi, r14d
0x140027447  test    edi, edi
0x140027449  jns     short loc_1400274A8
0x14002744b  mov     rax, cs:WPP_GLOBAL_Control
0x140027452  cmp     rax, rsi
0x140027455  jz      loc_1400275F2
0x14002745b  test    byte ptr [rax+1Ch], 8
0x14002745f  jz      loc_1400275F2
0x140027465  cmp     byte ptr [rax+19h], 2
0x140027469  jb      loc_1400275F2
0x14002746f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140027474  lea     rcx, aWaitforsingleo_0; "WaitForSingleObject"
0x14002747b  mov     dword ptr [rsp+60h+var_38], edi
0x14002747f  mov     [rsp+60h+lpOverlapped], rcx
0x140027484  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x14002748b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027492  mov     edx, 1Eh
0x140027497  mov     r9d, eax
0x14002749a  mov     rcx, [rcx+10h]
0x14002749e  call    WPP_SF_DsD
0x1400274a3  jmp     loc_1400275F2
0x1400274a8  mov     rcx, rbx; this
0x1400274ab  mov     [rbp+var_30], rbx
0x1400274af  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1400274b4  test    byte ptr [r13+24h], 4
0x1400274b9  jz      short loc_14002751E
0x1400274bb  mov     edi, 800702A4h
0x1400274c0  mov     rax, cs:WPP_GLOBAL_Control
0x1400274c7  cmp     rax, rsi
0x1400274ca  jz      short loc_140027510
0x1400274cc  test    byte ptr [rax+1Ch], 8
0x1400274d0  jz      short loc_140027510
0x1400274d2  cmp     byte ptr [rax+19h], 2
0x1400274d6  jb      short loc_140027510
0x1400274d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400274dd  lea     rcx, aErrorHandlesCl; "ERROR_HANDLES_CLOSED"
0x1400274e4  mov     dword ptr [rsp+60h+var_38], 800702A4h
0x1400274ec  mov     [rsp+60h+lpOverlapped], rcx
0x1400274f1  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1400274f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400274ff  mov     edx, 1Fh
0x140027504  mov     r9d, eax
0x140027507  mov     rcx, [rcx+10h]
0x14002750b  call    WPP_SF_DsD
0x140027510  lea     rcx, [rbp+var_30]; this
0x140027514  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140027519  jmp     loc_1400275F2
0x14002751e  mov     rcx, [r13+158h]; hFile
0x140027525  lea     r8, [rbp+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x140027529  xor     r9d, r9d; bWait
0x14002752c  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x140027530  call    cs:__imp_GetOverlappedResult
0x140027536  lea     rcx, [rbp+var_30]; this
0x14002753a  mov     ebx, eax
0x14002753c  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140027541  test    ebx, ebx
0x140027543  jnz     short loc_1400275A3
0x140027545  call    cs:__imp_GetLastError
0x14002754b  mov     edi, eax
0x14002754d  mov     rax, cs:WPP_GLOBAL_Control
0x140027554  cmp     rax, rsi
0x140027557  jz      short loc_14002758D
0x140027559  test    byte ptr [rax+1Ch], 8
0x14002755d  jz      short loc_14002758D
0x14002755f  cmp     byte ptr [rax+19h], 2
0x140027563  jb      short loc_14002758D
0x140027565  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002756a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027571  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140027578  mov     edx, 20h ; ' '
0x14002757d  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x140027581  mov     r9d, eax
0x140027584  mov     rcx, [rcx+10h]
0x140027588  call    WPP_SF_Dd
0x14002758d  test    edi, edi
0x14002758f  jle     short loc_140027597
0x140027591  movzx   edi, di
0x140027594  or      edi, r14d
0x140027597  test    edi, edi
0x140027599  mov     eax, 80004005h
0x14002759e  cmovns  edi, eax
0x1400275a1  jmp     short loc_1400275F2
0x1400275a3  test    r12, r12
0x1400275a6  jz      short loc_1400275F0
0x1400275a8  mov     rax, [r12]
0x1400275ac  lea     r8, [rbp+var_30]
0x1400275b0  lea     rdx, IID_IWTSWriteCallback
0x1400275b7  mov     [rbp+var_30], 0
0x1400275bf  mov     rcx, r12
0x1400275c2  mov     rax, [rax]
0x1400275c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275ca  test    eax, eax
0x1400275cc  js      short loc_1400275F0
0x1400275ce  mov     rcx, [rbp+var_30]
0x1400275d2  xor     edx, edx
0x1400275d4  mov     rax, [rcx]
0x1400275d7  mov     rax, [rax+18h]
0x1400275db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275e0  mov     rcx, [rbp+var_30]
0x1400275e4  mov     rax, [rcx]
0x1400275e7  mov     rax, [rax+10h]
0x1400275eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275f0  xor     edi, edi
0x1400275f2  mov     rcx, [rbp+hHandle]; hObject
0x1400275f6  call    cs:__imp_CloseHandle
0x1400275fc  mov     eax, edi
0x1400275fe  lea     r11, [rsp+60h+var_s0]
0x140027603  mov     rbx, [r11+38h]
0x140027607  mov     rsi, [r11+48h]
0x14002760b  mov     rsp, r11
0x14002760e  pop     r14
0x140027610  pop     r13
0x140027612  pop     r12
0x140027614  pop     rdi
0x140027615  pop     rbp
0x140027616  retn
```
