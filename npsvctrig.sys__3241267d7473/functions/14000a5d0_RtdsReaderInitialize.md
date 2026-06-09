# RtdsReaderInitialize

- ea: `0x14000a5d0`
- end: `0x14000a631`
- name: `RtdsReaderInitialize`
- size: `97`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000b080`

## callees

- `0x1400018b0`

## pseudocode

```c
__int64 RtdsReaderInitialize()
{
  RtdspInitializeLock((struct _KMUTANT *)RtdsTriggerUpdateLock);
  qword_140005288 = (__int64)&RtdsTriggerDbList;
  RtdsTriggerDbList = (__int64)&RtdsTriggerDbList;
  qword_1400050B8 = 0;
  RtdspInitializeLock((struct _KMUTANT *)qword_140005238);
  qword_1400050F0 = 0;
  qword_140005298 = (__int64)&qword_140005290;
  qword_140005290 = (__int64)&qword_140005290;
  return 0;
}

```

## disassembly

```asm
0x14000a5d0  push    rbx
0x14000a5d2  sub     rsp, 20h
0x14000a5d6  lea     rcx, RtdsTriggerUpdateLock
0x14000a5dd  call    RtdspInitializeLock
0x14000a5e2  lea     rax, RtdsTriggerDbList
0x14000a5e9  xor     ebx, ebx
0x14000a5eb  lea     rcx, qword_140005238
0x14000a5f2  mov     cs:qword_140005288, rax
0x14000a5f9  mov     cs:RtdsTriggerDbList, rax
0x14000a600  mov     cs:qword_1400050B8, rbx
0x14000a607  call    RtdspInitializeLock
0x14000a60c  lea     rax, qword_140005290
0x14000a613  mov     cs:qword_1400050F0, rbx
0x14000a61a  mov     cs:qword_140005298, rax
0x14000a621  mov     cs:qword_140005290, rax
0x14000a628  xor     eax, eax
0x14000a62a  add     rsp, 20h
0x14000a62e  pop     rbx
0x14000a62f  retn
```
