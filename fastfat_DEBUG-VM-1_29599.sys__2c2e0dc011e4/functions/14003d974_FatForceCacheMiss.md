# FatForceCacheMiss

- ea: `0x14003d974`
- end: `0x14003dad8`
- name: `FatForceCacheMiss`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003dae0`

## callees

- `0x14003d974`
- `0x14003e870`
- `0x1400465f4`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x14003da68`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003da68`
- `ntoskrnl!MmFlushImageSection` at `0x14003da4c`
- `ntoskrnl!MmFlushImageSection` at `0x14003da4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003da8d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003dab9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e924`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e957`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003da8d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003dab9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e924`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e957`
- `ntoskrnl!ExRaiseStatus` at `0x14003d9a2`
- `ntoskrnl!ExRaiseStatus` at `0x14003d9a2`

## pseudocode

```c
void __fastcall FatForceCacheMiss(__int64 a1, __int64 a2, int a3)
{
  char v6; // r15
  _QWORD *v7; // r14
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r14
  SECTION_OBJECT_POINTERS *v11; // rdi
  PVOID DataSectionObject; // rsi
  _QWORD *i; // rdi

  if ( (*(_DWORD *)(a1 + 68) & 2) == 0 )
  {
    *(_DWORD *)(a1 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  v6 = 0;
  if ( *(_WORD *)a2 != 1282 )
  {
    v7 = (_QWORD *)(a2 + 320);
    v8 = *(_QWORD **)(a2 + 320);
    if ( v8 != (_QWORD *)(a2 + 320) )
    {
      v6 = 1;
      do
      {
        FatAcquireExclusiveFcb(a1, v8 - 20);
        v8 = (_QWORD *)*v8;
      }
      while ( v8 != v7 );
    }
  }
  FatAcquireExclusiveFcb(a1, a2);
  v10 = *(_QWORD *)(a2 + 184);
  *(_DWORD *)(a2 + 192) |= 8u;
  _InterlockedAnd((volatile signed __int32 *)(v10 + 200), 0xFFFFFEFF);
  if ( a3 )
    FatFlushFile(v9, a2, a3);
  if ( (*(_DWORD *)(v10 + 200) & 0x100) == 0 )
  {
    v11 = *(SECTION_OBJECT_POINTERS **)(a2 + 120);
    DataSectionObject = v11->DataSectionObject;
    if ( v11->ImageSectionObject )
      MmFlushImageSection(v11, MmFlushForWrite);
    if ( DataSectionObject )
      CcPurgeCacheSection(v11, 0, 0, 0);
  }
  if ( v6 )
  {
    for ( i = *(_QWORD **)(a2 + 320); i != (_QWORD *)(a2 + 320); i = (_QWORD *)*i )
      ExReleaseResourceLite((PERESOURCE)*(i - 19));
  }
  if ( (*(_DWORD *)(v10 + 200) & 0x100) == 0 )
  {
    *(_DWORD *)(a2 + 192) &= ~8u;
    ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
  }
}

```

## disassembly

