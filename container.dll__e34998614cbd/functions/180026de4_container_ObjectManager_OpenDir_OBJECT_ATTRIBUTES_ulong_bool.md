# container::ObjectManager::OpenDir(_OBJECT_ATTRIBUTES *,ulong,bool)

- ea: `0x180026de4`
- end: `0x180026e73`
- name: `?OpenDir@ObjectManager@container@@YAPEAXPEAU_OBJECT_ATTRIBUTES@@K_N@Z`
- size: `143`
- prototype: `void *__fastcall(POBJECT_ATTRIBUTES ObjectAttributes, struct _OBJECT_ATTRIBUTES *, unsigned int, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180026b68`
- `0x180026f60`
- `0x180027254`

## callees

- `0x180026de4`
- `0x18002759c`

## import_xrefs

- `ntdll!NtOpenDirectoryObject` at `0x180026e05`
- `ntdll!NtOpenDirectoryObject` at `0x180026e05`

## string_xrefs

- `0x180026e61`: `OpenDirectoryObject(%ws) failed`

## pseudocode

```c
void *__fastcall container::ObjectManager::OpenDir(
        POBJECT_ATTRIBUTES ObjectAttributes,
        struct _OBJECT_ATTRIBUTES *a2,
        char a3)
{
  NTSTATUS v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *FileHandle; // [rsp+58h] [rbp+20h] BYREF

  FileHandle = 0;
  v5 = NtOpenDirectoryObject(&FileHandle, (ACCESS_MASK)a2, ObjectAttributes);
  if ( v5 >= 0 )
    return FileHandle;
  if ( v5 != -1073741772 && v5 != -1073741766 || a3 )
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x25D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
      (const char *)(unsigned int)v5,
      (int)"OpenDirectoryObject(%ws) failed",
      (const char *)ObjectAttributes->ObjectName->Buffer);
  return 0;
}

```

## disassembly

```asm
0x180026de4  mov     [rsp+arg_0], rbx
0x180026de9  push    rdi
0x180026dea  sub     rsp, 30h
0x180026dee  mov     bl, r8b
0x180026df1  mov     [rsp+38h+FileHandle], 0
0x180026dfa  mov     r8, rcx; ObjectAttributes
0x180026dfd  mov     rdi, rcx
0x180026e00  lea     rcx, [rsp+38h+FileHandle]; FileHandle
0x180026e05  call    cs:__imp_NtOpenDirectoryObject
0x180026e0c  nop     dword ptr [rax+rax+00h]
0x180026e11  mov     r9d, eax; char *
0x180026e14  test    eax, eax
0x180026e16  js      short loc_180026E29
0x180026e18  mov     rax, [rsp+38h+FileHandle]
0x180026e1d  mov     rbx, [rsp+38h+arg_0]
0x180026e22  add     rsp, 30h
0x180026e26  pop     rdi
0x180026e27  retn
0x180026e29  cmp     r9d, 0C0000034h
0x180026e30  jz      short loc_180026E3B
0x180026e32  cmp     r9d, 0C000003Ah
0x180026e39  jnz     short loc_180026E43
0x180026e3b  test    bl, bl
0x180026e3d  jnz     short loc_180026E43
0x180026e3f  xor     eax, eax
0x180026e41  jmp     short loc_180026E1D
0x180026e43  mov     rax, [rdi+10h]
0x180026e47  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026e4e  mov     rcx, [rsp+38h]; this
0x180026e53  mov     edx, 25Dh; void *
0x180026e58  mov     rax, [rax+8]
0x180026e5c  mov     [rsp+38h+var_10], rax; char *
0x180026e61  lea     rax, aOpendirectoryo; "OpenDirectoryObject(%ws) failed"
0x180026e68  mov     qword ptr [rsp+38h+var_18], rax; int
0x180026e6d  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
