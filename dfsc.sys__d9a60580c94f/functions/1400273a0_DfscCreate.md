# DfscCreate

- ea: `0x1400273a0`
- end: `0x1400273e6`
- name: `DfscCreate`
- size: `70`
- prototype: `__int64 __fastcall(void *, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400273a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400273ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400273ca`

## pseudocode

```c
__int64 __fastcall DfscCreate(void *a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // r8
  unsigned int v3; // ebx

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject->FileName.Length )
  {
    v3 = -1073741808;
  }
  else
  {
    FileObject->FsContext = a1;
    v3 = 0;
  }
  a2->IoStatus.Status = v3;
  IofCompleteRequest(a2, 0);
  return v3;
}

```

## disassembly

```asm
0x1400273a0  push    rbx
0x1400273a2  sub     rsp, 20h
0x1400273a6  mov     rax, rdx
0x1400273a9  mov     rdx, [rdx+0B8h]
0x1400273b0  mov     r8, [rdx+30h]
0x1400273b4  cmp     word ptr [r8+58h], 0
0x1400273ba  jnz     short loc_1400273DF
0x1400273bc  mov     [r8+18h], rcx
0x1400273c0  xor     ebx, ebx
0x1400273c2  xor     edx, edx; PriorityBoost
0x1400273c4  mov     [rax+30h], ebx
0x1400273c7  mov     rcx, rax; Irp
0x1400273ca  call    cs:__imp_IofCompleteRequest
0x1400273d1  nop     dword ptr [rax+rax+00h]
0x1400273d6  mov     eax, ebx
0x1400273d8  add     rsp, 20h
0x1400273dc  pop     rbx
0x1400273dd  retn
0x1400273df  mov     ebx, 0C0000010h
0x1400273e4  jmp     short loc_1400273C2
```
