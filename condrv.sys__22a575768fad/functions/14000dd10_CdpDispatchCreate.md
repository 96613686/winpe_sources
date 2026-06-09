# CdpDispatchCreate

- ea: `0x14000dd10`
- end: `0x14000dda9`
- name: `CdpDispatchCreate`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000dd10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000dd96`
- `ntoskrnl!IofCompleteRequest` at `0x14000dd96`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000dd4c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000dd4c`

## pseudocode

```c
__int64 __fastcall CdpDispatchCreate(__int64 a1, IRP *a2)
{
  unsigned int v3; // ebx
  PFILE_OBJECT FileObject; // rsi
  __int64 v5; // rdi

  v3 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  while ( v3 < 0xB )
  {
    v5 = 4LL * v3;
    if ( !RtlCompareUnicodeString(&FileObject->FileName, (PCUNICODE_STRING)&CdpObjectCreationTable[v5], 1u) )
      return ((__int64 (__fastcall *)(IRP *, _QWORD))CdpObjectCreationTable[v5 + 2])(
               a2,
               LODWORD(CdpObjectCreationTable[v5 + 3]));
    ++v3;
  }
  a2->IoStatus.Status = -1073741275;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14000dd10  push    rbx
0x14000dd12  push    rbp
0x14000dd13  push    rsi
0x14000dd14  push    r14
0x14000dd16  sub     rsp, 28h
0x14000dd1a  mov     rax, [rdx+0B8h]
0x14000dd21  lea     r14, CdpObjectCreationTable
0x14000dd28  mov     rbp, rdx
0x14000dd2b  mov     [rsp+48h+arg_0], rdi
0x14000dd30  xor     ebx, ebx
0x14000dd32  mov     rsi, [rax+30h]
0x14000dd36  cmp     ebx, 0Bh
0x14000dd39  jnb     short loc_14000DD82
0x14000dd3b  mov     edi, ebx
0x14000dd3d  lea     rcx, [rsi+58h]; String1
0x14000dd41  shl     rdi, 5
0x14000dd45  mov     r8b, 1; CaseInSensitive
0x14000dd48  lea     rdx, [rdi+r14]; String2
0x14000dd4c  call    cs:__imp_RtlCompareUnicodeString
0x14000dd53  nop     dword ptr [rax+rax+00h]
0x14000dd58  test    eax, eax
0x14000dd5a  jz      short loc_14000DD60
0x14000dd5c  inc     ebx
0x14000dd5e  jmp     short loc_14000DD36
0x14000dd60  mov     rax, [rdi+r14+10h]
0x14000dd65  mov     rcx, rbp
0x14000dd68  mov     edx, [rdi+r14+18h]
0x14000dd6d  call    _guard_dispatch_icall
0x14000dd72  mov     rdi, [rsp+48h+arg_0]
0x14000dd77  add     rsp, 28h
0x14000dd7b  pop     r14
0x14000dd7d  pop     rsi
0x14000dd7e  pop     rbp
0x14000dd7f  pop     rbx
0x14000dd80  retn
0x14000dd82  xor     edx, edx; PriorityBoost
0x14000dd84  mov     dword ptr [rbp+30h], 0C0000225h
0x14000dd8b  mov     rcx, rbp; Irp
0x14000dd8e  mov     qword ptr [rbp+38h], 0
0x14000dd96  call    cs:__imp_IofCompleteRequest
0x14000dd9d  nop     dword ptr [rax+rax+00h]
0x14000dda2  mov     eax, 0C0000225h
0x14000dda7  jmp     short loc_14000DD72
```
