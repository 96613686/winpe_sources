# _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::_QueryInterface<IUnknown *>(IUnknown * const &)

- ea: `0x14000cca0`
- end: `0x14000cd3d`
- name: `??$_QueryInterface@PEAUIUnknown@@@?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIUnknown@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d110`

## callees

- `0x1400046bc`
- `0x140004eb4`
- `0x14000cca0`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::_QueryInterface<IUnknown *>(
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
    v4 = (**v3)(v3, &GUID_07f19951_ab28_11d2_8936_000000000000, &v8);
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
0x14000cca0  mov     r11, rsp
0x14000cca3  mov     [r11+8], rbx
0x14000cca7  mov     [r11+18h], rsi
0x14000ccab  push    rdi
0x14000ccac  sub     rsp, 20h
0x14000ccb0  mov     rdi, rcx
0x14000ccb3  mov     rcx, [rdx]
0x14000ccb6  test    rcx, rcx
0x14000ccb9  jz      short loc_14000CCFF
0x14000ccbb  mov     qword ptr [r11+10h], 0
0x14000ccc3  mov     rax, [rcx]
0x14000ccc6  lea     r8, [r11+10h]
0x14000ccca  lea     rdx, _GUID_07f19951_ab28_11d2_8936_000000000000
0x14000ccd1  mov     rax, [rax]
0x14000ccd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccd9  mov     esi, eax
0x14000ccdb  mov     rcx, rdi
0x14000ccde  test    eax, eax
0x14000cce0  jns     short loc_14000CCF0
0x14000cce2  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000cce7  mov     qword ptr [rdi], 0
0x14000ccee  jmp     short loc_14000CD2B
0x14000ccf0  mov     rbx, [rsp+28h+arg_8]
0x14000ccf5  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000ccfa  mov     [rdi], rbx
0x14000ccfd  jmp     short loc_14000CD2B
0x14000ccff  mov     rbx, [rdi]
0x14000cd02  test    rbx, rbx
0x14000cd05  jz      short loc_14000CD26
0x14000cd07  mov     qword ptr [rdi], 0
0x14000cd0e  mov     rcx, rdi
0x14000cd11  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x14000cd16  mov     rax, [rbx]
0x14000cd19  mov     rcx, rbx
0x14000cd1c  mov     rax, [rax+10h]
0x14000cd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd25  nop
0x14000cd26  mov     esi, 80004002h
0x14000cd2b  mov     eax, esi
0x14000cd2d  mov     rbx, [rsp+28h+arg_0]
0x14000cd32  mov     rsi, [rsp+28h+arg_10]
0x14000cd37  add     rsp, 20h
0x14000cd3b  pop     rdi
0x14000cd3c  retn
```
