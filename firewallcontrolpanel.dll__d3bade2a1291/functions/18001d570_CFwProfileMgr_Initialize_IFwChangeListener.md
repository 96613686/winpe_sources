# CFwProfileMgr::Initialize(IFwChangeListener *)

- ea: `0x18001d570`
- end: `0x18001d70a`
- name: `?Initialize@CFwProfileMgr@@QEAAJPEAUIFwChangeListener@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CFwProfileMgr *__hidden this, struct IFwChangeListener *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000906c`

## callees

- `0x180008b30`
- `0x18000994c`
- `0x180009a80`
- `0x18001c31c`
- `0x18001c594`
- `0x18001d33c`
- `0x18001d570`
- `0x18001d854`
- `0x18001e310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d66d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d6dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d6dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d63d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d63d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFwProfileMgr::Initialize(CFwProfileMgr *this, struct IFwChangeListener *a2)
{
  signed int inited; // ebx
  HANDLE *v5; // rsi
  int v6; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  _BYTE v10[56]; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  ppv = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v10,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 104));
  if ( !a2 )
  {
    inited = -2147024809;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, 2147942487LL);
    v5 = (HANDLE *)((char *)this + 208);
LABEL_21:
    if ( inited >= 0 )
      goto LABEL_24;
    goto LABEL_22;
  }
  *((_QWORD *)this + 10) = a2;
  v6 = CFwProfileMgr::RegisterForChangeNotifications(this);
  if ( v6 < 0
    && WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, (unsigned int)v6);
  }
  if ( CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &ppv) >= 0
    && (int)ATL::CComGITPtr<INetworkListManagerPrivate>::Attach((_DWORD *)this + 22, (__int64)ppv) >= 0 )
  {
    CFwProfileMgr::InitializeNetworkCP(this);
  }
  EventW = CreateEventW(0, 1, 1, 0);
  v5 = (HANDLE *)((char *)this + 208);
  *((_QWORD *)this + 26) = EventW;
  if ( EventW )
    goto LABEL_20;
  LastError = GetLastError();
  inited = LastError;
  if ( LastError > 0 )
    inited = (unsigned __int16)LastError | 0x80070000;
  if ( inited >= 0 )
  {
LABEL_20:
    inited = CFwProfileMgr::InitProfiles(this);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids,
      (unsigned int)inited);
LABEL_22:
  if ( *v5 )
  {
    CloseHandle(*v5);
    *v5 = 0;
  }
LABEL_24:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001d570  push    rbx
0x18001d572  push    rbp
0x18001d573  push    rsi
0x18001d574  push    rdi
0x18001d575  sub     rsp, 48h
0x18001d579  mov     rbx, rdx
0x18001d57c  mov     rdi, rcx
0x18001d57f  mov     [rsp+68h+arg_0], 0
0x18001d588  lea     rdx, [rcx+68h]
0x18001d58c  lea     rcx, [rsp+68h+var_38]
0x18001d591  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001d596  nop
0x18001d597  test    rbx, rbx
0x18001d59a  jnz     short loc_18001D5DE
0x18001d59c  mov     ebx, 80070057h
0x18001d5a1  lea     rbp, WPP_GLOBAL_Control
0x18001d5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5af  cmp     rcx, rbp
0x18001d5b2  jz      short loc_18001D5D2
0x18001d5b4  test    byte ptr [rcx+1Ch], 1
0x18001d5b8  jz      short loc_18001D5D2
0x18001d5ba  mov     edx, 11h
0x18001d5bf  mov     r9d, ebx
0x18001d5c2  lea     r8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001d5c9  mov     rcx, [rcx+10h]
0x18001d5cd  call    WPP_SF_d
0x18001d5d2  lea     rsi, [rdi+0D0h]
0x18001d5d9  jmp     loc_18001D6D1
0x18001d5de  mov     [rdi+50h], rbx
0x18001d5e2  mov     rcx, rdi; this
0x18001d5e5  call    ?RegisterForChangeNotifications@CFwProfileMgr@@AEAAJXZ; CFwProfileMgr::RegisterForChangeNotifications(void)
0x18001d5ea  lea     rbp, WPP_GLOBAL_Control
0x18001d5f1  test    eax, eax
0x18001d5f3  jns     short loc_18001D61F
0x18001d5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5fc  cmp     rcx, rbp
0x18001d5ff  jz      short loc_18001D61F
0x18001d601  test    byte ptr [rcx+1Ch], 1
0x18001d605  jz      short loc_18001D61F
0x18001d607  mov     edx, 27h ; '''
0x18001d60c  mov     r9d, eax
0x18001d60f  lea     r8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001d616  mov     rcx, [rcx+10h]
0x18001d61a  call    WPP_SF_d
0x18001d61f  lea     rax, [rsp+68h+arg_0]
0x18001d624  mov     [rsp+68h+ppv], rax; ppv
0x18001d629  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18001d630  xor     edx, edx; pUnkOuter
0x18001d632  lea     r8d, [rdx+17h]; dwClsContext
0x18001d636  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18001d63d  call    cs:__imp_CoCreateInstance
0x18001d643  test    eax, eax
0x18001d645  js      short loc_18001D661
0x18001d647  lea     rcx, [rdi+58h]
0x18001d64b  mov     rdx, [rsp+68h+arg_0]
0x18001d650  call    ?Attach@?$CComGITPtr@UINetworkListManagerPrivate@@@ATL@@QEAAJPEAUINetworkListManagerPrivate@@@Z; ATL::CComGITPtr<INetworkListManagerPrivate>::Attach(INetworkListManagerPrivate *)
0x18001d655  test    eax, eax
0x18001d657  js      short loc_18001D661
0x18001d659  mov     rcx, rdi; this
0x18001d65c  call    ?InitializeNetworkCP@CFwProfileMgr@@AEAAJXZ; CFwProfileMgr::InitializeNetworkCP(void)
0x18001d661  xor     r9d, r9d; lpName
0x18001d664  lea     edx, [r9+1]; bManualReset
0x18001d668  xor     ecx, ecx; lpEventAttributes
0x18001d66a  mov     r8d, edx; bInitialState
0x18001d66d  call    cs:__imp_CreateEventW
0x18001d673  lea     rsi, [rdi+0D0h]
0x18001d67a  mov     [rsi], rax
0x18001d67d  test    rax, rax
0x18001d680  jnz     short loc_18001D6C7
0x18001d682  call    cs:__imp_GetLastError
0x18001d688  mov     ebx, eax
0x18001d68a  test    eax, eax
0x18001d68c  jle     short loc_18001D697
0x18001d68e  movzx   ebx, ax
0x18001d691  or      ebx, 80070000h
0x18001d697  test    ebx, ebx
0x18001d699  jns     short loc_18001D6C7
0x18001d69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a2  cmp     rcx, rbp
0x18001d6a5  jz      short loc_18001D6D5
0x18001d6a7  test    byte ptr [rcx+1Ch], 1
0x18001d6ab  jz      short loc_18001D6D5
0x18001d6ad  mov     edx, 28h ; '('
0x18001d6b2  mov     r9d, ebx
0x18001d6b5  lea     r8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001d6bc  mov     rcx, [rcx+10h]
0x18001d6c0  call    WPP_SF_d
0x18001d6c5  jmp     short loc_18001D6D5
0x18001d6c7  mov     rcx, rdi; this
0x18001d6ca  call    ?InitProfiles@CFwProfileMgr@@AEAAJXZ; CFwProfileMgr::InitProfiles(void)
0x18001d6cf  mov     ebx, eax
0x18001d6d1  test    ebx, ebx
0x18001d6d3  jns     short loc_18001D6EA
0x18001d6d5  mov     rcx, [rsi]; hObject
0x18001d6d8  test    rcx, rcx
0x18001d6db  jz      short loc_18001D6EA
0x18001d6dd  call    cs:__imp_CloseHandle
0x18001d6e3  mov     qword ptr [rsi], 0
0x18001d6ea  lea     rcx, [rsp+68h+var_38]
0x18001d6ef  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001d6f4  nop
0x18001d6f5  lea     rcx, [rsp+68h+arg_0]
0x18001d6fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d6ff  mov     eax, ebx
0x18001d701  add     rsp, 48h
0x18001d705  pop     rdi
0x18001d706  pop     rsi
0x18001d707  pop     rbp
0x18001d708  pop     rbx
0x18001d709  retn
```
