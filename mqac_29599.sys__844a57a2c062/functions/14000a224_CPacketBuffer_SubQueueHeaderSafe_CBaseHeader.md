# CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)

- ea: `0x14000a224`
- end: `0x14000a26e`
- name: `?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z`
- size: `74`
- prototype: `struct CSubQueueHeader *__fastcall(struct CBaseHeader *)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140007e3c`
- `0x14001569c`
- `0x140017ec4`
- `0x140018150`
- `0x14001821c`
- `0x140019284`
- `0x14001f1c4`
- `0x14001f3dc`
- `0x14001f714`
- `0x14001f8d4`

## callees

- `0x140003f24`
- `0x140009bac`
- `0x14000a120`
- `0x14000a224`

## pseudocode

```c
struct CSubQueueHeader *__fastcall CPacketBuffer::SubQueueHeaderSafe(struct CBaseHeader *a1)
{
  struct COnDiskExtensionHeader *v2; // rax
  char *v3; // rbx
  char *NextSectionDataPtrSafe; // rax

  if ( !_bittest16((const signed __int16 *)a1 + 1, 0xCu) )
    return 0;
  v2 = CPacketBuffer::OnDiskExtensionHeaderSafe(a1);
  if ( !v2 || (*((_BYTE *)v2 + 8) & 2) == 0 )
    return 0;
  v3 = (char *)a1 + *((unsigned int *)a1 + 2);
  NextSectionDataPtrSafe = GetNextSectionDataPtrSafe((unsigned __int64)v2, *(unsigned int *)v2, v3);
  return (struct CSubQueueHeader *)drv_section_cast_safe<CSubQueueHeader *>(NextSectionDataPtrSafe, v3);
}

```

## disassembly

```asm
0x14000a224  push    rbx
0x14000a226  sub     rsp, 20h
0x14000a22a  bt      word ptr [rcx+2], 0Ch
0x14000a230  mov     rbx, rcx
0x14000a233  jnb     short loc_14000A265
0x14000a235  call    ?OnDiskExtensionHeaderSafe@CPacketBuffer@@SAPEAVCOnDiskExtensionHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::OnDiskExtensionHeaderSafe(CBaseHeader *)
0x14000a23a  test    rax, rax
0x14000a23d  jz      short loc_14000A265
0x14000a23f  test    byte ptr [rax+8], 2
0x14000a243  jz      short loc_14000A265
0x14000a245  mov     ecx, [rbx+8]
0x14000a248  mov     edx, [rax]; unsigned __int64
0x14000a24a  add     rbx, rcx
0x14000a24d  mov     r8, rbx; char *
0x14000a250  mov     rcx, rax; unsigned __int64
0x14000a253  call    ?GetNextSectionDataPtrSafe@@YAPEAD_K0PEAD@Z; GetNextSectionDataPtrSafe(unsigned __int64,unsigned __int64,char *)
0x14000a258  mov     rcx, rax
0x14000a25b  mov     rdx, rbx
0x14000a25e  call    ??$drv_section_cast_safe@PEAVCSubQueueHeader@@@@YAPEAVCSubQueueHeader@@PEAXPEAD@Z; drv_section_cast_safe<CSubQueueHeader *>(void *,char *)
0x14000a263  jmp     short loc_14000A267
0x14000a265  xor     eax, eax
0x14000a267  add     rsp, 20h
0x14000a26b  pop     rbx
0x14000a26c  retn
```
