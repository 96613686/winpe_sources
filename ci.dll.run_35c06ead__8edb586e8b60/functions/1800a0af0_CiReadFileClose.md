# CiReadFileClose

- ea: `0x1800a0af0`
- end: `0x1800a0b95`
- name: `CiReadFileClose`
- size: `165`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18006021c`
- `0x180064d70`
- `0x18006ea14`
- `0x180076a4c`
- `0x18008fa34`
- `0x18009e9b0`
- `0x1800a057c`
- `0x1800a0690`
- `0x1800a0780`
- `0x1800d399c`

## callees

- `0x1800a0af0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800a0b59`
- `ntoskrnl!ZwClose` at `0x1800a0b6d`
- `ntoskrnl!ZwClose` at `0x1800a0b59`
- `ntoskrnl!ZwClose` at `0x1800a0b6d`
- `ntoskrnl!ObfDereferenceObject` at `0x1800a0b44`
- `ntoskrnl!ObfDereferenceObject` at `0x1800a0b44`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800a0b87`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800a0b87`
- `ntoskrnl!ZwSetInformationThread` at `0x1800a0b13`
- `ntoskrnl!ZwSetInformationThread` at `0x1800a0b13`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1800a0b2f`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1800a0b2f`

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
0x1800a0af0  push    rbx
0x1800a0af2  sub     rsp, 20h
0x1800a0af6  cmp     byte ptr [rcx+24h], 0
0x1800a0afa  mov     rbx, rcx
0x1800a0afd  jz      short loc_1800A0B1F
0x1800a0aff  mov     edx, 18h; ThreadInformationClass
0x1800a0b04  lea     r8, [rcx+28h]; ThreadInformation
0x1800a0b08  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800a0b0f  lea     r9d, [rdx-14h]; ThreadInformationLength
0x1800a0b13  call    cs:__imp_ZwSetInformationThread
0x1800a0b1a  nop     dword ptr [rax+rax+00h]
0x1800a0b1f  mov     rcx, [rbx+18h]; MappedBase
0x1800a0b23  test    rcx, rcx
0x1800a0b26  jz      short loc_1800A0B3B
0x1800a0b28  mov     eax, [rbx+20h]
0x1800a0b2b  test    al, 2
0x1800a0b2d  jnz     short loc_1800A0B80
0x1800a0b2f  call    cs:__imp_MmUnmapViewInSystemSpace
0x1800a0b36  nop     dword ptr [rax+rax+00h]
0x1800a0b3b  mov     rcx, [rbx+8]; Object
0x1800a0b3f  test    rcx, rcx
0x1800a0b42  jz      short loc_1800A0B50
0x1800a0b44  call    cs:__imp_ObfDereferenceObject
0x1800a0b4b  nop     dword ptr [rax+rax+00h]
0x1800a0b50  mov     rcx, [rbx+10h]; Handle
0x1800a0b54  test    rcx, rcx
0x1800a0b57  jz      short loc_1800A0B65
0x1800a0b59  call    cs:__imp_ZwClose
0x1800a0b60  nop     dword ptr [rax+rax+00h]
0x1800a0b65  mov     rcx, [rbx]; Handle
0x1800a0b68  test    rcx, rcx
0x1800a0b6b  jz      short loc_1800A0B79
0x1800a0b6d  call    cs:__imp_ZwClose
0x1800a0b74  nop     dword ptr [rax+rax+00h]
0x1800a0b79  add     rsp, 20h
0x1800a0b7d  pop     rbx
0x1800a0b7e  retn
0x1800a0b80  mov     rdx, rcx; BaseAddress
0x1800a0b83  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800a0b87  call    cs:__imp_ZwUnmapViewOfSection
0x1800a0b8e  nop     dword ptr [rax+rax+00h]
0x1800a0b93  jmp     short loc_1800A0B3B
```
