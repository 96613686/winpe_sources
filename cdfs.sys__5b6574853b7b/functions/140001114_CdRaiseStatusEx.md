# CdRaiseStatusEx

- ea: `0x140001114`
- end: `0x14000115a`
- name: `CdRaiseStatusEx`
- size: `70`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `37`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400028e0`
- `0x14000b008`
- `0x14000b1a4`
- `0x14000b684`
- `0x14000c8b4`
- `0x14000d400`
- `0x14000e978`
- `0x14000edcc`
- `0x14000f060`
- `0x14000f27c`
- `0x14000f618`
- `0x14000fe14`
- `0x140010098`
- `0x140010700`
- `0x140010c38`
- `0x140011138`
- `0x140011744`
- `0x140011fd4`
- `0x140012508`
- `0x14001292c`
- `0x140012a14`
- `0x1400135d0`
- `0x140013e2c`
- `0x140015fac`
- `0x14001617c`
- `0x1400166ac`
- `0x140016c58`
- `0x1400176a8`
- `0x140017ab8`
- `0x1400181a4`
- `0x1400184f4`
- `0x140018790`
- `0x140018bec`
- `0x140019a00`
- `0x14001a2a0`
- `0x14001a400`
- `0x14001aa78`

## callees

- `0x140001114`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14000114d`
- `ntoskrnl!ExRaiseStatus` at `0x14000114d`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140001132`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140001132`

## pseudocode

```c
void __fastcall __noreturn CdRaiseStatusEx(__int64 a1, NTSTATUS a2, char a3, int a4, int a5)
{
  NTSTATUS v6; // eax

  v6 = a2;
  if ( a3 )
    v6 = FsRtlNormalizeNtstatus(a2, -1073741591);
  *(_DWORD *)(a1 + 24) = v6;
  *(_DWORD *)(a1 + 28) = a5 | (a4 << 16);
  ExRaiseStatus(v6);
}

```

## disassembly

```asm
0x140001114  mov     [rsp+arg_0], rbx
0x140001119  push    rdi
0x14000111a  sub     rsp, 20h
0x14000111e  mov     ebx, r9d
0x140001121  mov     eax, edx
0x140001123  mov     rdi, rcx
0x140001126  test    r8b, r8b
0x140001129  jz      short loc_14000113E
0x14000112b  mov     edx, 0C00000E9h; GenericException
0x140001130  mov     ecx, eax; Exception
0x140001132  call    cs:__imp_FsRtlNormalizeNtstatus
0x140001139  nop     dword ptr [rax+rax+00h]
0x14000113e  shl     ebx, 10h
0x140001141  mov     ecx, eax; Status
0x140001143  or      ebx, [rsp+28h+arg_20]
0x140001147  mov     [rdi+18h], eax
0x14000114a  mov     [rdi+1Ch], ebx
0x14000114d  call    cs:__imp_ExRaiseStatus
```
