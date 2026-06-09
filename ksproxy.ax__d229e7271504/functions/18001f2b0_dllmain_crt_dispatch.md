# dllmain_crt_dispatch

- ea: `0x18001f2b0`
- end: `0x18001f300`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001f494`

## callees

- `0x18001f2b0`
- `0x18001f308`
- `0x18001f408`
- `0x18001f6f4`
- `0x18001f724`

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
0x18001f2b0  sub     rsp, 28h
0x18001f2b4  test    edx, edx
0x18001f2b6  jz      short loc_18001F2F1
0x18001f2b8  sub     edx, 1
0x18001f2bb  jz      short loc_18001F2E5
0x18001f2bd  sub     edx, 1
0x18001f2c0  jz      short loc_18001F2D8
0x18001f2c2  cmp     edx, 1
0x18001f2c5  jz      short loc_18001F2D1
0x18001f2c7  mov     eax, 1
0x18001f2cc  add     rsp, 28h
0x18001f2d0  retn
0x18001f2d1  call    __scrt_dllmain_crt_thread_detach
0x18001f2d6  jmp     short loc_18001F2DD
0x18001f2d8  call    __scrt_dllmain_crt_thread_attach
0x18001f2dd  movzx   eax, al
0x18001f2e0  add     rsp, 28h
0x18001f2e4  retn
0x18001f2e5  mov     rdx, r8
0x18001f2e8  add     rsp, 28h
0x18001f2ec  jmp     dllmain_crt_process_attach
0x18001f2f1  test    r8, r8
0x18001f2f4  setnz   cl
0x18001f2f7  add     rsp, 28h
0x18001f2fb  jmp     dllmain_crt_process_detach
```
