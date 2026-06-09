# CreateSecurityManager(IInternetSecurityManager * *)

- ea: `0x100762a2`
- end: `0x10076310`
- name: `?CreateSecurityManager@@YGJPAPAUIInternetSecurityManager@@@Z`
- size: `110`
- prototype: `HRESULT __stdcall(IInternetSecurityManager **ppUnk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10130f3f`

## callees

- `0x1003fcda`
- `0x1003fd1f`
- `0x10040c44`
- `0x100762a2`
- `0x10076316`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100762dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100762dd`

## string_xrefs

- `0x100762e9`: `Security`

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
0x100762a2  mov     edi, edi
0x100762a4  push    ebp
0x100762a5  mov     ebp, esp
0x100762a7  push    ecx
0x100762a8  push    esi
0x100762a9  xor     esi, esi
0x100762ab  cmp     ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A, esi; IInternetSecurityManager * URL::g_pSecMgr
0x100762b1  jnz     short loc_1007630B
0x100762b3  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x100762b9  lea     ecx, [ebp+lock]; this
0x100762bc  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x100762c1  cmp     ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A, esi; IInternetSecurityManager * URL::g_pSecMgr
0x100762c7  jnz     short loc_10076303
0x100762c9  push    edi
0x100762ca  mov     edi, offset ?g_pSecMgr@URL@@2PAUIInternetSecurityManager@@A; IInternetSecurityManager * URL::g_pSecMgr
0x100762cf  push    edi; ppv
0x100762d0  push    offset _IID_IInternetSecurityManager; riid
0x100762d5  push    1; dwClsContext
0x100762d7  push    esi; pUnkOuter
0x100762d8  push    offset _CLSID_InternetSecurityManager; rclsid
0x100762dd  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100762e3  mov     esi, eax
0x100762e5  test    esi, esi
0x100762e7  js      short loc_10076302
0x100762e9  mov     edx, offset aSecurity; "Security"
0x100762ee  mov     ecx, edi; ppUnk
0x100762f0  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x100762f5  mov     esi, eax
0x100762f7  test    esi, esi
0x100762f9  jns     short loc_10076302
0x100762fb  mov     ecx, edi; ppref
0x100762fd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10076302  pop     edi
0x10076303  lea     ecx, [ebp+lock]; this
0x10076306  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x1007630b  mov     eax, esi
0x1007630d  pop     esi
0x1007630e  leave
0x1007630f  retn
```
