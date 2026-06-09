# OpenIptDevice

- ea: `0x18002a13c`
- end: `0x18002a1b4`
- name: `OpenIptDevice`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180013510`
- `0x1800269bc`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18002a1a6`
- `ntdll!NtCreateFile` at `0x18002a1a6`

## pseudocode

```c
NTSTATUS __fastcall OpenIptDevice(void **a1)
{
  struct _IO_STATUS_BLOCK v2; // [rsp+60h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v3; // [rsp+70h] [rbp-38h] BYREF

  *(_QWORD *)&v3.Length = 48;
  v3.ObjectName = (PUNICODE_STRING)&qword_18003C038;
  memset(&v3.Attributes, 0, 24);
  v3.RootDirectory = 0;
  v2 = 0;
  return NtCreateFile(a1, 0x120089u, &v3, &v2, 0, 0x80u, 1u, 1u, 0x4Cu, 0, 0);
}

```

## disassembly

```asm
0x18002a13c  mov     r11, rsp
0x18002a13f  sub     rsp, 0A8h
0x18002a146  xor     edx, edx
0x18002a148  mov     qword ptr [r11-38h], 30h ; '0'
0x18002a150  mov     [rsp+0A8h+EaLength], edx; EaLength
0x18002a154  lea     rax, qword_18003C038
0x18002a15b  mov     [r11-60h], rdx
0x18002a15f  lea     r9, [r11-48h]; IoStatusBlock
0x18002a163  mov     [rsp+0A8h+CreateOptions], 4Ch ; 'L'; CreateOptions
0x18002a16b  lea     r8, [r11-38h]; ObjectAttributes
0x18002a16f  xorps   xmm0, xmm0
0x18002a172  mov     [r11-28h], rax
0x18002a176  lea     eax, [rdx+1]
0x18002a179  mov     [r11-20h], rdx
0x18002a17d  mov     [rsp+0A8h+CreateDisposition], eax; CreateDisposition
0x18002a181  mov     [rsp+0A8h+ShareAccess], eax; ShareAccess
0x18002a185  mov     [r11-30h], rdx
0x18002a189  mov     [rsp+0A8h+FileAttributes], 80h; FileAttributes
0x18002a191  mov     [rsp+0A8h+AllocationSize], rdx; AllocationSize
0x18002a196  mov     edx, 120089h; DesiredAccess
0x18002a19b  movups  [rsp+0A8h+var_48], xmm0
0x18002a1a0  movdqu  xmmword ptr [r11-18h], xmm0
0x18002a1a6  call    cs:__imp_NtCreateFile
0x18002a1ac  add     rsp, 0A8h
0x18002a1b3  retn
```
