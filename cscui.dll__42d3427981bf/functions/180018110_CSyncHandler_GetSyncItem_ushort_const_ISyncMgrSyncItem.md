# CSyncHandler::GetSyncItem(ushort const *,ISyncMgrSyncItem * *)

- ea: `0x180018110`
- end: `0x180018343`
- name: `?GetSyncItem@CSyncHandler@@UEAAJPEBGPEAPEAUISyncMgrSyncItem@@@Z`
- size: `563`
- prototype: `int(CSyncHandler *__hidden this, const unsigned __int16 *, struct ISyncMgrSyncItem **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077f4`
- `0x180013d9c`
- `0x180013dfc`
- `0x180017b10`
- `0x180018110`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018178`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018270`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018222`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018222`

## pseudocode

```c
__int64 __fastcall CSyncHandler::GetSyncItem(
        CSyncHandler *this,
        const unsigned __int16 *a2,
        struct ISyncMgrSyncItem **a3)
{
  int SyncContext; // ebx
  struct _RTL_CRITICAL_SECTION *v7; // r15
  struct IOfflineFilesSyncContext *v8; // r14
  const struct _GUID *v9; // rdx
  PCNZWCH lpString1; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+38h] [rbp-8h] BYREF
  struct IOfflineFilesSyncContext *v13; // [rsp+78h] [rbp+38h] BYREF
  struct IOfflineFilesSyncContextItem *v14; // [rsp+88h] [rbp+48h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v13 = 0;
  SyncContext = CSyncHandler::_GetSyncContext((CSyncHandler *)((char *)this - 8), &v13);
  if ( SyncContext < 0 )
    goto LABEL_23;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = v13;
  v12 = 0;
  SyncContext = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContext *, __int64 *))(*(_QWORD *)v13 + 64LL))(
                  v13,
                  &v12);
  if ( SyncContext >= 0 )
  {
    LODWORD(v13) = 0;
    v14 = 0;
    while ( !*a3 )
    {
      SyncContext = (*(__int64 (__fastcall **)(__int64, __int64, struct IOfflineFilesSyncContextItem **, struct IOfflineFilesSyncContext **))(*(_QWORD *)v12 + 24LL))(
                      v12,
                      1,
                      &v14,
                      &v13);
      if ( !SyncContext )
      {
        lpString1 = 0;
        SyncContext = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, PCNZWCH *))(*(_QWORD *)v14 + 24LL))(
                        v14,
                        &lpString1);
        if ( SyncContext >= 0 )
        {
          if ( CompareStringW(0x7Fu, 1u, lpString1, -1, a2, -1) == 2 )
          {
            SyncContext = CSyncItem::CreateInstance(v14, v9, (void **)a3);
            if ( SyncContext >= 0
              && WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, a2);
            }
          }
          CoTaskMemFree((LPVOID)lpString1);
        }
        (*(void (__fastcall **)(struct IOfflineFilesSyncContextItem *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( SyncContext >= 0 )
          continue;
      }
      if ( SyncContext >= 0 && !*a3 )
      {
        SyncContext = -2147024809;
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, a2);
        }
      }
      break;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  LeaveCriticalSection(v7);
  (*(void (__fastcall **)(struct IOfflineFilesSyncContext *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( SyncContext < 0 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
        (_DWORD)a2,
        SyncContext);
    }
  }
  return (unsigned int)SyncContext;
}

```

## disassembly

