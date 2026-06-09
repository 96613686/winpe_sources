# SrvDereferenceSecret

- ea: `0x180008f00`
- end: `0x180008f48`
- name: `SrvDereferenceSecret`
- size: `72`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008e98`
- `0x18000e3f0`
- `0x18000ebb0`

## callees

- `0x180003cf0`
- `0x180008f00`
- `0x18000a13c`

## string_xrefs

- `0x180008f27`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvDereferenceSecret(volatile signed __int64 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx

  if ( _InterlockedExchangeAdd64(a1 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 && (v1 = SrvFreeSecret((PVOID)a1), v2 = v1, v1 < 0) )
    DebugTraceError(
      (unsigned int)v1,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
      930);
  else
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180008f00  push    rbx
0x180008f02  sub     rsp, 20h
0x180008f06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f0a  lock xadd [rcx+8], rax
0x180008f10  cmp     rax, 1
0x180008f14  jnz     short loc_180008F3E
0x180008f16  call    SrvFreeSecret
0x180008f1b  mov     ebx, eax
0x180008f1d  test    eax, eax
0x180008f1f  jns     short loc_180008F3E
0x180008f21  mov     r9d, 3A2h
0x180008f27  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008f2e  lea     rdx, aStatus; "Status"
0x180008f35  mov     ecx, eax
0x180008f37  call    DebugTraceError
0x180008f3c  jmp     short loc_180008F40
0x180008f3e  xor     ebx, ebx
0x180008f40  mov     eax, ebx
0x180008f42  add     rsp, 20h
0x180008f46  pop     rbx
0x180008f47  retn
```
