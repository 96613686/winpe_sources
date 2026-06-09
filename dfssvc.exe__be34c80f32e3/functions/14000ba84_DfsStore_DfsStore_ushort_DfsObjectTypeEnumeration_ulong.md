# DfsStore::DfsStore(ushort *,DfsObjectTypeEnumeration,ulong *)

- ea: `0x14000ba84`
- end: `0x14000bb59`
- name: `??0DfsStore@@QEAA@PEAGW4DfsObjectTypeEnumeration@@PEAK@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140018c28`

## callees

- `0x1400011d0`
- `0x14000ba84`
- `0x1400586a8`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x14000bb26`
- `ntdll!RtlCopyUnicodeString` at `0x14000bb26`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000bac2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000bac2`

## pseudocode

```c
__int64 __fastcall DfsStore::DfsStore(__int64 a1, __int64 a2, int a3, int *a4)
{
  int inited; // ebx
  void *v8; // rax
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)a1 = &DfsStore::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = a3;
  SourceString = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 16));
  *(_DWORD *)(a1 + 24) = 0;
  inited = DfsRtlInitUnicodeStringEx(&SourceString, a2);
  if ( !inited )
  {
    *(_WORD *)(a1 + 34) = 2 * SourceString.MaximumLength;
    v8 = operator new(saturated_mul(SourceString.MaximumLength, 2u));
    *(_QWORD *)(a1 + 40) = v8;
    if ( v8 )
    {
      RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 32), &SourceString);
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_DWORD *)(a1 + 48) = 1;
    }
    else
    {
      inited = 8;
    }
  }
  *a4 = inited;
  return a1;
}

```

## disassembly

```asm
0x14000ba84  mov     [rsp+arg_0], rbx
0x14000ba89  mov     [rsp+arg_8], rsi
0x14000ba8e  push    rdi
0x14000ba8f  sub     rsp, 30h
0x14000ba93  and     qword ptr [rcx+28h], 0
0x14000ba98  lea     rax, ??_7DfsStore@@6B@; const DfsStore::`vftable'
0x14000ba9f  mov     [rcx], rax
0x14000baa2  mov     rdi, rcx
0x14000baa5  mov     dword ptr [rcx+8], 1
0x14000baac  xorps   xmm0, xmm0
0x14000baaf  mov     [rcx+0Ch], r8d
0x14000bab3  mov     rsi, r9
0x14000bab6  add     rcx, 10h; SRWLock
0x14000baba  mov     rbx, rdx
0x14000babd  movups  xmmword ptr [rsp+38h+SourceString.Length], xmm0
0x14000bac2  call    cs:__imp_InitializeSRWLock
0x14000bac9  nop     dword ptr [rax+rax+00h]
0x14000bace  and     dword ptr [rdi+18h], 0
0x14000bad2  lea     rcx, [rsp+38h+SourceString]
0x14000bad7  mov     rdx, rbx
0x14000bada  call    DfsRtlInitUnicodeStringEx
0x14000badf  mov     ebx, eax
0x14000bae1  test    eax, eax
0x14000bae3  jnz     short loc_14000BB43
0x14000bae5  movzx   ecx, [rsp+38h+SourceString.MaximumLength]
0x14000baea  lea     eax, [rbx+2]
0x14000baed  add     cx, cx
0x14000baf0  mov     [rdi+22h], cx
0x14000baf4  movzx   ecx, [rsp+38h+SourceString.MaximumLength]
0x14000baf9  mul     rcx
0x14000bafc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000bb03  cmovo   rax, rcx
0x14000bb07  mov     rcx, rax; Size
0x14000bb0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000bb0f  mov     [rdi+28h], rax
0x14000bb13  test    rax, rax
0x14000bb16  jnz     short loc_14000BB1D
0x14000bb18  lea     ebx, [rax+8]
0x14000bb1b  jmp     short loc_14000BB43
0x14000bb1d  lea     rcx, [rdi+20h]; DestinationString
0x14000bb21  lea     rdx, [rsp+38h+SourceString]; SourceString
0x14000bb26  call    cs:__imp_RtlCopyUnicodeString
0x14000bb2d  nop     dword ptr [rax+rax+00h]
0x14000bb32  and     qword ptr [rdi+38h], 0
0x14000bb37  and     qword ptr [rdi+48h], 0
0x14000bb3c  mov     dword ptr [rdi+30h], 1
0x14000bb43  mov     [rsi], ebx
0x14000bb45  mov     rax, rdi
0x14000bb48  mov     rbx, [rsp+38h+arg_0]
0x14000bb4d  mov     rsi, [rsp+38h+arg_8]
0x14000bb52  add     rsp, 30h
0x14000bb56  pop     rdi
0x14000bb57  retn
```
