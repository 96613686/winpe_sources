# HvStatspClientBufferUnshare

- ea: `0x1400101d0`
- end: `0x1400102e6`
- name: `HvStatspClientBufferUnshare`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, PRKPROCESS *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e0b0`
- `0x14001006c`
- `0x140010458`
- `0x1400140f0`

## callees

- `0x140002ae0`
- `0x140010130`
- `0x1400101d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400102cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14001028f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001028f`
- `ntoskrnl!KeStackAttachProcess` at `0x14001024e`
- `ntoskrnl!KeStackAttachProcess` at `0x14001024e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010262`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010262`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010273`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010273`

## pseudocode

```c
__int64 __fastcall HvStatspClientBufferUnshare(__int64 a1, __int64 a2, PRKPROCESS *a3)
{
  PRKPROCESS *v3; // rbx
  PRKPROCESS *v6; // rdi
  PRKPROCESS v7; // rcx
  PRKPROCESS **v8; // rdx
  _KAPC_STATE ApcState; // [rsp+20h] [rbp-58h] BYREF

  v3 = a3;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( a3 )
  {
    if ( a3 != (PRKPROCESS *)a1 || a2 )
      return 3221225485LL;
  }
  else
  {
    if ( !a2 )
      return 3221225485LL;
    v3 = (PRKPROCESS *)HvStatspClientBufferLookupUserInstance((_QWORD *)a1, a2);
    if ( !v3 )
      return 3221225485LL;
  }
  v6 = v3 + 3;
  if ( v3[4] )
  {
    KeStackAttachProcess(*v6, &ApcState);
    MmUnmapLockedPages(v3[4], *(PMDL *)(a1 + 56));
    KeUnstackDetachProcess(&ApcState);
    v3[4] = 0;
  }
  if ( *v6 )
  {
    ObfDereferenceObject(*v6);
    *v6 = 0;
  }
  if ( v3 != (PRKPROCESS *)a1 )
  {
    v7 = v3[1];
    if ( *((PRKPROCESS **)v7 + 1) != v3 + 1 || (v8 = (PRKPROCESS **)v3[2], *v8 != v3 + 1) )
      __fastfail(3u);
    *v8 = (PRKPROCESS *)v7;
    *((_QWORD *)v7 + 1) = v8;
    ExFreePoolWithTag(v3, 0x74537648u);
  }
  return 0;
}

```

## disassembly

```asm
0x1400101d0  push    rbx
0x1400101d2  push    rsi
0x1400101d3  push    rdi
0x1400101d4  sub     rsp, 60h
0x1400101d8  mov     rax, cs:__security_cookie
0x1400101df  xor     rax, rsp
0x1400101e2  mov     [rsp+78h+var_28], rax
0x1400101e7  xorps   xmm0, xmm0
0x1400101ea  mov     rbx, r8
0x1400101ed  mov     rsi, rcx
0x1400101f0  movups  xmmword ptr [rsp+78h+ApcState.ApcListHead.Flink], xmm0
0x1400101f5  movups  xmmword ptr [rsp+78h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400101fa  movups  xmmword ptr [rsp+78h+ApcState.Process], xmm0
0x1400101ff  test    r8, r8
0x140010202  jnz     short loc_140010231
0x140010204  test    rdx, rdx
0x140010207  jz      short loc_140010216
0x140010209  call    HvStatspClientBufferLookupUserInstance
0x14001020e  mov     rbx, rax
0x140010211  test    rax, rax
0x140010214  jnz     short loc_14001023B
0x140010216  mov     eax, 0C000000Dh
0x14001021b  mov     rcx, [rsp+78h+var_28]
0x140010220  xor     rcx, rsp; StackCookie
0x140010223  call    __security_check_cookie
0x140010228  add     rsp, 60h
0x14001022c  pop     rdi
0x14001022d  pop     rsi
0x14001022e  pop     rbx
0x14001022f  retn
0x140010231  cmp     rbx, rsi
0x140010234  jnz     short loc_140010216
0x140010236  test    rdx, rdx
0x140010239  jnz     short loc_140010216
0x14001023b  cmp     qword ptr [rbx+20h], 0
0x140010240  lea     rdi, [rbx+18h]
0x140010244  jz      short loc_140010287
0x140010246  mov     rcx, [rdi]; PROCESS
0x140010249  lea     rdx, [rsp+78h+ApcState]; ApcState
0x14001024e  call    cs:__imp_KeStackAttachProcess
0x140010255  nop     dword ptr [rax+rax+00h]
0x14001025a  mov     rdx, [rsi+38h]; MemoryDescriptorList
0x14001025e  mov     rcx, [rbx+20h]; BaseAddress
0x140010262  call    cs:__imp_MmUnmapLockedPages
0x140010269  nop     dword ptr [rax+rax+00h]
0x14001026e  lea     rcx, [rsp+78h+ApcState]; ApcState
0x140010273  call    cs:__imp_KeUnstackDetachProcess
0x14001027a  nop     dword ptr [rax+rax+00h]
0x14001027f  mov     qword ptr [rbx+20h], 0
0x140010287  mov     rcx, [rdi]; Object
0x14001028a  test    rcx, rcx
0x14001028d  jz      short loc_1400102A2
0x14001028f  call    cs:__imp_ObfDereferenceObject
0x140010296  nop     dword ptr [rax+rax+00h]
0x14001029b  mov     qword ptr [rdi], 0
0x1400102a2  cmp     rbx, rsi
0x1400102a5  jz      short loc_1400102D8
0x1400102a7  lea     rax, [rbx+8]
0x1400102ab  mov     rcx, [rax]
0x1400102ae  cmp     [rcx+8], rax
0x1400102b2  jnz     short loc_1400102DF
0x1400102b4  mov     rdx, [rax+8]
0x1400102b8  cmp     [rdx], rax
0x1400102bb  jnz     short loc_1400102DF
0x1400102bd  mov     [rdx], rcx
0x1400102c0  mov     [rcx+8], rdx
0x1400102c4  mov     edx, 74537648h; Tag
0x1400102c9  mov     rcx, rbx; P
0x1400102cc  call    cs:__imp_ExFreePoolWithTag
0x1400102d3  nop     dword ptr [rax+rax+00h]
0x1400102d8  xor     eax, eax
0x1400102da  jmp     loc_14001021B
0x1400102df  mov     ecx, 3
0x1400102e4  int     29h; Win8: RtlFailFast(ecx)
```
