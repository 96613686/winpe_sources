# std::thread::_Invoke_std::tuple__lambda_4840845e56fa40d3de607244c2981607____0_

- ea: `0x18013ecb0`
- end: `0x18013ecf0`
- name: `std::thread::_Invoke_std::tuple__lambda_4840845e56fa40d3de607244c2981607____0_`
- size: `64`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1803130ec`
- `0x18032f050`
- `0x18032f140`

## import_xrefs

- `KERNEL32!WaitForThreadpoolIoCallbacks` at `0x18013ecc7`
- `KERNEL32!WaitForThreadpoolIoCallbacks` at `0x18013ecc7`
- `KERNEL32!CloseThreadpoolIo` at `0x18013ecd0`
- `KERNEL32!CloseThreadpoolIo` at `0x18013ecd0`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_4840845e56fa40d3de607244c2981607____0_(PTP_IO *a1)
{
  WaitForThreadpoolIoCallbacks(*a1, 0);
  CloseThreadpoolIo(*a1);
  Cnd_do_broadcast_at_thread_exit();
  operator delete(a1, (const struct std::nothrow_t *)8);
  return 0;
}

```

## disassembly

```asm
0x18013ecb0  push    rbx
0x18013ecb2  mov     eax, 20h
0x18013ecb7  call    _alloca_probe
0x18013ecbc  sub     rsp, rax
0x18013ecbf  mov     rbx, rcx
0x18013ecc2  xor     edx, edx; fCancelPendingCallbacks
0x18013ecc4  mov     rcx, [rcx]; pio
0x18013ecc7  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18013eccd  mov     rcx, [rbx]; pio
0x18013ecd0  call    cs:__imp_CloseThreadpoolIo
0x18013ecd6  call    _Cnd_do_broadcast_at_thread_exit
0x18013ecdb  mov     edx, 8; struct std::nothrow_t *
0x18013ece0  mov     rcx, rbx; void *
0x18013ece3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013ece8  xor     eax, eax
0x18013ecea  add     rsp, 20h
0x18013ecee  pop     rbx
0x18013ecef  retn
```
