# dllmain_crt_dispatch

- ea: `0x1003a7c0`
- end: `0x1003a815`
- name: `dllmain_crt_dispatch`
- size: `85`
- prototype: `int __stdcall(int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1003a9e8`

## callees

- `0x1003a7c0`
- `0x1003a81b`
- `0x1003a92b`
- `0x1003acd8`
- `0x1003acfd`

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
0x1003a7c0  mov     edi, edi
0x1003a7c2  push    ebp
0x1003a7c3  mov     ebp, esp
0x1003a7c5  mov     eax, [ebp+arg_4]
0x1003a7c8  sub     eax, 0
0x1003a7cb  jz      short loc_1003A800
0x1003a7cd  sub     eax, 1
0x1003a7d0  jz      short loc_1003A7F2
0x1003a7d2  sub     eax, 1
0x1003a7d5  jz      short loc_1003A7E8
0x1003a7d7  sub     eax, 1
0x1003a7da  jz      short loc_1003A7E1
0x1003a7dc  xor     eax, eax
0x1003a7de  inc     eax
0x1003a7df  jmp     short loc_1003A811
0x1003a7e1  call    ___scrt_dllmain_crt_thread_detach
0x1003a7e6  jmp     short loc_1003A7ED
0x1003a7e8  call    ___scrt_dllmain_crt_thread_attach
0x1003a7ed  movzx   eax, al
0x1003a7f0  jmp     short loc_1003A811
0x1003a7f2  push    [ebp+arg_8]
0x1003a7f5  push    [ebp+arg_0]
0x1003a7f8  call    dllmain_crt_process_attach
0x1003a7fd  pop     ecx
0x1003a7fe  jmp     short loc_1003A810
0x1003a800  cmp     [ebp+arg_8], 0
0x1003a804  setnz   al
0x1003a807  movzx   eax, al
0x1003a80a  push    eax
0x1003a80b  call    dllmain_crt_process_detach
0x1003a810  pop     ecx
0x1003a811  pop     ebp
0x1003a812  retn    0Ch
```
