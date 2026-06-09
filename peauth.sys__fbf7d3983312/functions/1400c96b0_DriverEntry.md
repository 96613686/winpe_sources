# DriverEntry

- ea: `0x1400c96b0`
- end: `0x1400c973e`
- name: `DriverEntry`
- size: `142`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140025fd0`
- `0x1400c9644`
- `0x1400c96b0`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax

  if ( (int)sub_1400C9644() >= 0 )
  {
    result = ((__int64 (__fastcall *)(PDRIVER_OBJECT, PUNICODE_STRING))(0x140000000LL + (unsigned int)dword_14003A0B4))(
               DriverObject,
               RegistryPath);
    if ( result >= 0 )
    {
      qword_14003A5C0 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)sub_1400019E0;
    }
    else if ( dword_14003A428 )
    {
      dword_14003A428 = 0;
    }
  }
  else
  {
    if ( dword_14003A428 )
      dword_14003A428 = 0;
    return -1073740955;
  }
  return result;
}

```

## disassembly

```asm
0x1400c96b0  mov     [rsp+arg_0], rbx
0x1400c96b5  push    rdi
0x1400c96b6  sub     rsp, 20h
0x1400c96ba  mov     rdi, rdx
0x1400c96bd  mov     rbx, rcx
0x1400c96c0  call    sub_1400C9644
0x1400c96c5  test    eax, eax
0x1400c96c7  jns     short loc_1400C96E3
0x1400c96c9  cmp     cs:dword_14003A428, 0
0x1400c96d0  jz      short loc_1400C96DC
0x1400c96d2  mov     cs:dword_14003A428, 0
0x1400c96dc  mov     eax, 0C0000365h
0x1400c96e1  jmp     short loc_1400C9732
0x1400c96e3  mov     eax, cs:dword_14003A0B4
0x1400c96e9  lea     rcx, cs:140000000h
0x1400c96f0  add     rax, rcx
0x1400c96f3  mov     rdx, rdi
0x1400c96f6  mov     rcx, rbx
0x1400c96f9  call    cs:__guard_dispatch_icall_fptr
0x1400c96ff  mov     ecx, eax
0x1400c9701  test    eax, eax
0x1400c9703  jns     short loc_1400C971A
0x1400c9705  cmp     cs:dword_14003A428, 0
0x1400c970c  jz      short loc_1400C9732
0x1400c970e  mov     cs:dword_14003A428, 0
0x1400c9718  jmp     short loc_1400C9732
0x1400c971a  mov     rax, [rbx+68h]
0x1400c971e  mov     cs:qword_14003A5C0, rax
0x1400c9725  lea     rax, sub_1400019E0
0x1400c972c  mov     [rbx+68h], rax
0x1400c9730  mov     eax, ecx
0x1400c9732  mov     rbx, [rsp+28h+arg_0]
0x1400c9737  add     rsp, 20h
0x1400c973b  pop     rdi
0x1400c973c  retn
```
