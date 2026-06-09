# dllmain_crt_dispatch

- ea: `0x1800011b0`
- end: `0x180001200`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001394`

## callees

- `0x1800011b0`
- `0x180001208`
- `0x180001308`
- `0x1800015d0`
- `0x180001600`

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
0x1800011b0  sub     rsp, 28h
0x1800011b4  test    edx, edx
0x1800011b6  jz      short loc_1800011F1
0x1800011b8  sub     edx, 1
0x1800011bb  jz      short loc_1800011E5
0x1800011bd  sub     edx, 1
0x1800011c0  jz      short loc_1800011D8
0x1800011c2  cmp     edx, 1
0x1800011c5  jz      short loc_1800011D1
0x1800011c7  mov     eax, 1
0x1800011cc  add     rsp, 28h
0x1800011d0  retn
0x1800011d1  call    __scrt_dllmain_crt_thread_detach
0x1800011d6  jmp     short loc_1800011DD
0x1800011d8  call    __scrt_dllmain_crt_thread_attach
0x1800011dd  movzx   eax, al
0x1800011e0  add     rsp, 28h
0x1800011e4  retn
0x1800011e5  mov     rdx, r8
0x1800011e8  add     rsp, 28h
0x1800011ec  jmp     dllmain_crt_process_attach
0x1800011f1  test    r8, r8
0x1800011f4  setnz   cl
0x1800011f7  add     rsp, 28h
0x1800011fb  jmp     dllmain_crt_process_detach
```
