# _invalid_parameter_internal

- ea: `0x180014e3c`
- end: `0x180014f2c`
- name: `_invalid_parameter_internal`
- size: `240`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, DWORD dwErrCode)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014d98`
- `0x18001bf78`
- `0x18001bff8`
- `0x18001cb24`
- `0x18001cc4c`
- `0x18001d158`

## callees

- `0x180014bc8`
- `0x180014e3c`
- `0x180014f5c`
- `0x1800154e4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ea2`

## pseudocode

```c
__int64 __fastcall invalid_parameter_internal(
        wchar_t *Expression,
        wchar_t *FunctionName,
        wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved,
        __int64 *dwErrCode)
{
  __int64 v6; // rbx
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  DWORD v14; // ecx
  __int64 (__fastcall *v15)(wchar_t *, wchar_t *, wchar_t *, __int64, uintptr_t); // rax
  __int64 v16; // r9
  wchar_t *v17; // r8
  wchar_t *v18; // rdx
  _QWORD *v20; // rax

  v6 = (__int64)dwErrCode;
  v11 = *dwErrCode;
  if ( !*dwErrCode )
  {
    LODWORD(dwErrCode) = GetLastError();
    if ( *(_BYTE *)(v6 + 16) )
    {
      v12 = *(_QWORD *)(v6 + 8);
    }
    else
    {
      *(_QWORD *)(v6 + 8) = 0;
      v12 = 0;
      *(_BYTE *)(v6 + 16) = 1;
    }
    v13 = _acrt_getptd_noexit_explicit(&dwErrCode, v12);
    v14 = (unsigned int)dwErrCode;
    v11 = v13;
    *(_QWORD *)v6 = v13;
    SetLastError(v14);
    if ( !v11 )
      goto LABEL_9;
  }
  v15 = *(__int64 (__fastcall **)(wchar_t *, wchar_t *, wchar_t *, __int64, uintptr_t))(v11 + 952);
  if ( v15 )
  {
    v16 = LineNo;
    v17 = FileName;
    v18 = FunctionName;
  }
  else
  {
LABEL_9:
    v20 = (_QWORD *)__crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
                      (__int64)&qword_18003DEC0,
                      v6);
    v16 = LineNo;
    v17 = FileName;
    v18 = FunctionName;
    v15 = (__int64 (__fastcall *)(wchar_t *, wchar_t *, wchar_t *, __int64, uintptr_t))__ROR8__(
                                                                                         _security_cookie ^ *v20,
                                                                                         _security_cookie & 0x3F);
    if ( !v15 )
      invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  }
  return v15(Expression, v18, v17, v16, Reserved);
}

```

## disassembly

```asm
0x180014e3c  push    rbx
0x180014e3e  push    rbp
0x180014e3f  push    rsi
0x180014e40  push    rdi
0x180014e41  push    r14
0x180014e43  push    r15
0x180014e45  sub     rsp, 38h
0x180014e49  mov     rbx, [rsp+68h+dwErrCode]
0x180014e51  mov     esi, r9d
0x180014e54  mov     rbp, r8
0x180014e57  mov     r14, rdx
0x180014e5a  mov     r15, rcx
0x180014e5d  mov     rdi, [rbx]
0x180014e60  test    rdi, rdi
0x180014e63  jnz     short loc_180014EAD
0x180014e65  call    cs:__imp_GetLastError
0x180014e6b  mov     dword ptr [rsp+68h+dwErrCode], eax
0x180014e72  cmp     [rbx+10h], dil
0x180014e76  jnz     short loc_180014E84
0x180014e78  mov     [rbx+8], rdi
0x180014e7c  xor     edx, edx
0x180014e7e  mov     byte ptr [rbx+10h], 1
0x180014e82  jmp     short loc_180014E88
0x180014e84  mov     rdx, [rbx+8]
0x180014e88  lea     rcx, [rsp+68h+dwErrCode]
0x180014e90  call    __acrt_getptd_noexit_explicit
0x180014e95  mov     ecx, dword ptr [rsp+68h+dwErrCode]; dwErrCode
0x180014e9c  mov     rdi, rax
0x180014e9f  mov     [rbx], rax
0x180014ea2  call    cs:__imp_SetLastError
0x180014ea8  test    rdi, rdi
0x180014eab  jz      short loc_180014EE4
0x180014ead  mov     rax, [rdi+3B8h]
0x180014eb4  test    rax, rax
0x180014eb7  jz      short loc_180014EE4
0x180014eb9  mov     r9d, esi
0x180014ebc  mov     r8, rbp
0x180014ebf  mov     rdx, r14
0x180014ec2  mov     rcx, [rsp+68h+arg_20]
0x180014eca  mov     [rsp+68h+Reserved], rcx
0x180014ecf  mov     rcx, r15
0x180014ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ed7  add     rsp, 38h
0x180014edb  pop     r15
0x180014edd  pop     r14
0x180014edf  pop     rdi
0x180014ee0  pop     rsi
0x180014ee1  pop     rbp
0x180014ee2  pop     rbx
0x180014ee3  retn
0x180014ee4  mov     rdx, rbx
0x180014ee7  lea     rcx, qword_18003DEC0
0x180014eee  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x180014ef3  mov     rdx, cs:__security_cookie
0x180014efa  mov     r9d, esi; LineNo
0x180014efd  mov     ecx, edx
0x180014eff  mov     r8, rbp; FileName
0x180014f02  and     ecx, 3Fh
0x180014f05  mov     rax, [rax]
0x180014f08  xor     rax, rdx
0x180014f0b  mov     rdx, r14; FunctionName
0x180014f0e  ror     rax, cl
0x180014f11  test    rax, rax
0x180014f14  jnz     short loc_180014EC2
0x180014f16  mov     rax, [rsp+68h+arg_20]
0x180014f1e  mov     rcx, r15; Expression
0x180014f21  mov     [rsp+68h+Reserved], rax; Reserved
0x180014f26  call    _invoke_watson
```
