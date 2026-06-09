# dllmain_crt_dispatch

- ea: `0x180001240`
- end: `0x180001290`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001424`

## callees

- `0x180001240`
- `0x180001298`
- `0x180001398`
- `0x1800017f0`
- `0x180001820`

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
0x180001240  sub     rsp, 28h
0x180001244  test    edx, edx
0x180001246  jz      short loc_180001281
0x180001248  sub     edx, 1
0x18000124b  jz      short loc_180001275
0x18000124d  sub     edx, 1
0x180001250  jz      short loc_180001268
0x180001252  cmp     edx, 1
0x180001255  jz      short loc_180001261
0x180001257  mov     eax, 1
0x18000125c  add     rsp, 28h
0x180001260  retn
0x180001261  call    __scrt_dllmain_crt_thread_detach
0x180001266  jmp     short loc_18000126D
0x180001268  call    __scrt_dllmain_crt_thread_attach
0x18000126d  movzx   eax, al
0x180001270  add     rsp, 28h
0x180001274  retn
0x180001275  mov     rdx, r8
0x180001278  add     rsp, 28h
0x18000127c  jmp     dllmain_crt_process_attach
0x180001281  test    r8, r8
0x180001284  setnz   cl
0x180001287  add     rsp, 28h
0x18000128b  jmp     dllmain_crt_process_detach
```
