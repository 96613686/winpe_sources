# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015570`
- end: `0x1800155ed`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015600`

## callees

- `0x180013520`
- `0x180013fd8`
- `0x180015570`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  __int64 v8; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_5075a55f_68ba_56f2_97e6_9b1cbfa2c5f2, v4, v5) )
  {
    *v6 = v7;
    CanCastTo = 0;
LABEL_5:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                v7 + 8,
                v8);
  if ( CanCastTo >= 0 )
    goto LABEL_5;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180015570  push    rbx
0x180015572  sub     rsp, 20h
0x180015576  mov     r10, rdx
0x180015579  mov     r9, rcx
0x18001557c  mov     qword ptr [r8], 0
0x180015583  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001558a  mov     rcx, r10
0x18001558d  call    InlineIsEqualGUID
0x180015592  test    eax, eax
0x180015594  jnz     short loc_1800155D0
0x180015596  lea     rdx, _GUID_5075a55f_68ba_56f2_97e6_9b1cbfa2c5f2
0x18001559d  call    InlineIsEqualGUID
0x1800155a2  test    eax, eax
0x1800155a4  jz      short loc_1800155AD
0x1800155a6  mov     [r8], r9
0x1800155a9  xor     ebx, ebx
0x1800155ab  jmp     short loc_1800155BF
0x1800155ad  lea     rcx, [r9+8]
0x1800155b1  mov     rdx, r10
0x1800155b4  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x1800155b9  mov     ebx, eax
0x1800155bb  test    eax, eax
0x1800155bd  js      short loc_1800155E4
0x1800155bf  mov     rcx, [r8]
0x1800155c2  mov     rax, [rcx]
0x1800155c5  mov     rax, [rax+8]
0x1800155c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ce  jmp     short loc_1800155E4
0x1800155d0  mov     [r8], r9
0x1800155d3  mov     rax, [r9]
0x1800155d6  mov     rcx, r9
0x1800155d9  mov     rax, [rax+8]
0x1800155dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e2  xor     ebx, ebx
0x1800155e4  mov     eax, ebx
0x1800155e6  add     rsp, 20h
0x1800155ea  pop     rbx
0x1800155eb  retn
```
