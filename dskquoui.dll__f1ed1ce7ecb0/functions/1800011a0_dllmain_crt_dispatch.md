# dllmain_crt_dispatch

- ea: `0x1800011a0`
- end: `0x1800011f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001384`

## callees

- `0x1800011a0`
- `0x1800011f8`
- `0x1800012f8`
- `0x18000169c`
- `0x1800016cc`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
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

```

## disassembly

```asm
0x1800011a0  sub     rsp, 28h
0x1800011a4  test    edx, edx
0x1800011a6  jz      short loc_1800011E1
0x1800011a8  sub     edx, 1
0x1800011ab  jz      short loc_1800011D5
0x1800011ad  sub     edx, 1
0x1800011b0  jz      short loc_1800011C8
0x1800011b2  cmp     edx, 1
0x1800011b5  jz      short loc_1800011C1
0x1800011b7  mov     eax, 1
0x1800011bc  add     rsp, 28h
0x1800011c0  retn
0x1800011c1  call    __scrt_dllmain_crt_thread_detach
0x1800011c6  jmp     short loc_1800011CD
0x1800011c8  call    __scrt_dllmain_crt_thread_attach
0x1800011cd  movzx   eax, al
0x1800011d0  add     rsp, 28h
0x1800011d4  retn
0x1800011d5  mov     rdx, r8
0x1800011d8  add     rsp, 28h
0x1800011dc  jmp     dllmain_crt_process_attach
0x1800011e1  test    r8, r8
0x1800011e4  setnz   cl
0x1800011e7  add     rsp, 28h
0x1800011eb  jmp     dllmain_crt_process_detach
```
