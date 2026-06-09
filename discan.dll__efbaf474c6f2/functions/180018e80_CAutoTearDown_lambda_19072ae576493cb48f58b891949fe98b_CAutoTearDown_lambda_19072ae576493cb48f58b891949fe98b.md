# CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___::_CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___

- ea: `0x180018e80`
- end: `0x180018ea3`
- name: `CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___::_CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ae24`
- `0x180038448`

## callees

- `0x180018e80`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180018e98`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180018e98`

## pseudocode

```c
void __fastcall CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___::_CAutoTearDown__lambda_19072ae576493cb48f58b891949fe98b___(
        __int64 *a1)
{
  __int64 v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(*(_QWORD *)v1 + 104LL), 0, 0);
}

```

## disassembly

```asm
0x180018e80  sub     rsp, 28h
0x180018e84  mov     rcx, [rcx]
0x180018e87  test    rcx, rcx
0x180018e8a  jz      short loc_180018E9E
0x180018e8c  mov     rcx, [rcx]
0x180018e8f  xor     r8d, r8d; pvCleanupContext
0x180018e92  xor     edx, edx; fCancelPendingCallbacks
0x180018e94  mov     rcx, [rcx+68h]; ptpcg
0x180018e98  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180018e9e  add     rsp, 28h
0x180018ea2  retn
```
