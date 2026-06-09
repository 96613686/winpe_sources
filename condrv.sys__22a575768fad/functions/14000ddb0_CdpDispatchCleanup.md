# CdpDispatchCleanup

- ea: `0x14000ddb0`
- end: `0x14000de3e`
- name: `CdpDispatchCleanup`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000ddb0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000ddef`
- `ntoskrnl!IofCompleteRequest` at `0x14000de15`
- `ntoskrnl!IofCompleteRequest` at `0x14000ddef`
- `ntoskrnl!IofCompleteRequest` at `0x14000de15`

## pseudocode

```c
__int64 __fastcall CdpDispatchCleanup(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rdx
  unsigned int **FsContext; // rcx
  unsigned int *v5; // rdx
  __int64 (__fastcall *v6)(char *, IRP *); // r8

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject && (FsContext = (unsigned int **)FileObject->FsContext) != 0 && (v5 = *FsContext) != 0 )
  {
    v6 = (__int64 (__fastcall *)(char *, IRP *))*((_QWORD *)v5 + 4);
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
0x14000ddb0  sub     rsp, 28h
0x14000ddb4  mov     rcx, [rdx+0B8h]
0x14000ddbb  mov     rax, rdx
0x14000ddbe  mov     rdx, [rcx+30h]
0x14000ddc2  test    rdx, rdx
0x14000ddc5  jz      short loc_14000DE03
0x14000ddc7  mov     rcx, [rdx+18h]
0x14000ddcb  test    rcx, rcx
0x14000ddce  jz      short loc_14000DE03
0x14000ddd0  mov     rdx, [rcx]
0x14000ddd3  test    rdx, rdx
0x14000ddd6  jz      short loc_14000DE03
0x14000ddd8  mov     r8, [rdx+20h]
0x14000dddc  test    r8, r8
0x14000dddf  jnz     short loc_14000DE28
0x14000dde1  xor     ecx, ecx
0x14000dde3  xor     edx, edx; PriorityBoost
0x14000dde5  mov     [rax+30h], ecx
0x14000dde8  mov     [rax+38h], rcx
0x14000ddec  mov     rcx, rax; Irp
0x14000ddef  call    cs:__imp_IofCompleteRequest
0x14000ddf6  nop     dword ptr [rax+rax+00h]
0x14000ddfb  xor     eax, eax
0x14000ddfd  add     rsp, 28h
0x14000de01  retn
0x14000de03  xor     ecx, ecx
0x14000de05  mov     dword ptr [rax+30h], 0C000000Dh
0x14000de0c  mov     [rax+38h], rcx
0x14000de10  xor     edx, edx; PriorityBoost
0x14000de12  mov     rcx, rax; Irp
0x14000de15  call    cs:__imp_IofCompleteRequest
0x14000de1c  nop     dword ptr [rax+rax+00h]
0x14000de21  mov     eax, 0C000000Dh
0x14000de26  jmp     short loc_14000DDFD
0x14000de28  mov     edx, [rdx]
0x14000de2a  sub     rcx, rdx
0x14000de2d  mov     rdx, rax
0x14000de30  mov     rax, r8
0x14000de33  call    _guard_dispatch_icall
0x14000de38  add     rsp, 28h
0x14000de3c  retn
```
