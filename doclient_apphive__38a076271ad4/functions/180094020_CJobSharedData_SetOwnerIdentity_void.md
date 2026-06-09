# CJobSharedData::SetOwnerIdentity(void)

- ea: `0x180094020`
- end: `0x1800940ed`
- name: `?SetOwnerIdentity@CJobSharedData@@QEAAXXZ`
- size: `205`
- prototype: `void __fastcall(CJobSharedData *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180088104`

## callees

- `0x1800095a0`
- `0x18000cea4`
- `0x1800179a4`
- `0x180094020`
- `0x1800ac4ac`
- `0x1800ac58c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009409b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009409b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180094073`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180094073`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800940b7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800940b7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18009403c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18009403c`

## string_xrefs

- `0x1800940db`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CJobSharedData::SetOwnerIdentity(RTL_SRWLOCK *this)
{
  HRESULT v2; // eax
  int v3; // [rsp+20h] [rbp-58h]
  _BYTE v4[32]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v5[32]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1262,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v3);
  GetUserIdFromToken(v5);
  GetAppIdFromToken((__int64)v4);
  AcquireSRWLockExclusive(this + 34);
  std::string::operator=(&this[8], v5);
  std::string::operator=(&this[16], v4);
  ReleaseSRWLockExclusive(this + 34);
  std::string::~string(v4);
  std::string::~string(v5);
  CoRevertToSelf();
}

```

## disassembly

```asm
0x180094020  mov     [rsp+arg_8], rbx
0x180094025  push    rdi
0x180094026  sub     rsp, 70h
0x18009402a  mov     rax, cs:__security_cookie
0x180094031  xor     rax, rsp
0x180094034  mov     [rsp+78h+var_10], rax
0x180094039  mov     rdi, rcx
0x18009403c  call    cs:__imp_CoImpersonateClient
0x180094042  mov     rcx, [rsp+78h]; this
0x180094047  test    eax, eax
0x180094049  js      loc_1800940D8
0x18009404f  mov     [rsp+78h+var_58], 1
0x180094054  lea     rcx, [rsp+78h+var_30]
0x180094059  call    ?GetUserIdFromToken@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetUserIdFromToken(void *)
0x18009405e  nop
0x18009405f  lea     rcx, [rsp+78h+var_50]
0x180094064  call    ?GetAppIdFromToken@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetAppIdFromToken(void *)
0x180094069  lea     rbx, [rdi+110h]
0x180094070  mov     rcx, rbx; SRWLock
0x180094073  call    cs:__imp_AcquireSRWLockExclusive
0x180094079  lea     rcx, [rdi+40h]
0x18009407d  lea     rdx, [rsp+78h+var_30]
0x180094082  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180094087  lea     rcx, [rdi+80h]
0x18009408e  lea     rdx, [rsp+78h+var_50]
0x180094093  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180094098  mov     rcx, rbx; SRWLock
0x18009409b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800940a1  lea     rcx, [rsp+78h+var_50]; void *
0x1800940a6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800940ab  nop
0x1800940ac  lea     rcx, [rsp+78h+var_30]; void *
0x1800940b1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800940b6  nop
0x1800940b7  call    cs:__imp_CoRevertToSelf
0x1800940bd  mov     rcx, [rsp+78h+var_10]
0x1800940c2  xor     rcx, rsp; StackCookie
0x1800940c5  call    __security_check_cookie
0x1800940ca  mov     rbx, [rsp+78h+arg_8]
0x1800940d2  add     rsp, 70h
0x1800940d6  pop     rdi
0x1800940d7  retn
0x1800940d8  mov     r9d, eax; char *
0x1800940db  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800940e2  mov     edx, 1262h; void *
0x1800940e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
