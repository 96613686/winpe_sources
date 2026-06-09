# W3_CONTEXT_BASE::PostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),void *)

- ea: `0x180025d50`
- end: `0x180025da1`
- name: `?PostCompletion@W3_CONTEXT_BASE@@UEAAJKP6AXKKPEAU_OVERLAPPED@@@ZPEAX@Z`
- size: `81`
- prototype: `__int64 __fastcall(W3_CONTEXT_BASE *__hidden this, unsigned int, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *), void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d7f`
- `W3TP!ThreadPoolPostCompletion` at `0x180025d6f`
- `W3TP!ThreadPoolPostCompletion` at `0x180025d6f`

## pseudocode

```c
signed int __fastcall W3_CONTEXT_BASE::PostCompletion(
        W3_CONTEXT_BASE *this,
        unsigned int a2,
        void (*a3)(unsigned int, unsigned int, struct _OVERLAPPED *),
        struct _OVERLAPPED *a4)
{
  signed int result; // eax

  if ( !a3 )
    return -2147024809;
  if ( ThreadPoolPostCompletion(a2, a3, a4) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025d50  sub     rsp, 28h
0x180025d54  mov     rax, r8
0x180025d57  mov     r10d, edx
0x180025d5a  test    r8, r8
0x180025d5d  jnz     short loc_180025D66
0x180025d5f  mov     eax, 80070057h
0x180025d64  jmp     short loc_180025D9B
0x180025d66  mov     r8, r9
0x180025d69  mov     rdx, rax
0x180025d6c  mov     ecx, r10d
0x180025d6f  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180025d76  nop     dword ptr [rax+rax+00h]
0x180025d7b  test    eax, eax
0x180025d7d  jnz     short loc_180025D99
0x180025d7f  call    cs:__imp_GetLastError
0x180025d86  nop     dword ptr [rax+rax+00h]
0x180025d8b  test    eax, eax
0x180025d8d  jle     short loc_180025D9B
0x180025d8f  movzx   eax, ax
0x180025d92  or      eax, 80070000h
0x180025d97  jmp     short loc_180025D9B
0x180025d99  xor     eax, eax
0x180025d9b  add     rsp, 28h
0x180025d9f  retn
```
