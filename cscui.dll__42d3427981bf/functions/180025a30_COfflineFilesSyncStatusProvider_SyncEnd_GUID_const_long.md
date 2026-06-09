# COfflineFilesSyncStatusProvider::SyncEnd(_GUID const &,long)

- ea: `0x180025a30`
- end: `0x180025ae4`
- name: `?SyncEnd@COfflineFilesSyncStatusProvider@@QEAAJAEBU_GUID@@J@Z`
- size: `180`
- prototype: `__int64 __fastcall(COfflineFilesSyncStatusProvider *__hidden this, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021fa0`

## callees

- `0x180025a30`
- `0x180025ba4`
- `0x18003fe40`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025aa6`
- `ntdll!RtlReleaseResource` at `0x180025ac1`
- `ntdll!RtlReleaseResource` at `0x180025ac1`
- `ntdll!RtlAcquireResourceShared` at `0x180025a6d`
- `ntdll!RtlAcquireResourceShared` at `0x180025a6d`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncStatusProvider::SyncEnd(
        COfflineFilesSyncStatusProvider *this,
        const struct _GUID *a2)
{
  struct _GUID v2; // xmm0
  CSyncItemLog *v4; // rcx
  const unsigned __int16 *v6; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+30h] [rbp-38h] BYREF
  struct IOfflineFilesSyncItem *v8; // [rsp+38h] [rbp-30h] BYREF
  struct _GUID v9; // [rsp+40h] [rbp-28h] BYREF

  v2 = *a2;
  v8 = 0;
  pv = 0;
  v9 = v2;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 48), 1u);
  v4 = (CSyncItemLog *)*((_QWORD *)this + 5);
  if ( v4 && (int)CSyncItemLog::QueryEntryByID(v4, &v9, (unsigned __int16 **)&pv, &v8, v6) >= 0 )
  {
    COfflineFilesSyncStatusProvider::_NotifySyncStatus(this, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    (*(void (__fastcall **)(struct IOfflineFilesSyncItem *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 48));
  return 0;
}

```

## disassembly

```asm
0x180025a30  mov     [rsp+arg_10], rbx
0x180025a35  push    rdi
0x180025a36  sub     rsp, 60h
0x180025a3a  mov     rax, cs:__security_cookie
0x180025a41  xor     rax, rsp
0x180025a44  mov     [rsp+68h+var_18], rax
0x180025a49  movups  xmm0, xmmword ptr [rdx]
0x180025a4c  mov     rdi, rcx
0x180025a4f  mov     [rsp+68h+var_30], 0
0x180025a58  mov     dl, 1; Wait
0x180025a5a  mov     [rsp+68h+pv], 0
0x180025a63  add     rcx, 30h ; '0'; Resource
0x180025a67  movdqu  xmmword ptr [rsp+68h+var_28.Data1], xmm0
0x180025a6d  call    cs:__imp_RtlAcquireResourceShared
0x180025a73  mov     rcx, [rdi+28h]; this
0x180025a77  test    rcx, rcx
0x180025a7a  jz      short loc_180025ABD
0x180025a7c  lea     r9, [rsp+68h+var_30]; struct IOfflineFilesSyncItem **
0x180025a81  lea     r8, [rsp+68h+pv]; unsigned __int16 **
0x180025a86  lea     rdx, [rsp+68h+var_28]; struct _GUID *
0x180025a8b  call    ?QueryEntryByID@CSyncItemLog@@QEAAJPEAU_GUID@@PEAPEAGPEAPEAUIOfflineFilesSyncItem@@PEBG@Z; CSyncItemLog::QueryEntryByID(_GUID *,ushort * *,IOfflineFilesSyncItem * *,ushort const *)
0x180025a90  test    eax, eax
0x180025a92  js      short loc_180025ABD
0x180025a94  mov     rdx, [rsp+68h+pv]; unsigned __int16 *
0x180025a99  mov     rcx, rdi; this
0x180025a9c  call    ?_NotifySyncStatus@COfflineFilesSyncStatusProvider@@AEAAJPEBG@Z; COfflineFilesSyncStatusProvider::_NotifySyncStatus(ushort const *)
0x180025aa1  mov     rcx, [rsp+68h+pv]; pv
0x180025aa6  call    cs:__imp_CoTaskMemFree
0x180025aac  mov     rcx, [rsp+68h+var_30]
0x180025ab1  mov     rax, [rcx]
0x180025ab4  mov     rax, [rax+10h]
0x180025ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025abd  lea     rcx, [rdi+30h]; Resource
0x180025ac1  call    cs:__imp_RtlReleaseResource
0x180025ac7  xor     eax, eax
0x180025ac9  mov     rcx, [rsp+68h+var_18]
0x180025ace  xor     rcx, rsp; StackCookie
0x180025ad1  call    __security_check_cookie
0x180025ad6  mov     rbx, [rsp+68h+arg_10]
0x180025ade  add     rsp, 60h
0x180025ae2  pop     rdi
0x180025ae3  retn
```
