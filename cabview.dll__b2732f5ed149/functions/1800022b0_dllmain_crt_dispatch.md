# dllmain_crt_dispatch

- ea: `0x1800022b0`
- end: `0x180002300`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002494`

## callees

- `0x1800022b0`
- `0x180002308`
- `0x180002408`
- `0x1800026dc`
- `0x18000270c`

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
0x1800022b0  sub     rsp, 28h
0x1800022b4  test    edx, edx
0x1800022b6  jz      short loc_1800022F1
0x1800022b8  sub     edx, 1
0x1800022bb  jz      short loc_1800022E5
0x1800022bd  sub     edx, 1
0x1800022c0  jz      short loc_1800022D8
0x1800022c2  cmp     edx, 1
0x1800022c5  jz      short loc_1800022D1
0x1800022c7  mov     eax, 1
0x1800022cc  add     rsp, 28h
0x1800022d0  retn
0x1800022d1  call    __scrt_dllmain_crt_thread_detach
0x1800022d6  jmp     short loc_1800022DD
0x1800022d8  call    __scrt_dllmain_crt_thread_attach
0x1800022dd  movzx   eax, al
0x1800022e0  add     rsp, 28h
0x1800022e4  retn
0x1800022e5  mov     rdx, r8
0x1800022e8  add     rsp, 28h
0x1800022ec  jmp     dllmain_crt_process_attach
0x1800022f1  test    r8, r8
0x1800022f4  setnz   cl
0x1800022f7  add     rsp, 28h
0x1800022fb  jmp     dllmain_crt_process_detach
```
