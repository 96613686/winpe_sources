# CdpClientFlushBuffers

- ea: `0x140008230`
- end: `0x1400082e3`
- name: `CdpClientFlushBuffers`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140008230`
- `0x14000a5e0`
- `0x14000ab30`
- `0x14000d440`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400082a2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400082a2`
- `ntoskrnl!IofCompleteRequest` at `0x1400082c9`
- `ntoskrnl!IofCompleteRequest` at `0x1400082c9`

## pseudocode

```c
__int64 __fastcall CdpClientFlushBuffers(__int64 a1, IRP *a2)
{
  int ClientTarget; // edi
  int v4; // r8d
  __int128 v6; // [rsp+40h] [rbp-28h] BYREF
  __int128 v7; // [rsp+50h] [rbp-18h]

  v6 = 0;
  v7 = 0;
  ClientTarget = CdpGetClientTarget(a1, a2, &v6);
  if ( ClientTarget >= 0 )
  {
    LOBYTE(v4) = 8;
    CdInitializeIo((_DWORD)a2, v7 + 64, v4, v6, *((__int64 *)&v6 + 1), 0, 0);
    ClientTarget = CdAddIoToPipe((__int64)a2);
    if ( *((_QWORD *)&v7 + 1) )
      ObfDereferenceObject(*((PVOID *)&v7 + 1));
    if ( ClientTarget >= 0 )
      return 259;
  }
  a2->IoStatus.Status = ClientTarget;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return (unsigned int)ClientTarget;
}

```

## disassembly

```asm
0x140008230  mov     rax, rsp
0x140008233  mov     [rax+8], rbx
0x140008237  push    rdi
0x140008238  sub     rsp, 60h
0x14000823c  xorps   xmm0, xmm0
0x14000823f  lea     r8, [rax-28h]
0x140008243  movups  xmmword ptr [rax-28h], xmm0
0x140008247  mov     rbx, rdx
0x14000824a  movups  xmmword ptr [rax-18h], xmm0
0x14000824e  call    CdpGetClientTarget
0x140008253  mov     edi, eax
0x140008255  test    eax, eax
0x140008257  js      short loc_1400082B9
0x140008259  mov     rax, [rsp+68h+var_20]
0x14000825e  mov     r8b, 8
0x140008261  mov     rdx, [rsp+68h+var_18]
0x140008266  mov     rcx, rbx
0x140008269  mov     r9, [rsp+68h+var_28]
0x14000826e  add     rdx, 40h ; '@'
0x140008272  mov     [rsp+68h+var_38], 0
0x14000827b  mov     [rsp+68h+var_40], 0
0x140008284  mov     [rsp+68h+var_48], rax
0x140008289  call    CdInitializeIo
0x14000828e  mov     rcx, rbx
0x140008291  call    CdAddIoToPipe
0x140008296  mov     rcx, [rsp+68h+Object]; Object
0x14000829b  mov     edi, eax
0x14000829d  test    rcx, rcx
0x1400082a0  jz      short loc_1400082AE
0x1400082a2  call    cs:__imp_ObfDereferenceObject
0x1400082a9  nop     dword ptr [rax+rax+00h]
0x1400082ae  test    edi, edi
0x1400082b0  js      short loc_1400082B9
0x1400082b2  mov     eax, 103h
0x1400082b7  jmp     short loc_1400082D7
0x1400082b9  xor     edx, edx; PriorityBoost
0x1400082bb  mov     [rbx+30h], edi
0x1400082be  mov     rcx, rbx; Irp
0x1400082c1  mov     qword ptr [rbx+38h], 0
0x1400082c9  call    cs:__imp_IofCompleteRequest
0x1400082d0  nop     dword ptr [rax+rax+00h]
0x1400082d5  mov     eax, edi
0x1400082d7  mov     rbx, [rsp+68h+arg_0]
0x1400082dc  add     rsp, 60h
0x1400082e0  pop     rdi
0x1400082e1  retn
```
