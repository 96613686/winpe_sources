# CJobSharedData::VerifyCallerIdentity(void)

- ea: `0x1800940f4`
- end: `0x180094211`
- name: `?VerifyCallerIdentity@CJobSharedData@@QEBAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800171c0`
- `0x18008d49c`
- `0x180096410`

## callees

- `0x1800095a0`
- `0x18000cea4`
- `0x1800940f4`
- `0x1800ac58c`
- `0x1800ac64c`
- `0x1800f82f0`
- `0x1801099b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009413d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009413d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094181`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800941a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094181`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800941a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180094193`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800941bb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800941ce`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180094193`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800941bb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800941ce`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180094110`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180094110`

## string_xrefs

- `0x1800941fe`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CJobSharedData::VerifyCallerIdentity(RTL_SRWLOCK *this)
{
  HRESULT v2; // eax
  RTL_SRWLOCK *v3; // rdx
  void **v4; // rcx
  const char *v5; // r9
  __int64 result; // rax
  void *v7; // rcx
  int v8; // [rsp+20h] [rbp-38h]
  void *Buf1[2]; // [rsp+28h] [rbp-30h] BYREF
  size_t Size; // [rsp+38h] [rbp-20h]
  unsigned __int64 v11; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = CoImpersonateClient();
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v2,
        v8);
    GetUserIdFromToken(Buf1);
    AcquireSRWLockShared(this + 34);
    v3 = this + 8;
    if ( this[11].Ptr > (PVOID)0xF )
      v3 = (RTL_SRWLOCK *)v3->Ptr;
    v4 = Buf1;
    if ( v11 > 0xF )
      v4 = (void **)Buf1[0];
    if ( (PVOID)Size == this[10].Ptr && (!Size || !memcmp(v4, v3, Size)) )
    {
      ReleaseSRWLockShared(this + 34);
      std::string::~string(Buf1);
      CoRevertToSelf();
      result = 0;
    }
    else
    {
      ReleaseSRWLockShared(this + 34);
      if ( IsAdminToken(v7) )
      {
        std::string::~string(Buf1);
        CoRevertToSelf();
        result = 0;
      }
      else
      {
        std::string::~string(Buf1);
        CoRevertToSelf();
        result = 2147942405LL;
      }
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA36,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800940f4  mov     [rsp+arg_8], rbx
0x1800940f9  push    rdi
0x1800940fa  sub     rsp, 50h
0x1800940fe  mov     rax, cs:__security_cookie
0x180094105  xor     rax, rsp
0x180094108  mov     [rsp+58h+var_10], rax
0x18009410d  mov     rdi, rcx
0x180094110  call    cs:__imp_CoImpersonateClient
0x180094116  mov     rcx, [rsp+58h]; this
0x18009411b  test    eax, eax
0x18009411d  js      loc_1800941FB
0x180094123  mov     byte ptr [rsp+58h+var_38], 1
0x180094128  lea     rcx, [rsp+58h+Buf1]
0x18009412d  call    ?GetUserIdFromToken@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetUserIdFromToken(void *)
0x180094132  nop
0x180094133  lea     rbx, [rdi+110h]
0x18009413a  mov     rcx, rbx; SRWLock
0x18009413d  call    cs:__imp_AcquireSRWLockShared
0x180094143  lea     rdx, [rdi+40h]
0x180094147  mov     rax, [rdx+10h]
0x18009414b  cmp     qword ptr [rdx+18h], 0Fh
0x180094150  jbe     short loc_180094155
0x180094152  mov     rdx, [rdx]; Buf2
0x180094155  lea     rcx, [rsp+58h+Buf1]
0x18009415a  cmp     [rsp+58h+var_18], 0Fh
0x180094160  cmova   rcx, [rsp+58h+Buf1]; Buf1
0x180094166  mov     r8, [rsp+58h+Size]; Size
0x18009416b  cmp     r8, rax
0x18009416e  jnz     short loc_18009419D
0x180094170  test    r8, r8
0x180094173  jz      short loc_18009417E
0x180094175  call    memcmp
0x18009417a  test    eax, eax
0x18009417c  jnz     short loc_18009419D
0x18009417e  mov     rcx, rbx; SRWLock
0x180094181  call    cs:__imp_ReleaseSRWLockShared
0x180094187  nop
0x180094188  lea     rcx, [rsp+58h+Buf1]; void *
0x18009418d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180094192  nop
0x180094193  call    cs:__imp_CoRevertToSelf
0x180094199  xor     eax, eax
0x18009419b  jmp     short loc_1800941E3
0x18009419d  mov     rcx, rbx; SRWLock
0x1800941a0  call    cs:__imp_ReleaseSRWLockShared
0x1800941a6  call    ?IsAdminToken@@YA_NPEAX@Z; IsAdminToken(void *)
0x1800941ab  nop
0x1800941ac  lea     rcx, [rsp+58h+Buf1]; void *
0x1800941b1  test    al, al
0x1800941b3  jnz     short loc_1800941C8
0x1800941b5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800941ba  nop
0x1800941bb  call    cs:__imp_CoRevertToSelf
0x1800941c1  mov     eax, 80070005h
0x1800941c6  jmp     short loc_1800941E3
0x1800941c8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800941cd  nop
0x1800941ce  call    cs:__imp_CoRevertToSelf
0x1800941d4  xor     eax, eax
0x1800941d6  jmp     short loc_1800941E3
0x1800941d8  mov     eax, 8007000Eh
0x1800941dd  jmp     short loc_1800941E3
0x1800941df  mov     eax, [rsp+58h+var_34]
0x1800941e3  mov     rcx, [rsp+58h+var_10]
0x1800941e8  xor     rcx, rsp; StackCookie
0x1800941eb  call    __security_check_cookie
0x1800941f0  mov     rbx, [rsp+58h+arg_8]
0x1800941f5  add     rsp, 50h
0x1800941f9  pop     rdi
0x1800941fa  retn
0x1800941fb  mov     r9d, eax; char *
0x1800941fe  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180094205  mov     edx, 1262h; void *
0x18009420a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
