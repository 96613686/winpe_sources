# GhostLPCThreadProc

- ea: `0x18000a7f0`
- end: `0x18000a83b`
- name: `GhostLPCThreadProc`
- size: `75`
- prototype: `__int64 __fastcall(CGhostMgr **Parameter)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a6b0`

## callees

- `0x180001560`
- `0x180004dc4`
- `0x180007e64`
- `0x18000a7f0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall GhostLPCThreadProc(CGhostMgr **Parameter)
{
  CGhostMgr::HandleRequest(Parameter[11], (struct GHOSTLPCMSG *)Parameter, 0);
  CCountedObject::Release(Parameter[11]);
  if ( *((_DWORD *)Parameter + 24) )
  {
    (*(void (__fastcall **)(CGhostMgr *))(*(_QWORD *)*Parameter + 8LL))(*Parameter);
    operator delete(Parameter, 0x68u);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a7f0  push    rbx
0x18000a7f2  sub     rsp, 20h
0x18000a7f6  mov     rbx, rcx
0x18000a7f9  mov     rdx, rcx; struct GHOSTLPCMSG *
0x18000a7fc  mov     rcx, [rcx+58h]; this
0x18000a800  xor     r8d, r8d; struct CGhostWindow **
0x18000a803  call    ?HandleRequest@CGhostMgr@@QEAAHPEAUGHOSTLPCMSG@@PEAPEAVCGhostWindow@@@Z; CGhostMgr::HandleRequest(GHOSTLPCMSG *,CGhostWindow * *)
0x18000a808  mov     rcx, [rbx+58h]; this
0x18000a80c  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000a811  cmp     dword ptr [rbx+60h], 0
0x18000a815  jz      short loc_18000A833
0x18000a817  mov     rcx, [rbx]
0x18000a81a  mov     rax, [rcx]
0x18000a81d  mov     rax, [rax+8]
0x18000a821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a826  mov     edx, 68h ; 'h'; unsigned __int64
0x18000a82b  mov     rcx, rbx; void *
0x18000a82e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a833  xor     eax, eax
0x18000a835  add     rsp, 20h
0x18000a839  pop     rbx
0x18000a83a  retn
```
