# CdpDispatchFlushBuffers

- ea: `0x14000e3a0`
- end: `0x14000e435`
- name: `CdpDispatchFlushBuffers`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000e3a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000e3e1`
- `ntoskrnl!IofCompleteRequest` at `0x14000e41e`
- `ntoskrnl!IofCompleteRequest` at `0x14000e3e1`
- `ntoskrnl!IofCompleteRequest` at `0x14000e41e`

## pseudocode

```c
__int64 __fastcall CdpDispatchFlushBuffers(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[7] )
    {
      return v4[7](&FsContext[-*(unsigned int *)v4], a2);
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
0x14000e3a0  sub     rsp, 28h
0x14000e3a4  mov     rax, [rdx+0B8h]
0x14000e3ab  mov     r9, rdx
0x14000e3ae  mov     rcx, [rax+30h]
0x14000e3b2  test    rcx, rcx
0x14000e3b5  jz      short loc_14000E40A
0x14000e3b7  mov     rcx, [rcx+18h]
0x14000e3bb  test    rcx, rcx
0x14000e3be  jz      short loc_14000E40A
0x14000e3c0  mov     rax, [rcx]
0x14000e3c3  test    rax, rax
0x14000e3c6  jz      short loc_14000E40A
0x14000e3c8  mov     r8, [rax+38h]
0x14000e3cc  test    r8, r8
0x14000e3cf  jnz     short loc_14000E3F4
0x14000e3d1  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000e3d8  mov     rcx, r9; Irp
0x14000e3db  mov     [rdx+38h], r8
0x14000e3df  xor     edx, edx; PriorityBoost
0x14000e3e1  call    cs:__imp_IofCompleteRequest
0x14000e3e8  nop     dword ptr [rax+rax+00h]
0x14000e3ed  mov     eax, 0C00000BBh
0x14000e3f2  jmp     short loc_14000E42F
0x14000e3f4  mov     edx, [rax]
0x14000e3f6  mov     rax, r8
0x14000e3f9  sub     rcx, rdx
0x14000e3fc  mov     rdx, r9
0x14000e3ff  call    _guard_dispatch_icall
0x14000e404  add     rsp, 28h
0x14000e408  retn
0x14000e40a  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000e411  mov     rcx, r9; Irp
0x14000e414  mov     qword ptr [rdx+38h], 0
0x14000e41c  xor     edx, edx; PriorityBoost
0x14000e41e  call    cs:__imp_IofCompleteRequest
0x14000e425  nop     dword ptr [rax+rax+00h]
0x14000e42a  mov     eax, 0C000000Dh
0x14000e42f  add     rsp, 28h
0x14000e433  retn
```
