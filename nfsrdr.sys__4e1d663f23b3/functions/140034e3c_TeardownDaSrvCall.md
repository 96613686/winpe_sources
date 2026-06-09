# TeardownDaSrvCall

- ea: `0x140034e3c`
- end: `0x140034f88`
- name: `TeardownDaSrvCall`
- size: `332`
- prototype: `void __fastcall(char *P, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140009f60`
- `0x140034990`

## callees

- `0x14002d1e4`
- `0x140034a64`
- `0x140034e3c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140034f02`
- `ntoskrnl!ExDeleteResourceLite` at `0x140034f28`
- `ntoskrnl!ExDeleteResourceLite` at `0x140034f4e`
- `ntoskrnl!ExDeleteResourceLite` at `0x140034f02`
- `ntoskrnl!ExDeleteResourceLite` at `0x140034f28`
- `ntoskrnl!ExDeleteResourceLite` at `0x140034f4e`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140034e5a`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140034e5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034eb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034eb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034f70`

## pseudocode

```c
void __fastcall TeardownDaSrvCall(char *P, __int64 a2)
{
  __int64 v3; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE *v5; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *v6; // rdi
  void *v7; // rcx
  PERESOURCE *v8; // rdi
  struct _ERESOURCE *v9; // rcx

  v3 = *((_QWORD *)P + 29);
  if ( v3 )
  {
    while ( 1 )
    {
      LOBYTE(a2) = 1;
      UnicodePrefix = (struct _UNICODE_PREFIX_TABLE_ENTRY *)MdaTryNextUnicodePrefix(v3, a2);
      v5 = (struct _UNICODE_PREFIX_TABLE *)*((_QWORD *)P + 29);
      v6 = UnicodePrefix;
      if ( !UnicodePrefix )
        break;
      RtlRemoveUnicodePrefix(v5, UnicodePrefix);
      ExFreePoolWithTag(v6, 0);
      v3 = *((_QWORD *)P + 29);
    }
    ExFreePoolWithTag(v5, 0);
  }
  v7 = (void *)*((_QWORD *)P + 27);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( *((_QWORD *)P + 13) )
    NfsForceDisconnect((__int64)(P + 72), 1);
  if ( *((_QWORD *)P + 4) )
    NfsForceDisconnect((__int64)P, 1);
  v8 = (PERESOURCE *)(P + 144);
  if ( *((_QWORD *)P + 22) )
    NfsForceDisconnect((__int64)(P + 144), 1);
  if ( *v8 )
  {
    ExDeleteResourceLite(*v8);
    ExFreePoolWithTag(*v8, 0);
  }
  v9 = (struct _ERESOURCE *)*((_QWORD *)P + 9);
  if ( v9 )
  {
    ExDeleteResourceLite(v9);
    ExFreePoolWithTag(*((PVOID *)P + 9), 0);
  }
  if ( *(_QWORD *)P )
  {
    ExDeleteResourceLite(*(PERESOURCE *)P);
    ExFreePoolWithTag(*(PVOID *)P, 0);
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140034e3c  mov     [rsp+arg_0], rbx
0x140034e41  push    rdi
0x140034e42  sub     rsp, 20h
0x140034e46  mov     rbx, rcx
0x140034e49  mov     rcx, [rcx+0E8h]
0x140034e50  test    rcx, rcx
0x140034e53  jz      short loc_140034EA2
0x140034e55  jmp     short loc_140034E7E
0x140034e57  mov     rdx, rdi; PrefixTableEntry
0x140034e5a  call    cs:__imp_RtlRemoveUnicodePrefix
0x140034e61  nop     dword ptr [rax+rax+00h]
0x140034e66  xor     edx, edx; Tag
0x140034e68  mov     rcx, rdi; P
0x140034e6b  call    cs:__imp_ExFreePoolWithTag
0x140034e72  nop     dword ptr [rax+rax+00h]
0x140034e77  mov     rcx, [rbx+0E8h]
0x140034e7e  mov     dl, 1
0x140034e80  call    MdaTryNextUnicodePrefix
0x140034e85  mov     rcx, [rbx+0E8h]; P
0x140034e8c  mov     rdi, rax
0x140034e8f  test    rax, rax
0x140034e92  jnz     short loc_140034E57
0x140034e94  xor     edx, edx; Tag
0x140034e96  call    cs:__imp_ExFreePoolWithTag
0x140034e9d  nop     dword ptr [rax+rax+00h]
0x140034ea2  mov     rcx, [rbx+0D8h]; P
0x140034ea9  test    rcx, rcx
0x140034eac  jz      short loc_140034EBC
0x140034eae  xor     edx, edx; Tag
0x140034eb0  call    cs:__imp_ExFreePoolWithTag
0x140034eb7  nop     dword ptr [rax+rax+00h]
0x140034ebc  cmp     qword ptr [rbx+68h], 0
0x140034ec1  jz      short loc_140034ECE
0x140034ec3  lea     rcx, [rbx+48h]
0x140034ec7  mov     dl, 1
0x140034ec9  call    NfsForceDisconnect
0x140034ece  cmp     qword ptr [rbx+20h], 0
0x140034ed3  jz      short loc_140034EDF
0x140034ed5  mov     dl, 1
0x140034ed7  mov     rcx, rbx
0x140034eda  call    NfsForceDisconnect
0x140034edf  cmp     qword ptr [rbx+0B0h], 0
0x140034ee7  lea     rdi, [rbx+90h]
0x140034eee  jz      short loc_140034EFA
0x140034ef0  mov     dl, 1
0x140034ef2  mov     rcx, rdi
0x140034ef5  call    NfsForceDisconnect
0x140034efa  mov     rcx, [rdi]; Resource
0x140034efd  test    rcx, rcx
0x140034f00  jz      short loc_140034F1F
0x140034f02  call    cs:__imp_ExDeleteResourceLite
0x140034f09  nop     dword ptr [rax+rax+00h]
0x140034f0e  mov     rcx, [rdi]; P
0x140034f11  xor     edx, edx; Tag
0x140034f13  call    cs:__imp_ExFreePoolWithTag
0x140034f1a  nop     dword ptr [rax+rax+00h]
0x140034f1f  mov     rcx, [rbx+48h]; Resource
0x140034f23  test    rcx, rcx
0x140034f26  jz      short loc_140034F46
0x140034f28  call    cs:__imp_ExDeleteResourceLite
0x140034f2f  nop     dword ptr [rax+rax+00h]
0x140034f34  mov     rcx, [rbx+48h]; P
0x140034f38  xor     edx, edx; Tag
0x140034f3a  call    cs:__imp_ExFreePoolWithTag
0x140034f41  nop     dword ptr [rax+rax+00h]
0x140034f46  mov     rcx, [rbx]; Resource
0x140034f49  test    rcx, rcx
0x140034f4c  jz      short loc_140034F6B
0x140034f4e  call    cs:__imp_ExDeleteResourceLite
0x140034f55  nop     dword ptr [rax+rax+00h]
0x140034f5a  mov     rcx, [rbx]; P
0x140034f5d  xor     edx, edx; Tag
0x140034f5f  call    cs:__imp_ExFreePoolWithTag
0x140034f66  nop     dword ptr [rax+rax+00h]
0x140034f6b  xor     edx, edx; Tag
0x140034f6d  mov     rcx, rbx; P
0x140034f70  call    cs:__imp_ExFreePoolWithTag
0x140034f77  nop     dword ptr [rax+rax+00h]
0x140034f7c  mov     rbx, [rsp+28h+arg_0]
0x140034f81  add     rsp, 20h
0x140034f85  pop     rdi
0x140034f86  retn
```
