# Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)

- ea: `0x18000eae0`
- end: `0x18000eb78`
- name: `?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b010`
- `0x18000ef18`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x18000eae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb11`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000eb07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000eb07`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000eb4b`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000eb4b`

## pseudocode

```c
void __fastcall Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(int *a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  EXCEPTION_RECORD pExceptionRecord; // [rsp+20h] [rbp-B8h] BYREF

  if ( *a1 >= 0 && !RevertToSelf() )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
    {
      memset_0(&pExceptionRecord.ExceptionFlags, 0, 0x94u);
      pExceptionRecord.ExceptionCode = v3;
      RaiseFailFastException(&pExceptionRecord, 0, 1u);
    }
  }
  *a1 = -2147024875;
}

```

## disassembly

```asm
0x18000eae0  mov     [rsp+arg_8], rbx
0x18000eae5  push    rdi
0x18000eae6  sub     rsp, 0D0h
0x18000eaed  mov     rax, cs:__security_cookie
0x18000eaf4  xor     rax, rsp
0x18000eaf7  mov     [rsp+0D8h+var_18], rax
0x18000eaff  cmp     dword ptr [rcx], 0
0x18000eb02  mov     rdi, rcx
0x18000eb05  jl      short loc_18000EB51
0x18000eb07  call    cs:__imp_RevertToSelf
0x18000eb0d  test    eax, eax
0x18000eb0f  jnz     short loc_18000EB51
0x18000eb11  call    cs:__imp_GetLastError
0x18000eb17  mov     ebx, eax
0x18000eb19  test    eax, eax
0x18000eb1b  jle     short loc_18000EB26
0x18000eb1d  movzx   ebx, ax
0x18000eb20  or      ebx, 80070000h
0x18000eb26  test    ebx, ebx
0x18000eb28  jns     short loc_18000EB51
0x18000eb2a  xor     edx, edx; Val
0x18000eb2c  lea     rcx, [rsp+0D8h+pExceptionRecord.ExceptionFlags]; void *
0x18000eb31  mov     r8d, 94h; Size
0x18000eb37  call    memset_0
0x18000eb3c  xor     edx, edx; pContextRecord
0x18000eb3e  mov     [rsp+0D8h+pExceptionRecord.ExceptionCode], ebx
0x18000eb42  lea     rcx, [rsp+0D8h+pExceptionRecord]; pExceptionRecord
0x18000eb47  lea     r8d, [rdx+1]; dwFlags
0x18000eb4b  call    cs:__imp_RaiseFailFastException
0x18000eb51  mov     dword ptr [rdi], 80070015h
0x18000eb57  mov     rcx, [rsp+0D8h+var_18]
0x18000eb5f  xor     rcx, rsp; StackCookie
0x18000eb62  call    __security_check_cookie
0x18000eb67  mov     rbx, [rsp+0D8h+arg_8]
0x18000eb6f  add     rsp, 0D0h
0x18000eb76  pop     rdi
0x18000eb77  retn
```
