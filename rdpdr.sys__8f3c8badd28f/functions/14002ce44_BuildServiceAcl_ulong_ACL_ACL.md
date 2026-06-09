# BuildServiceAcl(ulong *,_ACL *,_ACL * *)

- ea: `0x14002ce44`
- end: `0x14002cf4f`
- name: `?BuildServiceAcl@@YAJPEAKPEAU_ACL@@PEAPEAU1@@Z`
- size: `267`
- prototype: `__int64 __fastcall(unsigned int *, struct _ACL *Src, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1400114c4`

## callees

- `0x140001e30`
- `0x1400023f4`
- `0x140003188`
- `0x1400065c0`
- `0x14002ce44`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14002cea1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14002cea1`
- `ntoskrnl!RtlMapGenericMask` at `0x14002ceb5`
- `ntoskrnl!RtlMapGenericMask` at `0x14002ceb5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002ce6c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002ce6c`
- `ntoskrnl!RtlLengthSid` at `0x14002cec4`
- `ntoskrnl!RtlLengthSid` at `0x14002cec4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002cf20`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002cf20`

## pseudocode

```c
__int64 __fastcall BuildServiceAcl(unsigned int *a1, struct _ACL *Src, struct _ACL **a3)
{
  ULONG v6; // eax
  void *v7; // rax
  void *v8; // rbx
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ULONG v11; // esi
  struct _ACL *v12; // rax
  struct _ACL *v13; // rdi
  unsigned int v14; // edi
  DWORD AccessMask; // [rsp+58h] [rbp+20h] BYREF

  AccessMask = 0x10000000;
  v6 = RtlLengthRequiredSid(6u);
  v7 = operator new(v6, 0x100u);
  v8 = v7;
  if ( !v7 )
    return 3221225495LL;
  InitializeServiceSid(v7, a1);
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v11 = RtlLengthSid(v8) + Src->AclSize + 16;
  v12 = (struct _ACL *)operator new(v11, 0x100u);
  v13 = v12;
  if ( v12 )
  {
    memmove(v12, Src, Src->AclSize);
    v13->AclSize = v11 & 0xFFFC;
    RtlAddAccessAllowedAce(v13, 2u, AccessMask, v8);
    *a3 = v13;
    v14 = 0;
  }
  else
  {
    v14 = -1073741670;
  }
  operator delete(v8);
  return v14;
}

```

## disassembly

```asm
0x14002ce44  mov     [rsp+arg_0], rbx
0x14002ce49  mov     [rsp+arg_8], rbp
0x14002ce4e  push    rsi
0x14002ce4f  push    rdi
0x14002ce50  push    r14
0x14002ce52  sub     rsp, 20h
0x14002ce56  mov     rdi, rcx
0x14002ce59  mov     [rsp+38h+AccessMask], 10000000h
0x14002ce61  mov     ecx, 6; SubAuthorityCount
0x14002ce66  mov     r14, r8
0x14002ce69  mov     rbp, rdx
0x14002ce6c  call    cs:__imp_RtlLengthRequiredSid
0x14002ce73  nop     dword ptr [rax+rax+00h]
0x14002ce78  mov     ecx, eax; unsigned __int64
0x14002ce7a  mov     edx, 100h; unsigned __int64
0x14002ce7f  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002ce84  mov     rbx, rax
0x14002ce87  test    rax, rax
0x14002ce8a  jnz     short loc_14002CE96
0x14002ce8c  mov     eax, 0C0000017h
0x14002ce91  jmp     loc_14002CF3B
0x14002ce96  mov     rdx, rdi; unsigned int *
0x14002ce99  mov     rcx, rbx; Sid
0x14002ce9c  call    ?InitializeServiceSid@@YAXPEAXQEAK@Z; InitializeServiceSid(void *,ulong * const)
0x14002cea1  call    cs:__imp_IoGetFileObjectGenericMapping
0x14002cea8  nop     dword ptr [rax+rax+00h]
0x14002cead  mov     rdx, rax; GenericMapping
0x14002ceb0  lea     rcx, [rsp+38h+AccessMask]; AccessMask
0x14002ceb5  call    cs:__imp_RtlMapGenericMask
0x14002cebc  nop     dword ptr [rax+rax+00h]
0x14002cec1  mov     rcx, rbx; Sid
0x14002cec4  call    cs:__imp_RtlLengthSid
0x14002cecb  nop     dword ptr [rax+rax+00h]
0x14002ced0  movzx   esi, word ptr [rbp+2]
0x14002ced4  mov     edx, 100h; unsigned __int64
0x14002ced9  add     esi, 10h
0x14002cedc  add     esi, eax
0x14002cede  mov     ecx, esi; unsigned __int64
0x14002cee0  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002cee5  mov     rdi, rax
0x14002cee8  test    rax, rax
0x14002ceeb  jnz     short loc_14002CEF4
0x14002ceed  mov     edi, 0C000009Ah
0x14002cef2  jmp     short loc_14002CF31
0x14002cef4  movzx   r8d, word ptr [rbp+2]; Size
0x14002cef9  mov     rdx, rbp; Src
0x14002cefc  mov     rcx, rdi; void *
0x14002ceff  call    memmove
0x14002cf04  mov     eax, 0FFFCh
0x14002cf09  mov     r9, rbx; Sid
0x14002cf0c  and     si, ax
0x14002cf0f  mov     edx, 2; AceRevision
0x14002cf14  mov     [rdi+2], si
0x14002cf18  mov     rcx, rdi; Acl
0x14002cf1b  mov     r8d, [rsp+38h+AccessMask]; AccessMask
0x14002cf20  call    cs:__imp_RtlAddAccessAllowedAce
0x14002cf27  nop     dword ptr [rax+rax+00h]
0x14002cf2c  mov     [r14], rdi
0x14002cf2f  xor     edi, edi
0x14002cf31  mov     rcx, rbx; void *
0x14002cf34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cf39  mov     eax, edi
0x14002cf3b  mov     rbx, [rsp+38h+arg_0]
0x14002cf40  mov     rbp, [rsp+38h+arg_8]
0x14002cf45  add     rsp, 20h
0x14002cf49  pop     r14
0x14002cf4b  pop     rdi
0x14002cf4c  pop     rsi
0x14002cf4d  retn
```
