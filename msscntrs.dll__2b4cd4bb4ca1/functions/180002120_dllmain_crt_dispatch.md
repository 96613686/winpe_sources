# dllmain_crt_dispatch

- ea: `0x180002120`
- end: `0x180002170`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002304`

## callees

- `0x180002120`
- `0x180002178`
- `0x180002278`
- `0x180002664`
- `0x180002694`

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
0x180002120  sub     rsp, 28h
0x180002124  test    edx, edx
0x180002126  jz      short loc_180002161
0x180002128  sub     edx, 1
0x18000212b  jz      short loc_180002155
0x18000212d  sub     edx, 1
0x180002130  jz      short loc_180002148
0x180002132  cmp     edx, 1
0x180002135  jz      short loc_180002141
0x180002137  mov     eax, 1
0x18000213c  add     rsp, 28h
0x180002140  retn
0x180002141  call    __scrt_dllmain_crt_thread_detach
0x180002146  jmp     short loc_18000214D
0x180002148  call    __scrt_dllmain_crt_thread_attach
0x18000214d  movzx   eax, al
0x180002150  add     rsp, 28h
0x180002154  retn
0x180002155  mov     rdx, r8
0x180002158  add     rsp, 28h
0x18000215c  jmp     dllmain_crt_process_attach
0x180002161  test    r8, r8
0x180002164  setnz   cl
0x180002167  add     rsp, 28h
0x18000216b  jmp     dllmain_crt_process_detach
```
