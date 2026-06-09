# HvStatspClientBufferShare

- ea: `0x14000e0b0`
- end: `0x14000e227`
- name: `HvStatspClientBufferShare`
- size: `375`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fee8`

## callees

- `0x14000e0b0`
- `0x140010130`
- `0x1400101d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e11d`
- `ntoskrnl!ExAllocatePool2` at `0x14000e11d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e1a5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000e1a5`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000e167`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000e167`
- `ntoskrnl!ObfReferenceObject` at `0x14000e17a`
- `ntoskrnl!ObfReferenceObject` at `0x14000e17a`

## pseudocode

```c
__int64 __fastcall HvStatspClientBufferShare(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 Pool2; // rax
  _QWORD *v8; // r15
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  PEPROCESS CurrentProcess; // rax
  __int64 v12; // rax
  unsigned int v13; // r12d

  if ( a5 )
    *a5 = 0;
  if ( !*(_QWORD *)(a1 + 24) && !*(_QWORD *)(a1 + 32) && !HvStatspClientBufferLookupUserInstance() )
  {
    Pool2 = ExAllocatePool2(64, 40, 1951626824);
    v8 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      v9 = *(_QWORD **)(a1 + 48);
      if ( *v9 != a1 + 40 )
        __fastfail(3u);
      v10 = (_QWORD *)(Pool2 + 8);
      *v10 = a1 + 40;
      v10[1] = v9;
      *v9 = v10;
      *(_QWORD *)(a1 + 48) = v10;
      *v8 = a2;
      CurrentProcess = IoGetCurrentProcess();
      v8[3] = CurrentProcess;
      ObfReferenceObject(CurrentProcess);
      v8[4] = MmMapLockedPagesSpecifyCache(*(PMDL *)(a1 + 56), 1, MmCached, 0, 0, 0xC0000010);
      v12 = v8[4];
      if ( v12 )
      {
        v13 = 0;
        if ( a5 )
          *a5 = v12;
        return v13;
      }
    }
    else
    {
      v8 = 0;
    }
    v13 = -1073741670;
    if ( v8 != (_QWORD *)a1 )
      v8 = 0;
    HvStatspClientBufferUnshare(a1, a2, v8);
    return v13;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14000e0b0  mov     [rsp+arg_18], rbx
0x14000e0b5  mov     [rsp+arg_10], r8
0x14000e0ba  mov     [rsp+arg_8], rdx
0x14000e0bf  mov     [rsp+arg_0], rcx
0x14000e0c4  push    rsi
0x14000e0c5  push    rdi
0x14000e0c6  push    r12
0x14000e0c8  push    r14
0x14000e0ca  push    r15
0x14000e0cc  sub     rsp, 30h
0x14000e0d0  mov     rsi, rdx
0x14000e0d3  mov     rbx, rcx
0x14000e0d6  mov     rdi, [rsp+58h+arg_20]
0x14000e0de  xor     r14d, r14d
0x14000e0e1  test    rdi, rdi
0x14000e0e4  jz      short loc_14000E0E9
0x14000e0e6  mov     [rdi], r14
0x14000e0e9  cmp     qword ptr [rcx+18h], 0
0x14000e0ee  jnz     loc_14000E20F
0x14000e0f4  cmp     qword ptr [rcx+20h], 0
0x14000e0f9  jnz     loc_14000E20F
0x14000e0ff  call    HvStatspClientBufferLookupUserInstance
0x14000e104  test    rax, rax
0x14000e107  jnz     loc_14000E20F
0x14000e10d  mov     edx, 28h ; '('
0x14000e112  mov     ecx, 40h ; '@'
0x14000e117  mov     r8d, 74537648h
0x14000e11d  call    cs:__imp_ExAllocatePool2
0x14000e124  nop     dword ptr [rax+rax+00h]
0x14000e129  mov     r15, rax
0x14000e12c  mov     [rsp+58h+arg_10], rax
0x14000e131  test    rax, rax
0x14000e134  jnz     short loc_14000E13E
0x14000e136  mov     r15, r14
0x14000e139  jmp     loc_14000E1E2
0x14000e13e  lea     rcx, [rbx+28h]
0x14000e142  mov     rdx, [rcx+8]
0x14000e146  cmp     [rdx], rcx
0x14000e149  jz      short loc_14000E152
0x14000e14b  mov     ecx, 3
0x14000e150  int     29h; Win8: RtlFailFast(ecx)
0x14000e152  add     rax, 8
0x14000e156  mov     [rax], rcx
0x14000e159  mov     [rax+8], rdx
0x14000e15d  mov     [rdx], rax
0x14000e160  mov     [rcx+8], rax
0x14000e164  mov     [r15], rsi
0x14000e167  call    cs:__imp_IoGetCurrentProcess
0x14000e16e  nop     dword ptr [rax+rax+00h]
0x14000e173  mov     [r15+18h], rax
0x14000e177  mov     rcx, rax; Object
0x14000e17a  call    cs:__imp_ObfReferenceObject
0x14000e181  nop     dword ptr [rax+rax+00h]
0x14000e186  nop
0x14000e187  mov     [rsp+58h+Priority], 0C0000010h; Priority
0x14000e18f  mov     [rsp+58h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x14000e194  xor     r9d, r9d; RequestedAddress
0x14000e197  mov     r8d, 1; CacheType
0x14000e19d  movzx   edx, r8b; AccessMode
0x14000e1a1  mov     rcx, [rbx+38h]; MemoryDescriptorList
0x14000e1a5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000e1ac  nop     dword ptr [rax+rax+00h]
0x14000e1b1  mov     [r15+20h], rax
0x14000e1b5  jmp     short loc_14000E1D9
0x14000e1b7  mov     r15, [rsp+58h+arg_10]
0x14000e1bc  mov     qword ptr [r15+20h], 0
0x14000e1c4  xor     r14d, r14d
0x14000e1c7  mov     rdi, [rsp+58h+arg_20]
0x14000e1cf  mov     rsi, [rsp+58h+arg_8]
0x14000e1d4  mov     rbx, [rsp+58h+arg_0]
0x14000e1d9  mov     rax, [r15+20h]
0x14000e1dd  test    rax, rax
0x14000e1e0  jnz     short loc_14000E1FF
0x14000e1e2  mov     r12d, 0C000009Ah
0x14000e1e8  cmp     r15, rbx
0x14000e1eb  cmovnz  r15, r14
0x14000e1ef  mov     r8, r15
0x14000e1f2  mov     rdx, rsi
0x14000e1f5  mov     rcx, rbx
0x14000e1f8  call    HvStatspClientBufferUnshare
0x14000e1fd  jmp     short loc_14000E20A
0x14000e1ff  mov     r12d, r14d
0x14000e202  test    rdi, rdi
0x14000e205  jz      short loc_14000E20A
0x14000e207  mov     [rdi], rax
0x14000e20a  mov     eax, r12d
0x14000e20d  jmp     short loc_14000E214
0x14000e20f  mov     eax, 0C000000Dh
0x14000e214  mov     rbx, [rsp+58h+arg_18]
0x14000e219  add     rsp, 30h
0x14000e21d  pop     r15
0x14000e21f  pop     r14
0x14000e221  pop     r12
0x14000e223  pop     rdi
0x14000e224  pop     rsi
0x14000e225  retn
```
