# dllmain_crt_dispatch

- ea: `0x1800010a0`
- end: `0x1800010f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001284`

## callees

- `0x1800010a0`
- `0x1800010f8`
- `0x1800011f8`
- `0x180001620`
- `0x180001650`

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
0x1800010a0  sub     rsp, 28h
0x1800010a4  test    edx, edx
0x1800010a6  jz      short loc_1800010E1
0x1800010a8  sub     edx, 1
0x1800010ab  jz      short loc_1800010D5
0x1800010ad  sub     edx, 1
0x1800010b0  jz      short loc_1800010C8
0x1800010b2  cmp     edx, 1
0x1800010b5  jz      short loc_1800010C1
0x1800010b7  mov     eax, 1
0x1800010bc  add     rsp, 28h
0x1800010c0  retn
0x1800010c1  call    __scrt_dllmain_crt_thread_detach
0x1800010c6  jmp     short loc_1800010CD
0x1800010c8  call    __scrt_dllmain_crt_thread_attach
0x1800010cd  movzx   eax, al
0x1800010d0  add     rsp, 28h
0x1800010d4  retn
0x1800010d5  mov     rdx, r8
0x1800010d8  add     rsp, 28h
0x1800010dc  jmp     dllmain_crt_process_attach
0x1800010e1  test    r8, r8
0x1800010e4  setnz   cl
0x1800010e7  add     rsp, 28h
0x1800010eb  jmp     dllmain_crt_process_detach
```
