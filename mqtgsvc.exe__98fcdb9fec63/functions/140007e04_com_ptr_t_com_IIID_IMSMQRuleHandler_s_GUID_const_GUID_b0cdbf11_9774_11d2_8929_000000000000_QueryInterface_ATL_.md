# _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(ATL::CComPtr<IUnknown> const &)

- ea: `0x140007e04`
- end: `0x140007ea1`
- name: `??$_QueryInterface@V?$CComPtr@UIUnknown@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@AEAAJAEBV?$CComPtr@UIUnknown@@@ATL@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140007dbc`
- `0x14000d110`

## callees

- `0x1400046bc`
- `0x140004eb4`
- `0x140007e04`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::_QueryInterface<ATL::CComPtr<IUnknown>>(
        __int64 *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v3 = *a2;
  if ( *a2 )
  {
    v8 = 0;
    v4 = (**v3)(v3, &GUID_b0cdbf11_9774_11d2_8929_000000000000, &v8);
    if ( v4 >= 0 )
    {
      v5 = v8;
      R<IObjectContext>::~R<IObjectContext>(a1);
      *a1 = v5;
    }
    else
    {
      R<IObjectContext>::~R<IObjectContext>(a1);
      *a1 = 0;
    }
  }
  else
  {
    v6 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(a1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return (unsigned int)-2147467262;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140007e04  mov     r11, rsp
0x140007e07  mov     [r11+8], rbx
0x140007e0b  mov     [r11+18h], rsi
0x140007e0f  push    rdi
0x140007e10  sub     rsp, 20h
0x140007e14  mov     rdi, rcx
0x140007e17  mov     rcx, [rdx]
0x140007e1a  test    rcx, rcx
0x140007e1d  jz      short loc_140007E63
0x140007e1f  mov     qword ptr [r11+10h], 0
0x140007e27  mov     rax, [rcx]
0x140007e2a  lea     r8, [r11+10h]
0x140007e2e  lea     rdx, _GUID_b0cdbf11_9774_11d2_8929_000000000000
0x140007e35  mov     rax, [rax]
0x140007e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e3d  mov     esi, eax
0x140007e3f  mov     rcx, rdi
0x140007e42  test    eax, eax
0x140007e44  jns     short loc_140007E54
0x140007e46  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x140007e4b  mov     qword ptr [rdi], 0
0x140007e52  jmp     short loc_140007E8F
0x140007e54  mov     rbx, [rsp+28h+arg_8]
0x140007e59  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x140007e5e  mov     [rdi], rbx
0x140007e61  jmp     short loc_140007E8F
0x140007e63  mov     rbx, [rdi]
0x140007e66  test    rbx, rbx
0x140007e69  jz      short loc_140007E8A
0x140007e6b  mov     qword ptr [rdi], 0
0x140007e72  mov     rcx, rdi
0x140007e75  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x140007e7a  mov     rax, [rbx]
0x140007e7d  mov     rcx, rbx
0x140007e80  mov     rax, [rax+10h]
0x140007e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e89  nop
0x140007e8a  mov     esi, 80004002h
0x140007e8f  mov     eax, esi
0x140007e91  mov     rbx, [rsp+28h+arg_0]
0x140007e96  mov     rsi, [rsp+28h+arg_10]
0x140007e9b  add     rsp, 20h
0x140007e9f  pop     rdi
0x140007ea0  retn
```
