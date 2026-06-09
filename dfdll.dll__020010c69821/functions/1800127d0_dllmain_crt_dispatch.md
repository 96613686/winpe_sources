# dllmain_crt_dispatch

- ea: `0x1800127d0`
- end: `0x180012820`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800129bc`

## callees

- `0x1800127d0`
- `0x180012820`
- `0x180012938`
- `0x180012d18`
- `0x180012d40`

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
    return dllmain_crt_process_attach();
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
0x1800127d0  sub     rsp, 28h
0x1800127d4  test    edx, edx
0x1800127d6  jz      short loc_180012811
0x1800127d8  sub     edx, 1
0x1800127db  jz      short loc_180012805
0x1800127dd  sub     edx, 1
0x1800127e0  jz      short loc_1800127F8
0x1800127e2  cmp     edx, 1
0x1800127e5  jz      short loc_1800127F1
0x1800127e7  mov     eax, 1
0x1800127ec  add     rsp, 28h
0x1800127f0  retn
0x1800127f1  call    __scrt_dllmain_crt_thread_detach
0x1800127f6  jmp     short loc_1800127FD
0x1800127f8  call    __scrt_dllmain_crt_thread_attach
0x1800127fd  movzx   eax, al
0x180012800  add     rsp, 28h
0x180012804  retn
0x180012805  mov     rdx, r8
0x180012808  add     rsp, 28h
0x18001280c  jmp     dllmain_crt_process_attach
0x180012811  test    r8, r8
0x180012814  setnz   cl
0x180012817  add     rsp, 28h
0x18001281b  jmp     dllmain_crt_process_detach
```
