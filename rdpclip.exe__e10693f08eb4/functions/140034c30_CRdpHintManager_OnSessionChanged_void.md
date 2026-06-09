# CRdpHintManager::OnSessionChanged(void)

- ea: `0x140034c30`
- end: `0x140034e2b`
- name: `?OnSessionChanged@CRdpHintManager@@UEAAJXZ`
- size: `507`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400365d0`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x140034c30`
- `0x1400366a0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034d65`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140034cdc`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140034cdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034ccf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034ccf`
- `WTSAPI32!WTSFreeMemory` at `0x140034e18`
- `WTSAPI32!WTSFreeMemory` at `0x140034e18`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140034d5b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140034d5b`

## string_xrefs

- `0x140034d34`: `ProcessIdToSessionId() failed`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::OnSessionChanged(CRdpHintManager *this)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  unsigned int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD pSessionId; // [rsp+40h] [rbp+8h] BYREF
  DWORD pBytesReturned; // [rsp+48h] [rbp+10h] BYREF
  LPWSTR ppBuffer; // [rsp+50h] [rbp+18h] BYREF

  pSessionId = 0;
  v2 = *((_QWORD *)this + 9);
  ppBuffer = 0;
  pBytesReturned = 0;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
  if ( v3 >= 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
      goto LABEL_19;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_19:
      if ( WTSQuerySessionInformationW(0, pSessionId, WTSConnectState, &ppBuffer, &pBytesReturned) )
        goto LABEL_24;
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_24:
        if ( pBytesReturned == 4 )
        {
          if ( !*(_DWORD *)ppBuffer )
            CRdpHintManager::UpdateHints(this);
        }
        else
        {
          v3 = -2147418113;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
              CurrentThreadActivityIdPrefix,
              (__int64)"WTSQuerySessionInformation( WTSConnectState ) returned a buffer of unexpected size.",
              -2147418113);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 53;
        v6 = "WTSQuerySessionInformation() failed";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 52;
      v6 = "ProcessIdToSessionId() failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 51;
    v6 = "OnDisplayChange() failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
      v4,
      (__int64)v6,
      v3);
  }
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140034c30  mov     rax, rsp
0x140034c33  mov     [rax+20h], rbx
0x140034c37  push    rdi
0x140034c38  sub     rsp, 30h
0x140034c3c  mov     dword ptr [rax+8], 0
0x140034c43  mov     rdi, rcx
0x140034c46  mov     rcx, [rcx+48h]
0x140034c4a  mov     qword ptr [rax+18h], 0
0x140034c52  mov     dword ptr [rax+10h], 0
0x140034c59  mov     rax, [rcx]
0x140034c5c  mov     rax, [rax+30h]
0x140034c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034c65  mov     ebx, eax
0x140034c67  test    eax, eax
0x140034c69  jns     short loc_140034CCF
0x140034c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c72  lea     rax, WPP_GLOBAL_Control
0x140034c79  cmp     rcx, rax
0x140034c7c  jz      loc_140034E0E
0x140034c82  test    byte ptr [rcx+1Ch], 8
0x140034c86  jz      loc_140034E0E
0x140034c8c  cmp     byte ptr [rcx+19h], 2
0x140034c90  jb      loc_140034E0E
0x140034c96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034c9b  mov     edx, 33h ; '3'
0x140034ca0  lea     rcx, aOndisplaychang; "OnDisplayChange() failed"
0x140034ca7  mov     [rsp+38h+var_10], ebx
0x140034cab  mov     [rsp+38h+pBytesReturned], rcx
0x140034cb0  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140034cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cbe  mov     r9d, eax
0x140034cc1  mov     rcx, [rcx+10h]
0x140034cc5  call    WPP_SF_DsD
0x140034cca  jmp     loc_140034E0E
0x140034ccf  call    cs:__imp_GetCurrentProcessId
0x140034cd5  mov     ecx, eax; dwProcessId
0x140034cd7  lea     rdx, [rsp+38h+pSessionId]; pSessionId
0x140034cdc  call    cs:__imp_ProcessIdToSessionId
0x140034ce2  test    eax, eax
0x140034ce4  jnz     short loc_140034D40
0x140034ce6  call    cs:__imp_GetLastError
0x140034cec  mov     ebx, eax
0x140034cee  test    eax, eax
0x140034cf0  jle     short loc_140034CFB
0x140034cf2  movzx   ebx, ax
0x140034cf5  or      ebx, 80070000h
0x140034cfb  test    ebx, ebx
0x140034cfd  jns     short loc_140034D40
0x140034cff  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d06  lea     rax, WPP_GLOBAL_Control
0x140034d0d  cmp     rcx, rax
0x140034d10  jz      loc_140034E0E
0x140034d16  test    byte ptr [rcx+1Ch], 8
0x140034d1a  jz      loc_140034E0E
0x140034d20  cmp     byte ptr [rcx+19h], 2
0x140034d24  jb      loc_140034E0E
0x140034d2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034d2f  mov     edx, 34h ; '4'
0x140034d34  lea     rcx, aProcessidtoses; "ProcessIdToSessionId() failed"
0x140034d3b  jmp     loc_140034CA7
0x140034d40  mov     edx, [rsp+38h+pSessionId]; SessionId
0x140034d44  lea     rax, [rsp+38h+arg_8]
0x140034d49  lea     r9, [rsp+38h+ppBuffer]; ppBuffer
0x140034d4e  mov     [rsp+38h+pBytesReturned], rax; pBytesReturned
0x140034d53  mov     r8d, 8; WTSInfoClass
0x140034d59  xor     ecx, ecx; hServer
0x140034d5b  call    cs:__imp_WTSQuerySessionInformationW
0x140034d61  test    eax, eax
0x140034d63  jnz     short loc_140034DB3
0x140034d65  call    cs:__imp_GetLastError
0x140034d6b  mov     ebx, eax
0x140034d6d  test    eax, eax
0x140034d6f  jle     short loc_140034D7A
0x140034d71  movzx   ebx, ax
0x140034d74  or      ebx, 80070000h
0x140034d7a  test    ebx, ebx
0x140034d7c  jns     short loc_140034DB3
0x140034d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d85  lea     rax, WPP_GLOBAL_Control
0x140034d8c  cmp     rcx, rax
0x140034d8f  jz      short loc_140034E0E
0x140034d91  test    byte ptr [rcx+1Ch], 8
0x140034d95  jz      short loc_140034E0E
0x140034d97  cmp     byte ptr [rcx+19h], 2
0x140034d9b  jb      short loc_140034E0E
0x140034d9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034da2  mov     edx, 35h ; '5'
0x140034da7  lea     rcx, aWtsquerysessio_0; "WTSQuerySessionInformation() failed"
0x140034dae  jmp     loc_140034CA7
0x140034db3  cmp     [rsp+38h+arg_8], 4
0x140034db8  jz      short loc_140034DFC
0x140034dba  mov     ebx, 8000FFFFh
0x140034dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140034dc6  lea     rax, WPP_GLOBAL_Control
0x140034dcd  cmp     rcx, rax
0x140034dd0  jz      short loc_140034E0E
0x140034dd2  test    byte ptr [rcx+1Ch], 8
0x140034dd6  jz      short loc_140034E0E
0x140034dd8  cmp     byte ptr [rcx+19h], 2
0x140034ddc  jb      short loc_140034E0E
0x140034dde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034de3  mov     edx, 36h ; '6'
0x140034de8  mov     [rsp+38h+var_10], 8000FFFFh
0x140034df0  lea     rcx, aWtsquerysessio_1; "WTSQuerySessionInformation( WTSConnectS"...
0x140034df7  jmp     loc_140034CAB
0x140034dfc  mov     rax, [rsp+38h+ppBuffer]
0x140034e01  cmp     dword ptr [rax], 0
0x140034e04  jnz     short loc_140034E0E
0x140034e06  mov     rcx, rdi; this
0x140034e09  call    ?UpdateHints@CRdpHintManager@@AEAAXXZ; CRdpHintManager::UpdateHints(void)
0x140034e0e  mov     rcx, [rsp+38h+ppBuffer]; pMemory
0x140034e13  test    rcx, rcx
0x140034e16  jz      short loc_140034E1E
0x140034e18  call    cs:__imp_WTSFreeMemory
0x140034e1e  mov     eax, ebx
0x140034e20  mov     rbx, [rsp+38h+arg_18]
0x140034e25  add     rsp, 30h
0x140034e29  pop     rdi
0x140034e2a  retn
```
