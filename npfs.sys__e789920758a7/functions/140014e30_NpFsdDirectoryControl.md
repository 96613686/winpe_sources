# NpFsdDirectoryControl

- ea: `0x140014e30`
- end: `0x140014ece`
- name: `NpFsdDirectoryControl`
- size: `158`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140014e30`
- `0x140014ed4`
- `0x140015444`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014e94`
- `ntoskrnl!IofCompleteRequest` at `0x140014e94`

## pseudocode

```c
__int64 __fastcall NpFsdDirectoryControl(__int64 a1, IRP *a2)
{
  __int64 v2; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  PFILE_OBJECT FileObject; // rdx
  unsigned __int64 v6; // rdx
  int v7; // ecx
  unsigned int Directory; // eax
  unsigned int v9; // ebx

  v2 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( ((__int64)FileObject->FsContext2 & 1) == 0
    || *(_WORD *)FileObject->FsContext != 518
    || (v6 = (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = -1073741811;
    goto LABEL_8;
  }
  v7 = CurrentStackLocation->MinorFunction - 1;
  if ( !v7 )
  {
    Directory = NpQueryDirectory(v2, v6, (__int64)a2);
LABEL_6:
    v9 = Directory;
    goto LABEL_7;
  }
  if ( v7 == 1 )
  {
    Directory = NpNotifyChangeDirectory(v2, v6, (__int64)a2);
    goto LABEL_6;
  }
  v9 = -1073741808;
LABEL_7:
  if ( v9 != 259 )
  {
LABEL_8:
    a2->IoStatus.Status = v9;
    IofCompleteRequest(a2, 2);
  }
  return v9;
}

```

## disassembly

```asm
0x140014e30  mov     [rsp+arg_0], rbx
0x140014e35  push    rdi
0x140014e36  sub     rsp, 20h
0x140014e3a  mov     r9, [rcx+40h]
0x140014e3e  mov     rdi, rdx
0x140014e41  mov     rcx, [rdx+0B8h]
0x140014e48  mov     rdx, [rcx+30h]
0x140014e4c  mov     rax, [rdx+20h]
0x140014e50  test    al, 1
0x140014e52  jz      short loc_140014EAE
0x140014e54  mov     rax, [rdx+18h]
0x140014e58  mov     r8d, 206h
0x140014e5e  cmp     r8w, [rax]
0x140014e62  jnz     short loc_140014EAE
0x140014e64  mov     rdx, [rdx+20h]
0x140014e68  and     rdx, 0FFFFFFFFFFFFFFFEh
0x140014e6c  jz      short loc_140014EAE
0x140014e6e  movzx   ecx, byte ptr [rcx+1]
0x140014e72  sub     ecx, 1
0x140014e75  jnz     short loc_140014EB5
0x140014e77  mov     r8, rdi
0x140014e7a  mov     rcx, r9
0x140014e7d  call    NpQueryDirectory
0x140014e82  mov     ebx, eax
0x140014e84  cmp     ebx, 103h
0x140014e8a  jz      short loc_140014EA0
0x140014e8c  mov     dl, 2; PriorityBoost
0x140014e8e  mov     [rdi+30h], ebx
0x140014e91  mov     rcx, rdi; Irp
0x140014e94  call    cs:__imp_IofCompleteRequest
0x140014e9b  nop     dword ptr [rax+rax+00h]
0x140014ea0  mov     eax, ebx
0x140014ea2  mov     rbx, [rsp+28h+arg_0]
0x140014ea7  add     rsp, 20h
0x140014eab  pop     rdi
0x140014eac  retn
0x140014eae  mov     ebx, 0C000000Dh
0x140014eb3  jmp     short loc_140014E8C
0x140014eb5  cmp     ecx, 1
0x140014eb8  jnz     short loc_140014EC7
0x140014eba  mov     r8, rdi
0x140014ebd  mov     rcx, r9
0x140014ec0  call    NpNotifyChangeDirectory
0x140014ec5  jmp     short loc_140014E82
0x140014ec7  mov     ebx, 0C0000010h
0x140014ecc  jmp     short loc_140014E84
```
