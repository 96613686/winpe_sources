# _lambda_650b069bedae799f787ef4ee3bedeed8_::operator()

- ea: `0x18000e5f0`
- end: `0x18000e6a8`
- name: `_lambda_650b069bedae799f787ef4ee3bedeed8_::operator()`
- size: `184`
- prototype: `int __fastcall(HANDLE **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001409c`

## callees

- `0x18000dc40`
- `0x18000e5f0`
- `0x1800169b2`
- `0x180016a72`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000e60f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000e60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e61d`

## pseudocode

```c
int __fastcall lambda_650b069bedae799f787ef4ee3bedeed8_::operator()(HANDLE **a1)
{
  HANDLE *v1; // rax
  DWORD LastError; // eax
  __int64 v3; // rdx
  int v4; // ebx
  __int64 v6; // [rsp+20h] [rbp-30h] BYREF
  char v7; // [rsp+28h] [rbp-28h]
  int v8; // [rsp+29h] [rbp-27h]
  __int16 v9; // [rsp+2Dh] [rbp-23h]
  char v10; // [rsp+2Fh] [rbp-21h]
  void **pExceptionObject; // [rsp+30h] [rbp-20h] BYREF
  __int128 v12; // [rsp+38h] [rbp-18h]
  int v13; // [rsp+48h] [rbp-8h]
  DWORD v14; // [rsp+60h] [rbp+10h] BYREF
  int v15; // [rsp+68h] [rbp+18h] BYREF
  int v16; // [rsp+6Ch] [rbp+1Ch]

  v1 = *a1;
  if ( **a1 != (HANDLE)-1LL )
  {
    LODWORD(v1) = SetThreadToken(0, *v1);
    if ( !(_DWORD)v1 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      v14 = LastError;
      errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v15, v3, &v14);
      v4 = v15;
      pExceptionObject = &std::exception::`vftable';
      v12 = 0;
      v6 = 0;
      v7 = 1;
      v8 = 0;
      v9 = 0;
      v10 = 0;
      o___std_exception_copy_0(&v6);
      pExceptionObject = &errorlib::specific_error_exception<winerror_error::tag>::`vftable';
      v13 = v4;
      v16 = 6;
      throw (errorlib::specific_error_exception<winerror_error::tag> *)&pExceptionObject;
    }
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000e5f0  mov     [rsp-8+arg_10], rbx
0x18000e5f5  push    rbp
0x18000e5f6  mov     rbp, rsp
0x18000e5f9  sub     rsp, 50h
0x18000e5fd  mov     rax, [rcx]
0x18000e600  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18000e604  jz      loc_18000E69D
0x18000e60a  mov     rdx, [rax]; Token
0x18000e60d  xor     ecx, ecx; Thread
0x18000e60f  call    cs:__imp_SetThreadToken
0x18000e615  test    eax, eax
0x18000e617  jnz     loc_18000E69D
0x18000e61d  call    cs:__imp_GetLastError
0x18000e623  mov     ecx, 507h
0x18000e628  test    eax, eax
0x18000e62a  cmovz   eax, ecx
0x18000e62d  mov     [rbp+arg_0], eax
0x18000e630  lea     r8, [rbp+arg_0]
0x18000e634  lea     rcx, [rbp+arg_8]
0x18000e638  call    ??$?0K@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@W4type@ErrorSource@1@$$QEAK@Z; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(errorlib::ErrorSource::type,ulong &&)
0x18000e63d  mov     ebx, [rbp+arg_8]
0x18000e640  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000e647  mov     [rbp+pExceptionObject], rax
0x18000e64b  xorps   xmm0, xmm0
0x18000e64e  movups  [rbp+var_18], xmm0
0x18000e652  mov     [rbp+var_30], 0
0x18000e65a  mov     [rbp+var_28], 1
0x18000e65e  xor     eax, eax
0x18000e660  mov     [rbp+var_27], eax
0x18000e663  mov     [rbp+var_23], ax
0x18000e667  mov     [rbp+var_21], al
0x18000e66a  lea     rdx, [rbp+var_18]
0x18000e66e  lea     rcx, [rbp+var_30]
0x18000e672  call    _o___std_exception_copy_0
0x18000e677  lea     rax, ??_7?$specific_error_exception@Utag@winerror_error@@@errorlib@@6B@; const errorlib::specific_error_exception<winerror_error::tag>::`vftable'
0x18000e67e  mov     [rbp+pExceptionObject], rax
0x18000e682  mov     [rbp+var_8], ebx
0x18000e685  mov     [rbp+arg_C], 6
0x18000e68c  lea     rdx, _TI4?AV?$specific_error_exception@Utag@winerror_error@@@errorlib@@; pThrowInfo
0x18000e693  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e697  call    _CxxThrowException_0
0x18000e69d  mov     rbx, [rsp+50h+arg_10]
0x18000e6a2  add     rsp, 50h
0x18000e6a6  pop     rbp
0x18000e6a7  retn
```
