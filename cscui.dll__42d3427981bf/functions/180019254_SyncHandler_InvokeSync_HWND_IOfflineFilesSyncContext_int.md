# SyncHandler_InvokeSync(HWND__ *,IOfflineFilesSyncContext *,int)

- ea: `0x180019254`
- end: `0x180019442`
- name: `?SyncHandler_InvokeSync@@YAJPEAUHWND__@@PEAUIOfflineFilesSyncContext@@H@Z`
- size: `494`
- prototype: `__int64 __fastcall(HWND, struct IOfflineFilesSyncContext *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016268`

## callees

- `0x180008b40`
- `0x180010ff4`
- `0x18001101c`
- `0x180018e48`
- `0x1800190e0`
- `0x180019254`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18001935a`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001935a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800192b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800192b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019427`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800193a9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800193a9`

## pseudocode

```c
__int64 __fastcall SyncHandler_InvokeSync(HWND a1, struct IOfflineFilesSyncContext *a2, DWORD a3)
{
  HANDLE EventW; // rax
  unsigned int Error; // eax
  unsigned int v7; // ebx
  int v8; // eax
  UstCommon::CImpersonator *v9; // rcx
  __int64 v10; // rdx
  HANDLE pHandles; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+18h] BYREF
  void *pData; // [rsp+78h] [rbp+20h] BYREF

  dwindex = a3;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  pHandles = EventW;
  if ( EventW )
  {
    pData = 0;
    v8 = SyncHandler_CreateInvokeSyncThreadParamBlock(a1, EventW, a2, (struct tagINVOKE_SYNC_THREAD_PARAMS **)&pData);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
          (unsigned int)v8);
      }
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids);
    }
    if ( SHCreateThread(SyncHandler_InvokeSyncThreadProc, pData, 0x58u, 0) )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids);
      }
      dwindex = 0;
      CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) == 0 )
      {
        goto LABEL_26;
      }
      v10 = 104;
    }
    else
    {
      SyncHandler_DestroyInvokeSyncThreadParamBlock((struct tagINVOKE_SYNC_THREAD_PARAMS *)pData);
      v7 = -2147467259;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_26;
      }
      v10 = 105;
    }
    WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids);
LABEL_26:
    CloseHandle(pHandles);
    return v7;
  }
  Error = ResultFromLastError();
  v7 = Error;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, Error);
  }
  return v7;
}

