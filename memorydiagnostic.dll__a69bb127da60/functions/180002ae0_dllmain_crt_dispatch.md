# dllmain_crt_dispatch

- ea: `0x180002ae0`
- end: `0x180002b30`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002cc4`

## callees

- `0x180002ae0`
- `0x180002b38`
- `0x180002c38`
- `0x180002f68`
- `0x180002f98`

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
0x180002ae0  sub     rsp, 28h
0x180002ae4  test    edx, edx
0x180002ae6  jz      short loc_180002B21
0x180002ae8  sub     edx, 1
0x180002aeb  jz      short loc_180002B15
0x180002aed  sub     edx, 1
0x180002af0  jz      short loc_180002B08
0x180002af2  cmp     edx, 1
0x180002af5  jz      short loc_180002B01
0x180002af7  mov     eax, 1
0x180002afc  add     rsp, 28h
0x180002b00  retn
0x180002b01  call    __scrt_dllmain_crt_thread_detach
0x180002b06  jmp     short loc_180002B0D
0x180002b08  call    __scrt_dllmain_crt_thread_attach
0x180002b0d  movzx   eax, al
0x180002b10  add     rsp, 28h
0x180002b14  retn
0x180002b15  mov     rdx, r8
0x180002b18  add     rsp, 28h
0x180002b1c  jmp     dllmain_crt_process_attach
0x180002b21  test    r8, r8
0x180002b24  setnz   cl
0x180002b27  add     rsp, 28h
0x180002b2b  jmp     dllmain_crt_process_detach
```
