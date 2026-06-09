# CdpClientIoctl

- ea: `0x1400093b0`
- end: `0x140009417`
- name: `CdpClientIoctl`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400093b0`
- `0x140009760`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400093fb`
- `ntoskrnl!IofCompleteRequest` at `0x1400093fb`

## pseudocode

```c
__int64 __fastcall CdpClientIoctl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v4; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5242902 )
  {
    if ( (CurrentStackLocation->FileObject->Flags & 2) != 0 )
      return CdClientUserIo(a1, (__int64)a2);
    v4 = -1073741811;
  }
  else
  {
    v4 = -1073741808;
  }
  a2->IoStatus.Status = v4;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v4;
}

```

## disassembly

```asm
0x1400093b0  push    rbx
0x1400093b2  sub     rsp, 20h
0x1400093b6  mov     rax, [rdx+0B8h]
0x1400093bd  mov     r8, rdx
0x1400093c0  mov     r9, rcx
0x1400093c3  cmp     dword ptr [rax+18h], 500016h
0x1400093ca  jnz     short loc_1400093E6
0x1400093cc  mov     rcx, [rax+30h]
0x1400093d0  mov     eax, [rcx+50h]
0x1400093d3  test    al, 2
0x1400093d5  jz      short loc_140009410
0x1400093d7  mov     rcx, r9
0x1400093da  call    CdClientUserIo
0x1400093df  add     rsp, 20h
0x1400093e3  pop     rbx
0x1400093e4  retn
0x1400093e6  mov     ebx, 0C0000010h
0x1400093eb  mov     [rdx+30h], ebx
0x1400093ee  mov     rcx, r8; Irp
0x1400093f1  mov     qword ptr [rdx+38h], 0
0x1400093f9  xor     edx, edx; PriorityBoost
0x1400093fb  call    cs:__imp_IofCompleteRequest
0x140009402  nop     dword ptr [rax+rax+00h]
0x140009407  mov     eax, ebx
0x140009409  add     rsp, 20h
0x14000940d  pop     rbx
0x14000940e  retn
0x140009410  mov     ebx, 0C000000Dh
0x140009415  jmp     short loc_1400093EB
```
