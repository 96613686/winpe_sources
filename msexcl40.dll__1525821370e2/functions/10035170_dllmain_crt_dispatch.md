# dllmain_crt_dispatch

- ea: `0x10035170`
- end: `0x100351c5`
- name: `dllmain_crt_dispatch`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x10035398`

## callees

- `0x10035170`
- `0x100351cb`
- `0x100352db`
- `0x10035600`
- `0x10035625`

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
0x10035170  mov     edi, edi
0x10035172  push    ebp
0x10035173  mov     ebp, esp
0x10035175  mov     eax, [ebp+arg_4]
0x10035178  sub     eax, 0
0x1003517b  jz      short loc_100351B0
0x1003517d  sub     eax, 1
0x10035180  jz      short loc_100351A2
0x10035182  sub     eax, 1
0x10035185  jz      short loc_10035198
0x10035187  sub     eax, 1
0x1003518a  jz      short loc_10035191
0x1003518c  xor     eax, eax
0x1003518e  inc     eax
0x1003518f  jmp     short loc_100351C1
0x10035191  call    ___scrt_dllmain_crt_thread_detach
0x10035196  jmp     short loc_1003519D
0x10035198  call    ___scrt_dllmain_crt_thread_attach
0x1003519d  movzx   eax, al
0x100351a0  jmp     short loc_100351C1
0x100351a2  push    [ebp+arg_8]
0x100351a5  push    [ebp+arg_0]
0x100351a8  call    dllmain_crt_process_attach
0x100351ad  pop     ecx
0x100351ae  jmp     short loc_100351C0
0x100351b0  cmp     [ebp+arg_8], 0
0x100351b4  setnz   al
0x100351b7  movzx   eax, al
0x100351ba  push    eax
0x100351bb  call    dllmain_crt_process_detach
0x100351c0  pop     ecx
0x100351c1  pop     ebp
0x100351c2  retn    0Ch
```
