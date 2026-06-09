# ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800104a0`
- end: `0x180010534`
- name: `?Invoke@?$IDispatchImpl@UIIasComponent@@$1?_GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B$1?_GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010020`
- `0x1800104a0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct ITypeInfo *v11; // rcx
  __int64 result; // rax

  v11 = qword_1800242B8;
  if ( !qword_1800242B8 || (result = 0, !qword_1800242C8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI((ATL::CComTypeInfoHolder *)qword_1800242B8, a4);
    v11 = qword_1800242B8;
  }
  if ( v11 )
    return ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))v11->lpVtbl->Invoke)(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x1800104a0  mov     [rsp+arg_0], rbx
0x1800104a5  push    rdi
0x1800104a6  sub     rsp, 50h
0x1800104aa  mov     rdi, rcx
0x1800104ad  mov     ebx, edx
0x1800104af  mov     rcx, cs:qword_1800242B8; this
0x1800104b6  test    rcx, rcx
0x1800104b9  jz      short loc_1800104C6
0x1800104bb  xor     eax, eax
0x1800104bd  cmp     cs:qword_1800242C8, rax
0x1800104c4  jnz     short loc_1800104D5
0x1800104c6  mov     edx, r9d; unsigned int
0x1800104c9  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800104ce  mov     rcx, cs:qword_1800242B8
0x1800104d5  test    rcx, rcx
0x1800104d8  jz      short loc_180010529
0x1800104da  mov     rdx, [rsp+58h+arg_40]
0x1800104e2  mov     r8d, ebx
0x1800104e5  mov     rax, [rcx]
0x1800104e8  movzx   r9d, [rsp+58h+arg_20]
0x1800104f1  mov     [rsp+58h+var_20], rdx
0x1800104f6  mov     rdx, [rsp+58h+arg_38]
0x1800104fe  mov     rax, [rax+58h]
0x180010502  mov     [rsp+58h+var_28], rdx
0x180010507  mov     rdx, [rsp+58h+arg_30]
0x18001050f  mov     [rsp+58h+var_30], rdx
0x180010514  mov     rdx, [rsp+58h+arg_28]
0x18001051c  mov     [rsp+58h+var_38], rdx
0x180010521  mov     rdx, rdi
0x180010524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010529  mov     rbx, [rsp+58h+arg_0]
0x18001052e  add     rsp, 50h
0x180010532  pop     rdi
0x180010533  retn
```
