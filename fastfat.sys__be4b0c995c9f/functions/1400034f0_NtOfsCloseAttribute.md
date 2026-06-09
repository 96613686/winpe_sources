# NtOfsCloseAttribute

- ea: `0x1400034f0`
- end: `0x140003633`
- name: `NtOfsCloseAttribute`
- size: `323`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140050780`
- `0x140050cf0`
- `0x140053a88`
- `0x140053b10`
- `0x140053c18`
- `0x140054480`
- `0x14005489c`
- `0x140056ccc`

## callees

- `0x14000179c`
- `0x1400034f0`
- `0x14003172c`
- `0x1400465f4`
- `0x1400492a4`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x140003585`
- `ntoskrnl!CcPurgeCacheSection` at `0x140003585`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400035a4`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400035a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400035e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000361b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400035e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000361b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400035fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400035fb`

## pseudocode

```c
void __fastcall NtOfsCloseAttribute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v6; // rbp
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // r9
  char v10; // r14
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx

  if ( (byte_140017D4D & 2) != 0 && *(_WORD *)a2 == 1282 )
  {
    if ( (*(_DWORD *)(a2 + 192) & 0x10000) != 0 )
    {
      v6 = 0;
      FatAcquireExclusiveFcb(a1, a2, a3, a4);
      v7 = *(_QWORD *)(a2 + 176);
      FatAcquireExclusiveFcb(a1, v7, v8, v9);
      v10 = *(_BYTE *)(a2 + 192) & 1;
      --*(_DWORD *)(*(_QWORD *)(a2 + 176) + 352LL);
      v11 = *(_QWORD *)(a2 + 176);
      if ( !*(_DWORD *)(v11 + 352) )
      {
        CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(v11 + 368) + 120LL), 0, 0, 0);
        CcUninitializeCacheMap(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 176) + 360LL), 0, 0);
        v12 = *(_QWORD *)(a2 + 176);
        v6 = *(void **)(v12 + 360);
        *(_QWORD *)(v12 + 360) = 0;
        *(_QWORD *)(*(_QWORD *)(a2 + 176) + 368LL) = 0;
        FatRemoveNames(v13, a2);
      }
      ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
      if ( v6 )
        ObfDereferenceObject(v6);
      if ( v10 )
        FatDeleteEfsAttributeOnDirectory(a1, v7);
      ExReleaseResourceLite(*(PERESOURCE *)(v7 + 8));
    }
    else
    {
      FatCloseFileHeader(a1, a2, a3, a4);
    }
  }
}

```

## disassembly

```asm
0x1400034f0  push    rbx
0x1400034f2  push    rbp
0x1400034f3  push    rsi
0x1400034f4  push    rdi
0x1400034f5  push    r14
0x1400034f7  sub     rsp, 20h
0x1400034fb  test    cs:byte_140017D4D, 2
0x140003502  mov     rbx, rdx
0x140003505  mov     rdi, rcx
0x140003508  jz      loc_140003627
0x14000350e  mov     eax, 502h
0x140003513  cmp     [rdx], ax
0x140003516  jnz     loc_140003627
0x14000351c  test    dword ptr [rdx+0C0h], 10000h
0x140003526  jnz     short loc_140003532
0x140003528  call    FatCloseFileHeader
0x14000352d  jmp     loc_140003627
0x140003532  xor     ebp, ebp
0x140003534  call    FatAcquireExclusiveFcb
0x140003539  mov     rsi, [rbx+0B0h]
0x140003540  mov     rcx, rdi
0x140003543  mov     rdx, rsi
0x140003546  call    FatAcquireExclusiveFcb
0x14000354b  mov     r14b, [rbx+0C0h]
0x140003552  mov     rax, [rbx+0B0h]
0x140003559  and     r14b, 1
0x14000355d  dec     dword ptr [rax+160h]
0x140003563  mov     rcx, [rbx+0B0h]
0x14000356a  cmp     [rcx+160h], ebp
0x140003570  jnz     short loc_1400035E3
0x140003572  mov     rcx, [rcx+170h]
0x140003579  xor     r9d, r9d; Flags
0x14000357c  xor     r8d, r8d; Length
0x14000357f  xor     edx, edx; FileOffset
0x140003581  mov     rcx, [rcx+78h]; SectionObjectPointer
0x140003585  call    cs:__imp_CcPurgeCacheSection
0x14000358c  nop     dword ptr [rax+rax+00h]
0x140003591  mov     rcx, [rbx+0B0h]
0x140003598  xor     r8d, r8d; UninitializeEvent
0x14000359b  xor     edx, edx; TruncateSize
0x14000359d  mov     rcx, [rcx+168h]; FileObject
0x1400035a4  call    cs:__imp_CcUninitializeCacheMap
0x1400035ab  nop     dword ptr [rax+rax+00h]
0x1400035b0  mov     rax, [rbx+0B0h]
0x1400035b7  mov     rdx, rbx
0x1400035ba  mov     rbp, [rax+168h]
0x1400035c1  mov     qword ptr [rax+168h], 0
0x1400035cc  mov     rax, [rbx+0B0h]
0x1400035d3  mov     qword ptr [rax+170h], 0
0x1400035de  call    FatRemoveNames
0x1400035e3  mov     rcx, [rbx+8]; Resource
0x1400035e7  call    cs:__imp_ExReleaseResourceLite
0x1400035ee  nop     dword ptr [rax+rax+00h]
0x1400035f3  test    rbp, rbp
0x1400035f6  jz      short loc_140003607
0x1400035f8  mov     rcx, rbp; Object
0x1400035fb  call    cs:__imp_ObfDereferenceObject
0x140003602  nop     dword ptr [rax+rax+00h]
0x140003607  test    r14b, r14b
0x14000360a  jz      short loc_140003617
0x14000360c  mov     rdx, rsi; int
0x14000360f  mov     rcx, rdi; int
0x140003612  call    FatDeleteEfsAttributeOnDirectory
0x140003617  mov     rcx, [rsi+8]; Resource
0x14000361b  call    cs:__imp_ExReleaseResourceLite
0x140003622  nop     dword ptr [rax+rax+00h]
0x140003627  add     rsp, 20h
0x14000362b  pop     r14
0x14000362d  pop     rdi
0x14000362e  pop     rsi
0x14000362f  pop     rbp
0x140003630  pop     rbx
0x140003631  retn
```
