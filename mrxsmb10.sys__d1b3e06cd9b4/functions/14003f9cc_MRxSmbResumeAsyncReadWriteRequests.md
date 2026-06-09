# MRxSmbResumeAsyncReadWriteRequests

- ea: `0x14003f9cc`
- end: `0x14003fa4a`
- name: `MRxSmbResumeAsyncReadWriteRequests`
- size: `126`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003bbd0`

## callees

- `0x140016640`
- `0x14003f9cc`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14003fa12`
- `ntoskrnl!DbgPrint` at `0x14003fa12`
- `rdbss!RxLowIoCompletion` at `0x14003fa32`
- `rdbss!RxLowIoCompletion` at `0x14003fa32`

## pseudocode

```c
void __fastcall MRxSmbResumeAsyncReadWriteRequests(PRX_CONTEXT RxContext)
{
  __int64 (*v2)(void); // rax
  NTSTATUS v3; // eax
  NTSTATUS v4; // edi

  if ( LOBYTE(RxContext->RealDevice) == 3 )
  {
    v2 = (__int64 (*)(void))MRxSmbRead;
  }
  else
  {
    if ( LOBYTE(RxContext->RealDevice) != 4 )
      return;
    v2 = MRxSmbWrite;
  }
  v3 = v2();
  v4 = v3;
  if ( v3 != 259 )
  {
    if ( v3 )
    {
      DbgPrint("RxContext Async CSC Status %lx\n", v3);
      RxContext->StoredStatus = v4;
      RxContext->InformationToReturn = 0;
    }
    RxLowIoCompletion(RxContext);
  }
}

```

## disassembly

```asm
0x14003f9cc  mov     [rsp+arg_0], rbx
0x14003f9d1  push    rdi
0x14003f9d2  sub     rsp, 20h
0x14003f9d6  movzx   edx, byte ptr [rcx+20h]
0x14003f9da  mov     rbx, rcx
0x14003f9dd  sub     edx, 3
0x14003f9e0  jz      short loc_14003F9F0
0x14003f9e2  cmp     edx, 1
0x14003f9e5  jnz     short loc_14003FA3E
0x14003f9e7  lea     rax, MRxSmbWrite
0x14003f9ee  jmp     short loc_14003F9F7
0x14003f9f0  lea     rax, MRxSmbRead
0x14003f9f7  call    _guard_dispatch_icall
0x14003f9fc  mov     edi, eax
0x14003f9fe  cmp     eax, 103h
0x14003fa03  jz      short loc_14003FA3E
0x14003fa05  test    eax, eax
0x14003fa07  jz      short loc_14003FA2F
0x14003fa09  mov     edx, eax
0x14003fa0b  lea     rcx, aRxcontextAsync; "RxContext Async CSC Status %lx\n"
0x14003fa12  call    cs:__imp_DbgPrint
0x14003fa19  nop     dword ptr [rax+rax+00h]
0x14003fa1e  mov     [rbx+0B0h], edi
0x14003fa24  mov     qword ptr [rbx+0B8h], 0
0x14003fa2f  mov     rcx, rbx; RxContext
0x14003fa32  call    cs:__imp_RxLowIoCompletion
0x14003fa39  nop     dword ptr [rax+rax+00h]
0x14003fa3e  mov     rbx, [rsp+28h+arg_0]
0x14003fa43  add     rsp, 20h
0x14003fa47  pop     rdi
0x14003fa48  retn
```
