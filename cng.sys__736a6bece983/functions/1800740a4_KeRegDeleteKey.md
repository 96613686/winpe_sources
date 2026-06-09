# KeRegDeleteKey

- ea: `0x1800740a4`
- end: `0x1800740f9`
- name: `KeRegDeleteKey`
- size: `85`
- prototype: `ULONG __fastcall(void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180074100`

## callees

- `0x180018ec0`
- `0x1800375a0`
- `0x1800740a4`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800740e6`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800740e6`
- `ntoskrnl!ZwDeleteKey` at `0x1800740cc`
- `ntoskrnl!ZwDeleteKey` at `0x1800740cc`

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
0x1800740a4  push    rbx
0x1800740a6  sub     rsp, 20h
0x1800740aa  lea     r9, [rsp+28h+KeyHandle]
0x1800740af  mov     [rsp+28h+KeyHandle], 0
0x1800740b8  mov     r8d, 3001Fh
0x1800740be  call    KeRegOpenKey
0x1800740c3  test    eax, eax
0x1800740c5  jnz     short loc_1800740F2
0x1800740c7  mov     rcx, [rsp+28h+KeyHandle]; KeyHandle
0x1800740cc  call    cs:__imp_ZwDeleteKey
0x1800740d3  nop     dword ptr [rax+rax+00h]
0x1800740d8  mov     rcx, [rsp+28h+KeyHandle]; Handle
0x1800740dd  mov     ebx, eax
0x1800740df  call    KeRegCloseKey
0x1800740e4  mov     ecx, ebx; Status
0x1800740e6  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800740ed  nop     dword ptr [rax+rax+00h]
0x1800740f2  add     rsp, 20h
0x1800740f6  pop     rbx
0x1800740f7  retn
```
