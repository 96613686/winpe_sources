# CSyncHandler::_SynchronizeWithoutContext(HWND__ *,ushort const * *,ulong,CInvSemaphore &,ISyncMgrSyncCallback *,_FILETIME const &,int)

- ea: `0x18001b324`
- end: `0x18001b5b7`
- name: `?_SynchronizeWithoutContext@CSyncHandler@@AEAAJPEAUHWND__@@PEAPEBGKAEAVCInvSemaphore@@PEAUISyncMgrSyncCallback@@AEBU_FILETIME@@H@Z`
- size: `659`
- prototype: `__int64 __fastcall(CSyncHandler *__hidden this, HWND, const unsigned __int16 **, unsigned int, struct CInvSemaphore *, struct ISyncMgrSyncCallback *, const struct _FILETIME *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019a20`

## callees

- `0x1800041f0`
- `0x180006500`
- `0x18001101c`
- `0x180013dfc`
- `0x1800173cc`
- `0x18001ab24`
- `0x18001b324`
- `0x18003fe40`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b410`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4f4`

## pseudocode

```c
__int64 __fastcall CSyncHandler::_SynchronizeWithoutContext(
        CSyncHandler *this,
        HWND a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        struct CInvSemaphore *a5,
        struct ISyncMgrSyncCallback *a6,
        const struct _FILETIME *a7,
        int a8)
{
  int v10; // eax
  HRESULT v11; // ebx
  __int64 v12; // rsi
  const OLECHAR *v13; // rcx
  int v14; // eax
  UstCommon::CImpersonator *v15; // rcx
  const unsigned __int16 *v17; // [rsp+20h] [rbp-91h]
  LPVOID pv; // [rsp+60h] [rbp-51h] BYREF
  CRefCounted *v19; // [rsp+68h] [rbp-49h] BYREF
  struct IOfflineFilesSyncItem *v20; // [rsp+70h] [rbp-41h] BYREF
  const struct _FILETIME *v21; // [rsp+78h] [rbp-39h]
  struct CInvSemaphore *v22; // [rsp+80h] [rbp-31h]
  HWND v23; // [rsp+88h] [rbp-29h]
  CSyncHandler *v24; // [rsp+90h] [rbp-21h]
  GUID pclsid; // [rsp+98h] [rbp-19h] BYREF

  v22 = a5;
  v24 = this;
  v21 = a7;
  v23 = a2;
  v19 = 0;
  v10 = CSyncItemLog::CreateInstance(&v19);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, a4);
    }
    v12 = 0;
    if ( !a4 )
    {
LABEL_21:
      CRefCounted::ReleaseReference(v19);
      return (unsigned int)v11;
    }
    while ( 1 )
    {
      v13 = a3[v12];
      pclsid = 0;
      v11 = CLSIDFromString(v13, &pclsid);
      if ( v11 < 0 )
        goto LABEL_15;
      pv = 0;
      v20 = 0;
      v14 = CSyncItemLog::QueryEntryByID(v19, &pclsid, (unsigned __int16 **)&pv, &v20, v17);
      v11 = v14;
      if ( v14 < 0 )
        break;
      v11 = CSyncHandler::_SyncPinOrUnpinItem(v24, v23, 0, &pclsid, pv, 0, &pv, 1, a8 != 0 ? 387 : 131, a6, v22, v21);
      CoTaskMemFree(pv);
      pv = 0;
      (*(void (__fastcall **)(struct IOfflineFilesSyncItem *))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v11 < 0 )
        goto LABEL_15;
LABEL_20:
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= a4 )
        goto LABEL_21;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
          (unsigned int)a3[v12],
          v14);
LABEL_15:
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x100000) != 0 )
        WPP_SF_DS(
          *((_QWORD *)v15 + 2),
          43,
          (unsigned int)WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
          v11,
          (__int64)a3[v12]);
    }
    LODWORD(v17) = 100;
    ((void (__fastcall *)(struct ISyncMgrSyncCallback *, const unsigned __int16 *, const WCHAR *, __int64))a6->lpVtbl->ReportProgress)(
      a6,
      a3[v12],
      &lParam,
      4);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b324  push    rbp
0x18001b326  push    rbx
0x18001b327  push    rsi
0x18001b328  push    rdi
0x18001b329  push    r12
0x18001b32b  push    r13
0x18001b32d  push    r14
0x18001b32f  push    r15
0x18001b331  lea     rbp, [rsp-7]
0x18001b336  sub     rsp, 0B8h
0x18001b33d  mov     rax, cs:__security_cookie
0x18001b344  xor     rax, rsp
0x18001b347  mov     [rbp+3Fh+var_48], rax
0x18001b34b  mov     rax, [rbp+3Fh+arg_20]
0x18001b34f  mov     r15d, r9d
0x18001b352  mov     r13, [rbp+3Fh+arg_28]
0x18001b356  mov     r12, r8
0x18001b359  mov     [rbp+3Fh+var_70], rax
0x18001b35d  mov     rax, [rbp+3Fh+arg_30]
0x18001b361  mov     [rbp+3Fh+var_60], rcx
0x18001b365  lea     rcx, [rbp+3Fh+var_88]; struct CSyncItemLog **
0x18001b369  mov     [rbp+3Fh+var_78], rax
0x18001b36d  mov     [rbp+3Fh+var_68], rdx
0x18001b371  mov     [rbp+3Fh+var_88], 0
0x18001b379  call    ?CreateInstance@CSyncItemLog@@SAJPEAPEAV1@@Z; CSyncItemLog::CreateInstance(CSyncItemLog * *)
0x18001b37e  mov     ebx, eax
0x18001b380  test    eax, eax
0x18001b382  jns     short loc_18001B3C2
0x18001b384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b38b  lea     rdi, WPP_GLOBAL_Control
0x18001b392  cmp     rcx, rdi
0x18001b395  jz      loc_18001B595
0x18001b39b  test    byte ptr [rcx+1Ch], 2
0x18001b39f  jz      loc_18001B595
0x18001b3a5  mov     rcx, [rcx+10h]
0x18001b3a9  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001b3b0  mov     edx, 28h ; '('
0x18001b3b5  mov     r9d, eax
0x18001b3b8  call    WPP_SF_d
0x18001b3bd  jmp     loc_18001B595
0x18001b3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3c9  lea     rdi, WPP_GLOBAL_Control
0x18001b3d0  cmp     rcx, rdi
0x18001b3d3  jz      short loc_18001B3F6
0x18001b3d5  test    dword ptr [rcx+1Ch], 100000h
0x18001b3dc  jz      short loc_18001B3F6
0x18001b3de  mov     rcx, [rcx+10h]
0x18001b3e2  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001b3e9  mov     edx, 29h ; ')'
0x18001b3ee  mov     r9d, r15d
0x18001b3f1  call    WPP_SF_d
0x18001b3f6  xor     esi, esi
0x18001b3f8  test    r15d, r15d
0x18001b3fb  jz      loc_18001B58C
0x18001b401  mov     rcx, [r12+rsi*8]; lpsz
0x18001b405  lea     rdx, [rbp+3Fh+pclsid]; pclsid
0x18001b409  xorps   xmm0, xmm0
0x18001b40c  movups  xmmword ptr [rbp+3Fh+pclsid.Data1], xmm0
0x18001b410  call    cs:__imp_CLSIDFromString
0x18001b416  mov     ebx, eax
0x18001b418  test    eax, eax
0x18001b41a  js      loc_18001B516
0x18001b420  mov     rcx, [rbp+3Fh+var_88]; this
0x18001b424  lea     r9, [rbp+3Fh+var_80]; struct IOfflineFilesSyncItem **
0x18001b428  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x18001b42c  mov     [rbp+3Fh+pv], 0
0x18001b434  lea     rdx, [rbp+3Fh+pclsid]; struct _GUID *
0x18001b438  mov     [rbp+3Fh+var_80], 0
0x18001b440  call    ?QueryEntryByID@CSyncItemLog@@QEAAJPEAU_GUID@@PEAPEAGPEAPEAUIOfflineFilesSyncItem@@PEBG@Z; CSyncItemLog::QueryEntryByID(_GUID *,ushort * *,IOfflineFilesSyncItem * *,ushort const *)
0x18001b445  mov     ebx, eax
0x18001b447  test    eax, eax
0x18001b449  jns     short loc_18001B487
0x18001b44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b452  cmp     rcx, rdi
0x18001b455  jz      loc_18001B54C
0x18001b45b  test    byte ptr [rcx+1Ch], 2
0x18001b45f  jz      loc_18001B51D
0x18001b465  mov     r9, [r12+rsi*8]
0x18001b469  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001b470  mov     rcx, [rcx+10h]
0x18001b474  mov     edx, 2Ah ; '*'
0x18001b479  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18001b47d  call    WPP_SF_Sd
0x18001b482  jmp     loc_18001B516
0x18001b487  mov     eax, [rbp+3Fh+arg_38]
0x18001b48d  lea     r9, [rbp+3Fh+pclsid]
0x18001b491  mov     rdx, [rbp+3Fh+var_68]
0x18001b495  neg     eax
0x18001b497  mov     rax, [rbp+3Fh+var_78]
0x18001b49b  mov     [rsp+0F0h+var_98], rax
0x18001b4a0  sbb     ecx, ecx
0x18001b4a2  mov     rax, [rbp+3Fh+var_70]
0x18001b4a6  and     ecx, 100h
0x18001b4ac  mov     [rsp+0F0h+var_A0], rax
0x18001b4b1  add     ecx, 83h
0x18001b4b7  mov     [rsp+0F0h+var_A8], r13
0x18001b4bc  lea     rax, [rbp+3Fh+pv]
0x18001b4c0  mov     [rsp+0F0h+var_B0], ecx
0x18001b4c4  xor     r8d, r8d
0x18001b4c7  mov     rcx, [rbp+3Fh+var_60]
0x18001b4cb  mov     [rsp+0F0h+var_B8], 1
0x18001b4d3  mov     [rsp+0F0h+var_C0], rax
0x18001b4d8  mov     rax, [rbp+3Fh+pv]
0x18001b4dc  mov     [rsp+0F0h+var_C8], 0
0x18001b4e4  mov     [rsp+0F0h+var_D0], rax
0x18001b4e9  call    ?_SyncPinOrUnpinItem@CSyncHandler@@AEAAJPEAUHWND__@@W4SYNC_PURPOSE@1@AEBU_GUID@@PEBGHPEAPEBGKKPEAUISyncMgrSyncCallback@@AEAVCInvSemaphore@@AEBU_FILETIME@@@Z; CSyncHandler::_SyncPinOrUnpinItem(HWND__ *,CSyncHandler::SYNC_PURPOSE,_GUID const &,ushort const *,int,ushort const * *,ulong,ulong,ISyncMgrSyncCallback *,CInvSemaphore &,_FILETIME const &)
0x18001b4ee  mov     rcx, [rbp+3Fh+pv]; pv
0x18001b4f2  mov     ebx, eax
0x18001b4f4  call    cs:__imp_CoTaskMemFree
0x18001b4fa  mov     rcx, [rbp+3Fh+var_80]
0x18001b4fe  mov     [rbp+3Fh+pv], 0
0x18001b506  mov     rax, [rcx]
0x18001b509  mov     rax, [rax+10h]
0x18001b50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b512  test    ebx, ebx
0x18001b514  jns     short loc_18001B581
0x18001b516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b51d  cmp     rcx, rdi
0x18001b520  jz      short loc_18001B54C
0x18001b522  test    dword ptr [rcx+1Ch], 100000h
0x18001b529  jz      short loc_18001B54C
0x18001b52b  mov     rax, [r12+rsi*8]
0x18001b52f  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001b536  mov     rcx, [rcx+10h]
0x18001b53a  mov     edx, 2Bh ; '+'
0x18001b53f  mov     r9d, ebx
0x18001b542  mov     [rsp+0F0h+var_D0], rax
0x18001b547  call    WPP_SF_DS
0x18001b54c  mov     rax, [r13+0]
0x18001b550  lea     r8, lParam
0x18001b557  mov     rdx, [r12+rsi*8]
0x18001b55b  mov     ecx, 64h ; 'd'
0x18001b560  mov     [rsp+0F0h+var_C0], 0
0x18001b569  mov     [rsp+0F0h+var_C8], ecx
0x18001b56d  mov     rax, [rax+18h]
0x18001b571  lea     r9d, [rcx-60h]
0x18001b575  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18001b579  mov     rcx, r13
0x18001b57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b581  inc     esi
0x18001b583  cmp     esi, r15d
0x18001b586  jb      loc_18001B401
0x18001b58c  mov     rcx, [rbp+3Fh+var_88]; this
0x18001b590  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18001b595  mov     eax, ebx
0x18001b597  mov     rcx, [rbp+3Fh+var_48]
0x18001b59b  xor     rcx, rsp; StackCookie
0x18001b59e  call    __security_check_cookie
0x18001b5a3  add     rsp, 0B8h
0x18001b5aa  pop     r15
0x18001b5ac  pop     r14
0x18001b5ae  pop     r13
0x18001b5b0  pop     r12
0x18001b5b2  pop     rdi
0x18001b5b3  pop     rsi
0x18001b5b4  pop     rbx
0x18001b5b5  pop     rbp
0x18001b5b6  retn
```
