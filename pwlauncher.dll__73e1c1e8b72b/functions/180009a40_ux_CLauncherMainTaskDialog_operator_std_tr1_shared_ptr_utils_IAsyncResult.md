# ux::CLauncherMainTaskDialog::operator()(std::tr1::shared_ptr<utils::IAsyncResult>)

- ea: `0x180009a40`
- end: `0x180009b8f`
- name: `??RCLauncherMainTaskDialog@ux@@UEAAXV?$shared_ptr@VIAsyncResult@utils@@@tr1@std@@@Z`
- size: `335`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009a40`
- `0x180009ce4`
- `0x18000c6bc`
- `0x18000c8f4`
- `0x18000d130`
- `0x180011010`

## import_xrefs

- `USER32!SendMessageW` at `0x180009b20`
- `USER32!SendMessageW` at `0x180009b20`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::operator()(ux::CLauncherMainTaskDialog *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  ux::CLauncherMainTaskDialog *v3; // r14
  __int64 v4; // rsi
  __int64 v5; // r15
  signed __int32 v6; // eax
  char v7; // di
  volatile signed __int32 *v8; // rbx
  const ATL::CAtlException *v9; // [rsp+20h] [rbp-48h] BYREF
  __int128 v10; // [rsp+28h] [rbp-40h] BYREF

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v2 = a2;
    v3 = a1;
    v10 = 0;
    v4 = a2[1];
    v5 = *a2;
    if ( v4 )
    {
      while ( 1 )
      {
        v6 = *(_DWORD *)(v4 + 8);
        if ( !v6 )
          break;
        if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v6 + 1, v6) )
        {
          if ( *((_QWORD *)&v10 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
            }
          }
          *((_QWORD *)&v10 + 1) = v4;
          *(_QWORD *)&v10 = v5;
          break;
        }
      }
    }
    v7 = CSetLauncherWorkItem::EndSetLauncher(&v10);
    CLauncherUtils::LogSqm(v7);
    CLauncherUtils::LogTraceLog(v7);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v9) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180009AF9);
      if ( !ux::CLauncherMainTaskDialog::HandleException(a1, v9) )
      {
        ux::CLauncherMainTaskDialog::EnableControls((HWND *)a1, 1u);
        v2 = a2;
        goto LABEL_15;
      }
      v3 = a1;
      v2 = a2;
    }
  }
  SendMessageW(*((HWND *)v3 + 21), 0x466u, 2u, 0);
LABEL_15:
  v8 = (volatile signed __int32 *)v2[1];
  if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  }
}

```

## disassembly