```asm
0x180018110  mov     [rsp-28h+arg_0], rbx
0x180018115  mov     [rsp-28h+arg_10], rsi
0x18001811a  push    rbp
0x18001811b  push    rdi
0x18001811c  push    r13
0x18001811e  push    r14
0x180018120  push    r15
0x180018122  mov     rbp, rsp
0x180018125  sub     rsp, 40h
0x180018129  mov     rdi, r8
0x18001812c  mov     rsi, rdx
0x18001812f  mov     r14, rcx
0x180018132  test    rdx, rdx
0x180018135  jz      loc_180018325
0x18001813b  test    r8, r8
0x18001813e  jz      loc_180018325
0x180018144  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180018148  mov     qword ptr [r8], 0
0x18001814f  lea     rdx, [rbp+arg_8]; struct IOfflineFilesSyncContext **
0x180018153  mov     [rbp+arg_8], 0
0x18001815b  call    ?_GetSyncContext@CSyncHandler@@AEAAJPEAPEAUIOfflineFilesSyncContext@@@Z; CSyncHandler::_GetSyncContext(IOfflineFilesSyncContext * *)
0x180018160  lea     r13, WPP_GLOBAL_Control
0x180018167  mov     ebx, eax
0x180018169  test    eax, eax
0x18001816b  js      loc_1800182F3
0x180018171  lea     r15, [r14+18h]
0x180018175  mov     rcx, r15; lpCriticalSection
0x180018178  call    cs:__imp_EnterCriticalSection
0x18001817e  mov     r14, [rbp+arg_8]
0x180018182  lea     rdx, [rbp+var_8]
0x180018186  mov     [rbp+var_8], 0
0x18001818e  mov     rcx, r14
0x180018191  mov     rax, [r14]
0x180018194  mov     rax, [rax+40h]
0x180018198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001819d  mov     ebx, eax
0x18001819f  test    eax, eax
0x1800181a1  js      loc_1800182D7
0x1800181a7  mov     dword ptr [rbp+arg_8], 0
0x1800181ae  mov     [rbp+arg_18], 0
0x1800181b6  cmp     qword ptr [rdi], 0
0x1800181ba  jnz     loc_1800182C7
0x1800181c0  mov     rcx, [rbp+var_8]
0x1800181c4  lea     r9, [rbp+arg_8]
0x1800181c8  lea     r8, [rbp+arg_18]
0x1800181cc  mov     edx, 1
0x1800181d1  mov     rax, [rcx]
0x1800181d4  mov     rax, [rax+18h]
0x1800181d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181dd  mov     ebx, eax
0x1800181df  test    eax, eax
0x1800181e1  jnz     loc_18001828E
0x1800181e7  mov     rcx, [rbp+arg_18]
0x1800181eb  lea     rdx, [rbp+lpString1]
0x1800181ef  mov     [rbp+lpString1], 0
0x1800181f7  mov     rax, [rcx]
0x1800181fa  mov     rax, [rax+18h]
0x1800181fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018203  mov     ebx, eax
0x180018205  test    eax, eax
0x180018207  js      short loc_180018276
0x180018209  mov     r8, [rbp+lpString1]; lpString1
0x18001820d  or      eax, 0FFFFFFFFh
0x180018210  mov     [rsp+40h+cchCount2], eax; cchCount2
0x180018214  mov     r9d, eax; cchCount1
0x180018217  mov     [rsp+40h+lpString2], rsi; lpString2
0x18001821c  lea     edx, [rax+2]; dwCmpFlags
0x18001821f  lea     ecx, [rdx+7Eh]; Locale
0x180018222  call    cs:__imp_CompareStringW
0x180018228  cmp     eax, 2
0x18001822b  jnz     short loc_18001826C
0x18001822d  mov     rcx, [rbp+arg_18]; struct IOfflineFilesSyncContextItem *
0x180018231  mov     r8, rdi; void **
0x180018234  call    ?CreateInstance@CSyncItem@@SAJPEAUIOfflineFilesSyncContextItem@@AEBU_GUID@@PEAPEAX@Z; CSyncItem::CreateInstance(IOfflineFilesSyncContextItem *,_GUID const &,void * *)
0x180018239  mov     ebx, eax
0x18001823b  test    eax, eax
0x18001823d  js      short loc_18001826C
0x18001823f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018246  cmp     rcx, r13
0x180018249  jz      short loc_18001826C
0x18001824b  test    dword ptr [rcx+1Ch], 100000h
0x180018252  jz      short loc_18001826C
0x180018254  mov     rcx, [rcx+10h]
0x180018258  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001825f  mov     edx, 31h ; '1'
0x180018264  mov     r9, rsi
0x180018267  call    WPP_SF_S
0x18001826c  mov     rcx, [rbp+lpString1]; pv
0x180018270  call    cs:__imp_CoTaskMemFree
0x180018276  mov     rcx, [rbp+arg_18]
0x18001827a  mov     rax, [rcx]
0x18001827d  mov     rax, [rax+10h]
0x180018281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018286  test    ebx, ebx
0x180018288  jns     loc_1800181B6
0x18001828e  test    ebx, ebx
0x180018290  js      short loc_1800182C7
0x180018292  cmp     qword ptr [rdi], 0
0x180018296  jnz     short loc_1800182C7
0x180018298  mov     ebx, 80070057h
0x18001829d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182a4  cmp     rcx, r13
0x1800182a7  jz      short loc_1800182C7
0x1800182a9  test    byte ptr [rcx+1Ch], 2
0x1800182ad  jz      short loc_1800182C7
0x1800182af  mov     rcx, [rcx+10h]
0x1800182b3  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x1800182ba  mov     edx, 32h ; '2'
0x1800182bf  mov     r9, rsi
0x1800182c2  call    WPP_SF_S
0x1800182c7  mov     rcx, [rbp+var_8]
0x1800182cb  mov     rax, [rcx]
0x1800182ce  mov     rax, [rax+10h]
0x1800182d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182d7  mov     rcx, r15; lpCriticalSection
0x1800182da  call    cs:__imp_LeaveCriticalSection
0x1800182e0  mov     rax, [r14]
0x1800182e3  mov     rcx, r14
0x1800182e6  mov     rax, [rax+10h]
0x1800182ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ef  test    ebx, ebx
0x1800182f1  jns     short loc_180018321
0x1800182f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182fa  cmp     rcx, r13
0x1800182fd  jz      short loc_180018321
0x1800182ff  test    byte ptr [rcx+1Ch], 2
0x180018303  jz      short loc_180018321
0x180018305  mov     rcx, [rcx+10h]
0x180018309  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x180018310  mov     edx, 33h ; '3'
0x180018315  mov     dword ptr [rsp+40h+lpString2], ebx
0x180018319  mov     r9, rsi
0x18001831c  call    WPP_SF_Sd
0x180018321  mov     eax, ebx
0x180018323  jmp     short loc_18001832A
0x180018325  mov     eax, 80004003h
0x18001832a  lea     r11, [rsp+40h+var_s0]
0x18001832f  mov     rbx, [r11+30h]
0x180018333  mov     rsi, [r11+40h]
0x180018337  mov     rsp, r11
0x18001833a  pop     r15
0x18001833c  pop     r14
0x18001833e  pop     r13
0x180018340  pop     rdi
0x180018341  pop     rbp
0x180018342  retn
```
