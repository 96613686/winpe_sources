# CdpDispatchSetSecurity

- ea: `0x1400082f0`
- end: `0x140008381`
- name: `CdpDispatchSetSecurity`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x1400082f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140008331`
- `ntoskrnl!IofCompleteRequest` at `0x14000836a`
- `ntoskrnl!IofCompleteRequest` at `0x140008331`
- `ntoskrnl!IofCompleteRequest` at `0x14000836a`

## pseudocode

```c
__int64 __fastcall CdpDispatchSetSecurity(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[9] )
    {
      return v4[9](&FsContext[-*(unsigned int *)v4], a2);
    }
    else
    {
      a2->IoStatus.Status = -1073741637;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 0);
      return 3221225659LL;
    }
  }
  else
  {
    a2->IoStatus.Status = -1073741811;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400082f0  sub     rsp, 28h
0x1400082f4  mov     rax, [rdx+0B8h]
0x1400082fb  mov     r8, rdx
0x1400082fe  mov     rcx, [rax+30h]
0x140008302  test    rcx, rcx
0x140008305  jz      short loc_140008356
0x140008307  mov     rcx, [rcx+18h]
0x14000830b  test    rcx, rcx
0x14000830e  jz      short loc_140008356
0x140008310  mov     rax, [rcx]
0x140008313  test    rax, rax
0x140008316  jz      short loc_140008356
0x140008318  mov     r9, [rax+48h]
0x14000831c  test    r9, r9
0x14000831f  jnz     short loc_140008344
0x140008321  mov     dword ptr [rdx+30h], 0C00000BBh
0x140008328  mov     rcx, r8; Irp
0x14000832b  mov     [rdx+38h], r9
0x14000832f  xor     edx, edx; PriorityBoost
0x140008331  call    cs:__imp_IofCompleteRequest
0x140008338  nop     dword ptr [rax+rax+00h]
0x14000833d  mov     eax, 0C00000BBh
0x140008342  jmp     short loc_14000837B
0x140008344  mov     edx, [rax]
0x140008346  mov     rax, r9
0x140008349  sub     rcx, rdx
0x14000834c  mov     rdx, r8
0x14000834f  call    _guard_dispatch_icall
0x140008354  jmp     short loc_14000837B
0x140008356  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000835d  mov     rcx, r8; Irp
0x140008360  mov     qword ptr [rdx+38h], 0
0x140008368  xor     edx, edx; PriorityBoost
0x14000836a  call    cs:__imp_IofCompleteRequest
0x140008371  nop     dword ptr [rax+rax+00h]
0x140008376  mov     eax, 0C000000Dh
0x14000837b  add     rsp, 28h
0x14000837f  retn
```
