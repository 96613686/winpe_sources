# dllmain_crt_dispatch

- ea: `0x180003f90`
- end: `0x180003fe0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004174`

## callees

- `0x180003f90`
- `0x180003fe8`
- `0x1800040e8`
- `0x180004404`
- `0x180004434`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180003f90  sub     rsp, 28h
0x180003f94  test    edx, edx
0x180003f96  jz      short loc_180003FD1
0x180003f98  sub     edx, 1
0x180003f9b  jz      short loc_180003FC5
0x180003f9d  sub     edx, 1
0x180003fa0  jz      short loc_180003FB8
0x180003fa2  cmp     edx, 1
0x180003fa5  jz      short loc_180003FB1
0x180003fa7  mov     eax, 1
0x180003fac  add     rsp, 28h
0x180003fb0  retn
0x180003fb1  call    __scrt_dllmain_crt_thread_detach
0x180003fb6  jmp     short loc_180003FBD
0x180003fb8  call    __scrt_dllmain_crt_thread_attach
0x180003fbd  movzx   eax, al
0x180003fc0  add     rsp, 28h
0x180003fc4  retn
0x180003fc5  mov     rdx, r8
0x180003fc8  add     rsp, 28h
0x180003fcc  jmp     dllmain_crt_process_attach
0x180003fd1  test    r8, r8
0x180003fd4  setnz   cl
0x180003fd7  add     rsp, 28h
0x180003fdb  jmp     dllmain_crt_process_detach
```
