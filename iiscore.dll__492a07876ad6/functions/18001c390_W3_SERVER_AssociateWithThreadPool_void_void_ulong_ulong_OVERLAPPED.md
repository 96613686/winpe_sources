# W3_SERVER::AssociateWithThreadPool(void *,void (*)(ulong,ulong,_OVERLAPPED *))

- ea: `0x18001c390`
- end: `0x18001c3d2`
- name: `?AssociateWithThreadPool@W3_SERVER@@UEAAJPEAXP6AXKKPEAU_OVERLAPPED@@@Z@Z`
- size: `66`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, void *, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3b0`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x18001c3a0`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x18001c3a0`

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
0x18001c390  sub     rsp, 28h
0x18001c394  mov     rax, r8
0x18001c397  mov     rcx, rdx
0x18001c39a  mov     rdx, rax
0x18001c39d  xor     r8d, r8d
0x18001c3a0  call    cs:__imp_?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x18001c3a7  nop     dword ptr [rax+rax+00h]
0x18001c3ac  test    eax, eax
0x18001c3ae  jnz     short loc_18001C3CA
0x18001c3b0  call    cs:__imp_GetLastError
0x18001c3b7  nop     dword ptr [rax+rax+00h]
0x18001c3bc  test    eax, eax
0x18001c3be  jle     short loc_18001C3CC
0x18001c3c0  movzx   eax, ax
0x18001c3c3  or      eax, 80070000h
0x18001c3c8  jmp     short loc_18001C3CC
0x18001c3ca  xor     eax, eax
0x18001c3cc  add     rsp, 28h
0x18001c3d0  retn
```
