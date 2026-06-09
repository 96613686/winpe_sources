# dllmain_crt_dispatch

- ea: `0x180009c40`
- end: `0x180009c90`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009e24`

## callees

- `0x180009c40`
- `0x180009c98`
- `0x180009d98`
- `0x18000a194`
- `0x18000a1c4`

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
0x180009c40  sub     rsp, 28h
0x180009c44  test    edx, edx
0x180009c46  jz      short loc_180009C81
0x180009c48  sub     edx, 1
0x180009c4b  jz      short loc_180009C75
0x180009c4d  sub     edx, 1
0x180009c50  jz      short loc_180009C68
0x180009c52  cmp     edx, 1
0x180009c55  jz      short loc_180009C61
0x180009c57  mov     eax, 1
0x180009c5c  add     rsp, 28h
0x180009c60  retn
0x180009c61  call    __scrt_dllmain_crt_thread_detach
0x180009c66  jmp     short loc_180009C6D
0x180009c68  call    __scrt_dllmain_crt_thread_attach
0x180009c6d  movzx   eax, al
0x180009c70  add     rsp, 28h
0x180009c74  retn
0x180009c75  mov     rdx, r8
0x180009c78  add     rsp, 28h
0x180009c7c  jmp     dllmain_crt_process_attach
0x180009c81  test    r8, r8
0x180009c84  setnz   cl
0x180009c87  add     rsp, 28h
0x180009c8b  jmp     dllmain_crt_process_detach
```
