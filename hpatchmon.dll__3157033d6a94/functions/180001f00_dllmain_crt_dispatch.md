# dllmain_crt_dispatch

- ea: `0x180001f00`
- end: `0x180001f50`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800020e4`

## callees

- `0x180001f00`
- `0x180001f58`
- `0x180002058`
- `0x180002320`
- `0x180002350`

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
0x180001f00  sub     rsp, 28h
0x180001f04  test    edx, edx
0x180001f06  jz      short loc_180001F41
0x180001f08  sub     edx, 1
0x180001f0b  jz      short loc_180001F35
0x180001f0d  sub     edx, 1
0x180001f10  jz      short loc_180001F28
0x180001f12  cmp     edx, 1
0x180001f15  jz      short loc_180001F21
0x180001f17  mov     eax, 1
0x180001f1c  add     rsp, 28h
0x180001f20  retn
0x180001f21  call    __scrt_dllmain_crt_thread_detach
0x180001f26  jmp     short loc_180001F2D
0x180001f28  call    __scrt_dllmain_crt_thread_attach
0x180001f2d  movzx   eax, al
0x180001f30  add     rsp, 28h
0x180001f34  retn
0x180001f35  mov     rdx, r8
0x180001f38  add     rsp, 28h
0x180001f3c  jmp     dllmain_crt_process_attach
0x180001f41  test    r8, r8
0x180001f44  setnz   cl
0x180001f47  add     rsp, 28h
0x180001f4b  jmp     dllmain_crt_process_detach
```
