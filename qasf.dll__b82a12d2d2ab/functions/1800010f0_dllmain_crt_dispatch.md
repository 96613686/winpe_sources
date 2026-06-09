# dllmain_crt_dispatch

- ea: `0x1800010f0`
- end: `0x180001140`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800012d4`

## callees

- `0x1800010f0`
- `0x180001148`
- `0x180001248`
- `0x180001618`
- `0x180001648`

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
0x1800010f0  sub     rsp, 28h
0x1800010f4  test    edx, edx
0x1800010f6  jz      short loc_180001131
0x1800010f8  sub     edx, 1
0x1800010fb  jz      short loc_180001125
0x1800010fd  sub     edx, 1
0x180001100  jz      short loc_180001118
0x180001102  cmp     edx, 1
0x180001105  jz      short loc_180001111
0x180001107  mov     eax, 1
0x18000110c  add     rsp, 28h
0x180001110  retn
0x180001111  call    __scrt_dllmain_crt_thread_detach
0x180001116  jmp     short loc_18000111D
0x180001118  call    __scrt_dllmain_crt_thread_attach
0x18000111d  movzx   eax, al
0x180001120  add     rsp, 28h
0x180001124  retn
0x180001125  mov     rdx, r8
0x180001128  add     rsp, 28h
0x18000112c  jmp     dllmain_crt_process_attach
0x180001131  test    r8, r8
0x180001134  setnz   cl
0x180001137  add     rsp, 28h
0x18000113b  jmp     dllmain_crt_process_detach
```
