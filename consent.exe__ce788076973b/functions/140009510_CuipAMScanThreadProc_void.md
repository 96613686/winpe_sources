# CuipAMScanThreadProc(void *)

- ea: `0x140009510`
- end: `0x14000953d`
- name: `?CuipAMScanThreadProc@@YAKPEAX@Z`
- size: `45`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140009510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009528`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009528`

## pseudocode

```c
__int64 __fastcall CuipAMScanThreadProc(HANDLE *Parameter)
{
  while ( WaitForSingleObjectEx(Parameter[2], 0xFFFFFFFF, 1) == 192 )
    ;
  return 0;
}

```

## disassembly

```asm
0x140009510  push    rbx
0x140009512  sub     rsp, 20h
0x140009516  mov     rbx, rcx
0x140009519  mov     rcx, [rbx+10h]; hHandle
0x14000951d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140009522  mov     r8d, 1; bAlertable
0x140009528  call    cs:__imp_WaitForSingleObjectEx
0x14000952e  cmp     eax, 0C0h
0x140009533  jz      short loc_140009519
0x140009535  xor     eax, eax
0x140009537  add     rsp, 20h
0x14000953b  pop     rbx
0x14000953c  retn
```
