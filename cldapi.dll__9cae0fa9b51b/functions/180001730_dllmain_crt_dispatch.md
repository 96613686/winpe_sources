# dllmain_crt_dispatch

- ea: `0x180001730`
- end: `0x180001780`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001914`

## callees

- `0x180001730`
- `0x180001788`
- `0x180001888`
- `0x180001c58`
- `0x180001c88`

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
0x180001730  sub     rsp, 28h
0x180001734  test    edx, edx
0x180001736  jz      short loc_180001771
0x180001738  sub     edx, 1
0x18000173b  jz      short loc_180001765
0x18000173d  sub     edx, 1
0x180001740  jz      short loc_180001758
0x180001742  cmp     edx, 1
0x180001745  jz      short loc_180001751
0x180001747  mov     eax, 1
0x18000174c  add     rsp, 28h
0x180001750  retn
0x180001751  call    __scrt_dllmain_crt_thread_detach
0x180001756  jmp     short loc_18000175D
0x180001758  call    __scrt_dllmain_crt_thread_attach
0x18000175d  movzx   eax, al
0x180001760  add     rsp, 28h
0x180001764  retn
0x180001765  mov     rdx, r8
0x180001768  add     rsp, 28h
0x18000176c  jmp     dllmain_crt_process_attach
0x180001771  test    r8, r8
0x180001774  setnz   cl
0x180001777  add     rsp, 28h
0x18000177b  jmp     dllmain_crt_process_detach
```
