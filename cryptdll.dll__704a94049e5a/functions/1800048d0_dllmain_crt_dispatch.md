# dllmain_crt_dispatch

- ea: `0x1800048d0`
- end: `0x180004920`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004ab4`

## callees

- `0x1800048d0`
- `0x180004928`
- `0x180004a28`
- `0x180004df8`
- `0x180004e28`

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
0x1800048d0  sub     rsp, 28h
0x1800048d4  test    edx, edx
0x1800048d6  jz      short loc_180004911
0x1800048d8  sub     edx, 1
0x1800048db  jz      short loc_180004905
0x1800048dd  sub     edx, 1
0x1800048e0  jz      short loc_1800048F8
0x1800048e2  cmp     edx, 1
0x1800048e5  jz      short loc_1800048F1
0x1800048e7  mov     eax, 1
0x1800048ec  add     rsp, 28h
0x1800048f0  retn
0x1800048f1  call    __scrt_dllmain_crt_thread_detach
0x1800048f6  jmp     short loc_1800048FD
0x1800048f8  call    __scrt_dllmain_crt_thread_attach
0x1800048fd  movzx   eax, al
0x180004900  add     rsp, 28h
0x180004904  retn
0x180004905  mov     rdx, r8
0x180004908  add     rsp, 28h
0x18000490c  jmp     dllmain_crt_process_attach
0x180004911  test    r8, r8
0x180004914  setnz   cl
0x180004917  add     rsp, 28h
0x18000491b  jmp     dllmain_crt_process_detach
```
