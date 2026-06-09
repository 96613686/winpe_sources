# CHttpAgent::_OnSendRequestComplete(void *)

- ea: `0x1800cdcb4`
- end: `0x1800cdfe0`
- name: `?_OnSendRequestComplete@CHttpAgent@@AEAAXPEAX@Z`
- size: `812`
- prototype: `void __fastcall(CHttpAgent *__hidden this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800cd870`

## callees

- `0x180009ab4`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800a1f08`
- `0x1800cdcb4`
- `0x1800ce610`
- `0x1800cea1c`
- `0x1800cec6c`
- `0x1800cf144`
- `0x1800d0318`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cded7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cdf16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cded7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cdf16`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cdebd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cdf00`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cdebd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cdf00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cde8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cde8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdef2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cdf1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cdf1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cdd95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cddd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cdded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cde37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cdd95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cddd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cdded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cde37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdd76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cddb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdf8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdd76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cddb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdf8d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cddc7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cddc7`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cde80`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cde80`

## string_xrefs

- `0x1800cdf4b`: `CHttpAgent::_OnSendRequestComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CHttpAgent::_OnSendRequestComplete(RTL_SRWLOCK *this, void *a2)
{
  RTL_SRWLOCK *v3; // rdi
  char v4; // r13
  _QWORD *Ptr; // rdx
  _QWORD *v6; // rax
  _BYTE *v7; // rcx
  volatile __int32 *v8; // rbx
  __int64 v9; // rax
  bool v10; // zf
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // rbx
  int v13; // eax
  signed int LastError; // eax
  unsigned int v15; // r15d
  HINTERNET hRequest; // [rsp+68h] [rbp-18h] BYREF

  hRequest = a2;
  v3 = this + 35;
  if ( (unsigned int)mtx_do_lock(&this[35]) )
    std::_Throw_Cpp_error(5);
  if ( HIDWORD(v3[9].Ptr) == 0x7FFFFFFF )
  {
    HIDWORD(v3[9].Ptr) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v4 = 1;
  if ( !BYTE3(this[48].Ptr) )
  {
    Ptr = this[3].Ptr;
    v6 = (_QWORD *)Ptr[1];
    v7 = Ptr;
    while ( !*((_BYTE *)v6 + 25) )
    {
      if ( v6[4] >= (unsigned __int64)hRequest )
        v7 = v6;
      else
        v6 += 2;
      v6 = (_QWORD *)*v6;
    }
    if ( !v7[25] && (unsigned __int64)hRequest >= *((_QWORD *)v7 + 4) && v7 != (_BYTE *)Ptr )
    {
      AcquireSRWLockExclusive(this + 33);
      ++HIDWORD(this[34].Ptr);
      v8 = (volatile __int32 *)&this[34];
      if ( HIDWORD(this[34].Ptr) == 1 )
        _InterlockedExchange(v8, 0);
      ReleaseSRWLockExclusive(this + 33);
      v9 = std::map<void *,CHttpAgent::RequestCtx>::operator[](&this[3], &hRequest);
      if ( *(_BYTE *)(v9 + 106) )
      {
        AcquireSRWLockExclusive(this + 33);
        v10 = HIDWORD(this[34].Ptr)-- == 1;
        if ( !v10 )
        {
LABEL_19:
          ReleaseSRWLockExclusive(this + 33);
          goto LABEL_20;
        }
        *v8 = 1;
        v11 = this + 34;
      }
      else
      {
        v12 = *(_QWORD *)v9;
        if ( !v3 )
          std::_Throw_system_error(1);
        v10 = HIDWORD(v3[9].Ptr)-- == 1;
        if ( v10 )
        {
          LODWORD(v3[9].Ptr) = -1;
          ReleaseSRWLockExclusive(v3 + 2);
        }
        v4 = 0;
        v13 = (*(__int64 (__fastcall **)(PVOID, HINTERNET, __int64))(*(_QWORD *)this[31].Ptr + 24LL))(
                this[31].Ptr,
                hRequest,
                v12);
        if ( v13 )
        {
          if ( v13 == 1 )
            CHttpAgent::_DoneWithRequest((CHttpAgent *)this, hRequest);
          else
            CHttpAgent::_OnComplete((CHttpAgent *)this, hRequest, v13);
        }
        else
        {
          CHttpAgent::_ImpersonateUserToken((__int64)this);
          if ( !WinHttpReceiveResponse(hRequest, 0) )
          {
            LastError = GetLastError();
            if ( LastError )
            {
              v15 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v15 = LastError;
            }
            else
            {
              v15 = -2147467259;
            }
            LogResult(
              2u,
              "CHttpAgent::_OnSendRequestComplete",
              0x3DFu,
              v15,
              "Failed to initiate wait for receiving response for request = 0x%p",
              hRequest);
            CHttpAgent::_OnError((CHttpAgent *)this, hRequest, v15);
          }
        }
        AcquireSRWLockExclusive(this + 33);
        v10 = HIDWORD(this[34].Ptr)-- == 1;
        if ( !v10 )
          goto LABEL_19;
        v11 = this + 34;
        LODWORD(this[34].Ptr) = 1;
      }
      WakeByAddressAll(v11);
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v4 )
  {
    v10 = HIDWORD(v3[9].Ptr)-- == 1;
    if ( v10 )
    {
      LODWORD(v3[9].Ptr) = -1;
      ReleaseSRWLockExclusive(v3 + 2);
    }
  }
}

```

