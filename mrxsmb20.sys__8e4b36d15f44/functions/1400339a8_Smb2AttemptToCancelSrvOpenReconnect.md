# Smb2AttemptToCancelSrvOpenReconnect

- ea: `0x1400339a8`
- end: `0x140033a24`
- name: `Smb2AttemptToCancelSrvOpenReconnect`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140022e90`

## callees

- `0x1400339a8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400339df`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400339df`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400339be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400339be`
- `rdbss!RxCancelContext` at `0x1400339fd`
- `rdbss!RxCancelContext` at `0x1400339fd`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140033a0c`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140033a0c`

## pseudocode

```c
void __fastcall Smb2AttemptToCancelSrvOpenReconnect(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbx

  v1 = a1 + 16;
  ExAcquirePushLockExclusiveEx(a1 + 16, 0);
  v3 = *(_QWORD *)(a1 + 304);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 4));
  ExReleasePushLockExclusiveEx(v1, 0);
  if ( v3 )
  {
    *(_DWORD *)(v3 + 232) = -1073741628;
    RxCancelContext(v3);
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)v3);
  }
}

```

## disassembly

```asm
0x1400339a8  mov     [rsp+arg_0], rbx
0x1400339ad  push    rdi
0x1400339ae  sub     rsp, 20h
0x1400339b2  lea     rdi, [rcx+10h]
0x1400339b6  mov     rbx, rcx
0x1400339b9  mov     rcx, rdi
0x1400339bc  xor     edx, edx
0x1400339be  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400339c5  nop     dword ptr [rax+rax+00h]
0x1400339ca  mov     rbx, [rbx+130h]
0x1400339d1  test    rbx, rbx
0x1400339d4  jz      short loc_1400339DA
0x1400339d6  lock inc dword ptr [rbx+4]
0x1400339da  xor     edx, edx
0x1400339dc  mov     rcx, rdi
0x1400339df  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400339e6  nop     dword ptr [rax+rax+00h]
0x1400339eb  test    rbx, rbx
0x1400339ee  jz      short loc_140033A18
0x1400339f0  mov     rcx, rbx
0x1400339f3  mov     dword ptr [rbx+0E8h], 0C00000C4h
0x1400339fd  call    cs:__imp_RxCancelContext
0x140033a04  nop     dword ptr [rax+rax+00h]
0x140033a09  mov     rcx, rbx; RxContext
0x140033a0c  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140033a13  nop     dword ptr [rax+rax+00h]
0x140033a18  mov     rbx, [rsp+28h+arg_0]
0x140033a1d  add     rsp, 20h
0x140033a21  pop     rdi
0x140033a22  retn
```
