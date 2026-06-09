# dllmain_crt_dispatch

- ea: `0x18001b470`
- end: `0x18001b4c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b654`

## callees

- `0x18001b470`
- `0x18001b4c8`
- `0x18001b5c8`
- `0x18001b9c4`
- `0x18001b9f4`

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
0x18001b470  sub     rsp, 28h
0x18001b474  test    edx, edx
0x18001b476  jz      short loc_18001B4B1
0x18001b478  sub     edx, 1
0x18001b47b  jz      short loc_18001B4A5
0x18001b47d  sub     edx, 1
0x18001b480  jz      short loc_18001B498
0x18001b482  cmp     edx, 1
0x18001b485  jz      short loc_18001B491
0x18001b487  mov     eax, 1
0x18001b48c  add     rsp, 28h
0x18001b490  retn
0x18001b491  call    __scrt_dllmain_crt_thread_detach
0x18001b496  jmp     short loc_18001B49D
0x18001b498  call    __scrt_dllmain_crt_thread_attach
0x18001b49d  movzx   eax, al
0x18001b4a0  add     rsp, 28h
0x18001b4a4  retn
0x18001b4a5  mov     rdx, r8
0x18001b4a8  add     rsp, 28h
0x18001b4ac  jmp     dllmain_crt_process_attach
0x18001b4b1  test    r8, r8
0x18001b4b4  setnz   cl
0x18001b4b7  add     rsp, 28h
0x18001b4bb  jmp     dllmain_crt_process_detach
```
