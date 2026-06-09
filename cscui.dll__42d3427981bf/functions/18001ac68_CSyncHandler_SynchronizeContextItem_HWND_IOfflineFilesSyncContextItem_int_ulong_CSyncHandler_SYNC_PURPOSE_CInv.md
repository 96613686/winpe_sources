# CSyncHandler::_SynchronizeContextItem(HWND__ *,IOfflineFilesSyncContextItem *,int,ulong,CSyncHandler::SYNC_PURPOSE,CInvSemaphore &,ISyncMgrSyncCallback *,_FILETIME const &)

- ea: `0x18001ac68`
- end: `0x18001ae61`
- name: `?_SynchronizeContextItem@CSyncHandler@@AEAAJPEAUHWND__@@PEAUIOfflineFilesSyncContextItem@@HKW4SYNC_PURPOSE@1@AEAVCInvSemaphore@@PEAUISyncMgrSyncCallback@@AEBU_FILETIME@@@Z`
- size: `505`
- prototype: `int __high(HWND, struct IOfflineFilesSyncContextItem *, int, unsigned int, enum CSyncHandler::SYNC_PURPOSE, struct CInvSemaphore *, struct ISyncMgrSyncCallback *, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ae68`

## callees

- `0x18001101c`
- `0x18001ab24`
- `0x18001ac68`
- `0x18003d9a4`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ada3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ada3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae32`

## pseudocode

```c
__int64 __fastcall CSyncHandler::_SynchronizeContextItem(
        __int64 a1,
        __int64 a2,
        struct IOfflineFilesSyncContextItem *a3,
        int a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v12; // rax
  HRESULT v14; // ebx
  __int64 v15; // rax
  int v16; // eax
  LPVOID *v17; // rsi
  unsigned int v18; // r14d
  __int64 i; // rdi
  unsigned int v21; // [rsp+60h] [rbp-49h] BYREF
  LPCOLESTR lpsz; // [rsp+68h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-39h] BYREF
  __int64 v24; // [rsp+78h] [rbp-31h]
  __int64 v25; // [rsp+80h] [rbp-29h]
  __int64 v26; // [rsp+88h] [rbp-21h]
  GUID pclsid; // [rsp+90h] [rbp-19h] BYREF

  v25 = a7;
  v26 = a8;
  v24 = a9;
  v12 = *(_QWORD *)a3;
  pv = 0;
  v14 = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, LPVOID *))(v12 + 32))(a3, &pv);
  if ( v14 >= 0 )
  {
    *(_QWORD *)&pclsid.Data1 = 0;
    v21 = 0;
    v14 = SyncContext_CreateSyncItemPathArray(a3, (unsigned __int16 ***)&pclsid, &v21);
    if ( v14 >= 0 )
    {
      v15 = *(_QWORD *)a3;
      lpsz = 0;
      v16 = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, LPCOLESTR *))(v15 + 24))(a3, &lpsz);
      v17 = *(LPVOID **)&pclsid.Data1;
      v14 = v16;
      v18 = v21;
      if ( v16 >= 0 )
      {
        pclsid = 0;
        v14 = CLSIDFromString(lpsz, &pclsid);
        if ( v14 >= 0 )
          v14 = CSyncHandler::_SyncPinOrUnpinItem(a1, a2, a6, &pclsid, pv, a4, v17, v18, a5, v26, v25, v24);
        CoTaskMemFree((LPVOID)lpsz);
      }
      if ( v17 )
      {
        for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
          CoTaskMemFree(v17[i]);
        CoTaskMemFree(v17);
      }
    }
    else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
        (unsigned int)v14);
    }
    CoTaskMemFree(pv);
  }
  else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001ac68  mov     [rsp-8+arg_18], rbx
