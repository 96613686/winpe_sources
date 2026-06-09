# ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800102b0`
- end: `0x180010310`
- name: `?GetTypeInfo@?$IDispatchImpl@UIIasComponent@@$1?_GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B$1?_GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(__int64, int, LCID, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010020`
- `0x1800102b0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  __int64 result; // rax
  struct ITypeInfo *v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_1800242B8;
  result = 0;
  if ( !qword_1800242B8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(0, a3);
    v6 = qword_1800242B8;
  }
  *a4 = v6;
  if ( qword_1800242B8 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_1800242B8->lpVtbl->AddRef)(qword_1800242B8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800102b0  push    rbx
0x1800102b2  sub     rsp, 20h
0x1800102b6  mov     rbx, r9
0x1800102b9  test    edx, edx
0x1800102bb  jz      short loc_1800102C4
0x1800102bd  mov     eax, 8002000Bh
0x1800102c2  jmp     short loc_18001030A
0x1800102c4  test    rbx, rbx
0x1800102c7  jnz     short loc_1800102D0
0x1800102c9  mov     eax, 80004003h
0x1800102ce  jmp     short loc_18001030A
0x1800102d0  mov     rcx, cs:qword_1800242B8; this
0x1800102d7  xor     eax, eax
0x1800102d9  test    rcx, rcx
0x1800102dc  jnz     short loc_1800102ED
0x1800102de  mov     edx, r8d; unsigned int
0x1800102e1  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800102e6  mov     rcx, cs:qword_1800242B8
0x1800102ed  mov     [rbx], rcx
0x1800102f0  mov     rcx, cs:qword_1800242B8
0x1800102f7  test    rcx, rcx
0x1800102fa  jz      short loc_18001030A
0x1800102fc  mov     rax, [rcx]
0x1800102ff  mov     rax, [rax+8]
0x180010303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010308  xor     eax, eax
0x18001030a  add     rsp, 20h
0x18001030e  pop     rbx
0x18001030f  retn
```
