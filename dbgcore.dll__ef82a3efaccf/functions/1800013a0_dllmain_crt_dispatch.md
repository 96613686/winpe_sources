# dllmain_crt_dispatch

- ea: `0x1800013a0`
- end: `0x1800013f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001584`

## callees

- `0x1800013a0`
- `0x1800013f8`
- `0x1800014f8`
- `0x1800017c0`
- `0x1800017f0`

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
0x1800013a0  sub     rsp, 28h
0x1800013a4  test    edx, edx
0x1800013a6  jz      short loc_1800013E1
0x1800013a8  sub     edx, 1
0x1800013ab  jz      short loc_1800013D5
0x1800013ad  sub     edx, 1
0x1800013b0  jz      short loc_1800013C8
0x1800013b2  cmp     edx, 1
0x1800013b5  jz      short loc_1800013C1
0x1800013b7  mov     eax, 1
0x1800013bc  add     rsp, 28h
0x1800013c0  retn
0x1800013c1  call    __scrt_dllmain_crt_thread_detach
0x1800013c6  jmp     short loc_1800013CD
0x1800013c8  call    __scrt_dllmain_crt_thread_attach
0x1800013cd  movzx   eax, al
0x1800013d0  add     rsp, 28h
0x1800013d4  retn
0x1800013d5  mov     rdx, r8
0x1800013d8  add     rsp, 28h
0x1800013dc  jmp     dllmain_crt_process_attach
0x1800013e1  test    r8, r8
0x1800013e4  setnz   cl
0x1800013e7  add     rsp, 28h
0x1800013eb  jmp     dllmain_crt_process_detach
```
