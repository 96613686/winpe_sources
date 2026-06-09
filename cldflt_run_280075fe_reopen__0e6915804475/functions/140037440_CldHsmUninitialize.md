# CldHsmUninitialize

- ea: `0x140037440`
- end: `0x14003750b`
- name: `CldHsmUninitialize`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140037440`
- `0x1400411d8`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037487`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003749a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374ad`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374c0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374d3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374e6`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374f9`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037487`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003749a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374ad`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374c0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374d3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374e6`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374f9`
- `FLTMGR!FltCloseCommunicationPort` at `0x140037457`
- `FLTMGR!FltCloseCommunicationPort` at `0x140037457`

## pseudocode

```c
void CldHsmUninitialize()
{
  byte_140028878 = 0;
  if ( ServerPort )
  {
    FltCloseCommunicationPort(ServerPort);
    ServerPort = 0;
  }
  CldStreamUninitialize();
  if ( byte_140028879 )
  {
    ExDeletePagedLookasideList(&stru_140028880);
    ExDeletePagedLookasideList(&stru_140028980);
    ExDeletePagedLookasideList(&stru_140028A00);
    ExDeletePagedLookasideList(&Lookaside);
    ExDeletePagedLookasideList(&stru_140028A80);
    ExDeletePagedLookasideList(&stru_140028B00);
    ExDeletePagedLookasideList(&stru_140028B80);
  }
}

```

## disassembly

```asm
0x140037440  sub     rsp, 28h
0x140037444  mov     rcx, cs:ServerPort; ServerPort
0x14003744b  mov     cs:byte_140028878, 0
0x140037452  test    rcx, rcx
0x140037455  jz      short loc_14003746E
0x140037457  call    cs:__imp_FltCloseCommunicationPort
0x14003745e  nop     dword ptr [rax+rax+00h]
0x140037463  mov     cs:ServerPort, 0
0x14003746e  call    CldStreamUninitialize
0x140037473  cmp     cs:byte_140028879, 0
0x14003747a  jz      loc_140037505
0x140037480  lea     rcx, stru_140028880; Lookaside
0x140037487  call    cs:__imp_ExDeletePagedLookasideList
0x14003748e  nop     dword ptr [rax+rax+00h]
0x140037493  lea     rcx, stru_140028980; Lookaside
0x14003749a  call    cs:__imp_ExDeletePagedLookasideList
0x1400374a1  nop     dword ptr [rax+rax+00h]
0x1400374a6  lea     rcx, stru_140028A00; Lookaside
0x1400374ad  call    cs:__imp_ExDeletePagedLookasideList
0x1400374b4  nop     dword ptr [rax+rax+00h]
0x1400374b9  lea     rcx, Lookaside; Lookaside
0x1400374c0  call    cs:__imp_ExDeletePagedLookasideList
0x1400374c7  nop     dword ptr [rax+rax+00h]
0x1400374cc  lea     rcx, stru_140028A80; Lookaside
0x1400374d3  call    cs:__imp_ExDeletePagedLookasideList
0x1400374da  nop     dword ptr [rax+rax+00h]
0x1400374df  lea     rcx, stru_140028B00; Lookaside
0x1400374e6  call    cs:__imp_ExDeletePagedLookasideList
0x1400374ed  nop     dword ptr [rax+rax+00h]
0x1400374f2  lea     rcx, stru_140028B80; Lookaside
0x1400374f9  call    cs:__imp_ExDeletePagedLookasideList
0x140037500  nop     dword ptr [rax+rax+00h]
0x140037505  add     rsp, 28h
0x140037509  retn
```
