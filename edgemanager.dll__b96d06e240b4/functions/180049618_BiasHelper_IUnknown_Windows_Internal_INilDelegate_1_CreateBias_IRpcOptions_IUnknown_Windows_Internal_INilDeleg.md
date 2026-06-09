# BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(IRpcOptions *,IUnknown *,Windows::Internal::INilDelegate *)

- ea: `0x180049618`
- end: `0x18004969d`
- name: `?CreateBias@?$BiasHelper@UIUnknown@@UINilDelegate@Internal@Windows@@$00@@SA?AV?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@PEAUIRpcOptions@@PEAUIUnknown@@PEAUINilDelegate@Internal@Windows@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049960`
- `0x180049b10`
- `0x180052880`
- `0x1800529d0`
- `0x180052c68`
- `0x180052de4`

## callees

- `0x18000b0ec`
- `0x180049618`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004964f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004964f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18004967d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18004967d`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<IUnknown,Windows::Internal::INilDelegate,1>::CreateBias(
        LPSTREAM *ppstm,
        __int64 a2,
        IUnknown *a3,
        __int64 a4)
{
  HRESULT StreamOnHGlobal; // eax

  *ppstm = 0;
  *((_DWORD *)ppstm + 2) = 0;
  if ( a2 && a4 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppstm);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
    *((_DWORD *)ppstm + 2) = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      *((_DWORD *)ppstm + 2) = CoMarshalInterface(*ppstm, &GUID_00000000_0000_0000_c000_000000000046, a3, 0, 0, 1u);
  }
  else
  {
    *((_DWORD *)ppstm + 2) = -2147467262;
  }
  return ppstm;
}

```

## disassembly

```asm
0x180049618  mov     [rsp+arg_0], rbx
0x18004961d  push    rdi
0x18004961e  sub     rsp, 30h
0x180049622  mov     qword ptr [rcx], 0
0x180049629  mov     rdi, r8
0x18004962c  mov     dword ptr [rcx+8], 0
0x180049633  mov     rbx, rcx
0x180049636  test    rdx, rdx
0x180049639  jz      short loc_180049688
0x18004963b  test    r9, r9
0x18004963e  jz      short loc_180049688
0x180049640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049645  mov     r8, rbx; ppstm
0x180049648  mov     edx, 1; fDeleteOnRelease
0x18004964d  xor     ecx, ecx; hGlobal
0x18004964f  call    cs:__imp_CreateStreamOnHGlobal
0x180049655  mov     [rbx+8], eax
0x180049658  test    eax, eax
0x18004965a  js      short loc_18004968F
0x18004965c  mov     rcx, [rbx]; pStm
0x18004965f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180049666  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18004966e  xor     r9d, r9d; dwDestContext
0x180049671  mov     r8, rdi; pUnk
0x180049674  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18004967d  call    cs:__imp_CoMarshalInterface
0x180049683  mov     [rbx+8], eax
0x180049686  jmp     short loc_18004968F
0x180049688  mov     dword ptr [rcx+8], 80004002h
0x18004968f  mov     rax, rbx
0x180049692  mov     rbx, [rsp+38h+arg_0]
0x180049697  add     rsp, 30h
0x18004969b  pop     rdi
0x18004969c  retn
```
