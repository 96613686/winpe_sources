# WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180021be0`
- end: `0x180021df9`
- name: `?WorkCallback@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180007900`
- `0x18000e190`
- `0x180021be0`
- `0x180021e00`
- `0x1800221a0`
- `0x180022b54`
- `0x180023044`
- `0x1800a88a0`
- `0x1800a9738`
- `0x180149010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180021df2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180021df2`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180021d67`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180021d86`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180021d67`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180021d86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021d43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  struct _RTL_CRITICAL_SECTION *i; // rbx
  __int64 (__fastcall ***v4)(_QWORD, _BYTE *); // rcx
  __int64 v5; // rax
  _BYTE *v6; // rdx
  __int64 result; // rax
  __int64 *v8; // rcx
  void ***v9; // rcx
  std::_Ref_count_base *v10; // rbx
  _BYTE v11[64]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v12; // [rsp+60h] [rbp-39h] BYREF
  volatile signed __int32 *v13; // [rsp+68h] [rbp-31h]
  __int64 *v14; // [rsp+88h] [rbp-11h]
  __int64 (__fastcall **v15)(__int64 *); // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]
  _BYTE v17[56]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE *v18; // [rsp+D8h] [rbp+3Fh]

  memset_0(&v12, 0, 0x40u);
  EnterCriticalSection(a2);
  for ( i = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 152); ; i = (struct _RTL_CRITICAL_SECTION *)((char *)i + 64) )
  {
    if ( i == (struct _RTL_CRITICAL_SECTION *)&a2[5].OwningThread )
    {
      if ( a2 )
        LeaveCriticalSection(a2);
      goto LABEL_13;
    }
    if ( i[1].OwningThread )
      break;
  }
  std::any::any(v11, &v12);
  std::any::operator=(&v12, i);
  std::any::operator=(i, v11);
  std::any::reset((std::any *)v11);
  if ( a2 )
    LeaveCriticalSection(a2);
  v9 = &void `RTTI Type Descriptor';
  if ( (v16 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    v9 = (void ***)(v16 & 0xFFFFFFFFFFFFFFFCuLL);
  if ( (unsigned int)__std_type_info_compare(v9 + 1, &qword_1801BF750) )
  {
    if ( (v16 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || !(unsigned __int8)type_info::operator==(
                             v16 & 0xFFFFFFFFFFFFFFFCuLL,
                             &std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor') )
    {
      std::_Throw_bad_any_cast();
    }
    if ( v13 )
      _InterlockedIncrement(v13 + 2);
    v10 = (std::_Ref_count_base *)v13;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  else
  {
    if ( (v16 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || (unsigned int)__std_type_info_compare((v16 & 0xFFFFFFFFFFFFFFFCuLL) + 8, &qword_1801BF750)
      || !v14 )
    {
      std::_Throw_bad_any_cast();
    }
    v18 = 0;
    v4 = (__int64 (__fastcall ***)(_QWORD, _BYTE *))v14[7];
    if ( !v4 || (v5 = (**v4)(v4, v17), (v18 = (_BYTE *)v5) == 0) )
    {
      std::_Xbad_function_call();
      JUMPOUT(0x180021DF8LL);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v18 )
    {
      v6 = v17;
      LOBYTE(v6) = v18 != v17;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v18 + 32LL))(v18, v6);
    }
  }
LABEL_13:
  result = (v16 & 3) - 1;
  if ( (v16 & 3) == 1 )
  {
    v8 = v14;
    return (*v15)(v8);
  }
  if ( (v16 & 3) == 2 )
  {
    v8 = &v12;
    return (*v15)(v8);
  }
  return result;
}

```

## disassembly

```asm
0x180021be0  mov     [rsp-8+arg_0], rbx
0x180021be5  mov     [rsp-8+arg_10], rdi
0x180021bea  push    rbp
0x180021beb  lea     rbp, [rsp-57h]
0x180021bf0  sub     rsp, 0F0h
0x180021bf7  mov     rax, cs:__security_cookie
0x180021bfe  xor     rax, rsp
0x180021c01  mov     [rbp+57h+var_10], rax
0x180021c05  mov     rdi, rdx
0x180021c08  xor     edx, edx; Val
0x180021c0a  lea     r8d, [rdx+40h]; Size
0x180021c0e  lea     rcx, [rbp+57h+var_90]; void *
0x180021c12  call    memset_0
0x180021c17  mov     rcx, rdi; lpCriticalSection
0x180021c1a  call    cs:__imp_EnterCriticalSection
0x180021c20  lea     rbx, [rdi+98h]
0x180021c27  lea     rax, [rbx+40h]
0x180021c2b  jmp     short loc_180021C3C
0x180021c2d  cmp     qword ptr [rbx+38h], 0
0x180021c32  jnz     loc_180021D0D
0x180021c38  add     rbx, 40h ; '@'
0x180021c3c  cmp     rbx, rax
0x180021c3f  jnz     short loc_180021C2D
0x180021c41  test    rdi, rdi
0x180021c44  jz      short loc_180021C50
0x180021c46  mov     rcx, rdi; lpCriticalSection
0x180021c49  call    cs:__imp_LeaveCriticalSection
0x180021c4f  nop
0x180021c50  jmp     short loc_180021CC2
0x180021c52  mov     rax, [rbp+57h+var_68]
0x180021c56  test    rax, rax
0x180021c59  jz      loc_180021D94
0x180021c5f  mov     [rbp+57h+var_18], 0
0x180021c67  mov     rcx, [rax+38h]
0x180021c6b  test    rcx, rcx
0x180021c6e  jz      loc_180021DF2
0x180021c74  mov     rax, [rcx]
0x180021c77  lea     rdx, [rbp+57h+var_50]
0x180021c7b  mov     rax, [rax]
0x180021c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c83  mov     rdx, rax
0x180021c86  mov     [rbp+57h+var_18], rax
0x180021c8a  test    rax, rax
0x180021c8d  jz      loc_180021DF2
0x180021c93  mov     rcx, [rax]
0x180021c96  mov     rax, [rcx+10h]
0x180021c9a  mov     rcx, rdx
0x180021c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ca2  mov     rcx, [rbp+57h+var_18]
0x180021ca6  test    rcx, rcx
0x180021ca9  jz      short loc_180021CC2
0x180021cab  mov     rax, [rcx]
0x180021cae  lea     rdx, [rbp+57h+var_50]
0x180021cb2  cmp     rcx, rdx
0x180021cb5  setnz   dl
0x180021cb8  mov     rax, [rax+20h]
0x180021cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cc1  nop
0x180021cc2  mov     rax, [rbp+57h+var_58]
0x180021cc6  and     eax, 3
0x180021cc9  sub     rax, 1
0x180021ccd  jnz     short loc_180021D01
0x180021ccf  mov     rcx, [rbp+57h+var_68]
0x180021cd3  mov     rax, [rbp+57h+var_60]
0x180021cd7  mov     rax, [rax]
0x180021cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cdf  nop
0x180021ce0  mov     rcx, [rbp+57h+var_10]
0x180021ce4  xor     rcx, rsp; StackCookie
0x180021ce7  call    __security_check_cookie
0x180021cec  lea     r11, [rsp+0F0h+var_s0]
0x180021cf4  mov     rbx, [r11+10h]
0x180021cf8  mov     rdi, [r11+20h]
0x180021cfc  mov     rsp, r11
0x180021cff  pop     rbp
0x180021d00  retn
0x180021d01  cmp     rax, 1
0x180021d05  jnz     short loc_180021CE0
0x180021d07  lea     rcx, [rbp+57h+var_90]
0x180021d0b  jmp     short loc_180021CD3
0x180021d0d  lea     rdx, [rbp+57h+var_90]
0x180021d11  lea     rcx, [rbp+57h+var_D0]
0x180021d15  call    ??0any@std@@QEAA@$$QEAV01@@Z; std::any::any(std::any &&)
0x180021d1a  mov     rdx, rbx
0x180021d1d  lea     rcx, [rbp+57h+var_90]
0x180021d21  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180021d26  lea     rdx, [rbp+57h+var_D0]
0x180021d2a  mov     rcx, rbx
0x180021d2d  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180021d32  lea     rcx, [rbp+57h+var_D0]; this
0x180021d36  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180021d3b  test    rdi, rdi
0x180021d3e  jz      short loc_180021D49
0x180021d40  mov     rcx, rdi; lpCriticalSection
0x180021d43  call    cs:__imp_LeaveCriticalSection
0x180021d49  mov     rax, [rbp+57h+var_58]
0x180021d4d  and     rax, 0FFFFFFFFFFFFFFFCh
0x180021d51  lea     rcx, ??_R0X@8; void `RTTI Type Descriptor'
0x180021d58  cmovnz  rcx, rax
0x180021d5c  add     rcx, 8
0x180021d60  lea     rdx, qword_1801BF750
0x180021d67  call    cs:__imp___std_type_info_compare
0x180021d6d  mov     rcx, [rbp+57h+var_58]
0x180021d71  test    eax, eax
0x180021d73  jnz     short loc_180021DD0
0x180021d75  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180021d79  jz      short loc_180021D94
0x180021d7b  add     rcx, 8
0x180021d7f  lea     rdx, qword_1801BF750
0x180021d86  call    cs:__imp___std_type_info_compare
0x180021d8c  test    eax, eax
0x180021d8e  jz      loc_180021C52
0x180021d94  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x180021d9a  lea     rbx, [rbp+57h+var_90]
0x180021d9e  mov     rax, [rbx+8]
0x180021da2  test    rax, rax
0x180021da5  jnz     short loc_180021DEC
0x180021da7  mov     rcx, [rbx]
0x180021daa  mov     rbx, [rbx+8]
0x180021dae  mov     rax, [rcx]
0x180021db1  mov     rax, [rax+8]
0x180021db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dba  test    rbx, rbx
0x180021dbd  jz      loc_180021CC2
0x180021dc3  mov     rcx, rbx; this
0x180021dc6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021dcb  jmp     loc_180021CC2
0x180021dd0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180021dd4  jz      short loc_180021DE6
0x180021dd6  lea     rdx, ??_R0?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@8; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor'
0x180021ddd  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x180021de2  test    al, al
0x180021de4  jnz     short loc_180021D9A
0x180021de6  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x180021dec  lock inc dword ptr [rax+8]
0x180021df0  jmp     short loc_180021DA7
0x180021df2  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
