# dllmain_crt_dispatch

- ea: `0x180001d90`
- end: `0x180001de0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f74`

## callees

- `0x180001d90`
- `0x180001de8`
- `0x180001ee8`
- `0x1800021b0`
- `0x1800021e0`

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
0x180001d90  sub     rsp, 28h
0x180001d94  test    edx, edx
0x180001d96  jz      short loc_180001DD1
0x180001d98  sub     edx, 1
0x180001d9b  jz      short loc_180001DC5
0x180001d9d  sub     edx, 1
0x180001da0  jz      short loc_180001DB8
0x180001da2  cmp     edx, 1
0x180001da5  jz      short loc_180001DB1
0x180001da7  mov     eax, 1
0x180001dac  add     rsp, 28h
0x180001db0  retn
0x180001db1  call    __scrt_dllmain_crt_thread_detach
0x180001db6  jmp     short loc_180001DBD
0x180001db8  call    __scrt_dllmain_crt_thread_attach
0x180001dbd  movzx   eax, al
0x180001dc0  add     rsp, 28h
0x180001dc4  retn
0x180001dc5  mov     rdx, r8
0x180001dc8  add     rsp, 28h
0x180001dcc  jmp     dllmain_crt_process_attach
0x180001dd1  test    r8, r8
0x180001dd4  setnz   cl
0x180001dd7  add     rsp, 28h
0x180001ddb  jmp     dllmain_crt_process_detach
```
