# Pku2uImportContext

- ea: `0x140021db0`
- end: `0x140021e9a`
- name: `Pku2uImportContext`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140007008`
- `0x140021db0`
- `0x1400299f8`
- `0x140029d94`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140021e3f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140021e3f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140021e6b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140021e6b`

## string_xrefs

- `0x140021e1c`: `Failed to create kernel mode context: 0x%x\n`

## pseudocode

```c
__int64 __fastcall Pku2uImportContext(int a1, int a2, _QWORD *a3)
{
  int KernelModeContext; // eax
  PVOID v7; // rbx
  unsigned int v8; // edi
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  P = 0;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uImportContext called\n");
  KernelModeContext = Pku2uCreateKernelModeContext(0, a1, (unsigned int)&P, a2, 128);
  v7 = P;
  v8 = KernelModeContext;
  if ( KernelModeContext >= 0 )
  {
    if ( !Pku2uCryptInitialized )
    {
      ExEnterCriticalRegionAndAcquireResourceExclusive(&Pku2uGlobalResource);
      if ( !Pku2uCryptInitialized )
        Pku2uCryptInitialized = (unsigned int)LibAttach() != 0;
      ExReleaseResourceAndLeaveCriticalRegion(&Pku2uGlobalResource);
    }
    *a3 = v7;
  }
  else if ( KsecInfoLevel )
  {
    KsecDebugOut(1, "Failed to create kernel mode context: 0x%x\n", KernelModeContext);
  }
  if ( v7 )
    Pku2uDereferenceContext(v7);
  return v8;
}

```

## disassembly

```asm
0x140021db0  mov     [rsp+arg_0], rbx
0x140021db5  mov     [rsp+arg_8], rsi
0x140021dba  push    rdi
0x140021dbb  sub     rsp, 30h
0x140021dbf  cmp     cs:KsecInfoLevel, 0
0x140021dc6  mov     rsi, r8
0x140021dc9  mov     rbx, rdx
0x140021dcc  mov     [rsp+38h+P], 0
0x140021dd5  mov     rdi, rcx
0x140021dd8  jz      short loc_140021DEB
0x140021dda  lea     rdx, aPku2uimportcon; "Pku2uImportContext called\n"
0x140021de1  mov     ecx, 4
0x140021de6  call    KsecDebugOut
0x140021deb  mov     r9, rbx
0x140021dee  mov     [rsp+38h+var_18], 80h
0x140021df6  lea     r8, [rsp+38h+P]
0x140021dfb  mov     rdx, rdi
0x140021dfe  xor     ecx, ecx
0x140021e00  call    Pku2uCreateKernelModeContext
0x140021e05  mov     rbx, [rsp+38h+P]
0x140021e0a  mov     edi, eax
0x140021e0c  test    eax, eax
0x140021e0e  jns     short loc_140021E2F
0x140021e10  cmp     cs:KsecInfoLevel, 0
0x140021e17  jz      short loc_140021E7A
0x140021e19  mov     r8d, eax
0x140021e1c  lea     rdx, aFailedToCreate_0; "Failed to create kernel mode context: 0"...
0x140021e23  mov     ecx, 1
0x140021e28  call    KsecDebugOut
0x140021e2d  jmp     short loc_140021E7A
0x140021e2f  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140021e36  jnz     short loc_140021E77
0x140021e38  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x140021e3f  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140021e46  nop     dword ptr [rax+rax+00h]
0x140021e4b  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140021e52  jnz     short loc_140021E64
0x140021e54  call    LibAttach
0x140021e59  test    eax, eax
0x140021e5b  jz      short loc_140021E64
0x140021e5d  mov     cs:?Pku2uCryptInitialized@@3EA, 1; uchar Pku2uCryptInitialized
0x140021e64  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x140021e6b  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140021e72  nop     dword ptr [rax+rax+00h]
0x140021e77  mov     [rsi], rbx
0x140021e7a  test    rbx, rbx
0x140021e7d  jz      short loc_140021E87
0x140021e7f  mov     rcx, rbx; P
0x140021e82  call    Pku2uDereferenceContext
0x140021e87  mov     rbx, [rsp+38h+arg_0]
0x140021e8c  mov     eax, edi
0x140021e8e  mov     rsi, [rsp+38h+arg_8]
0x140021e93  add     rsp, 30h
0x140021e97  pop     rdi
0x140021e98  retn
```
