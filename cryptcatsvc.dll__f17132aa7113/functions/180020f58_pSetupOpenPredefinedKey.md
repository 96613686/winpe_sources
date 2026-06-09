# pSetupOpenPredefinedKey

- ea: `0x180020f58`
- end: `0x180020fcf`
- name: `pSetupOpenPredefinedKey`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020e58`

## callees

- `0x180020e04`
- `0x180020f3c`
- `0x180020f58`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180020f77`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180020f77`
- `ntdll!RtlFreeUnicodeString` at `0x180020fb2`
- `ntdll!RtlFreeUnicodeString` at `0x180020fb2`
- `ntdll!RtlNtStatusToDosError` at `0x180020f83`
- `ntdll!RtlNtStatusToDosError` at `0x180020f83`

## pseudocode

```c
__int64 __fastcall pSetupOpenPredefinedKey(__int64 a1, __int64 a2)
{
  int v3; // eax
  ULONG v4; // eax
  PWSTR Buffer; // rax
  unsigned int v6; // ebx
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-18h] BYREF

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
    v4 = pSetupOpenKeyEx(0, Buffer, 0x2000000, a2, *(_QWORD *)&KeyPath.Length);
    goto LABEL_6;
  }
  Buffer = (PWSTR)pSetupGetPredefinedKeyPath(a1);
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
0x180020f58  push    rbx
0x180020f5a  sub     rsp, 30h
0x180020f5e  xorps   xmm0, xmm0
0x180020f61  mov     rbx, rdx
0x180020f64  movups  xmmword ptr [rsp+38h+KeyPath.Length], xmm0
0x180020f69  cmp     rcx, 0FFFFFFFF80000001h
0x180020f70  jnz     short loc_180020FC0
0x180020f72  lea     rcx, [rsp+38h+KeyPath]; KeyPath
0x180020f77  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180020f7d  test    eax, eax
0x180020f7f  jns     short loc_180020F8B
0x180020f81  mov     ecx, eax; Status
0x180020f83  call    cs:__imp_RtlNtStatusToDosError
0x180020f89  jmp     short loc_180020FA3
0x180020f8b  mov     rax, [rsp+38h+KeyPath.Buffer]
0x180020f90  mov     r9, rbx
0x180020f93  mov     r8d, 2000000h
0x180020f99  mov     rdx, rax
0x180020f9c  xor     ecx, ecx
0x180020f9e  call    pSetupOpenKeyEx
0x180020fa3  mov     ebx, eax
0x180020fa5  cmp     [rsp+38h+KeyPath.Buffer], 0
0x180020fab  jz      short loc_180020FB8
0x180020fad  lea     rcx, [rsp+38h+KeyPath]; UnicodeString
0x180020fb2  call    cs:__imp_RtlFreeUnicodeString
0x180020fb8  mov     eax, ebx
0x180020fba  add     rsp, 30h
0x180020fbe  pop     rbx
0x180020fbf  retn
0x180020fc0  call    pSetupGetPredefinedKeyPath
0x180020fc5  test    rax, rax
0x180020fc8  jnz     short loc_180020F90
0x180020fca  lea     ebx, [rax+32h]
0x180020fcd  jmp     short loc_180020FA5
```
