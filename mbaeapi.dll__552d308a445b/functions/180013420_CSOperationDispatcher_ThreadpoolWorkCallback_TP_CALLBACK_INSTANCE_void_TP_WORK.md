# CSOperationDispatcher::_ThreadpoolWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180013420`
- end: `0x180013661`
- name: `?_ThreadpoolWorkCallback@CSOperationDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `577`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, volatile __int32 *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180013420`
- `0x18005c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180013565`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800135a1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180013565`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800135a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001347b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001347b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800135c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800135c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013545`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001363c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013545`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001363c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013458`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013458`

## pseudocode

```c
void __fastcall CSOperationDispatcher::_ThreadpoolWorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        volatile __int32 *Context,
        PTP_WORK Work)
{
  volatile __int32 *v3; // rdi
  volatile __int32 *v4; // r14
  volatile __int32 *v5; // r13
  volatile __int32 *v6; // r12
  __int64 *v7; // rsi
  __int64 v8; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // r13
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char *v17; // r9
  __int64 v18; // [rsp+20h] [rbp-58h] BYREF
  volatile __int32 *v19; // [rsp+28h] [rbp-50h]
  volatile __int32 *v20; // [rsp+38h] [rbp-40h]
  __int128 v21; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v24; // [rsp+98h] [rbp+20h] BYREF

  if ( Context )
  {
    v3 = Context;
    v19 = Context;
    v4 = Context;
    v5 = Context;
    v6 = Context + 15;
    v20 = Context + 15;
    _InterlockedExchange(Context + 15, GetCurrentThreadId());
    while ( 1 )
    {
      v21 = 0;
      AcquireSRWLockExclusive((PSRWLOCK)v3 + 6);
      if ( *((_BYTE *)v3 + 57) || !*((_QWORD *)v5 + 5) )
        break;
      v7 = *(__int64 **)(*((_QWORD *)v4 + 2) + 8 * (*((_QWORD *)v4 + 4) & (*((_QWORD *)v4 + 3) - 1LL)));
      v8 = v7[1];
      if ( v8 )
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
      v24 = *v7;
      *(_QWORD *)&v21 = v24;
      v9 = (volatile signed __int32 *)v7[1];
      *((_QWORD *)&v21 + 1) = v9;
      v10 = *(volatile signed __int32 **)(*(_QWORD *)(*((_QWORD *)v4 + 2)
                                                    + 8 * (*((_QWORD *)v4 + 4) & (*((_QWORD *)v4 + 3) - 1LL)))
                                        + 8LL);
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v5 = Context;
      if ( (*((_QWORD *)Context + 5))-- == 1 )
        *((_QWORD *)v4 + 4) = 0;
      else
        ++*((_QWORD *)v4 + 4);
      if ( v3 != (volatile __int32 *)-48LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v3 + 6);
      try
      {
        v12 = v24;
        if ( *(_QWORD *)v24 )
        {
          v13 = *(_QWORD *)(*(_QWORD *)v24 + 56LL);
          if ( !v13 )
            std::_Xbad_function_call();
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v14 = *(_QWORD *)(v12 + 8);
        if ( v14 )
        {
          v15 = *(_QWORD *)(v12 + 24);
          v24 = *(_QWORD *)(v12 + 32) - v15;
          v18 = v15;
          v16 = *(_QWORD *)(v14 + 56);
          if ( !v16 )
            std::_Xbad_function_call();
          (*(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v16 + 16LL))(v16, &v18, &v24);
        }
        SetEvent(*(HANDLE *)(v12 + 16));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\Utils.h",
          v17);
        v3 = v19;
        v9 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
        v4 = v19;
        v6 = v20;
        v5 = v19;
      }
      if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    *((_BYTE *)v3 + 56) = 0;
    if ( v3 != (volatile __int32 *)-48LL )
      ReleaseSRWLockExclusive((PSRWLOCK)v3 + 6);
    _InterlockedExchange(v6, 0);
  }
}

```

## disassembly

```asm
0x180013420  test    rdx, rdx
0x180013423  jz      locret_180013660
0x180013429  mov     [rsp+arg_0], rbx
0x18001342e  mov     [rsp+arg_10], rsi
0x180013433  push    rdi
0x180013434  push    r12
0x180013436  push    r13
0x180013438  push    r14
0x18001343a  push    r15
0x18001343c  sub     rsp, 50h
0x180013440  mov     rdi, rdx
0x180013443  xor     ebx, ebx
0x180013445  mov     [rsp+78h+var_50], rdx
0x18001344a  mov     r14, rdx
0x18001344d  mov     r13, rdx
0x180013450  mov     [rsp+78h+arg_8], rdx
0x180013458  call    cs:__imp_GetCurrentThreadId
0x18001345e  lea     r12, [r13+3Ch]
0x180013462  mov     [rsp+78h+var_40], r12
0x180013467  xchg    eax, [r12]
0x18001346b  xorps   xmm0, xmm0
0x18001346e  movdqu  [rsp+78h+var_38], xmm0
0x180013474  lea     r15, [rdi+30h]
0x180013478  mov     rcx, r15; SRWLock
0x18001347b  call    cs:__imp_AcquireSRWLockExclusive
0x180013481  cmp     [rdi+39h], bl
0x180013484  jnz     loc_180013631
0x18001348a  cmp     [r13+28h], rbx
0x18001348e  jz      loc_180013631
0x180013494  mov     rcx, [r14+18h]
0x180013498  dec     rcx
0x18001349b  and     rcx, [r14+20h]
0x18001349f  mov     rax, [r14+10h]
0x1800134a3  mov     rsi, [rax+rcx*8]
0x1800134a7  mov     rax, [rsi+8]
0x1800134ab  test    rax, rax
0x1800134ae  jz      short loc_1800134B4
0x1800134b0  lock inc dword ptr [rax+8]
0x1800134b4  mov     rax, [rsi]
0x1800134b7  mov     [rsp+78h+arg_18], rax
0x1800134bf  mov     qword ptr [rsp+78h+var_38], rax
0x1800134c4  mov     rsi, [rsi+8]
0x1800134c8  mov     qword ptr [rsp+78h+var_38+8], rsi
0x1800134cd  mov     rcx, [r14+18h]
0x1800134d1  dec     rcx
0x1800134d4  and     rcx, [r14+20h]
0x1800134d8  mov     rax, [r14+10h]
0x1800134dc  mov     rcx, [rax+rcx*8]
0x1800134e0  mov     r13, [rcx+8]
0x1800134e4  test    r13, r13
0x1800134e7  jz      short loc_180013524
0x1800134e9  or      eax, 0FFFFFFFFh
0x1800134ec  lock xadd [r13+8], eax
0x1800134f2  cmp     eax, 1
0x1800134f5  jnz     short loc_180013524
0x1800134f7  mov     rax, [r13+0]
0x1800134fb  mov     rcx, r13
0x1800134fe  mov     rax, [rax]
0x180013501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013506  or      eax, 0FFFFFFFFh
0x180013509  lock xadd [r13+0Ch], eax
0x18001350f  cmp     eax, 1
0x180013512  jnz     short loc_180013524
0x180013514  mov     rax, [r13+0]
0x180013518  mov     rcx, r13
0x18001351b  mov     rax, [rax+8]
0x18001351f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013524  mov     r13, [rsp+78h+arg_8]
0x18001352c  sub     qword ptr [r13+28h], 1
0x180013531  jnz     short loc_180013539
0x180013533  mov     [r14+20h], rbx
0x180013537  jmp     short loc_18001353D
0x180013539  inc     qword ptr [r14+20h]
0x18001353d  test    r15, r15
0x180013540  jz      short loc_18001354C
0x180013542  mov     rcx, r15; SRWLock
0x180013545  call    cs:__imp_ReleaseSRWLockExclusive
0x18001354b  nop
0x18001354c  mov     r15, [rsp+78h+arg_18]
0x180013554  mov     rcx, [r15]
0x180013557  test    rcx, rcx
0x18001355a  jz      short loc_180013577
0x18001355c  mov     rcx, [rcx+38h]
0x180013560  test    rcx, rcx
0x180013563  jnz     short loc_18001356B
0x180013565  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001356b  mov     rax, [rcx]
0x18001356e  mov     rax, [rax+10h]
0x180013572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013577  mov     rdx, [r15+8]
0x18001357b  test    rdx, rdx
0x18001357e  jz      short loc_1800135C0
0x180013580  mov     rcx, [r15+18h]
0x180013584  mov     rax, [r15+20h]
0x180013588  sub     rax, rcx
0x18001358b  mov     [rsp+78h+arg_18], rax
0x180013593  mov     [rsp+78h+var_58], rcx
0x180013598  mov     rcx, [rdx+38h]
0x18001359c  test    rcx, rcx
0x18001359f  jnz     short loc_1800135A7
0x1800135a1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800135a7  mov     rax, [rcx]
0x1800135aa  lea     r8, [rsp+78h+arg_18]
0x1800135b2  lea     rdx, [rsp+78h+var_58]
0x1800135b7  mov     rax, [rax+10h]
0x1800135bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135c0  mov     rcx, [r15+10h]; hEvent
0x1800135c4  call    cs:__imp_SetEvent
0x1800135ca  nop
0x1800135cb  jmp     short loc_1800135E4
0x1800135cd  xor     ebx, ebx
0x1800135cf  mov     rdi, [rsp+78h+var_50]
0x1800135d4  mov     rsi, qword ptr [rsp+78h+var_38+8]
0x1800135d9  mov     r14, rdi
0x1800135dc  mov     r12, [rsp+78h+var_40]
0x1800135e1  mov     r13, rdi
0x1800135e4  test    rsi, rsi
0x1800135e7  jz      loc_18001346B
0x1800135ed  or      eax, 0FFFFFFFFh
0x1800135f0  lock xadd [rsi+8], eax
0x1800135f5  cmp     eax, 1
0x1800135f8  jnz     loc_18001346B
0x1800135fe  mov     rax, [rsi]
0x180013601  mov     rcx, rsi
0x180013604  mov     rax, [rax]
0x180013607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001360c  or      eax, 0FFFFFFFFh
0x18001360f  lock xadd [rsi+0Ch], eax
0x180013614  cmp     eax, 1
0x180013617  jnz     loc_18001346B
0x18001361d  mov     rax, [rsi]
0x180013620  mov     rcx, rsi
0x180013623  mov     rax, [rax+8]
0x180013627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001362c  jmp     loc_18001346B
0x180013631  mov     [rdi+38h], bl
0x180013634  test    r15, r15
0x180013637  jz      short loc_180013643
0x180013639  mov     rcx, r15; SRWLock
0x18001363c  call    cs:__imp_ReleaseSRWLockExclusive
0x180013642  nop
0x180013643  xchg    ebx, [r12]
0x180013647  lea     r11, [rsp+78h+var_28]
0x18001364c  mov     rbx, [r11+30h]
0x180013650  mov     rsi, [r11+40h]
0x180013654  mov     rsp, r11
0x180013657  pop     r15
0x180013659  pop     r14
0x18001365b  pop     r13
0x18001365d  pop     r12
0x18001365f  pop     rdi
0x180013660  retn
```
