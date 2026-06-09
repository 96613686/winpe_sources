# ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z

- ea: `0x1800083c0`
- end: `0x180008516`
- name: `??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `342`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008260`
- `0x1800083c0`
- `0x180009c00`
- `0x18000a040`
- `0x18002a3d0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008462`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008462`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084c2`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18000844d`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18000844d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800084d1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800084d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _lambda_8b0b9dbd4459d626ffc8152be8328efc_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long>(
        PTP_CALLBACK_INSTANCE Instance,
        __int64 *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _TP_CALLBACK_INSTANCE *v5; // r8
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rbx
  std::_Ref_count_base *v8; // rdi
  RTL_SRWLOCK *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  _BYTE *v12; // rdx
  _BYTE v13[56]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE *v14; // [rsp+68h] [rbp-18h]

  v5 = Instance;
  v6 = (std::_Ref_count_base *)Context[1];
  if ( v6 && std::_Ref_count_base::_Incref_nz(v6) )
  {
    v7 = *Context;
    v8 = (std::_Ref_count_base *)Context[1];
  }
  else
  {
    v8 = 0;
    v7 = 0;
  }
  if ( v7 )
  {
    DisassociateCurrentThreadFromCallback(v5);
    v14 = 0;
    v9 = (RTL_SRWLOCK *)(v7 + 16);
    AcquireSRWLockExclusive((PSRWLOCK)(v7 + 16));
    *(_BYTE *)(v7 + 88) = 0;
    v10 = v7 + 24;
    if ( v13 != (_BYTE *)v10 )
    {
      std::_Func_class<void,>::_Tidy(v13);
      v11 = *(_QWORD *)(v10 + 56);
      if ( v11 )
      {
        if ( v11 == v10 )
        {
          v14 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 8LL))(v11, v13);
          std::_Func_class<void,>::_Tidy(v10);
        }
        else
        {
          v14 = *(_BYTE **)(v10 + 56);
          *(_QWORD *)(v10 + 56) = 0;
        }
      }
    }
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    if ( !v14 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v14 )
    {
      v12 = v13;
      LOBYTE(v12) = v14 != v13;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v14 + 32LL))(v14, v12);
      v14 = 0;
    }
  }
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
}

```

## disassembly

```asm
0x1800083c0  mov     [rsp-18h+arg_10], rbx
0x1800083c5  push    rbp
0x1800083c6  push    rsi
0x1800083c7  push    rdi
0x1800083c8  mov     rbp, rsp
0x1800083cb  sub     rsp, 80h
0x1800083d2  mov     rax, cs:__security_cookie
0x1800083d9  xor     rax, rsp
0x1800083dc  mov     [rbp+var_10], rax
0x1800083e0  mov     rdi, rdx
0x1800083e3  mov     r8, rcx
0x1800083e6  xorps   xmm0, xmm0
0x1800083e9  movdqu  [rbp+var_60], xmm0
0x1800083ee  mov     rcx, [rdx+8]; this
0x1800083f2  test    rcx, rcx
0x1800083f5  jz      short loc_180008411
0x1800083f7  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x1800083fc  test    al, al
0x1800083fe  jz      short loc_180008411
0x180008400  mov     rbx, [rdi]
0x180008403  mov     qword ptr [rbp+var_60], rbx
0x180008407  mov     rdi, [rdi+8]
0x18000840b  mov     qword ptr [rbp+var_60+8], rdi
0x18000840f  jmp     short loc_180008419
0x180008411  mov     rdi, qword ptr [rbp+var_60+8]
0x180008415  mov     rbx, qword ptr [rbp+var_60]
0x180008419  test    rbx, rbx
0x18000841c  jnz     short loc_18000844A
0x18000841e  test    rdi, rdi
0x180008421  jz      short loc_18000842B
0x180008423  mov     rcx, rdi; this
0x180008426  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000842b  mov     rcx, [rbp+var_10]
0x18000842f  xor     rcx, rsp; StackCookie
0x180008432  call    __security_check_cookie
0x180008437  mov     rbx, [rsp+80h+arg_10]
0x18000843f  add     rsp, 80h
0x180008446  pop     rdi
0x180008447  pop     rsi
0x180008448  pop     rbp
0x180008449  retn
0x18000844a  mov     rcx, r8; pci
0x18000844d  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x180008453  mov     [rbp+var_18], 0
0x18000845b  lea     rsi, [rbx+10h]
0x18000845f  mov     rcx, rsi; SRWLock
0x180008462  call    cs:__imp_AcquireSRWLockExclusive
0x180008468  mov     byte ptr [rbx+58h], 0
0x18000846c  add     rbx, 18h
0x180008470  lea     rax, [rbp+var_50]
0x180008474  cmp     rax, rbx
0x180008477  jz      short loc_1800084BA
0x180008479  lea     rcx, [rbp+var_50]
0x18000847d  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180008482  mov     rcx, [rbx+38h]
0x180008486  test    rcx, rcx
0x180008489  jz      short loc_1800084BA
0x18000848b  cmp     rcx, rbx
0x18000848e  jnz     short loc_1800084AE
0x180008490  mov     rax, [rcx]
0x180008493  lea     rdx, [rbp+var_50]
0x180008497  mov     rax, [rax+8]
0x18000849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a0  mov     [rbp+var_18], rax
0x1800084a4  mov     rcx, rbx
0x1800084a7  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800084ac  jmp     short loc_1800084BA
0x1800084ae  mov     [rbp+var_18], rcx
0x1800084b2  mov     qword ptr [rbx+38h], 0
0x1800084ba  test    rsi, rsi
0x1800084bd  jz      short loc_1800084C8
0x1800084bf  mov     rcx, rsi; SRWLock
0x1800084c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084c8  mov     rcx, [rbp+var_18]
0x1800084cc  test    rcx, rcx
0x1800084cf  jnz     short loc_1800084D8
0x1800084d1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800084d7  int     3; Trap to Debugger
0x1800084d8  mov     rax, [rcx]
0x1800084db  mov     rax, [rax+10h]
0x1800084df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e4  nop
0x1800084e5  mov     rcx, [rbp+var_18]
0x1800084e9  test    rcx, rcx
0x1800084ec  jz      loc_18000841E
0x1800084f2  mov     rax, [rcx]
0x1800084f5  lea     rdx, [rbp+var_50]
0x1800084f9  cmp     rcx, rdx
0x1800084fc  setnz   dl
0x1800084ff  mov     rax, [rax+20h]
0x180008503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008508  mov     [rbp+var_18], 0
0x180008510  jmp     loc_18000841E
```
