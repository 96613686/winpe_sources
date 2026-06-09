# ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1400034b0`
- end: `0x140003510`
- name: `?GetTypeInfo@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400031f4`
- `0x1400034b0`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_14000B068;
  result = 0;
  if ( !qword_14000B068 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(0, a3);
    v6 = qword_14000B068;
  }
  *a4 = v6;
  if ( qword_14000B068 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_14000B068->lpVtbl->AddRef)(qword_14000B068);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400034b0  push    rbx
0x1400034b2  sub     rsp, 20h
0x1400034b6  mov     rbx, r9
0x1400034b9  test    edx, edx
0x1400034bb  jz      short loc_1400034C4
0x1400034bd  mov     eax, 8002000Bh
0x1400034c2  jmp     short loc_14000350A
0x1400034c4  test    rbx, rbx
0x1400034c7  jnz     short loc_1400034D0
0x1400034c9  mov     eax, 80004003h
0x1400034ce  jmp     short loc_14000350A
0x1400034d0  mov     rcx, cs:qword_14000B068; this
0x1400034d7  xor     eax, eax
0x1400034d9  test    rcx, rcx
0x1400034dc  jnz     short loc_1400034ED
0x1400034de  mov     edx, r8d; unsigned int
0x1400034e1  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1400034e6  mov     rcx, cs:qword_14000B068
0x1400034ed  mov     [rbx], rcx
0x1400034f0  mov     rcx, cs:qword_14000B068
0x1400034f7  test    rcx, rcx
0x1400034fa  jz      short loc_14000350A
0x1400034fc  mov     rax, [rcx]
0x1400034ff  mov     rax, [rax+8]
0x140003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003508  xor     eax, eax
0x14000350a  add     rsp, 20h
0x14000350e  pop     rbx
0x14000350f  retn
```
