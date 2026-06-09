# dllmain_crt_dispatch

- ea: `0x180001bf0`
- end: `0x180001c40`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001dd4`

## callees

- `0x180001bf0`
- `0x180001c48`
- `0x180001d48`
- `0x180002010`
- `0x180002040`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180001bf0  sub     rsp, 28h
0x180001bf4  test    edx, edx
0x180001bf6  jz      short loc_180001C31
0x180001bf8  sub     edx, 1
0x180001bfb  jz      short loc_180001C25
0x180001bfd  sub     edx, 1
0x180001c00  jz      short loc_180001C18
0x180001c02  cmp     edx, 1
0x180001c05  jz      short loc_180001C11
0x180001c07  mov     eax, 1
0x180001c0c  add     rsp, 28h
0x180001c10  retn
0x180001c11  call    __scrt_dllmain_crt_thread_detach
0x180001c16  jmp     short loc_180001C1D
0x180001c18  call    __scrt_dllmain_crt_thread_attach
0x180001c1d  movzx   eax, al
0x180001c20  add     rsp, 28h
0x180001c24  retn
0x180001c25  mov     rdx, r8
0x180001c28  add     rsp, 28h
0x180001c2c  jmp     dllmain_crt_process_attach
0x180001c31  test    r8, r8
0x180001c34  setnz   cl
0x180001c37  add     rsp, 28h
0x180001c3b  jmp     dllmain_crt_process_detach
```
