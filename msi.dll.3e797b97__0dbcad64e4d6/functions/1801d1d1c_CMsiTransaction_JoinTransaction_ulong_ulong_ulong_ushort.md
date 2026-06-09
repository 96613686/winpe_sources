# CMsiTransaction::JoinTransaction(ulong,ulong,ulong *,ushort *)

- ea: `0x1801d1d1c`
- end: `0x1801d204e`
- name: `?JoinTransaction@CMsiTransaction@@SAKKKPEAKPEAG@Z`
- size: `818`
- prototype: `static unsigned int(unsigned int, unsigned int, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1801b9230`

## callees

- `0x18000d270`
- `0x180014160`
- `0x18013a028`
- `0x18015d018`
- `0x1801c7ee0`
- `0x1801cfaa4`
- `0x1801d1628`
- `0x1801d1d1c`
- `0x1801d46f4`
- `0x18025a82c`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801d1f08`
- `KERNEL32!CloseHandle` at `0x1801d2014`
- `KERNEL32!CloseHandle` at `0x1801d1f08`
- `KERNEL32!CloseHandle` at `0x1801d2014`
- `KERNEL32!LeaveCriticalSection` at `0x1801d2027`
- `KERNEL32!LeaveCriticalSection` at `0x1801d2027`
- `KERNEL32!GetLastError` at `0x1801d1f3b`
- `KERNEL32!GetLastError` at `0x1801d1ff6`
- `KERNEL32!GetLastError` at `0x1801d1f3b`
- `KERNEL32!GetLastError` at `0x1801d1ff6`
- `KERNEL32!EnterCriticalSection` at `0x1801d1d52`
- `KERNEL32!EnterCriticalSection` at `0x1801d1d52`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1e00`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1e00`
- `KERNEL32!CreateEventW` at `0x1801d1f73`
- `KERNEL32!CreateEventW` at `0x1801d1f73`
- `KERNEL32!CreateThread` at `0x1801d1fae`
- `KERNEL32!CreateThread` at `0x1801d1fae`
- `KERNEL32!OpenProcess` at `0x1801d1f1f`
- `KERNEL32!OpenProcess` at `0x1801d1f1f`

## pseudocode

```c
__int64 __fastcall CMsiTransaction::JoinTransaction(int a1, int a2, unsigned int *a3, unsigned __int16 *a4)
{
  DWORD CallerInfo; // edi
  __int64 v9; // r10
  const unsigned __int16 *v10; // rax
  struct IUnknown *v11; // rax
  DWORD CurrentProcessId; // ebx
  DWORD v13; // ecx
  struct Node *lpVtbl; // rax
  char v15; // r8
  DWORD lpVtbl_high; // edx
  struct Node *v17; // rax
  char v18; // dl
  DWORD v19; // ecx
  struct IUnknown *v20; // rcx
  struct IUnknownVtbl *v21; // rcx
  struct IUnknownVtbl *v22; // rax
  CMsiTransaction *v23; // rcx
  struct IUnknown *v24; // rbx
  DWORD LastError; // eax
  struct IUnknownVtbl *v26; // rbx
  struct IUnknownVtbl *EventW; // rax
  unsigned int v28; // edx
  struct IUnknown *v29; // rcx
  struct IUnknownVtbl *v30; // rax
  MSIHANDLE v31; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp-20h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-1Ch] BYREF
  struct Node *v35; // [rsp+38h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF

  dwProcessId = 0;
  v35 = 0;
  hObject = 0;
  EnterCriticalSection(&g_csTransactionLock);
  if ( !CMsiTransaction::m_pMsiTransaction || CMsiTransaction::m_fRollbackDisabled )
    goto LABEL_55;
  if ( a1 != HIDWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) )
  {
    CallerInfo = 6;
    goto LABEL_58;
  }
  if ( MsiUIMessageContext::IsServiceInstalling((MsiUIMessageContext *)&g_MessageContext) )
  {
    CallerInfo = 1618;
    goto LABEL_58;
  }
  v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 96) + 80LL))(*(_QWORD *)(v9 + 96));
  if ( (int)StringCchCopyW(a4, 0x104u, v10) < 0 )
  {
    CallerInfo = 87;
    goto LABEL_58;
  }
  CallerInfo = CMsiTransaction::GetCallerInfo(&dwProcessId, &hObject);
  if ( !CallerInfo )
  {
    v11 = CMsiTransaction::m_pMsiTransaction;
    if ( SLODWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) >= 0 )
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( dwProcessId == CurrentProcessId )
      {
LABEL_14:
        CallerInfo = 0;
        goto LABEL_56;
      }
      v11 = CMsiTransaction::m_pMsiTransaction;
    }
    else
    {
      CurrentProcessId = (DWORD)CMsiTransaction::m_pMsiTransaction[3].lpVtbl;
      if ( dwProcessId == CurrentProcessId )
        goto LABEL_14;
    }
    *a3 = (unsigned int)v11[16].lpVtbl;
    CallerInfo = CMsiTransaction::GetActiveProcesses((struct CBinaryTree *)&v35);
    if ( !CallerInfo )
    {
      v13 = dwProcessId;
LABEL_18:
      lpVtbl = v35;
      v15 = 0;
      while ( lpVtbl )
      {
        if ( v13 >= LODWORD(lpVtbl->lpVtbl) )
        {
          if ( v13 <= LODWORD(lpVtbl->lpVtbl) )
          {
            lpVtbl_high = HIDWORD(lpVtbl->lpVtbl);
            v15 = 1;
            v13 = lpVtbl_high;
            if ( lpVtbl_high != CurrentProcessId && lpVtbl_high )
              goto LABEL_18;
            break;
          }
          lpVtbl = (struct Node *)lpVtbl[2].lpVtbl;
        }
        else
        {
          lpVtbl = (struct Node *)lpVtbl[1].lpVtbl;
        }
      }
      if ( v13 && v15 )
      {
LABEL_38:
        if ( (unsigned int)IsTokenAMemberOfAndHavePrivilegesAsTokenB(
                             hObject,
                             CMsiTransaction::m_pMsiTransaction[5].lpVtbl) == 1 )
        {
          v20 = CMsiTransaction::m_pMsiTransaction;
          if ( a2 )
          {
            LODWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) = a2 | 1;
          }
          else
          {
            LODWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) = 0;
            LODWORD(v20[20].lpVtbl) = 0;
          }
          LODWORD(v20[2].lpVtbl) |= 0x80000000;
          LODWORD(v20[3].lpVtbl) = dwProcessId;
          v21 = v20[4].lpVtbl;
          if ( v21 )
            CloseHandle(v21);
          v22 = (struct IUnknownVtbl *)OpenProcess(0x100000u, 0, dwProcessId);
          v24 = CMsiTransaction::m_pMsiTransaction;
          CMsiTransaction::m_pMsiTransaction[4].lpVtbl = v22;
          if ( !v22 )
          {
            LastError = GetLastError();
            v24 = CMsiTransaction::m_pMsiTransaction;
            CallerInfo = LastError;
          }
          v26 = v24[6].lpVtbl;
          CMsiTransaction::ShutdownWaitingThread(v23);
          if ( v26 )
          {
            ThreadId = 0;
            EventW = (struct IUnknownVtbl *)CreateEventW(0, 0, 0, 0);
            v29 = CMsiTransaction::m_pMsiTransaction;
            CMsiTransaction::m_pMsiTransaction[7].lpVtbl = EventW;
            if ( EventW )
            {
              v30 = (struct IUnknownVtbl *)CreateThread(0, 0, WaitOnClientProcessThread, 0, 0, &ThreadId);
              v29 = CMsiTransaction::m_pMsiTransaction;
              CMsiTransaction::m_pMsiTransaction[6].lpVtbl = v30;
            }
            if ( !v29[6].lpVtbl )
            {
              v31 = HIDWORD(v29[2].lpVtbl);
              if ( v31 )
              {
                MsiCloseHandle(v31);
                v29 = CMsiTransaction::m_pMsiTransaction;
              }
              if ( v29 )
                CMsiTransaction::`scalar deleting destructor'((CMsiTransaction *)v29, v28);
              CMsiTransaction::m_pMsiTransaction = 0;
              CallerInfo = GetLastError();
            }
          }
          goto LABEL_56;
        }
        goto LABEL_55;
      }
LABEL_28:
      v17 = v35;
      v18 = 0;
      while ( v17 )
      {
        if ( CurrentProcessId >= LODWORD(v17->lpVtbl) )
        {
          if ( CurrentProcessId <= LODWORD(v17->lpVtbl) )
          {
            v19 = HIDWORD(v17->lpVtbl);
            v18 = 1;
            CurrentProcessId = v19;
            if ( v19 != dwProcessId && v19 )
              goto LABEL_28;
            break;
          }
          v17 = (struct Node *)v17[2].lpVtbl;
        }
        else
        {
          v17 = (struct Node *)v17[1].lpVtbl;
        }
      }
      if ( CurrentProcessId && v18 )
        goto LABEL_38;
LABEL_55:
      CallerInfo = 5;
    }
  }
LABEL_56:
  if ( hObject )
    CloseHandle(hObject);
LABEL_58:
  LeaveCriticalSection(&g_csTransactionLock);
  CBinaryTree::DeleteTree((CBinaryTree *)&v35, v35);
  return CallerInfo;
}

```

## disassembly

```asm
0x1801d1d1c  push    rbp
0x1801d1d1e  push    rbx
0x1801d1d1f  push    rsi
0x1801d1d20  push    rdi
0x1801d1d21  push    r14
0x1801d1d23  mov     rbp, rsp
0x1801d1d26  sub     rsp, 50h
0x1801d1d2a  mov     ebx, ecx
0x1801d1d2c  mov     [rbp+dwProcessId], 0
0x1801d1d33  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801d1d3a  mov     [rbp+var_18], 0
0x1801d1d42  mov     rdi, r9
0x1801d1d45  mov     [rbp+hObject], 0
0x1801d1d4d  mov     r14, r8
0x1801d1d50  mov     esi, edx
0x1801d1d52  call    cs:__imp_EnterCriticalSection
0x1801d1d59  nop     dword ptr [rax+rax+00h]
0x1801d1d5e  mov     r10, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1d65  test    r10, r10
0x1801d1d68  jz      loc_1801D2006
0x1801d1d6e  cmp     cs:?m_fRollbackDisabled@CMsiTransaction@@0_NA, 0; bool CMsiTransaction::m_fRollbackDisabled
0x1801d1d75  jnz     loc_1801D2006
0x1801d1d7b  cmp     ebx, [r10+14h]
0x1801d1d7f  jz      short loc_1801D1D8B
0x1801d1d81  mov     edi, 6
0x1801d1d86  jmp     loc_1801D2020
0x1801d1d8b  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801d1d92  call    ?IsServiceInstalling@MsiUIMessageContext@@QEAA_NXZ; MsiUIMessageContext::IsServiceInstalling(void)
0x1801d1d97  cmp     al, 1
0x1801d1d99  jnz     short loc_1801D1DA5
0x1801d1d9b  mov     edi, 652h
0x1801d1da0  jmp     loc_1801D2020
0x1801d1da5  mov     rcx, [r10+60h]
0x1801d1da9  mov     rax, [rcx]
0x1801d1dac  mov     rax, [rax+50h]
0x1801d1db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1db5  mov     r8, rax; unsigned __int16 *
0x1801d1db8  mov     edx, 104h; unsigned __int64
0x1801d1dbd  mov     rcx, rdi; unsigned __int16 *
0x1801d1dc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801d1dc5  test    eax, eax
0x1801d1dc7  jns     short loc_1801D1DD3
0x1801d1dc9  mov     edi, 57h ; 'W'
0x1801d1dce  jmp     loc_1801D2020
0x1801d1dd3  lea     rdx, [rbp+hObject]; void **
0x1801d1dd7  lea     rcx, [rbp+dwProcessId]; unsigned int *
0x1801d1ddb  call    ?GetCallerInfo@CMsiTransaction@@SAKPEAKPEAPEAX@Z; CMsiTransaction::GetCallerInfo(ulong *,void * *)
0x1801d1de0  mov     edi, eax
0x1801d1de2  test    eax, eax
0x1801d1de4  jnz     loc_1801D200B
0x1801d1dea  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1df1  cmp     [rax+10h], edi
0x1801d1df4  jge     short loc_1801D1E00
0x1801d1df6  mov     ebx, [rax+18h]
0x1801d1df9  cmp     [rbp+dwProcessId], ebx
0x1801d1dfc  jnz     short loc_1801D1E21
0x1801d1dfe  jmp     short loc_1801D1E13
0x1801d1e00  call    cs:__imp_GetCurrentProcessId
0x1801d1e07  nop     dword ptr [rax+rax+00h]
0x1801d1e0c  mov     ebx, eax
0x1801d1e0e  cmp     [rbp+dwProcessId], eax
0x1801d1e11  jnz     short loc_1801D1E1A
0x1801d1e13  xor     edi, edi
0x1801d1e15  jmp     loc_1801D200B
0x1801d1e1a  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1e21  mov     eax, [rax+80h]
0x1801d1e27  lea     rcx, [rbp+var_18]; this
0x1801d1e2b  mov     [r14], eax
0x1801d1e2e  call    ?GetActiveProcesses@CMsiTransaction@@SAKAEAVCBinaryTree@@@Z; CMsiTransaction::GetActiveProcesses(CBinaryTree &)
0x1801d1e33  mov     edi, eax
0x1801d1e35  test    eax, eax
0x1801d1e37  jnz     loc_1801D200B
0x1801d1e3d  mov     ecx, [rbp+dwProcessId]
0x1801d1e40  mov     rax, [rbp+var_18]
0x1801d1e44  xor     r8b, r8b
0x1801d1e47  test    rax, rax
0x1801d1e4a  jz      short loc_1801D1E6E
0x1801d1e4c  cmp     ecx, [rax]
0x1801d1e4e  jnb     short loc_1801D1E56
0x1801d1e50  mov     rax, [rax+8]
0x1801d1e54  jmp     short loc_1801D1E47
0x1801d1e56  jbe     short loc_1801D1E5E
0x1801d1e58  mov     rax, [rax+10h]
0x1801d1e5c  jmp     short loc_1801D1E47
0x1801d1e5e  mov     edx, [rax+4]
0x1801d1e61  mov     r8b, 1
0x1801d1e64  mov     ecx, edx
0x1801d1e66  cmp     edx, ebx
0x1801d1e68  jz      short loc_1801D1E6E
0x1801d1e6a  test    edx, edx
0x1801d1e6c  jnz     short loc_1801D1E40
0x1801d1e6e  test    ecx, ecx
0x1801d1e70  jz      short loc_1801D1E77
0x1801d1e72  test    r8b, r8b
0x1801d1e75  jnz     short loc_1801D1EB4
0x1801d1e77  mov     rax, [rbp+var_18]
0x1801d1e7b  xor     dl, dl
0x1801d1e7d  test    rax, rax
0x1801d1e80  jz      short loc_1801D1EA4
0x1801d1e82  cmp     ebx, [rax]
0x1801d1e84  jnb     short loc_1801D1E8C
0x1801d1e86  mov     rax, [rax+8]
0x1801d1e8a  jmp     short loc_1801D1E7D
0x1801d1e8c  jbe     short loc_1801D1E94
0x1801d1e8e  mov     rax, [rax+10h]
0x1801d1e92  jmp     short loc_1801D1E7D
0x1801d1e94  mov     ecx, [rax+4]
0x1801d1e97  mov     dl, 1
0x1801d1e99  mov     ebx, ecx
0x1801d1e9b  cmp     ecx, [rbp+dwProcessId]
0x1801d1e9e  jz      short loc_1801D1EA4
0x1801d1ea0  test    ecx, ecx
0x1801d1ea2  jnz     short loc_1801D1E77
0x1801d1ea4  test    ebx, ebx
0x1801d1ea6  jz      loc_1801D2006
0x1801d1eac  test    dl, dl
0x1801d1eae  jz      loc_1801D2006
0x1801d1eb4  mov     rdx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1ebb  mov     rcx, [rbp+hObject]
0x1801d1ebf  mov     rdx, [rdx+28h]
0x1801d1ec3  call    ?IsTokenAMemberOfAndHavePrivilegesAsTokenB@@YA?AW4TRI@@PEAX0@Z; IsTokenAMemberOfAndHavePrivilegesAsTokenB(void *,void *)
0x1801d1ec8  cmp     eax, 1
0x1801d1ecb  jnz     loc_1801D2006
0x1801d1ed1  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1ed8  test    esi, esi
0x1801d1eda  jz      short loc_1801D1EE3
0x1801d1edc  or      esi, eax
0x1801d1ede  mov     [rcx+10h], esi
0x1801d1ee1  jmp     short loc_1801D1EF4
0x1801d1ee3  mov     dword ptr [rcx+10h], 0
0x1801d1eea  mov     dword ptr [rcx+0A0h], 0
0x1801d1ef4  bts     dword ptr [rcx+10h], 1Fh
0x1801d1ef9  mov     eax, [rbp+dwProcessId]
0x1801d1efc  mov     [rcx+18h], eax
0x1801d1eff  mov     rcx, [rcx+20h]; hObject
0x1801d1f03  test    rcx, rcx
0x1801d1f06  jz      short loc_1801D1F14
0x1801d1f08  call    cs:__imp_CloseHandle
0x1801d1f0f  nop     dword ptr [rax+rax+00h]
0x1801d1f14  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1801d1f18  xor     edx, edx; bInheritHandle
0x1801d1f1a  mov     ecx, 100000h; dwDesiredAccess
0x1801d1f1f  call    cs:__imp_OpenProcess
0x1801d1f26  nop     dword ptr [rax+rax+00h]
0x1801d1f2b  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1f32  mov     [rbx+20h], rax
0x1801d1f36  test    rax, rax
0x1801d1f39  jnz     short loc_1801D1F50
0x1801d1f3b  call    cs:__imp_GetLastError
0x1801d1f42  nop     dword ptr [rax+rax+00h]
0x1801d1f47  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1f4e  mov     edi, eax
0x1801d1f50  mov     rbx, [rbx+30h]
0x1801d1f54  call    ?ShutdownWaitingThread@CMsiTransaction@@QEAAXXZ; CMsiTransaction::ShutdownWaitingThread(void)
0x1801d1f59  test    rbx, rbx
0x1801d1f5c  jz      loc_1801D200B
0x1801d1f62  xor     r9d, r9d; lpName
0x1801d1f65  mov     [rbp+ThreadId], 0
0x1801d1f6c  xor     r8d, r8d; bInitialState
0x1801d1f6f  xor     edx, edx; bManualReset
0x1801d1f71  xor     ecx, ecx; lpEventAttributes
0x1801d1f73  call    cs:__imp_CreateEventW
0x1801d1f7a  nop     dword ptr [rax+rax+00h]
0x1801d1f7f  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1f86  mov     [rcx+38h], rax
0x1801d1f8a  test    rax, rax
0x1801d1f8d  jz      short loc_1801D1FC5
0x1801d1f8f  lea     rax, [rbp+ThreadId]
0x1801d1f93  xor     r9d, r9d; lpParameter
0x1801d1f96  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x1801d1f9b  lea     r8, ?WaitOnClientProcessThread@@YAKPEAX@Z; lpStartAddress
0x1801d1fa2  xor     edx, edx; dwStackSize
0x1801d1fa4  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x1801d1fac  xor     ecx, ecx; lpThreadAttributes
0x1801d1fae  call    cs:__imp_CreateThread
0x1801d1fb5  nop     dword ptr [rax+rax+00h]
0x1801d1fba  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1fc1  mov     [rcx+30h], rax
0x1801d1fc5  cmp     qword ptr [rcx+30h], 0
0x1801d1fca  jnz     short loc_1801D200B
0x1801d1fcc  mov     eax, [rcx+14h]
0x1801d1fcf  test    eax, eax
0x1801d1fd1  jz      short loc_1801D1FE1
0x1801d1fd3  mov     ecx, eax; hAny
0x1801d1fd5  call    MsiCloseHandle
0x1801d1fda  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; this
0x1801d1fe1  test    rcx, rcx
0x1801d1fe4  jz      short loc_1801D1FEB
0x1801d1fe6  call    ??_GCMsiTransaction@@IEAAPEAXI@Z; CMsiTransaction::`scalar deleting destructor'(uint)
0x1801d1feb  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, 0; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801d1ff6  call    cs:__imp_GetLastError
0x1801d1ffd  nop     dword ptr [rax+rax+00h]
0x1801d2002  mov     edi, eax
0x1801d2004  jmp     short loc_1801D200B
0x1801d2006  mov     edi, 5
0x1801d200b  mov     rcx, [rbp+hObject]; hObject
0x1801d200f  test    rcx, rcx
0x1801d2012  jz      short loc_1801D2020
0x1801d2014  call    cs:__imp_CloseHandle
0x1801d201b  nop     dword ptr [rax+rax+00h]
0x1801d2020  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801d2027  call    cs:__imp_LeaveCriticalSection
0x1801d202e  nop     dword ptr [rax+rax+00h]
0x1801d2033  mov     rdx, [rbp+var_18]; struct Node *
0x1801d2037  lea     rcx, [rbp+var_18]; this
0x1801d203b  call    ?DeleteTree@CBinaryTree@@QEAAXPEAUNode@@@Z; CBinaryTree::DeleteTree(Node *)
0x1801d2040  mov     eax, edi
0x1801d2042  add     rsp, 50h
0x1801d2046  pop     r14
0x1801d2048  pop     rdi
0x1801d2049  pop     rsi
0x1801d204a  pop     rbx
0x1801d204b  pop     rbp
0x1801d204c  retn
```
