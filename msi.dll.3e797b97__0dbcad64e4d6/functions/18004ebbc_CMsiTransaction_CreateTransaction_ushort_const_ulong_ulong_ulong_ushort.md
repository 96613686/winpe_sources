# CMsiTransaction::CreateTransaction(ushort const *,ulong,ulong,ulong *,ushort *)

- ea: `0x18004ebbc`
- end: `0x18004efd9`
- name: `?CreateTransaction@CMsiTransaction@@SAKPEBGKKPEAKPEAG@Z`
- size: `1053`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x1801b8530`
- `0x1801b9150`

## callees

- `0x18000c4bc`
- `0x18000cb24`
- `0x18000d270`
- `0x180010ac0`
- `0x180018ee0`
- `0x18004dc10`
- `0x18004ebbc`
- `0x180086264`
- `0x18009ecb8`
- `0x18013b0f0`
- `0x180178774`
- `0x180188680`
- `0x1801cc5bc`
- `0x1801cf58c`
- `0x1801cfaa4`
- `0x180259830`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004ee3f`
- `KERNEL32!CloseHandle` at `0x18004ee3f`
- `KERNEL32!LeaveCriticalSection` at `0x18004efa7`
- `KERNEL32!LeaveCriticalSection` at `0x18004efa7`
- `KERNEL32!GetCurrentThreadId` at `0x18004ed3d`
- `KERNEL32!GetCurrentThreadId` at `0x18004ed3d`
- `KERNEL32!GetLastError` at `0x18004ee4b`
- `KERNEL32!GetLastError` at `0x18004ee4b`
- `KERNEL32!EnterCriticalSection` at `0x18004ec03`
- `KERNEL32!EnterCriticalSection` at `0x18004ec03`
- `KERNEL32!CreateEventW` at `0x18004eddf`
- `KERNEL32!CreateEventW` at `0x18004eddf`
- `KERNEL32!CreateThread` at `0x18004ee17`
- `KERNEL32!CreateThread` at `0x18004ee17`

## pseudocode

