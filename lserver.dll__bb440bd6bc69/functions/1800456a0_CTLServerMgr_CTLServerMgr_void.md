# CTLServerMgr::CTLServerMgr(void)

- ea: `0x1800456a0`
- end: `0x18004577d`
- name: `??0CTLServerMgr@@QEAA@XZ`
- size: `221`
- prototype: `CTLServerMgr *__fastcall(CTLServerMgr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ba0`

## callees

- `0x1800456a0`
- `0x18004692c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800456c2`
- `KERNEL32!CreateEventW` at `0x1800456e0`
- `KERNEL32!CreateEventW` at `0x1800456c2`
- `KERNEL32!CreateEventW` at `0x1800456e0`
- `KERNEL32!CreateMutexW` at `0x1800456fa`
- `KERNEL32!CreateMutexW` at `0x1800456fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CTLServerMgr *__fastcall CTLServerMgr::CTLServerMgr(CTLServerMgr *this)
{
  HANDLE MutexW; // rax

  qword_1800E9280 = (__int64)CreateEventW(0, 1, 0, 0);
  g_ServerMgr = CreateEventW(0, 0, 1, 0);
  MutexW = CreateMutexW(0, 0, 0);
  qword_1800E9278 = (__int64)MutexW;
  if ( qword_1800E9280 && g_ServerMgr && MutexW )
  {
    dword_1800E9288 = -1;
    dword_1800E928C = -1;
    dword_1800E9290 = 0;
    dword_1800E9294 = 0;
  }
  qword_1800E9298 = 0;
  qword_1800E92A0 = 0;
  qword_1800E9298 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,CWorkObject *>>>::_Buyheadnode();
  qword_1800E92A8 = 0;
  return (CTLServerMgr *)&g_ServerMgr;
}

```

## disassembly

```asm
0x1800456a0  mov     [rsp+arg_0], rcx
0x1800456a5  push    rdi
0x1800456a6  sub     rsp, 20h
0x1800456aa  lea     rdi, ?g_ServerMgr@@3VCTLServerMgr@@A; CTLServerMgr g_ServerMgr
0x1800456b1  mov     [rsp+28h+arg_8], rdi
0x1800456b6  xor     r9d, r9d; lpName
0x1800456b9  xor     r8d, r8d; bInitialState
0x1800456bc  lea     edx, [r9+1]; bManualReset
0x1800456c0  xor     ecx, ecx; lpEventAttributes
0x1800456c2  call    cs:__imp_CreateEventW
0x1800456c9  nop     dword ptr [rax+rax+00h]
0x1800456ce  mov     cs:qword_1800E9280, rax
0x1800456d5  xor     r9d, r9d; lpName
0x1800456d8  xor     edx, edx; bManualReset
0x1800456da  xor     ecx, ecx; lpEventAttributes
0x1800456dc  lea     r8d, [r9+1]; bInitialState
0x1800456e0  call    cs:__imp_CreateEventW
0x1800456e7  nop     dword ptr [rax+rax+00h]
0x1800456ec  mov     cs:?g_ServerMgr@@3VCTLServerMgr@@A, rax; CTLServerMgr g_ServerMgr
0x1800456f3  xor     r8d, r8d; lpName
0x1800456f6  xor     edx, edx; bInitialOwner
0x1800456f8  xor     ecx, ecx; lpMutexAttributes
0x1800456fa  call    cs:__imp_CreateMutexW
0x180045701  nop     dword ptr [rax+rax+00h]
0x180045706  mov     cs:qword_1800E9278, rax
0x18004570d  cmp     cs:qword_1800E9280, 0
0x180045715  jz      short loc_180045743
0x180045717  cmp     cs:?g_ServerMgr@@3VCTLServerMgr@@A, 0; CTLServerMgr g_ServerMgr
0x18004571f  jz      short loc_180045743
0x180045721  test    rax, rax
0x180045724  jz      short loc_180045743
0x180045726  or      eax, 0FFFFFFFFh
0x180045729  mov     cs:dword_1800E9288, eax
0x18004572f  mov     cs:dword_1800E928C, eax
0x180045735  and     cs:dword_1800E9290, 0
0x18004573c  and     cs:dword_1800E9294, 0
0x180045743  lea     rax, qword_1800E9298
0x18004574a  mov     [rsp+28h+arg_0], rax
0x18004574f  and     cs:qword_1800E9298, 0
0x180045757  and     cs:qword_1800E92A0, 0
0x18004575f  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKPEAVCWorkObject@@@std@@V?$allocator@U?$pair@$$CBKPEAVCWorkObject@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCWorkObject@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,CWorkObject *>>>::_Buyheadnode(void)
0x180045764  mov     cs:qword_1800E9298, rax
0x18004576b  and     cs:qword_1800E92A8, 0
0x180045773  mov     rax, rdi
0x180045776  add     rsp, 20h
0x18004577a  pop     rdi
0x18004577b  retn
```
