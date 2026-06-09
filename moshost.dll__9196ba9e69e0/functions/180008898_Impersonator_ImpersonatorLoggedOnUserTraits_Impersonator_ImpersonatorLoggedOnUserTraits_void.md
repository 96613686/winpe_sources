# Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(void)

- ea: `0x180008898`
- end: `0x180008930`
- name: `??1?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008ac0`

## callees

- `0x180001d00`
- `0x180002722`
- `0x180008898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088c9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800088bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800088bf`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180008903`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180008903`

## pseudocode

```c
void __fastcall Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(int *a1)
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
0x180008898  mov     [rsp+arg_8], rbx
0x18000889d  push    rdi
0x18000889e  sub     rsp, 0D0h
0x1800088a5  mov     rax, cs:__security_cookie
0x1800088ac  xor     rax, rsp
0x1800088af  mov     [rsp+0D8h+var_18], rax
0x1800088b7  cmp     dword ptr [rcx], 0
0x1800088ba  mov     rdi, rcx
0x1800088bd  jl      short loc_180008909
0x1800088bf  call    cs:__imp_RevertToSelf
0x1800088c5  test    eax, eax
0x1800088c7  jnz     short loc_180008909
0x1800088c9  call    cs:__imp_GetLastError
0x1800088cf  mov     ebx, eax
0x1800088d1  test    eax, eax
0x1800088d3  jle     short loc_1800088DE
0x1800088d5  movzx   ebx, ax
0x1800088d8  or      ebx, 80070000h
0x1800088de  test    ebx, ebx
0x1800088e0  jns     short loc_180008909
0x1800088e2  xor     edx, edx; Val
0x1800088e4  lea     rcx, [rsp+0D8h+pExceptionRecord.ExceptionFlags]; void *
0x1800088e9  mov     r8d, 94h; Size
0x1800088ef  call    memset_0
0x1800088f4  xor     edx, edx; pContextRecord
0x1800088f6  mov     [rsp+0D8h+pExceptionRecord.ExceptionCode], ebx
0x1800088fa  lea     rcx, [rsp+0D8h+pExceptionRecord]; pExceptionRecord
0x1800088ff  lea     r8d, [rdx+1]; dwFlags
0x180008903  call    cs:__imp_RaiseFailFastException
0x180008909  mov     dword ptr [rdi], 80070015h
0x18000890f  mov     rcx, [rsp+0D8h+var_18]
0x180008917  xor     rcx, rsp; StackCookie
0x18000891a  call    __security_check_cookie
0x18000891f  mov     rbx, [rsp+0D8h+arg_8]
0x180008927  add     rsp, 0D0h
0x18000892e  pop     rdi
0x18000892f  retn
```
