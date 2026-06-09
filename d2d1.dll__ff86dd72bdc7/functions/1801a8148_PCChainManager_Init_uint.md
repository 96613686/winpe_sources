# PCChainManager::Init(uint)

- ea: `0x1801a8148`
- end: `0x1801a81ff`
- name: `?Init@PCChainManager@@QEAAJI@Z`
- size: `183`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800d0bd8`

## callees

- `0x1800152a0`
- `0x18001fd58`
- `0x1801a8148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a816e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a816e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a81c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a81c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a81b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801a81b4`

## pseudocode

```c
__int64 __fastcall PCChainManager::Init(_DWORD *pv, int a2)
{
  HANDLE EventW; // rax
  HANDLE v4; // rdi
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  HANDLE hObject; // [rsp+30h] [rbp+8h] BYREF

  pv[12] = a2;
  pv[15] = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  hObject = 0;
  v4 = EventW;
  win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
    &hObject,
    pv + 16);
  if ( hObject )
    CloseHandle(hObject);
  *((_QWORD *)pv + 8) = v4;
  if ( v4 )
  {
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)PCChainManager::WorkCallBack, pv, 0);
    *((_QWORD *)pv + 9) = ThreadpoolWork;
    if ( ThreadpoolWork )
      return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2003238887;
  DoStackCapture(v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801a8148  mov     [rsp+arg_8], rbx
0x1801a814d  mov     [rsp+arg_10], rsi
0x1801a8152  push    rdi
0x1801a8153  sub     rsp, 20h
0x1801a8157  mov     [rcx+30h], edx
0x1801a815a  mov     rbx, rcx
0x1801a815d  mov     dword ptr [rcx+3Ch], 0
0x1801a8164  xor     r9d, r9d; lpName
0x1801a8167  xor     ecx, ecx; lpEventAttributes
0x1801a8169  xor     r8d, r8d; bInitialState
0x1801a816c  xor     edx, edx; bManualReset
0x1801a816e  call    cs:__imp_CreateEventW
0x1801a8174  lea     rdx, [rbx+40h]
0x1801a8178  mov     [rsp+28h+hObject], 0
0x1801a8181  lea     rcx, [rsp+28h+hObject]
0x1801a8186  mov     rdi, rax
0x1801a8189  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801a818e  mov     rcx, [rsp+28h+hObject]; hObject
0x1801a8193  test    rcx, rcx
0x1801a8196  jz      short loc_1801A819E
0x1801a8198  call    cs:__imp_CloseHandle
0x1801a819e  mov     [rbx+40h], rdi
0x1801a81a2  test    rdi, rdi
0x1801a81a5  jz      short loc_1801A81C3
0x1801a81a7  xor     r8d, r8d; pcbe
0x1801a81aa  lea     rcx, ?WorkCallBack@PCChainManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801a81b1  mov     rdx, rbx; pv
0x1801a81b4  call    cs:__imp_CreateThreadpoolWork
0x1801a81ba  mov     [rbx+48h], rax
0x1801a81be  test    rax, rax
0x1801a81c1  jnz     short loc_1801A81ED
0x1801a81c3  call    cs:__imp_GetLastError
0x1801a81c9  mov     ebx, eax
0x1801a81cb  test    eax, eax
0x1801a81cd  jle     short loc_1801A81D8
0x1801a81cf  movzx   ebx, ax
0x1801a81d2  or      ebx, 80070000h
0x1801a81d8  test    ebx, ebx
0x1801a81da  mov     eax, 88990019h
0x1801a81df  cmovns  ebx, eax
0x1801a81e2  mov     ecx, ebx; int
0x1801a81e4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a81e9  mov     eax, ebx
0x1801a81eb  jmp     short loc_1801A81EF
0x1801a81ed  xor     eax, eax
0x1801a81ef  mov     rbx, [rsp+28h+arg_8]
0x1801a81f4  mov     rsi, [rsp+28h+arg_10]
0x1801a81f9  add     rsp, 20h
0x1801a81fd  pop     rdi
0x1801a81fe  retn
```
