# SetAclPerms(_ACL * *)

- ea: `0x18003ba34`
- end: `0x18003bb38`
- name: `?SetAclPerms@@YAKPEAPEAU_ACL@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b850`

## callees

- `0x18003ba34`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003baa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bafe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003baa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bafe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bab2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bab2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bb0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baf6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ba7c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ba7c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ba98`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ba98`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003bad2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003bad2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003baec`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003baec`

## pseudocode

```c
__int64 __fastcall SetAclPerms(struct _ACL **a1)
{
  DWORD LastError; // ebx
  DWORD v3; // esi
  HANDLE ProcessHeap; // rax
  struct _ACL *v5; // rax
  struct _ACL *v6; // rdi
  HANDLE v7; // rax
  DWORD cbSid[4]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-88h] BYREF

  cbSid[0] = 68;
  memset_0(pSid, 0, 0x44u);
  if ( CreateWellKnownSid(WinWorldSid, 0, pSid, cbSid) )
  {
    v3 = GetLengthSid(pSid) + 20;
    ProcessHeap = GetProcessHeap();
    v5 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v3);
    v6 = v5;
    if ( v5 )
    {
      if ( InitializeAcl(v5, v3, 2u) && AddAccessAllowedAce(v6, 2u, 0x10000000u, pSid) )
      {
        LastError = 0;
        *a1 = v6;
      }
      else
      {
        LastError = GetLastError();
        v7 = GetProcessHeap();
        HeapFree(v7, 0, v6);
      }
    }
    else
    {
      return 14;
    }
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18003ba34  push    rbx
0x18003ba36  push    rsi
0x18003ba37  push    rdi
0x18003ba38  push    r14
0x18003ba3a  sub     rsp, 98h
0x18003ba41  mov     rax, cs:__security_cookie
0x18003ba48  xor     rax, rsp
0x18003ba4b  mov     [rsp+0B8h+var_38], rax
0x18003ba53  mov     r14, rcx
0x18003ba56  mov     r8d, 44h ; 'D'; Size
0x18003ba5c  lea     rcx, [rsp+0B8h+pSid]; void *
0x18003ba61  mov     [rsp+0B8h+cbSid], r8d
0x18003ba66  xor     edx, edx; Val
0x18003ba68  call    memset_0
0x18003ba6d  xor     edx, edx; DomainSid
0x18003ba6f  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x18003ba74  lea     r8, [rsp+0B8h+pSid]; pSid
0x18003ba79  lea     ecx, [rdx+1]; WellKnownSidType
0x18003ba7c  call    cs:__imp_CreateWellKnownSid
0x18003ba82  test    eax, eax
0x18003ba84  jnz     short loc_18003BA93
0x18003ba86  call    cs:__imp_GetLastError
0x18003ba8c  mov     ebx, eax
0x18003ba8e  jmp     loc_18003BB19
0x18003ba93  lea     rcx, [rsp+0B8h+pSid]; pSid
0x18003ba98  call    cs:__imp_GetLengthSid
0x18003ba9e  lea     esi, [rax+14h]
0x18003baa1  call    cs:__imp_GetProcessHeap
0x18003baa7  mov     r8d, esi; dwBytes
0x18003baaa  mov     edx, 8; dwFlags
0x18003baaf  mov     rcx, rax; hHeap
0x18003bab2  call    cs:__imp_HeapAlloc
0x18003bab8  mov     rdi, rax
0x18003babb  test    rax, rax
0x18003babe  jnz     short loc_18003BAC5
0x18003bac0  lea     ebx, [rax+0Eh]
0x18003bac3  jmp     short loc_18003BB19
0x18003bac5  mov     ebx, 2
0x18003baca  mov     edx, esi; nAclLength
0x18003bacc  mov     r8d, ebx; dwAclRevision
0x18003bacf  mov     rcx, rdi; pAcl
0x18003bad2  call    cs:__imp_InitializeAcl
0x18003bad8  test    eax, eax
0x18003bada  jz      short loc_18003BAF6
0x18003badc  lea     r9, [rsp+0B8h+pSid]; pSid
0x18003bae1  mov     r8d, 10000000h; AccessMask
0x18003bae7  mov     edx, ebx; dwAceRevision
0x18003bae9  mov     rcx, rdi; pAcl
0x18003baec  call    cs:__imp_AddAccessAllowedAce
0x18003baf2  test    eax, eax
0x18003baf4  jnz     short loc_18003BB14
0x18003baf6  call    cs:__imp_GetLastError
0x18003bafc  mov     ebx, eax
0x18003bafe  call    cs:__imp_GetProcessHeap
0x18003bb04  mov     r8, rdi; lpMem
0x18003bb07  xor     edx, edx; dwFlags
0x18003bb09  mov     rcx, rax; hHeap
0x18003bb0c  call    cs:__imp_HeapFree
0x18003bb12  jmp     short loc_18003BB19
0x18003bb14  xor     ebx, ebx
0x18003bb16  mov     [r14], rdi
0x18003bb19  mov     eax, ebx
0x18003bb1b  mov     rcx, [rsp+0B8h+var_38]
0x18003bb23  xor     rcx, rsp; StackCookie
0x18003bb26  call    __security_check_cookie
0x18003bb2b  add     rsp, 98h
0x18003bb32  pop     r14
0x18003bb34  pop     rdi
0x18003bb35  pop     rsi
0x18003bb36  pop     rbx
0x18003bb37  retn
```