```asm
0x180009a40  mov     rax, rsp
0x180009a43  mov     [rax+20h], rbx
0x180009a47  mov     [rax+10h], rdx
0x180009a4b  mov     [rax+8], rcx
0x180009a4f  push    rsi
0x180009a50  push    rdi
0x180009a51  push    r12
0x180009a53  push    r14
0x180009a55  push    r15
0x180009a57  sub     rsp, 40h
0x180009a5b  mov     rbx, rdx
0x180009a5e  mov     r14, rcx
0x180009a61  lea     r12, [rax-40h]
0x180009a65  mov     [rsp+68h+arg_10], r12
0x180009a6d  xorps   xmm0, xmm0
0x180009a70  movdqu  xmmword ptr [rax-40h], xmm0
0x180009a75  mov     rsi, [rdx+8]
0x180009a79  mov     r15, [rdx]
0x180009a7c  test    rsi, rsi
0x180009a7f  jz      short loc_180009ADC
0x180009a81  mov     eax, [rsi+8]
0x180009a84  test    eax, eax
0x180009a86  jz      short loc_180009ADC
0x180009a88  lea     ecx, [rax+1]
0x180009a8b  lock cmpxchg [rsi+8], ecx
0x180009a90  jnz     short loc_180009A81
0x180009a92  mov     rdi, [r12+8]
0x180009a97  test    rdi, rdi
0x180009a9a  jz      short loc_180009AD3
0x180009a9c  or      eax, 0FFFFFFFFh
0x180009a9f  lock xadd [rdi+8], eax
0x180009aa4  cmp     eax, 1
0x180009aa7  jnz     short loc_180009AD3
0x180009aa9  mov     rax, [rdi]
0x180009aac  mov     rcx, rdi
0x180009aaf  mov     rax, [rax]
0x180009ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab7  or      eax, 0FFFFFFFFh
0x180009aba  lock xadd [rdi+0Ch], eax
0x180009abf  cmp     eax, 1
0x180009ac2  jnz     short loc_180009AD3
0x180009ac4  mov     rax, [rdi]
0x180009ac7  mov     rcx, rdi
0x180009aca  mov     rax, [rax+8]
0x180009ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad3  mov     [r12+8], rsi
0x180009ad8  mov     [r12], r15
0x180009adc  mov     rcx, r12
0x180009adf  call    ?EndSetLauncher@CSetLauncherWorkItem@@SA_NV?$shared_ptr@VIAsyncResult@utils@@@tr1@std@@@Z; CSetLauncherWorkItem::EndSetLauncher(std::tr1::shared_ptr<utils::IAsyncResult>)
0x180009ae4  mov     dil, al
0x180009ae7  mov     cl, al; bool
0x180009ae9  call    ?LogSqm@CLauncherUtils@@SAX_N@Z; CLauncherUtils::LogSqm(bool)
0x180009aee  mov     cl, dil; bool
0x180009af1  call    ?LogTraceLog@CLauncherUtils@@SAX_N@Z; CLauncherUtils::LogTraceLog(bool)
0x180009af6  nop
0x180009af7  jmp     short loc_180009B0D
0x180009af9  cmp     byte ptr [rsp+68h+arg_10], 0
0x180009b01  jz      short loc_180009B28
0x180009b03  mov     r14, [rsp+68h+arg_0]
0x180009b08  mov     rbx, [rsp+68h+arg_8]
0x180009b0d  xor     r9d, r9d; lParam
0x180009b10  mov     edx, 466h; Msg
0x180009b15  lea     r8d, [r9+2]; wParam
0x180009b19  mov     rcx, [r14+0A8h]; hWnd
0x180009b20  call    cs:__imp_SendMessageW
0x180009b26  jmp     short loc_180009B39
0x180009b28  mov     dl, 1; bool
0x180009b2a  mov     rcx, [rsp+68h+arg_0]; this
0x180009b2f  call    ?EnableControls@CLauncherMainTaskDialog@ux@@AEAAX_N@Z; ux::CLauncherMainTaskDialog::EnableControls(bool)
0x180009b34  mov     rbx, [rsp+68h+arg_8]
0x180009b39  mov     rbx, [rbx+8]
0x180009b3d  test    rbx, rbx
0x180009b40  jz      short loc_180009B7A
0x180009b42  or      eax, 0FFFFFFFFh
0x180009b45  lock xadd [rbx+8], eax
0x180009b4a  cmp     eax, 1
0x180009b4d  jnz     short loc_180009B7A
0x180009b4f  mov     rax, [rbx]
0x180009b52  mov     rcx, rbx
0x180009b55  mov     rax, [rax]
0x180009b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5d  or      eax, 0FFFFFFFFh
0x180009b60  lock xadd [rbx+0Ch], eax
0x180009b65  cmp     eax, 1
0x180009b68  jnz     short loc_180009B7A
0x180009b6a  mov     rax, [rbx]
0x180009b6d  mov     rcx, rbx
0x180009b70  mov     rax, [rax+8]
0x180009b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b79  nop
0x180009b7a  mov     rbx, [rsp+68h+arg_18]
0x180009b82  add     rsp, 40h
0x180009b86  pop     r15
0x180009b88  pop     r14
0x180009b8a  pop     r12
0x180009b8c  pop     rdi
0x180009b8d  pop     rsi
0x180009b8e  retn
```
