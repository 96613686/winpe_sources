# MyRead(unsigned __int64,uchar *,long,long *)

- ea: `0x180085fd0`
- end: `0x180086022`
- name: `?MyRead@@YAK_KPEAEJPEAJ@Z`
- size: `82`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180085fd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180086000`
- `KERNEL32!GetLastError` at `0x180086000`
- `KERNEL32!ReadFile` at `0x180085ff0`
- `KERNEL32!ReadFile` at `0x180085ff0`

## pseudocode

```c
signed int __fastcall MyRead(void *a1, unsigned __int8 *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( !a1 )
    return -2147467259;
  *a4 = 0;
  if ( ReadFile(a1, a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180085fd0  sub     rsp, 38h
0x180085fd4  test    rcx, rcx
0x180085fd7  jnz     short loc_180085FE0
0x180085fd9  mov     eax, 80004005h
0x180085fde  jmp     short loc_18008601C
0x180085fe0  mov     dword ptr [r9], 0
0x180085fe7  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180085ff0  call    cs:__imp_ReadFile
0x180085ff7  nop     dword ptr [rax+rax+00h]
0x180085ffc  test    eax, eax
0x180085ffe  jnz     short loc_18008601A
0x180086000  call    cs:__imp_GetLastError
0x180086007  nop     dword ptr [rax+rax+00h]
0x18008600c  test    eax, eax
0x18008600e  jle     short loc_18008601C
0x180086010  movzx   eax, ax
0x180086013  or      eax, 80070000h
0x180086018  jmp     short loc_18008601C
0x18008601a  xor     eax, eax
0x18008601c  add     rsp, 38h
0x180086020  retn
```
