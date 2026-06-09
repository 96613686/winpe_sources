# VmbusTlFindAndReferenceServiceListener

- ea: `0x1400095a0`
- end: `0x140009644`
- name: `VmbusTlFindAndReferenceServiceListener`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14001f5e4`

## callees

- `0x140001608`
- `0x1400095a0`
- `0x14000a154`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000962c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000962c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009620`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140009620`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095b2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400095c2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400095c2`

## string_xrefs

- `0x14000960b`: `VmbusTlFindAndReferenceServiceListener`

## pseudocode

```c
__int64 __fastcall VmbusTlFindAndReferenceServiceListener(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v6; // r9
  __int64 v7; // rax
  unsigned int v8; // ebx

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  LOBYTE(v6) = 1;
  v7 = VmbusTlFindAndReferenceObjectInTable(a1, a1 + 168, a2, v6);
  if ( v7 )
  {
    *a3 = v7;
    v8 = 0;
  }
  else
  {
    v8 = -1073741275;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((unsigned int)"VmbusTlFindAndReferenceServiceListener", 307, -1073741275, a1 + 112, a2);
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return v8;
}

```

## disassembly

```asm
0x1400095a0  push    rbx
0x1400095a2  push    rbp
0x1400095a3  push    rsi
0x1400095a4  push    rdi
0x1400095a5  sub     rsp, 38h
0x1400095a9  mov     rbx, r8
0x1400095ac  mov     rbp, rdx
0x1400095af  mov     rdi, rcx
0x1400095b2  call    cs:__imp_KeEnterCriticalRegion
0x1400095b9  nop     dword ptr [rax+rax+00h]
0x1400095be  lea     rcx, [rdi+10h]; FastMutex
0x1400095c2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400095c9  nop     dword ptr [rax+rax+00h]
0x1400095ce  lea     rdx, [rdi+0A8h]
0x1400095d5  mov     r9b, 1
0x1400095d8  mov     r8, rbp
0x1400095db  mov     rcx, rdi
0x1400095de  call    VmbusTlFindAndReferenceObjectInTable
0x1400095e3  test    rax, rax
0x1400095e6  jz      short loc_1400095EF
0x1400095e8  mov     [rbx], rax
0x1400095eb  xor     ebx, ebx
0x1400095ed  jmp     short loc_14000961C
0x1400095ef  mov     edx, cs:dword_140013058
0x1400095f5  mov     ebx, 0C0000225h
0x1400095fa  cmp     edx, 2
0x1400095fd  jbe     short loc_14000961C
0x1400095ff  lea     r9, [rdi+70h]
0x140009603  mov     [rsp+58h+var_38], rbp
0x140009608  mov     r8d, ebx
0x14000960b  lea     rcx, aVmbustlfindand_2; "VmbusTlFindAndReferenceServiceListener"
0x140009612  mov     edx, 133h
0x140009617  call    HvsocketTraceServiceError
0x14000961c  lea     rcx, [rdi+10h]; FastMutex
0x140009620  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140009627  nop     dword ptr [rax+rax+00h]
0x14000962c  call    cs:__imp_KeLeaveCriticalRegion
0x140009633  nop     dword ptr [rax+rax+00h]
0x140009638  mov     eax, ebx
0x14000963a  add     rsp, 38h
0x14000963e  pop     rdi
0x14000963f  pop     rsi
0x140009640  pop     rbp
0x140009641  pop     rbx
0x140009642  retn
```