```asm
0x14003d974  mov     [rsp+arg_10], rbx
0x14003d979  mov     [rsp+arg_8], rdx
0x14003d97e  push    rsi
0x14003d97f  push    rdi
0x14003d980  push    r12
0x14003d982  push    r14
0x14003d984  push    r15
0x14003d986  sub     rsp, 20h
0x14003d98a  mov     r12d, r8d
0x14003d98d  mov     rbx, rdx
0x14003d990  mov     rsi, rcx
0x14003d993  mov     eax, [rcx+44h]
0x14003d996  test    al, 2
0x14003d998  jnz     short loc_14003D9AF
0x14003d99a  mov     ecx, 0C00000D8h; Status
0x14003d99f  mov     [rsi+48h], ecx
0x14003d9a2  call    cs:__imp_ExRaiseStatus
0x14003d9af  xor     r15b, r15b
0x14003d9b2  mov     [rsp+48h+arg_0], r15b
0x14003d9b7  mov     eax, 502h
0x14003d9bc  cmp     [rdx], ax
0x14003d9bf  jz      short loc_14003D9EF
0x14003d9c1  lea     r14, [rdx+140h]
0x14003d9c8  mov     rdi, [r14]
0x14003d9cb  cmp     rdi, r14
0x14003d9ce  jz      short loc_14003D9EF
0x14003d9d0  mov     r15b, 1
0x14003d9d3  mov     [rsp+48h+arg_0], r15b
0x14003d9d8  lea     rdx, [rdi-0A0h]
0x14003d9df  mov     rcx, rsi
0x14003d9e2  call    FatAcquireExclusiveFcb
0x14003d9e7  mov     rdi, [rdi]
0x14003d9ea  cmp     rdi, r14
0x14003d9ed  jnz     short loc_14003D9D8
0x14003d9ef  mov     rdx, rbx
0x14003d9f2  mov     rcx, rsi
0x14003d9f5  call    FatAcquireExclusiveFcb
0x14003d9fa  mov     r14, [rbx+0B8h]
0x14003da01  mov     [rsp+48h+arg_18], r14
0x14003da06  or      dword ptr [rbx+0C0h], 8
0x14003da0d  lock and dword ptr [r14+0C8h], 0FFFFFEFFh
0x14003da19  test    r12d, r12d
0x14003da1c  jz      short loc_14003DA29
0x14003da1e  mov     r8d, r12d
0x14003da21  mov     rdx, rbx
0x14003da24  call    FatFlushFile
0x14003da29  mov     eax, [r14+0C8h]
0x14003da30  bt      eax, 8
0x14003da34  jb      short loc_14003DA75
0x14003da36  mov     rdi, [rbx+78h]
0x14003da3a  mov     rsi, [rdi]
0x14003da3d  cmp     qword ptr [rdi+10h], 0
0x14003da42  jz      short loc_14003DA58
0x14003da44  mov     edx, 1; FlushType
0x14003da49  mov     rcx, rdi; SectionObjectPointer
0x14003da4c  call    cs:__imp_MmFlushImageSection
0x14003da53  nop     dword ptr [rax+rax+00h]
0x14003da58  test    rsi, rsi
0x14003da5b  jz      short loc_14003DA75
0x14003da5d  xor     r9d, r9d; Flags
0x14003da60  xor     r8d, r8d; Length
0x14003da63  xor     edx, edx; FileOffset
0x14003da65  mov     rcx, rdi; SectionObjectPointer
0x14003da68  call    cs:__imp_CcPurgeCacheSection
0x14003da6f  nop     dword ptr [rax+rax+00h]
0x14003da74  nop
0x14003da75  test    r15b, r15b
0x14003da78  jz      short loc_14003DAA1
0x14003da7a  lea     rsi, [rbx+140h]
0x14003da81  mov     rdi, [rsi]
0x14003da84  jmp     short loc_14003DA9C
0x14003da86  mov     rcx, [rdi-98h]; Resource
0x14003da8d  call    cs:__imp_ExReleaseResourceLite
0x14003da94  nop     dword ptr [rax+rax+00h]
0x14003da99  mov     rdi, [rdi]
0x14003da9c  cmp     rdi, rsi
0x14003da9f  jnz     short loc_14003DA86
0x14003daa1  mov     eax, [r14+0C8h]
0x14003daa8  bt      eax, 8
0x14003daac  jb      short loc_14003DAC5
0x14003daae  and     dword ptr [rbx+0C0h], 0FFFFFFF7h
0x14003dab5  mov     rcx, [rbx+8]; Resource
0x14003dab9  call    cs:__imp_ExReleaseResourceLite
0x14003dac0  nop     dword ptr [rax+rax+00h]
0x14003dac5  mov     rbx, [rsp+48h+arg_10]
0x14003daca  add     rsp, 20h
0x14003dace  pop     r15
0x14003dad0  pop     r14
0x14003dad2  pop     r12
0x14003dad4  pop     rdi
0x14003dad5  pop     rsi
0x14003dad6  retn
0x14005e8f8  push    rbx
0x14005e8fa  push    rbp
0x14005e8fb  push    rdi
0x14005e8fc  sub     rsp, 20h
0x14005e900  mov     rbp, rdx
0x14005e903  cmp     byte ptr [rbp+50h], 0
0x14005e907  jz      short loc_14005E938
0x14005e909  mov     rcx, [rbp+58h]
0x14005e90d  mov     rbx, [rcx+140h]
0x14005e914  lea     rdi, [rcx+140h]
0x14005e91b  jmp     short loc_14005E933
0x14005e91d  mov     rcx, [rbx-98h]; Resource
0x14005e924  call    cs:__imp_ExReleaseResourceLite
0x14005e92b  nop     dword ptr [rax+rax+00h]
0x14005e930  mov     rbx, [rbx]
0x14005e933  cmp     rbx, rdi
0x14005e936  jnz     short loc_14005E91D
0x14005e938  mov     rax, [rbp+68h]
0x14005e93c  mov     ecx, [rax+0C8h]
0x14005e942  bt      ecx, 8
0x14005e946  jb      short loc_14005E964
0x14005e948  mov     rcx, [rbp+58h]
0x14005e94c  and     dword ptr [rcx+0C0h], 0FFFFFFF7h
0x14005e953  mov     rcx, [rcx+8]; Resource
0x14005e957  call    cs:__imp_ExReleaseResourceLite
0x14005e95e  nop     dword ptr [rax+rax+00h]
0x14005e963  nop
0x14005e964  add     rsp, 20h
0x14005e968  pop     rdi
0x14005e969  pop     rbp
0x14005e96a  pop     rbx
0x14005e96b  retn
```
