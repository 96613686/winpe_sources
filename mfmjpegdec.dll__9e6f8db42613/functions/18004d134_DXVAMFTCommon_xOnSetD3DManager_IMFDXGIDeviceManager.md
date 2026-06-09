# DXVAMFTCommon::xOnSetD3DManager(IMFDXGIDeviceManager *)

- ea: `0x18004d134`
- end: `0x18004d1ad`
- name: `?xOnSetD3DManager@DXVAMFTCommon@@QEAAJPEAUIMFDXGIDeviceManager@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, struct IMFDXGIDeviceManager *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800425f0`
- `0x18004d1c0`

## callees

- `0x180020598`
- `0x1800488d8`
- `0x18004d134`
- `0x18004d23c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall DXVAMFTCommon::xOnSetD3DManager(DXVAMFTCommon *this, struct IMFDXGIDeviceManager *a2)
{
  __int64 *v3; // rsi
  __int64 v4; // rcx
  _QWORD *v6; // rbx

  v3 = (__int64 *)((char *)this + 400);
  v4 = *((_QWORD *)this + 50);
  v6 = (_QWORD *)((char *)this + 416);
  if ( v4 && *v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
    *v6 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
  }
  Microsoft::WRL::ComPtr<IMFDXGIDeviceManager>::operator=(v3, a2);
  if ( !a2 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
    *v6 = 0;
    *((_BYTE *)this + 16) = 0;
  }
  return DXVAMFTCommon::xReopenDeviceManager(this, 1);
}

```

## disassembly

```asm
0x18004d134  push    rbx
0x18004d136  push    rbp
0x18004d137  push    rsi
0x18004d138  push    rdi
0x18004d139  sub     rsp, 28h
0x18004d13d  mov     rdi, rcx
0x18004d140  lea     rsi, [rcx+190h]
0x18004d147  mov     rcx, [rsi]
0x18004d14a  mov     rbp, rdx
0x18004d14d  lea     rbx, [rdi+1A0h]
0x18004d154  test    rcx, rcx
0x18004d157  jz      short loc_18004D17C
0x18004d159  mov     rdx, [rbx]
0x18004d15c  test    rdx, rdx
0x18004d15f  jz      short loc_18004D17C
0x18004d161  mov     rax, [rcx]
0x18004d164  mov     rax, [rax+18h]
0x18004d168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d16d  mov     rcx, rsi
0x18004d170  mov     qword ptr [rbx], 0
0x18004d177  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d17c  mov     rdx, rbp
0x18004d17f  mov     rcx, rsi
0x18004d182  call    ??4?$ComPtr@UIMFDXGIDeviceManager@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFDXGIDeviceManager@@@Z; Microsoft::WRL::ComPtr<IMFDXGIDeviceManager>::operator=(IMFDXGIDeviceManager *)
0x18004d187  test    rbp, rbp
0x18004d18a  jnz     short loc_18004D19B
0x18004d18c  mov     rcx, rsi
0x18004d18f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d194  mov     [rbx], rbp
0x18004d197  mov     [rdi+10h], bpl
0x18004d19b  mov     dl, 1; bool
0x18004d19d  mov     rcx, rdi; this
0x18004d1a0  add     rsp, 28h
0x18004d1a4  pop     rdi
0x18004d1a5  pop     rsi
0x18004d1a6  pop     rbp
0x18004d1a7  pop     rbx
0x18004d1a8  jmp     ?xReopenDeviceManager@DXVAMFTCommon@@AEAAJ_N@Z; DXVAMFTCommon::xReopenDeviceManager(bool)
```
