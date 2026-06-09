# SafeAllocaInitialize

- ea: `0x18001e928`
- end: `0x18001e9e4`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018560`
- `0x180018740`

## callees

- `0x18001e928`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18001e939`
- `ntdll!RtlImageNtHeader` at `0x18001e939`

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
  g_pfnAllocate = (__int64)WSTAllocate;
  result = WSTFree;
  g_pfnFree = (__int64)WSTFree;
  return result;
}

```

## disassembly

```asm
0x18001e928  sub     rsp, 28h
0x18001e92c  mov     rcx, gs:60h
0x18001e935  mov     rcx, [rcx+10h]; BaseAddress
0x18001e939  call    cs:__imp_RtlImageNtHeader
0x18001e93f  mov     rcx, gs:60h
0x18001e948  mov     r8d, 3000h
0x18001e94e  mov     rdx, rax
0x18001e951  cmp     byte ptr [rcx+2], 0
0x18001e955  jnz     short loc_18001E97C
0x18001e957  test    rax, rax
0x18001e95a  jz      short loc_18001E97C
0x18001e95c  mov     rax, [rax+60h]
0x18001e960  sub     rax, [rdx+68h]
0x18001e964  cmp     rax, r8
0x18001e967  jnb     short loc_18001E976
0x18001e969  mov     cs:g_ulMaxStackAllocSize, 0
0x18001e974  jmp     short loc_18001E98A
0x18001e976  mov     rax, [rdx+68h]
0x18001e97a  jmp     short loc_18001E97E
0x18001e97c  xor     eax, eax
0x18001e97e  mov     cs:g_ulMaxStackAllocSize, rax
0x18001e985  test    rdx, rdx
0x18001e988  jz      short loc_18001E9B8
0x18001e98a  mov     rax, gs:30h
0x18001e993  mov     eax, [rax+1748h]
0x18001e999  mov     cs:g_ulAdditionalProbeSize, rax
0x18001e9a0  test    rax, rax
0x18001e9a3  jnz     short loc_18001E9AE
0x18001e9a5  mov     cs:g_ulAdditionalProbeSize, r8
0x18001e9ac  jmp     short loc_18001E9C3
0x18001e9ae  add     rax, 8
0x18001e9b2  cmp     rax, 8
0x18001e9b6  jnb     short loc_18001E9C3
0x18001e9b8  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18001e9c3  lea     rax, ?WSTAllocate@@YAPEAX_K@Z; WSTAllocate(unsigned __int64)
0x18001e9ca  mov     cs:g_pfnAllocate, rax
0x18001e9d1  lea     rax, ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x18001e9d8  mov     cs:g_pfnFree, rax
0x18001e9df  add     rsp, 28h
0x18001e9e3  retn
```
