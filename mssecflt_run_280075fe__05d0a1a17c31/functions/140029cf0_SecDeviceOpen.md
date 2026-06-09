# SecDeviceOpen

- ea: `0x140029cf0`
- end: `0x140029d60`
- name: `SecDeviceOpen`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140029c04`
- `0x140029cf0`
- `0x14002a1d4`
- `0x14002ae58`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029d46`
- `ntoskrnl!IofCompleteRequest` at `0x140029d46`

## pseudocode

```c
__int64 __fastcall SecDeviceOpen(__int64 a1, IRP *a2)
{
  int v3; // ebx

  if ( (unsigned __int8)SecIsProcessAllowedToConnect(-1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)SecData + 295);
    v3 = SecIntilization();
    if ( v3 >= 0 )
      EventWriteDriverStatus(&Event3);
  }
  else
  {
    v3 = -1073741790;
  }
  a2->IoStatus.Status = v3;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140029cf0  mov     [rsp+arg_0], rbx
0x140029cf5  push    rdi
0x140029cf6  sub     rsp, 20h
0x140029cfa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140029cfe  mov     rdi, rdx
0x140029d01  call    SecIsProcessAllowedToConnect
0x140029d06  test    al, al
0x140029d08  jnz     short loc_140029D11
0x140029d0a  mov     ebx, 0C0000022h
0x140029d0f  jmp     short loc_140029D36
0x140029d11  mov     rax, cs:SecData
0x140029d18  lock inc dword ptr [rax+49Ch]
0x140029d1f  call    SecIntilization
0x140029d24  mov     ebx, eax
0x140029d26  test    eax, eax
0x140029d28  js      short loc_140029D36
0x140029d2a  lea     rcx, Event3; EventDescriptor
0x140029d31  call    EventWriteDriverStatus
0x140029d36  xor     edx, edx; PriorityBoost
0x140029d38  mov     [rdi+30h], ebx
0x140029d3b  mov     rcx, rdi; Irp
0x140029d3e  mov     qword ptr [rdi+38h], 0
0x140029d46  call    cs:__imp_IofCompleteRequest
0x140029d4d  nop     dword ptr [rax+rax+00h]
0x140029d52  mov     eax, ebx
0x140029d54  mov     rbx, [rsp+28h+arg_0]
0x140029d59  add     rsp, 20h
0x140029d5d  pop     rdi
0x140029d5e  retn
```
