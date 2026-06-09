# NcsiThreadpoolUpdateWcm(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18002b720`
- end: `0x18002b818`
- name: `?NcsiThreadpoolUpdateWcm@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `248`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x18002b720`
- `0x180043ca0`
- `0x180047240`
- `0x1800473f8`
- `0x18005582c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002b73d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002b73d`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmSetParameter` at `0x18002b7c0`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmSetParameter` at `0x18002b7c0`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x18002b7ea`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x18002b7ea`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmOpenHandle` at `0x18002b768`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmOpenHandle` at `0x18002b768`

## pseudocode

```c
void __fastcall NcsiThreadpoolUpdateWcm(struct _TP_CALLBACK_INSTANCE *a1, char *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // [rsp+20h] [rbp-48h]
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF
  char *v8; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a1 )
    CallbackMayRunLong(a1);
  v8 = a2;
  v7 = 0;
  v6 = 0;
  v3 = WcmOpenHandle(1, 0, &v7, &v6);
  if ( v3 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\networkhealthtracking\\lib\\networkhealthtracking.cpp",
      (const char *)v3,
      v5);
    std::unique_ptr<UpdateWCMCallbackInfo>::~unique_ptr<UpdateWCMCallbackInfo>(&v8);
  }
  else
  {
    v4 = WcmSetParameter(v6, a2 + 4, 0, 304);
    if ( v4 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\networkhealthtracking\\lib\\networkhealthtracking.cpp",
        (const char *)v4,
        0);
    WcmCloseHandle(v6, 0);
    if ( a2 )
      operator delete(a2);
  }
}

```

## disassembly

```asm
0x18002b720  push    rbx
0x18002b722  sub     rsp, 60h
0x18002b726  mov     rax, cs:__security_cookie
0x18002b72d  xor     rax, rsp
0x18002b730  mov     [rsp+68h+var_10], rax
0x18002b735  mov     rbx, rdx
0x18002b738  test    rcx, rcx
0x18002b73b  jz      short loc_18002B743
0x18002b73d  call    cs:__imp_CallbackMayRunLong
0x18002b743  mov     [rsp+68h+var_18], rbx
0x18002b748  mov     [rsp+68h+var_20], 0
0x18002b750  mov     [rsp+68h+var_28], 0
0x18002b759  lea     r9, [rsp+68h+var_28]
0x18002b75e  lea     r8, [rsp+68h+var_20]
0x18002b763  xor     edx, edx
0x18002b765  lea     ecx, [rdx+1]
0x18002b768  call    cs:__imp_WcmOpenHandle
0x18002b76e  mov     rcx, [rsp+68h]; this
0x18002b773  test    eax, eax
0x18002b775  jz      short loc_18002B798
0x18002b777  mov     r9d, eax; char *
0x18002b77a  lea     r8, aOnecoreNetDiag_11; "onecore\\net\\diagnostics\\ncsi\\networ"...
0x18002b781  mov     edx, 141h; void *
0x18002b786  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002b78b  lea     rcx, [rsp+68h+var_18]
0x18002b790  call    ??1?$unique_ptr@UUpdateWCMCallbackInfo@@U?$default_delete@UUpdateWCMCallbackInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<UpdateWCMCallbackInfo>::~unique_ptr<UpdateWCMCallbackInfo>(void)
0x18002b795  nop
0x18002b796  jmp     short loc_18002B805
0x18002b798  lea     rdx, [rbx+4]
0x18002b79c  mov     [rsp+68h+var_38], rbx
0x18002b7a1  mov     [rsp+68h+var_40], 4
0x18002b7a9  mov     qword ptr [rsp+68h+var_48], 0; unsigned int
0x18002b7b2  mov     r9d, 130h
0x18002b7b8  xor     r8d, r8d
0x18002b7bb  mov     rcx, [rsp+68h+var_28]
0x18002b7c0  call    cs:__imp_WcmSetParameter
0x18002b7c6  mov     rcx, [rsp+68h]; this
0x18002b7cb  test    eax, eax
0x18002b7cd  jz      short loc_18002B7E3
0x18002b7cf  mov     r9d, eax; char *
0x18002b7d2  lea     r8, aOnecoreNetDiag_11; "onecore\\net\\diagnostics\\ncsi\\networ"...
0x18002b7d9  mov     edx, 14Eh; void *
0x18002b7de  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002b7e3  xor     edx, edx
0x18002b7e5  mov     rcx, [rsp+68h+var_28]
0x18002b7ea  call    cs:__imp_WcmCloseHandle
0x18002b7f0  test    rbx, rbx
0x18002b7f3  jz      short loc_18002B803
0x18002b7f5  mov     edx, 14h
0x18002b7fa  mov     rcx, rbx; Block
0x18002b7fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b802  nop
0x18002b803  jmp     short $+2
0x18002b805  mov     rcx, [rsp+68h+var_10]
0x18002b80a  xor     rcx, rsp; StackCookie
0x18002b80d  call    __security_check_cookie
0x18002b812  add     rsp, 60h
0x18002b816  pop     rbx
0x18002b817  retn
```
