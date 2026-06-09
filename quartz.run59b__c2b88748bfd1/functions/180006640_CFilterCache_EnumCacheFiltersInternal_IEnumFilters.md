# CFilterCache::EnumCacheFiltersInternal(IEnumFilters * *)

- ea: `0x180006640`
- end: `0x1800069b3`
- name: `?EnumCacheFiltersInternal@CFilterCache@@AEAAJPEAPEAUIEnumFilters@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(CFilterCache *__hidden this, struct IEnumFilters **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18006d9d0`

## callees

- `0x180005358`
- `0x180006640`
- `0x18000e730`
- `0x18001d3b0`
- `0x180038458`
- `0x18006f20c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800067e6`
- `KERNEL32!GetCurrentThread` at `0x180006809`
- `KERNEL32!GetCurrentThread` at `0x180006865`
- `KERNEL32!GetCurrentThread` at `0x1800067e6`
- `KERNEL32!GetCurrentThread` at `0x180006809`
- `KERNEL32!GetCurrentThread` at `0x180006865`
- `KERNEL32!GetThreadPriority` at `0x1800067f5`
- `KERNEL32!GetThreadPriority` at `0x1800067f5`
- `KERNEL32!GetTickCount` at `0x1800067bd`
- `KERNEL32!GetTickCount` at `0x1800067bd`
- `KERNEL32!SetThreadPriority` at `0x18000681b`
- `KERNEL32!SetThreadPriority` at `0x180006877`
- `KERNEL32!SetThreadPriority` at `0x18000681b`
- `KERNEL32!SetThreadPriority` at `0x180006877`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800066d7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000683d`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800066d7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000683d`
- `KERNEL32!GetCurrentThreadId` at `0x18000666d`
- `KERNEL32!GetCurrentThreadId` at `0x1800068ff`
- `KERNEL32!GetCurrentThreadId` at `0x18000666d`
- `KERNEL32!GetCurrentThreadId` at `0x1800068ff`
- `USER32!GetQueueStatus` at `0x180006888`
- `USER32!GetQueueStatus` at `0x180006888`
- `USER32!DispatchMessageW` at `0x180006767`
- `USER32!DispatchMessageW` at `0x180006767`
- `USER32!PeekMessageW` at `0x180006784`
- `USER32!PeekMessageW` at `0x1800067a8`
- `USER32!PeekMessageW` at `0x1800068e9`
- `USER32!PeekMessageW` at `0x180006784`
- `USER32!PeekMessageW` at `0x1800067a8`
- `USER32!PeekMessageW` at `0x1800068e9`
- `USER32!MsgWaitForMultipleObjects` at `0x180006722`
- `USER32!MsgWaitForMultipleObjects` at `0x180006722`
- `USER32!RegisterWindowMessageW` at `0x1800068b0`
- `USER32!RegisterWindowMessageW` at `0x1800068b0`
- `USER32!PostThreadMessageW` at `0x180006915`
- `USER32!PostThreadMessageW` at `0x180006915`

## pseudocode

