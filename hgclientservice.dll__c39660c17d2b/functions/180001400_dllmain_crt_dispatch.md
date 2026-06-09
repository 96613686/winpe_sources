# dllmain_crt_dispatch

- ea: `0x180001400`
- end: `0x180001450`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015e4`

## callees

- `0x180001400`
- `0x180001458`
- `0x180001558`
- `0x180001888`
- `0x1800018b8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 1;
    LOBYTE(result) = _scrt_dllmain_crt_thread_detach();
  }
  else
  {
    LOBYTE(result) = _scrt_dllmain_crt_thread_attach();
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x180001400  sub     rsp, 28h
0x180001404  test    edx, edx
0x180001406  jz      short loc_180001441
0x180001408  sub     edx, 1
0x18000140b  jz      short loc_180001435
0x18000140d  sub     edx, 1
0x180001410  jz      short loc_180001428
0x180001412  cmp     edx, 1
0x180001415  jz      short loc_180001421
0x180001417  mov     eax, 1
0x18000141c  add     rsp, 28h
0x180001420  retn
0x180001421  call    __scrt_dllmain_crt_thread_detach
0x180001426  jmp     short loc_18000142D
0x180001428  call    __scrt_dllmain_crt_thread_attach
0x18000142d  movzx   eax, al
0x180001430  add     rsp, 28h
0x180001434  retn
0x180001435  mov     rdx, r8
0x180001438  add     rsp, 28h
0x18000143c  jmp     dllmain_crt_process_attach
0x180001441  test    r8, r8
0x180001444  setnz   cl
0x180001447  add     rsp, 28h
0x18000144b  jmp     dllmain_crt_process_detach
```
