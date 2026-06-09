# dllmain_crt_dispatch

- ea: `0x1800027a0`
- end: `0x1800027f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002984`

## callees

- `0x1800027a0`
- `0x1800027f8`
- `0x1800028f8`
- `0x180002bc0`
- `0x180002bf0`

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
0x1800027a0  sub     rsp, 28h
0x1800027a4  test    edx, edx
0x1800027a6  jz      short loc_1800027E1
0x1800027a8  sub     edx, 1
0x1800027ab  jz      short loc_1800027D5
0x1800027ad  sub     edx, 1
0x1800027b0  jz      short loc_1800027C8
0x1800027b2  cmp     edx, 1
0x1800027b5  jz      short loc_1800027C1
0x1800027b7  mov     eax, 1
0x1800027bc  add     rsp, 28h
0x1800027c0  retn
0x1800027c1  call    __scrt_dllmain_crt_thread_detach
0x1800027c6  jmp     short loc_1800027CD
0x1800027c8  call    __scrt_dllmain_crt_thread_attach
0x1800027cd  movzx   eax, al
0x1800027d0  add     rsp, 28h
0x1800027d4  retn
0x1800027d5  mov     rdx, r8
0x1800027d8  add     rsp, 28h
0x1800027dc  jmp     dllmain_crt_process_attach
0x1800027e1  test    r8, r8
0x1800027e4  setnz   cl
0x1800027e7  add     rsp, 28h
0x1800027eb  jmp     dllmain_crt_process_detach
```
