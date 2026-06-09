# dllmain_crt_dispatch

- ea: `0x1800011d0`
- end: `0x180001220`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013b4`

## callees

- `0x1800011d0`
- `0x180001228`
- `0x180001328`
- `0x180001640`
- `0x180001670`

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
0x1800011d0  sub     rsp, 28h
0x1800011d4  test    edx, edx
0x1800011d6  jz      short loc_180001211
0x1800011d8  sub     edx, 1
0x1800011db  jz      short loc_180001205
0x1800011dd  sub     edx, 1
0x1800011e0  jz      short loc_1800011F8
0x1800011e2  cmp     edx, 1
0x1800011e5  jz      short loc_1800011F1
0x1800011e7  mov     eax, 1
0x1800011ec  add     rsp, 28h
0x1800011f0  retn
0x1800011f1  call    __scrt_dllmain_crt_thread_detach
0x1800011f6  jmp     short loc_1800011FD
0x1800011f8  call    __scrt_dllmain_crt_thread_attach
0x1800011fd  movzx   eax, al
0x180001200  add     rsp, 28h
0x180001204  retn
0x180001205  mov     rdx, r8
0x180001208  add     rsp, 28h
0x18000120c  jmp     dllmain_crt_process_attach
0x180001211  test    r8, r8
0x180001214  setnz   cl
0x180001217  add     rsp, 28h
0x18000121b  jmp     dllmain_crt_process_detach
```
