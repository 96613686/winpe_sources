# BiasHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<bool> *,Windows::Foundation::IAsyncOperationCompletedHandler<bool> *)

- ea: `0x180026bd4`
- end: `0x180026c59`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@_N@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@_N@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027400`
- `0x180027550`
- `0x18002784c`

## callees

- `0x18000683c`
- `0x180026bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180026c39`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180026c39`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180026c0b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180026c0b`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1>::CreateBias(
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppstm);
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
0x180026bd4  mov     [rsp+arg_0], rbx
0x180026bd9  push    rdi
0x180026bda  sub     rsp, 30h
0x180026bde  mov     qword ptr [rcx], 0
0x180026be5  mov     rdi, r8
0x180026be8  mov     dword ptr [rcx+8], 0
0x180026bef  mov     rbx, rcx
0x180026bf2  test    rdx, rdx
0x180026bf5  jz      short loc_180026C44
0x180026bf7  test    r9, r9
0x180026bfa  jz      short loc_180026C44
0x180026bfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026c01  mov     r8, rbx; ppstm
0x180026c04  mov     edx, 1; fDeleteOnRelease
0x180026c09  xor     ecx, ecx; hGlobal
0x180026c0b  call    cs:__imp_CreateStreamOnHGlobal
0x180026c11  mov     [rbx+8], eax
0x180026c14  test    eax, eax
0x180026c16  js      short loc_180026C4B
0x180026c18  mov     rcx, [rbx]; pStm
0x180026c1b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180026c22  mov     [rsp+38h+mshlflags], 1; mshlflags
0x180026c2a  xor     r9d, r9d; dwDestContext
0x180026c2d  mov     r8, rdi; pUnk
0x180026c30  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180026c39  call    cs:__imp_CoMarshalInterface
0x180026c3f  mov     [rbx+8], eax
0x180026c42  jmp     short loc_180026C4B
0x180026c44  mov     dword ptr [rcx+8], 80004002h
0x180026c4b  mov     rax, rbx
0x180026c4e  mov     rbx, [rsp+38h+arg_0]
0x180026c53  add     rsp, 30h
0x180026c57  pop     rdi
0x180026c58  retn
```
