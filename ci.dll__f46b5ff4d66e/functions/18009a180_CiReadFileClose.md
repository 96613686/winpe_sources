# CiReadFileClose

- ea: `0x18009a180`
- end: `0x18009a225`
- name: `CiReadFileClose`
- size: `165`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18005fac8`
- `0x1800642e8`
- `0x18006d960`
- `0x1800751b0`
- `0x180098474`
- `0x180099c0c`
- `0x180099d20`
- `0x180099e10`
- `0x18009d178`
- `0x1800d24cc`

## callees

- `0x18009a180`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18009a1e9`
- `ntoskrnl!ZwClose` at `0x18009a1fd`
- `ntoskrnl!ZwClose` at `0x18009a1e9`
- `ntoskrnl!ZwClose` at `0x18009a1fd`
- `ntoskrnl!ObfDereferenceObject` at `0x18009a1d4`
- `ntoskrnl!ObfDereferenceObject` at `0x18009a1d4`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009a217`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009a217`
- `ntoskrnl!ZwSetInformationThread` at `0x18009a1a3`
- `ntoskrnl!ZwSetInformationThread` at `0x18009a1a3`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x18009a1bf`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x18009a1bf`

## pseudocode

```c
NTSTATUS __fastcall CiReadFileClose(__int64 a1)
{
  NTSTATUS result; // eax
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  if ( *(_BYTE *)(a1 + 36) )
    result = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, (PVOID)(a1 + 40), 4u);
  v3 = *(void **)(a1 + 24);
  if ( v3 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 2) != 0 )
      result = ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *(PVOID *)(a1 + 24));
    else
      result = MmUnmapViewInSystemSpace(v3);
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    result = ObfDereferenceObject(v4);
  v5 = *(void **)(a1 + 16);
  if ( v5 )
    result = ZwClose(v5);
  if ( *(_QWORD *)a1 )
    return ZwClose(*(HANDLE *)a1);
  return result;
}

```

## disassembly

```asm
0x18009a180  push    rbx
0x18009a182  sub     rsp, 20h
0x18009a186  cmp     byte ptr [rcx+24h], 0
0x18009a18a  mov     rbx, rcx
0x18009a18d  jz      short loc_18009A1AF
0x18009a18f  mov     edx, 18h; ThreadInformationClass
0x18009a194  lea     r8, [rcx+28h]; ThreadInformation
0x18009a198  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18009a19f  lea     r9d, [rdx-14h]; ThreadInformationLength
0x18009a1a3  call    cs:__imp_ZwSetInformationThread
0x18009a1aa  nop     dword ptr [rax+rax+00h]
0x18009a1af  mov     rcx, [rbx+18h]; MappedBase
0x18009a1b3  test    rcx, rcx
0x18009a1b6  jz      short loc_18009A1CB
0x18009a1b8  mov     eax, [rbx+20h]
0x18009a1bb  test    al, 2
0x18009a1bd  jnz     short loc_18009A210
0x18009a1bf  call    cs:__imp_MmUnmapViewInSystemSpace
0x18009a1c6  nop     dword ptr [rax+rax+00h]
0x18009a1cb  mov     rcx, [rbx+8]; Object
0x18009a1cf  test    rcx, rcx
0x18009a1d2  jz      short loc_18009A1E0
0x18009a1d4  call    cs:__imp_ObfDereferenceObject
0x18009a1db  nop     dword ptr [rax+rax+00h]
0x18009a1e0  mov     rcx, [rbx+10h]; Handle
0x18009a1e4  test    rcx, rcx
0x18009a1e7  jz      short loc_18009A1F5
0x18009a1e9  call    cs:__imp_ZwClose
0x18009a1f0  nop     dword ptr [rax+rax+00h]
0x18009a1f5  mov     rcx, [rbx]; Handle
0x18009a1f8  test    rcx, rcx
0x18009a1fb  jz      short loc_18009A209
0x18009a1fd  call    cs:__imp_ZwClose
0x18009a204  nop     dword ptr [rax+rax+00h]
0x18009a209  add     rsp, 20h
0x18009a20d  pop     rbx
0x18009a20e  retn
0x18009a210  mov     rdx, rcx; BaseAddress
0x18009a213  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009a217  call    cs:__imp_ZwUnmapViewOfSection
0x18009a21e  nop     dword ptr [rax+rax+00h]
0x18009a223  jmp     short loc_18009A1CB
```