```

## disassembly

```asm
0x180019254  mov     [rsp+arg_0], rbx
0x180019259  mov     [rsp+arg_8], rbp
0x18001925e  mov     [rsp+dwindex], r8d
0x180019263  push    rsi
0x180019264  push    rdi
0x180019265  push    r14
0x180019267  sub     rsp, 40h
0x18001926b  mov     rbx, rdx
0x18001926e  mov     rdi, rcx
0x180019271  mov     rcx, cs:WPP_GLOBAL_Control
0x180019278  lea     rsi, WPP_GLOBAL_Control
0x18001927f  lea     rbp, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x180019286  mov     r14d, 100000h
0x18001928c  cmp     rcx, rsi
0x18001928f  jz      short loc_1800192A8
0x180019291  test    [rcx+1Ch], r14d
0x180019295  jz      short loc_1800192A8
0x180019297  mov     rcx, [rcx+10h]
0x18001929b  mov     edx, 64h ; 'd'
0x1800192a0  mov     r8, rbp
0x1800192a3  call    WPP_SF_
0x1800192a8  xor     r9d, r9d; lpName
0x1800192ab  xor     r8d, r8d; bInitialState
0x1800192ae  xor     ecx, ecx; lpEventAttributes
0x1800192b0  lea     edx, [r9+1]; bManualReset
0x1800192b4  call    cs:__imp_CreateEventW
0x1800192ba  mov     [rsp+58h+pHandles], rax
0x1800192bf  test    rax, rax
0x1800192c2  jnz     short loc_1800192FE
0x1800192c4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800192c9  mov     ebx, eax
0x1800192cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192d2  cmp     rcx, rsi
0x1800192d5  jz      loc_18001942D
0x1800192db  test    byte ptr [rcx+1Ch], 2
0x1800192df  jz      loc_18001942D
0x1800192e5  mov     rcx, [rcx+10h]
0x1800192e9  mov     edx, 65h ; 'e'
0x1800192ee  mov     r9d, eax
0x1800192f1  mov     r8, rbp
0x1800192f4  call    WPP_SF_d
0x1800192f9  jmp     loc_18001942D
0x1800192fe  lea     r9, [rsp+58h+pData]; struct tagINVOKE_SYNC_THREAD_PARAMS **
0x180019303  mov     [rsp+58h+pData], 0
0x18001930c  mov     r8, rbx; struct IOfflineFilesSyncContext *
0x18001930f  mov     rdx, rax; void *
0x180019312  mov     rcx, rdi; HWND
0x180019315  call    ?SyncHandler_CreateInvokeSyncThreadParamBlock@@YAJPEAUHWND__@@PEAXPEAUIOfflineFilesSyncContext@@PEAPEAUtagINVOKE_SYNC_THREAD_PARAMS@@@Z; SyncHandler_CreateInvokeSyncThreadParamBlock(HWND__ *,void *,IOfflineFilesSyncContext *,tagINVOKE_SYNC_THREAD_PARAMS * *)
0x18001931a  mov     ebx, eax
0x18001931c  test    eax, eax
0x18001931e  js      loc_1800193FC
0x180019324  mov     rcx, cs:WPP_GLOBAL_Control
0x18001932b  cmp     rcx, rsi
0x18001932e  jz      short loc_180019347
0x180019330  test    [rcx+1Ch], r14d
0x180019334  jz      short loc_180019347
0x180019336  mov     rcx, [rcx+10h]
0x18001933a  mov     edx, 66h ; 'f'
0x18001933f  mov     r8, rbp
0x180019342  call    WPP_SF_
0x180019347  mov     rdx, [rsp+58h+pData]; pData
0x18001934c  lea     rcx, ?SyncHandler_InvokeSyncThreadProc@@YAKPEAX@Z; pfnThreadProc
0x180019353  xor     r9d, r9d; pfnCallback
0x180019356  lea     r8d, [r9+58h]; flags
0x18001935a  call    cs:__imp_SHCreateThread
0x180019360  test    eax, eax
0x180019362  jz      short loc_1800193C8
0x180019364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001936b  cmp     rcx, rsi
0x18001936e  jz      short loc_180019387
0x180019370  test    [rcx+1Ch], r14d
0x180019374  jz      short loc_180019387
0x180019376  mov     rcx, [rcx+10h]
0x18001937a  mov     edx, 67h ; 'g'
0x18001937f  mov     r8, rbp
0x180019382  call    WPP_SF_
0x180019387  lea     rax, [rsp+58h+dwindex]
0x18001938c  mov     [rsp+58h+dwindex], 0
0x180019394  lea     r9, [rsp+58h+pHandles]; pHandles
0x180019399  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001939e  mov     r8d, 1; cHandles
0x1800193a4  or      edx, 0FFFFFFFFh; dwTimeout
0x1800193a7  xor     ecx, ecx; dwFlags
0x1800193a9  call    cs:__imp_CoWaitForMultipleHandles
0x1800193af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193b6  cmp     rcx, rsi
0x1800193b9  jz      short loc_180019422
0x1800193bb  test    [rcx+1Ch], r14d
0x1800193bf  jz      short loc_180019422
0x1800193c1  mov     edx, 68h ; 'h'
0x1800193c6  jmp     short loc_1800193EE
0x1800193c8  mov     rcx, [rsp+58h+pData]; lpMem
0x1800193cd  call    ?SyncHandler_DestroyInvokeSyncThreadParamBlock@@YAXPEAUtagINVOKE_SYNC_THREAD_PARAMS@@@Z; SyncHandler_DestroyInvokeSyncThreadParamBlock(tagINVOKE_SYNC_THREAD_PARAMS *)
0x1800193d2  mov     ebx, 80004005h
0x1800193d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193de  cmp     rcx, rsi
0x1800193e1  jz      short loc_180019422
0x1800193e3  test    byte ptr [rcx+1Ch], 2
0x1800193e7  jz      short loc_180019422
0x1800193e9  mov     edx, 69h ; 'i'
0x1800193ee  mov     rcx, [rcx+10h]
0x1800193f2  mov     r8, rbp
0x1800193f5  call    WPP_SF_
0x1800193fa  jmp     short loc_180019422
0x1800193fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019403  cmp     rcx, rsi
0x180019406  jz      short loc_180019422
0x180019408  test    byte ptr [rcx+1Ch], 2
0x18001940c  jz      short loc_180019422
0x18001940e  mov     rcx, [rcx+10h]
0x180019412  mov     edx, 6Ah ; 'j'
0x180019417  mov     r9d, eax
0x18001941a  mov     r8, rbp
0x18001941d  call    WPP_SF_d
0x180019422  mov     rcx, [rsp+58h+pHandles]; hObject
0x180019427  call    cs:__imp_CloseHandle
0x18001942d  mov     rbp, [rsp+58h+arg_8]
0x180019432  mov     eax, ebx
0x180019434  mov     rbx, [rsp+58h+arg_0]
0x180019439  add     rsp, 40h
0x18001943d  pop     r14
0x18001943f  pop     rdi
0x180019440  pop     rsi
0x180019441  retn
```
