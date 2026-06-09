# CPacketBuffer::SecurityHeaderSafe(CBaseHeader *)

- ea: `0x14001e6e8`
- end: `0x14001e75f`
- name: `?SecurityHeaderSafe@CPacketBuffer@@SAPEAUCSecurityHeader@@PEAUCBaseHeader@@@Z`
- size: `119`
- prototype: `struct CSecurityHeader *__fastcall(struct CBaseHeader *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001d9e4`
- `0x14001e0c0`

## callees

- `0x140001c78`
- `0x140001c94`
- `0x140002304`
- `0x140002460`
- `0x14001e6e8`

## pseudocode

```c
struct CSecurityHeader *__fastcall CPacketBuffer::SecurityHeaderSafe(struct CBaseHeader *a1)
{
  char *v1; // rdi
  unsigned __int8 *v2; // rbx
  char *NextSectionSafe; // rax
  _DWORD *v4; // rax

  v1 = (char *)a1 + 16;
  if ( (*((_DWORD *)a1 + 15) & 0x80000) != 0 )
  {
    v2 = (unsigned __int8 *)a1 + *((unsigned int *)a1 + 2);
    NextSectionSafe = CUserHeader::GetNextSectionSafe((struct CBaseHeader *)((char *)a1 + 16), v2);
    if ( (*((_DWORD *)v1 + 11) & 0x100000) == 0 )
      return (struct CSecurityHeader *)drv_section_cast_safe<CSecurityHeader *>(NextSectionSafe, v2);
    v4 = (_DWORD *)drv_section_cast_safe<CXactHeader *>(NextSectionSafe, v2);
    if ( v4 )
    {
      NextSectionSafe = GetNextSectionPtrSafe((unsigned __int64)v4, 0x14u, 16LL * (*v4 & 1), (char *)v2);
      return (struct CSecurityHeader *)drv_section_cast_safe<CSecurityHeader *>(NextSectionSafe, v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001e6e8  mov     [rsp+arg_0], rbx
0x14001e6ed  push    rdi
0x14001e6ee  sub     rsp, 20h
0x14001e6f2  lea     rdi, [rcx+10h]
0x14001e6f6  test    dword ptr [rdi+2Ch], 80000h
0x14001e6fd  jz      short loc_14001E751
0x14001e6ff  mov     ebx, [rcx+8]
0x14001e702  add     rbx, rcx
0x14001e705  mov     rcx, rdi; this
0x14001e708  mov     rdx, rbx; unsigned __int8 *
0x14001e70b  call    ?GetNextSectionSafe@CUserHeader@@QEBAPEADQEAE@Z; CUserHeader::GetNextSectionSafe(uchar * const)
0x14001e710  test    dword ptr [rdi+2Ch], 100000h
0x14001e717  jz      short loc_14001E744
0x14001e719  mov     rdx, rbx
0x14001e71c  mov     rcx, rax
0x14001e71f  call    ??$drv_section_cast_safe@PEAUCXactHeader@@@@YAPEAUCXactHeader@@PEAXPEAD@Z; drv_section_cast_safe<CXactHeader *>(void *,char *)
0x14001e724  test    rax, rax
0x14001e727  jz      short loc_14001E751
0x14001e729  mov     r8d, [rax]
0x14001e72c  mov     r9, rbx; char *
0x14001e72f  and     r8d, 1
0x14001e733  mov     edx, 14h; unsigned __int64
0x14001e738  shl     r8, 4; unsigned __int64
0x14001e73c  mov     rcx, rax; unsigned __int64
0x14001e73f  call    ?GetNextSectionPtrSafe@@YAPEAD_K00PEAD@Z; GetNextSectionPtrSafe(unsigned __int64,unsigned __int64,unsigned __int64,char *)
0x14001e744  mov     rdx, rbx
0x14001e747  mov     rcx, rax
0x14001e74a  call    ??$drv_section_cast_safe@PEAUCSecurityHeader@@@@YAPEAUCSecurityHeader@@PEAXPEAD@Z; drv_section_cast_safe<CSecurityHeader *>(void *,char *)
0x14001e74f  jmp     short loc_14001E753
0x14001e751  xor     eax, eax
0x14001e753  mov     rbx, [rsp+28h+arg_0]
0x14001e758  add     rsp, 20h
0x14001e75c  pop     rdi
0x14001e75d  retn
```
