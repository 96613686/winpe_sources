# KsFreeDeviceHeader

- ea: `0x180047f70`
- end: `0x180047fd4`
- name: `KsFreeDeviceHeader`
- size: `100`
- prototype: `void __stdcall(KSDEVICE_HEADER Header)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180047ea0`
- `0x180049460`

## callees

- `0x180019c60`
- `0x180047f70`
- `0x180048ae8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180047f82`
- `ntoskrnl!ExDeleteResourceLite` at `0x180047f82`
- `ntoskrnl!ExFreePoolWithTag` at `0x180047fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180047fc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180047fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180047fc1`

## pseudocode

```c
void __stdcall KsFreeDeviceHeader(KSDEVICE_HEADER Header)
{
  __int64 v2; // rcx

  FreeCreateEntries(Header);
  ExDeleteResourceLite((PERESOURCE)((char *)Header + 16));
  v2 = *((_QWORD *)Header + 16);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD))(v2 + 24))(*(_QWORD *)(v2 + 8));
    ExFreePoolWithTag(*((PVOID *)Header + 16), 0);
  }
  ExFreePoolWithTag(Header, 0);
}

```

## disassembly

```asm
0x180047f70  push    rbx
0x180047f72  sub     rsp, 20h
0x180047f76  mov     rbx, rcx
0x180047f79  call    FreeCreateEntries
0x180047f7e  lea     rcx, [rbx+10h]; Resource
0x180047f82  call    cs:__imp_ExDeleteResourceLite
0x180047f89  nop     dword ptr [rax+rax+00h]
0x180047f8e  mov     rcx, [rbx+80h]
0x180047f95  test    rcx, rcx
0x180047f98  jz      short loc_180047FBC
0x180047f9a  mov     rax, [rcx+18h]
0x180047f9e  mov     rcx, [rcx+8]
0x180047fa2  call    _guard_dispatch_icall
0x180047fa7  mov     rcx, [rbx+80h]; P
0x180047fae  xor     edx, edx; Tag
0x180047fb0  call    cs:__imp_ExFreePoolWithTag
0x180047fb7  nop     dword ptr [rax+rax+00h]
0x180047fbc  xor     edx, edx; Tag
0x180047fbe  mov     rcx, rbx; P
0x180047fc1  call    cs:__imp_ExFreePoolWithTag
0x180047fc8  nop     dword ptr [rax+rax+00h]
0x180047fcd  add     rsp, 20h
0x180047fd1  pop     rbx
0x180047fd2  retn
```
