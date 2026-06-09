# dllmain_crt_dispatch

- ea: `0x18000f6a0`
- end: `0x18000f6f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f884`

## callees

- `0x18000f6a0`
- `0x18000f6f8`
- `0x18000f7f8`
- `0x18000fac0`
- `0x18000faf0`

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
0x18000f6a0  sub     rsp, 28h
0x18000f6a4  test    edx, edx
0x18000f6a6  jz      short loc_18000F6E1
0x18000f6a8  sub     edx, 1
0x18000f6ab  jz      short loc_18000F6D5
0x18000f6ad  sub     edx, 1
0x18000f6b0  jz      short loc_18000F6C8
0x18000f6b2  cmp     edx, 1
0x18000f6b5  jz      short loc_18000F6C1
0x18000f6b7  mov     eax, 1
0x18000f6bc  add     rsp, 28h
0x18000f6c0  retn
0x18000f6c1  call    __scrt_dllmain_crt_thread_detach
0x18000f6c6  jmp     short loc_18000F6CD
0x18000f6c8  call    __scrt_dllmain_crt_thread_attach
0x18000f6cd  movzx   eax, al
0x18000f6d0  add     rsp, 28h
0x18000f6d4  retn
0x18000f6d5  mov     rdx, r8
0x18000f6d8  add     rsp, 28h
0x18000f6dc  jmp     dllmain_crt_process_attach
0x18000f6e1  test    r8, r8
0x18000f6e4  setnz   cl
0x18000f6e7  add     rsp, 28h
0x18000f6eb  jmp     dllmain_crt_process_detach
```
