# SetAclPerms(_ACL * *)

- ea: `0x18003ec78`
- end: `0x18003edb9`
- name: `?SetAclPerms@@YAKPEAPEAU_ACL@@@Z`
- size: `321`
- prototype: `unsigned int __fastcall(struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ea64`

## callees

- `0x18003ec78`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ecf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ed72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ecf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ed72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ed0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ed0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ed86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ed86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed64`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ecc0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ecc0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ece8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ece8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003ed34`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003ed34`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003ed54`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18003ed54`

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
0x18003ec78  push    rbx
0x18003ec7a  push    rsi
0x18003ec7b  push    rdi
0x18003ec7c  push    r14
0x18003ec7e  sub     rsp, 98h
0x18003ec85  mov     rax, cs:__security_cookie
0x18003ec8c  xor     rax, rsp
0x18003ec8f  mov     [rsp+0B8h+var_38], rax
0x18003ec97  mov     r14, rcx
0x18003ec9a  mov     r8d, 44h ; 'D'; Size
0x18003eca0  lea     rcx, [rsp+0B8h+pSid]; void *
0x18003eca5  mov     [rsp+0B8h+cbSid], r8d
0x18003ecaa  xor     edx, edx; Val
0x18003ecac  call    memset_0
0x18003ecb1  xor     edx, edx; DomainSid
0x18003ecb3  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x18003ecb8  lea     r8, [rsp+0B8h+pSid]; pSid
0x18003ecbd  lea     ecx, [rdx+1]; WellKnownSidType
0x18003ecc0  call    cs:__imp_CreateWellKnownSid
0x18003ecc7  nop     dword ptr [rax+rax+00h]
0x18003eccc  test    eax, eax
0x18003ecce  jnz     short loc_18003ECE3
0x18003ecd0  call    cs:__imp_GetLastError
0x18003ecd7  nop     dword ptr [rax+rax+00h]
0x18003ecdc  mov     ebx, eax
0x18003ecde  jmp     loc_18003ED99
0x18003ece3  lea     rcx, [rsp+0B8h+pSid]; pSid
0x18003ece8  call    cs:__imp_GetLengthSid
0x18003ecef  nop     dword ptr [rax+rax+00h]
0x18003ecf4  lea     esi, [rax+14h]
0x18003ecf7  call    cs:__imp_GetProcessHeap
0x18003ecfe  nop     dword ptr [rax+rax+00h]
0x18003ed03  mov     r8d, esi; dwBytes
0x18003ed06  mov     edx, 8; dwFlags
0x18003ed0b  mov     rcx, rax; hHeap
0x18003ed0e  call    cs:__imp_HeapAlloc
0x18003ed15  nop     dword ptr [rax+rax+00h]
0x18003ed1a  mov     rdi, rax
0x18003ed1d  test    rax, rax
0x18003ed20  jnz     short loc_18003ED27
0x18003ed22  lea     ebx, [rax+0Eh]
0x18003ed25  jmp     short loc_18003ED99
0x18003ed27  mov     ebx, 2
0x18003ed2c  mov     edx, esi; nAclLength
0x18003ed2e  mov     r8d, ebx; dwAclRevision
0x18003ed31  mov     rcx, rdi; pAcl
0x18003ed34  call    cs:__imp_InitializeAcl
0x18003ed3b  nop     dword ptr [rax+rax+00h]
0x18003ed40  test    eax, eax
0x18003ed42  jz      short loc_18003ED64
0x18003ed44  lea     r9, [rsp+0B8h+pSid]; pSid
0x18003ed49  mov     r8d, 10000000h; AccessMask
0x18003ed4f  mov     edx, ebx; dwAceRevision
0x18003ed51  mov     rcx, rdi; pAcl
0x18003ed54  call    cs:__imp_AddAccessAllowedAce
0x18003ed5b  nop     dword ptr [rax+rax+00h]
0x18003ed60  test    eax, eax
0x18003ed62  jnz     short loc_18003ED94
0x18003ed64  call    cs:__imp_GetLastError
0x18003ed6b  nop     dword ptr [rax+rax+00h]
0x18003ed70  mov     ebx, eax
0x18003ed72  call    cs:__imp_GetProcessHeap
0x18003ed79  nop     dword ptr [rax+rax+00h]
0x18003ed7e  mov     r8, rdi; lpMem
0x18003ed81  xor     edx, edx; dwFlags
0x18003ed83  mov     rcx, rax; hHeap
0x18003ed86  call    cs:__imp_HeapFree
0x18003ed8d  nop     dword ptr [rax+rax+00h]
0x18003ed92  jmp     short loc_18003ED99
0x18003ed94  xor     ebx, ebx
0x18003ed96  mov     [r14], rdi
0x18003ed99  mov     eax, ebx
0x18003ed9b  mov     rcx, [rsp+0B8h+var_38]
0x18003eda3  xor     rcx, rsp; StackCookie
0x18003eda6  call    __security_check_cookie
0x18003edab  add     rsp, 98h
0x18003edb2  pop     r14
0x18003edb4  pop     rdi
0x18003edb5  pop     rsi
0x18003edb6  pop     rbx
0x18003edb7  retn
```
