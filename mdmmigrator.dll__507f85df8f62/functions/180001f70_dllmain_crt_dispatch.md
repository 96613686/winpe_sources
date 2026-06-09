# dllmain_crt_dispatch

- ea: `0x180001f70`
- end: `0x180001fc0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002154`

## callees

- `0x180001f70`
- `0x180001fc8`
- `0x1800020c8`
- `0x180002390`
- `0x1800023c0`

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
0x180001f70  sub     rsp, 28h
0x180001f74  test    edx, edx
0x180001f76  jz      short loc_180001FB1
0x180001f78  sub     edx, 1
0x180001f7b  jz      short loc_180001FA5
0x180001f7d  sub     edx, 1
0x180001f80  jz      short loc_180001F98
0x180001f82  cmp     edx, 1
0x180001f85  jz      short loc_180001F91
0x180001f87  mov     eax, 1
0x180001f8c  add     rsp, 28h
0x180001f90  retn
0x180001f91  call    __scrt_dllmain_crt_thread_detach
0x180001f96  jmp     short loc_180001F9D
0x180001f98  call    __scrt_dllmain_crt_thread_attach
0x180001f9d  movzx   eax, al
0x180001fa0  add     rsp, 28h
0x180001fa4  retn
0x180001fa5  mov     rdx, r8
0x180001fa8  add     rsp, 28h
0x180001fac  jmp     dllmain_crt_process_attach
0x180001fb1  test    r8, r8
0x180001fb4  setnz   cl
0x180001fb7  add     rsp, 28h
0x180001fbb  jmp     dllmain_crt_process_detach
```
