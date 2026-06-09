# dllmain_crt_dispatch

- ea: `0x18001fee0`
- end: `0x18001ff30`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800200c4`

## callees

- `0x18001fee0`
- `0x18001ff38`
- `0x180020038`
- `0x180020430`
- `0x180020460`

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
0x18001fee0  sub     rsp, 28h
0x18001fee4  test    edx, edx
0x18001fee6  jz      short loc_18001FF21
0x18001fee8  sub     edx, 1
0x18001feeb  jz      short loc_18001FF15
0x18001feed  sub     edx, 1
0x18001fef0  jz      short loc_18001FF08
0x18001fef2  cmp     edx, 1
0x18001fef5  jz      short loc_18001FF01
0x18001fef7  mov     eax, 1
0x18001fefc  add     rsp, 28h
0x18001ff00  retn
0x18001ff01  call    __scrt_dllmain_crt_thread_detach
0x18001ff06  jmp     short loc_18001FF0D
0x18001ff08  call    __scrt_dllmain_crt_thread_attach
0x18001ff0d  movzx   eax, al
0x18001ff10  add     rsp, 28h
0x18001ff14  retn
0x18001ff15  mov     rdx, r8
0x18001ff18  add     rsp, 28h
0x18001ff1c  jmp     dllmain_crt_process_attach
0x18001ff21  test    r8, r8
0x18001ff24  setnz   cl
0x18001ff27  add     rsp, 28h
0x18001ff2b  jmp     dllmain_crt_process_detach
```
