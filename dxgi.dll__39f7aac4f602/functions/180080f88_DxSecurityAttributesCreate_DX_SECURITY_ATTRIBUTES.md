# DxSecurityAttributesCreate(_DX_SECURITY_ATTRIBUTES *)

- ea: `0x180080f88`
- end: `0x1800810f1`
- name: `?DxSecurityAttributesCreate@@YAXPEAU_DX_SECURITY_ATTRIBUTES@@@Z`
- size: `361`
- prototype: `void __fastcall(struct _DX_SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081180`

## callees

- `0x180075fa0`
- `0x180080f88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080fd7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008102e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081080`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080fd7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008102e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081020`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081020`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081071`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180081095`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180081095`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180081067`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180081067`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180080fff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180080fff`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180080ff4`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180080ff4`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180080fc1`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180080fc1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008104e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008104e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180081017`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180081017`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800810ad`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800810ad`

## pseudocode

```c
void __fastcall DxSecurityAttributesCreate(struct _DX_SECURITY_ATTRIBUTES *a1)
{
  DWORD SidLengthRequired; // ebx
  HANDLE ProcessHeap; // rax
  void *v4; // rax
  PDWORD SidSubAuthority; // rax
  DWORD v6; // esi
  HANDLE v7; // rax
  struct _ACL *v8; // rax
  HANDLE v9; // rax
  void *v10; // rax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *((_DWORD *)a1 + 12) = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  SidLengthRequired = GetSidLengthRequired(1u);
  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 0, SidLengthRequired);
  *(_QWORD *)a1 = v4;
  if ( v4 )
  {
    InitializeSid(v4, &pIdentifierAuthority, 1u);
    SidSubAuthority = GetSidSubAuthority(*(PSID *)a1, 0);
    if ( SidSubAuthority )
    {
      *SidSubAuthority = 0;
      v6 = GetLengthSid(*(PSID *)a1) + 16;
      v7 = GetProcessHeap();
      v8 = (struct _ACL *)HeapAlloc(v7, 0, v6);
      *((_QWORD *)a1 + 1) = v8;
      if ( v8 )
      {
        if ( InitializeAcl(v8, v6, 2u) )
        {
          if ( AddAccessAllowedAce(*((PACL *)a1 + 1), 2u, 0x120001u, *(PSID *)a1) )
          {
            v9 = GetProcessHeap();
            v10 = HeapAlloc(v9, 0, 0x28u);
            *((_QWORD *)a1 + 2) = v10;
            if ( v10 )
            {
              if ( InitializeSecurityDescriptor(v10, 1u) )
              {
                if ( SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)a1 + 2), 1, *((PACL *)a1 + 1), 0) )
                {
                  *((_QWORD *)a1 + 4) = *((_QWORD *)a1 + 2);
                  *((_DWORD *)a1 + 6) = 24;
                  *((_DWORD *)a1 + 10) = 1;
                  *((_DWORD *)a1 + 12) = 1;
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180080f88  mov     [rsp+arg_8], rbx
0x180080f8d  mov     [rsp+arg_10], rsi
0x180080f92  push    rdi
0x180080f93  sub     rsp, 30h
0x180080f97  mov     rax, cs:__security_cookie
0x180080f9e  xor     rax, rsp
0x180080fa1  mov     [rsp+38h+var_10], rax
0x180080fa6  mov     rdi, rcx
0x180080fa9  mov     dword ptr [rcx+30h], 0
0x180080fb0  mov     cl, 1; nSubAuthorityCount
0x180080fb2  mov     dword ptr [rsp+38h+pIdentifierAuthority.Value], 0
0x180080fba  mov     word ptr [rsp+38h+pIdentifierAuthority.Value+4], 100h
0x180080fc1  call    cs:__imp_GetSidLengthRequired
0x180080fc7  mov     ebx, eax
0x180080fc9  call    cs:__imp_GetProcessHeap
0x180080fcf  mov     r8d, ebx; dwBytes
0x180080fd2  xor     edx, edx; dwFlags
0x180080fd4  mov     rcx, rax; hHeap
0x180080fd7  call    cs:__imp_HeapAlloc
0x180080fdd  mov     [rdi], rax
0x180080fe0  test    rax, rax
0x180080fe3  jz      loc_1800810D4
0x180080fe9  mov     r8b, 1; nSubAuthorityCount
0x180080fec  lea     rdx, [rsp+38h+pIdentifierAuthority]; pIdentifierAuthority
0x180080ff1  mov     rcx, rax; Sid
0x180080ff4  call    cs:__imp_InitializeSid
0x180080ffa  mov     rcx, [rdi]; pSid
0x180080ffd  xor     edx, edx; nSubAuthority
0x180080fff  call    cs:__imp_GetSidSubAuthority
0x180081005  test    rax, rax
0x180081008  jz      loc_1800810D4
0x18008100e  mov     dword ptr [rax], 0
0x180081014  mov     rcx, [rdi]; pSid
0x180081017  call    cs:__imp_GetLengthSid
0x18008101d  lea     esi, [rax+10h]
0x180081020  call    cs:__imp_GetProcessHeap
0x180081026  mov     r8d, esi; dwBytes
0x180081029  xor     edx, edx; dwFlags
0x18008102b  mov     rcx, rax; hHeap
0x18008102e  call    cs:__imp_HeapAlloc
0x180081034  mov     [rdi+8], rax
0x180081038  test    rax, rax
0x18008103b  jz      loc_1800810D4
0x180081041  mov     ebx, 2
0x180081046  mov     edx, esi; nAclLength
0x180081048  mov     r8d, ebx; dwAclRevision
0x18008104b  mov     rcx, rax; pAcl
0x18008104e  call    cs:__imp_InitializeAcl
0x180081054  test    eax, eax
0x180081056  jz      short loc_1800810D4
0x180081058  mov     r9, [rdi]; pSid
0x18008105b  mov     r8d, 120001h; AccessMask
0x180081061  mov     rcx, [rdi+8]; pAcl
0x180081065  mov     edx, ebx; dwAceRevision
0x180081067  call    cs:__imp_AddAccessAllowedAce
0x18008106d  test    eax, eax
0x18008106f  jz      short loc_1800810D4
0x180081071  call    cs:__imp_GetProcessHeap
0x180081077  xor     edx, edx; dwFlags
0x180081079  lea     r8d, [rbx+26h]; dwBytes
0x18008107d  mov     rcx, rax; hHeap
0x180081080  call    cs:__imp_HeapAlloc
0x180081086  mov     [rdi+10h], rax
0x18008108a  test    rax, rax
0x18008108d  jz      short loc_1800810D4
0x18008108f  lea     edx, [rbx-1]; dwRevision
0x180081092  mov     rcx, rax; pSecurityDescriptor
0x180081095  call    cs:__imp_InitializeSecurityDescriptor
0x18008109b  test    eax, eax
0x18008109d  jz      short loc_1800810D4
0x18008109f  mov     r8, [rdi+8]; pDacl
0x1800810a3  lea     edx, [rbx-1]; bDaclPresent
0x1800810a6  mov     rcx, [rdi+10h]; pSecurityDescriptor
0x1800810aa  xor     r9d, r9d; bDaclDefaulted
0x1800810ad  call    cs:__imp_SetSecurityDescriptorDacl
0x1800810b3  test    eax, eax
0x1800810b5  jz      short loc_1800810D4
0x1800810b7  mov     rax, [rdi+10h]
0x1800810bb  mov     [rdi+20h], rax
0x1800810bf  mov     dword ptr [rdi+18h], 18h
0x1800810c6  mov     dword ptr [rdi+28h], 1
0x1800810cd  mov     dword ptr [rdi+30h], 1
0x1800810d4  mov     rcx, [rsp+38h+var_10]
0x1800810d9  xor     rcx, rsp; StackCookie
0x1800810dc  call    __security_check_cookie
0x1800810e1  mov     rbx, [rsp+38h+arg_8]
0x1800810e6  mov     rsi, [rsp+38h+arg_10]
0x1800810eb  add     rsp, 30h
0x1800810ef  pop     rdi
0x1800810f0  retn
```
