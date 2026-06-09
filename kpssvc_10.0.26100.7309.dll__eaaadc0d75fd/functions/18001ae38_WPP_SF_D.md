# WPP_SF_D

- ea: `0x18001ae38`
- end: `0x18001ae73`
- name: `WPP_SF_D`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `72`
- callee_count: `0`
- tags: ``

## callers

- `0x1800195d8`
- `0x180019ad0`
- `0x180019d2c`
- `0x180019dcc`
- `0x18001a0c0`
- `0x18001a1e0`
- `0x18001a958`
- `0x18001aa80`
- `0x18001e520`
- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x1800202d0`
- `0x180020610`
- `0x180020750`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800215c0`
- `0x1800216f4`
- `0x180021b10`
- `0x1800222f0`
- `0x1800223fc`
- `0x1800225d0`
- `0x180022708`
- `0x180022a5c`
- `0x180027530`
- `0x1800276c8`
- `0x1800279f8`
- `0x180027af8`
- `0x180027de0`
- `0x180028030`
- `0x1800280d8`
- `0x1800284ec`
- `0x1800285a0`
- `0x180028800`
- `0x1800288c4`
- `0x1800289f8`
- `0x180028c08`
- `0x1800291e4`
- `0x180029c48`
- `0x180029e64`
- `0x18002a42c`
- `0x18002a5a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ae61`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ae61`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18001ae38  mov     r11, rsp
0x18001ae3b  mov     [r11+20h], r9d
0x18001ae3f  sub     rsp, 48h
0x18001ae43  and     qword ptr [r11-18h], 0
0x18001ae48  lea     rax, [r11+20h]
0x18001ae4c  movzx   r9d, dx; MessageNumber
0x18001ae50  mov     edx, 2Bh ; '+'; MessageFlags
0x18001ae55  mov     qword ptr [r11-20h], 4
0x18001ae5d  mov     [r11-28h], rax
0x18001ae61  call    cs:__imp_TraceMessage
0x18001ae68  nop     dword ptr [rax+rax+00h]
0x18001ae6d  add     rsp, 48h
0x18001ae71  retn
```
