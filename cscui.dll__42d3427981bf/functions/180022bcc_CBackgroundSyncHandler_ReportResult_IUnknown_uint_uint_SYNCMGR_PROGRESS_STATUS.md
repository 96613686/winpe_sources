# CBackgroundSyncHandler::ReportResult(IUnknown *,uint,uint,SYNCMGR_PROGRESS_STATUS)

- ea: `0x180022bcc`
- end: `0x180022de2`
- name: `?ReportResult@CBackgroundSyncHandler@@QEAAJPEAUIUnknown@@IIW4SYNCMGR_PROGRESS_STATUS@@@Z`
- size: `534`
- prototype: `__int64 __usercall@<rax>(CBackgroundSyncHandler *__hidden this@<rcx>, struct IUnknown *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, enum SYNCMGR_PROGRESS_STATUS)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022df0`
- `0x180022e70`

## callees

- `0x180010ff4`
- `0x180013d9c`
- `0x180022bcc`
- `0x180023270`
- `0x1800244ac`
- `0x1800245e4`
- `0x180024930`
- `0x18003fe40`
- `0x18003ff70`
- `0x18004c0fc`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x180022c74`
- `SHELL32!__imp_GUIDFromStringW` at `0x180022c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022cbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022cbc`

## pseudocode

```c
__int64 __fastcall CBackgroundSyncHandler::ReportResult(
        CSyncItemLog **this,
        struct IUnknown *a2,
        unsigned int a3,
        __int64 a4,
        enum SYNCMGR_PROGRESS_STATUS a5)
{
  int updated; // r14d
  unsigned int v9; // ecx
  __int64 v10; // r13
  CSyncItemLog *v11; // rcx
  const unsigned __int16 *v12; // r8
  CSyncItemLog *v13; // rcx
  struct IOfflineFilesSyncItem *v14; // r15
  unsigned __int16 *v15; // rsi
  int v16; // eax
  const unsigned __int16 *v18; // [rsp+20h] [rbp-40h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v21; // [rsp+40h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids);
  }
  updated = 0;
  CBackgroundSyncHandler::_WaitOnMutex((CBackgroundSyncHandler *)this, (int *)a2);
  if ( !*((_DWORD *)this + 31) )
    goto LABEL_24;
  v9 = 0;
  while ( *((struct IUnknown **)this[16] + v9) != a2 )
  {
    if ( ++v9 >= *((_DWORD *)this + 31) )
      goto LABEL_24;
  }
  v10 = v9;
  v11 = this[14];
  v21 = 0;
  if ( (unsigned int)GUIDFromStringW(*((_QWORD *)v11 + v10), &v21) )
  {
    v13 = this[11];
    pv = 0;
    SystemTimeAsFileTime = 0;
    updated = CSyncItemLog::QueryEntryByID(
                v13,
                &v21,
                (unsigned __int16 **)&pv,
                (struct IOfflineFilesSyncItem **)&SystemTimeAsFileTime,
                v18);
    if ( updated >= 0 )
    {
      v14 = (struct IOfflineFilesSyncItem *)SystemTimeAsFileTime;
      if ( a5 == SYNCMGR_PS_SUCCEEDED )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        (*(void (__fastcall **)(struct IOfflineFilesSyncItem *, struct _FILETIME *))(*(_QWORD *)v14 + 56LL))(
          v14,
          &SystemTimeAsFileTime);
        v15 = (unsigned __int16 *)pv;
        updated = CSyncItemLog::UpdateEntry(this[11], (const unsigned __int16 *)pv, v14);
      }
      else
      {
        v15 = (unsigned __int16 *)pv;
        if ( !*((_BYTE *)this + 104) && a3 )
        {
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids, pv);
          }
          CscEvt_BGSyncFailedOnScopeWithErrorCount(v15, a3);
        }
        ++*((_DWORD *)this + 35);
      }
      CoTaskMemFree(v15);
      (*(void (__fastcall **)(struct IOfflineFilesSyncItem *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  *((_QWORD *)this[16] + v10) = 0;
  v16 = ++*((_DWORD *)this + 34);
  if ( v16 != *((_DWORD *)this + 31) )
  {
    CWinTaskHandler::UpdateStatus((CWinTaskHandler *)this, (unsigned int)(100 * v16) / *((_DWORD *)this + 31), v12);
LABEL_24:
    CBackgroundSyncHandler::_ReleaseMutex((CBackgroundSyncHandler *)this);
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
    return (unsigned int)updated;
  }
  CBackgroundSyncHandler::_ReleaseMutex((CBackgroundSyncHandler *)this);
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
  CBackgroundSyncHandler::_OnComplete((CBackgroundSyncHandler *)this);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180022bcc  mov     [rsp-38h+arg_18], rbx
0x180022bd1  push    rbp
0x180022bd2  push    rsi
0x180022bd3  push    rdi
0x180022bd4  push    r12
0x180022bd6  push    r13
0x180022bd8  push    r14
0x180022bda  push    r15
0x180022bdc  mov     rbp, rsp
0x180022bdf  sub     rsp, 60h
0x180022be3  mov     rax, cs:__security_cookie
0x180022bea  xor     rax, rsp
0x180022bed  mov     [rbp+var_10], rax
0x180022bf1  mov     r12d, r8d
0x180022bf4  mov     rdi, rdx
0x180022bf7  mov     rbx, rcx
0x180022bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c01  lea     rax, WPP_GLOBAL_Control
0x180022c08  cmp     rcx, rax
0x180022c0b  jz      short loc_180022C2B
0x180022c0d  test    dword ptr [rcx+1Ch], 100000h
0x180022c14  jz      short loc_180022C2B
0x180022c16  mov     rcx, [rcx+10h]
0x180022c1a  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180022c21  mov     edx, 20h ; ' '
0x180022c26  call    WPP_SF_
0x180022c2b  xor     esi, esi
0x180022c2d  mov     rcx, rbx; this
0x180022c30  mov     r14d, esi
0x180022c33  call    ?_WaitOnMutex@CBackgroundSyncHandler@@AEAAJPEAH@Z; CBackgroundSyncHandler::_WaitOnMutex(int *)
0x180022c38  cmp     [rbx+7Ch], esi
0x180022c3b  jbe     loc_180022DA4
0x180022c41  mov     rdx, [rbx+80h]
0x180022c48  mov     ecx, esi
0x180022c4a  mov     eax, ecx
0x180022c4c  cmp     [rdx+rax*8], rdi
0x180022c50  jz      short loc_180022C5E
0x180022c52  inc     ecx
0x180022c54  cmp     ecx, [rbx+7Ch]
0x180022c57  jb      short loc_180022C4A
0x180022c59  jmp     loc_180022DA4
0x180022c5e  mov     r13d, ecx
0x180022c61  lea     rdx, [rbp+var_20]
0x180022c65  mov     rcx, [rbx+70h]
0x180022c69  xorps   xmm0, xmm0
0x180022c6c  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180022c70  mov     rcx, [rcx+r13*8]
0x180022c74  call    cs:__imp_GUIDFromStringW
0x180022c7a  test    eax, eax
0x180022c7c  jz      loc_180022D58
0x180022c82  mov     rcx, [rbx+58h]; this
0x180022c86  lea     r9, [rbp+SystemTimeAsFileTime]; struct IOfflineFilesSyncItem **
0x180022c8a  lea     r8, [rbp+pv]; unsigned __int16 **
0x180022c8e  mov     [rbp+pv], rsi
0x180022c92  lea     rdx, [rbp+var_20]; struct _GUID *
0x180022c96  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180022c9a  call    ?QueryEntryByID@CSyncItemLog@@QEAAJPEAU_GUID@@PEAPEAGPEAPEAUIOfflineFilesSyncItem@@PEBG@Z; CSyncItemLog::QueryEntryByID(_GUID *,ushort * *,IOfflineFilesSyncItem * *,ushort const *)
0x180022c9f  mov     r14d, eax
0x180022ca2  test    eax, eax
0x180022ca4  js      loc_180022D58
0x180022caa  cmp     [rbp+arg_20], 3
0x180022cae  mov     r15, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180022cb2  jnz     short loc_180022CED
0x180022cb4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022cb8  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180022cbc  call    cs:__imp_GetSystemTimeAsFileTime
0x180022cc2  mov     rax, [r15]
0x180022cc5  lea     rdx, [rbp+SystemTimeAsFileTime]
0x180022cc9  mov     rcx, r15
0x180022ccc  mov     rax, [rax+38h]
0x180022cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cd5  mov     rsi, [rbp+pv]
0x180022cd9  mov     r8, r15; struct IOfflineFilesSyncItem *
0x180022cdc  mov     rcx, [rbx+58h]; this
0x180022ce0  mov     rdx, rsi; unsigned __int16 *
0x180022ce3  call    ?UpdateEntry@CSyncItemLog@@QEAAJPEBGPEAUIOfflineFilesSyncItem@@@Z; CSyncItemLog::UpdateEntry(ushort const *,IOfflineFilesSyncItem *)
0x180022ce8  mov     r14d, eax
0x180022ceb  jmp     short loc_180022D3E
0x180022ced  cmp     byte ptr [rbx+68h], 0
0x180022cf1  mov     rsi, [rbp+pv]
0x180022cf5  jnz     short loc_180022D38
0x180022cf7  test    r12d, r12d
0x180022cfa  jz      short loc_180022D38
0x180022cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d03  lea     rax, WPP_GLOBAL_Control
0x180022d0a  cmp     rcx, rax
0x180022d0d  jz      short loc_180022D2D
0x180022d0f  test    byte ptr [rcx+1Ch], 2
0x180022d13  jz      short loc_180022D2D
0x180022d15  mov     rcx, [rcx+10h]
0x180022d19  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180022d20  mov     edx, 21h ; '!'
0x180022d25  mov     r9, rsi
0x180022d28  call    WPP_SF_S
0x180022d2d  mov     edx, r12d; unsigned int
0x180022d30  mov     rcx, rsi; unsigned __int16 *
0x180022d33  call    ?CscEvt_BGSyncFailedOnScopeWithErrorCount@@YAKPEBGI@Z; CscEvt_BGSyncFailedOnScopeWithErrorCount(ushort const *,uint)
0x180022d38  inc     dword ptr [rbx+8Ch]
0x180022d3e  mov     rcx, rsi; pv
0x180022d41  call    cs:__imp_CoTaskMemFree
0x180022d47  mov     rax, [r15]
0x180022d4a  mov     rcx, r15
0x180022d4d  mov     rax, [rax+10h]
0x180022d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d56  xor     esi, esi
0x180022d58  mov     rax, [rbx+80h]
0x180022d5f  mov     rcx, rbx; this
0x180022d62  mov     [rax+r13*8], rsi
0x180022d66  inc     dword ptr [rbx+88h]
0x180022d6c  mov     eax, [rbx+88h]
0x180022d72  cmp     eax, [rbx+7Ch]
0x180022d75  jnz     short loc_180022D95
0x180022d77  call    ?_ReleaseMutex@CBackgroundSyncHandler@@AEAAXXZ; CBackgroundSyncHandler::_ReleaseMutex(void)
0x180022d7c  mov     rax, [rdi]
0x180022d7f  mov     rcx, rdi
0x180022d82  mov     rax, [rax+10h]
0x180022d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d8b  mov     rcx, rbx; this
0x180022d8e  call    ?_OnComplete@CBackgroundSyncHandler@@AEAAXXZ; CBackgroundSyncHandler::_OnComplete(void)
0x180022d93  jmp     short loc_180022DBB
0x180022d95  xor     edx, edx
0x180022d97  imul    eax, 64h ; 'd'
0x180022d9a  div     dword ptr [rbx+7Ch]
0x180022d9d  mov     edx, eax; __int16
0x180022d9f  call    ?UpdateStatus@CWinTaskHandler@@IEAAJFPEBG@Z; CWinTaskHandler::UpdateStatus(short,ushort const *)
0x180022da4  mov     rcx, rbx; this
0x180022da7  call    ?_ReleaseMutex@CBackgroundSyncHandler@@AEAAXXZ; CBackgroundSyncHandler::_ReleaseMutex(void)
0x180022dac  mov     rax, [rdi]
0x180022daf  mov     rcx, rdi
0x180022db2  mov     rax, [rax+10h]
0x180022db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dbb  mov     eax, r14d
0x180022dbe  mov     rcx, [rbp+var_10]
0x180022dc2  xor     rcx, rsp; StackCookie
0x180022dc5  call    __security_check_cookie
0x180022dca  mov     rbx, [rsp+60h+arg_18]
0x180022dd2  add     rsp, 60h
0x180022dd6  pop     r15
0x180022dd8  pop     r14
0x180022dda  pop     r13
0x180022ddc  pop     r12
0x180022dde  pop     rdi
0x180022ddf  pop     rsi
0x180022de0  pop     rbp
0x180022de1  retn
```
