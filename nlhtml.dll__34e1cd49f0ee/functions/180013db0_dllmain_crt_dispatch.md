# dllmain_crt_dispatch

- ea: `0x180013db0`
- end: `0x180013e00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180013f94`

## callees

- `0x180013db0`
- `0x180013e08`
- `0x180013f08`
- `0x180014224`
- `0x180014254`

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
0x180013db0  sub     rsp, 28h
0x180013db4  test    edx, edx
0x180013db6  jz      short loc_180013DF1
0x180013db8  sub     edx, 1
0x180013dbb  jz      short loc_180013DE5
0x180013dbd  sub     edx, 1
0x180013dc0  jz      short loc_180013DD8
0x180013dc2  cmp     edx, 1
0x180013dc5  jz      short loc_180013DD1
0x180013dc7  mov     eax, 1
0x180013dcc  add     rsp, 28h
0x180013dd0  retn
0x180013dd1  call    __scrt_dllmain_crt_thread_detach
0x180013dd6  jmp     short loc_180013DDD
0x180013dd8  call    __scrt_dllmain_crt_thread_attach
0x180013ddd  movzx   eax, al
0x180013de0  add     rsp, 28h
0x180013de4  retn
0x180013de5  mov     rdx, r8
0x180013de8  add     rsp, 28h
0x180013dec  jmp     dllmain_crt_process_attach
0x180013df1  test    r8, r8
0x180013df4  setnz   cl
0x180013df7  add     rsp, 28h
0x180013dfb  jmp     dllmain_crt_process_detach
```
