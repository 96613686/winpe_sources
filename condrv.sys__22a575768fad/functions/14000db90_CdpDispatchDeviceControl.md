# CdpDispatchDeviceControl

- ea: `0x14000db90`
- end: `0x14000dc21`
- name: `CdpDispatchDeviceControl`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000db90`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000dbe9`
- `ntoskrnl!IofCompleteRequest` at `0x14000dc0e`
- `ntoskrnl!IofCompleteRequest` at `0x14000dbe9`
- `ntoskrnl!IofCompleteRequest` at `0x14000dc0e`

## pseudocode

```c
__int64 __fastcall CdpDispatchDeviceControl(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[3] )
    {
      return v4[3](&FsContext[-*(unsigned int *)v4], a2);
    }
    else
    {
      a2->IoStatus.Status = -1073741808;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 0);
      return 3221225488LL;
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
0x14000db90  sub     rsp, 28h
0x14000db94  mov     rax, [rdx+0B8h]
0x14000db9b  mov     r8, rdx
0x14000db9e  mov     rcx, [rax+30h]
0x14000dba2  test    rcx, rcx
0x14000dba5  jz      short loc_14000DBD7
0x14000dba7  mov     rcx, [rcx+18h]
0x14000dbab  test    rcx, rcx
0x14000dbae  jz      short loc_14000DBD7
0x14000dbb0  mov     rax, [rcx]
0x14000dbb3  test    rax, rax
0x14000dbb6  jz      short loc_14000DBD7
0x14000dbb8  mov     r9, [rax+18h]
0x14000dbbc  test    r9, r9
0x14000dbbf  jz      short loc_14000DBFC
0x14000dbc1  mov     edx, [rax]
0x14000dbc3  mov     rax, r9
0x14000dbc6  sub     rcx, rdx
0x14000dbc9  mov     rdx, r8
0x14000dbcc  call    _guard_dispatch_icall
0x14000dbd1  add     rsp, 28h
0x14000dbd5  retn
0x14000dbd7  xor     ecx, ecx
0x14000dbd9  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000dbe0  mov     [rdx+38h], rcx
0x14000dbe4  xor     edx, edx; PriorityBoost
0x14000dbe6  mov     rcx, r8; Irp
0x14000dbe9  call    cs:__imp_IofCompleteRequest
0x14000dbf0  nop     dword ptr [rax+rax+00h]
0x14000dbf5  mov     eax, 0C000000Dh
0x14000dbfa  jmp     short loc_14000DBD1
0x14000dbfc  xor     ecx, ecx
0x14000dbfe  mov     dword ptr [rdx+30h], 0C0000010h
0x14000dc05  mov     [rdx+38h], rcx
0x14000dc09  xor     edx, edx; PriorityBoost
0x14000dc0b  mov     rcx, r8; Irp
0x14000dc0e  call    cs:__imp_IofCompleteRequest
0x14000dc15  nop     dword ptr [rax+rax+00h]
0x14000dc1a  mov     eax, 0C0000010h
0x14000dc1f  jmp     short loc_14000DBD1
```
