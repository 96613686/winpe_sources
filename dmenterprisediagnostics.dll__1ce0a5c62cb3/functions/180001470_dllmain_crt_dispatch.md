# dllmain_crt_dispatch

- ea: `0x180001470`
- end: `0x1800014c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001654`

## callees

- `0x180001470`
- `0x1800014c8`
- `0x1800015c8`
- `0x1800019bc`
- `0x1800019ec`

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
0x180001470  sub     rsp, 28h
0x180001474  test    edx, edx
0x180001476  jz      short loc_1800014B1
0x180001478  sub     edx, 1
0x18000147b  jz      short loc_1800014A5
0x18000147d  sub     edx, 1
0x180001480  jz      short loc_180001498
0x180001482  cmp     edx, 1
0x180001485  jz      short loc_180001491
0x180001487  mov     eax, 1
0x18000148c  add     rsp, 28h
0x180001490  retn
0x180001491  call    __scrt_dllmain_crt_thread_detach
0x180001496  jmp     short loc_18000149D
0x180001498  call    __scrt_dllmain_crt_thread_attach
0x18000149d  movzx   eax, al
0x1800014a0  add     rsp, 28h
0x1800014a4  retn
0x1800014a5  mov     rdx, r8
0x1800014a8  add     rsp, 28h
0x1800014ac  jmp     dllmain_crt_process_attach
0x1800014b1  test    r8, r8
0x1800014b4  setnz   cl
0x1800014b7  add     rsp, 28h
0x1800014bb  jmp     dllmain_crt_process_detach
```
