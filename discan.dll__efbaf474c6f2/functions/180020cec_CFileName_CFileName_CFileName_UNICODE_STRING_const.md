# CFileName::CFileName(CFileName *,_UNICODE_STRING const *)

- ea: `0x180020cec`
- end: `0x180020d89`
- name: `??0CFileName@@QEAA@PEAV0@PEBU_UNICODE_STRING@@@Z`
- size: `157`
- prototype: `CFileName *__fastcall(CFileName *this, struct CFileName *, const struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024280`
- `0x180027b88`
- `0x180028360`

## callees

- `0x18000353c`
- `0x180003640`
- `0x180020cec`
- `0x180039010`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180020d6f`
- `ntdll!RtlCopyUnicodeString` at `0x180020d6f`

## pseudocode

```c
CFileName *__fastcall CFileName::CFileName(CFileName *this, struct CFileName *a2, const struct _UNICODE_STRING *a3)
{
  *(_QWORD *)this = &CFileName::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct CFileName *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + 5) = 0;
  if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CCRTAllocator>::AllocateBytes((char *)this + 40) )
    ATL::AtlThrowImpl(-2147024882);
  *((_QWORD *)this + 4) = *((_QWORD *)this + 5);
  *((_WORD *)this + 12) = 0;
  *((_WORD *)this + 13) = a3->Length;
  RtlCopyUnicodeString((PUNICODE_STRING)((char *)this + 24), a3);
  return this;
}

```

## disassembly

```asm
0x180020cec  mov     [rsp+arg_8], rbx
0x180020cf1  mov     [rsp+arg_10], rsi
0x180020cf6  mov     [rsp+arg_0], rcx
0x180020cfb  push    rdi
0x180020cfc  sub     rsp, 20h
0x180020d00  mov     rsi, r8
0x180020d03  mov     rbx, rcx
0x180020d06  lea     rax, ??_7CFileName@@6B@; const CFileName::`vftable'
0x180020d0d  mov     [rcx], rax
0x180020d10  mov     dword ptr [rcx+8], 0
0x180020d17  mov     [rcx+10h], rdx
0x180020d1b  test    rdx, rdx
0x180020d1e  jz      short loc_180020D30
0x180020d20  mov     rax, [rdx]
0x180020d23  mov     rcx, rdx
0x180020d26  mov     rax, [rax+8]
0x180020d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d2f  nop
0x180020d30  lea     rdi, [rbx+28h]
0x180020d34  mov     qword ptr [rdi], 0
0x180020d3b  movzx   edx, word ptr [rsi]
0x180020d3e  mov     rcx, rdi
0x180020d41  call    ?AllocateBytes@?$CHeapPtrBase@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180020d46  test    al, al
0x180020d48  jnz     short loc_180020D55
0x180020d4a  mov     ecx, 8007000Eh; int
0x180020d4f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020d55  lea     rcx, [rbx+18h]; DestinationString
0x180020d59  mov     rax, [rdi]
0x180020d5c  mov     [rcx+8], rax
0x180020d60  xor     eax, eax
0x180020d62  mov     [rcx], ax
0x180020d65  movzx   eax, word ptr [rsi]
0x180020d68  mov     [rbx+1Ah], ax
0x180020d6c  mov     rdx, rsi; SourceString
0x180020d6f  call    cs:__imp_RtlCopyUnicodeString
0x180020d75  nop
0x180020d76  mov     rax, rbx
0x180020d79  mov     rbx, [rsp+28h+arg_8]
0x180020d7e  mov     rsi, [rsp+28h+arg_10]
0x180020d83  add     rsp, 20h
0x180020d87  pop     rdi
0x180020d88  retn
```
