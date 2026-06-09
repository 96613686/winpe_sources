# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x1800169f0`
- end: `0x180016a88`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aec0`

## callees

- `0x1800169f0`
- `0x18001e118`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  _QWORD *v11; // r8
  __int64 v12; // r9
  __int64 v13; // r10

  v3 = 0;
  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_a4ed5c81_76c9_40bd_8be6_b1d90fb20ae7, v5, v6) )
    {
      *v8 = v9;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(v7, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, v8, v9)
        && !(unsigned int)InlineIsEqualGUID(v10, &GUID_00000003_0000_0000_c000_000000000046, v11, v12) )
      {
        return (unsigned int)-2147467262;
      }
      v9 = v13;
      *v11 = v13;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    return v3;
  }
  *v5 = v6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x1800169f0  push    rbx
0x1800169f2  sub     rsp, 20h
0x1800169f6  mov     r11, rdx
0x1800169f9  mov     r9, rcx
0x1800169fc  xor     ebx, ebx
0x1800169fe  mov     [r8], rbx
0x180016a01  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180016a08  mov     rcx, r11
0x180016a0b  call    InlineIsEqualGUID
0x180016a10  test    eax, eax
0x180016a12  jnz     short loc_180016A6D
0x180016a14  lea     rdx, _GUID_a4ed5c81_76c9_40bd_8be6_b1d90fb20ae7
0x180016a1b  call    InlineIsEqualGUID
0x180016a20  test    eax, eax
0x180016a22  jz      short loc_180016A29
0x180016a24  mov     [r8], r9
0x180016a27  jmp     short loc_180016A53
0x180016a29  lea     r10, [r9+8]
0x180016a2d  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180016a34  call    InlineIsEqualGUID
0x180016a39  test    eax, eax
0x180016a3b  jnz     short loc_180016A4D
0x180016a3d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180016a44  call    InlineIsEqualGUID
0x180016a49  test    eax, eax
0x180016a4b  jz      short loc_180016A64
0x180016a4d  mov     r9, r10
0x180016a50  mov     [r8], r10
0x180016a53  mov     rax, [r9]
0x180016a56  mov     rcx, r9
0x180016a59  mov     rax, [rax+8]
0x180016a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a62  jmp     short loc_180016A69
0x180016a64  mov     ebx, 80004002h
0x180016a69  mov     eax, ebx
0x180016a6b  jmp     short loc_180016A81
0x180016a6d  mov     [r8], r9
0x180016a70  mov     rax, [r9]
0x180016a73  mov     rcx, r9
0x180016a76  mov     rax, [rax+8]
0x180016a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a7f  xor     eax, eax
0x180016a81  add     rsp, 20h
0x180016a85  pop     rbx
0x180016a86  retn
```
