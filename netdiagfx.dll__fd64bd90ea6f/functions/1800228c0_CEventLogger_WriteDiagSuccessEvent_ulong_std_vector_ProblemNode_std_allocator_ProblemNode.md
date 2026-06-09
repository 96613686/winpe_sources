# CEventLogger::WriteDiagSuccessEvent(ulong,std::vector<ProblemNode *,std::allocator<ProblemNode *>> *)

- ea: `0x1800228c0`
- end: `0x18002291a`
- name: `?WriteDiagSuccessEvent@CEventLogger@@UEAAJKPEAV?$vector@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800228c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800228fd`
- `ADVAPI32!EventWrite` at `0x1800228fd`
- `ADVAPI32!EventEnabled` at `0x1800228df`
- `ADVAPI32!EventEnabled` at `0x1800228df`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteDiagSuccessEvent(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  signed int v4; // eax

  v3 = 0;
  if ( !a2 || !a3 )
  {
    if ( EventEnabled(NETDIAG_EVT_GUID_Context, &NDFDiagSuccessNPEvtDesc) )
    {
      v4 = EventWrite(NETDIAG_EVT_GUID_Context, &NDFDiagSuccessNPEvtDesc, 0, 0);
      v3 = v4;
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800228c0  push    rbx
0x1800228c2  sub     rsp, 20h
0x1800228c6  xor     ebx, ebx
0x1800228c8  test    edx, edx
0x1800228ca  jz      short loc_1800228D1
0x1800228cc  test    r8, r8
0x1800228cf  jnz     short loc_180022912
0x1800228d1  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x1800228d8  lea     rdx, NDFDiagSuccessNPEvtDesc; EventDescriptor
0x1800228df  call    cs:__imp_EventEnabled
0x1800228e5  test    al, al
0x1800228e7  jz      short loc_180022912
0x1800228e9  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x1800228f0  lea     rdx, NDFDiagSuccessNPEvtDesc; EventDescriptor
0x1800228f7  xor     r9d, r9d; UserData
0x1800228fa  xor     r8d, r8d; UserDataCount
0x1800228fd  call    cs:__imp_EventWrite
0x180022903  mov     ebx, eax
0x180022905  test    eax, eax
0x180022907  jle     short loc_180022912
0x180022909  movzx   ebx, ax
0x18002290c  or      ebx, 80070000h
0x180022912  mov     eax, ebx
0x180022914  add     rsp, 20h
0x180022918  pop     rbx
0x180022919  retn
```
