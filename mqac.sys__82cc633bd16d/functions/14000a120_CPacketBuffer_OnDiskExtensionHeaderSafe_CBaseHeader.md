# CPacketBuffer::OnDiskExtensionHeaderSafe(CBaseHeader *)

- ea: `0x14000a120`
- end: `0x14000a1ce`
- name: `?OnDiskExtensionHeaderSafe@CPacketBuffer@@SAPEAVCOnDiskExtensionHeader@@PEAUCBaseHeader@@@Z`
- size: `174`
- prototype: `struct COnDiskExtensionHeader *__fastcall(struct CBaseHeader *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000a224`
- `0x14001569c`

## callees

- `0x140002ee8`
- `0x140009c34`
- `0x14000a120`

## pseudocode

```c
struct COnDiskExtensionHeader *__fastcall CPacketBuffer::OnDiskExtensionHeaderSafe(struct CBaseHeader *a1)
{
  unsigned int *v3; // rdi
  unsigned int *SectionAfterSrmpSafe; // rax
  unsigned int *v5; // rcx
  unsigned int *v6; // rbx
  char *v7; // rax
  unsigned __int64 v8; // rax
  unsigned __int64 v9[5]; // [rsp+20h] [rbp-28h] BYREF
  bool v10; // [rsp+50h] [rbp+8h] BYREF

  if ( !_bittest16((const signed __int16 *)a1 + 1, 0xCu) )
    return 0;
  v3 = (unsigned int *)((char *)a1 + *((unsigned int *)a1 + 2));
  SectionAfterSrmpSafe = (unsigned int *)CPacketBuffer::GetSectionAfterSrmpSafe(a1);
  v5 = SectionAfterSrmpSafe;
  if ( SectionAfterSrmpSafe && _bittest16((const signed __int16 *)a1 + 1, 0xBu) )
  {
    v6 = (unsigned int *)((char *)a1 + *((unsigned int *)a1 + 2));
    v7 = (char *)(SectionAfterSrmpSafe + 3);
    if ( v5 + 3 > v6
      || v7 < (char *)v5
      || (v9[1] = *v5,
          v8 = v5[1],
          v9[0] = (unsigned __int64)v5,
          v9[2] = v8,
          v10 = 0,
          v5 = (unsigned int *)SafeAddPointersEx(3, v9, &v10),
          v10) )
    {
      v5 = 0;
    }
    else if ( v5 > v6 )
    {
      v5 = 0;
    }
  }
  if ( v5 + 3 > v3 || v5 + 3 < v5 )
    return 0;
  return (struct COnDiskExtensionHeader *)v5;
}

```

## disassembly

```asm
0x14000a120  mov     [rsp+arg_8], rbx
0x14000a125  push    rdi
0x14000a126  sub     rsp, 40h
0x14000a12a  bt      word ptr [rcx+2], 0Ch
0x14000a130  mov     rbx, rcx
0x14000a133  jb      short loc_14000A13C
0x14000a135  xor     eax, eax
0x14000a137  jmp     loc_14000A1C2
0x14000a13c  mov     edi, [rcx+8]
0x14000a13f  add     rdi, rbx
0x14000a142  call    ?GetSectionAfterSrmpSafe@CPacketBuffer@@SAPEAXPEAUCBaseHeader@@@Z; CPacketBuffer::GetSectionAfterSrmpSafe(CBaseHeader *)
0x14000a147  mov     rcx, rax
0x14000a14a  test    rax, rax
0x14000a14d  jz      short loc_14000A1AF
0x14000a14f  bt      word ptr [rbx+2], 0Bh
0x14000a155  jnb     short loc_14000A1AF
0x14000a157  mov     eax, [rbx+8]
0x14000a15a  add     rbx, rax
0x14000a15d  lea     rax, [rcx+0Ch]
0x14000a161  cmp     rax, rbx
0x14000a164  ja      short loc_14000A1AD
0x14000a166  cmp     rax, rcx
0x14000a169  jb      short loc_14000A1AD
0x14000a16b  mov     eax, [rcx]
0x14000a16d  lea     r8, [rsp+48h+arg_0]; bool *
0x14000a172  mov     [rsp+48h+var_20], rax
0x14000a177  lea     rdx, [rsp+48h+var_28]; unsigned __int64 *
0x14000a17c  mov     eax, [rcx+4]
0x14000a17f  mov     [rsp+48h+var_28], rcx
0x14000a184  mov     ecx, 3; int
0x14000a189  mov     [rsp+48h+var_18], rax
0x14000a18e  mov     [rsp+48h+arg_0], 0
0x14000a193  call    ?SafeAddPointersEx@@YA_KHQEA_KPEA_N@Z; SafeAddPointersEx(int,unsigned __int64 * const,bool *)
0x14000a198  cmp     [rsp+48h+arg_0], 0
0x14000a19d  mov     rcx, rax
0x14000a1a0  jnz     short loc_14000A1AD
0x14000a1a2  xor     eax, eax
0x14000a1a4  cmp     rcx, rbx
0x14000a1a7  cmova   rcx, rax
0x14000a1ab  jmp     short loc_14000A1AF
0x14000a1ad  xor     ecx, ecx
0x14000a1af  lea     rax, [rcx+0Ch]
0x14000a1b3  cmp     rax, rdi
0x14000a1b6  ja      short loc_14000A1BD
0x14000a1b8  cmp     rax, rcx
0x14000a1bb  jnb     short loc_14000A1BF
0x14000a1bd  xor     ecx, ecx
0x14000a1bf  mov     rax, rcx
0x14000a1c2  mov     rbx, [rsp+48h+arg_8]
0x14000a1c7  add     rsp, 40h
0x14000a1cb  pop     rdi
0x14000a1cc  retn
```
