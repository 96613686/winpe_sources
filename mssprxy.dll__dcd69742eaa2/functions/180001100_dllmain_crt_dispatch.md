# dllmain_crt_dispatch

- ea: `0x180001100`
- end: `0x180001150`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800012e4`

## callees

- `0x180001100`
- `0x180001158`
- `0x180001258`
- `0x180001628`
- `0x180001658`

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
0x180001100  sub     rsp, 28h
0x180001104  test    edx, edx
0x180001106  jz      short loc_180001141
0x180001108  sub     edx, 1
0x18000110b  jz      short loc_180001135
0x18000110d  sub     edx, 1
0x180001110  jz      short loc_180001128
0x180001112  cmp     edx, 1
0x180001115  jz      short loc_180001121
0x180001117  mov     eax, 1
0x18000111c  add     rsp, 28h
0x180001120  retn
0x180001121  call    __scrt_dllmain_crt_thread_detach
0x180001126  jmp     short loc_18000112D
0x180001128  call    __scrt_dllmain_crt_thread_attach
0x18000112d  movzx   eax, al
0x180001130  add     rsp, 28h
0x180001134  retn
0x180001135  mov     rdx, r8
0x180001138  add     rsp, 28h
0x18000113c  jmp     dllmain_crt_process_attach
0x180001141  test    r8, r8
0x180001144  setnz   cl
0x180001147  add     rsp, 28h
0x18000114b  jmp     dllmain_crt_process_detach
```
