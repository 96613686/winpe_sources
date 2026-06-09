# dllmain_crt_dispatch

- ea: `0x180001970`
- end: `0x1800019c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b54`

## callees

- `0x180001970`
- `0x1800019c8`
- `0x180001ac8`
- `0x180001dd8`
- `0x180001e08`

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
0x180001970  sub     rsp, 28h
0x180001974  test    edx, edx
0x180001976  jz      short loc_1800019B1
0x180001978  sub     edx, 1
0x18000197b  jz      short loc_1800019A5
0x18000197d  sub     edx, 1
0x180001980  jz      short loc_180001998
0x180001982  cmp     edx, 1
0x180001985  jz      short loc_180001991
0x180001987  mov     eax, 1
0x18000198c  add     rsp, 28h
0x180001990  retn
0x180001991  call    __scrt_dllmain_crt_thread_detach
0x180001996  jmp     short loc_18000199D
0x180001998  call    __scrt_dllmain_crt_thread_attach
0x18000199d  movzx   eax, al
0x1800019a0  add     rsp, 28h
0x1800019a4  retn
0x1800019a5  mov     rdx, r8
0x1800019a8  add     rsp, 28h
0x1800019ac  jmp     dllmain_crt_process_attach
0x1800019b1  test    r8, r8
0x1800019b4  setnz   cl
0x1800019b7  add     rsp, 28h
0x1800019bb  jmp     dllmain_crt_process_detach
```
