# dllmain_crt_dispatch

- ea: `0x180001090`
- end: `0x1800010e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001274`

## callees

- `0x180001090`
- `0x1800010e8`
- `0x1800011e8`
- `0x1800015d4`
- `0x180001604`

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
0x180001090  sub     rsp, 28h
0x180001094  test    edx, edx
0x180001096  jz      short loc_1800010D1
0x180001098  sub     edx, 1
0x18000109b  jz      short loc_1800010C5
0x18000109d  sub     edx, 1
0x1800010a0  jz      short loc_1800010B8
0x1800010a2  cmp     edx, 1
0x1800010a5  jz      short loc_1800010B1
0x1800010a7  mov     eax, 1
0x1800010ac  add     rsp, 28h
0x1800010b0  retn
0x1800010b1  call    __scrt_dllmain_crt_thread_detach
0x1800010b6  jmp     short loc_1800010BD
0x1800010b8  call    __scrt_dllmain_crt_thread_attach
0x1800010bd  movzx   eax, al
0x1800010c0  add     rsp, 28h
0x1800010c4  retn
0x1800010c5  mov     rdx, r8
0x1800010c8  add     rsp, 28h
0x1800010cc  jmp     dllmain_crt_process_attach
0x1800010d1  test    r8, r8
0x1800010d4  setnz   cl
0x1800010d7  add     rsp, 28h
0x1800010db  jmp     dllmain_crt_process_detach
```
