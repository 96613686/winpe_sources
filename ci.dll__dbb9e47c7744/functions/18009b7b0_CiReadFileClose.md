# CiReadFileClose

- ea: `0x18009b7b0`
- end: `0x18009b855`
- name: `CiReadFileClose`
- size: `165`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18006027c`
- `0x180064c00`
- `0x18006e734`
- `0x18007676c`
- `0x180099aa4`
- `0x18009b23c`
- `0x18009b350`
- `0x18009b440`
- `0x18009e7a8`
- `0x1800d398c`

## callees

- `0x18009b7b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18009b819`
- `ntoskrnl!ZwClose` at `0x18009b82d`
- `ntoskrnl!ZwClose` at `0x18009b819`
- `ntoskrnl!ZwClose` at `0x18009b82d`
- `ntoskrnl!ObfDereferenceObject` at `0x18009b804`
- `ntoskrnl!ObfDereferenceObject` at `0x18009b804`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009b847`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009b847`
- `ntoskrnl!ZwSetInformationThread` at `0x18009b7d3`
- `ntoskrnl!ZwSetInformationThread` at `0x18009b7d3`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x18009b7ef`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x18009b7ef`

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
0x18009b7b0  push    rbx
0x18009b7b2  sub     rsp, 20h
0x18009b7b6  cmp     byte ptr [rcx+24h], 0
0x18009b7ba  mov     rbx, rcx
0x18009b7bd  jz      short loc_18009B7DF
0x18009b7bf  mov     edx, 18h; ThreadInformationClass
0x18009b7c4  lea     r8, [rcx+28h]; ThreadInformation
0x18009b7c8  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18009b7cf  lea     r9d, [rdx-14h]; ThreadInformationLength
0x18009b7d3  call    cs:__imp_ZwSetInformationThread
0x18009b7da  nop     dword ptr [rax+rax+00h]
0x18009b7df  mov     rcx, [rbx+18h]; MappedBase
0x18009b7e3  test    rcx, rcx
0x18009b7e6  jz      short loc_18009B7FB
0x18009b7e8  mov     eax, [rbx+20h]
0x18009b7eb  test    al, 2
0x18009b7ed  jnz     short loc_18009B840
0x18009b7ef  call    cs:__imp_MmUnmapViewInSystemSpace
0x18009b7f6  nop     dword ptr [rax+rax+00h]
0x18009b7fb  mov     rcx, [rbx+8]; Object
0x18009b7ff  test    rcx, rcx
0x18009b802  jz      short loc_18009B810
0x18009b804  call    cs:__imp_ObfDereferenceObject
0x18009b80b  nop     dword ptr [rax+rax+00h]
0x18009b810  mov     rcx, [rbx+10h]; Handle
0x18009b814  test    rcx, rcx
0x18009b817  jz      short loc_18009B825
0x18009b819  call    cs:__imp_ZwClose
0x18009b820  nop     dword ptr [rax+rax+00h]
0x18009b825  mov     rcx, [rbx]; Handle
0x18009b828  test    rcx, rcx
0x18009b82b  jz      short loc_18009B839
0x18009b82d  call    cs:__imp_ZwClose
0x18009b834  nop     dword ptr [rax+rax+00h]
0x18009b839  add     rsp, 20h
0x18009b83d  pop     rbx
0x18009b83e  retn
0x18009b840  mov     rdx, rcx; BaseAddress
0x18009b843  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009b847  call    cs:__imp_ZwUnmapViewOfSection
0x18009b84e  nop     dword ptr [rax+rax+00h]
0x18009b853  jmp     short loc_18009B7FB
```
