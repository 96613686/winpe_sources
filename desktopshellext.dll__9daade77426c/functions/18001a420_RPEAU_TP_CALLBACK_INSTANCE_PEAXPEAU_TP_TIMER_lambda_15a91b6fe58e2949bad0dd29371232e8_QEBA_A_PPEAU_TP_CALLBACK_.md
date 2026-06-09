# ??$?RPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@_lambda_15a91b6fe58e2949bad0dd29371232e8_@@QEBA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z

- ea: `0x18001a420`
- end: `0x18001a50a`
- name: `??$?RPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@_lambda_15a91b6fe58e2949bad0dd29371232e8_@@QEBA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003dd80`

## callees

- `0x180008260`
- `0x180009c00`
- `0x18000a040`
- `0x18001a420`
- `0x18001a510`
- `0x18001a5f8`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4e9`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001a4b3`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001a4b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _lambda_15a91b6fe58e2949bad0dd29371232e8_::operator()<_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *>(
        __int64 a1,
        struct _TP_CALLBACK_INSTANCE *a2,
        __int64 a3)
{
  struct _TP_CALLBACK_INSTANCE *v3; // r9
  std::_Ref_count_base *v4; // rcx
  __int64 *v5; // r8
  __int64 v6; // rdi
  std::_Ref_count_base *v7; // rbx
  _BYTE v8[56]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v9; // [rsp+68h] [rbp-20h]

  v3 = a2;
  v4 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v4 && std::_Ref_count_base::_Incref_nz(v4) )
  {
    v6 = *v5;
    v7 = (std::_Ref_count_base *)v5[1];
  }
  else
  {
    v7 = 0;
    v6 = 0;
  }
  if ( v6 )
  {
    DisassociateCurrentThreadFromCallback(v3);
    v9 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v6 + 16));
    *(_BYTE *)(v6 + 88) = 0;
    std::function<void (void)>::operator=(v8, v6 + 24);
    if ( v6 != -16 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 16));
    std::_Func_class<void,>::operator()(v8);
    std::_Func_class<void,>::_Tidy(v8);
  }
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x18001a420  mov     [rsp+arg_0], rbx
0x18001a425  mov     [rsp+arg_18], rsi
0x18001a42a  push    rdi
0x18001a42b  sub     rsp, 80h
0x18001a432  mov     rax, cs:__security_cookie
0x18001a439  xor     rax, rsp
0x18001a43c  mov     [rsp+88h+var_18], rax
0x18001a441  mov     r9, rdx
0x18001a444  xorps   xmm0, xmm0
0x18001a447  movdqu  [rsp+88h+var_68], xmm0
0x18001a44d  mov     rcx, [r8+8]; this
0x18001a451  test    rcx, rcx
0x18001a454  jz      short loc_18001A472
0x18001a456  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18001a45b  test    al, al
0x18001a45d  jz      short loc_18001A472
0x18001a45f  mov     rdi, [r8]
0x18001a462  mov     qword ptr [rsp+88h+var_68], rdi
0x18001a467  mov     rbx, [r8+8]
0x18001a46b  mov     qword ptr [rsp+88h+var_68+8], rbx
0x18001a470  jmp     short loc_18001A47C
0x18001a472  mov     rbx, qword ptr [rsp+88h+var_68+8]
0x18001a477  mov     rdi, qword ptr [rsp+88h+var_68]
0x18001a47c  test    rdi, rdi
0x18001a47f  jnz     short loc_18001A4B0
0x18001a481  test    rbx, rbx
0x18001a484  jz      short loc_18001A48E
0x18001a486  mov     rcx, rbx; this
0x18001a489  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a48e  mov     rcx, [rsp+88h+var_18]
0x18001a493  xor     rcx, rsp; StackCookie
0x18001a496  call    __security_check_cookie
0x18001a49b  lea     r11, [rsp+88h+var_8]
0x18001a4a3  mov     rbx, [r11+10h]
0x18001a4a7  mov     rsi, [r11+28h]
0x18001a4ab  mov     rsp, r11
0x18001a4ae  pop     rdi
0x18001a4af  retn
0x18001a4b0  mov     rcx, r9; pci
0x18001a4b3  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18001a4b9  mov     [rsp+88h+var_20], 0
0x18001a4c2  lea     rsi, [rdi+10h]
0x18001a4c6  mov     rcx, rsi; SRWLock
0x18001a4c9  call    cs:__imp_AcquireSRWLockExclusive
0x18001a4cf  mov     byte ptr [rdi+58h], 0
0x18001a4d3  lea     rdx, [rdi+18h]
0x18001a4d7  lea     rcx, [rsp+88h+var_58]
0x18001a4dc  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18001a4e1  test    rsi, rsi
0x18001a4e4  jz      short loc_18001A4EF
0x18001a4e6  mov     rcx, rsi; SRWLock
0x18001a4e9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a4ef  lea     rcx, [rsp+88h+var_58]
0x18001a4f4  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18001a4f9  nop
0x18001a4fa  lea     rcx, [rsp+88h+var_58]
0x18001a4ff  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001a504  jmp     loc_18001A481
```