```c
__int64 __fastcall CMsiTransaction::CreateTransaction(
        const unsigned __int16 *a1,
        int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int16 *a5)
{
  unsigned int v8; // edx
  __int64 v9; // r8
  DWORD LastError; // edi
  __int64 v11; // r8
  bool v12; // al
  CMsiTransaction *v13; // rax
  struct IUnknown *v14; // rax
  unsigned int MsiHandle; // eax
  struct IUnknown *v16; // rcx
  CMsiSystemChange *v17; // rax
  CMsiSystemChange *v18; // rax
  struct IUnknownVtbl *EventW; // rax
  MSIHANDLE lpVtbl_high; // ecx
  unsigned __int16 v21; // dx
  int v22; // r8d
  int dwCreationFlags; // [rsp+20h] [rbp-B8h]
  DWORD ThreadId; // [rsp+64h] [rbp-74h] BYREF
  unsigned int *v26; // [rsp+68h] [rbp-70h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-68h]
  unsigned __int16 v28; // [rsp+78h] [rbp-60h] BYREF
  _BYTE v29[28]; // [rsp+7Ah] [rbp-5Eh] BYREF

  v26 = a4;
  v27 = a1;
  EnterCriticalSection(&g_csTransactionLock);
  if ( g_scServerContext == 2 )
    LastError = CMessageContextState::SetState((CMessageContextState *)&dword_180313690, 1);
  else
    LastError = 0;
  if ( !LastError )
  {
    if ( CMsiTransaction::m_pMsiTransaction )
    {
      LastError = 1618;
    }
    else
    {
      if ( (unsigned int)GetIntegerPolicyValue(8, 0, v9) == 1 || (unsigned int)GetIntegerPolicyValue(8, 1, v11) == 1 )
      {
        if ( a2 < 0 )
        {
          LastError = 1653;
          goto LABEL_35;
        }
        v12 = 1;
      }
      else
      {
        v12 = 0;
      }
      CMsiTransaction::m_fRollbackDisabled = v12;
      v13 = (CMsiTransaction *)operator new(0x350u);
      if ( v13 )
        v14 = (struct IUnknown *)CMsiTransaction::CMsiTransaction(v13, a1, a2, a3, a5);
      else
        v14 = 0;
      CMsiTransaction::m_pMsiTransaction = v14;
      if ( v14 && MsiUIMessageContext::InitializeEnvironmentVariables((MsiUIMessageContext *)&g_MessageContext) )
      {
        if ( LoadCurrentUserKey(0) )
        {
          if ( a2 < 0 )
          {
            MsiHandle = CreateMsiHandle(CMsiTransaction::m_pMsiTransaction, 790535);
            v16 = CMsiTransaction::m_pMsiTransaction;
            HIDWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) = MsiHandle;
            v8 = (unsigned int)v26;
            *v26 = MsiHandle;
            if ( HIDWORD(v16[2].lpVtbl) )
            {
              ((void (__fastcall *)(struct IUnknown *))CMsiTransaction::m_pMsiTransaction->lpVtbl->AddRef)(CMsiTransaction::m_pMsiTransaction);
              LODWORD(CMsiTransaction::m_pMsiTransaction[10].lpVtbl) = GetCurrentThreadId();
              v17 = qword_180313730;
              if ( qword_180313730
                || ((v18 = (CMsiSystemChange *)operator new(0x20u)) == 0
                  ? (v17 = 0)
                  : (v17 = CMsiSystemChange::CMsiSystemChange(v18)),
                    (qword_180313730 = v17) != 0) )
              {
                LOBYTE(dwCreationFlags) = 0;
                CMsiSystemChange::SetSystemChangeInfo(v17, 0, 0, 0, dwCreationFlags, 0, 0, 0, a1, 2, 0);
                CMsiSystemChange::BeginSystemChange(qword_180313730, 0);
                ThreadId = 0;
                EventW = (struct IUnknownVtbl *)CreateEventW(0, 0, 0, 0);
                CMsiTransaction::m_pMsiTransaction[7].lpVtbl = EventW;
                if ( EventW )
                  CMsiTransaction::m_pMsiTransaction[6].lpVtbl = (struct IUnknownVtbl *)CreateThread(
                                                                                          0,
                                                                                          0,
                                                                                          WaitOnClientProcessThread,
                                                                                          0,
                                                                                          0,
                                                                                          &ThreadId);
                if ( !CMsiTransaction::m_pMsiTransaction[6].lpVtbl )
                {
                  CloseHandle(CMsiTransaction::m_pMsiTransaction[7].lpVtbl);
                  LastError = GetLastError();
                }
              }
              else
              {
                LastError = 8;
              }
            }
            else
            {
              LastError = 1603;
            }
          }
        }
        else
        {
          LastError = 1631;
        }
      }
      else
      {
        LastError = 1603;
      }
    }
  }
LABEL_35:
  if ( g_scServerContext == 2 )
    CMessageContextState::SetState((CMessageContextState *)&dword_180313690, 0);
  if ( CMsiTransaction::m_pMsiTransaction )
  {
    if ( !LastError )
      goto LABEL_46;
    if ( LastError != 1618 )
    {
      lpVtbl_high = HIDWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl);
      if ( lpVtbl_high )
        MsiCloseHandle(lpVtbl_high);
      if ( CMsiTransaction::m_pMsiTransaction )
        CMsiTransaction::`scalar deleting destructor'((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction, v8);
      CMsiTransaction::m_pMsiTransaction = 0;
    }
  }
  if ( !LastError )
  {
LABEL_46:
    v28 = 0;
    memset(v29, 0, sizeof(v29));
    if ( (int)StringCchPrintfW(&v28, 0xFu, L"%d", LODWORD(CMsiTransaction::m_pMsiTransaction[3].lpVtbl)) >= 0 )
    {
      v21 = 4;
      v22 = 1040;
LABEL_50:
      DebugString(21, v21, v22, a1, &v28, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  if ( (int)StringCchPrintfW(&v28, 0xFu, L"%d", LastError) >= 0 )
  {
    v21 = 1;
    v22 = 1041;
    goto LABEL_50;
  }
LABEL_51:
  LeaveCriticalSection(&g_csTransactionLock);
  return LastError;
}

```

## disassembly

```asm
0x18004ebbc  push    rbx
0x18004ebbe  push    rsi
0x18004ebbf  push    rdi
0x18004ebc0  push    r12
0x18004ebc2  push    r13
0x18004ebc4  push    r14
0x18004ebc6  push    r15
0x18004ebc8  sub     rsp, 0A0h
0x18004ebcf  mov     rax, cs:__security_cookie
0x18004ebd6  xor     rax, rsp
0x18004ebd9  mov     [rsp+0D8h+var_40], rax
0x18004ebe1  mov     [rsp+0D8h+var_70], r9
0x18004ebe6  mov     r15d, r8d
0x18004ebe9  mov     r14d, edx
0x18004ebec  mov     r13, rcx
0x18004ebef  mov     [rsp+0D8h+var_68], rcx
0x18004ebf4  mov     r12, [rsp+0D8h+arg_20]
0x18004ebfc  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004ec03  call    cs:__imp_EnterCriticalSection
0x18004ec0a  nop     dword ptr [rax+rax+00h]
0x18004ec0f  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004ec16  jnz     short loc_18004EC2C
0x18004ec18  mov     dl, 1; bool
0x18004ec1a  lea     rcx, dword_180313690; this
0x18004ec21  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x18004ec26  mov     edi, eax
0x18004ec28  xor     ebx, ebx
0x18004ec2a  jmp     short loc_18004EC30
0x18004ec2c  xor     ebx, ebx
0x18004ec2e  mov     edi, ebx
0x18004ec30  test    edi, edi
0x18004ec32  jnz     loc_18004EE81
0x18004ec38  cmp     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rbx; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ec3f  jnz     loc_18004EE7C
0x18004ec45  mov     esi, r14d
0x18004ec48  shr     esi, 1Fh
0x18004ec4b  xor     edx, edx
0x18004ec4d  lea     ecx, [rdi+8]
0x18004ec50  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x18004ec55  cmp     eax, 1
0x18004ec58  jz      short loc_18004EC6E
0x18004ec5a  lea     edx, [rdi+1]
0x18004ec5d  lea     ecx, [rdi+8]
0x18004ec60  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x18004ec65  cmp     eax, 1
0x18004ec68  jz      short loc_18004EC6E
0x18004ec6a  mov     al, bl
0x18004ec6c  jmp     short loc_18004EC7F
0x18004ec6e  test    sil, sil
0x18004ec71  jz      short loc_18004EC7D
0x18004ec73  mov     edi, 675h
0x18004ec78  jmp     loc_18004EE81
0x18004ec7d  mov     al, 1
0x18004ec7f  mov     cs:?m_fRollbackDisabled@CMsiTransaction@@0_NA, al; bool CMsiTransaction::m_fRollbackDisabled
0x18004ec85  mov     ecx, 350h; unsigned __int64
0x18004ec8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ec8f  test    rax, rax
0x18004ec92  jz      short loc_18004ECAC
0x18004ec94  mov     qword ptr [rsp+0D8h+dwCreationFlags], r12; unsigned __int16 *
0x18004ec99  mov     r9d, r15d; unsigned int
0x18004ec9c  mov     r8d, r14d; unsigned int
0x18004ec9f  mov     rdx, r13; unsigned __int16 *
0x18004eca2  mov     rcx, rax; this
0x18004eca5  call    ??0CMsiTransaction@@IEAA@PEBGKKPEAG@Z; CMsiTransaction::CMsiTransaction(ushort const *,ulong,ulong,ushort *)
0x18004ecaa  jmp     short loc_18004ECAF
0x18004ecac  mov     rax, rbx
0x18004ecaf  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rax; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ecb6  test    rax, rax
0x18004ecb9  jz      loc_18004EE5F
0x18004ecbf  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x18004ecc6  call    ?InitializeEnvironmentVariables@MsiUIMessageContext@@QEAA_NXZ; MsiUIMessageContext::InitializeEnvironmentVariables(void)
0x18004eccb  test    al, al
0x18004eccd  jz      loc_18004EE5F
0x18004ecd3  xor     ecx, ecx; bool
0x18004ecd5  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x18004ecda  test    al, al
0x18004ecdc  jnz     short loc_18004ECEC
0x18004ecde  mov     edi, 65Fh
0x18004ece3  mov     [rsp+0D8h+var_78], edi
0x18004ece7  jmp     loc_18004EE81
0x18004ecec  test    sil, sil
0x18004ecef  jz      loc_18004EE5D
0x18004ecf5  mov     edx, 0C1007h; int
0x18004ecfa  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; struct IUnknown *
0x18004ed01  call    ?CreateMsiHandle@@YAKPEAUIUnknown@@H@Z; CreateMsiHandle(IUnknown *,int)
0x18004ed06  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ed0d  mov     [rcx+14h], eax
0x18004ed10  mov     rdx, [rsp+0D8h+var_70]
0x18004ed15  mov     [rdx], eax
0x18004ed17  cmp     [rcx+14h], ebx
0x18004ed1a  jnz     short loc_18004ED2A
0x18004ed1c  mov     edi, 643h
0x18004ed21  mov     [rsp+0D8h+var_78], edi
0x18004ed25  jmp     loc_18004EE81
0x18004ed2a  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ed31  mov     rax, [rcx]
0x18004ed34  mov     rax, [rax+8]
0x18004ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed3d  call    cs:__imp_GetCurrentThreadId
0x18004ed44  nop     dword ptr [rax+rax+00h]
0x18004ed49  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ed50  mov     [rcx+50h], eax
0x18004ed53  mov     rax, cs:qword_180313730
0x18004ed5a  test    rax, rax
0x18004ed5d  jnz     short loc_18004ED91
0x18004ed5f  lea     ecx, [rax+20h]; unsigned __int64
0x18004ed62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ed67  test    rax, rax
0x18004ed6a  jz      short loc_18004ED76
0x18004ed6c  mov     rcx, rax; this
0x18004ed6f  call    ??0CMsiSystemChange@@QEAA@XZ; CMsiSystemChange::CMsiSystemChange(void)
0x18004ed74  jmp     short loc_18004ED79
0x18004ed76  mov     rax, rbx
0x18004ed79  mov     cs:qword_180313730, rax
0x18004ed80  test    rax, rax
0x18004ed83  jnz     short loc_18004ED91
0x18004ed85  lea     edi, [rax+8]
0x18004ed88  mov     [rsp+0D8h+var_78], edi
0x18004ed8c  jmp     loc_18004EE81
0x18004ed91  mov     word ptr [rsp+0D8h+var_88], bx
0x18004ed96  mov     dword ptr [rsp+0D8h+var_90], 2
0x18004ed9e  mov     [rsp+0D8h+var_98], r13
0x18004eda3  mov     byte ptr [rsp+0D8h+var_A0], bl
0x18004eda7  mov     byte ptr [rsp+0D8h+var_A8], bl
0x18004edab  mov     byte ptr [rsp+0D8h+lpThreadId], bl
0x18004edaf  mov     byte ptr [rsp+0D8h+dwCreationFlags], bl
0x18004edb3  xor     r9d, r9d
0x18004edb6  xor     r8d, r8d
0x18004edb9  xor     edx, edx
0x18004edbb  mov     rcx, rax
0x18004edbe  call    ?SetSystemChangeInfo@CMsiSystemChange@@QEAAX_N000000PEBGW4iuiEnum@@G@Z; CMsiSystemChange::SetSystemChangeInfo(bool,bool,bool,bool,bool,bool,bool,ushort const *,iuiEnum,ushort)
0x18004edc3  xor     edx, edx; struct IMsiDatabase *
0x18004edc5  mov     rcx, cs:qword_180313730; this
0x18004edcc  call    ?BeginSystemChange@CMsiSystemChange@@QEAAXPEAVIMsiDatabase@@@Z; CMsiSystemChange::BeginSystemChange(IMsiDatabase *)
0x18004edd1  mov     [rsp+0D8h+ThreadId], ebx
0x18004edd5  xor     r9d, r9d; lpName
0x18004edd8  xor     r8d, r8d; bInitialState
0x18004eddb  xor     edx, edx; bManualReset
0x18004eddd  xor     ecx, ecx; lpEventAttributes
0x18004eddf  call    cs:__imp_CreateEventW
0x18004ede6  nop     dword ptr [rax+rax+00h]
0x18004edeb  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004edf2  mov     [rcx+38h], rax
0x18004edf6  test    rax, rax
0x18004edf9  jz      short loc_18004EE2E
0x18004edfb  lea     rax, [rsp+0D8h+ThreadId]
0x18004ee00  mov     [rsp+0D8h+lpThreadId], rax; lpThreadId
0x18004ee05  mov     [rsp+0D8h+dwCreationFlags], ebx; dwCreationFlags
0x18004ee09  xor     r9d, r9d; lpParameter
0x18004ee0c  lea     r8, ?WaitOnClientProcessThread@@YAKPEAX@Z; lpStartAddress
0x18004ee13  xor     edx, edx; dwStackSize
0x18004ee15  xor     ecx, ecx; lpThreadAttributes
0x18004ee17  call    cs:__imp_CreateThread
0x18004ee1e  nop     dword ptr [rax+rax+00h]
0x18004ee23  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ee2a  mov     [rcx+30h], rax
0x18004ee2e  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ee35  cmp     [rcx+30h], rbx
0x18004ee39  jnz     short loc_18004EE5D
0x18004ee3b  mov     rcx, [rcx+38h]; hObject
0x18004ee3f  call    cs:__imp_CloseHandle
0x18004ee46  nop     dword ptr [rax+rax+00h]
0x18004ee4b  call    cs:__imp_GetLastError
0x18004ee52  nop     dword ptr [rax+rax+00h]
0x18004ee57  mov     edi, eax
0x18004ee59  mov     [rsp+0D8h+var_78], eax
0x18004ee5d  jmp     short loc_18004EE81
0x18004ee5f  mov     edi, 643h
0x18004ee64  mov     [rsp+0D8h+var_78], edi
0x18004ee68  jmp     short loc_18004EE81
0x18004ee6a  mov     edi, 643h
0x18004ee6f  mov     [rsp+0D8h+var_78], edi
0x18004ee73  xor     ebx, ebx
0x18004ee75  mov     r13, [rsp+0D8h+var_68]
0x18004ee7a  jmp     short loc_18004EE81
0x18004ee7c  mov     edi, 652h
0x18004ee81  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004ee88  jnz     short loc_18004EE98
0x18004ee8a  xor     edx, edx; bool
0x18004ee8c  lea     rcx, dword_180313690; this
0x18004ee93  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x18004ee98  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004ee9f  test    rcx, rcx
0x18004eea2  jz      short loc_18004EED4
0x18004eea4  test    edi, edi
0x18004eea6  jz      short loc_18004EED8
0x18004eea8  cmp     edi, 652h
0x18004eeae  jz      short loc_18004EED4
0x18004eeb0  mov     ecx, [rcx+14h]; hAny
0x18004eeb3  test    ecx, ecx
0x18004eeb5  jz      short loc_18004EEBC
0x18004eeb7  call    MsiCloseHandle
0x18004eebc  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; this
0x18004eec3  test    rcx, rcx
0x18004eec6  jz      short loc_18004EECD
0x18004eec8  call    ??_GCMsiTransaction@@IEAAPEAXI@Z; CMsiTransaction::`scalar deleting destructor'(uint)
0x18004eecd  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rbx; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004eed4  test    edi, edi
0x18004eed6  jnz     short loc_18004EF23
0x18004eed8  mov     [rsp+0D8h+var_60], bx
0x18004eedd  xorps   xmm0, xmm0
0x18004eee0  movups  xmmword ptr [rsp+0D8h+var_5E], xmm0
0x18004eee5  movups  xmmword ptr [rsp+0D8h+var_5E+0Ch], xmm0
0x18004eeed  mov     r9, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004eef4  mov     r9d, [r9+18h]
0x18004eef8  lea     r8, aD; "%d"
0x18004eeff  mov     edx, 0Fh; unsigned __int64
0x18004ef04  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x18004ef09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ef0e  test    eax, eax
0x18004ef10  js      loc_18004EFA0
0x18004ef16  mov     edx, 4
0x18004ef1b  mov     r8d, 410h
0x18004ef21  jmp     short loc_18004EF60
0x18004ef23  mov     [rsp+0D8h+var_60], bx
0x18004ef28  xorps   xmm0, xmm0
0x18004ef2b  movups  xmmword ptr [rsp+0D8h+var_5E], xmm0
0x18004ef30  movups  xmmword ptr [rsp+0D8h+var_5E+0Ch], xmm0
0x18004ef38  mov     r9d, edi
0x18004ef3b  lea     r8, aD; "%d"
0x18004ef42  mov     edx, 0Fh; unsigned __int64
0x18004ef47  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x18004ef4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ef51  test    eax, eax
0x18004ef53  js      short loc_18004EFA0
0x18004ef55  mov     edx, 1; unsigned __int16
0x18004ef5a  mov     r8d, 411h; int
0x18004ef60  mov     [rsp+0D8h+var_80], rbx; void *
0x18004ef65  mov     [rsp+0D8h+var_88], ebx; unsigned int
0x18004ef69  lea     rax, aNull; "(NULL)"
0x18004ef70  mov     [rsp+0D8h+var_90], rax; unsigned __int16 *
0x18004ef75  mov     [rsp+0D8h+var_98], rax; unsigned __int16 *
0x18004ef7a  mov     [rsp+0D8h+var_A0], rax; unsigned __int16 *
0x18004ef7f  mov     [rsp+0D8h+var_A8], rax; unsigned __int16 *
0x18004ef84  mov     [rsp+0D8h+lpThreadId], rax; unsigned __int16 *
0x18004ef89  lea     rax, [rsp+0D8h+var_60]
0x18004ef8e  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax; unsigned __int16 *
0x18004ef93  mov     r9, r13; unsigned __int16 *
0x18004ef96  mov     ecx, 15h; int
0x18004ef9b  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004efa0  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004efa7  call    cs:__imp_LeaveCriticalSection
0x18004efae  nop     dword ptr [rax+rax+00h]
0x18004efb3  mov     eax, edi
0x18004efb5  mov     rcx, [rsp+0D8h+var_40]
0x18004efbd  xor     rcx, rsp; StackCookie
0x18004efc0  call    __security_check_cookie
0x18004efc5  add     rsp, 0A0h
0x18004efcc  pop     r15
0x18004efce  pop     r14
0x18004efd0  pop     r13
0x18004efd2  pop     r12
0x18004efd4  pop     rdi
0x18004efd5  pop     rsi
0x18004efd6  pop     rbx
0x18004efd7  retn
0x18026536c  push    rbp
0x18026536e  sub     rsp, 60h
0x180265372  mov     rbp, rdx
0x180265375  call    ?InstallEngineExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; InstallEngineExceptionFilter(_EXCEPTION_POINTERS *)
0x18026537a  nop
0x18026537b  add     rsp, 60h
0x18026537f  pop     rbp
0x180265380  retn
```
