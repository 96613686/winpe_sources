# CRegistryMonitor::Initialize(ushort const *,ushort const *,IRegistryMonitorNotificationSink *,HKEY__ *)

- ea: `0x18052f5b4`
- end: `0x18052f9de`
- name: `?Initialize@CRegistryMonitor@@QEAAJPEBG0PEAUIRegistryMonitorNotificationSink@@PEAUHKEY__@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CRegistryMonitor *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IRegistryMonitorNotificationSink *, HKEY)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1802418c0`
- `0x18026c618`
- `0x18026dda8`

## callees

- `0x18002a334`
- `0x1800cfa74`
- `0x18052f5b4`
- `0x18068c010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18052f838`
- `KERNEL32!WaitForSingleObject` at `0x18052f8e8`
- `KERNEL32!WaitForSingleObject` at `0x18052f838`
- `KERNEL32!WaitForSingleObject` at `0x18052f8e8`
- `KERNEL32!CloseHandle` at `0x18052f7ab`
- `KERNEL32!CloseHandle` at `0x18052f7d6`
- `KERNEL32!CloseHandle` at `0x18052f921`
- `KERNEL32!CloseHandle` at `0x18052f954`
- `KERNEL32!CloseHandle` at `0x18052f97f`
- `KERNEL32!CloseHandle` at `0x18052f7ab`
- `KERNEL32!CloseHandle` at `0x18052f7d6`
- `KERNEL32!CloseHandle` at `0x18052f921`
- `KERNEL32!CloseHandle` at `0x18052f954`
- `KERNEL32!CloseHandle` at `0x18052f97f`
- `KERNEL32!GetLastError` at `0x18052f672`
- `KERNEL32!GetLastError` at `0x18052f722`
- `KERNEL32!GetLastError` at `0x18052f789`
- `KERNEL32!GetLastError` at `0x18052f7b5`
- `KERNEL32!GetLastError` at `0x18052f7e0`
- `KERNEL32!GetLastError` at `0x18052f849`
- `KERNEL32!GetLastError` at `0x18052f8c1`
- `KERNEL32!GetLastError` at `0x18052f90c`
- `KERNEL32!GetLastError` at `0x18052f92b`
- `KERNEL32!GetLastError` at `0x18052f95e`
- `KERNEL32!GetLastError` at `0x18052f989`
- `KERNEL32!GetLastError` at `0x18052f672`
- `KERNEL32!GetLastError` at `0x18052f722`
- `KERNEL32!GetLastError` at `0x18052f789`
- `KERNEL32!GetLastError` at `0x18052f7b5`
- `KERNEL32!GetLastError` at `0x18052f7e0`
- `KERNEL32!GetLastError` at `0x18052f849`
- `KERNEL32!GetLastError` at `0x18052f8c1`
- `KERNEL32!GetLastError` at `0x18052f90c`
- `KERNEL32!GetLastError` at `0x18052f92b`
- `KERNEL32!GetLastError` at `0x18052f95e`
- `KERNEL32!GetLastError` at `0x18052f989`
- `KERNEL32!SetEvent` at `0x18052f8b7`
- `KERNEL32!SetEvent` at `0x18052f8b7`
- `KERNEL32!CreateEventW` at `0x18052f65f`
- `KERNEL32!CreateEventW` at `0x18052f70e`
- `KERNEL32!CreateEventW` at `0x18052f745`
- `KERNEL32!CreateEventW` at `0x18052f65f`
- `KERNEL32!CreateEventW` at `0x18052f70e`
- `KERNEL32!CreateEventW` at `0x18052f745`
- `KERNEL32!CreateThread` at `0x18052f776`
- `KERNEL32!CreateThread` at `0x18052f776`
- `KERNEL32!GetExitCodeThread` at `0x18052f902`
- `KERNEL32!GetExitCodeThread` at `0x18052f902`

## pseudocode

