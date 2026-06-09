# CMsiTransaction::JoinTransaction(ulong,ulong,ulong *,ushort *)

- ea: `0x1801c94a0`
- end: `0x1801c9795`
- name: `?JoinTransaction@CMsiTransaction@@SAKKKPEAKPEAG@Z`
- size: `757`
- prototype: `static unsigned int(unsigned int, unsigned int, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1801b1520`

## callees

- `0x18001e5d0`
- `0x180025560`
- `0x180134e3c`
- `0x180157528`
- `0x1801bfa98`
- `0x1801c7284`
- `0x1801c8de8`
- `0x1801c94a0`
- `0x1801cbe2c`
- `0x18025048c`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801c9680`
- `KERNEL32!CloseHandle` at `0x1801c9768`
- `KERNEL32!CloseHandle` at `0x1801c9680`
- `KERNEL32!CloseHandle` at `0x1801c9768`
- `KERNEL32!LeaveCriticalSection` at `0x1801c9775`
- `KERNEL32!LeaveCriticalSection` at `0x1801c9775`
- `KERNEL32!GetLastError` at `0x1801c96a7`
- `KERNEL32!GetLastError` at `0x1801c9750`
- `KERNEL32!GetLastError` at `0x1801c96a7`
- `KERNEL32!GetLastError` at `0x1801c9750`
- `KERNEL32!EnterCriticalSection` at `0x1801c94d6`
- `KERNEL32!EnterCriticalSection` at `0x1801c94d6`
- `KERNEL32!GetCurrentProcessId` at `0x1801c957e`
- `KERNEL32!GetCurrentProcessId` at `0x1801c957e`
- `KERNEL32!CreateEventW` at `0x1801c96d9`
- `KERNEL32!CreateEventW` at `0x1801c96d9`
- `KERNEL32!CreateThread` at `0x1801c970e`
- `KERNEL32!CreateThread` at `0x1801c970e`
- `KERNEL32!OpenProcess` at `0x1801c9691`
- `KERNEL32!OpenProcess` at `0x1801c9691`

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
0x1801c94a0  push    rbp
0x1801c94a2  push    rbx
0x1801c94a3  push    rsi
0x1801c94a4  push    rdi
0x1801c94a5  push    r14
0x1801c94a7  mov     rbp, rsp
0x1801c94aa  sub     rsp, 50h
0x1801c94ae  mov     ebx, ecx
0x1801c94b0  mov     [rbp+dwProcessId], 0
0x1801c94b7  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c94be  mov     [rbp+var_18], 0
0x1801c94c6  mov     rdi, r9
0x1801c94c9  mov     [rbp+hObject], 0
0x1801c94d1  mov     r14, r8
0x1801c94d4  mov     esi, edx
0x1801c94d6  call    cs:__imp_EnterCriticalSection
0x1801c94dc  mov     r10, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c94e3  test    r10, r10
0x1801c94e6  jz      loc_1801C975A
0x1801c94ec  cmp     cs:?m_fRollbackDisabled@CMsiTransaction@@0_NA, 0; bool CMsiTransaction::m_fRollbackDisabled
0x1801c94f3  jnz     loc_1801C975A
0x1801c94f9  cmp     ebx, [r10+14h]
0x1801c94fd  jz      short loc_1801C9509
0x1801c94ff  mov     edi, 6
0x1801c9504  jmp     loc_1801C976E
0x1801c9509  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1801c9510  call    ?IsServiceInstalling@MsiUIMessageContext@@QEAA_NXZ; MsiUIMessageContext::IsServiceInstalling(void)
0x1801c9515  cmp     al, 1
0x1801c9517  jnz     short loc_1801C9523
0x1801c9519  mov     edi, 652h
0x1801c951e  jmp     loc_1801C976E
0x1801c9523  mov     rcx, [r10+60h]
0x1801c9527  mov     rax, [rcx]
0x1801c952a  mov     rax, [rax+50h]
0x1801c952e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9533  mov     r8, rax; unsigned __int16 *
0x1801c9536  mov     edx, 104h; unsigned __int64
0x1801c953b  mov     rcx, rdi; unsigned __int16 *
0x1801c953e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c9543  test    eax, eax
0x1801c9545  jns     short loc_1801C9551
0x1801c9547  mov     edi, 57h ; 'W'
0x1801c954c  jmp     loc_1801C976E
0x1801c9551  lea     rdx, [rbp+hObject]; void **
0x1801c9555  lea     rcx, [rbp+dwProcessId]; unsigned int *
0x1801c9559  call    ?GetCallerInfo@CMsiTransaction@@SAKPEAKPEAPEAX@Z; CMsiTransaction::GetCallerInfo(ulong *,void * *)
0x1801c955e  mov     edi, eax
0x1801c9560  test    eax, eax
0x1801c9562  jnz     loc_1801C975F
0x1801c9568  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c956f  cmp     [rax+10h], edi
0x1801c9572  jge     short loc_1801C957E
0x1801c9574  mov     ebx, [rax+18h]
0x1801c9577  cmp     [rbp+dwProcessId], ebx
0x1801c957a  jnz     short loc_1801C9599
0x1801c957c  jmp     short loc_1801C958B
0x1801c957e  call    cs:__imp_GetCurrentProcessId
0x1801c9584  mov     ebx, eax
0x1801c9586  cmp     [rbp+dwProcessId], eax
0x1801c9589  jnz     short loc_1801C9592
0x1801c958b  xor     edi, edi
0x1801c958d  jmp     loc_1801C975F
0x1801c9592  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c9599  mov     eax, [rax+80h]
0x1801c959f  lea     rcx, [rbp+var_18]; this
0x1801c95a3  mov     [r14], eax
0x1801c95a6  call    ?GetActiveProcesses@CMsiTransaction@@SAKAEAVCBinaryTree@@@Z; CMsiTransaction::GetActiveProcesses(CBinaryTree &)
0x1801c95ab  mov     edi, eax
0x1801c95ad  test    eax, eax
0x1801c95af  jnz     loc_1801C975F
0x1801c95b5  mov     ecx, [rbp+dwProcessId]
0x1801c95b8  mov     rax, [rbp+var_18]
0x1801c95bc  xor     r8b, r8b
0x1801c95bf  test    rax, rax
0x1801c95c2  jz      short loc_1801C95E6
0x1801c95c4  cmp     ecx, [rax]
0x1801c95c6  jnb     short loc_1801C95CE
0x1801c95c8  mov     rax, [rax+8]
0x1801c95cc  jmp     short loc_1801C95BF
0x1801c95ce  jbe     short loc_1801C95D6
0x1801c95d0  mov     rax, [rax+10h]
0x1801c95d4  jmp     short loc_1801C95BF
0x1801c95d6  mov     edx, [rax+4]
0x1801c95d9  mov     r8b, 1
0x1801c95dc  mov     ecx, edx
0x1801c95de  cmp     edx, ebx
0x1801c95e0  jz      short loc_1801C95E6
0x1801c95e2  test    edx, edx
0x1801c95e4  jnz     short loc_1801C95B8
0x1801c95e6  test    ecx, ecx
0x1801c95e8  jz      short loc_1801C95EF
0x1801c95ea  test    r8b, r8b
0x1801c95ed  jnz     short loc_1801C962C
0x1801c95ef  mov     rax, [rbp+var_18]
0x1801c95f3  xor     dl, dl
0x1801c95f5  test    rax, rax
0x1801c95f8  jz      short loc_1801C961C
0x1801c95fa  cmp     ebx, [rax]
0x1801c95fc  jnb     short loc_1801C9604
0x1801c95fe  mov     rax, [rax+8]
0x1801c9602  jmp     short loc_1801C95F5
0x1801c9604  jbe     short loc_1801C960C
0x1801c9606  mov     rax, [rax+10h]
0x1801c960a  jmp     short loc_1801C95F5
0x1801c960c  mov     ecx, [rax+4]
0x1801c960f  mov     dl, 1
0x1801c9611  mov     ebx, ecx
0x1801c9613  cmp     ecx, [rbp+dwProcessId]
0x1801c9616  jz      short loc_1801C961C
0x1801c9618  test    ecx, ecx
0x1801c961a  jnz     short loc_1801C95EF
0x1801c961c  test    ebx, ebx
0x1801c961e  jz      loc_1801C975A
0x1801c9624  test    dl, dl
0x1801c9626  jz      loc_1801C975A
0x1801c962c  mov     rdx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c9633  mov     rcx, [rbp+hObject]
0x1801c9637  mov     rdx, [rdx+28h]
0x1801c963b  call    ?IsTokenAMemberOfAndHavePrivilegesAsTokenB@@YA?AW4TRI@@PEAX0@Z; IsTokenAMemberOfAndHavePrivilegesAsTokenB(void *,void *)
0x1801c9640  cmp     eax, 1
0x1801c9643  jnz     loc_1801C975A
0x1801c9649  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c9650  test    esi, esi
0x1801c9652  jz      short loc_1801C965B
0x1801c9654  or      esi, eax
0x1801c9656  mov     [rcx+10h], esi
0x1801c9659  jmp     short loc_1801C966C
0x1801c965b  mov     dword ptr [rcx+10h], 0
0x1801c9662  mov     dword ptr [rcx+0A0h], 0
0x1801c966c  bts     dword ptr [rcx+10h], 1Fh
0x1801c9671  mov     eax, [rbp+dwProcessId]
0x1801c9674  mov     [rcx+18h], eax
0x1801c9677  mov     rcx, [rcx+20h]; hObject
0x1801c967b  test    rcx, rcx
0x1801c967e  jz      short loc_1801C9686
0x1801c9680  call    cs:__imp_CloseHandle
0x1801c9686  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1801c968a  xor     edx, edx; bInheritHandle
0x1801c968c  mov     ecx, 100000h; dwDesiredAccess
0x1801c9691  call    cs:__imp_OpenProcess
0x1801c9697  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c969e  mov     [rbx+20h], rax
0x1801c96a2  test    rax, rax
0x1801c96a5  jnz     short loc_1801C96B6
0x1801c96a7  call    cs:__imp_GetLastError
0x1801c96ad  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c96b4  mov     edi, eax
0x1801c96b6  mov     rbx, [rbx+30h]
0x1801c96ba  call    ?ShutdownWaitingThread@CMsiTransaction@@QEAAXXZ; CMsiTransaction::ShutdownWaitingThread(void)
0x1801c96bf  test    rbx, rbx
0x1801c96c2  jz      loc_1801C975F
0x1801c96c8  xor     r9d, r9d; lpName
0x1801c96cb  mov     [rbp+ThreadId], 0
0x1801c96d2  xor     r8d, r8d; bInitialState
0x1801c96d5  xor     edx, edx; bManualReset
0x1801c96d7  xor     ecx, ecx; lpEventAttributes
0x1801c96d9  call    cs:__imp_CreateEventW
0x1801c96df  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c96e6  mov     [rcx+38h], rax
0x1801c96ea  test    rax, rax
0x1801c96ed  jz      short loc_1801C971F
0x1801c96ef  lea     rax, [rbp+ThreadId]
0x1801c96f3  xor     r9d, r9d; lpParameter
0x1801c96f6  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x1801c96fb  lea     r8, ?WaitOnClientProcessThread@@YAKPEAX@Z; lpStartAddress
0x1801c9702  xor     edx, edx; dwStackSize
0x1801c9704  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x1801c970c  xor     ecx, ecx; lpThreadAttributes
0x1801c970e  call    cs:__imp_CreateThread
0x1801c9714  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c971b  mov     [rcx+30h], rax
0x1801c971f  cmp     qword ptr [rcx+30h], 0
0x1801c9724  jnz     short loc_1801C975F
0x1801c9726  mov     eax, [rcx+14h]
0x1801c9729  test    eax, eax
0x1801c972b  jz      short loc_1801C973B
0x1801c972d  mov     ecx, eax; hAny
0x1801c972f  call    MsiCloseHandle
0x1801c9734  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; this
0x1801c973b  test    rcx, rcx
0x1801c973e  jz      short loc_1801C9745
0x1801c9740  call    ??_GCMsiTransaction@@IEAAPEAXI@Z; CMsiTransaction::`scalar deleting destructor'(uint)
0x1801c9745  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, 0; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801c9750  call    cs:__imp_GetLastError
0x1801c9756  mov     edi, eax
0x1801c9758  jmp     short loc_1801C975F
0x1801c975a  mov     edi, 5
0x1801c975f  mov     rcx, [rbp+hObject]; hObject
0x1801c9763  test    rcx, rcx
0x1801c9766  jz      short loc_1801C976E
0x1801c9768  call    cs:__imp_CloseHandle
0x1801c976e  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c9775  call    cs:__imp_LeaveCriticalSection
0x1801c977b  mov     rdx, [rbp+var_18]; struct Node *
0x1801c977f  lea     rcx, [rbp+var_18]; this
0x1801c9783  call    ?DeleteTree@CBinaryTree@@QEAAXPEAUNode@@@Z; CBinaryTree::DeleteTree(Node *)
0x1801c9788  mov     eax, edi
0x1801c978a  add     rsp, 50h
0x1801c978e  pop     r14
0x1801c9790  pop     rdi
0x1801c9791  pop     rsi
0x1801c9792  pop     rbx
0x1801c9793  pop     rbp
0x1801c9794  retn
```
