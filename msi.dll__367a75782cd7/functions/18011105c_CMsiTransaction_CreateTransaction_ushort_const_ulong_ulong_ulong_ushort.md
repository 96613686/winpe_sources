# CMsiTransaction::CreateTransaction(ushort const *,ulong,ulong,ulong *,ushort *)

- ea: `0x18011105c`
- end: `0x18011144e`
- name: `?CreateTransaction@CMsiTransaction@@SAKPEBGKKPEAKPEAG@Z`
- size: `1010`
- prototype: `__int64 __fastcall(const unsigned __int16 *, signed int, unsigned int, unsigned int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x1801b08b0`
- `0x1801b1460`

## callees

- `0x18001dee8`
- `0x18001e5d0`
- `0x180022120`
- `0x180025a18`
- `0x180061334`
- `0x180081a5c`
- `0x18008f3e8`
- `0x18011105c`
- `0x180112320`
- `0x180135d88`
- `0x180172494`
- `0x180182040`
- `0x1801c3f68`
- `0x1801c6dac`
- `0x1801c7284`
- `0x18024f4dc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801112c7`
- `KERNEL32!CloseHandle` at `0x1801112c7`
- `KERNEL32!LeaveCriticalSection` at `0x180111423`
- `KERNEL32!LeaveCriticalSection` at `0x180111423`
- `KERNEL32!GetCurrentThreadId` at `0x1801111d7`
- `KERNEL32!GetCurrentThreadId` at `0x1801111d7`
- `KERNEL32!GetLastError` at `0x1801112cd`
- `KERNEL32!GetLastError` at `0x1801112cd`
- `KERNEL32!EnterCriticalSection` at `0x1801110a3`
- `KERNEL32!EnterCriticalSection` at `0x1801110a3`
- `KERNEL32!CreateEventW` at `0x180111273`
- `KERNEL32!CreateEventW` at `0x180111273`
- `KERNEL32!CreateThread` at `0x1801112a5`
- `KERNEL32!CreateThread` at `0x1801112a5`

## pseudocode

