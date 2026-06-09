# dllmain_crt_dispatch

- ea: `0x18000b090`
- end: `0x18000b0e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b274`

## callees

- `0x18000b090`
- `0x18000b0e8`
- `0x18000b1e8`
- `0x18000b4c0`
- `0x18000b4f0`

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
0x18000b090  sub     rsp, 28h
0x18000b094  test    edx, edx
0x18000b096  jz      short loc_18000B0D1
0x18000b098  sub     edx, 1
0x18000b09b  jz      short loc_18000B0C5
0x18000b09d  sub     edx, 1
0x18000b0a0  jz      short loc_18000B0B8
0x18000b0a2  cmp     edx, 1
0x18000b0a5  jz      short loc_18000B0B1
0x18000b0a7  mov     eax, 1
0x18000b0ac  add     rsp, 28h
0x18000b0b0  retn
0x18000b0b1  call    __scrt_dllmain_crt_thread_detach
0x18000b0b6  jmp     short loc_18000B0BD
0x18000b0b8  call    __scrt_dllmain_crt_thread_attach
0x18000b0bd  movzx   eax, al
0x18000b0c0  add     rsp, 28h
0x18000b0c4  retn
0x18000b0c5  mov     rdx, r8
0x18000b0c8  add     rsp, 28h
0x18000b0cc  jmp     dllmain_crt_process_attach
0x18000b0d1  test    r8, r8
0x18000b0d4  setnz   cl
0x18000b0d7  add     rsp, 28h
0x18000b0db  jmp     dllmain_crt_process_detach
```
