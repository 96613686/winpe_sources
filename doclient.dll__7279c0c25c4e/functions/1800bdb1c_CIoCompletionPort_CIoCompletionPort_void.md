# CIoCompletionPort::CIoCompletionPort(void)

- ea: `0x1800bdb1c`
- end: `0x1800bdd1f`
- name: `??0CIoCompletionPort@@QEAA@XZ`
- size: `515`
- prototype: `CIoCompletionPort *__fastcall(CIoCompletionPort *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800283f0`
- `0x18007c4c0`

## callees

- `0x180009528`
- `0x1800199b4`
- `0x180039b68`
- `0x1800bdb1c`
- `0x1800be6bc`
- `0x1800f7fe8`
- `0x1800f82f0`
- `0x1800f8320`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdcc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdcc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdc1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdc1e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800bdbf4`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800bdbf4`

## string_xrefs

- `0x1800bdd0d`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\IoCompletionPort.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CIoCompletionPort *__fastcall CIoCompletionPort::CIoCompletionPort(CIoCompletionPort *this)
{
  char *v2; // rdi
  void **v3; // r14
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  const char *v6; // r9
  HANDLE IoCompletionPort; // r15
  void *v8; // rbx
  DWORD LastError; // edi
  char v10; // al
  __int64 v11; // rax
  __int64 v12; // rbx
  char *v13; // rax
  HANDLE hObject; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+38h] [rbp-38h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  CIoCompletionPort *v18; // [rsp+50h] [rbp-20h]
  char *v19; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v18 = this;
  v2 = (char *)operator new(0x40u);
  v19 = v2;
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  *((_DWORD *)v2 + 3) = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<CIoCompletionPort::PortCompletionHandler>::`vftable';
  v3 = (void **)(v2 + 16);
  *(_QWORD *)&v17 = v2 + 16;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 0;
  *((_QWORD *)v2 + 7) = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *v4 = v4;
  v4[1] = v4;
  *((_QWORD *)v2 + 3) = v4;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 0;
  v5 = operator new(0x68u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *((_QWORD *)v2 + 5) = v5;
  *((_QWORD *)v2 + 7) = 0;
  *(_OWORD *)this = 0;
  *(_QWORD *)this = v2 + 16;
  *((_QWORD *)this + 1) = v2;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( *((_QWORD *)v2 + 2) && *v3 != (void *)-1LL )
  {
    v8 = *v3;
    LastError = GetLastError();
    CloseHandle(v8);
    SetLastError(LastError);
  }
  *v3 = IoCompletionPort;
  if ( !**(_QWORD **)this || (v10 = 0, **(_QWORD **)this == -1) )
    v10 = 1;
  if ( v10 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\IoCompletionPort.cpp",
      v6);
  v11 = *((_QWORD *)this + 1);
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)&v17 = *(_QWORD *)this;
  v12 = *((_QWORD *)this + 1);
  v13 = (char *)operator new(0x10u);
  *(_QWORD *)v13 = v17;
  *((_QWORD *)v13 + 1) = v12;
  v17 = 0;
  v19 = v13;
  hObject = (HANDLE)o__beginthreadex_0(
                      0,
                      0,
                      std::thread::_Invoke_std::tuple__CIoCompletionPort::CIoCompletionPort_::_2_::_lambda_1____0_,
                      v13,
                      0,
                      &v16);
  if ( !hObject )
  {
    v16 = 0;
    std::_Throw_Cpp_error(6);
  }
  v19 = 0;
  std::unique_ptr_std::tuple__CIoCompletionPort::CIoCompletionPort_::_2_::_lambda_1____std::default_delete_std::tuple__CIoCompletionPort::CIoCompletionPort_::_2_::_lambda_1_______::_unique_ptr_std::tuple__CIoCompletionPort::CIoCompletionPort_::_2_::_lambda_1____std::default_delete_std::tuple__CIoCompletionPort::CIoCompletionPort_::_2_::_lambda_1_______(&v19);
  if ( !v16 || !CloseHandle(hObject) )
    std::_Throw_Cpp_error(1);
  return this;
}

```

## disassembly

```asm
0x1800bdb1c  mov     [rsp-28h+arg_8], rbx
0x1800bdb21  mov     [rsp-28h+arg_10], rsi
0x1800bdb26  push    rbp
0x1800bdb27  push    rdi
0x1800bdb28  push    r12
0x1800bdb2a  push    r14
0x1800bdb2c  push    r15
0x1800bdb2e  mov     rbp, rsp
0x1800bdb31  sub     rsp, 70h
0x1800bdb35  mov     rax, cs:__security_cookie
0x1800bdb3c  xor     rax, rsp
0x1800bdb3f  mov     [rbp+var_10], rax
0x1800bdb43  mov     rsi, rcx
0x1800bdb46  mov     [rbp+var_20], rcx
0x1800bdb4a  xor     r12d, r12d
0x1800bdb4d  lea     ecx, [r12+40h]; Size
0x1800bdb52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdb57  mov     rdi, rax
0x1800bdb5a  mov     [rbp+var_18], rax
0x1800bdb5e  xorps   xmm0, xmm0
0x1800bdb61  movups  xmmword ptr [rax], xmm0
0x1800bdb64  mov     dword ptr [rax+8], 1
0x1800bdb6b  mov     dword ptr [rax+0Ch], 1
0x1800bdb72  lea     rax, ??_7?$_Ref_count_obj2@UPortCompletionHandler@CIoCompletionPort@@@std@@6B@; const std::_Ref_count_obj2<CIoCompletionPort::PortCompletionHandler>::`vftable'
0x1800bdb79  mov     [rdi], rax
0x1800bdb7c  lea     r14, [rdi+10h]
0x1800bdb80  mov     qword ptr [rbp+var_30], r14
0x1800bdb84  mov     [r14+18h], r12
0x1800bdb88  mov     [r14+20h], r12
0x1800bdb8c  mov     [r14+28h], r12
0x1800bdb90  mov     [r14], r12
0x1800bdb93  mov     [r14+8], r12
0x1800bdb97  mov     [r14+10h], r12
0x1800bdb9b  lea     ecx, [r12+18h]
0x1800bdba0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800bdba5  mov     [rax], rax
0x1800bdba8  mov     [rax+8], rax
0x1800bdbac  mov     [r14+8], rax
0x1800bdbb0  mov     [r14+18h], r12
0x1800bdbb4  mov     [r14+20h], r12
0x1800bdbb8  lea     ecx, [r12+68h]; Size
0x1800bdbbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdbc2  mov     [rax], rax
0x1800bdbc5  mov     [rax+8], rax
0x1800bdbc9  mov     [rax+10h], rax
0x1800bdbcd  mov     word ptr [rax+18h], 101h
0x1800bdbd3  mov     [r14+18h], rax
0x1800bdbd7  mov     [r14+28h], r12
0x1800bdbdb  xorps   xmm0, xmm0
0x1800bdbde  movups  xmmword ptr [rsi], xmm0
0x1800bdbe1  mov     [rsi], r14
0x1800bdbe4  mov     [rsi+8], rdi
0x1800bdbe8  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800bdbeb  xor     r8d, r8d; CompletionKey
0x1800bdbee  xor     edx, edx; ExistingCompletionPort
0x1800bdbf0  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800bdbf4  call    cs:__imp_CreateIoCompletionPort
0x1800bdbfa  mov     r15, rax
0x1800bdbfd  cmp     [r14], r12
0x1800bdc00  jz      short loc_1800BDC24
0x1800bdc02  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800bdc06  jz      short loc_1800BDC24
0x1800bdc08  mov     rbx, [r14]
0x1800bdc0b  call    cs:__imp_GetLastError
0x1800bdc11  mov     edi, eax
0x1800bdc13  mov     rcx, rbx; hObject
0x1800bdc16  call    cs:__imp_CloseHandle
0x1800bdc1c  mov     ecx, edi; dwErrCode
0x1800bdc1e  call    cs:__imp_SetLastError
0x1800bdc24  mov     [r14], r15
0x1800bdc27  mov     rax, [rsi]
0x1800bdc2a  cmp     [rax], r12
0x1800bdc2d  jz      short loc_1800BDC38
0x1800bdc2f  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800bdc33  mov     al, r12b
0x1800bdc36  jnz     short loc_1800BDC3A
0x1800bdc38  mov     al, 1
0x1800bdc3a  mov     rcx, [rbp+28h]; this
0x1800bdc3e  test    al, al
0x1800bdc40  jnz     loc_1800BDD0D
0x1800bdc46  mov     rax, [rsi+8]
0x1800bdc4a  test    rax, rax
0x1800bdc4d  jz      short loc_1800BDC53
0x1800bdc4f  lock inc dword ptr [rax+8]
0x1800bdc53  mov     rdi, [rsi]
0x1800bdc56  mov     qword ptr [rbp+var_30], rdi
0x1800bdc5a  mov     rbx, [rsi+8]
0x1800bdc5e  mov     qword ptr [rbp+var_30+8], rbx
0x1800bdc62  mov     ecx, 10h; Size
0x1800bdc67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdc6c  mov     [rax], rdi
0x1800bdc6f  mov     [rax+8], rbx
0x1800bdc73  xorps   xmm0, xmm0
0x1800bdc76  movdqu  [rbp+var_30], xmm0
0x1800bdc7b  mov     [rbp+var_18], rax
0x1800bdc7f  lea     rcx, [rbp+var_38]
0x1800bdc83  mov     [rsp+70h+var_48], rcx
0x1800bdc88  mov     [rsp+70h+var_50], r12d
0x1800bdc8d  mov     r9, rax
0x1800bdc90  lea     r8, std__thread___Invoke_std__tuple__CIoCompletionPort__CIoCompletionPort____2____lambda_1____0_
0x1800bdc97  xor     edx, edx
0x1800bdc99  xor     ecx, ecx
0x1800bdc9b  call    _o__beginthreadex_0
0x1800bdca0  mov     [rbp+hObject], rax
0x1800bdca4  test    rax, rax
0x1800bdca7  jz      short loc_1800BDCFE
0x1800bdca9  mov     [rbp+var_18], r12
0x1800bdcad  lea     rcx, [rbp+var_18]
0x1800bdcb1  call    std__unique_ptr_std__tuple__CIoCompletionPort__CIoCompletionPort____2____lambda_1____std__default_delete_std__tuple__CIoCompletionPort__CIoCompletionPort____2____lambda_1__________unique_ptr_std__tuple__CIoCompletionPort__CIoCompletionPort____2____lambda_1____std__default_delete_std__tuple__CIoCompletionPort__CIoCompletionPort____2____lambda_1_______
0x1800bdcb6  nop
0x1800bdcb7  cmp     [rbp+var_38], r12d
0x1800bdcbb  jz      short loc_1800BDCF3
0x1800bdcbd  mov     rcx, [rbp+hObject]; hObject
0x1800bdcc1  call    cs:__imp_CloseHandle
0x1800bdcc7  test    eax, eax
0x1800bdcc9  jz      short loc_1800BDCF3
0x1800bdccb  mov     rax, rsi
0x1800bdcce  mov     rcx, [rbp+var_10]
0x1800bdcd2  xor     rcx, rsp; StackCookie
0x1800bdcd5  call    __security_check_cookie
0x1800bdcda  lea     r11, [rsp+70h+var_s0]
0x1800bdcdf  mov     rbx, [r11+38h]
0x1800bdce3  mov     rsi, [r11+40h]
0x1800bdce7  mov     rsp, r11
0x1800bdcea  pop     r15
0x1800bdcec  pop     r14
0x1800bdcee  pop     r12
0x1800bdcf0  pop     rdi
0x1800bdcf1  pop     rbp
0x1800bdcf2  retn
0x1800bdcf3  mov     ecx, 1; int
0x1800bdcf8  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800bdcfe  mov     [rbp+var_38], r12d
0x1800bdd02  mov     ecx, 6; int
0x1800bdd07  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800bdd0d  lea     r8, aCW1SSrcDeliver_72; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800bdd14  mov     edx, 0Ah; void *
0x1800bdd19  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
