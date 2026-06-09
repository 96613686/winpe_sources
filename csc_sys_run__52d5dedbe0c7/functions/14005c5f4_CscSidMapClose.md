# CscSidMapClose

- ea: `0x14005c5f4`
- end: `0x14005c6b8`
- name: `CscSidMapClose`
- size: `196`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400269c4`
- `0x14008df70`

## callees

- `0x140010f6c`
- `0x1400287bc`
- `0x14005c5f4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005c684`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c6a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c684`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c6a0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005c670`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005c670`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005c62b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005c642`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005c62b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005c642`

## pseudocode

```c
void __fastcall CscSidMapClose(char *P)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rdi

  if ( P )
  {
    v2 = (void *)*((_QWORD *)P + 7);
    if ( v2 )
    {
      CscSidMappDestroySidArray(v2);
      *((_QWORD *)P + 7) = 0;
    }
    if ( *((_QWORD *)P + 6) )
      RtlFreeUnicodeString((PUNICODE_STRING)(P + 40));
    if ( *((_QWORD *)P + 4) )
      RtlFreeUnicodeString((PUNICODE_STRING)(P + 24));
    v3 = *((_QWORD *)P + 2);
    if ( v3 )
    {
      CscStorepLowIoClosePoster(v3);
      *((_QWORD *)P + 2) = 0;
    }
    v4 = (void *)*((_QWORD *)P + 1);
    if ( v4 )
    {
      ExDeleteResourceLite(*((PERESOURCE *)P + 1));
      ExFreePoolWithTag(v4, 0x22407343u);
      *((_QWORD *)P + 1) = 0;
    }
    ExFreePoolWithTag(P, 0x23407343u);
  }
}

```

## disassembly

```asm
0x14005c5f4  test    rcx, rcx
0x14005c5f7  jz      locret_14005C6B6
0x14005c5fd  mov     [rsp+arg_0], rbx
0x14005c602  push    rdi
0x14005c603  sub     rsp, 20h
0x14005c607  mov     rbx, rcx
0x14005c60a  mov     rcx, [rcx+38h]; P
0x14005c60e  test    rcx, rcx
0x14005c611  jz      short loc_14005C620
0x14005c613  call    CscSidMappDestroySidArray
0x14005c618  mov     qword ptr [rbx+38h], 0
0x14005c620  cmp     qword ptr [rbx+30h], 0
0x14005c625  jz      short loc_14005C637
0x14005c627  lea     rcx, [rbx+28h]; UnicodeString
0x14005c62b  call    cs:__imp_RtlFreeUnicodeString
0x14005c632  nop     dword ptr [rax+rax+00h]
0x14005c637  cmp     qword ptr [rbx+20h], 0
0x14005c63c  jz      short loc_14005C64E
0x14005c63e  lea     rcx, [rbx+18h]; UnicodeString
0x14005c642  call    cs:__imp_RtlFreeUnicodeString
0x14005c649  nop     dword ptr [rax+rax+00h]
0x14005c64e  mov     rcx, [rbx+10h]
0x14005c652  test    rcx, rcx
0x14005c655  jz      short loc_14005C664
0x14005c657  call    CscStorepLowIoClosePoster
0x14005c65c  mov     qword ptr [rbx+10h], 0
0x14005c664  mov     rdi, [rbx+8]
0x14005c668  test    rdi, rdi
0x14005c66b  jz      short loc_14005C698
0x14005c66d  mov     rcx, rdi; Resource
0x14005c670  call    cs:__imp_ExDeleteResourceLite
0x14005c677  nop     dword ptr [rax+rax+00h]
0x14005c67c  mov     edx, 22407343h; Tag
0x14005c681  mov     rcx, rdi; P
0x14005c684  call    cs:__imp_ExFreePoolWithTag
0x14005c68b  nop     dword ptr [rax+rax+00h]
0x14005c690  mov     qword ptr [rbx+8], 0
0x14005c698  mov     edx, 23407343h; Tag
0x14005c69d  mov     rcx, rbx; P
0x14005c6a0  call    cs:__imp_ExFreePoolWithTag
0x14005c6a7  nop     dword ptr [rax+rax+00h]
0x14005c6ac  mov     rbx, [rsp+28h+arg_0]
0x14005c6b1  add     rsp, 20h
0x14005c6b5  pop     rdi
0x14005c6b6  retn
```