```c
__int64 __fastcall CMsiTransaction::CreateTransaction(
        const unsigned __int16 *a1,
        signed int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int16 *a5)
{
  unsigned int v8; // edx
  DWORD LastError; // edi
  bool v10; // al
  CMsiTransaction *v11; // rax
  struct IUnknown *v12; // rax
  unsigned int MsiHandle; // eax
  struct IUnknown *v14; // rcx
  CMsiSystemChange *v15; // rax
  CMsiSystemChange *v16; // rax
  struct IUnknownVtbl *EventW; // rax
  MSIHANDLE lpVtbl_high; // ecx
  unsigned __int16 v19; // dx
  int v20; // r8d
  int dwCreationFlags; // [rsp+20h] [rbp-B8h]
  DWORD ThreadId; // [rsp+64h] [rbp-74h] BYREF
  unsigned int *v24; // [rsp+68h] [rbp-70h]
  const unsigned __int16 *v25; // [rsp+70h] [rbp-68h]
  unsigned __int16 v26; // [rsp+78h] [rbp-60h] BYREF
  _BYTE v27[28]; // [rsp+7Ah] [rbp-5Eh] BYREF

  v24 = a4;
  v25 = a1;
  EnterCriticalSection(&g_csTransactionLock);
  if ( g_scServerContext == 2 )
    LastError = CMessageContextState::SetState((CMessageContextState *)&dword_1803096E0, 1);
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
      if ( (unsigned int)GetIntegerPolicyValue(8) == 1 || (unsigned int)GetIntegerPolicyValue(8) == 1 )
      {
        if ( a2 < 0 )
        {
          LastError = 1653;
          goto LABEL_35;
        }
        v10 = 1;
      }
      else
      {
        v10 = 0;
      }
      CMsiTransaction::m_fRollbackDisabled = v10;
      v11 = (CMsiTransaction *)operator new(0x350u);
      if ( v11 )
        v12 = (struct IUnknown *)CMsiTransaction::CMsiTransaction(v11, a1, a2, a3, a5);
      else
        v12 = 0;
      CMsiTransaction::m_pMsiTransaction = v12;
      if ( v12 && MsiUIMessageContext::InitializeEnvironmentVariables((MsiUIMessageContext *)&g_MessageContext) )
      {
        if ( LoadCurrentUserKey(0) )
        {
          if ( a2 < 0 )
          {
            MsiHandle = CreateMsiHandle(CMsiTransaction::m_pMsiTransaction, 790535);
            v14 = CMsiTransaction::m_pMsiTransaction;
            HIDWORD(CMsiTransaction::m_pMsiTransaction[2].lpVtbl) = MsiHandle;
            v8 = (unsigned int)v24;
            *v24 = MsiHandle;
            if ( HIDWORD(v14[2].lpVtbl) )
            {
              ((void (__fastcall *)(struct IUnknown *))CMsiTransaction::m_pMsiTransaction->lpVtbl->AddRef)(CMsiTransaction::m_pMsiTransaction);
              LODWORD(CMsiTransaction::m_pMsiTransaction[10].lpVtbl) = GetCurrentThreadId();
              v15 = qword_180309780;
              if ( qword_180309780
                || ((v16 = (CMsiSystemChange *)operator new(0x20u)) == 0
                  ? (v15 = 0)
                  : (v15 = CMsiSystemChange::CMsiSystemChange(v16)),
                    (qword_180309780 = v15) != 0) )
              {
                LOBYTE(dwCreationFlags) = 0;
                CMsiSystemChange::SetSystemChangeInfo(v15, 0, 0, 0, dwCreationFlags, 0, 0, 0, a1, 2, 0);
                CMsiSystemChange::BeginSystemChange(qword_180309780, 0);
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
    CMessageContextState::SetState((CMessageContextState *)&dword_1803096E0, 0);
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
    v26 = 0;
    memset(v27, 0, sizeof(v27));
    if ( (int)StringCchPrintfW(&v26, 0xFu, L"%d", LODWORD(CMsiTransaction::m_pMsiTransaction[3].lpVtbl)) >= 0 )
    {
      v19 = 4;
      v20 = 1040;
LABEL_50:
      DebugString(21, v19, v20, a1, &v26, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  v26 = 0;
  memset(v27, 0, sizeof(v27));
  if ( (int)StringCchPrintfW(&v26, 0xFu, L"%d", LastError) >= 0 )
  {
    v19 = 1;
    v20 = 1041;
    goto LABEL_50;
  }
LABEL_51:
  LeaveCriticalSection(&g_csTransactionLock);
  return LastError;
}

```

## disassembly

