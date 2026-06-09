# RxSetupFcbForCaching

- ea: `0x1400080b0`
- end: `0x14000817e`
- name: `RxSetupFcbForCaching`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140054ca0`

## callees

- `0x140008030`
- `0x1400080b0`
- `0x140008190`
- `0x140071c90`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x140008118`
- `ntoskrnl!CcSetFileSizes` at `0x140008141`
- `ntoskrnl!CcSetFileSizes` at `0x140008118`
- `ntoskrnl!CcSetFileSizes` at `0x140008141`

## pseudocode

```c
void __fastcall RxSetupFcbForCaching(__int64 a1, struct _CC_FILE_SIZES *a2, struct _FILE_OBJECT *a3)
{
  struct _FILE_OBJECT *v3; // rbx
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  struct _CC_FILE_SIZES *v7; // rdx
  LARGE_INTEGER FileSize; // r8
  __int64 v9; // rcx

  v3 = a3;
  if ( (unsigned int)(*(_DWORD *)(a1 + 536) - 4) <= 1 )
  {
    LOBYTE(a3) = 1;
    RxAcquirePagingIoResource(a1, a2, a3);
    a2[1].FileSize.QuadPart = 0;
    a2[1].AllocationSize.QuadPart = 0;
    a2[1].ValidDataLength.QuadPart = 0;
    CcSetFileSizes(v3, a2 + 1);
    RxReleasePagingIoResource(a1, a2);
  }
  else
  {
    SectionObjectPointer = a3->SectionObjectPointer;
    if ( SectionObjectPointer && SectionObjectPointer->SharedCacheMap )
    {
      v7 = a2 + 1;
      FileSize = a2[1].FileSize;
      if ( FileSize.QuadPart > v7->AllocationSize.QuadPart )
      {
        v9 = *(unsigned int *)(a2[5].AllocationSize.QuadPart + 104);
        v7->AllocationSize.QuadPart = -v9 & (v9 + FileSize.QuadPart);
      }
      CcSetFileSizes(v3, v7);
    }
  }
}

```

## disassembly

```asm
0x1400080b0  mov     [rsp+arg_0], rbx
0x1400080b5  mov     [rsp+arg_10], rsi
0x1400080ba  mov     [rsp+Fcb], rdx
0x1400080bf  push    rdi
0x1400080c0  sub     rsp, 30h
0x1400080c4  mov     rbx, r8
0x1400080c7  mov     rsi, rdx
0x1400080ca  mov     rdi, rcx
0x1400080cd  mov     eax, [rcx+218h]
0x1400080d3  sub     eax, 4
0x1400080d6  cmp     eax, 1
0x1400080d9  jbe     short loc_1400080FC
0x1400080db  mov     rax, [r8+28h]
0x1400080df  test    rax, rax
0x1400080e2  jz      short loc_1400080EB
0x1400080e4  cmp     qword ptr [rax+8], 0
0x1400080e9  jnz     short loc_140008131
0x1400080eb  mov     rbx, [rsp+38h+arg_0]
0x1400080f0  mov     rsi, [rsp+38h+arg_10]
0x1400080f5  add     rsp, 30h
0x1400080f9  pop     rdi
0x1400080fa  retn
0x1400080fc  mov     r8b, 1
0x1400080ff  call    RxAcquirePagingIoResource
0x140008104  xor     eax, eax
0x140008106  mov     [rsi+20h], rax
0x14000810a  lea     rdx, [rsi+18h]; FileSizes
0x14000810e  mov     [rdx], rax
0x140008111  mov     [rsi+28h], rax
0x140008115  mov     rcx, rbx; FileObject
0x140008118  call    cs:__imp_CcSetFileSizes
0x14000811f  nop     dword ptr [rax+rax+00h]
0x140008124  mov     rdx, rsi
0x140008127  mov     rcx, rdi
0x14000812a  call    RxReleasePagingIoResource
0x14000812f  jmp     short loc_1400080EB
0x140008131  add     rdx, 18h; FileSizes
0x140008135  mov     r8, [rsi+20h]
0x140008139  cmp     r8, [rdx]
0x14000813c  jg      short loc_140008168
0x14000813e  mov     rcx, rbx; FileObject
0x140008141  call    cs:__imp_CcSetFileSizes
0x140008148  nop     dword ptr [rax+rax+00h]
0x14000814d  jmp     short loc_1400080EB
0x14000814f  mov     [rsp+38h+FlushFile], 1; FlushFile
0x140008154  mov     r9b, 1; UninitializeCacheMaps
0x140008157  xor     r8d, r8d; Length
0x14000815a  xor     edx, edx; FileOffset
0x14000815c  mov     rcx, [rsp+38h+Fcb]; Fcb
0x140008161  call    RxPurgeFcbInSystemCache
0x140008166  jmp     short loc_1400080EB
0x140008168  mov     rax, [rsi+78h]
0x14000816c  mov     ecx, [rax+68h]
0x14000816f  lea     rax, [rcx+r8]
0x140008173  neg     rcx
0x140008176  and     rax, rcx
0x140008179  mov     [rdx], rax
0x14000817c  jmp     short loc_14000813E
```
