# CRdpWindowTracker::GetWindowEnvironmentState(RDP_WINDOW_ENVIRONMENT_STATE *)

- ea: `0x14005c7f0`
- end: `0x14005ca3b`
- name: `?GetWindowEnvironmentState@CRdpWindowTracker@@UEAAJPEAURDP_WINDOW_ENVIRONMENT_STATE@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this, struct RDP_WINDOW_ENVIRONMENT_STATE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x140011054`
- `0x14005ba0c`
- `0x14005c7f0`
- `0x14006a0e2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c965`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14005c89e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14005c89e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005c892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005c892`
- `WTSAPI32!WTSFreeMemory` at `0x14005ca19`
- `WTSAPI32!WTSFreeMemory` at `0x14005ca19`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14005c937`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14005c937`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::GetWindowEnvironmentState(
        CRdpWindowTracker *this,
        struct RDP_WINDOW_ENVIRONMENT_STATE *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // ebx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  unsigned int v13; // eax
  DWORD pSessionId; // [rsp+60h] [rbp+28h] BYREF
  DWORD pBytesReturned; // [rsp+68h] [rbp+30h] BYREF
  LPWSTR ppBuffer; // [rsp+70h] [rbp+38h] BYREF
  char *v18; // [rsp+78h] [rbp+40h] BYREF

  pSessionId = 0;
  ppBuffer = 0;
  v18 = (char *)this + 8;
  pBytesReturned = 0;
  CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 8));
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pEnvironmentState");
    }
    v5 = -2147467261;
    goto LABEL_29;
  }
  *(_DWORD *)a2 = *((_DWORD *)this + 47);
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 48);
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 33;
LABEL_14:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids, v9, v8);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  if ( !WTSQuerySessionInformationW(0, pSessionId, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 34;
      goto LABEL_14;
    }
LABEL_15:
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_29;
  }
  memcpy_0((char *)a2 + 24, ppBuffer, pBytesReturned);
  *((_QWORD *)a2 + 1) = *((_QWORD *)this + 8);
  *((_QWORD *)a2 + 2) = *((_QWORD *)this + 9);
  v5 = CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(
         (LPRGNDATA *)this - 6,
         *((HRGN *)this + 10),
         (struct RDP_WINDOW_ENVIRONMENT_STATE *)((char *)a2 + 28));
  if ( v5 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v13,
      (__int64)"ConvertHrgnToRdpRegionUsingBuffer() failed",
      v5);
  }
LABEL_29:
  if ( ppBuffer )
  {
    WTSFreeMemory(ppBuffer);
    ppBuffer = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14005c7f0  push    rbp
0x14005c7f2  push    rbx
0x14005c7f3  push    rsi
0x14005c7f4  push    rdi
0x14005c7f5  mov     rbp, rsp
0x14005c7f8  sub     rsp, 38h
0x14005c7fc  mov     rdi, rcx
0x14005c7ff  mov     [rbp+pSessionId], 0
0x14005c806  add     rcx, 8; this
0x14005c80a  mov     [rbp+ppBuffer], 0
0x14005c812  mov     [rbp+arg_18], rcx
0x14005c816  mov     rbx, rdx
0x14005c819  mov     [rbp+arg_8], 0
0x14005c820  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005c825  test    rbx, rbx
0x14005c828  jnz     short loc_14005C881
0x14005c82a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c831  lea     rax, WPP_GLOBAL_Control
0x14005c838  cmp     rcx, rax
0x14005c83b  jz      short loc_14005C877
0x14005c83d  test    byte ptr [rcx+1Ch], 8
0x14005c841  jz      short loc_14005C877
0x14005c843  cmp     byte ptr [rcx+19h], 2
0x14005c847  jb      short loc_14005C877
0x14005c849  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c84e  lea     rcx, aPenvironmentst; "pEnvironmentState"
0x14005c855  mov     r9d, eax
0x14005c858  mov     [rsp+38h+pBytesReturned], rcx
0x14005c85d  lea     edx, [rbx+20h]
0x14005c860  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c867  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c86e  mov     rcx, [rcx+10h]
0x14005c872  call    WPP_SF_Ds
0x14005c877  mov     ebx, 80004003h
0x14005c87c  jmp     loc_14005CA10
0x14005c881  mov     eax, [rdi+0BCh]
0x14005c887  mov     [rbx], eax
0x14005c889  mov     eax, [rdi+0C0h]
0x14005c88f  mov     [rbx+4], eax
0x14005c892  call    cs:__imp_GetCurrentProcessId
0x14005c898  mov     ecx, eax; dwProcessId
0x14005c89a  lea     rdx, [rbp+pSessionId]; pSessionId
0x14005c89e  call    cs:__imp_ProcessIdToSessionId
0x14005c8a4  test    eax, eax
0x14005c8a6  jnz     short loc_14005C91F
0x14005c8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c8af  lea     rax, WPP_GLOBAL_Control
0x14005c8b6  mov     edi, 80070000h
0x14005c8bb  cmp     rcx, rax
0x14005c8be  jz      short loc_14005C905
0x14005c8c0  test    byte ptr [rcx+1Ch], 8
0x14005c8c4  jz      short loc_14005C905
0x14005c8c6  cmp     byte ptr [rcx+19h], 2
0x14005c8ca  jb      short loc_14005C905
0x14005c8cc  call    cs:__imp_GetLastError
0x14005c8d2  mov     ebx, eax
0x14005c8d4  test    eax, eax
0x14005c8d6  jle     short loc_14005C8DD
0x14005c8d8  movzx   ebx, ax
0x14005c8db  or      ebx, edi
0x14005c8dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c8e2  mov     edx, 21h ; '!'
0x14005c8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c8ee  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c8f5  mov     r9d, eax
0x14005c8f8  mov     dword ptr [rsp+38h+pBytesReturned], ebx
0x14005c8fc  mov     rcx, [rcx+10h]
0x14005c900  call    WPP_SF_Dd
0x14005c905  call    cs:__imp_GetLastError
0x14005c90b  mov     ebx, eax
0x14005c90d  test    eax, eax
0x14005c90f  jle     loc_14005CA10
0x14005c915  movzx   ebx, ax
0x14005c918  or      ebx, edi
0x14005c91a  jmp     loc_14005CA10
0x14005c91f  mov     edx, [rbp+pSessionId]; SessionId
0x14005c922  lea     rax, [rbp+arg_8]
0x14005c926  lea     r9, [rbp+ppBuffer]; ppBuffer
0x14005c92a  mov     [rsp+38h+pBytesReturned], rax; pBytesReturned
0x14005c92f  mov     r8d, 8; WTSInfoClass
0x14005c935  xor     ecx, ecx; hServer
0x14005c937  call    cs:__imp_WTSQuerySessionInformationW
0x14005c93d  test    eax, eax
0x14005c93f  jnz     short loc_14005C985
0x14005c941  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c948  lea     rax, WPP_GLOBAL_Control
0x14005c94f  mov     edi, 80070000h
0x14005c954  cmp     rcx, rax
0x14005c957  jz      short loc_14005C905
0x14005c959  test    byte ptr [rcx+1Ch], 8
0x14005c95d  jz      short loc_14005C905
0x14005c95f  cmp     byte ptr [rcx+19h], 2
0x14005c963  jb      short loc_14005C905
0x14005c965  call    cs:__imp_GetLastError
0x14005c96b  mov     ebx, eax
0x14005c96d  test    eax, eax
0x14005c96f  jle     short loc_14005C976
0x14005c971  movzx   ebx, ax
0x14005c974  or      ebx, edi
0x14005c976  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c97b  mov     edx, 22h ; '"'
0x14005c980  jmp     loc_14005C8E7
0x14005c985  mov     r8d, [rbp+arg_8]; Size
0x14005c989  lea     rcx, [rbx+18h]; void *
0x14005c98d  mov     rdx, [rbp+ppBuffer]; Src
0x14005c991  call    memcpy_0
0x14005c996  mov     rax, [rdi+40h]
0x14005c99a  lea     r8, [rbx+1Ch]; struct _RDPGFX_REGION *
0x14005c99e  mov     [rbx+8], rax
0x14005c9a2  lea     rcx, [rdi-30h]; this
0x14005c9a6  mov     rax, [rdi+48h]
0x14005c9aa  mov     [rbx+10h], rax
0x14005c9ae  mov     rdx, [rdi+50h]; HRGN
0x14005c9b2  call    ?ConvertHrgnToRdpRegionUsingBuffer@CRdpWindowTracker@@AEAAJPEAUHRGN__@@PEAU_RDPGFX_REGION@@@Z; CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(HRGN__ *,_RDPGFX_REGION *)
0x14005c9b7  mov     ebx, eax
0x14005c9b9  test    eax, eax
0x14005c9bb  jns     short loc_14005CA10
0x14005c9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c9c4  lea     rax, WPP_GLOBAL_Control
0x14005c9cb  cmp     rcx, rax
0x14005c9ce  jz      short loc_14005CA10
0x14005c9d0  test    byte ptr [rcx+1Ch], 8
0x14005c9d4  jz      short loc_14005CA10
0x14005c9d6  cmp     byte ptr [rcx+19h], 2
0x14005c9da  jb      short loc_14005CA10
0x14005c9dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c9e1  lea     rcx, aConverthrgntor; "ConvertHrgnToRdpRegionUsingBuffer() fai"...
0x14005c9e8  mov     [rsp+38h+var_10], ebx
0x14005c9ec  mov     [rsp+38h+pBytesReturned], rcx
0x14005c9f1  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c9ff  mov     edx, 23h ; '#'
0x14005ca04  mov     r9d, eax
0x14005ca07  mov     rcx, [rcx+10h]
0x14005ca0b  call    WPP_SF_DsD
0x14005ca10  mov     rcx, [rbp+ppBuffer]; pMemory
0x14005ca14  test    rcx, rcx
0x14005ca17  jz      short loc_14005CA27
0x14005ca19  call    cs:__imp_WTSFreeMemory
0x14005ca1f  mov     [rbp+ppBuffer], 0
0x14005ca27  lea     rcx, [rbp+arg_18]; this
0x14005ca2b  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005ca30  mov     eax, ebx
0x14005ca32  add     rsp, 38h
0x14005ca36  pop     rdi
0x14005ca37  pop     rsi
0x14005ca38  pop     rbx
0x14005ca39  pop     rbp
0x14005ca3a  retn
```
