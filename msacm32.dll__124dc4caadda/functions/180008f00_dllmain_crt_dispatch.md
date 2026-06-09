# dllmain_crt_dispatch

- ea: `0x180008f00`
- end: `0x180008f50`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800090e4`

## callees

- `0x180008f00`
- `0x180008f58`
- `0x180009058`
- `0x180009444`
- `0x180009474`

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
0x180008f00  sub     rsp, 28h
0x180008f04  test    edx, edx
0x180008f06  jz      short loc_180008F41
0x180008f08  sub     edx, 1
0x180008f0b  jz      short loc_180008F35
0x180008f0d  sub     edx, 1
0x180008f10  jz      short loc_180008F28
0x180008f12  cmp     edx, 1
0x180008f15  jz      short loc_180008F21
0x180008f17  mov     eax, 1
0x180008f1c  add     rsp, 28h
0x180008f20  retn
0x180008f21  call    __scrt_dllmain_crt_thread_detach
0x180008f26  jmp     short loc_180008F2D
0x180008f28  call    __scrt_dllmain_crt_thread_attach
0x180008f2d  movzx   eax, al
0x180008f30  add     rsp, 28h
0x180008f34  retn
0x180008f35  mov     rdx, r8
0x180008f38  add     rsp, 28h
0x180008f3c  jmp     dllmain_crt_process_attach
0x180008f41  test    r8, r8
0x180008f44  setnz   cl
0x180008f47  add     rsp, 28h
0x180008f4b  jmp     dllmain_crt_process_detach
```
