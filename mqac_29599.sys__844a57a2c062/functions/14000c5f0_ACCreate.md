# ACCreate

- ea: `0x14000c5f0`
- end: `0x14000c6bf`
- name: `ACCreate`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001128`
- `0x140001c04`
- `0x14000c5f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000c6a5`
- `ntoskrnl!IofCompleteRequest` at `0x14000c6a5`

## pseudocode

```c
__int64 __fastcall ACCreate(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rdi
  _QWORD *v4; // rax
  unsigned int v5; // edi

  _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 64) + 64LL));
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v4 = operator new(0x18u, 0x40u, 0x4451514Du, LowPoolPriority);
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
  }
  FileObject->FsContext2 = v4;
  if ( v4 )
  {
    v5 = 0;
    *((_DWORD *)v4 + 4) = *(_DWORD *)(a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_b379d71efbf73e5446e1455e1c7314cf_Traceguids);
    }
    v5 = -1073741670;
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x14000c5f0  mov     [rsp+arg_0], rbx
0x14000c5f5  push    rdi
0x14000c5f6  sub     rsp, 20h
0x14000c5fa  mov     rax, [rcx+40h]
0x14000c5fe  mov     rbx, rdx
0x14000c601  mov     edx, 40h ; '@'; unsigned __int64
0x14000c606  lock inc qword ptr [rax+rdx]
0x14000c60b  mov     rax, [rbx+0B8h]
0x14000c612  lea     ecx, [rdx-28h]; unsigned __int64
0x14000c615  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000c618  mov     r8d, 4451514Dh; unsigned int
0x14000c61e  mov     rdi, [rax+30h]
0x14000c622  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000c627  test    rax, rax
0x14000c62a  jz      short loc_14000C643
0x14000c62c  mov     qword ptr [rax], 0
0x14000c633  mov     qword ptr [rax+8], 0
0x14000c63b  mov     qword ptr [rax+10h], 0
0x14000c643  mov     [rdi+20h], rax
0x14000c647  test    rax, rax
0x14000c64a  jnz     short loc_14000C682
0x14000c64c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c653  lea     rax, WPP_GLOBAL_Control
0x14000c65a  cmp     rcx, rax
0x14000c65d  jz      short loc_14000C67B
0x14000c65f  mov     eax, [rcx+6Ch]
0x14000c662  test    al, 1
0x14000c664  jz      short loc_14000C67B
0x14000c666  mov     rcx, [rcx+58h]
0x14000c66a  lea     r8, WPP_b379d71efbf73e5446e1455e1c7314cf_Traceguids
0x14000c671  mov     edx, 0Ah
0x14000c676  call    WPP_SF_
0x14000c67b  mov     edi, 0C000009Ah
0x14000c680  jmp     short loc_14000C695
0x14000c682  mov     rcx, [rbx+0B8h]
0x14000c689  xor     edi, edi
0x14000c68b  mov     rdx, [rcx+8]
0x14000c68f  mov     ecx, [rdx+10h]
0x14000c692  mov     [rax+10h], ecx
0x14000c695  xor     edx, edx; PriorityBoost
0x14000c697  mov     qword ptr [rbx+38h], 0
0x14000c69f  mov     rcx, rbx; Irp
0x14000c6a2  mov     [rbx+30h], edi
0x14000c6a5  call    cs:__imp_IofCompleteRequest
0x14000c6ac  nop     dword ptr [rax+rax+00h]
0x14000c6b1  mov     rbx, [rsp+28h+arg_0]
0x14000c6b6  mov     eax, edi
0x14000c6b8  add     rsp, 20h
0x14000c6bc  pop     rdi
0x14000c6bd  retn
```
