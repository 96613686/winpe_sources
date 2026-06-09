# dllmain_crt_dispatch

- ea: `0x180001410`
- end: `0x180001460`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015f4`

## callees

- `0x180001410`
- `0x180001468`
- `0x180001568`
- `0x180001868`
- `0x180001898`

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
0x180001410  sub     rsp, 28h
0x180001414  test    edx, edx
0x180001416  jz      short loc_180001451
0x180001418  sub     edx, 1
0x18000141b  jz      short loc_180001445
0x18000141d  sub     edx, 1
0x180001420  jz      short loc_180001438
0x180001422  cmp     edx, 1
0x180001425  jz      short loc_180001431
0x180001427  mov     eax, 1
0x18000142c  add     rsp, 28h
0x180001430  retn
0x180001431  call    __scrt_dllmain_crt_thread_detach
0x180001436  jmp     short loc_18000143D
0x180001438  call    __scrt_dllmain_crt_thread_attach
0x18000143d  movzx   eax, al
0x180001440  add     rsp, 28h
0x180001444  retn
0x180001445  mov     rdx, r8
0x180001448  add     rsp, 28h
0x18000144c  jmp     dllmain_crt_process_attach
0x180001451  test    r8, r8
0x180001454  setnz   cl
0x180001457  add     rsp, 28h
0x18000145b  jmp     dllmain_crt_process_detach
```
