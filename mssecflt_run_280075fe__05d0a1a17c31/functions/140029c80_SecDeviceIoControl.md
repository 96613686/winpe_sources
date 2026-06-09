# SecDeviceIoControl

- ea: `0x140029c80`
- end: `0x140029ce2`
- name: `SecDeviceIoControl`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140029c80`
- `0x14002a5e8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029cc8`
- `ntoskrnl!IofCompleteRequest` at `0x140029cc8`

## pseudocode

```c
__int64 __fastcall SecDeviceIoControl(__int64 a1, IRP *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( *(_DWORD *)(a1 + 72) == 34 )
  {
    if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2236416 )
      SecUninitialize();
    else
      v2 = -1073741811;
  }
  else
  {
    v2 = -1073741808;
  }
  a2->IoStatus.Status = v2;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v2;
}

```

## disassembly

```asm
0x140029c80  mov     [rsp+arg_0], rbx
0x140029c85  push    rdi
0x140029c86  sub     rsp, 20h
0x140029c8a  xor     ebx, ebx
0x140029c8c  mov     rdi, rdx
0x140029c8f  cmp     dword ptr [rcx+48h], 22h ; '"'
0x140029c93  jz      short loc_140029C9C
0x140029c95  mov     ebx, 0C0000010h
0x140029c9a  jmp     short loc_140029CB8
0x140029c9c  mov     rax, [rdx+0B8h]
0x140029ca3  cmp     dword ptr [rax+18h], 222000h
0x140029caa  jz      short loc_140029CB3
0x140029cac  mov     ebx, 0C000000Dh
0x140029cb1  jmp     short loc_140029CB8
0x140029cb3  call    SecUninitialize
0x140029cb8  xor     edx, edx; PriorityBoost
0x140029cba  mov     [rdi+30h], ebx
0x140029cbd  mov     rcx, rdi; Irp
0x140029cc0  mov     qword ptr [rdi+38h], 0
0x140029cc8  call    cs:__imp_IofCompleteRequest
0x140029ccf  nop     dword ptr [rax+rax+00h]
0x140029cd4  mov     eax, ebx
0x140029cd6  mov     rbx, [rsp+28h+arg_0]
0x140029cdb  add     rsp, 20h
0x140029cdf  pop     rdi
0x140029ce0  retn
```
