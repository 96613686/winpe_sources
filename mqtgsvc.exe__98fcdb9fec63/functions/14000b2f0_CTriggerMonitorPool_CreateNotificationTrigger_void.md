# CTriggerMonitorPool::CreateNotificationTrigger(void)

- ea: `0x14000b2f0`
- end: `0x14000b433`
- name: `?CreateNotificationTrigger@CTriggerMonitorPool@@AEAA?AV?$R@VCRuntimeTriggerInfo@@@@XZ`
- size: `323`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14000b984`

## callees

- `0x1400030ac`
- `0x140003868`
- `0x14000ae40`
- `0x14000b2f0`
- `0x14000ed18`
- `0x1400108d0`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::CreateNotificationTrigger(__int64 a1, __int64 a2)
{
  char v4; // di
  _bstr_t *v5; // rbx
  _bstr_t *v6; // rax
  void *v7; // rax
  void *v8; // r15
  __int64 v9; // r14
  __int64 v10; // rbx
  void *v12; // [rsp+58h] [rbp-8h] BYREF
  __int64 v13; // [rsp+A8h] [rbp+48h] BYREF
  __int64 *v14; // [rsp+B0h] [rbp+50h] BYREF
  __int64 *v15; // [rsp+B8h] [rbp+58h] BYREF

  v13 = a2;
  v4 = 0;
  _bstr_t::_bstr_t((_bstr_t *)&v15, L"MSMQ Trigger Notifications");
  v5 = _bstr_t::_bstr_t((_bstr_t *)&v12, L".\\private$\\");
  v6 = _bstr_t::_bstr_t((_bstr_t *)&v13, L"triggers_queue$");
  _bstr_t::operator+(v5, &v14, v6);
  _bstr_t::_Free((_bstr_t *)&v13);
  _bstr_t::_Free((_bstr_t *)&v12);
  v7 = MmAllocate(0x858u);
  v8 = v7;
  v12 = v7;
  if ( v7 )
  {
    if ( v14 )
      v9 = *v14;
    else
      v9 = 0;
    if ( v15 )
      v10 = *v15;
    else
      v10 = 0;
    _bstr_t::_bstr_t((_bstr_t *)&v13, &ServiceName);
    v4 = 1;
    v7 = (void *)CRuntimeTriggerInfo::CRuntimeTriggerInfo(v8, &v13, v10, v9, a1 + 296, 0, 1, 1, 0);
  }
  *(_QWORD *)a2 = v7;
  if ( (v4 & 1) != 0 )
    _bstr_t::_Free((_bstr_t *)&v13);
  *(_BYTE *)(*(_QWORD *)a2 + 16LL) = 1;
  _bstr_t::_Free((_bstr_t *)&v14);
  _bstr_t::_Free((_bstr_t *)&v15);
  return a2;
}

```

## disassembly

