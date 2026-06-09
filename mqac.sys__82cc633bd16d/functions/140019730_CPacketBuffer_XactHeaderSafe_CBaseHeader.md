# CPacketBuffer::XactHeaderSafe(CBaseHeader *)

- ea: `0x140019730`
- end: `0x140019767`
- name: `?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z`
- size: `55`
- prototype: `struct CXactHeader *__fastcall(struct CBaseHeader *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140014e18`
- `0x140018dc8`
- `0x14001c868`
- `0x14001cb24`
- `0x14001d69c`
- `0x14001e4c8`
- `0x14001fe88`

## callees

- `0x140001c94`
- `0x140002460`
- `0x140019730`

## pseudocode

```c
struct CXactHeader *__fastcall CPacketBuffer::XactHeaderSafe(struct CBaseHeader *a1)
{
  unsigned __int8 *v2; // rbx
  char *NextSectionSafe; // rax

  if ( (*((_DWORD *)a1 + 15) & 0x100000) == 0 )
    return 0;
  v2 = (unsigned __int8 *)a1 + *((unsigned int *)a1 + 2);
  NextSectionSafe = CUserHeader::GetNextSectionSafe((struct CBaseHeader *)((char *)a1 + 16), v2);
  return (struct CXactHeader *)drv_section_cast_safe<CXactHeader *>(NextSectionSafe, v2);
}

```

## disassembly

```asm
0x140019730  push    rbx
0x140019732  sub     rsp, 20h
0x140019736  test    dword ptr [rcx+3Ch], 100000h
0x14001973d  jnz     short loc_140019743
0x14001973f  xor     eax, eax
0x140019741  jmp     short loc_140019760
0x140019743  mov     ebx, [rcx+8]
0x140019746  add     rbx, rcx
0x140019749  add     rcx, 10h; this
0x14001974d  mov     rdx, rbx; unsigned __int8 *
0x140019750  call    ?GetNextSectionSafe@CUserHeader@@QEBAPEADQEAE@Z; CUserHeader::GetNextSectionSafe(uchar * const)
0x140019755  mov     rcx, rax
0x140019758  mov     rdx, rbx
0x14001975b  call    ??$drv_section_cast_safe@PEAUCXactHeader@@@@YAPEAUCXactHeader@@PEAXPEAD@Z; drv_section_cast_safe<CXactHeader *>(void *,char *)
0x140019760  add     rsp, 20h
0x140019764  pop     rbx
0x140019765  retn
```
