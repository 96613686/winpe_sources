# AddSidToAcl(_ACL *,void *,ulong,_ACL * *)

- ea: `0x18004cb54`
- end: `0x18004cc4e`
- name: `?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct _ACL *, void *, __int64, struct _ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d360`
- `0x18002d7c0`

## callees

- `0x18002d2d8`
- `0x18002db38`
- `0x18004cb54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18004cbed`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18004cbed`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004cbc3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004cbc3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004cc0f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004cc0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cb85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cb85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc34`
- `ntdll!RtlLengthSid` at `0x18004cb72`
- `ntdll!RtlLengthSid` at `0x18004cb72`

## string_xrefs

- `0x18004cb98`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004cc23`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
0x18004cb54  push    rbx
0x18004cb56  push    rbp
0x18004cb57  push    rsi
0x18004cb58  push    rdi
0x18004cb59  push    r14
0x18004cb5b  sub     rsp, 30h
0x18004cb5f  mov     rsi, rcx
0x18004cb62  mov     qword ptr [r9], 0
0x18004cb69  mov     rcx, rdx; Sid
0x18004cb6c  mov     rdi, r9
0x18004cb6f  mov     r14, rdx
0x18004cb72  call    cs:__imp_RtlLengthSid
0x18004cb78  movzx   ebp, word ptr [rsi+2]
0x18004cb7c  xor     ecx, ecx; uFlags
0x18004cb7e  add     ebp, 8
0x18004cb81  add     ebp, eax
0x18004cb83  mov     edx, ebp; uBytes
0x18004cb85  call    cs:__imp_LocalAlloc
0x18004cb8b  mov     rbx, rax
0x18004cb8e  test    rax, rax
0x18004cb91  jnz     short loc_18004CBB8
0x18004cb93  mov     rcx, [rsp+58h]; this
0x18004cb98  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cb9f  mov     ebx, 8007000Eh
0x18004cba4  mov     edx, 4CEh; void *
0x18004cba9  mov     r9d, ebx; char *
0x18004cbac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cbb1  mov     eax, ebx
0x18004cbb3  jmp     loc_18004CC43
0x18004cbb8  mov     r8d, 2; dwAclRevision
0x18004cbbe  mov     edx, ebp; nAclLength
0x18004cbc0  mov     rcx, rbx; pAcl
0x18004cbc3  call    cs:__imp_InitializeAcl
0x18004cbc9  test    eax, eax
0x18004cbcb  jnz     short loc_18004CBD4
0x18004cbcd  mov     edx, 4D0h
0x18004cbd2  jmp     short loc_18004CC1E
0x18004cbd4  movzx   eax, word ptr [rsi+2]
0x18004cbd8  lea     r9, [rsi+8]; pAceList
0x18004cbdc  xor     r8d, r8d; dwStartingAceIndex
0x18004cbdf  sub     eax, 8
0x18004cbe2  mov     rcx, rbx; pAcl
0x18004cbe5  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18004cbe9  lea     edx, [r8+2]; dwAceRevision
0x18004cbed  call    cs:__imp_AddAce
0x18004cbf3  test    eax, eax
0x18004cbf5  jnz     short loc_18004CBFE
0x18004cbf7  mov     edx, 4D5h
0x18004cbfc  jmp     short loc_18004CC1E
0x18004cbfe  mov     r9, r14; pSid
0x18004cc01  mov     edx, 2; dwAceRevision
0x18004cc06  mov     r8d, 2001Bh; AccessMask
0x18004cc0c  mov     rcx, rbx; pAcl
0x18004cc0f  call    cs:__imp_AddAccessAllowedAce
0x18004cc15  test    eax, eax
0x18004cc17  jnz     short loc_18004CC3E
0x18004cc19  mov     edx, 4DAh; void *
0x18004cc1e  mov     rcx, [rsp+58h]; this
0x18004cc23  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cc2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004cc2f  mov     rcx, rbx; hMem
0x18004cc32  mov     edi, eax
0x18004cc34  call    cs:__imp_LocalFree
0x18004cc3a  mov     eax, edi
0x18004cc3c  jmp     short loc_18004CC43
0x18004cc3e  mov     [rdi], rbx
0x18004cc41  xor     eax, eax
0x18004cc43  add     rsp, 30h
0x18004cc47  pop     r14
0x18004cc49  pop     rdi
0x18004cc4a  pop     rsi
0x18004cc4b  pop     rbp
0x18004cc4c  pop     rbx
0x18004cc4d  retn
```
