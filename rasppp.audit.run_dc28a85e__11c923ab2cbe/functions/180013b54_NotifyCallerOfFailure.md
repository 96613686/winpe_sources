# NotifyCallerOfFailure

- ea: `0x180013b54`
- end: `0x180013b81`
- name: `NotifyCallerOfFailure`
- size: `45`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000423c`
- `0x18000442c`
- `0x18000b2e8`
- `0x18000b720`
- `0x18000c8d4`
- `0x18000e7a4`
- `0x18000ecac`
- `0x180015a80`
- `0x180016260`
- `0x180017510`
- `0x1800181b0`

## callees

- `0x18001348c`

## pseudocode

```c
ULONG __fastcall NotifyCallerOfFailure(__int64 a1, unsigned int a2)
{
  int v2; // eax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  v2 = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 48) = 0;
  return NotifyCaller(a1, (v2 & 4) != 0 ? 20 : 1, &v4);
}

```

## disassembly

```asm
0x180013b54  mov     [rsp+arg_8], edx
0x180013b58  sub     rsp, 28h
0x180013b5c  mov     eax, [rcx+38h]
0x180013b5f  lea     r8, [rsp+28h+arg_8]
0x180013b64  and     al, 4
0x180013b66  mov     dword ptr [rcx+30h], 0
0x180013b6d  neg     al
0x180013b6f  sbb     edx, edx
0x180013b71  and     edx, 13h
0x180013b74  inc     edx
0x180013b76  call    NotifyCaller
0x180013b7b  add     rsp, 28h
0x180013b7f  retn
```
