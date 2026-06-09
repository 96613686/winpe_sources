# CreateSecurityManager(IInternetSecurityManager * *)

- ea: `0x1800c2cb8`
- end: `0x1800c2d53`
- name: `?CreateSecurityManager@@YAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `155`
- prototype: `HRESULT __fastcall(IInternetSecurityManager **ppUnk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082dd0`

## callees

- `0x180019e20`
- `0x18005ed7c`
- `0x180060074`
- `0x1800c2cb8`
- `0x1800d6e48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c2d0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c2d0c`

## string_xrefs

- `0x1800c2d1e`: `Security`

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
0x1800c2cb8  mov     [rsp+arg_8], rbx
0x1800c2cbd  mov     [rsp+lock._pMutex], rcx
0x1800c2cc2  push    rdi
0x1800c2cc3  sub     rsp, 30h
0x1800c2cc7  xor     ebx, ebx
0x1800c2cc9  cmp     cs:?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA, rbx; IInternetSecurityManager * URL::g_pSecMgr
0x1800c2cd0  jnz     short loc_1800C2D45
0x1800c2cd2  mov     rdx, cs:?g_pMutexSR@@3PEAVCSMutex@@EA; pMutex
0x1800c2cd9  lea     rcx, [rsp+38h+lock]; this
0x1800c2cde  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1800c2ce3  cmp     cs:?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA, rbx; IInternetSecurityManager * URL::g_pSecMgr
0x1800c2cea  jnz     short loc_1800C2D3B
0x1800c2cec  lea     rdi, ?g_pSecMgr@URL@@2PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * URL::g_pSecMgr
0x1800c2cf3  xor     edx, edx; pUnkOuter
0x1800c2cf5  lea     r9, IID_IInternetSecurityManager; riid
0x1800c2cfc  mov     [rsp+38h+ppv], rdi; ppv
0x1800c2d01  lea     r8d, [rbx+1]; dwClsContext
0x1800c2d05  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800c2d0c  call    cs:__imp_CoCreateInstance
0x1800c2d13  nop     dword ptr [rax+rax+00h]
0x1800c2d18  mov     ebx, eax
0x1800c2d1a  test    eax, eax
0x1800c2d1c  js      short loc_1800C2D3B
0x1800c2d1e  lea     rdx, pName; "Security"
0x1800c2d25  mov     rcx, rdi; ppUnk
0x1800c2d28  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800c2d2d  mov     ebx, eax
0x1800c2d2f  test    eax, eax
0x1800c2d31  jns     short loc_1800C2D3B
0x1800c2d33  mov     rcx, rdi; ppref
0x1800c2d36  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c2d3b  lea     rcx, [rsp+38h+lock]; this
0x1800c2d40  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800c2d45  mov     eax, ebx
0x1800c2d47  mov     rbx, [rsp+38h+arg_8]
0x1800c2d4c  add     rsp, 30h
0x1800c2d50  pop     rdi
0x1800c2d51  retn
```
