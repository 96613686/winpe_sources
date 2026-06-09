# CAssociationWriteCallback::Create(void *,IAepAssociationWriteCallback * *)

- ea: `0x140018438`
- end: `0x14001849e`
- name: `?Create@CAssociationWriteCallback@@SAJPEAXPEAPEAUIAepAssociationWriteCallback@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(void *, struct IAepAssociationWriteCallback **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cb50`

## callees

- `0x14000190c`
- `0x140018438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140018483`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140018483`

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::Create(void *a1, struct IAepAssociationWriteCallback **a2)
{
  unsigned int v4; // edi
  void *v6; // rbx

  v4 = 0;
  if ( !a2 )
    return 2147942487LL;
  try
  {
    *a2 = 0;
    v6 = operator new(0x28u);
    *(_QWORD *)v6 = &CAssociationWriteCallback::`vftable';
    *((_DWORD *)v6 + 2) = 1;
    *((_QWORD *)v6 + 2) = a1;
    *((_DWORD *)v6 + 8) = 1;
    InitializeSRWLock((PSRWLOCK)v6 + 3);
    *a2 = (struct IAepAssociationWriteCallback *)v6;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147467259;
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x140018438  push    rbx
0x14001843a  push    rsi
0x14001843b  push    rdi
0x14001843c  push    r14
0x14001843e  sub     rsp, 28h
0x140018442  mov     rsi, rdx
0x140018445  mov     r14, rcx
0x140018448  xor     edi, edi
0x14001844a  test    rdx, rdx
0x14001844d  jnz     short loc_140018456
0x14001844f  mov     eax, 80070057h
0x140018454  jmp     short loc_140018494
0x140018456  mov     [rdx], rdi
0x140018459  mov     ecx, 28h ; '('; Size
0x14001845e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018463  mov     rbx, rax
0x140018466  lea     rax, ??_7CAssociationWriteCallback@@6B@; const CAssociationWriteCallback::`vftable'
0x14001846d  mov     [rbx], rax
0x140018470  mov     eax, 1
0x140018475  mov     [rbx+8], eax
0x140018478  mov     [rbx+10h], r14
0x14001847c  mov     [rbx+20h], eax
0x14001847f  lea     rcx, [rbx+18h]; SRWLock
0x140018483  call    cs:__imp_InitializeSRWLock
0x140018489  mov     [rsi], rbx
0x14001848c  jmp     short loc_140018492
0x14001848e  mov     edi, [rsp+48h+arg_8]
0x140018492  mov     eax, edi
0x140018494  add     rsp, 28h
0x140018498  pop     r14
0x14001849a  pop     rdi
0x14001849b  pop     rsi
0x14001849c  pop     rbx
0x14001849d  retn
```
