# CdpDispatchWrite

- ea: `0x14000dc70`
- end: `0x14000dd01`
- name: `CdpDispatchWrite`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000dc70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000dcc9`
- `ntoskrnl!IofCompleteRequest` at `0x14000dcee`
- `ntoskrnl!IofCompleteRequest` at `0x14000dcc9`
- `ntoskrnl!IofCompleteRequest` at `0x14000dcee`

## pseudocode

```c
__int64 __fastcall CdpDispatchWrite(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[2] )
    {
      return v4[2](&FsContext[-*(unsigned int *)v4], a2);
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
0x14000dc70  sub     rsp, 28h
0x14000dc74  mov     rax, [rdx+0B8h]
0x14000dc7b  mov     r8, rdx
0x14000dc7e  mov     rcx, [rax+30h]
0x14000dc82  test    rcx, rcx
0x14000dc85  jz      short loc_14000DCB7
0x14000dc87  mov     rcx, [rcx+18h]
0x14000dc8b  test    rcx, rcx
0x14000dc8e  jz      short loc_14000DCB7
0x14000dc90  mov     rax, [rcx]
0x14000dc93  test    rax, rax
0x14000dc96  jz      short loc_14000DCB7
0x14000dc98  mov     r9, [rax+10h]
0x14000dc9c  test    r9, r9
0x14000dc9f  jz      short loc_14000DCDC
0x14000dca1  mov     edx, [rax]
0x14000dca3  mov     rax, r9
0x14000dca6  sub     rcx, rdx
0x14000dca9  mov     rdx, r8
0x14000dcac  call    _guard_dispatch_icall
0x14000dcb1  add     rsp, 28h
0x14000dcb5  retn
0x14000dcb7  xor     ecx, ecx
0x14000dcb9  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000dcc0  mov     [rdx+38h], rcx
0x14000dcc4  xor     edx, edx; PriorityBoost
0x14000dcc6  mov     rcx, r8; Irp
0x14000dcc9  call    cs:__imp_IofCompleteRequest
0x14000dcd0  nop     dword ptr [rax+rax+00h]
0x14000dcd5  mov     eax, 0C000000Dh
0x14000dcda  jmp     short loc_14000DCB1
0x14000dcdc  xor     ecx, ecx
0x14000dcde  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000dce5  mov     [rdx+38h], rcx
0x14000dce9  xor     edx, edx; PriorityBoost
0x14000dceb  mov     rcx, r8; Irp
0x14000dcee  call    cs:__imp_IofCompleteRequest
0x14000dcf5  nop     dword ptr [rax+rax+00h]
0x14000dcfa  mov     eax, 0C00000BBh
0x14000dcff  jmp     short loc_14000DCB1
```
