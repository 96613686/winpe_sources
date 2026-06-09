# dllmain_crt_dispatch

- ea: `0x180001180`
- end: `0x1800011d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001364`

## callees

- `0x180001180`
- `0x1800011d8`
- `0x1800012d8`
- `0x1800016d4`
- `0x180001704`

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
0x180001180  sub     rsp, 28h
0x180001184  test    edx, edx
0x180001186  jz      short loc_1800011C1
0x180001188  sub     edx, 1
0x18000118b  jz      short loc_1800011B5
0x18000118d  sub     edx, 1
0x180001190  jz      short loc_1800011A8
0x180001192  cmp     edx, 1
0x180001195  jz      short loc_1800011A1
0x180001197  mov     eax, 1
0x18000119c  add     rsp, 28h
0x1800011a0  retn
0x1800011a1  call    __scrt_dllmain_crt_thread_detach
0x1800011a6  jmp     short loc_1800011AD
0x1800011a8  call    __scrt_dllmain_crt_thread_attach
0x1800011ad  movzx   eax, al
0x1800011b0  add     rsp, 28h
0x1800011b4  retn
0x1800011b5  mov     rdx, r8
0x1800011b8  add     rsp, 28h
0x1800011bc  jmp     dllmain_crt_process_attach
0x1800011c1  test    r8, r8
0x1800011c4  setnz   cl
0x1800011c7  add     rsp, 28h
0x1800011cb  jmp     dllmain_crt_process_detach
```
