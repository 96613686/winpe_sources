# CldHsmUninitialize

- ea: `0x140037460`
- end: `0x14003752b`
- name: `CldHsmUninitialize`
- size: `203`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140037460`
- `0x1400411e8`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374a7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374ba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374cd`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374e0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374f3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037506`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037519`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374a7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374ba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374cd`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374e0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400374f3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037506`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140037519`
- `FLTMGR!FltCloseCommunicationPort` at `0x140037477`
- `FLTMGR!FltCloseCommunicationPort` at `0x140037477`

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
0x140037460  sub     rsp, 28h
0x140037464  mov     rcx, cs:ServerPort; ServerPort
0x14003746b  mov     cs:byte_140028878, 0
0x140037472  test    rcx, rcx
0x140037475  jz      short loc_14003748E
0x140037477  call    cs:__imp_FltCloseCommunicationPort
0x14003747e  nop     dword ptr [rax+rax+00h]
0x140037483  mov     cs:ServerPort, 0
0x14003748e  call    CldStreamUninitialize
0x140037493  cmp     cs:byte_140028879, 0
0x14003749a  jz      loc_140037525
0x1400374a0  lea     rcx, stru_140028880; Lookaside
0x1400374a7  call    cs:__imp_ExDeletePagedLookasideList
0x1400374ae  nop     dword ptr [rax+rax+00h]
0x1400374b3  lea     rcx, stru_140028980; Lookaside
0x1400374ba  call    cs:__imp_ExDeletePagedLookasideList
0x1400374c1  nop     dword ptr [rax+rax+00h]
0x1400374c6  lea     rcx, stru_140028A00; Lookaside
0x1400374cd  call    cs:__imp_ExDeletePagedLookasideList
0x1400374d4  nop     dword ptr [rax+rax+00h]
0x1400374d9  lea     rcx, Lookaside; Lookaside
0x1400374e0  call    cs:__imp_ExDeletePagedLookasideList
0x1400374e7  nop     dword ptr [rax+rax+00h]
0x1400374ec  lea     rcx, stru_140028A80; Lookaside
0x1400374f3  call    cs:__imp_ExDeletePagedLookasideList
0x1400374fa  nop     dword ptr [rax+rax+00h]
0x1400374ff  lea     rcx, stru_140028B00; Lookaside
0x140037506  call    cs:__imp_ExDeletePagedLookasideList
0x14003750d  nop     dword ptr [rax+rax+00h]
0x140037512  lea     rcx, stru_140028B80; Lookaside
0x140037519  call    cs:__imp_ExDeletePagedLookasideList
0x140037520  nop     dword ptr [rax+rax+00h]
0x140037525  add     rsp, 28h
0x140037529  retn
```
