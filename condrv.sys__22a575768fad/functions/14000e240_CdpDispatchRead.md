# CdpDispatchRead

- ea: `0x14000e240`
- end: `0x14000e2d5`
- name: `CdpDispatchRead`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000e240`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000e29b`
- `ntoskrnl!IofCompleteRequest` at `0x14000e2c2`
- `ntoskrnl!IofCompleteRequest` at `0x14000e29b`
- `ntoskrnl!IofCompleteRequest` at `0x14000e2c2`

## pseudocode

```c
__int64 __fastcall CdpDispatchRead(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[1] )
    {
      return v4[1](&FsContext[-*(unsigned int *)v4], a2);
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
0x14000e240  sub     rsp, 28h
0x14000e244  mov     rax, [rdx+0B8h]
0x14000e24b  mov     r9, rdx
0x14000e24e  mov     rcx, [rax+30h]
0x14000e252  test    rcx, rcx
0x14000e255  jz      short loc_14000E2AE
0x14000e257  mov     rcx, [rcx+18h]
0x14000e25b  test    rcx, rcx
0x14000e25e  jz      short loc_14000E2AE
0x14000e260  mov     rax, [rcx]
0x14000e263  test    rax, rax
0x14000e266  jz      short loc_14000E2AE
0x14000e268  mov     r8, [rax+8]
0x14000e26c  test    r8, r8
0x14000e26f  jz      short loc_14000E287
0x14000e271  mov     edx, [rax]
0x14000e273  mov     rax, r8
0x14000e276  sub     rcx, rdx
0x14000e279  mov     rdx, r9
0x14000e27c  call    _guard_dispatch_icall
0x14000e281  add     rsp, 28h
0x14000e285  retn
0x14000e287  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000e28e  mov     rcx, r9; Irp
0x14000e291  mov     qword ptr [rdx+38h], 0
0x14000e299  xor     edx, edx; PriorityBoost
0x14000e29b  call    cs:__imp_IofCompleteRequest
0x14000e2a2  nop     dword ptr [rax+rax+00h]
0x14000e2a7  mov     eax, 0C00000BBh
0x14000e2ac  jmp     short loc_14000E281
0x14000e2ae  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000e2b5  mov     rcx, r9; Irp
0x14000e2b8  mov     qword ptr [rdx+38h], 0
0x14000e2c0  xor     edx, edx; PriorityBoost
0x14000e2c2  call    cs:__imp_IofCompleteRequest
0x14000e2c9  nop     dword ptr [rax+rax+00h]
0x14000e2ce  mov     eax, 0C000000Dh
0x14000e2d3  jmp     short loc_14000E281
```