```asm
0x14000b2f0  mov     [rsp-38h+arg_8], rdx
0x14000b2f5  push    rbp
0x14000b2f6  push    rbx
0x14000b2f7  push    rsi
0x14000b2f8  push    rdi
0x14000b2f9  push    r13
0x14000b2fb  push    r14
0x14000b2fd  push    r15
0x14000b2ff  mov     rbp, rsp
0x14000b302  sub     rsp, 60h
0x14000b306  mov     rsi, rdx
0x14000b309  mov     r13, rcx
0x14000b30c  xor     edi, edi
0x14000b30e  mov     [rbp+var_10], edi
0x14000b311  lea     rdx, aMsmqTriggerNot; "MSMQ Trigger Notifications"
0x14000b318  lea     rcx, [rbp+arg_18]; this
0x14000b31c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000b321  nop
0x14000b322  lea     rdx, aPrivate; ".\\private$\\"
0x14000b329  lea     rcx, [rbp+var_8]; this
0x14000b32d  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000b332  mov     rbx, rax
0x14000b335  lea     rdx, aTriggersQueue; "triggers_queue$"
0x14000b33c  lea     rcx, [rbp+arg_8]; this
0x14000b340  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000b345  nop
0x14000b346  mov     r8, rax
0x14000b349  lea     rdx, [rbp+arg_10]
0x14000b34d  mov     rcx, rbx
0x14000b350  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14000b355  nop
0x14000b356  lea     rcx, [rbp+arg_8]; this
0x14000b35a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000b35f  nop
0x14000b360  lea     rcx, [rbp+var_8]; this
0x14000b364  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000b369  mov     ecx, 858h; unsigned __int64
0x14000b36e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000b373  mov     r15, rax
0x14000b376  mov     [rbp+var_8], rax
0x14000b37a  test    rax, rax
0x14000b37d  jz      short loc_14000B3F2
0x14000b37f  mov     rcx, [rbp+arg_10]
0x14000b383  test    rcx, rcx
0x14000b386  jz      short loc_14000B38D
0x14000b388  mov     r14, [rcx]
0x14000b38b  jmp     short loc_14000B390
0x14000b38d  xor     r14d, r14d
0x14000b390  mov     rax, [rbp+arg_18]
0x14000b394  test    rax, rax
0x14000b397  jz      short loc_14000B39E
0x14000b399  mov     rbx, [rax]
0x14000b39c  jmp     short loc_14000B3A0
0x14000b39e  xor     ebx, ebx
0x14000b3a0  lea     rdx, ServiceName; wchar_t *
0x14000b3a7  lea     rcx, [rbp+arg_8]; this
0x14000b3ab  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000b3b0  nop
0x14000b3b1  mov     edi, 1
0x14000b3b6  mov     [rbp+var_10], edi
0x14000b3b9  lea     rax, [r13+128h]
0x14000b3c0  mov     [rsp+60h+var_20], 0
0x14000b3c8  mov     [rsp+60h+var_28], dil
0x14000b3cd  mov     [rsp+60h+var_30], dil
0x14000b3d2  mov     [rsp+60h+var_38], 0
0x14000b3da  mov     [rsp+60h+var_40], rax
0x14000b3df  mov     r9, r14
0x14000b3e2  mov     r8, rbx
0x14000b3e5  lea     rdx, [rbp+arg_8]
0x14000b3e9  mov     rcx, r15
0x14000b3ec  call    ??0CRuntimeTriggerInfo@@QEAA@AEBV_bstr_t@@PEA_W1PEB_WW4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@_N4W4__MIDL___MIDL_itf_mqtrig_0000_0000_0003@@@Z; CRuntimeTriggerInfo::CRuntimeTriggerInfo(_bstr_t const &,wchar_t *,wchar_t *,wchar_t const *,__MIDL___MIDL_itf_mqtrig_0000_0000_0002,bool,bool,__MIDL___MIDL_itf_mqtrig_0000_0000_0003)
0x14000b3f1  nop
0x14000b3f2  mov     [rsi], rax
0x14000b3f5  or      edi, 2
0x14000b3f8  test    dil, 1
0x14000b3fc  jz      short loc_14000B407
0x14000b3fe  lea     rcx, [rbp+arg_8]; this
0x14000b402  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000b407  mov     rax, [rsi]
0x14000b40a  mov     byte ptr [rax+10h], 1
0x14000b40e  lea     rcx, [rbp+arg_10]; this
0x14000b412  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000b417  nop
0x14000b418  lea     rcx, [rbp+arg_18]; this
0x14000b41c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000b421  mov     rax, rsi
0x14000b424  add     rsp, 60h
0x14000b428  pop     r15
0x14000b42a  pop     r14
0x14000b42c  pop     r13
0x14000b42e  pop     rdi
0x14000b42f  pop     rsi
0x14000b430  pop     rbx
0x14000b431  pop     rbp
0x14000b432  retn
```
