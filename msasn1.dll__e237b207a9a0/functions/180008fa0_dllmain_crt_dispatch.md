# dllmain_crt_dispatch

- ea: `0x180008fa0`
- end: `0x180008ff0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009184`

## callees

- `0x180008fa0`
- `0x180008ff8`
- `0x1800090f8`
- `0x1800094c8`
- `0x1800094f8`

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
0x180008fa0  sub     rsp, 28h
0x180008fa4  test    edx, edx
0x180008fa6  jz      short loc_180008FE1
0x180008fa8  sub     edx, 1
0x180008fab  jz      short loc_180008FD5
0x180008fad  sub     edx, 1
0x180008fb0  jz      short loc_180008FC8
0x180008fb2  cmp     edx, 1
0x180008fb5  jz      short loc_180008FC1
0x180008fb7  mov     eax, 1
0x180008fbc  add     rsp, 28h
0x180008fc0  retn
0x180008fc1  call    __scrt_dllmain_crt_thread_detach
0x180008fc6  jmp     short loc_180008FCD
0x180008fc8  call    __scrt_dllmain_crt_thread_attach
0x180008fcd  movzx   eax, al
0x180008fd0  add     rsp, 28h
0x180008fd4  retn
0x180008fd5  mov     rdx, r8
0x180008fd8  add     rsp, 28h
0x180008fdc  jmp     dllmain_crt_process_attach
0x180008fe1  test    r8, r8
0x180008fe4  setnz   cl
0x180008fe7  add     rsp, 28h
0x180008feb  jmp     dllmain_crt_process_detach
```
