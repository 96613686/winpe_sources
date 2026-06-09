# dllmain_crt_dispatch

- ea: `0x100127b0`
- end: `0x10012805`
- name: `dllmain_crt_dispatch`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x100129d8`

## callees

- `0x100127b0`
- `0x1001280b`
- `0x1001291b`
- `0x10012d15`
- `0x10012d3a`

## pseudocode

```c
int __stdcall dllmain_crt_dispatch(int a1, int a2, int a3)
{
  int result; // eax

  switch ( a2 )
  {
    case 0:
      return dllmain_crt_process_detach(a3 != 0);
    case 1:
      return dllmain_crt_process_attach(a1, a3);
    case 2:
      LOBYTE(result) = __scrt_dllmain_crt_thread_attach();
      break;
    case 3:
      LOBYTE(result) = __scrt_dllmain_crt_thread_detach();
      break;
    default:
      return 1;
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x100127b0  mov     edi, edi
0x100127b2  push    ebp
0x100127b3  mov     ebp, esp
0x100127b5  mov     eax, [ebp+arg_4]
0x100127b8  sub     eax, 0
0x100127bb  jz      short loc_100127F0
0x100127bd  sub     eax, 1
0x100127c0  jz      short loc_100127E2
0x100127c2  sub     eax, 1
0x100127c5  jz      short loc_100127D8
0x100127c7  sub     eax, 1
0x100127ca  jz      short loc_100127D1
0x100127cc  xor     eax, eax
0x100127ce  inc     eax
0x100127cf  jmp     short loc_10012801
0x100127d1  call    ___scrt_dllmain_crt_thread_detach
0x100127d6  jmp     short loc_100127DD
0x100127d8  call    ___scrt_dllmain_crt_thread_attach
0x100127dd  movzx   eax, al
0x100127e0  jmp     short loc_10012801
0x100127e2  push    [ebp+arg_8]
0x100127e5  push    [ebp+arg_0]
0x100127e8  call    dllmain_crt_process_attach
0x100127ed  pop     ecx
0x100127ee  jmp     short loc_10012800
0x100127f0  cmp     [ebp+arg_8], 0
0x100127f4  setnz   al
0x100127f7  movzx   eax, al
0x100127fa  push    eax
0x100127fb  call    dllmain_crt_process_detach
0x10012800  pop     ecx
0x10012801  pop     ebp
0x10012802  retn    0Ch
```