```c
__int64 __fastcall CRegistryMonitor::Initialize(
        CRegistryMonitor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IRegistryMonitorNotificationSink *a4)
{
  signed int v6; // ebx
  const unsigned __int16 *v7; // r11
  HKEY v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int16 *v11; // rcx
  HANDLE EventW; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  signed int v15; // eax
  HANDLE *v16; // r14
  HANDLE v17; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  void *v20; // rcx
  signed int v21; // eax
  signed int v22; // eax
  DWORD v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  void *v28; // rcx
  signed int v29; // eax
  signed int v30; // eax
  DWORD ExitCode; // [rsp+60h] [rbp+8h] BYREF

  ExitCode = 0;
  *((_QWORD *)this + 137) = -2147483647;
  v6 = StringCchCopyW((unsigned __int16 *)this + 24, 0x104u, a2);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 11;
LABEL_6:
      v10 = (unsigned int)v6;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_3f6ebc25c9733d74d8afc52d6fef8389_Traceguids, v10);
      return (unsigned int)v6;
    }
    return (unsigned int)v6;
  }
  v11 = (unsigned __int16 *)((char *)this + 568);
  if ( v7 )
  {
    v6 = StringCchCopyW(v11, 0x104u, v7);
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 12;
        goto LABEL_6;
      }
      return (unsigned int)v6;
    }
  }
  else
  {
    *v11 = 0;
  }
  *((_QWORD *)this + 136) = a4;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( EventW )
  {
    v14 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = v14;
    if ( v14 )
    {
      v17 = CreateEventW(0, 1, 0, 0);
      v16 = (HANDLE *)((char *)this + 24);
      *((_QWORD *)this + 3) = v17;
      if ( v17 )
      {
        Thread = CreateThread(0, 0, CThread::staticThreadProc, this, 0, (LPDWORD)this + 8);
        *((_QWORD *)this + 1) = Thread;
        if ( Thread )
          goto LABEL_46;
      }
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v15 = GetLastError();
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      v16 = (HANDLE *)((char *)this + 24);
    }
    if ( v6 < 0 )
    {
      v20 = (void *)*((_QWORD *)this + 2);
      if ( v20 )
      {
        if ( !CloseHandle(v20) )
        {
          v21 = GetLastError();
          v6 = v21;
          if ( v21 > 0 )
            v6 = (unsigned __int16)v21 | 0x80070000;
        }
        *((_QWORD *)this + 2) = 0;
      }
      if ( *v16 )
      {
        if ( !CloseHandle(*v16) )
        {
          v22 = GetLastError();
          v6 = v22;
          if ( v22 > 0 )
            v6 = (unsigned __int16)v22 | 0x80070000;
        }
        *v16 = 0;
      }
      if ( v6 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 14;
          goto LABEL_6;
        }
        return (unsigned int)v6;
      }
    }
LABEL_46:
    v23 = WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
    if ( v23 )
    {
      if ( v23 == 258 )
      {
        v6 = -2147023436;
        goto LABEL_53;
      }
      v24 = GetLastError();
      v6 = v24;
      if ( v24 > 0 )
        v6 = (unsigned __int16)v24 | 0x80070000;
      if ( v6 < 0 )
      {
LABEL_53:
        v10 = (unsigned int)v6;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 15;
          goto LABEL_7;
        }
        return (unsigned int)v6;
      }
    }
    else
    {
      v6 = 0;
      if ( *((_BYTE *)this + 36) )
        return (unsigned int)v6;
    }
    v6 = 0;
    if ( *((_QWORD *)this + 1) )
    {
      if ( !SetEvent(*v16) )
      {
        v25 = GetLastError();
        v6 = v25;
        if ( v25 > 0 )
          v6 = (unsigned __int16)v25 | 0x80070000;
      }
      (*(void (__fastcall **)(CRegistryMonitor *))(*(_QWORD *)this + 32LL))(this);
      if ( WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF) )
      {
        v6 = -2147418113;
      }
      else if ( !GetExitCodeThread(*((HANDLE *)this + 1), &ExitCode) )
      {
        v26 = GetLastError();
        v6 = v26;
        if ( v26 > 0 )
          v6 = (unsigned __int16)v26 | 0x80070000;
      }
      if ( !CloseHandle(*((HANDLE *)this + 1)) )
      {
        v27 = GetLastError();
        v6 = v27;
        if ( v27 > 0 )
          v6 = (unsigned __int16)v27 | 0x80070000;
      }
      *((_QWORD *)this + 1) = 0;
      *((_DWORD *)this + 8) = 0;
    }
    v28 = (void *)*((_QWORD *)this + 2);
    if ( v28 )
    {
      if ( !CloseHandle(v28) )
      {
        v29 = GetLastError();
        v6 = v29;
        if ( v29 > 0 )
          v6 = (unsigned __int16)v29 | 0x80070000;
      }
      *((_QWORD *)this + 2) = 0;
    }
    if ( *v16 )
    {
      if ( !CloseHandle(*v16) )
      {
        v30 = GetLastError();
        v6 = v30;
        if ( v30 > 0 )
          v6 = (unsigned __int16)v30 | 0x80070000;
      }
      *v16 = 0;
    }
    if ( v6 >= 0 )
      return ExitCode;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 16;
      goto LABEL_6;
    }
    return (unsigned int)v6;
  }
  v13 = GetLastError();
  v6 = v13;
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 13;
    goto LABEL_6;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18052f5b4  push    rbx
0x18052f5b6  push    rsi
0x18052f5b7  push    rdi
0x18052f5b8  push    r14
0x18052f5ba  sub     rsp, 38h
0x18052f5be  mov     rsi, r9
0x18052f5c1  mov     [rsp+58h+ExitCode], 0
0x18052f5c9  mov     r11, r8
0x18052f5cc  mov     rdi, rcx
0x18052f5cf  mov     qword ptr [rcx+448h], 0FFFFFFFF80000001h
0x18052f5da  mov     r8, rdx; unsigned __int16 *
0x18052f5dd  mov     r14d, 104h
0x18052f5e3  add     rcx, 30h ; '0'; unsigned __int16 *
0x18052f5e7  mov     edx, r14d; unsigned __int64
0x18052f5ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18052f5ef  mov     ebx, eax
0x18052f5f1  test    eax, eax
0x18052f5f3  jns     short loc_18052F63D
0x18052f5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f5fc  lea     rax, WPP_GLOBAL_Control
0x18052f603  cmp     rcx, rax
0x18052f606  jz      loc_18052F9D2
0x18052f60c  test    byte ptr [rcx+1Ch], 1
0x18052f610  jz      loc_18052F9D2
0x18052f616  cmp     byte ptr [rcx+19h], 2
0x18052f61a  jb      loc_18052F9D2
0x18052f620  mov     edx, 0Bh
0x18052f625  mov     r9d, ebx
0x18052f628  mov     rcx, [rcx+10h]
0x18052f62c  lea     r8, WPP_3f6ebc25c9733d74d8afc52d6fef8389_Traceguids
0x18052f633  call    WPP_SF_d
0x18052f638  jmp     loc_18052F9D2
0x18052f63d  lea     rcx, [rdi+238h]; unsigned __int16 *
0x18052f644  test    r11, r11
0x18052f647  jnz     short loc_18052F6BC
0x18052f649  xor     eax, eax
0x18052f64b  mov     [rcx], ax
0x18052f64e  xor     r9d, r9d; lpName
0x18052f651  mov     [rdi+440h], rsi
0x18052f658  xor     r8d, r8d; bInitialState
0x18052f65b  xor     edx, edx; bManualReset
0x18052f65d  xor     ecx, ecx; lpEventAttributes
0x18052f65f  call    cs:__imp_CreateEventW
0x18052f665  mov     [rdi+28h], rax
0x18052f669  test    rax, rax
0x18052f66c  jnz     loc_18052F702
0x18052f672  call    cs:__imp_GetLastError
0x18052f678  mov     ebx, eax
0x18052f67a  test    eax, eax
0x18052f67c  jle     short loc_18052F687
0x18052f67e  movzx   ebx, ax
0x18052f681  or      ebx, 80070000h
0x18052f687  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f68e  lea     rax, WPP_GLOBAL_Control
0x18052f695  cmp     rcx, rax
0x18052f698  jz      loc_18052F9D2
0x18052f69e  test    byte ptr [rcx+1Ch], 1
0x18052f6a2  jz      loc_18052F9D2
0x18052f6a8  cmp     byte ptr [rcx+19h], 2
0x18052f6ac  jb      loc_18052F9D2
0x18052f6b2  mov     edx, 0Dh
0x18052f6b7  jmp     loc_18052F625
0x18052f6bc  mov     r8, r11; unsigned __int16 *
0x18052f6bf  mov     rdx, r14; unsigned __int64
0x18052f6c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18052f6c7  mov     ebx, eax
0x18052f6c9  test    eax, eax
0x18052f6cb  jns     short loc_18052F64E
0x18052f6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f6d4  lea     rax, WPP_GLOBAL_Control
0x18052f6db  cmp     rcx, rax
0x18052f6de  jz      loc_18052F9D2
0x18052f6e4  test    byte ptr [rcx+1Ch], 1
0x18052f6e8  jz      loc_18052F9D2
0x18052f6ee  cmp     byte ptr [rcx+19h], 2
0x18052f6f2  jb      loc_18052F9D2
0x18052f6f8  mov     edx, 0Ch
0x18052f6fd  jmp     loc_18052F625
0x18052f702  xor     r9d, r9d; lpName
0x18052f705  xor     r8d, r8d; bInitialState
0x18052f708  xor     ecx, ecx; lpEventAttributes
0x18052f70a  lea     edx, [r9+1]; bManualReset
0x18052f70e  call    cs:__imp_CreateEventW
0x18052f714  mov     [rdi+10h], rax
0x18052f718  mov     esi, 80070000h
0x18052f71d  test    rax, rax
0x18052f720  jnz     short loc_18052F739
0x18052f722  call    cs:__imp_GetLastError
0x18052f728  mov     ebx, eax
0x18052f72a  test    eax, eax
0x18052f72c  jle     short loc_18052F733
0x18052f72e  movzx   ebx, ax
0x18052f731  or      ebx, esi
0x18052f733  lea     r14, [rdi+18h]
0x18052f737  jmp     short loc_18052F79A
0x18052f739  xor     r9d, r9d; lpName
0x18052f73c  xor     r8d, r8d; bInitialState
0x18052f73f  xor     ecx, ecx; lpEventAttributes
0x18052f741  lea     edx, [r9+1]; bManualReset
0x18052f745  call    cs:__imp_CreateEventW
0x18052f74b  lea     r14, [rdi+18h]
0x18052f74f  mov     [r14], rax
0x18052f752  test    rax, rax
0x18052f755  jz      short loc_18052F789
0x18052f757  lea     rax, [rdi+20h]
0x18052f75b  mov     r9, rdi; lpParameter
0x18052f75e  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18052f763  lea     r8, ?staticThreadProc@CThread@@CAKPEAX@Z; lpStartAddress
0x18052f76a  xor     edx, edx; dwStackSize
0x18052f76c  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18052f774  xor     ecx, ecx; lpThreadAttributes
0x18052f776  call    cs:__imp_CreateThread
0x18052f77c  mov     [rdi+8], rax
0x18052f780  test    rax, rax
0x18052f783  jnz     loc_18052F831
0x18052f789  call    cs:__imp_GetLastError
0x18052f78f  mov     ebx, eax
0x18052f791  test    eax, eax
0x18052f793  jle     short loc_18052F79A
0x18052f795  movzx   ebx, ax
0x18052f798  or      ebx, esi
0x18052f79a  test    ebx, ebx
0x18052f79c  jns     loc_18052F831
0x18052f7a2  mov     rcx, [rdi+10h]; hObject
0x18052f7a6  test    rcx, rcx
0x18052f7a9  jz      short loc_18052F7CE
0x18052f7ab  call    cs:__imp_CloseHandle
0x18052f7b1  test    eax, eax
0x18052f7b3  jnz     short loc_18052F7C6
0x18052f7b5  call    cs:__imp_GetLastError
0x18052f7bb  mov     ebx, eax
0x18052f7bd  test    eax, eax
0x18052f7bf  jle     short loc_18052F7C6
0x18052f7c1  movzx   ebx, ax
0x18052f7c4  or      ebx, esi
0x18052f7c6  mov     qword ptr [rdi+10h], 0
0x18052f7ce  mov     rcx, [r14]; hObject
0x18052f7d1  test    rcx, rcx
0x18052f7d4  jz      short loc_18052F7F8
0x18052f7d6  call    cs:__imp_CloseHandle
0x18052f7dc  test    eax, eax
0x18052f7de  jnz     short loc_18052F7F1
0x18052f7e0  call    cs:__imp_GetLastError
0x18052f7e6  mov     ebx, eax
0x18052f7e8  test    eax, eax
0x18052f7ea  jle     short loc_18052F7F1
0x18052f7ec  movzx   ebx, ax
0x18052f7ef  or      ebx, esi
0x18052f7f1  mov     qword ptr [r14], 0
0x18052f7f8  test    ebx, ebx
0x18052f7fa  jns     short loc_18052F831
0x18052f7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f803  lea     rax, WPP_GLOBAL_Control
0x18052f80a  cmp     rcx, rax
0x18052f80d  jz      loc_18052F9D2
0x18052f813  test    byte ptr [rcx+1Ch], 1
0x18052f817  jz      loc_18052F9D2
0x18052f81d  cmp     byte ptr [rcx+19h], 2
0x18052f821  jb      loc_18052F9D2
0x18052f827  mov     edx, 0Eh
0x18052f82c  jmp     loc_18052F625
0x18052f831  mov     rcx, [rdi+10h]; hHandle
0x18052f835  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18052f838  call    cs:__imp_WaitForSingleObject
0x18052f83e  test    eax, eax
0x18052f840  jz      short loc_18052F89D
0x18052f842  cmp     eax, 102h
0x18052f847  jz      short loc_18052F860
0x18052f849  call    cs:__imp_GetLastError
0x18052f84f  mov     ebx, eax
0x18052f851  test    eax, eax
0x18052f853  jle     short loc_18052F85A
0x18052f855  movzx   ebx, ax
0x18052f858  or      ebx, esi
0x18052f85a  test    ebx, ebx
0x18052f85c  jns     short loc_18052F8A8
0x18052f85e  jmp     short loc_18052F865
0x18052f860  mov     ebx, 800705B4h
0x18052f865  mov     r9d, ebx
0x18052f868  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f86f  lea     rax, WPP_GLOBAL_Control
0x18052f876  cmp     rcx, rax
0x18052f879  jz      loc_18052F9D2
0x18052f87f  test    byte ptr [rcx+1Ch], 1
0x18052f883  jz      loc_18052F9D2
0x18052f889  cmp     byte ptr [rcx+19h], 2
0x18052f88d  jb      loc_18052F9D2
0x18052f893  mov     edx, 0Fh
0x18052f898  jmp     loc_18052F628
0x18052f89d  xor     ebx, ebx
0x18052f89f  cmp     [rdi+24h], bl
0x18052f8a2  jnz     loc_18052F9D2
0x18052f8a8  xor     ebx, ebx
0x18052f8aa  cmp     [rdi+8], rbx
0x18052f8ae  jz      loc_18052F94B
0x18052f8b4  mov     rcx, [r14]; hEvent
0x18052f8b7  call    cs:__imp_SetEvent
0x18052f8bd  test    eax, eax
0x18052f8bf  jnz     short loc_18052F8D2
0x18052f8c1  call    cs:__imp_GetLastError
0x18052f8c7  mov     ebx, eax
0x18052f8c9  test    eax, eax
0x18052f8cb  jle     short loc_18052F8D2
0x18052f8cd  movzx   ebx, ax
0x18052f8d0  or      ebx, esi
0x18052f8d2  mov     rax, [rdi]
0x18052f8d5  mov     rcx, rdi
0x18052f8d8  mov     rax, [rax+20h]
0x18052f8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052f8e1  mov     rcx, [rdi+8]; hHandle
0x18052f8e5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18052f8e8  call    cs:__imp_WaitForSingleObject
0x18052f8ee  test    eax, eax
0x18052f8f0  jz      short loc_18052F8F9
0x18052f8f2  mov     ebx, 8000FFFFh
0x18052f8f7  jmp     short loc_18052F91D
0x18052f8f9  mov     rcx, [rdi+8]; hThread
0x18052f8fd  lea     rdx, [rsp+58h+ExitCode]; lpExitCode
0x18052f902  call    cs:__imp_GetExitCodeThread
0x18052f908  test    eax, eax
0x18052f90a  jnz     short loc_18052F91D
0x18052f90c  call    cs:__imp_GetLastError
0x18052f912  mov     ebx, eax
0x18052f914  test    eax, eax
0x18052f916  jle     short loc_18052F91D
0x18052f918  movzx   ebx, ax
0x18052f91b  or      ebx, esi
0x18052f91d  mov     rcx, [rdi+8]; hObject
0x18052f921  call    cs:__imp_CloseHandle
0x18052f927  test    eax, eax
0x18052f929  jnz     short loc_18052F93C
0x18052f92b  call    cs:__imp_GetLastError
0x18052f931  mov     ebx, eax
0x18052f933  test    eax, eax
0x18052f935  jle     short loc_18052F93C
0x18052f937  movzx   ebx, ax
0x18052f93a  or      ebx, esi
0x18052f93c  mov     qword ptr [rdi+8], 0
0x18052f944  mov     dword ptr [rdi+20h], 0
0x18052f94b  mov     rcx, [rdi+10h]; hObject
0x18052f94f  test    rcx, rcx
0x18052f952  jz      short loc_18052F977
0x18052f954  call    cs:__imp_CloseHandle
0x18052f95a  test    eax, eax
0x18052f95c  jnz     short loc_18052F96F
0x18052f95e  call    cs:__imp_GetLastError
0x18052f964  mov     ebx, eax
0x18052f966  test    eax, eax
0x18052f968  jle     short loc_18052F96F
0x18052f96a  movzx   ebx, ax
0x18052f96d  or      ebx, esi
0x18052f96f  mov     qword ptr [rdi+10h], 0
0x18052f977  mov     rcx, [r14]; hObject
0x18052f97a  test    rcx, rcx
0x18052f97d  jz      short loc_18052F9A1
0x18052f97f  call    cs:__imp_CloseHandle
0x18052f985  test    eax, eax
0x18052f987  jnz     short loc_18052F99A
0x18052f989  call    cs:__imp_GetLastError
0x18052f98f  mov     ebx, eax
0x18052f991  test    eax, eax
0x18052f993  jle     short loc_18052F99A
0x18052f995  movzx   ebx, ax
0x18052f998  or      ebx, esi
0x18052f99a  mov     qword ptr [r14], 0
0x18052f9a1  test    ebx, ebx
0x18052f9a3  jns     short loc_18052F9CE
0x18052f9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18052f9ac  lea     rax, WPP_GLOBAL_Control
0x18052f9b3  cmp     rcx, rax
0x18052f9b6  jz      short loc_18052F9D2
0x18052f9b8  test    byte ptr [rcx+1Ch], 1
0x18052f9bc  jz      short loc_18052F9D2
0x18052f9be  cmp     byte ptr [rcx+19h], 2
0x18052f9c2  jb      short loc_18052F9D2
0x18052f9c4  mov     edx, 10h
0x18052f9c9  jmp     loc_18052F625
0x18052f9ce  mov     ebx, [rsp+58h+ExitCode]
0x18052f9d2  mov     eax, ebx
0x18052f9d4  add     rsp, 38h
0x18052f9d8  pop     r14
0x18052f9da  pop     rdi
0x18052f9db  pop     rsi
0x18052f9dc  pop     rbx
0x18052f9dd  retn
```
