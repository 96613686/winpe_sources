# SafeAllocaInitialize

- ea: `0x180044ab0`
- end: `0x180044b6c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800238f0`
- `0x180023b70`

## callees

- `0x180044ab0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180044ac1`
- `ntdll!RtlImageNtHeader` at `0x180044ac1`

## pseudocode

```c
void (__fastcall *SafeAllocaInitialize())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  void (__fastcall *result)(void *); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged || !v0 )
  {
    SizeOfStackCommit = 0;
  }
  else
  {
    if ( v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_8;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_8:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_12;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_12;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_12:
  g_pfnAllocate = (__int64)Pku2uAllocate;
  result = Pku2uFree;
  g_pfnFree = (__int64)Pku2uFree;
  return result;
}

```

## disassembly

```asm
0x180044ab0  sub     rsp, 28h
0x180044ab4  mov     rcx, gs:60h
0x180044abd  mov     rcx, [rcx+10h]; BaseAddress
0x180044ac1  call    cs:__imp_RtlImageNtHeader
0x180044ac7  mov     rcx, gs:60h
0x180044ad0  mov     r8d, 3000h
0x180044ad6  mov     rdx, rax
0x180044ad9  cmp     byte ptr [rcx+2], 0
0x180044add  jnz     short loc_180044B04
0x180044adf  test    rax, rax
0x180044ae2  jz      short loc_180044B04
0x180044ae4  mov     rax, [rax+60h]
0x180044ae8  sub     rax, [rdx+68h]
0x180044aec  cmp     rax, r8
0x180044aef  jnb     short loc_180044AFE
0x180044af1  mov     cs:g_ulMaxStackAllocSize, 0
0x180044afc  jmp     short loc_180044B12
0x180044afe  mov     rax, [rdx+68h]
0x180044b02  jmp     short loc_180044B06
0x180044b04  xor     eax, eax
0x180044b06  mov     cs:g_ulMaxStackAllocSize, rax
0x180044b0d  test    rdx, rdx
0x180044b10  jz      short loc_180044B40
0x180044b12  mov     rax, gs:30h
0x180044b1b  mov     eax, [rax+1748h]
0x180044b21  mov     cs:g_ulAdditionalProbeSize, rax
0x180044b28  test    rax, rax
0x180044b2b  jnz     short loc_180044B36
0x180044b2d  mov     cs:g_ulAdditionalProbeSize, r8
0x180044b34  jmp     short loc_180044B4B
0x180044b36  add     rax, 8
0x180044b3a  cmp     rax, 8
0x180044b3e  jnb     short loc_180044B4B
0x180044b40  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180044b4b  lea     rax, ?Pku2uAllocate@@YAPEAX_K@Z; Pku2uAllocate(unsigned __int64)
0x180044b52  mov     cs:g_pfnAllocate, rax
0x180044b59  lea     rax, ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180044b60  mov     cs:g_pfnFree, rax
0x180044b67  add     rsp, 28h
0x180044b6b  retn
```
