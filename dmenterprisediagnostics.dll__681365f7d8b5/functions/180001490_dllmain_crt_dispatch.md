# dllmain_crt_dispatch

- ea: `0x180001490`
- end: `0x1800014e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001674`

## callees

- `0x180001490`
- `0x1800014e8`
- `0x1800015e8`
- `0x1800019dc`
- `0x180001a0c`

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
0x180001490  sub     rsp, 28h
0x180001494  test    edx, edx
0x180001496  jz      short loc_1800014D1
0x180001498  sub     edx, 1
0x18000149b  jz      short loc_1800014C5
0x18000149d  sub     edx, 1
0x1800014a0  jz      short loc_1800014B8
0x1800014a2  cmp     edx, 1
0x1800014a5  jz      short loc_1800014B1
0x1800014a7  mov     eax, 1
0x1800014ac  add     rsp, 28h
0x1800014b0  retn
0x1800014b1  call    __scrt_dllmain_crt_thread_detach
0x1800014b6  jmp     short loc_1800014BD
0x1800014b8  call    __scrt_dllmain_crt_thread_attach
0x1800014bd  movzx   eax, al
0x1800014c0  add     rsp, 28h
0x1800014c4  retn
0x1800014c5  mov     rdx, r8
0x1800014c8  add     rsp, 28h
0x1800014cc  jmp     dllmain_crt_process_attach
0x1800014d1  test    r8, r8
0x1800014d4  setnz   cl
0x1800014d7  add     rsp, 28h
0x1800014db  jmp     dllmain_crt_process_detach
```
