# CdpDispatchClose

- ea: `0x14000de50`
- end: `0x14000deda`
- name: `CdpDispatchClose`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000de50`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000dea9`
- `ntoskrnl!IofCompleteRequest` at `0x14000deca`
- `ntoskrnl!IofCompleteRequest` at `0x14000dea9`
- `ntoskrnl!IofCompleteRequest` at `0x14000deca`

## pseudocode

```c
__int64 __fastcall CdpDispatchClose(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rdx
  unsigned int **FsContext; // rcx
  unsigned int *v5; // rdx
  __int64 (__fastcall *v6)(char *, IRP *); // r8

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject && (FsContext = (unsigned int **)FileObject->FsContext) != 0 && (v5 = *FsContext) != 0 )
  {
    v6 = (__int64 (__fastcall *)(char *, IRP *))*((_QWORD *)v5 + 5);
    if ( v6 )
    {
      return v6((char *)FsContext - *v5, a2);
    }
    else
    {
      a2->IoStatus.Status = 0;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 0);
      return 0;
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
0x14000de50  sub     rsp, 28h
0x14000de54  mov     rcx, [rdx+0B8h]
0x14000de5b  mov     rax, rdx
0x14000de5e  mov     rdx, [rcx+30h]
0x14000de62  test    rdx, rdx
0x14000de65  jz      short loc_14000DE97
0x14000de67  mov     rcx, [rdx+18h]
0x14000de6b  test    rcx, rcx
0x14000de6e  jz      short loc_14000DE97
0x14000de70  mov     rdx, [rcx]
0x14000de73  test    rdx, rdx
0x14000de76  jz      short loc_14000DE97
0x14000de78  mov     r8, [rdx+28h]
0x14000de7c  test    r8, r8
0x14000de7f  jz      short loc_14000DEBC
0x14000de81  mov     edx, [rdx]
0x14000de83  sub     rcx, rdx
0x14000de86  mov     rdx, rax
0x14000de89  mov     rax, r8
0x14000de8c  call    _guard_dispatch_icall
0x14000de91  add     rsp, 28h
0x14000de95  retn
0x14000de97  xor     ecx, ecx
0x14000de99  mov     dword ptr [rax+30h], 0C000000Dh
0x14000dea0  mov     [rax+38h], rcx
0x14000dea4  xor     edx, edx; PriorityBoost
0x14000dea6  mov     rcx, rax; Irp
0x14000dea9  call    cs:__imp_IofCompleteRequest
0x14000deb0  nop     dword ptr [rax+rax+00h]
0x14000deb5  mov     eax, 0C000000Dh
0x14000deba  jmp     short loc_14000DE91
0x14000debc  xor     ecx, ecx
0x14000debe  xor     edx, edx; PriorityBoost
0x14000dec0  mov     [rax+30h], ecx
0x14000dec3  mov     [rax+38h], rcx
0x14000dec7  mov     rcx, rax; Irp
0x14000deca  call    cs:__imp_IofCompleteRequest
0x14000ded1  nop     dword ptr [rax+rax+00h]
0x14000ded6  xor     eax, eax
0x14000ded8  jmp     short loc_14000DE91
```
