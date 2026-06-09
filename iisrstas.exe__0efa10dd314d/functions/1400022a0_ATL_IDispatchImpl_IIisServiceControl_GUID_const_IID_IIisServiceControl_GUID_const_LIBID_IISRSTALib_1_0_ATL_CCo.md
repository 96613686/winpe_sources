# ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1400022a0`
- end: `0x140002307`
- name: `?GetTypeInfo@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400020ec`
- `0x1400022a0`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  *a4 = 0;
  result = 0;
  v6 = qword_14000A0A8;
  if ( !qword_14000A0A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(0, a3);
    v6 = qword_14000A0A8;
  }
  *a4 = v6;
  if ( qword_14000A0A8 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_14000A0A8->lpVtbl->AddRef)(qword_14000A0A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400022a0  push    rbx
0x1400022a2  sub     rsp, 20h
0x1400022a6  mov     rbx, r9
0x1400022a9  test    edx, edx
0x1400022ab  jz      short loc_1400022B4
0x1400022ad  mov     eax, 8002000Bh
0x1400022b2  jmp     short loc_140002301
0x1400022b4  test    rbx, rbx
0x1400022b7  jnz     short loc_1400022C0
0x1400022b9  mov     eax, 80004003h
0x1400022be  jmp     short loc_140002301
0x1400022c0  mov     qword ptr [r9], 0
0x1400022c7  xor     eax, eax
0x1400022c9  mov     rcx, cs:qword_14000A0A8; this
0x1400022d0  test    rcx, rcx
0x1400022d3  jnz     short loc_1400022E4
0x1400022d5  mov     edx, r8d; unsigned int
0x1400022d8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1400022dd  mov     rcx, cs:qword_14000A0A8
0x1400022e4  mov     [rbx], rcx
0x1400022e7  mov     rcx, cs:qword_14000A0A8
0x1400022ee  test    rcx, rcx
0x1400022f1  jz      short loc_140002301
0x1400022f3  mov     rax, [rcx]
0x1400022f6  mov     rax, [rax+8]
0x1400022fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022ff  xor     eax, eax
0x140002301  add     rsp, 20h
0x140002305  pop     rbx
0x140002306  retn
```
