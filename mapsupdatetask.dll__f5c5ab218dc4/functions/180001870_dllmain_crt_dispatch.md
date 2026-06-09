# dllmain_crt_dispatch

- ea: `0x180001870`
- end: `0x1800018c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a54`

## callees

- `0x180001870`
- `0x1800018c8`
- `0x1800019c8`
- `0x180001cd4`
- `0x180001d04`

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
0x180001870  sub     rsp, 28h
0x180001874  test    edx, edx
0x180001876  jz      short loc_1800018B1
0x180001878  sub     edx, 1
0x18000187b  jz      short loc_1800018A5
0x18000187d  sub     edx, 1
0x180001880  jz      short loc_180001898
0x180001882  cmp     edx, 1
0x180001885  jz      short loc_180001891
0x180001887  mov     eax, 1
0x18000188c  add     rsp, 28h
0x180001890  retn
0x180001891  call    __scrt_dllmain_crt_thread_detach
0x180001896  jmp     short loc_18000189D
0x180001898  call    __scrt_dllmain_crt_thread_attach
0x18000189d  movzx   eax, al
0x1800018a0  add     rsp, 28h
0x1800018a4  retn
0x1800018a5  mov     rdx, r8
0x1800018a8  add     rsp, 28h
0x1800018ac  jmp     dllmain_crt_process_attach
0x1800018b1  test    r8, r8
0x1800018b4  setnz   cl
0x1800018b7  add     rsp, 28h
0x1800018bb  jmp     dllmain_crt_process_detach
```