## disassembly

```asm
0x1800cdcb4  mov     [rsp-38h+arg_10], rbx
0x1800cdcb9  push    rbp
0x1800cdcba  push    rsi
0x1800cdcbb  push    rdi
0x1800cdcbc  push    r12
0x1800cdcbe  push    r13
0x1800cdcc0  push    r14
0x1800cdcc2  push    r15
0x1800cdcc4  mov     rbp, rsp
0x1800cdcc7  sub     rsp, 80h
0x1800cdcce  mov     rax, cs:__security_cookie
0x1800cdcd5  xor     rax, rsp
0x1800cdcd8  mov     [rbp+var_10], rax
0x1800cdcdc  mov     r14, rcx
0x1800cdcdf  mov     [rbp+hRequest], rdx
0x1800cdce3  xorps   xmm0, xmm0
0x1800cdce6  movups  [rbp+var_48], xmm0
0x1800cdcea  lea     rdi, [rcx+118h]
0x1800cdcf1  mov     qword ptr [rbp+var_48], rdi
0x1800cdcf5  xor     r12d, r12d
0x1800cdcf8  mov     byte ptr [rbp+var_48+8], r12b
0x1800cdcfc  mov     rcx, rdi
0x1800cdcff  call    mtx_do_lock
0x1800cdd04  test    eax, eax
0x1800cdd06  jnz     loc_1800CDFBD
0x1800cdd0c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800cdd13  jz      loc_1800CDFC8
0x1800cdd19  mov     r13b, 1
0x1800cdd1c  mov     byte ptr [rbp+var_48+8], r13b
0x1800cdd20  cmp     [r14+183h], r12b
0x1800cdd27  jnz     loc_1800CDDD7
0x1800cdd2d  mov     rdx, [r14+18h]
0x1800cdd31  mov     rax, [rdx+8]
0x1800cdd35  xor     ecx, ecx
0x1800cdd37  mov     [rbp+var_24], ecx
0x1800cdd3a  mov     rcx, rdx
0x1800cdd3d  mov     r8, [rbp+hRequest]
0x1800cdd41  jmp     short loc_1800CDD55
0x1800cdd43  cmp     [rax+20h], r8
0x1800cdd47  jnb     short loc_1800CDD4F
0x1800cdd49  add     rax, 10h
0x1800cdd4d  jmp     short loc_1800CDD52
0x1800cdd4f  mov     rcx, rax
0x1800cdd52  mov     rax, [rax]
0x1800cdd55  cmp     [rax+19h], r12b
0x1800cdd59  jz      short loc_1800CDD43
0x1800cdd5b  cmp     [rcx+19h], r12b
0x1800cdd5f  jnz     short loc_1800CDDD7
0x1800cdd61  cmp     r8, [rcx+20h]
0x1800cdd65  jb      short loc_1800CDDD7
0x1800cdd67  cmp     rcx, rdx
0x1800cdd6a  jz      short loc_1800CDDD7
0x1800cdd6c  lea     rsi, [r14+108h]
0x1800cdd73  mov     rcx, rsi; SRWLock
0x1800cdd76  call    cs:__imp_AcquireSRWLockExclusive
0x1800cdd7c  inc     dword ptr [rsi+0Ch]
0x1800cdd7f  lea     rbx, [rsi+8]
0x1800cdd83  cmp     dword ptr [rsi+0Ch], 1
0x1800cdd87  jnz     short loc_1800CDD8E
0x1800cdd89  mov     eax, r12d
0x1800cdd8c  xchg    eax, [rbx]
0x1800cdd8e  mov     [rbp+var_38], rsi
0x1800cdd92  mov     rcx, rsi; SRWLock
0x1800cdd95  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cdd9b  nop
0x1800cdd9c  lea     rdx, [rbp+hRequest]
0x1800cdda0  lea     rcx, [r14+18h]
0x1800cdda4  call    ??A?$map@PEAXURequestCtx@CHttpAgent@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXURequestCtx@CHttpAgent@@@std@@@4@@std@@QEAAAEAURequestCtx@CHttpAgent@@AEBQEAX@Z; std::map<void *,CHttpAgent::RequestCtx>::operator[](void * const &)
0x1800cdda9  cmp     [rax+6Ah], r12b
0x1800cddad  jz      short loc_1800CDE1A
0x1800cddaf  mov     rcx, rsi; SRWLock
0x1800cddb2  call    cs:__imp_AcquireSRWLockExclusive
0x1800cddb8  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x1800cddbc  jnz     short loc_1800CDDCD
0x1800cddbe  mov     dword ptr [rbx], 1
0x1800cddc4  mov     rcx, rbx; Address
0x1800cddc7  call    cs:__imp_WakeByAddressAll
0x1800cddcd  mov     rcx, rsi; SRWLock
0x1800cddd0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cddd6  nop
0x1800cddd7  test    r13b, r13b
0x1800cddda  jz      short loc_1800CDDF3
0x1800cdddc  sub     dword ptr [rdi+4Ch], 1
0x1800cdde0  jnz     short loc_1800CDDF3
0x1800cdde2  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cdde9  lea     rcx, [rdi+10h]; SRWLock
0x1800cdded  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cddf3  mov     rcx, [rbp+var_10]
0x1800cddf7  xor     rcx, rsp; StackCookie
0x1800cddfa  call    __security_check_cookie
0x1800cddff  mov     rbx, [rsp+80h+arg_10]
0x1800cde07  add     rsp, 80h
0x1800cde0e  pop     r15
0x1800cde10  pop     r14
0x1800cde12  pop     r13
0x1800cde14  pop     r12
0x1800cde16  pop     rdi
0x1800cde17  pop     rsi
0x1800cde18  pop     rbp
0x1800cde19  retn
0x1800cde1a  mov     rbx, [rax]
0x1800cde1d  test    rdi, rdi
0x1800cde20  jz      loc_1800CDFB2
0x1800cde26  sub     dword ptr [rdi+4Ch], 1
0x1800cde2a  jnz     short loc_1800CDE3D
0x1800cde2c  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cde33  lea     rcx, [rdi+10h]; SRWLock
0x1800cde37  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cde3d  mov     r13b, r12b
0x1800cde40  mov     byte ptr [rbp+var_48+8], r12b
0x1800cde44  mov     rcx, [r14+0F8h]
0x1800cde4b  mov     rax, [rcx]
0x1800cde4e  mov     r8, rbx
0x1800cde51  mov     rdx, [rbp+hRequest]
0x1800cde55  mov     rax, [rax+18h]
0x1800cde59  call    _guard_dispatch_icall
0x1800cde5e  test    eax, eax
0x1800cde60  jnz     loc_1800CDF6E
0x1800cde66  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800cde6e  lea     rdx, [rbp+Token]
0x1800cde72  mov     rcx, r14
0x1800cde75  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cde7a  xor     edx, edx; lpReserved
0x1800cde7c  mov     rcx, [rbp+hRequest]; hRequest
0x1800cde80  call    cs:__imp_WinHttpReceiveResponse
0x1800cde86  test    eax, eax
0x1800cde88  jnz     short loc_1800CDEAA
0x1800cde8a  call    cs:__imp_GetLastError
0x1800cde90  test    eax, eax
0x1800cde92  jz      short loc_1800CDEE2
0x1800cde94  movzx   r15d, ax
0x1800cde98  or      r15d, 80070000h
0x1800cde9f  test    eax, eax
0x1800cdea1  cmovle  r15d, eax
0x1800cdea5  test    r15d, r15d
0x1800cdea8  js      short loc_1800CDEE8
0x1800cdeaa  mov     rbx, [rbp+Token]
0x1800cdeae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cdeb2  jz      loc_1800CDF8A
0x1800cdeb8  mov     rdx, rbx; Token
0x1800cdebb  xor     ecx, ecx; Thread
0x1800cdebd  call    cs:__imp_SetThreadToken
0x1800cdec3  test    eax, eax
0x1800cdec5  jz      loc_1800CDFDA
0x1800cdecb  test    rbx, rbx
0x1800cdece  jz      loc_1800CDF8A
0x1800cded4  mov     rcx, rbx; hObject
0x1800cded7  call    cs:__imp_CloseHandle
0x1800cdedd  jmp     loc_1800CDF8A
0x1800cdee2  mov     r15d, 80004005h
0x1800cdee8  mov     rbx, [rbp+Token]
0x1800cdeec  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cdef0  jz      short loc_1800CDF25
0x1800cdef2  call    cs:__imp_GetLastError
0x1800cdef8  mov     r12d, eax
0x1800cdefb  mov     rdx, rbx; Token
0x1800cdefe  xor     ecx, ecx; Thread
0x1800cdf00  call    cs:__imp_SetThreadToken
0x1800cdf06  test    eax, eax
0x1800cdf08  jz      loc_1800CDFAC
0x1800cdf0e  test    rbx, rbx
0x1800cdf11  jz      short loc_1800CDF1C
0x1800cdf13  mov     rcx, rbx; hObject
0x1800cdf16  call    cs:__imp_CloseHandle
0x1800cdf1c  mov     ecx, r12d; dwErrCode
0x1800cdf1f  call    cs:__imp_SetLastError
0x1800cdf25  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cdf29  mov     [rbp+Token], rbx
0x1800cdf2d  mov     rax, [rbp+hRequest]
0x1800cdf31  mov     [rsp+80h+var_58], rax
0x1800cdf36  lea     rax, aFailedToInitia; "Failed to initiate wait for receiving r"...
0x1800cdf3d  mov     [rsp+80h+var_60], rax; char *
0x1800cdf42  mov     r9d, r15d; int
0x1800cdf45  mov     r8d, 3DFh; unsigned int
0x1800cdf4b  lea     rdx, aChttpagentOnse; "CHttpAgent::_OnSendRequestComplete"
0x1800cdf52  lea     ecx, [rbx+3]; unsigned __int8
0x1800cdf55  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800cdf5a  mov     r8d, r15d; int
0x1800cdf5d  mov     rdx, [rbp+hRequest]; void *
0x1800cdf61  mov     rcx, r14; this
0x1800cdf64  call    ?_OnError@CHttpAgent@@AEAAXPEAXJ@Z; CHttpAgent::_OnError(void *,long)
0x1800cdf69  jmp     loc_1800CDEAE
0x1800cdf6e  mov     rdx, [rbp+hRequest]; void *
0x1800cdf72  mov     rcx, r14; this
0x1800cdf75  cmp     eax, 1
0x1800cdf78  jnz     short loc_1800CDF81
0x1800cdf7a  call    ?_DoneWithRequest@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_DoneWithRequest(void *)
0x1800cdf7f  jmp     short loc_1800CDF8A
0x1800cdf81  mov     r8d, eax; int
0x1800cdf84  call    ?_OnComplete@CHttpAgent@@AEAAXPEAXJ@Z; CHttpAgent::_OnComplete(void *,long)
0x1800cdf89  nop
0x1800cdf8a  mov     rcx, rsi; SRWLock
0x1800cdf8d  call    cs:__imp_AcquireSRWLockExclusive
0x1800cdf93  add     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x1800cdf97  jnz     loc_1800CDDCD
0x1800cdf9d  lea     rcx, [rsi+8]
0x1800cdfa1  mov     dword ptr [rcx], 1
0x1800cdfa7  jmp     loc_1800CDDC7
0x1800cdfac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800cdfb2  mov     ecx, 1
0x1800cdfb7  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800cdfbd  mov     ecx, 5; int
0x1800cdfc2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cdfc8  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800cdfcf  mov     ecx, 6; int
0x1800cdfd4  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cdfda  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