```c
__int64 __fastcall CFilterCache::EnumCacheFiltersInternal(CFilterCache *this, struct IEnumFilters **a2)
{
  __int64 v2; // rsi
  struct CMsgMutex **v3; // r12
  DWORD CurrentThreadId; // eax
  int v5; // r8d
  int v6; // edi
  DWORD v7; // r15d
  HWND v8; // rbx
  void *v9; // rax
  unsigned int v10; // r13d
  DWORD v11; // r14d
  int v12; // esi
  DWORD v13; // r15d
  DWORD v14; // eax
  DWORD TickCount; // eax
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // eax
  HANDLE CurrentThread; // rax
  HANDLE v20; // rax
  bool v21; // zf
  HANDLE v22; // rax
  UINT v23; // ebx
  BOOL v24; // eax
  DWORD v25; // eax
  bool v26; // cf
  struct IEnumFilters **v27; // rdi
  CMsgMutex *v28; // rbx
  CEnumCachedFilter *v29; // rax
  CEnumCachedFilter *v30; // rax
  unsigned int nPriority; // [rsp+30h] [rbp-49h]
  UINT wMsgFilterMin; // [rsp+38h] [rbp-41h]
  __int64 v34; // [rsp+40h] [rbp-39h]
  HANDLE Handles[2]; // [rsp+48h] [rbp-31h] BYREF
  MSG Msg; // [rsp+58h] [rbp-21h] BYREF
  CFilterCache *v37; // [rsp+E0h] [rbp+67h] BYREF
  struct IEnumFilters **v38; // [rsp+E8h] [rbp+6Fh]
  DWORD v39; // [rsp+F0h] [rbp+77h]
  DWORD v40; // [rsp+F8h] [rbp+7Fh]

  v38 = a2;
  v37 = this;
  v2 = *((_QWORD *)this + 1);
  v3 = (struct CMsgMutex **)this;
  v34 = v2;
  CurrentThreadId = GetCurrentThreadId();
  v5 = *(_DWORD *)(v2 + 8);
  v6 = 1;
  v39 = CurrentThreadId;
  v7 = CurrentThreadId;
  if ( CurrentThreadId != v5 )
  {
    wMsgFilterMin = *(_DWORD *)(v2 + 24);
    if ( CurrentThreadId == *(_DWORD *)(v2 + 28) )
      v8 = *(HWND *)(v2 + 16);
    else
      v8 = 0;
    v9 = *(void **)v2;
    nPriority = 0;
    Handles[1] = 0;
    v10 = -1;
    v40 = 0;
    Handles[0] = v9;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      do
      {
        v13 = v10;
        if ( v10 > 0xA )
          v13 = 10;
        v14 = MsgWaitForMultipleObjects(1u, Handles, 0, v13, v8 != 0 ? 72 : 64);
        v11 = v14;
        if ( v14 != 1 && (v14 != 258 || v13 == v10) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v8 )
        {
          while ( PeekMessageW(&Msg, v8, wMsgFilterMin, wMsgFilterMin, 1u) )
            DispatchMessageW(&Msg);
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v10 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v16 = TickCount - v40;
          v17 = v10 - (TickCount - v40);
          v40 = TickCount;
          v18 = v10;
          v10 = 0;
          if ( v16 <= v18 )
            v10 = v17;
        }
        if ( !v12 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( nPriority < 2 )
          {
            v20 = GetCurrentThread();
            SetThreadPriority(v20, 2);
          }
          v12 = 1;
        }
        v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      }
      while ( v11 );
      v21 = v12 == 0;
      v2 = v34;
      if ( !v21 )
      {
        v22 = GetCurrentThread();
        SetThreadPriority(v22, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v23 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v23 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v24 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v23, v23, 1u);
              v23 = wMsgFilterMax;
            }
            while ( v24 );
          }
          v25 = GetCurrentThreadId();
          PostThreadMessageW(v25, v23, 0, 0);
        }
      }
      v7 = v39;
      v3 = (struct CMsgMutex **)v37;
    }
    if ( v11 )
    {
      v6 = 0;
      goto LABEL_35;
    }
    *(_DWORD *)(v2 + 8) = v7;
  }
  ++*(_DWORD *)(v2 + 12);
LABEL_35:
  v26 = v6 != 0;
  v27 = v38;
  v28 = (CMsgMutex *)(v2 & -(__int64)v26);
  v37 = v28;
  *v38 = 0;
  v29 = (CEnumCachedFilter *)operator new(0x40u);
  if ( v29 && (v30 = CEnumCachedFilter::CEnumCachedFilter(v29, (struct CFilterCache *)v3, v3[1])) != 0 )
  {
    GetInterface(v30, v27);
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v37);
    return 0;
  }
  else
  {
    if ( v28 )
      CMsgMutex::Unlock(v28);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180006640  mov     [rsp-8+arg_8], rdx
0x180006645  mov     [rsp-8+arg_0], rcx
0x18000664a  push    rbp
0x18000664b  push    rbx
0x18000664c  push    rsi
0x18000664d  push    rdi
0x18000664e  push    r12
0x180006650  push    r13
0x180006652  push    r14
0x180006654  push    r15
0x180006656  lea     rbp, [rsp-1Fh]
0x18000665b  sub     rsp, 98h
0x180006662  mov     rsi, [rcx+8]
0x180006666  mov     r12, rcx
0x180006669  mov     [rbp+57h+var_90], rsi
0x18000666d  call    cs:__imp_GetCurrentThreadId
0x180006674  nop     dword ptr [rax+rax+00h]
0x180006679  mov     r8d, [rsi+8]
0x18000667d  mov     edi, 1
0x180006682  mov     [rbp+57h+arg_10], eax
0x180006685  mov     r15d, eax
0x180006688  cmp     eax, r8d
0x18000668b  jz      loc_180006932
0x180006691  mov     eax, [rsi+18h]
0x180006694  mov     [rbp+57h+wMsgFilterMin], eax
0x180006697  cmp     r15d, [rsi+1Ch]
0x18000669b  jnz     short loc_1800066A3
0x18000669d  mov     rbx, [rsi+10h]
0x1800066a1  jmp     short loc_1800066A5
0x1800066a3  xor     ebx, ebx
0x1800066a5  mov     rax, [rsi]
0x1800066a8  xor     edx, edx
0x1800066aa  mov     [rbp+57h+nPriority], edx
0x1800066ad  xor     r9d, r9d; dwMilliseconds
0x1800066b0  mov     [rbp+57h+var_80], rdx
0x1800066b4  xor     r8d, r8d; bWaitAll
0x1800066b7  mov     [rsp+0D0h+bAlertable], edx; bAlertable
0x1800066bb  mov     ecx, edi; nCount
0x1800066bd  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800066c1  mov     [rbp+57h+var_9C], 0
0x1800066c8  or      r13d, 0FFFFFFFFh
0x1800066cc  mov     [rbp+57h+arg_18], 0
0x1800066d3  mov     [rbp+57h+Handles], rax
0x1800066d7  call    cs:__imp_WaitForMultipleObjectsEx
0x1800066de  nop     dword ptr [rax+rax+00h]
0x1800066e3  mov     r14d, eax
0x1800066e6  cmp     eax, edi
0x1800066e8  jb      loc_180006929
0x1800066ee  mov     esi, [rbp+57h+var_9C]
0x1800066f1  mov     rax, rbx
0x1800066f4  neg     rax
0x1800066f7  mov     eax, 0Ah
0x1800066fc  sbb     r12d, r12d
0x1800066ff  and     r12d, 8
0x180006703  add     r12d, 40h ; '@'
0x180006707  cmp     r13d, eax
0x18000670a  mov     [rsp+0D0h+bAlertable], r12d; dwWakeMask
0x18000670f  mov     r15d, r13d
0x180006712  lea     rdx, [rbp+57h+Handles]; pHandles
0x180006716  cmova   r15d, eax
0x18000671a  mov     ecx, edi; nCount
0x18000671c  mov     r9d, r15d; dwMilliseconds
0x18000671f  xor     r8d, r8d; fWaitAll
0x180006722  call    cs:__imp_MsgWaitForMultipleObjects
0x180006729  nop     dword ptr [rax+rax+00h]
0x18000672e  mov     r14d, eax
0x180006731  cmp     eax, edi
0x180006733  jz      short loc_180006749
0x180006735  cmp     eax, 102h
0x18000673a  jnz     loc_180006859
0x180006740  cmp     r15d, r13d
0x180006743  jz      loc_180006859
0x180006749  xorps   xmm0, xmm0
0x18000674c  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180006750  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180006754  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180006758  test    rbx, rbx
0x18000675b  jz      short loc_180006794
0x18000675d  mov     r14d, [rbp+57h+wMsgFilterMin]
0x180006761  jmp     short loc_180006773
0x180006763  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180006767  call    cs:__imp_DispatchMessageW
0x18000676e  nop     dword ptr [rax+rax+00h]
0x180006773  mov     r9d, r14d; wMsgFilterMax
0x180006776  mov     [rsp+0D0h+bAlertable], edi; wRemoveMsg
0x18000677a  mov     r8d, r14d; wMsgFilterMin
0x18000677d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180006781  mov     rdx, rbx; hWnd
0x180006784  call    cs:__imp_PeekMessageW
0x18000678b  nop     dword ptr [rax+rax+00h]
0x180006790  test    eax, eax
0x180006792  jnz     short loc_180006763
0x180006794  xor     r9d, r9d; wMsgFilterMax
0x180006797  mov     [rsp+0D0h+bAlertable], 0; wRemoveMsg
0x18000679f  xor     r8d, r8d; wMsgFilterMin
0x1800067a2  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800067a6  xor     edx, edx; hWnd
0x1800067a8  call    cs:__imp_PeekMessageW
0x1800067af  nop     dword ptr [rax+rax+00h]
0x1800067b4  lea     eax, [r13-1]
0x1800067b8  cmp     eax, 0FFFFFFFDh
0x1800067bb  ja      short loc_1800067E2
0x1800067bd  call    cs:__imp_GetTickCount
0x1800067c4  nop     dword ptr [rax+rax+00h]
0x1800067c9  mov     ecx, r13d
0x1800067cc  mov     edx, eax
0x1800067ce  sub     edx, [rbp+57h+arg_18]
0x1800067d1  sub     ecx, edx
0x1800067d3  mov     [rbp+57h+arg_18], eax
0x1800067d6  mov     eax, r13d
0x1800067d9  xor     r13d, r13d
0x1800067dc  cmp     edx, eax
0x1800067de  cmovbe  r13d, ecx
0x1800067e2  test    esi, esi
0x1800067e4  jnz     short loc_180006829
0x1800067e6  call    cs:__imp_GetCurrentThread
0x1800067ed  nop     dword ptr [rax+rax+00h]
0x1800067f2  mov     rcx, rax; hThread
0x1800067f5  call    cs:__imp_GetThreadPriority
0x1800067fc  nop     dword ptr [rax+rax+00h]
0x180006801  mov     [rbp+57h+nPriority], eax
0x180006804  cmp     eax, 2
0x180006807  jnb     short loc_180006827
0x180006809  call    cs:__imp_GetCurrentThread
0x180006810  nop     dword ptr [rax+rax+00h]
0x180006815  mov     rcx, rax; hThread
0x180006818  lea     edx, [rsi+2]; nPriority
0x18000681b  call    cs:__imp_SetThreadPriority
0x180006822  nop     dword ptr [rax+rax+00h]
0x180006827  mov     esi, edi
0x180006829  xor     r9d, r9d; dwMilliseconds
0x18000682c  mov     [rsp+0D0h+bAlertable], 0; bAlertable
0x180006834  xor     r8d, r8d; bWaitAll
0x180006837  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000683b  mov     ecx, edi; nCount
0x18000683d  call    cs:__imp_WaitForMultipleObjectsEx
0x180006844  nop     dword ptr [rax+rax+00h]
0x180006849  mov     r14d, eax
0x18000684c  cmp     eax, edi
0x18000684e  mov     eax, 0Ah
0x180006853  jnb     loc_180006707
0x180006859  test    esi, esi
0x18000685b  mov     rsi, [rbp+57h+var_90]
0x18000685f  jz      loc_180006921
0x180006865  call    cs:__imp_GetCurrentThread
0x18000686c  nop     dword ptr [rax+rax+00h]
0x180006871  mov     edx, [rbp+57h+nPriority]; nPriority
0x180006874  mov     rcx, rax; hThread
0x180006877  call    cs:__imp_SetThreadPriority
0x18000687e  nop     dword ptr [rax+rax+00h]
0x180006883  mov     ecx, 8; flags
0x180006888  call    cs:__imp_GetQueueStatus
0x18000688f  nop     dword ptr [rax+rax+00h]
0x180006894  shr     eax, 10h
0x180006897  test    al, 8
0x180006899  jz      loc_180006921
0x18000689f  mov     ebx, cs:wMsgFilterMax
0x1800068a5  test    ebx, ebx
0x1800068a7  jnz     short loc_1800068C8
0x1800068a9  lea     rcx, String; "AMUnblock"
0x1800068b0  call    cs:__imp_RegisterWindowMessageW
0x1800068b7  nop     dword ptr [rax+rax+00h]
0x1800068bc  mov     cs:wMsgFilterMax, eax
0x1800068c2  mov     ebx, eax
0x1800068c4  test    eax, eax
0x1800068c6  jz      short loc_1800068FF
0x1800068c8  xorps   xmm0, xmm0
0x1800068cb  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800068cf  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800068d3  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800068d7  mov     r9d, ebx; wMsgFilterMax
0x1800068da  mov     [rsp+0D0h+bAlertable], edi; wRemoveMsg
0x1800068de  mov     r8d, ebx; wMsgFilterMin
0x1800068e1  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800068e5  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x1800068e9  call    cs:__imp_PeekMessageW
0x1800068f0  nop     dword ptr [rax+rax+00h]
0x1800068f5  mov     ebx, cs:wMsgFilterMax
0x1800068fb  test    eax, eax
0x1800068fd  jnz     short loc_1800068D7
0x1800068ff  call    cs:__imp_GetCurrentThreadId
0x180006906  nop     dword ptr [rax+rax+00h]
0x18000690b  xor     r9d, r9d; lParam
0x18000690e  xor     r8d, r8d; wParam
0x180006911  mov     ecx, eax; idThread
0x180006913  mov     edx, ebx; Msg
0x180006915  call    cs:__imp_PostThreadMessageW
0x18000691c  nop     dword ptr [rax+rax+00h]
0x180006921  mov     r15d, [rbp+57h+arg_10]
0x180006925  mov     r12, [rbp+57h+arg_0]
0x180006929  test    r14d, r14d
0x18000692c  jnz     short loc_180006988
0x18000692e  mov     [rsi+8], r15d
0x180006932  add     [rsi+0Ch], edi
0x180006935  neg     edi
0x180006937  mov     ecx, 40h ; '@'; Size
0x18000693c  mov     rdi, [rbp+57h+arg_8]
0x180006940  sbb     rbx, rbx
0x180006943  and     rbx, rsi
0x180006946  mov     [rbp+57h+arg_0], rbx
0x18000694a  mov     qword ptr [rdi], 0
0x180006951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006956  test    rax, rax
0x180006959  jz      short loc_18000698C
0x18000695b  mov     r8, [r12+8]; struct CMsgMutex *
0x180006960  mov     rdx, r12; struct CFilterCache *
0x180006963  mov     rcx, rax; this
0x180006966  call    ??0CEnumCachedFilter@@QEAA@PEAVCFilterCache@@PEAVCMsgMutex@@@Z; CEnumCachedFilter::CEnumCachedFilter(CFilterCache *,CMsgMutex *)
0x18000696b  test    rax, rax
0x18000696e  jz      short loc_18000698C
0x180006970  mov     rdx, rdi
0x180006973  mov     rcx, rax
0x180006976  call    GetInterface
0x18000697b  lea     rcx, [rbp+57h+arg_0]; this
0x18000697f  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x180006984  xor     eax, eax
0x180006986  jmp     short loc_18000699E
0x180006988  xor     edi, edi
0x18000698a  jmp     short loc_180006935
0x18000698c  test    rbx, rbx
0x18000698f  jz      short loc_180006999
0x180006991  mov     rcx, rbx; this
0x180006994  call    ?Unlock@CMsgMutex@@QEAAXXZ; CMsgMutex::Unlock(void)
0x180006999  mov     eax, 8007000Eh
0x18000699e  add     rsp, 98h
0x1800069a5  pop     r15
0x1800069a7  pop     r14
0x1800069a9  pop     r13
0x1800069ab  pop     r12
0x1800069ad  pop     rdi
0x1800069ae  pop     rsi
0x1800069af  pop     rbx
0x1800069b0  pop     rbp
0x1800069b1  retn
```
