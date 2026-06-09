# CHttpAgent::_DoSendRequest(void *)

- ea: `0x1800cd460`
- end: `0x1800cd71a`
- name: `?_DoSendRequest@CHttpAgent@@AEAAJPEAX@Z`
- size: `698`
- prototype: `__int64 __fastcall(CHttpAgent *__hidden this, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800ccb24`
- `0x1800d0780`

## callees

- `0x180008cbc`
- `0x18000933c`
- `0x180009ab4`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800cd460`
- `0x1800cf144`
- `0x1800d0318`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd656`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd640`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd640`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd5af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd67f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd6bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd5af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd67f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd6bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd535`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd660`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd535`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd660`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cd676`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cd676`
- `WINHTTP!WinHttpSendRequest` at `0x1800cd5f7`
- `WINHTTP!WinHttpSendRequest` at `0x1800cd5f7`

## string_xrefs

- `0x1800cd618`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cd694`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHttpAgent::_DoSendRequest(CHttpAgent *this, void *a2)
{
  char *v3; // rdi
  char v4; // r12
  unsigned int LastErrorMsg; // r14d
  __int64 *v6; // rdx
  __int64 *v7; // rax
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD dwTotalLength; // r13d
  _QWORD *v12; // rbx
  bool v13; // zf
  int dwOptionalLength; // [rsp+20h] [rbp-60h]
  HINTERNET hRequest; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  hRequest = a2;
  v3 = (char *)this + 280;
  if ( (unsigned int)mtx_do_lock((char *)this + 280) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v3 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v4 = 1;
  if ( *((_BYTE *)this + 387) )
  {
    LastErrorMsg = -2147467260;
  }
  else
  {
    v6 = (__int64 *)*((_QWORD *)this + 3);
    v7 = (__int64 *)v6[1];
    v8 = v6;
    while ( !*((_BYTE *)v7 + 25) )
    {
      if ( v7[4] >= (unsigned __int64)hRequest )
        v8 = v7;
      else
        v7 += 2;
      v7 = (__int64 *)*v7;
    }
    if ( *((_BYTE *)v8 + 25) || (unsigned __int64)hRequest < v8[4] || v8 == v6 )
    {
      LastErrorMsg = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31F,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
        (const char *)0x80070490LL,
        dwOptionalLength);
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 33);
      if ( ++*((_DWORD *)this + 69) == 1 )
        _InterlockedExchange((volatile __int32 *)this + 68, 0);
      ReleaseSRWLockExclusive((PSRWLOCK)this + 33);
      v9 = std::map<void *,CHttpAgent::RequestCtx>::operator[]((char *)this + 24, &hRequest);
      if ( *(_BYTE *)(v9 + 106) )
      {
        LastErrorMsg = -2147467260;
      }
      else
      {
        v10 = v9 + 40;
        dwTotalLength = *(_DWORD *)(v9 + 24);
        if ( dwTotalLength )
        {
          v12 = (_QWORD *)(v9 + 8);
          if ( *(_QWORD *)(v9 + 32) > 0xFu )
            v12 = (_QWORD *)*v12;
        }
        else
        {
          v12 = 0;
        }
        if ( !v3 )
          std::_Throw_system_error(1);
        v13 = (*((_DWORD *)v3 + 19))-- == 1;
        if ( v13 )
        {
          *((_DWORD *)v3 + 18) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
        }
        v4 = 0;
        CHttpAgent::_ImpersonateUserToken((__int64)this);
        if ( *(_QWORD *)(v10 + 24) > 7u )
          v10 = *(_QWORD *)v10;
        if ( WinHttpSendRequest(hRequest, (LPCWSTR)v10, 0xFFFFFFFF, v12, dwTotalLength, dwTotalLength, 0) )
          LastErrorMsg = 0;
        else
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0x330,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                           "Failed to send request = 0x%p",
                           (const char *)hRequest);
      }
      AcquireSRWLockExclusive((PSRWLOCK)this + 33);
      v13 = (*((_DWORD *)this + 69))-- == 1;
      if ( v13 )
      {
        *((_DWORD *)this + 68) = 1;
        WakeByAddressAll((char *)this + 272);
      }
      ReleaseSRWLockExclusive((PSRWLOCK)this + 33);
    }
  }
  if ( v4 )
  {
    v13 = (*((_DWORD *)v3 + 19))-- == 1;
    if ( v13 )
    {
      *((_DWORD *)v3 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
    }
  }
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1800cd460  mov     [rsp-38h+arg_10], rbx
0x1800cd465  push    rbp
0x1800cd466  push    rsi
0x1800cd467  push    rdi
0x1800cd468  push    r12
0x1800cd46a  push    r13
0x1800cd46c  push    r14
0x1800cd46e  push    r15
0x1800cd470  mov     rbp, rsp
0x1800cd473  sub     rsp, 80h
0x1800cd47a  mov     rax, cs:__security_cookie
0x1800cd481  xor     rax, rsp
0x1800cd484  mov     [rbp+var_8], rax
0x1800cd488  mov     r15, rcx
0x1800cd48b  mov     [rbp+hRequest], rdx
0x1800cd48f  xorps   xmm0, xmm0
0x1800cd492  movups  [rbp+var_38], xmm0
0x1800cd496  lea     rdi, [rcx+118h]
0x1800cd49d  mov     qword ptr [rbp+var_38], rdi
0x1800cd4a1  xor     r13d, r13d
0x1800cd4a4  mov     byte ptr [rbp+var_38+8], r13b
0x1800cd4a8  mov     rcx, rdi
0x1800cd4ab  call    mtx_do_lock
0x1800cd4b0  test    eax, eax
0x1800cd4b2  jnz     loc_1800CD6F7
0x1800cd4b8  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800cd4bf  jz      loc_1800CD702
0x1800cd4c5  mov     r12b, 1
0x1800cd4c8  mov     byte ptr [rbp+var_38+8], r12b
0x1800cd4cc  cmp     [r15+183h], r13b
0x1800cd4d3  jz      short loc_1800CD4E0
0x1800cd4d5  mov     r14d, 80004004h
0x1800cd4db  jmp     loc_1800CD6A6
0x1800cd4e0  mov     rdx, [r15+18h]
0x1800cd4e4  mov     rax, [rdx+8]
0x1800cd4e8  xor     ecx, ecx
0x1800cd4ea  mov     [rbp+var_1C], ecx
0x1800cd4ed  mov     rcx, rdx
0x1800cd4f0  mov     r8, [rbp+hRequest]
0x1800cd4f4  jmp     short loc_1800CD508
0x1800cd4f6  cmp     [rax+20h], r8
0x1800cd4fa  jnb     short loc_1800CD502
0x1800cd4fc  add     rax, 10h
0x1800cd500  jmp     short loc_1800CD505
0x1800cd502  mov     rcx, rax
0x1800cd505  mov     rax, [rax]
0x1800cd508  cmp     [rax+19h], r13b
0x1800cd50c  jz      short loc_1800CD4F6
0x1800cd50e  cmp     [rcx+19h], r13b
0x1800cd512  jnz     loc_1800CD687
0x1800cd518  cmp     r8, [rcx+20h]
0x1800cd51c  jb      loc_1800CD687
0x1800cd522  cmp     rcx, rdx
0x1800cd525  jz      loc_1800CD687
0x1800cd52b  lea     rsi, [r15+108h]
0x1800cd532  mov     rcx, rsi; SRWLock
0x1800cd535  call    cs:__imp_AcquireSRWLockExclusive
0x1800cd53b  inc     dword ptr [rsi+0Ch]
0x1800cd53e  cmp     dword ptr [rsi+0Ch], 1
0x1800cd542  jnz     short loc_1800CD54A
0x1800cd544  mov     eax, r13d
0x1800cd547  xchg    eax, [rsi+8]
0x1800cd54a  mov     [rbp+Token], rsi
0x1800cd54e  mov     rcx, rsi; SRWLock
0x1800cd551  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd557  nop
0x1800cd558  lea     rdx, [rbp+hRequest]
0x1800cd55c  lea     rcx, [r15+18h]
0x1800cd560  call    ??A?$map@PEAXURequestCtx@CHttpAgent@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXURequestCtx@CHttpAgent@@@std@@@4@@std@@QEAAAEAURequestCtx@CHttpAgent@@AEBQEAX@Z; std::map<void *,CHttpAgent::RequestCtx>::operator[](void * const &)
0x1800cd565  cmp     [rax+6Ah], r13b
0x1800cd569  jz      short loc_1800CD576
0x1800cd56b  mov     r14d, 80004004h
0x1800cd571  jmp     loc_1800CD65D
0x1800cd576  lea     r14, [rax+28h]
0x1800cd57a  mov     r13d, [rax+18h]
0x1800cd57e  test    r13d, r13d
0x1800cd581  jz      short loc_1800CD593
0x1800cd583  lea     rbx, [rax+8]
0x1800cd587  cmp     qword ptr [rbx+18h], 0Fh
0x1800cd58c  jbe     short loc_1800CD595
0x1800cd58e  mov     rbx, [rbx]
0x1800cd591  jmp     short loc_1800CD595
0x1800cd593  xor     ebx, ebx
0x1800cd595  test    rdi, rdi
0x1800cd598  jz      loc_1800CD6EC
0x1800cd59e  sub     dword ptr [rdi+4Ch], 1
0x1800cd5a2  jnz     short loc_1800CD5B5
0x1800cd5a4  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cd5ab  lea     rcx, [rdi+10h]; SRWLock
0x1800cd5af  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd5b5  xor     r12b, r12b
0x1800cd5b8  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800cd5c0  lea     rdx, [rbp+Token]
0x1800cd5c4  mov     rcx, r15
0x1800cd5c7  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cd5cc  cmp     qword ptr [r14+18h], 7
0x1800cd5d1  jbe     short loc_1800CD5D6
0x1800cd5d3  mov     r14, [r14]
0x1800cd5d6  mov     [rsp+80h+dwContext], 0; dwContext
0x1800cd5df  mov     [rsp+80h+dwTotalLength], r13d; dwTotalLength
0x1800cd5e4  mov     [rsp+80h+dwOptionalLength], r13d; dwOptionalLength
0x1800cd5e9  mov     r9, rbx; lpOptional
0x1800cd5ec  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800cd5f0  mov     rdx, r14; lpszHeaders
0x1800cd5f3  mov     rcx, [rbp+hRequest]; hRequest
0x1800cd5f7  call    cs:__imp_WinHttpSendRequest
0x1800cd5fd  xor     r13d, r13d
0x1800cd600  test    eax, eax
0x1800cd602  jnz     short loc_1800CD62E
0x1800cd604  mov     rax, [rbp+hRequest]
0x1800cd608  mov     rcx, [rbp+38h]; this
0x1800cd60c  mov     qword ptr [rsp+80h+dwOptionalLength], rax; char *
0x1800cd611  lea     r9, aFailedToSendRe_0; "Failed to send request = 0x%p"
0x1800cd618  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cd61f  mov     edx, 330h; void *
0x1800cd624  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800cd629  mov     r14d, eax
0x1800cd62c  jmp     short loc_1800CD631
0x1800cd62e  mov     r14d, r13d
0x1800cd631  mov     rbx, [rbp+Token]
0x1800cd635  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd639  jz      short loc_1800CD65D
0x1800cd63b  mov     rdx, rbx; Token
0x1800cd63e  xor     ecx, ecx; Thread
0x1800cd640  call    cs:__imp_SetThreadToken
0x1800cd646  test    eax, eax
0x1800cd648  jz      loc_1800CD714
0x1800cd64e  test    rbx, rbx
0x1800cd651  jz      short loc_1800CD65D
0x1800cd653  mov     rcx, rbx; hObject
0x1800cd656  call    cs:__imp_CloseHandle
0x1800cd65c  nop
0x1800cd65d  mov     rcx, rsi; SRWLock
0x1800cd660  call    cs:__imp_AcquireSRWLockExclusive
0x1800cd666  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x1800cd66a  jnz     short loc_1800CD67C
0x1800cd66c  lea     rcx, [rsi+8]; Address
0x1800cd670  mov     dword ptr [rcx], 1
0x1800cd676  call    cs:__imp_WakeByAddressAll
0x1800cd67c  mov     rcx, rsi; SRWLock
0x1800cd67f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd685  jmp     short loc_1800CD6A6
0x1800cd687  mov     rcx, [rbp+38h]; this
0x1800cd68b  mov     r14d, 80070490h
0x1800cd691  mov     r9d, r14d; char *
0x1800cd694  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cd69b  mov     edx, 31Fh; void *
0x1800cd6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd6a5  nop
0x1800cd6a6  test    r12b, r12b
0x1800cd6a9  jz      short loc_1800CD6C2
0x1800cd6ab  sub     dword ptr [rdi+4Ch], 1
0x1800cd6af  jnz     short loc_1800CD6C2
0x1800cd6b1  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cd6b8  lea     rcx, [rdi+10h]; SRWLock
0x1800cd6bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd6c2  mov     eax, r14d
0x1800cd6c5  mov     rcx, [rbp+var_8]
0x1800cd6c9  xor     rcx, rsp; StackCookie
0x1800cd6cc  call    __security_check_cookie
0x1800cd6d1  mov     rbx, [rsp+80h+arg_10]
0x1800cd6d9  add     rsp, 80h
0x1800cd6e0  pop     r15
0x1800cd6e2  pop     r14
0x1800cd6e4  pop     r13
0x1800cd6e6  pop     r12
0x1800cd6e8  pop     rdi
0x1800cd6e9  pop     rsi
0x1800cd6ea  pop     rbp
0x1800cd6eb  retn
0x1800cd6ec  mov     ecx, 1
0x1800cd6f1  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800cd6f7  mov     ecx, 5; int
0x1800cd6fc  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cd702  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800cd709  mov     ecx, 6; int
0x1800cd70e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cd714  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
