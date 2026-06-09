# ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e1cc`
- end: `0x18000e298`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQPropertyBag@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000de70`

## callees

- `0x180002f08`
- `0x18000dc1c`
- `0x18000e1cc`
- `0x18000e7dc`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQPropertyBag>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CMSMQPropertyBag *v7; // rax
  CMSMQPropertyBag *v8; // rbx
  int v9; // eax
  unsigned int v10; // eax
  int v11; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQPropertyBag *)MmAllocate(0x38u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQPropertyBag::CMSMQPropertyBag(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = *((_DWORD *)v8 + 4);
    if ( v9 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 4) = v9 + 1;
    v10 = CMSMQPropertyBag::FinalConstruct(v8);
    v6 = v10;
    v11 = *((_DWORD *)v8 + 4);
    if ( v11 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 4) = v11 - 1;
    if ( v10 || (v6 = (**(__int64 (__fastcall ***)(CMSMQPropertyBag *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x18000e1cc  mov     [rsp+arg_0], rcx
0x18000e1d1  push    rbx
0x18000e1d2  push    rbp
0x18000e1d3  push    rsi
0x18000e1d4  push    rdi
0x18000e1d5  sub     rsp, 28h
0x18000e1d9  mov     rsi, r8
0x18000e1dc  mov     rbp, rdx
0x18000e1df  test    r8, r8
0x18000e1e2  jnz     short loc_18000E1EE
0x18000e1e4  mov     eax, 80004003h
0x18000e1e9  jmp     loc_18000E28F
0x18000e1ee  mov     qword ptr [r8], 0
0x18000e1f5  mov     edi, 8007000Eh
0x18000e1fa  mov     ecx, 38h ; '8'; unsigned __int64
0x18000e1ff  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e204  mov     rbx, rax
0x18000e207  mov     [rsp+48h+arg_0], rax
0x18000e20c  test    rax, rax
0x18000e20f  jz      short loc_18000E237
0x18000e211  mov     rcx, rax; this
0x18000e214  call    ??0CMSMQPropertyBag@@QEAA@XZ; CMSMQPropertyBag::CMSMQPropertyBag(void)
0x18000e219  lea     rax, ??_7?$CComObject@VCMSMQPropertyBag@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'}
0x18000e220  mov     [rbx], rax
0x18000e223  lea     rax, ??_7?$CComObject@VCMSMQPropertyBag@@@ATL@@6B?$IDispatchImpl@UIMSMQPropertyBag@@$1?IID_IMSMQPropertyBag@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e22a  mov     [rbx+8], rax
0x18000e22e  lock inc cs:dword_18002CFF8
0x18000e235  jmp     short loc_18000E239
0x18000e237  xor     ebx, ebx
0x18000e239  test    rbx, rbx
0x18000e23c  jz      short loc_18000E28D
0x18000e23e  mov     eax, [rbx+10h]
0x18000e241  cmp     eax, 7FFFFFFFh
0x18000e246  jz      short loc_18000E24D
0x18000e248  inc     eax
0x18000e24a  mov     [rbx+10h], eax
0x18000e24d  mov     rcx, rbx; this
0x18000e250  call    ?FinalConstruct@CMSMQPropertyBag@@QEAAJXZ; CMSMQPropertyBag::FinalConstruct(void)
0x18000e255  mov     edi, eax
0x18000e257  mov     ecx, [rbx+10h]
0x18000e25a  cmp     ecx, 7FFFFFFFh
0x18000e260  jz      short loc_18000E267
0x18000e262  dec     ecx
0x18000e264  mov     [rbx+10h], ecx
0x18000e267  test    eax, eax
0x18000e269  jnz     short loc_18000E285
0x18000e26b  mov     rax, [rbx]
0x18000e26e  mov     r8, rsi
0x18000e271  mov     rdx, rbp
0x18000e274  mov     rcx, rbx
0x18000e277  mov     rax, [rax]
0x18000e27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e27f  mov     edi, eax
0x18000e281  test    eax, eax
0x18000e283  jz      short loc_18000E28D
0x18000e285  mov     rcx, rbx; Block
0x18000e288  call    ??_G?$CComObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)
0x18000e28d  mov     eax, edi
0x18000e28f  add     rsp, 28h
0x18000e293  pop     rdi
0x18000e294  pop     rsi
0x18000e295  pop     rbp
0x18000e296  pop     rbx
0x18000e297  retn
```
