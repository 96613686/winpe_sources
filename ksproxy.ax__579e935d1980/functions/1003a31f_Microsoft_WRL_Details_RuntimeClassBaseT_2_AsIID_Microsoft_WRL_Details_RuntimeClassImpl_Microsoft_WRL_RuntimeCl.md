# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Microsoft::WRL::FtmBase>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Microsoft::WRL::FtmBase>> *,_GUID const &,void * *)

- ea: `0x1003a31f`
- end: `0x1003a3a7`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PAVAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@PAVAppCapabilityAccessChangedEventArgs@2345@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PAVAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@PAVAppCapabilityAccessChangedEventArgs@2345@@Foundation@Windows@@VFtmBase@23@@23@@123@ABU_GUID@@PAPAX@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1003a2d0`

## callees

- `0x100140b0`
- `0x1002d510`
- `0x1003918d`
- `0x1003a31f`

## pseudocode

```c
int __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapability *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs *>,Microsoft::WRL::FtmBase>>>(
        int a1,
        const struct _GUID *a2,
        void **a3)
{
  int v5; // ecx
  int v6; // edi
  int CanCastTo; // eax

  *a3 = 0;
  if ( !InlineIsEqualGUID(a2, &_GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( InlineIsEqualGUID(v5, &_GUID_6d923c95_7b83_5f59_8883_f44175284898) )
    {
      *a3 = (void *)a1;
      v6 = 0;
    }
    else
    {
      CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(a1 + 4), a2, a3);
      v6 = -2147467262;
      if ( CanCastTo == -2147467262 )
        CanCastTo = -2147467262;
      if ( CanCastTo == -2147467262 )
        return v6;
      v6 = CanCastTo;
      if ( CanCastTo < 0 )
        return v6;
    }
    (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)*a3 + 4))(*(_DWORD *)(*(_DWORD *)*a3 + 4), *a3);
    return v6;
  }
  *a3 = (void *)a1;
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)a1 + 4))(*(_DWORD *)(*(_DWORD *)a1 + 4), a1);
  return 0;
}

```

## disassembly

```asm
0x1003a31f  mov     edi, edi
0x1003a321  push    ebp
0x1003a322  mov     ebp, esp
0x1003a324  push    ebx
0x1003a325  mov     ebx, [ebp+arg_0]
0x1003a328  push    esi
0x1003a329  push    edi
0x1003a32a  mov     edi, edx
0x1003a32c  mov     esi, ecx
0x1003a32e  mov     edx, offset __GUID_00000000_0000_0000_c000_000000000046
0x1003a333  mov     dword ptr [ebx], 0
0x1003a339  mov     ecx, edi
0x1003a33b  call    _InlineIsEqualGUID@8; InlineIsEqualGUID(x,x)
0x1003a340  test    eax, eax
0x1003a342  jnz     short loc_1003A38C
0x1003a344  mov     edx, offset __GUID_6d923c95_7b83_5f59_8883_f44175284898
0x1003a349  call    _InlineIsEqualGUID@8; InlineIsEqualGUID(x,x)
0x1003a34e  test    eax, eax
0x1003a350  jz      short loc_1003A358
0x1003a352  mov     [ebx], esi
0x1003a354  xor     edi, edi
0x1003a356  jmp     short loc_1003A376
0x1003a358  push    ebx; void **
0x1003a359  push    edi; struct _GUID *
0x1003a35a  lea     ecx, [esi+4]; this
0x1003a35d  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IAEJABU_GUID@@PAPAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x1003a362  mov     edi, 80004002h
0x1003a367  cmp     eax, edi
0x1003a369  cmovz   eax, edi
0x1003a36c  cmp     eax, edi
0x1003a36e  jz      short loc_1003A388
0x1003a370  mov     edi, eax
0x1003a372  test    eax, eax
0x1003a374  js      short loc_1003A388
0x1003a376  mov     ecx, [ebx]
0x1003a378  push    ecx
0x1003a379  mov     edx, [ecx]
0x1003a37b  mov     esi, [edx+4]
0x1003a37e  mov     ecx, esi; this
0x1003a380  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a386  call    esi
0x1003a388  mov     eax, edi
0x1003a38a  jmp     short loc_1003A3A0
0x1003a38c  mov     [ebx], esi
0x1003a38e  mov     eax, [esi]
0x1003a390  push    esi
0x1003a391  mov     esi, [eax+4]
0x1003a394  mov     ecx, esi; this
0x1003a396  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a39c  call    esi
0x1003a39e  xor     eax, eax
0x1003a3a0  pop     edi
0x1003a3a1  pop     esi
0x1003a3a2  pop     ebx
0x1003a3a3  pop     ebp
0x1003a3a4  retn    4
```
