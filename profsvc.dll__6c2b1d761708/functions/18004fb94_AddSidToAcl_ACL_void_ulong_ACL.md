# AddSidToAcl(_ACL *,void *,ulong,_ACL * *)

- ea: `0x18004fb94`
- end: `0x18004fcb3`
- name: `?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z`
- size: `287`
- prototype: `int(struct _ACL *, void *, unsigned int, struct _ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003164c`
- `0x1800319ec`

## callees

- `0x18002df48`
- `0x180030ad0`
- `0x18004fb94`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18004fc3f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18004fc3f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004fc0f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004fc0f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004fc67`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004fc67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004fbcb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004fbcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fc92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fc92`
- `ntdll!RtlLengthSid` at `0x18004fbb2`
- `ntdll!RtlLengthSid` at `0x18004fbb2`

## string_xrefs

- `0x18004fbe4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004fc81`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall AddSidToAcl(struct _ACL *a1, void *a2, __int64 a3, struct _ACL **a4)
{
  DWORD v7; // ebp
  struct _ACL *v8; // rax
  struct _ACL *v9; // rbx
  const char *v11; // r9
  __int64 v12; // rdx
  unsigned int LastError; // edi
  DWORD nAceListLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a4 = 0;
  v7 = RtlLengthSid(a2) + a1->AclSize + 8;
  v8 = (struct _ACL *)LocalAlloc(0, v7);
  v9 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)0x8007000ELL,
      nAceListLength);
    return 2147942414LL;
  }
  if ( !InitializeAcl(v8, v7, 2u) )
  {
    v12 = 1232;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  v11);
    LocalFree(v9);
    return LastError;
  }
  if ( !AddAce(v9, 2u, 0, &a1[1], a1->AclSize - 8) )
  {
    v12 = 1237;
    goto LABEL_9;
  }
  if ( !AddAccessAllowedAce(v9, 2u, 0x2001Bu, a2) )
  {
    v12 = 1242;
    goto LABEL_9;
  }
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x18004fb94  push    rbx
0x18004fb96  push    rbp
0x18004fb97  push    rsi
0x18004fb98  push    rdi
0x18004fb99  push    r14
0x18004fb9b  sub     rsp, 30h
0x18004fb9f  mov     rsi, rcx
0x18004fba2  mov     qword ptr [r9], 0
0x18004fba9  mov     rcx, rdx; Sid
0x18004fbac  mov     rdi, r9
0x18004fbaf  mov     r14, rdx
0x18004fbb2  call    cs:__imp_RtlLengthSid
0x18004fbb9  nop     dword ptr [rax+rax+00h]
0x18004fbbe  movzx   ebp, word ptr [rsi+2]
0x18004fbc2  xor     ecx, ecx; uFlags
0x18004fbc4  add     ebp, 8
0x18004fbc7  add     ebp, eax
0x18004fbc9  mov     edx, ebp; uBytes
0x18004fbcb  call    cs:__imp_LocalAlloc
0x18004fbd2  nop     dword ptr [rax+rax+00h]
0x18004fbd7  mov     rbx, rax
0x18004fbda  test    rax, rax
0x18004fbdd  jnz     short loc_18004FC04
0x18004fbdf  mov     rcx, [rsp+58h]; this
0x18004fbe4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fbeb  mov     ebx, 8007000Eh
0x18004fbf0  mov     edx, 4CEh; void *
0x18004fbf5  mov     r9d, ebx; char *
0x18004fbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fbfd  mov     eax, ebx
0x18004fbff  jmp     loc_18004FCA7
0x18004fc04  mov     r8d, 2; dwAclRevision
0x18004fc0a  mov     edx, ebp; nAclLength
0x18004fc0c  mov     rcx, rbx; pAcl
0x18004fc0f  call    cs:__imp_InitializeAcl
0x18004fc16  nop     dword ptr [rax+rax+00h]
0x18004fc1b  test    eax, eax
0x18004fc1d  jnz     short loc_18004FC26
0x18004fc1f  mov     edx, 4D0h
0x18004fc24  jmp     short loc_18004FC7C
0x18004fc26  movzx   eax, word ptr [rsi+2]
0x18004fc2a  lea     r9, [rsi+8]; pAceList
0x18004fc2e  xor     r8d, r8d; dwStartingAceIndex
0x18004fc31  sub     eax, 8
0x18004fc34  mov     rcx, rbx; pAcl
0x18004fc37  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18004fc3b  lea     edx, [r8+2]; dwAceRevision
0x18004fc3f  call    cs:__imp_AddAce
0x18004fc46  nop     dword ptr [rax+rax+00h]
0x18004fc4b  test    eax, eax
0x18004fc4d  jnz     short loc_18004FC56
0x18004fc4f  mov     edx, 4D5h
0x18004fc54  jmp     short loc_18004FC7C
0x18004fc56  mov     r9, r14; pSid
0x18004fc59  mov     edx, 2; dwAceRevision
0x18004fc5e  mov     r8d, 2001Bh; AccessMask
0x18004fc64  mov     rcx, rbx; pAcl
0x18004fc67  call    cs:__imp_AddAccessAllowedAce
0x18004fc6e  nop     dword ptr [rax+rax+00h]
0x18004fc73  test    eax, eax
0x18004fc75  jnz     short loc_18004FCA2
0x18004fc77  mov     edx, 4DAh; void *
0x18004fc7c  mov     rcx, [rsp+58h]; this
0x18004fc81  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fc88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004fc8d  mov     rcx, rbx; hMem
0x18004fc90  mov     edi, eax
0x18004fc92  call    cs:__imp_LocalFree
0x18004fc99  nop     dword ptr [rax+rax+00h]
0x18004fc9e  mov     eax, edi
0x18004fca0  jmp     short loc_18004FCA7
0x18004fca2  mov     [rdi], rbx
0x18004fca5  xor     eax, eax
0x18004fca7  add     rsp, 30h
0x18004fcab  pop     r14
0x18004fcad  pop     rdi
0x18004fcae  pop     rsi
0x18004fcaf  pop     rbp
0x18004fcb0  pop     rbx
0x18004fcb1  retn
```
