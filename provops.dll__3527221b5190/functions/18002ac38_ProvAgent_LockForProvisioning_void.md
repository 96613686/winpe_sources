# ProvAgent::LockForProvisioning(void)

- ea: `0x18002ac38`
- end: `0x18002ad5b`
- name: `?LockForProvisioning@ProvAgent@@QEAAXXZ`
- size: `291`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000f8d0`
- `0x180010b40`
- `0x180016840`
- `0x180017020`

## callees

- `0x180001678`
- `0x180005bb8`
- `0x18000864c`
- `0x18002ac38`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ac9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ad01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ac9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ad01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ac5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ac5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aca8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aca8`

## string_xrefs

- `0x18002ad15`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002ad49`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002ad2f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProvAgent::LockForProvisioning(HANDLE *this)
{
  HANDLE v1; // rbx
  DWORD v3; // eax
  const char *v4; // r9
  char *v5; // rdi
  void *v6; // rsi
  DWORD LastError; // ebp
  const char *v8; // r9
  const char *v9; // r9
  char v10; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = *this;
  v3 = WaitForSingleObjectEx(*this, 0xFFFFFFFF, 0);
  if ( v3 == 258 )
  {
    v1 = 0;
  }
  else if ( (v3 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v4);
  }
  v5 = (char *)(this + 2);
  if ( v5 == &v10 )
  {
    if ( v1 && !ReleaseMutex(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
  }
  else
  {
    v6 = *(void **)v5;
    if ( *(_QWORD *)v5 )
    {
      LastError = GetLastError();
      if ( !ReleaseMutex(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v8);
      SetLastError(LastError);
    }
    *(_QWORD *)v5 = v1;
  }
  if ( *(_DWORD *)g_hProvTraceProvider > 4u )
    tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, byte_1800414FB, 0, 0);
}

```

## disassembly

```asm
0x18002ac38  push    rbx
0x18002ac3a  push    rbp
0x18002ac3b  push    rsi
0x18002ac3c  push    rdi
0x18002ac3d  sub     rsp, 68h
0x18002ac41  mov     rax, cs:__security_cookie
0x18002ac48  xor     rax, rsp
0x18002ac4b  mov     [rsp+88h+var_30], rax
0x18002ac50  mov     rbx, [rcx]
0x18002ac53  mov     rdi, rcx
0x18002ac56  mov     rcx, rbx; hHandle
0x18002ac59  xor     r8d, r8d; bAlertable
0x18002ac5c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ac5f  call    cs:__imp_WaitForSingleObjectEx
0x18002ac65  cmp     eax, 102h
0x18002ac6a  jz      short loc_18002AC79
0x18002ac6c  test    eax, 0FFFFFF7Fh
0x18002ac71  jnz     loc_18002AD27
0x18002ac77  jmp     short loc_18002AC7B
0x18002ac79  xor     ebx, ebx
0x18002ac7b  add     rdi, 10h
0x18002ac7f  lea     rax, [rsp+88h+var_58]
0x18002ac84  cmp     rdi, rax
0x18002ac87  jz      short loc_18002ACF9
0x18002ac89  mov     rsi, [rdi]
0x18002ac8c  test    rsi, rsi
0x18002ac8f  jz      short loc_18002ACAE
0x18002ac91  call    cs:__imp_GetLastError
0x18002ac97  mov     rcx, rsi; hMutex
0x18002ac9a  mov     ebp, eax
0x18002ac9c  call    cs:__imp_ReleaseMutex
0x18002aca2  test    eax, eax
0x18002aca4  jz      short loc_18002AD0D
0x18002aca6  mov     ecx, ebp; dwErrCode
0x18002aca8  call    cs:__imp_SetLastError
0x18002acae  mov     [rdi], rbx
0x18002acb1  mov     rcx, cs:g_hProvTraceProvider
0x18002acb8  mov     eax, [rcx]
0x18002acba  cmp     eax, 4
0x18002acbd  jbe     short loc_18002ACE3
0x18002acbf  lea     rax, [rsp+88h+var_50]
0x18002acc4  xor     r9d, r9d
0x18002acc7  mov     [rsp+88h+var_60], rax
0x18002accc  lea     rdx, byte_1800414FB
0x18002acd3  xor     r8d, r8d
0x18002acd6  mov     [rsp+88h+var_68], 2
0x18002acde  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ace3  mov     rcx, [rsp+88h+var_30]
0x18002ace8  xor     rcx, rsp; StackCookie
0x18002aceb  call    __security_check_cookie
0x18002acf0  add     rsp, 68h
0x18002acf4  pop     rdi
0x18002acf5  pop     rsi
0x18002acf6  pop     rbp
0x18002acf7  pop     rbx
0x18002acf8  retn
0x18002acf9  test    rbx, rbx
0x18002acfc  jz      short loc_18002ACB1
0x18002acfe  mov     rcx, rbx; hMutex
0x18002ad01  call    cs:__imp_ReleaseMutex
0x18002ad07  test    eax, eax
0x18002ad09  jz      short loc_18002AD41
0x18002ad0b  jmp     short loc_18002ACB1
0x18002ad0d  mov     rcx, [rsp+88h]; this
0x18002ad15  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ad1c  mov     edx, 0A15h; void *
0x18002ad21  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ad27  mov     rcx, [rsp+88h]; this
0x18002ad2f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ad36  mov     edx, 0E01h; void *
0x18002ad3b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002ad41  mov     rcx, [rsp+88h]; this
0x18002ad49  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ad50  mov     edx, 0A15h; void *
0x18002ad55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
