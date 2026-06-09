# dllmain_crt_dispatch

- ea: `0x180002940`
- end: `0x180002990`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002b24`

## callees

- `0x180002940`
- `0x180002998`
- `0x180002a98`
- `0x180002d84`
- `0x180002db4`

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
0x180002940  sub     rsp, 28h
0x180002944  test    edx, edx
0x180002946  jz      short loc_180002981
0x180002948  sub     edx, 1
0x18000294b  jz      short loc_180002975
0x18000294d  sub     edx, 1
0x180002950  jz      short loc_180002968
0x180002952  cmp     edx, 1
0x180002955  jz      short loc_180002961
0x180002957  mov     eax, 1
0x18000295c  add     rsp, 28h
0x180002960  retn
0x180002961  call    __scrt_dllmain_crt_thread_detach
0x180002966  jmp     short loc_18000296D
0x180002968  call    __scrt_dllmain_crt_thread_attach
0x18000296d  movzx   eax, al
0x180002970  add     rsp, 28h
0x180002974  retn
0x180002975  mov     rdx, r8
0x180002978  add     rsp, 28h
0x18000297c  jmp     dllmain_crt_process_attach
0x180002981  test    r8, r8
0x180002984  setnz   cl
0x180002987  add     rsp, 28h
0x18000298b  jmp     dllmain_crt_process_detach
```