0x18001ac6d  push    rbp
0x18001ac6e  push    rsi
0x18001ac6f  push    rdi
0x18001ac70  push    r12
0x18001ac72  push    r13
0x18001ac74  push    r14
0x18001ac76  push    r15
0x18001ac78  lea     rbp, [rsp-7]
0x18001ac7d  sub     rsp, 0B0h
0x18001ac84  mov     rax, cs:__security_cookie
0x18001ac8b  xor     rax, rsp
0x18001ac8e  mov     [rbp+37h+var_40], rax
0x18001ac92  mov     rax, [rbp+37h+arg_30]
0x18001ac96  mov     r13, rdx
0x18001ac99  mov     [rbp+37h+var_60], rax
0x18001ac9d  lea     rdx, [rbp+37h+pv]
0x18001aca1  mov     rax, [rbp+37h+arg_38]
0x18001aca5  mov     r12, rcx
0x18001aca8  mov     [rbp+37h+var_58], rax
0x18001acac  xor     esi, esi
0x18001acae  mov     rax, [rbp+37h+arg_40]
0x18001acb5  mov     rcx, r8
0x18001acb8  mov     [rbp+37h+var_68], rax
0x18001acbc  mov     r15d, r9d
0x18001acbf  mov     rax, [r8]
0x18001acc2  mov     rdi, r8
0x18001acc5  mov     [rbp+37h+pv], rsi
0x18001acc9  mov     rax, [rax+20h]
0x18001accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acd2  mov     ebx, eax
0x18001acd4  test    eax, eax
0x18001acd6  jns     short loc_18001AD14
0x18001acd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acdf  lea     rax, WPP_GLOBAL_Control
0x18001ace6  cmp     rcx, rax
0x18001ace9  jz      loc_18001AE38
0x18001acef  test    byte ptr [rcx+1Ch], 2
0x18001acf3  jz      loc_18001AE38
0x18001acf9  mov     rcx, [rcx+10h]
0x18001acfd  lea     edx, [rsi+26h]
0x18001ad00  mov     r9d, ebx
0x18001ad03  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001ad0a  call    WPP_SF_d
0x18001ad0f  jmp     loc_18001AE38
0x18001ad14  lea     r8, [rbp+37h+var_80]; unsigned int *
0x18001ad18  mov     qword ptr [rbp+37h+pclsid.Data1], rsi
0x18001ad1c  lea     rdx, [rbp+37h+pclsid]; unsigned __int16 ***
0x18001ad20  mov     [rbp+37h+var_80], esi
0x18001ad23  mov     rcx, rdi; struct IOfflineFilesSyncContextItem *
0x18001ad26  call    ?SyncContext_CreateSyncItemPathArray@@YAJPEAUIOfflineFilesSyncContextItem@@PEAPEAPEAGPEAK@Z; SyncContext_CreateSyncItemPathArray(IOfflineFilesSyncContextItem *,ushort * * *,ulong *)
0x18001ad2b  mov     ebx, eax
0x18001ad2d  test    eax, eax
0x18001ad2f  jns     short loc_18001AD6F
0x18001ad31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad38  lea     rax, WPP_GLOBAL_Control
0x18001ad3f  cmp     rcx, rax
0x18001ad42  jz      loc_18001AE2E
0x18001ad48  test    byte ptr [rcx+1Ch], 2
0x18001ad4c  jz      loc_18001AE2E
0x18001ad52  mov     rcx, [rcx+10h]
0x18001ad56  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001ad5d  mov     edx, 27h ; '''
0x18001ad62  mov     r9d, ebx
0x18001ad65  call    WPP_SF_d
0x18001ad6a  jmp     loc_18001AE2E
0x18001ad6f  mov     rax, [rdi]
0x18001ad72  lea     rdx, [rbp+37h+lpsz]
0x18001ad76  mov     rcx, rdi
0x18001ad79  mov     [rbp+37h+lpsz], rsi
0x18001ad7d  mov     rax, [rax+18h]
0x18001ad81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad86  mov     rsi, qword ptr [rbp+37h+pclsid.Data1]
0x18001ad8a  mov     ebx, eax
0x18001ad8c  mov     r14d, [rbp+37h+var_80]
0x18001ad90  test    eax, eax
0x18001ad92  js      short loc_18001AE08
0x18001ad94  mov     rcx, [rbp+37h+lpsz]; lpsz
0x18001ad98  lea     rdx, [rbp+37h+pclsid]; pclsid
0x18001ad9c  xorps   xmm0, xmm0
0x18001ad9f  movups  xmmword ptr [rbp+37h+pclsid.Data1], xmm0
0x18001ada3  call    cs:__imp_CLSIDFromString
0x18001ada9  mov     ebx, eax
0x18001adab  test    eax, eax
0x18001adad  js      short loc_18001ADFE
0x18001adaf  mov     rax, [rbp+37h+var_68]
0x18001adb3  lea     r9, [rbp+37h+pclsid]
0x18001adb7  mov     r8d, [rbp+37h+arg_28]
0x18001adbb  mov     rdx, r13
0x18001adbe  mov     [rsp+0E0h+var_88], rax
0x18001adc3  mov     rcx, r12
0x18001adc6  mov     rax, [rbp+37h+var_60]
0x18001adca  mov     [rsp+0E0h+var_90], rax
0x18001adcf  mov     rax, [rbp+37h+var_58]
0x18001add3  mov     [rsp+0E0h+var_98], rax
0x18001add8  mov     eax, [rbp+37h+arg_20]
0x18001addb  mov     [rsp+0E0h+var_A0], eax
0x18001addf  mov     rax, [rbp+37h+pv]
0x18001ade3  mov     [rsp+0E0h+var_A8], r14d
0x18001ade8  mov     [rsp+0E0h+var_B0], rsi
0x18001aded  mov     [rsp+0E0h+var_B8], r15d
0x18001adf2  mov     [rsp+0E0h+var_C0], rax
0x18001adf7  call    ?_SyncPinOrUnpinItem@CSyncHandler@@AEAAJPEAUHWND__@@W4SYNC_PURPOSE@1@AEBU_GUID@@PEBGHPEAPEBGKKPEAUISyncMgrSyncCallback@@AEAVCInvSemaphore@@AEBU_FILETIME@@@Z; CSyncHandler::_SyncPinOrUnpinItem(HWND__ *,CSyncHandler::SYNC_PURPOSE,_GUID const &,ushort const *,int,ushort const * *,ulong,ulong,ISyncMgrSyncCallback *,CInvSemaphore &,_FILETIME const &)
0x18001adfc  mov     ebx, eax
0x18001adfe  mov     rcx, [rbp+37h+lpsz]; pv
0x18001ae02  call    cs:__imp_CoTaskMemFree
0x18001ae08  test    rsi, rsi
0x18001ae0b  jz      short loc_18001AE2E
0x18001ae0d  xor     edi, edi
0x18001ae0f  test    r14d, r14d
0x18001ae12  jz      short loc_18001AE25
0x18001ae14  mov     rcx, [rsi+rdi*8]; pv
0x18001ae18  call    cs:__imp_CoTaskMemFree
0x18001ae1e  inc     edi
0x18001ae20  cmp     edi, r14d
0x18001ae23  jb      short loc_18001AE14
0x18001ae25  mov     rcx, rsi; pv
0x18001ae28  call    cs:__imp_CoTaskMemFree
0x18001ae2e  mov     rcx, [rbp+37h+pv]; pv
0x18001ae32  call    cs:__imp_CoTaskMemFree
0x18001ae38  mov     eax, ebx
0x18001ae3a  mov     rcx, [rbp+37h+var_40]
0x18001ae3e  xor     rcx, rsp; StackCookie
0x18001ae41  call    __security_check_cookie
0x18001ae46  mov     rbx, [rsp+0E0h+arg_18]
0x18001ae4e  add     rsp, 0B0h
0x18001ae55  pop     r15
0x18001ae57  pop     r14
0x18001ae59  pop     r13
0x18001ae5b  pop     r12
0x18001ae5d  pop     rdi
0x18001ae5e  pop     rsi
0x18001ae5f  pop     rbp
0x18001ae60  retn
```
