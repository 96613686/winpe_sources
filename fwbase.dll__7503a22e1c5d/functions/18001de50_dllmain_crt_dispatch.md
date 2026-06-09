# dllmain_crt_dispatch

- ea: `0x18001de50`
- end: `0x18001dea0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e034`

## callees

- `0x18001de50`
- `0x18001dea8`
- `0x18001dfa8`
- `0x18001e280`
- `0x18001e2b0`

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
0x18001de50  sub     rsp, 28h
0x18001de54  test    edx, edx
0x18001de56  jz      short loc_18001DE91
0x18001de58  sub     edx, 1
0x18001de5b  jz      short loc_18001DE85
0x18001de5d  sub     edx, 1
0x18001de60  jz      short loc_18001DE78
0x18001de62  cmp     edx, 1
0x18001de65  jz      short loc_18001DE71
0x18001de67  mov     eax, 1
0x18001de6c  add     rsp, 28h
0x18001de70  retn
0x18001de71  call    __scrt_dllmain_crt_thread_detach
0x18001de76  jmp     short loc_18001DE7D
0x18001de78  call    __scrt_dllmain_crt_thread_attach
0x18001de7d  movzx   eax, al
0x18001de80  add     rsp, 28h
0x18001de84  retn
0x18001de85  mov     rdx, r8
0x18001de88  add     rsp, 28h
0x18001de8c  jmp     dllmain_crt_process_attach
0x18001de91  test    r8, r8
0x18001de94  setnz   cl
0x18001de97  add     rsp, 28h
0x18001de9b  jmp     dllmain_crt_process_detach
```
