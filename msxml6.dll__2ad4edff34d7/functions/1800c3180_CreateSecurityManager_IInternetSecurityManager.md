# CreateSecurityManager(IInternetSecurityManager * *)

- ea: `0x1800c3180`
- end: `0x1800c3214`
- name: `?CreateSecurityManager@@YAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `148`
- prototype: `HRESULT __fastcall(IInternetSecurityManager **ppUnk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800837b4`

## callees

- `0x18000d7d0`
- `0x18005f3dc`
- `0x18005fbe0`
- `0x1800c3180`
- `0x1800d5198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c31d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c31d4`

## string_xrefs

- `0x1800c31e0`: `Security`

## pseudocode

```c
__int64 __fastcall CreateSecurityManager(IInternetSecurityManager **ppUnk)
{
  HRESULT Instance; // ebx
  MutexLock lock; // [rsp+40h] [rbp+8h] BYREF

  lock._pMutex = (Mutex *)ppUnk;
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
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800c3180  mov     [rsp+arg_8], rbx
0x1800c3185  mov     [rsp+lock._pMutex], rcx
0x1800c318a  push    rdi
0x1800c318b  sub     rsp, 30h
0x1800c318f  xor     ebx, ebx
0x1800c3191  cmp     cs:?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA, rbx; IInternetSecurityManager * URL::g_pSecMgr
0x1800c3198  jnz     short loc_1800C3207
0x1800c319a  mov     rdx, cs:?g_pMutexSR@@3PEAVCSMutex@@EA; pMutex
0x1800c31a1  lea     rcx, [rsp+38h+lock]; this
0x1800c31a6  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1800c31ab  cmp     cs:?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA, rbx; IInternetSecurityManager * URL::g_pSecMgr
0x1800c31b2  jnz     short loc_1800C31FD
0x1800c31b4  lea     rdi, ?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * URL::g_pSecMgr
0x1800c31bb  xor     edx, edx; pUnkOuter
0x1800c31bd  lea     r9, IID_IInternetSecurityManager; riid
0x1800c31c4  mov     [rsp+38h+ppv], rdi; ppv
0x1800c31c9  lea     r8d, [rbx+1]; dwClsContext
0x1800c31cd  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800c31d4  call    cs:__imp_CoCreateInstance
0x1800c31da  mov     ebx, eax
0x1800c31dc  test    eax, eax
0x1800c31de  js      short loc_1800C31FD
0x1800c31e0  lea     rdx, pName; "Security"
0x1800c31e7  mov     rcx, rdi; ppUnk
0x1800c31ea  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800c31ef  mov     ebx, eax
0x1800c31f1  test    eax, eax
0x1800c31f3  jns     short loc_1800C31FD
0x1800c31f5  mov     rcx, rdi; ppref
0x1800c31f8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c31fd  lea     rcx, [rsp+38h+lock]; this
0x1800c3202  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800c3207  mov     eax, ebx
0x1800c3209  mov     rbx, [rsp+38h+arg_8]
0x1800c320e  add     rsp, 30h
0x1800c3212  pop     rdi
0x1800c3213  retn
```
