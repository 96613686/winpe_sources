# CAssociationReadCallback::Create(void *,IAepAssociationReadCallback * *)

- ea: `0x140018290`
- end: `0x1400182f6`
- name: `?Create@CAssociationReadCallback@@SAJPEAXPEAPEAUIAepAssociationReadCallback@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(void *, struct IAepAssociationReadCallback **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c970`

## callees

- `0x14000190c`
- `0x140018290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400182db`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400182db`

## pseudocode

```c
__int64 __fastcall CAssociationReadCallback::Create(void *a1, struct IAepAssociationReadCallback **a2)
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
    *(_QWORD *)v6 = &CAssociationReadCallback::`vftable';
    *((_DWORD *)v6 + 2) = 1;
    *((_QWORD *)v6 + 2) = a1;
    *((_DWORD *)v6 + 8) = 1;
    InitializeSRWLock((PSRWLOCK)v6 + 3);
    *a2 = (struct IAepAssociationReadCallback *)v6;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x140018290  push    rbx
0x140018292  push    rsi
0x140018293  push    rdi
0x140018294  push    r14
0x140018296  sub     rsp, 28h
0x14001829a  mov     rsi, rdx
0x14001829d  mov     r14, rcx
0x1400182a0  xor     edi, edi
0x1400182a2  test    rdx, rdx
0x1400182a5  jnz     short loc_1400182AE
0x1400182a7  mov     eax, 80070057h
0x1400182ac  jmp     short loc_1400182EC
0x1400182ae  mov     [rdx], rdi
0x1400182b1  mov     ecx, 28h ; '('; Size
0x1400182b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400182bb  mov     rbx, rax
0x1400182be  lea     rax, ??_7CAssociationReadCallback@@6B@; const CAssociationReadCallback::`vftable'
0x1400182c5  mov     [rbx], rax
0x1400182c8  mov     eax, 1
0x1400182cd  mov     [rbx+8], eax
0x1400182d0  mov     [rbx+10h], r14
0x1400182d4  mov     [rbx+20h], eax
0x1400182d7  lea     rcx, [rbx+18h]; SRWLock
0x1400182db  call    cs:__imp_InitializeSRWLock
0x1400182e1  mov     [rsi], rbx
0x1400182e4  jmp     short loc_1400182EA
0x1400182e6  mov     edi, [rsp+48h+arg_8]
0x1400182ea  mov     eax, edi
0x1400182ec  add     rsp, 28h
0x1400182f0  pop     r14
0x1400182f2  pop     rdi
0x1400182f3  pop     rsi
0x1400182f4  pop     rbx
0x1400182f5  retn
```
