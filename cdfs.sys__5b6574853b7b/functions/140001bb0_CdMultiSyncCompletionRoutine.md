# CdMultiSyncCompletionRoutine

- ea: `0x140001bb0`
- end: `0x140001c2f`
- name: `CdMultiSyncCompletionRoutine`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001bb0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140001bda`
- `ntoskrnl!IoFreeMdl` at `0x140001bda`
- `ntoskrnl!IoFreeIrp` at `0x140001be9`
- `ntoskrnl!IoFreeIrp` at `0x140001be9`
- `ntoskrnl!KeSetEvent` at `0x140001c14`
- `ntoskrnl!KeSetEvent` at `0x140001c14`

## pseudocode

```c
__int64 __fastcall CdMultiSyncCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int32 Status; // eax

  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    _InterlockedExchange((volatile __int32 *)(a3 + 16), Status);
    *(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL) = 0;
  }
  IoFreeMdl(a2->MdlAddress);
  IoFreeIrp(a2);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3, 0xFFFFFFFF) == 1 )
  {
    *(_DWORD *)(*(_QWORD *)(a3 + 8) + 48LL) = *(_DWORD *)(a3 + 16);
    KeSetEvent((PRKEVENT)(a3 + 24), 0, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001bb0  push    rbx
0x140001bb2  push    rbp
0x140001bb3  push    rsi
0x140001bb4  push    rdi
0x140001bb5  sub     rsp, 28h
0x140001bb9  mov     eax, [rdx+30h]
0x140001bbc  mov     rsi, r8
0x140001bbf  mov     rbp, rdx
0x140001bc2  test    eax, eax
0x140001bc4  jns     short loc_140001BD6
0x140001bc6  xchg    eax, [r8+10h]
0x140001bca  mov     rax, [r8+8]
0x140001bce  mov     qword ptr [rax+38h], 0
0x140001bd6  mov     rcx, [rdx+8]; Mdl
0x140001bda  call    cs:__imp_IoFreeMdl
0x140001be1  nop     dword ptr [rax+rax+00h]
0x140001be6  mov     rcx, rbp; Irp
0x140001be9  call    cs:__imp_IoFreeIrp
0x140001bf0  nop     dword ptr [rax+rax+00h]
0x140001bf5  or      eax, 0FFFFFFFFh
0x140001bf8  lock xadd [rsi], eax
0x140001bfc  cmp     eax, 1
0x140001bff  jnz     short loc_140001C20
0x140001c01  mov     rcx, [rsi+8]
0x140001c05  xor     r8d, r8d; Wait
0x140001c08  mov     eax, [rsi+10h]
0x140001c0b  xor     edx, edx; Increment
0x140001c0d  mov     [rcx+30h], eax
0x140001c10  lea     rcx, [rsi+18h]; Event
0x140001c14  call    cs:__imp_KeSetEvent
0x140001c1b  nop     dword ptr [rax+rax+00h]
0x140001c20  mov     eax, 0C0000016h
0x140001c25  add     rsp, 28h
0x140001c29  pop     rdi
0x140001c2a  pop     rsi
0x140001c2b  pop     rbp
0x140001c2c  pop     rbx
0x140001c2d  retn
```
