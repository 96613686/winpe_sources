# DbgToolsSafe_EventWriteTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x1801a19a8`
- end: `0x1801a1a13`
- name: `?DbgToolsSafe_EventWriteTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `107`
- prototype: `unsigned int __fastcall(unsigned __int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000102c`

## callees

- `0x1801a19a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1a04`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1801a19d2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1801a19d2`

## pseudocode

```c
__int64 __fastcall DbgToolsSafe_EventWriteTransfer(
        REGHANDLE a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  if ( dword_1802B745C )
    return (unsigned int)dword_1802B7460;
  else
    return EventWriteTransfer(a1, a2, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1801a19a8  push    rbx
0x1801a19aa  sub     rsp, 40h
0x1801a19ae  mov     eax, cs:dword_1802B745C
0x1801a19b4  test    eax, eax
0x1801a19b6  jz      short loc_1801A19C0
0x1801a19b8  mov     eax, cs:dword_1802B7460
0x1801a19be  jmp     short loc_1801A1A0D
0x1801a19c0  mov     rax, [rsp+48h+arg_28]
0x1801a19c5  mov     [rsp+48h+UserData], rax; UserData
0x1801a19ca  mov     eax, [rsp+48h+arg_20]
0x1801a19ce  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1801a19d2  call    cs:__imp_EventWriteTransfer
0x1801a19d8  mov     ebx, eax
0x1801a19da  mov     [rsp+48h+var_18], eax
0x1801a19de  jmp     short loc_1801A1A0B
0x1801a19e0  xor     ebx, ebx
0x1801a19e2  cmp     eax, 0C06D007Eh
0x1801a19e7  setnz   bl
0x1801a19ea  add     ebx, 7Eh ; '~'
0x1801a19ed  mov     [rsp+48h+var_18], ebx
0x1801a19f1  mov     cs:dword_1802B7460, ebx
0x1801a19f7  mov     eax, 1
0x1801a19fc  xchg    eax, cs:dword_1802B745C
0x1801a1a02  mov     ecx, ebx; dwErrCode
0x1801a1a04  call    cs:__imp_SetLastError
0x1801a1a0a  nop
0x1801a1a0b  mov     eax, ebx
0x1801a1a0d  add     rsp, 40h
0x1801a1a11  pop     rbx
0x1801a1a12  retn
0x180202463  push    rbp
0x180202465  sub     rsp, 30h
0x180202469  mov     rbp, rdx
0x18020246c  mov     rax, [rcx]
0x18020246f  cmp     dword ptr [rax], 0C06D007Eh
0x180202475  jz      short loc_180202483
0x180202477  cmp     dword ptr [rax], 0C06D007Fh
0x18020247d  jz      short loc_180202483
0x18020247f  xor     eax, eax
0x180202481  jmp     short loc_180202488
0x180202483  mov     eax, 1
0x180202488  add     rsp, 30h
0x18020248c  pop     rbp
0x18020248d  retn
```
