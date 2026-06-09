# ServerGroupManager::getServersByGroup(ProxyContext *,uchar,ushort const *,RemoteServer const *,RequestStack &)

- ea: `0x180021db8`
- end: `0x180021ebe`
- name: `?getServersByGroup@ServerGroupManager@@QEBAXPEAVProxyContext@@EPEBGPEBVRemoteServer@@AEAVRequestStack@@@Z`
- size: `262`
- prototype: `void __fastcall(ServerGroupManager *__hidden this, struct ProxyContext *, unsigned __int8, const unsigned __int16 *Key, const struct RemoteServer *, struct RequestStack *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021828`

## callees

- `0x1800020f4`
- `0x180021db8`
- `0x180021f58`
- `0x180029cb4`
- `0x180029ee4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180021e84`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180021e84`
- `msvcrt!bsearch` at `0x180021e13`
- `msvcrt!bsearch` at `0x180021e13`
- `KERNEL32!GetCurrentThreadId` at `0x180021ddf`
- `KERNEL32!GetCurrentThreadId` at `0x180021e53`
- `KERNEL32!GetCurrentThreadId` at `0x180021ddf`
- `KERNEL32!GetCurrentThreadId` at `0x180021e53`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServerGroupManager::getServersByGroup(
        ServerGroupManager *this,
        struct ProxyContext *a2,
        unsigned __int8 a3,
        const unsigned __int16 *Key,
        const struct RemoteServer *a5,
        struct RequestStack *a6)
{
  ServerGroupManager *v9; // rdi
  char v10; // si
  DWORD CurrentThreadId; // eax
  ServerGroup **v12; // rax
  DWORD v13; // eax
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-30h] BYREF
  ServerGroupManager *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = this;
  v9 = this;
  v10 = 0;
  CurrentThreadId = GetCurrentThreadId();
  Perimeter::Lock(v9, CurrentThreadId);
  v12 = (ServerGroup **)bsearch(
                          Key,
                          *((const void **)v9 + 12),
                          (__int64)(*((_QWORD *)v9 + 13) - *((_QWORD *)v9 + 12)) >> 3,
                          8u,
                          findGroupByName);
  if ( v12 && *v12 )
  {
    try
    {
      ServerGroup::getServersForRequest(*v12, a2, a3, a5, a6);
    }
    catch ( std::bad_alloc )
    {
      v9 = v15;
      v10 = 1;
    }
  }
  v13 = GetCurrentThreadId();
  Perimeter::Unlock(v9, v13);
  if ( v10 )
  {
    v15 = (ServerGroupManager *)"bad allocation";
    exception::exception((exception *)pExceptionObject, (const char *const *)&v15, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180021db8  mov     [rsp+arg_8], rbx
0x180021dbd  mov     [rsp+arg_10], rsi
0x180021dc2  mov     [rsp+arg_0], rcx
0x180021dc7  push    rdi
0x180021dc8  push    r14
0x180021dca  push    r15
0x180021dcc  sub     rsp, 50h
0x180021dd0  mov     rbx, r9
0x180021dd3  mov     r14b, r8b
0x180021dd6  mov     r15, rdx
0x180021dd9  mov     rdi, rcx
0x180021ddc  xor     sil, sil
0x180021ddf  call    cs:__imp_GetCurrentThreadId
0x180021de5  mov     edx, eax; unsigned int
0x180021de7  mov     rcx, rdi; this
0x180021dea  call    ?Lock@Perimeter@@QEAAXK@Z; Perimeter::Lock(ulong)
0x180021def  mov     rdx, [rdi+60h]; Base
0x180021df3  mov     r8, [rdi+68h]
0x180021df7  sub     r8, rdx
0x180021dfa  sar     r8, 3; NumOfElements
0x180021dfe  lea     rax, ?findGroupByName@@YAHPEBXPEBQEBVServerGroup@@@Z; findGroupByName(void const *,ServerGroup const * const *)
0x180021e05  mov     [rsp+68h+CompareFunction], rax; CompareFunction
0x180021e0a  mov     r9d, 8; SizeOfElements
0x180021e10  mov     rcx, rbx; Key
0x180021e13  call    cs:__imp_bsearch
0x180021e19  test    rax, rax
0x180021e1c  jz      short loc_180021E53
0x180021e1e  mov     rcx, [rax]; this
0x180021e21  test    rcx, rcx
0x180021e24  jz      short loc_180021E53
0x180021e26  mov     rax, [rsp+68h+arg_28]
0x180021e2e  mov     [rsp+68h+CompareFunction], rax; struct RequestStack *
0x180021e33  mov     r9, [rsp+68h+arg_20]; struct RemoteServer *
0x180021e3b  mov     r8b, r14b; unsigned __int8
0x180021e3e  mov     rdx, r15; struct ProxyContext *
0x180021e41  call    ?getServersForRequest@ServerGroup@@QEBAXPEAVProxyContext@@EPEBVRemoteServer@@AEAVRequestStack@@@Z; ServerGroup::getServersForRequest(ProxyContext *,uchar,RemoteServer const *,RequestStack &)
0x180021e46  nop
0x180021e47  jmp     short loc_180021E53
0x180021e49  mov     rdi, [rsp+68h+arg_0]
0x180021e4e  mov     sil, [rsp+68h+var_38]
0x180021e53  call    cs:__imp_GetCurrentThreadId
0x180021e59  mov     edx, eax; unsigned int
0x180021e5b  mov     rcx, rdi; this
0x180021e5e  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x180021e63  test    sil, sil
0x180021e66  jz      short loc_180021EA8
0x180021e68  lea     rax, aBadAllocation; "bad allocation"
0x180021e6f  mov     [rsp+68h+arg_0], rax
0x180021e74  mov     r8d, 1
0x180021e7a  lea     rdx, [rsp+68h+arg_0]
0x180021e7f  lea     rcx, [rsp+68h+pExceptionObject]
0x180021e84  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180021e8a  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180021e91  mov     [rsp+68h+pExceptionObject], rax
0x180021e96  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180021e9d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180021ea2  call    _CxxThrowException_0
0x180021ea8  lea     r11, [rsp+68h+var_18]
0x180021ead  mov     rbx, [r11+28h]
0x180021eb1  mov     rsi, [r11+30h]
0x180021eb5  mov     rsp, r11
0x180021eb8  pop     r15
0x180021eba  pop     r14
0x180021ebc  pop     rdi
0x180021ebd  retn
```
