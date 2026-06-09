# _CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1_::operator()

- ea: `0x18004897c`
- end: `0x180048a7c`
- name: `_CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1_::operator()`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800483f8`

## callees

- `0x180020598`
- `0x180021cc4`
- `0x18004897c`
- `0x18004a11c`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1_::operator()(
        __int64 *a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v4; // r10
  __int64 v6; // rdx
  __int64 v7; // r14
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64 *, GUID *, __int64 *); // rdi
  __int64 *v15; // rbx
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v4 = a2;
  v6 = *a1;
  v7 = (unsigned int)v4;
  if ( !*(_QWORD *)(*(_QWORD *)(*a1 + 80) + 48 * v4) )
    return 1;
  v9 = *(_QWORD *)(v6 + 88) != 0 ? v4 : 0;
  v16 = 0;
  v10 = MFCreateTrackedDXGISurfaceBufferInternal(
          &GUID_696442be_a72e_4059_bc79_5b5c98040fad,
          *(struct IUnknown **)(*(_QWORD *)(v6 + 80) + 48 * v4),
          v9,
          6 * v4,
          (__int64)a3);
  if ( !v10 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a3;
    v12 = **v11;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v16);
    v10 = v12(v11, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v16);
    if ( !v10 )
    {
      v13 = v16;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v16 + 40LL);
      v15 = (__int64 *)(*(_QWORD *)(*a1 + 104) + 8 * v7);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
      v10 = v14(v13, &MF_D3D12_SYNCHRONIZATION_OBJECT, &GUID_09d0f835_92ff_4e53_8efa_40faa551f233, v15);
    }
  }
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v16);
  return v10;
}

```

## disassembly

```asm
0x18004897c  mov     [rsp+arg_8], rbx
0x180048981  mov     [rsp+arg_10], rsi
0x180048986  push    rdi
0x180048987  push    r14
0x180048989  push    r15
0x18004898b  sub     rsp, 30h
0x18004898f  mov     rdi, r8
0x180048992  mov     r10d, edx
0x180048995  mov     r15, rcx
0x180048998  mov     rdx, [rcx]
0x18004899b  mov     r14d, r10d
0x18004899e  lea     r9, [r10+r10*2]
0x1800489a2  add     r9, r9
0x1800489a5  mov     rax, [rdx+50h]
0x1800489a9  cmp     qword ptr [rax+r9*8], 0
0x1800489ae  jnz     short loc_1800489BA
0x1800489b0  mov     eax, 1
0x1800489b5  jmp     loc_180048A68
0x1800489ba  mov     rax, [rdx+58h]
0x1800489be  neg     rax
0x1800489c1  sbb     r8d, r8d
0x1800489c4  and     r8d, r10d; unsigned int
0x1800489c7  mov     [rsp+48h+arg_0], 0
0x1800489d0  mov     rdx, [rdx+50h]
0x1800489d4  mov     [rsp+48h+var_28], rdi; __int64
0x1800489d9  mov     rdx, [rdx+r9*8]; struct IUnknown *
0x1800489dd  lea     rcx, _GUID_696442be_a72e_4059_bc79_5b5c98040fad; struct _GUID *
0x1800489e4  call    MFCreateTrackedDXGISurfaceBufferInternal
0x1800489e9  mov     ebx, eax
0x1800489eb  test    eax, eax
0x1800489ed  jnz     short loc_180048A5C
0x1800489ef  mov     rdi, [rdi]
0x1800489f2  mov     rax, [rdi]
0x1800489f5  mov     rbx, [rax]
0x1800489f8  lea     rcx, [rsp+48h+arg_0]
0x1800489fd  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180048a02  lea     r8, [rsp+48h+arg_0]
0x180048a07  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x180048a0e  mov     rcx, rdi
0x180048a11  mov     rax, rbx
0x180048a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a19  mov     ebx, eax
0x180048a1b  test    eax, eax
0x180048a1d  jnz     short loc_180048A5C
0x180048a1f  mov     rsi, [rsp+48h+arg_0]
0x180048a24  mov     rax, [rsi]
0x180048a27  mov     rdi, [rax+28h]
0x180048a2b  mov     rdx, [r15]
0x180048a2e  mov     r8, [rdx+68h]
0x180048a32  lea     rbx, [r8+r14*8]
0x180048a36  mov     rcx, rbx
0x180048a39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a3e  mov     r9, rbx
0x180048a41  lea     r8, _GUID_09d0f835_92ff_4e53_8efa_40faa551f233
0x180048a48  lea     rdx, MF_D3D12_SYNCHRONIZATION_OBJECT
0x180048a4f  mov     rcx, rsi
0x180048a52  mov     rax, rdi
0x180048a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a5a  mov     ebx, eax
0x180048a5c  lea     rcx, [rsp+48h+arg_0]
0x180048a61  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180048a66  mov     eax, ebx
0x180048a68  mov     rbx, [rsp+48h+arg_8]
0x180048a6d  mov     rsi, [rsp+48h+arg_10]
0x180048a72  add     rsp, 30h
0x180048a76  pop     r15
0x180048a78  pop     r14
0x180048a7a  pop     rdi
0x180048a7b  retn
```
