# W3_SERVER::AssociateWithThreadPool(void *,void (*)(ulong,ulong,_OVERLAPPED *))

- ea: `0x18001ac90`
- end: `0x18001acc5`
- name: `?AssociateWithThreadPool@W3_SERVER@@UEAAJPEAXP6AXKKPEAU_OVERLAPPED@@@Z@Z`
- size: `53`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, void *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001ac90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acaa`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x18001aca0`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x18001aca0`

## pseudocode

```c
signed int __fastcall W3_SERVER::AssociateWithThreadPool(
        W3_SERVER *this,
        void *a2,
        void (*a3)(unsigned int, unsigned int, struct _OVERLAPPED *))
{
  signed int result; // eax

  if ( ThreadPoolBindIoCompletionCallback(a2, a3, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001ac90  sub     rsp, 28h
0x18001ac94  mov     rax, r8
0x18001ac97  mov     rcx, rdx
0x18001ac9a  mov     rdx, rax
0x18001ac9d  xor     r8d, r8d
0x18001aca0  call    cs:__imp_?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x18001aca6  test    eax, eax
0x18001aca8  jnz     short loc_18001ACBE
0x18001acaa  call    cs:__imp_GetLastError
0x18001acb0  test    eax, eax
0x18001acb2  jle     short loc_18001ACC0
0x18001acb4  movzx   eax, ax
0x18001acb7  or      eax, 80070000h
0x18001acbc  jmp     short loc_18001ACC0
0x18001acbe  xor     eax, eax
0x18001acc0  add     rsp, 28h
0x18001acc4  retn
```
