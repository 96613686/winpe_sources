# pSetupOpenPredefinedKey

- ea: `0x180003904`
- end: `0x180003980`
- name: `pSetupOpenPredefinedKey`
- size: `124`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800036a8`
- `0x180003820`

## callees

- `0x1800037cc`
- `0x180003820`
- `0x180003904`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180003963`
- `ntdll!RtlFreeUnicodeString` at `0x180003963`
- `ntdll!RtlNtStatusToDosError` at `0x18000392f`
- `ntdll!RtlNtStatusToDosError` at `0x18000392f`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003923`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003923`

## pseudocode

```c
__int64 __fastcall pSetupOpenPredefinedKey(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  const WCHAR *Buffer; // rax
  unsigned int v6; // ebx
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-18h] BYREF

  KeyPath = 0;
  if ( a1 == -2147483647 )
  {
    v3 = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( v3 < 0 )
    {
      v4 = RtlNtStatusToDosError(v3);
LABEL_6:
      v6 = v4;
      goto LABEL_7;
    }
    Buffer = KeyPath.Buffer;
LABEL_5:
    v4 = pSetupOpenKey(0, Buffer, 0, 0x2000000u, a2);
    goto LABEL_6;
  }
  Buffer = (const WCHAR *)pSetupGetPredefinedKeyPath();
  if ( Buffer )
    goto LABEL_5;
  v6 = 50;
LABEL_7:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  return v6;
}

```

## disassembly

```asm
0x180003904  push    rbx
0x180003906  sub     rsp, 40h
0x18000390a  xorps   xmm0, xmm0
0x18000390d  mov     rbx, rdx
0x180003910  movups  xmmword ptr [rsp+48h+KeyPath.Length], xmm0
0x180003915  cmp     rcx, 0FFFFFFFF80000001h
0x18000391c  jnz     short loc_180003971
0x18000391e  lea     rcx, [rsp+48h+KeyPath]; KeyPath
0x180003923  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180003929  test    eax, eax
0x18000392b  jns     short loc_180003937
0x18000392d  mov     ecx, eax; Status
0x18000392f  call    cs:__imp_RtlNtStatusToDosError
0x180003935  jmp     short loc_180003954
0x180003937  mov     rax, [rsp+48h+KeyPath.Buffer]
0x18000393c  mov     r9d, 2000000h
0x180003942  mov     [rsp+48h+var_28], rbx
0x180003947  xor     r8d, r8d
0x18000394a  mov     rdx, rax
0x18000394d  xor     ecx, ecx
0x18000394f  call    pSetupOpenKey
0x180003954  mov     ebx, eax
0x180003956  cmp     [rsp+48h+KeyPath.Buffer], 0
0x18000395c  jz      short loc_180003969
0x18000395e  lea     rcx, [rsp+48h+KeyPath]; UnicodeString
0x180003963  call    cs:__imp_RtlFreeUnicodeString
0x180003969  mov     eax, ebx
0x18000396b  add     rsp, 40h
0x18000396f  pop     rbx
0x180003970  retn
0x180003971  call    pSetupGetPredefinedKeyPath
0x180003976  test    rax, rax
0x180003979  jnz     short loc_18000393C
0x18000397b  lea     ebx, [rax+32h]
0x18000397e  jmp     short loc_180003956
```
