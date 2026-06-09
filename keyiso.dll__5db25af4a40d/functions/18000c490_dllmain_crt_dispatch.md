# dllmain_crt_dispatch

- ea: `0x18000c490`
- end: `0x18000c4e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c674`

## callees

- `0x18000c490`
- `0x18000c4e8`
- `0x18000c5e8`
- `0x18000c880`
- `0x18000c8b0`

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
0x18000c490  sub     rsp, 28h
0x18000c494  test    edx, edx
0x18000c496  jz      short loc_18000C4D1
0x18000c498  sub     edx, 1
0x18000c49b  jz      short loc_18000C4C5
0x18000c49d  sub     edx, 1
0x18000c4a0  jz      short loc_18000C4B8
0x18000c4a2  cmp     edx, 1
0x18000c4a5  jz      short loc_18000C4B1
0x18000c4a7  mov     eax, 1
0x18000c4ac  add     rsp, 28h
0x18000c4b0  retn
0x18000c4b1  call    __scrt_dllmain_crt_thread_detach
0x18000c4b6  jmp     short loc_18000C4BD
0x18000c4b8  call    __scrt_dllmain_crt_thread_attach
0x18000c4bd  movzx   eax, al
0x18000c4c0  add     rsp, 28h
0x18000c4c4  retn
0x18000c4c5  mov     rdx, r8
0x18000c4c8  add     rsp, 28h
0x18000c4cc  jmp     dllmain_crt_process_attach
0x18000c4d1  test    r8, r8
0x18000c4d4  setnz   cl
0x18000c4d7  add     rsp, 28h
0x18000c4db  jmp     dllmain_crt_process_detach
```
