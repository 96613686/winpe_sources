# W3_CONTEXT_BASE::PostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),void *)

- ea: `0x180023ec0`
- end: `0x180023f04`
- name: `?PostCompletion@W3_CONTEXT_BASE@@UEAAJKP6AXKKPEAU_OVERLAPPED@@@ZPEAX@Z`
- size: `68`
- prototype: `__int64 __fastcall(W3_CONTEXT_BASE *__hidden this, unsigned int, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *), void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180023ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ee9`
- `W3TP!ThreadPoolPostCompletion` at `0x180023edf`
- `W3TP!ThreadPoolPostCompletion` at `0x180023edf`

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
0x180023ec0  sub     rsp, 28h
0x180023ec4  mov     rax, r8
0x180023ec7  mov     r10d, edx
0x180023eca  test    r8, r8
0x180023ecd  jnz     short loc_180023ED6
0x180023ecf  mov     eax, 80070057h
0x180023ed4  jmp     short loc_180023EFF
0x180023ed6  mov     r8, r9
0x180023ed9  mov     rdx, rax
0x180023edc  mov     ecx, r10d
0x180023edf  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180023ee5  test    eax, eax
0x180023ee7  jnz     short loc_180023EFD
0x180023ee9  call    cs:__imp_GetLastError
0x180023eef  test    eax, eax
0x180023ef1  jle     short loc_180023EFF
0x180023ef3  movzx   eax, ax
0x180023ef6  or      eax, 80070000h
0x180023efb  jmp     short loc_180023EFF
0x180023efd  xor     eax, eax
0x180023eff  add     rsp, 28h
0x180023f03  retn
```
