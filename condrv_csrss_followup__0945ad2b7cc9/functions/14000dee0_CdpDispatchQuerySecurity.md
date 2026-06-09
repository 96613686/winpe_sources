# CdpDispatchQuerySecurity

- ea: `0x14000dee0`
- end: `0x14000df75`
- name: `CdpDispatchQuerySecurity`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x14000dee0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000df21`
- `ntoskrnl!IofCompleteRequest` at `0x14000df62`
- `ntoskrnl!IofCompleteRequest` at `0x14000df21`
- `ntoskrnl!IofCompleteRequest` at `0x14000df62`

## pseudocode

```c
__int64 __fastcall CdpDispatchQuerySecurity(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  char *FsContext; // rcx
  __int64 (__fastcall **v4)(char *, IRP *); // rax

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject
    && (FsContext = (char *)FileObject->FsContext) != 0
    && (v4 = *(__int64 (__fastcall ***)(char *, IRP *))FsContext) != 0 )
  {
    if ( v4[8] )
    {
      return v4[8](&FsContext[-*(unsigned int *)v4], a2);
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
0x14000dee0  sub     rsp, 28h
0x14000dee4  mov     rax, [rdx+0B8h]
0x14000deeb  mov     r8, rdx
0x14000deee  mov     rcx, [rax+30h]
0x14000def2  test    rcx, rcx
0x14000def5  jz      short loc_14000DF4E
0x14000def7  mov     rcx, [rcx+18h]
0x14000defb  test    rcx, rcx
0x14000defe  jz      short loc_14000DF4E
0x14000df00  mov     rax, [rcx]
0x14000df03  test    rax, rax
0x14000df06  jz      short loc_14000DF4E
0x14000df08  mov     r9, [rax+40h]
0x14000df0c  test    r9, r9
0x14000df0f  jnz     short loc_14000DF38
0x14000df11  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000df18  mov     rcx, r8; Irp
0x14000df1b  mov     [rdx+38h], r9
0x14000df1f  xor     edx, edx; PriorityBoost
0x14000df21  call    cs:__imp_IofCompleteRequest
0x14000df28  nop     dword ptr [rax+rax+00h]
0x14000df2d  mov     eax, 0C00000BBh
0x14000df32  add     rsp, 28h
0x14000df36  retn
0x14000df38  mov     edx, [rax]
0x14000df3a  mov     rax, r9
0x14000df3d  sub     rcx, rdx
0x14000df40  mov     rdx, r8
0x14000df43  call    _guard_dispatch_icall
0x14000df48  add     rsp, 28h
0x14000df4c  retn
0x14000df4e  mov     dword ptr [rdx+30h], 0C000000Dh
0x14000df55  mov     rcx, r8; Irp
0x14000df58  mov     qword ptr [rdx+38h], 0
0x14000df60  xor     edx, edx; PriorityBoost
0x14000df62  call    cs:__imp_IofCompleteRequest
0x14000df69  nop     dword ptr [rax+rax+00h]
0x14000df6e  mov     eax, 0C000000Dh
0x14000df73  jmp     short loc_14000DF32
```
