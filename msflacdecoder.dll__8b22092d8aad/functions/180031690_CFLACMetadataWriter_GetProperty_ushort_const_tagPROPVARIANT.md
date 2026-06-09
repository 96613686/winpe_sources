# CFLACMetadataWriter::GetProperty(ushort const *,tagPROPVARIANT *)

- ea: `0x180031690`
- end: `0x1800316d7`
- name: `?GetProperty@CFLACMetadataWriter@@UEAAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `71`
- prototype: `int(CFLACMetadataWriter *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d69c`

## callees

- `0x180031074`
- `0x180031690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800316bf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800316bf`

## pseudocode

```c
HRESULT __fastcall CFLACMetadataWriter::GetProperty(
        CFLACMetadataWriter *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int PropertyIndex; // eax

  PropertyIndex = CFLACMetadataWriter::FindPropertyIndex((CFLACMetadataWriter *)((char *)this - 8), a2);
  if ( PropertyIndex == -1 )
    return -1072873843;
  else
    return PropVariantCopy(a3, (const PROPVARIANT *)(*((_QWORD *)this + 11) + 24LL * PropertyIndex));
}

```

## disassembly

```asm
0x180031690  mov     [rsp+arg_0], rbx
0x180031695  push    rdi
0x180031696  sub     rsp, 20h
0x18003169a  mov     rbx, rcx
0x18003169d  mov     rdi, r8
0x1800316a0  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800316a4  call    ?FindPropertyIndex@CFLACMetadataWriter@@IEAAKPEBG@Z; CFLACMetadataWriter::FindPropertyIndex(ushort const *)
0x1800316a9  cmp     eax, 0FFFFFFFFh
0x1800316ac  jz      short loc_1800316C7
0x1800316ae  mov     eax, eax
0x1800316b0  mov     rcx, rdi; pvarDest
0x1800316b3  lea     rdx, [rax+rax*2]
0x1800316b7  mov     rax, [rbx+58h]
0x1800316bb  lea     rdx, [rax+rdx*8]; pvarSrc
0x1800316bf  call    cs:__imp_PropVariantCopy
0x1800316c5  jmp     short loc_1800316CC
0x1800316c7  mov     eax, 0C00D3E8Dh
0x1800316cc  mov     rbx, [rsp+28h+arg_0]
0x1800316d1  add     rsp, 20h
0x1800316d5  pop     rdi
0x1800316d6  retn
```
