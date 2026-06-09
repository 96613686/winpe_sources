# CreateSecurityManager(IInternetSecurityManager * *)

- ea: `0x100762d2`
- end: `0x10076340`
- name: `?CreateSecurityManager@@YGJPAPAUIInternetSecurityManager@@@Z`
- size: `110`
- prototype: `HRESULT __stdcall(IInternetSecurityManager **ppUnk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1013104f`

## callees

- `0x1003fc4a`
- `0x1003fc8f`
- `0x10040bb4`
- `0x100762d2`
- `0x10076346`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1007630d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1007630d`

## string_xrefs

- `0x10076319`: `Security`

## pseudocode

```c
HRESULT __stdcall CreateSecurityManager()
{
  HRESULT Instance; // esi
  MutexLock lock; // [esp+4h] [ebp-4h] BYREF

  Instance = 0;
  if ( !URL::g_pSecMgr )
  {
    MutexLock::MutexLock(&lock, g_pMutexSR);
    if ( !URL::g_pSecMgr )
    {
      Instance = CoCreateInstance(
                   &CLSID_InternetSecurityManager,
                   0,
                   1u,
                   &IID_IInternetSecurityManager,
                   (LPVOID *)&URL::g_pSecMgr);
      if ( Instance >= 0 )
      {
        Instance = RegisterStaticUnknown(&URL::g_pSecMgr, "Security");
        if ( Instance < 0 )
          release(&URL::g_pSecMgr);
      }
    }
    MutexLock::Release(&lock);
  }
  return Instance;
}

```

## disassembly

```asm
0x100762d2  mov     edi, edi
0x100762d4  push    ebp
0x100762d5  mov     ebp, esp
0x100762d7  push    ecx
0x100762d8  push    esi
0x100762d9  xor     esi, esi
0x100762db  cmp     ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A, esi; IInternetSecurityManager * URL::g_pSecMgr
0x100762e1  jnz     short loc_1007633B
0x100762e3  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x100762e9  lea     ecx, [ebp+lock]; this
0x100762ec  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x100762f1  cmp     ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A, esi; IInternetSecurityManager * URL::g_pSecMgr
0x100762f7  jnz     short loc_10076333
0x100762f9  push    edi
0x100762fa  mov     edi, offset ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A; IInternetSecurityManager * URL::g_pSecMgr
0x100762ff  push    edi; ppv
0x10076300  push    offset _IID_IInternetSecurityManager; riid
0x10076305  push    1; dwClsContext
0x10076307  push    esi; pUnkOuter
0x10076308  push    offset _CLSID_InternetSecurityManager; rclsid
0x1007630d  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10076313  mov     esi, eax
0x10076315  test    esi, esi
0x10076317  js      short loc_10076332
0x10076319  mov     edx, offset aSecurity; "Security"
0x1007631e  mov     ecx, edi; ppUnk
0x10076320  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x10076325  mov     esi, eax
0x10076327  test    esi, esi
0x10076329  jns     short loc_10076332
0x1007632b  mov     ecx, edi; ppref
0x1007632d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10076332  pop     edi
0x10076333  lea     ecx, [ebp+lock]; this
0x10076336  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x1007633b  mov     eax, esi
0x1007633d  pop     esi
0x1007633e  leave
0x1007633f  retn
```
