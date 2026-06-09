# dllmain_crt_dispatch

- ea: `0x180001840`
- end: `0x180001890`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a24`

## callees

- `0x180001840`
- `0x180001898`
- `0x180001998`
- `0x180001d08`
- `0x180001d38`

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
0x180001840  sub     rsp, 28h
0x180001844  test    edx, edx
0x180001846  jz      short loc_180001881
0x180001848  sub     edx, 1
0x18000184b  jz      short loc_180001875
0x18000184d  sub     edx, 1
0x180001850  jz      short loc_180001868
0x180001852  cmp     edx, 1
0x180001855  jz      short loc_180001861
0x180001857  mov     eax, 1
0x18000185c  add     rsp, 28h
0x180001860  retn
0x180001861  call    __scrt_dllmain_crt_thread_detach
0x180001866  jmp     short loc_18000186D
0x180001868  call    __scrt_dllmain_crt_thread_attach
0x18000186d  movzx   eax, al
0x180001870  add     rsp, 28h
0x180001874  retn
0x180001875  mov     rdx, r8
0x180001878  add     rsp, 28h
0x18000187c  jmp     dllmain_crt_process_attach
0x180001881  test    r8, r8
0x180001884  setnz   cl
0x180001887  add     rsp, 28h
0x18000188b  jmp     dllmain_crt_process_detach
```