```asm
0x18011105c  push    rbx
0x18011105e  push    rsi
0x18011105f  push    rdi
0x180111060  push    r12
0x180111062  push    r13
0x180111064  push    r14
0x180111066  push    r15
0x180111068  sub     rsp, 0A0h
0x18011106f  mov     rax, cs:__security_cookie
0x180111076  xor     rax, rsp
0x180111079  mov     [rsp+0D8h+var_40], rax
0x180111081  mov     [rsp+0D8h+var_70], r9
0x180111086  mov     r15d, r8d
0x180111089  mov     r14d, edx
0x18011108c  mov     r13, rcx
0x18011108f  mov     [rsp+0D8h+var_68], rcx
0x180111094  mov     r12, [rsp+0D8h+arg_20]
0x18011109c  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801110a3  call    cs:__imp_EnterCriticalSection
0x1801110a9  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801110b0  jnz     short loc_1801110C6
0x1801110b2  mov     dl, 1; bool
0x1801110b4  lea     rcx, dword_1803096E0; this
0x1801110bb  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x1801110c0  mov     edi, eax
0x1801110c2  xor     ebx, ebx
0x1801110c4  jmp     short loc_1801110CA
0x1801110c6  xor     ebx, ebx
0x1801110c8  mov     edi, ebx
0x1801110ca  test    edi, edi
0x1801110cc  jnz     loc_1801112FD
0x1801110d2  cmp     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rbx; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801110d9  jnz     loc_1801112F8
0x1801110df  mov     esi, r14d
0x1801110e2  shr     esi, 1Fh
0x1801110e5  xor     edx, edx
0x1801110e7  lea     ecx, [rdi+8]
0x1801110ea  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x1801110ef  cmp     eax, 1
0x1801110f2  jz      short loc_180111108
0x1801110f4  lea     edx, [rdi+1]
0x1801110f7  lea     ecx, [rdi+8]
0x1801110fa  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x1801110ff  cmp     eax, 1
0x180111102  jz      short loc_180111108
0x180111104  mov     al, bl
0x180111106  jmp     short loc_180111119
0x180111108  test    sil, sil
0x18011110b  jz      short loc_180111117
0x18011110d  mov     edi, 675h
0x180111112  jmp     loc_1801112FD
0x180111117  mov     al, 1
0x180111119  mov     cs:?m_fRollbackDisabled@CMsiTransaction@@0_NA, al; bool CMsiTransaction::m_fRollbackDisabled
0x18011111f  mov     ecx, 350h; unsigned __int64
0x180111124  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180111129  test    rax, rax
0x18011112c  jz      short loc_180111146
0x18011112e  mov     qword ptr [rsp+0D8h+dwCreationFlags], r12; unsigned __int16 *
0x180111133  mov     r9d, r15d; unsigned int
0x180111136  mov     r8d, r14d; unsigned int
0x180111139  mov     rdx, r13; unsigned __int16 *
0x18011113c  mov     rcx, rax; this
0x18011113f  call    ??0CMsiTransaction@@IEAA@PEBGKKPEAG@Z; CMsiTransaction::CMsiTransaction(ushort const *,ulong,ulong,ushort *)
0x180111144  jmp     short loc_180111149
0x180111146  mov     rax, rbx
0x180111149  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rax; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180111150  test    rax, rax
0x180111153  jz      loc_1801112DB
0x180111159  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x180111160  call    ?InitializeEnvironmentVariables@MsiUIMessageContext@@QEAA_NXZ; MsiUIMessageContext::InitializeEnvironmentVariables(void)
0x180111165  test    al, al
0x180111167  jz      loc_1801112DB
0x18011116d  xor     ecx, ecx; bool
0x18011116f  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x180111174  test    al, al
0x180111176  jnz     short loc_180111186
0x180111178  mov     edi, 65Fh
0x18011117d  mov     [rsp+0D8h+var_78], edi
0x180111181  jmp     loc_1801112FD
0x180111186  test    sil, sil
0x180111189  jz      loc_1801112D9
0x18011118f  mov     edx, 0C1007h; int
0x180111194  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; struct IUnknown *
0x18011119b  call    ?CreateMsiHandle@@YAKPEAUIUnknown@@H@Z; CreateMsiHandle(IUnknown *,int)
0x1801111a0  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801111a7  mov     [rcx+14h], eax
0x1801111aa  mov     rdx, [rsp+0D8h+var_70]
0x1801111af  mov     [rdx], eax
0x1801111b1  cmp     [rcx+14h], ebx
0x1801111b4  jnz     short loc_1801111C4
0x1801111b6  mov     edi, 643h
0x1801111bb  mov     [rsp+0D8h+var_78], edi
0x1801111bf  jmp     loc_1801112FD
0x1801111c4  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801111cb  mov     rax, [rcx]
0x1801111ce  mov     rax, [rax+8]
0x1801111d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801111d7  call    cs:__imp_GetCurrentThreadId
0x1801111dd  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801111e4  mov     [rcx+50h], eax
0x1801111e7  mov     rax, cs:qword_180309780
0x1801111ee  test    rax, rax
0x1801111f1  jnz     short loc_180111225
0x1801111f3  lea     ecx, [rax+20h]; unsigned __int64
0x1801111f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801111fb  test    rax, rax
0x1801111fe  jz      short loc_18011120A
0x180111200  mov     rcx, rax; this
0x180111203  call    ??0CMsiSystemChange@@QEAA@XZ; CMsiSystemChange::CMsiSystemChange(void)
0x180111208  jmp     short loc_18011120D
0x18011120a  mov     rax, rbx
0x18011120d  mov     cs:qword_180309780, rax
0x180111214  test    rax, rax
0x180111217  jnz     short loc_180111225
0x180111219  lea     edi, [rax+8]
0x18011121c  mov     [rsp+0D8h+var_78], edi
0x180111220  jmp     loc_1801112FD
0x180111225  mov     word ptr [rsp+0D8h+var_88], bx
0x18011122a  mov     dword ptr [rsp+0D8h+var_90], 2
0x180111232  mov     [rsp+0D8h+var_98], r13
0x180111237  mov     byte ptr [rsp+0D8h+var_A0], bl
0x18011123b  mov     byte ptr [rsp+0D8h+var_A8], bl
0x18011123f  mov     byte ptr [rsp+0D8h+lpThreadId], bl
0x180111243  mov     byte ptr [rsp+0D8h+dwCreationFlags], bl
0x180111247  xor     r9d, r9d
0x18011124a  xor     r8d, r8d
0x18011124d  xor     edx, edx
0x18011124f  mov     rcx, rax
0x180111252  call    ?SetSystemChangeInfo@CMsiSystemChange@@QEAAX_N000000PEBGW4iuiEnum@@G@Z; CMsiSystemChange::SetSystemChangeInfo(bool,bool,bool,bool,bool,bool,bool,ushort const *,iuiEnum,ushort)
0x180111257  xor     edx, edx; struct IMsiDatabase *
0x180111259  mov     rcx, cs:qword_180309780; this
0x180111260  call    ?BeginSystemChange@CMsiSystemChange@@QEAAXPEAVIMsiDatabase@@@Z; CMsiSystemChange::BeginSystemChange(IMsiDatabase *)
0x180111265  mov     [rsp+0D8h+ThreadId], ebx
0x180111269  xor     r9d, r9d; lpName
0x18011126c  xor     r8d, r8d; bInitialState
0x18011126f  xor     edx, edx; bManualReset
0x180111271  xor     ecx, ecx; lpEventAttributes
0x180111273  call    cs:__imp_CreateEventW
0x180111279  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180111280  mov     [rcx+38h], rax
0x180111284  test    rax, rax
0x180111287  jz      short loc_1801112B6
0x180111289  lea     rax, [rsp+0D8h+ThreadId]
0x18011128e  mov     [rsp+0D8h+lpThreadId], rax; lpThreadId
0x180111293  mov     [rsp+0D8h+dwCreationFlags], ebx; dwCreationFlags
0x180111297  xor     r9d, r9d; lpParameter
0x18011129a  lea     r8, ?WaitOnClientProcessThread@@YAKPEAX@Z; lpStartAddress
0x1801112a1  xor     edx, edx; dwStackSize
0x1801112a3  xor     ecx, ecx; lpThreadAttributes
0x1801112a5  call    cs:__imp_CreateThread
0x1801112ab  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801112b2  mov     [rcx+30h], rax
0x1801112b6  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1801112bd  cmp     [rcx+30h], rbx
0x1801112c1  jnz     short loc_1801112D9
0x1801112c3  mov     rcx, [rcx+38h]; hObject
0x1801112c7  call    cs:__imp_CloseHandle
0x1801112cd  call    cs:__imp_GetLastError
0x1801112d3  mov     edi, eax
0x1801112d5  mov     [rsp+0D8h+var_78], eax
0x1801112d9  jmp     short loc_1801112FD
0x1801112db  mov     edi, 643h
0x1801112e0  mov     [rsp+0D8h+var_78], edi
0x1801112e4  jmp     short loc_1801112FD
0x1801112e6  mov     edi, 643h
0x1801112eb  mov     [rsp+0D8h+var_78], edi
0x1801112ef  xor     ebx, ebx
0x1801112f1  mov     r13, [rsp+0D8h+var_68]
0x1801112f6  jmp     short loc_1801112FD
0x1801112f8  mov     edi, 652h
0x1801112fd  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180111304  jnz     short loc_180111314
0x180111306  xor     edx, edx; bool
0x180111308  lea     rcx, dword_1803096E0; this
0x18011130f  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x180111314  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18011131b  test    rcx, rcx
0x18011131e  jz      short loc_180111350
0x180111320  test    edi, edi
0x180111322  jz      short loc_180111354
0x180111324  cmp     edi, 652h
0x18011132a  jz      short loc_180111350
0x18011132c  mov     ecx, [rcx+14h]; hAny
0x18011132f  test    ecx, ecx
0x180111331  jz      short loc_180111338
0x180111333  call    MsiCloseHandle
0x180111338  mov     rcx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; this
0x18011133f  test    rcx, rcx
0x180111342  jz      short loc_180111349
0x180111344  call    ??_GCMsiTransaction@@IEAAPEAXI@Z; CMsiTransaction::`scalar deleting destructor'(uint)
0x180111349  mov     cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA, rbx; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180111350  test    edi, edi
0x180111352  jnz     short loc_18011139F
0x180111354  mov     [rsp+0D8h+var_60], bx
0x180111359  xorps   xmm0, xmm0
0x18011135c  movups  xmmword ptr [rsp+0D8h+var_5E], xmm0
0x180111361  movups  xmmword ptr [rsp+0D8h+var_5E+0Ch], xmm0
0x180111369  mov     r9, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180111370  mov     r9d, [r9+18h]
0x180111374  lea     r8, aD; "%d"
0x18011137b  mov     edx, 0Fh; unsigned __int64
0x180111380  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x180111385  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011138a  test    eax, eax
0x18011138c  js      loc_18011141C
0x180111392  mov     edx, 4
0x180111397  mov     r8d, 410h
0x18011139d  jmp     short loc_1801113DC
0x18011139f  mov     [rsp+0D8h+var_60], bx
0x1801113a4  xorps   xmm0, xmm0
0x1801113a7  movups  xmmword ptr [rsp+0D8h+var_5E], xmm0
0x1801113ac  movups  xmmword ptr [rsp+0D8h+var_5E+0Ch], xmm0
0x1801113b4  mov     r9d, edi
0x1801113b7  lea     r8, aD; "%d"
0x1801113be  mov     edx, 0Fh; unsigned __int64
0x1801113c3  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x1801113c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801113cd  test    eax, eax
0x1801113cf  js      short loc_18011141C
0x1801113d1  mov     edx, 1; unsigned __int16
0x1801113d6  mov     r8d, 411h; int
0x1801113dc  mov     [rsp+0D8h+var_80], rbx; void *
0x1801113e1  mov     [rsp+0D8h+var_88], ebx; unsigned int
0x1801113e5  lea     rax, aNull; "(NULL)"
0x1801113ec  mov     [rsp+0D8h+var_90], rax; unsigned __int16 *
0x1801113f1  mov     [rsp+0D8h+var_98], rax; unsigned __int16 *
0x1801113f6  mov     [rsp+0D8h+var_A0], rax; unsigned __int16 *
0x1801113fb  mov     [rsp+0D8h+var_A8], rax; unsigned __int16 *
0x180111400  mov     [rsp+0D8h+lpThreadId], rax; unsigned __int16 *
0x180111405  lea     rax, [rsp+0D8h+var_60]
0x18011140a  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax; unsigned __int16 *
0x18011140f  mov     r9, r13; unsigned __int16 *
0x180111412  mov     ecx, 15h; int
0x180111417  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18011141c  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180111423  call    cs:__imp_LeaveCriticalSection
0x180111429  mov     eax, edi
0x18011142b  mov     rcx, [rsp+0D8h+var_40]
0x180111433  xor     rcx, rsp; StackCookie
0x180111436  call    __security_check_cookie
0x18011143b  add     rsp, 0A0h
0x180111442  pop     r15
0x180111444  pop     r14
0x180111446  pop     r13
0x180111448  pop     r12
0x18011144a  pop     rdi
0x18011144b  pop     rsi
0x18011144c  pop     rbx
0x18011144d  retn
0x18025ad8d  push    rbp
0x18025ad8f  sub     rsp, 60h
0x18025ad93  mov     rbp, rdx
0x18025ad96  call    ?InstallEngineExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; InstallEngineExceptionFilter(_EXCEPTION_POINTERS *)
0x18025ad9b  nop
0x18025ad9c  add     rsp, 60h
0x18025ada0  pop     rbp
0x18025ada1  retn
```
