# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Microsoft::WRL::FtmBase>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180044020`
- end: `0x1800440a6`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@PEAVAppCapabilityAccessChangedEventArgs@2345@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800440b0`

## callees

- `0x18001233c`
- `0x1800147d0`
- `0x180044020`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Microsoft::WRL::FtmBase>>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  _DWORD *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  _DWORD *v8; // r10
  unsigned int v9; // ebx
  int CanCastTo; // eax

  *a3 = 0;
  if ( InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( InlineIsEqualGUID(v3, &GUID_6d923c95_7b83_5f59_8883_f44175284898) )
  {
    *v6 = v7;
    v9 = 0;
LABEL_6:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return v9;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                v7 + 8,
                v8,
                v6);
  v9 = -2147467262;
  if ( CanCastTo != -2147467262 )
  {
    v9 = CanCastTo;
    if ( CanCastTo >= 0 )
      goto LABEL_6;
  }
  return v9;
}

```

## disassembly

```asm
0x180044020  push    rbx
0x180044022  sub     rsp, 20h
0x180044026  mov     r10, rdx
0x180044029  mov     qword ptr [r8], 0
0x180044030  mov     r9, rcx
0x180044033  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18004403a  mov     rcx, r10
0x18004403d  call    InlineIsEqualGUID
0x180044042  test    eax, eax
0x180044044  jnz     short loc_180044089
0x180044046  lea     rdx, _GUID_6d923c95_7b83_5f59_8883_f44175284898
0x18004404d  call    InlineIsEqualGUID
0x180044052  test    eax, eax
0x180044054  jz      short loc_18004405D
0x180044056  mov     [r8], r9
0x180044059  xor     ebx, ebx
0x18004405b  jmp     short loc_180044078
0x18004405d  lea     rcx, [r9+8]
0x180044061  mov     rdx, r10
0x180044064  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x180044069  mov     ebx, 80004002h
0x18004406e  cmp     eax, ebx
0x180044070  jz      short loc_18004409D
0x180044072  mov     ebx, eax
0x180044074  test    eax, eax
0x180044076  js      short loc_18004409D
0x180044078  mov     rcx, [r8]
0x18004407b  mov     rax, [rcx]
0x18004407e  mov     rax, [rax+8]
0x180044082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044087  jmp     short loc_18004409D
0x180044089  mov     [r8], r9
0x18004408c  mov     rcx, r9
0x18004408f  mov     rax, [r9]
0x180044092  mov     rax, [rax+8]
0x180044096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004409b  xor     ebx, ebx
0x18004409d  mov     eax, ebx
0x18004409f  add     rsp, 20h
0x1800440a3  pop     rbx
0x1800440a4  retn
```
