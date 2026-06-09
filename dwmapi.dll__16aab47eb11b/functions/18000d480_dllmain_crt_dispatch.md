# dllmain_crt_dispatch

- ea: `0x18000d480`
- end: `0x18000d4d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d664`

## callees

- `0x18000d150`
- `0x18000d180`
- `0x18000d480`
- `0x18000d4d8`
- `0x18000d5d8`

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
0x18000d480  sub     rsp, 28h
0x18000d484  test    edx, edx
0x18000d486  jz      short loc_18000D4C1
0x18000d488  sub     edx, 1
0x18000d48b  jz      short loc_18000D4B5
0x18000d48d  sub     edx, 1
0x18000d490  jz      short loc_18000D4A8
0x18000d492  cmp     edx, 1
0x18000d495  jz      short loc_18000D4A1
0x18000d497  mov     eax, 1
0x18000d49c  add     rsp, 28h
0x18000d4a0  retn
0x18000d4a1  call    __scrt_dllmain_crt_thread_detach
0x18000d4a6  jmp     short loc_18000D4AD
0x18000d4a8  call    __scrt_dllmain_crt_thread_attach
0x18000d4ad  movzx   eax, al
0x18000d4b0  add     rsp, 28h
0x18000d4b4  retn
0x18000d4b5  mov     rdx, r8
0x18000d4b8  add     rsp, 28h
0x18000d4bc  jmp     dllmain_crt_process_attach
0x18000d4c1  test    r8, r8
0x18000d4c4  setnz   cl
0x18000d4c7  add     rsp, 28h
0x18000d4cb  jmp     dllmain_crt_process_detach
```
