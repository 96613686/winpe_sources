# KeRegDeleteKey

- ea: `0x18007d844`
- end: `0x18007d899`
- name: `KeRegDeleteKey`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007d8a0`

## callees

- `0x180025f40`
- `0x180040b10`
- `0x18007d844`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007d886`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007d886`
- `ntoskrnl!ZwDeleteKey` at `0x18007d86c`
- `ntoskrnl!ZwDeleteKey` at `0x18007d86c`

## pseudocode

```c
ULONG __fastcall KeRegDeleteKey(void *a1, const WCHAR *a2)
{
  ULONG result; // eax
  NTSTATUS v3; // ebx
  HANDLE KeyHandle; // [rsp+40h] [rbp+18h] BYREF

  KeyHandle = 0;
  result = KeRegOpenKey(a1, a2, 0x3001Fu, &KeyHandle);
  if ( !result )
  {
    v3 = ZwDeleteKey(KeyHandle);
    KeRegCloseKey(KeyHandle);
    return RtlNtStatusToDosErrorNoTeb(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18007d844  push    rbx
0x18007d846  sub     rsp, 20h
0x18007d84a  lea     r9, [rsp+28h+KeyHandle]
0x18007d84f  mov     [rsp+28h+KeyHandle], 0
0x18007d858  mov     r8d, 3001Fh
0x18007d85e  call    KeRegOpenKey
0x18007d863  test    eax, eax
0x18007d865  jnz     short loc_18007D892
0x18007d867  mov     rcx, [rsp+28h+KeyHandle]; KeyHandle
0x18007d86c  call    cs:__imp_ZwDeleteKey
0x18007d873  nop     dword ptr [rax+rax+00h]
0x18007d878  mov     rcx, [rsp+28h+KeyHandle]; Handle
0x18007d87d  mov     ebx, eax
0x18007d87f  call    KeRegCloseKey
0x18007d884  mov     ecx, ebx; Status
0x18007d886  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18007d88d  nop     dword ptr [rax+rax+00h]
0x18007d892  add     rsp, 20h
0x18007d896  pop     rbx
0x18007d897  retn
```
