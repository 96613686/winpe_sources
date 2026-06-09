# NTCheckSharedAccess

- ea: `0x1400504dc`
- end: `0x140050595`
- name: `NTCheckSharedAccess`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400031bc`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140050555`
- `ntoskrnl!SeAccessCheck` at `0x140050555`
- `ntoskrnl!IoCheckShareAccess` at `0x140050578`
- `ntoskrnl!IoCheckShareAccess` at `0x140050578`

## pseudocode

```c
NTSTATUS __fastcall NTCheckSharedAccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  ULONG v5; // ebx
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF
  DWORD v8; // [rsp+68h] [rbp+10h] BYREF

  v7 = a1;
  v3 = *(_QWORD *)(a2 + 184);
  v8 = 0;
  LODWORD(v7) = 0;
  v5 = (*(_BYTE *)(v3 + 26) & 3) != 0;
  SeAccessCheck(
    *(PSECURITY_DESCRIPTOR *)(a3 + 168),
    (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL) + 32LL),
    0,
    *(_DWORD *)(*(_QWORD *)(v3 + 8) + 16LL),
    0,
    0,
    (PGENERIC_MAPPING)qword_1400381D0,
    *(_BYTE *)(a2 + 64),
    &v8,
    (PNTSTATUS)&v7);
  return IoCheckShareAccess(1u, v5, *(PFILE_OBJECT *)(v3 + 48), (PSHARE_ACCESS)(a3 + 136), 1u);
}

```

## disassembly

```asm
0x1400504dc  mov     r11, rsp
0x1400504df  mov     [r11+18h], rbx
0x1400504e3  mov     [r11+20h], rsi
0x1400504e7  mov     [r11+8], rcx
0x1400504eb  push    rdi
0x1400504ec  sub     rsp, 50h
0x1400504f0  mov     rdi, [rdx+0B8h]
0x1400504f7  lea     rax, [r11+8]
0x1400504fb  mov     [r11-10h], rax
0x1400504ff  xor     ecx, ecx
0x140050501  mov     [rsp+58h+arg_8], ecx
0x140050505  lea     rax, [r11+10h]
0x140050509  mov     [r11-18h], rax
0x14005050d  mov     r10, rdx
0x140050510  mov     dword ptr [rsp+58h+arg_0], ecx
0x140050514  mov     rsi, r8
0x140050517  mov     r9, [rdi+8]
0x14005051b  mov     ebx, ecx
0x14005051d  test    byte ptr [rdi+1Ah], 3
0x140050521  mov     al, [r10+40h]
0x140050525  mov     [rsp+58h+AccessMode], al; AccessMode
0x140050529  setnz   bl
0x14005052c  mov     rdx, [r9+8]
0x140050530  lea     rax, qword_1400381D0
0x140050537  mov     r9d, [r9+10h]; DesiredAccess
0x14005053b  add     rdx, 20h ; ' '; SubjectSecurityContext
0x14005053f  mov     [r11-28h], rax
0x140050543  xor     r8d, r8d; SubjectContextLocked
0x140050546  mov     [r11-30h], rcx
0x14005054a  mov     [rsp+58h+PreviouslyGrantedAccess], ecx; PreviouslyGrantedAccess
0x14005054e  mov     rcx, [rsi+0A8h]; SecurityDescriptor
0x140050555  call    cs:__imp_SeAccessCheck
0x14005055c  nop     dword ptr [rax+rax+00h]
0x140050561  mov     r8, [rdi+30h]; FileObject
0x140050565  lea     r9, [rsi+88h]; ShareAccess
0x14005056c  mov     edx, ebx; DesiredShareAccess
0x14005056e  mov     byte ptr [rsp+58h+PreviouslyGrantedAccess], 1; Update
0x140050573  mov     ecx, 1; DesiredAccess
0x140050578  call    cs:__imp_IoCheckShareAccess
0x14005057f  nop     dword ptr [rax+rax+00h]
0x140050584  mov     rbx, [rsp+58h+arg_10]
0x140050589  mov     rsi, [rsp+58h+arg_18]
0x14005058e  add     rsp, 50h
0x140050592  pop     rdi
0x140050593  retn
```
