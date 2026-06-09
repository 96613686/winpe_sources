# NetConnectionManager::NetConnectionManager(void)

- ea: `0x1802542dc`
- end: `0x18025437e`
- name: `??0NetConnectionManager@@QEAA@XZ`
- size: `162`
- prototype: `NetConnectionManager *__fastcall(NetConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1802536a0`

## callees

- `0x18012a85c`
- `0x1802542dc`
- `0x180254390`
- `0x180254400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802542f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802542f8`
- `WININET!InternetOpenW` at `0x180254342`
- `WININET!InternetOpenW` at `0x180254342`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
NetConnectionManager *__fastcall NetConnectionManager::NetConnectionManager(NetConnectionManager *this)
{
  HINTERNET v3; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)this = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  v3 = InternetOpenW(0, 0, 0, 0, 0x10000000u);
  ScopedHandle<NetHandlePolicy,void *>::operator=((char *)this + 48, &v3);
  ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(&v3);
  if ( !*((_QWORD *)this + 6) )
    OSException::ThrowLastError();
  return this;
}

```

## disassembly

```asm
0x1802542dc  mov     [rsp+arg_10], rbx
0x1802542e1  mov     [rsp+arg_0], rcx
0x1802542e6  push    rdi
0x1802542e7  sub     rsp, 30h
0x1802542eb  mov     rdi, rcx
0x1802542ee  mov     dword ptr [rcx], 0
0x1802542f4  add     rcx, 8; lpCriticalSection
0x1802542f8  call    cs:__imp_InitializeCriticalSection
0x1802542fe  nop
0x1802542ff  lea     rbx, [rdi+30h]
0x180254303  mov     qword ptr [rbx], 0
0x18025430a  mov     qword ptr [rdi+38h], 0
0x180254312  mov     dword ptr [rdi+40h], 0
0x180254319  mov     qword ptr [rdi+48h], 0
0x180254321  mov     qword ptr [rdi+50h], 0
0x180254329  mov     dword ptr [rdi+58h], 0
0x180254330  mov     [rsp+38h+dwFlags], 10000000h; dwFlags
0x180254338  xor     r9d, r9d; lpszProxyBypass
0x18025433b  xor     r8d, r8d; lpszProxy
0x18025433e  xor     edx, edx; dwAccessType
0x180254340  xor     ecx, ecx; lpszAgent
0x180254342  call    cs:__imp_InternetOpenW
0x180254348  mov     [rsp+38h+arg_8], rax
0x18025434d  lea     rdx, [rsp+38h+arg_8]
0x180254352  mov     rcx, rbx
0x180254355  call    ??4?$ScopedHandle@UNetHandlePolicy@@PEAX@@QEAAAEAV0@$$QEAV0@@Z; ScopedHandle<NetHandlePolicy,void *>::operator=(ScopedHandle<NetHandlePolicy,void *> &&)
0x18025435a  lea     rcx, [rsp+38h+arg_8]
0x18025435f  call    ??1?$ScopedHandle@UNetHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(void)
0x180254364  cmp     qword ptr [rbx], 0
0x180254368  jnz     short loc_180254370
0x18025436a  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x180254370  mov     rax, rdi
0x180254373  mov     rbx, [rsp+38h+arg_10]
0x180254378  add     rsp, 30h
0x18025437c  pop     rdi
0x18025437d  retn
```
