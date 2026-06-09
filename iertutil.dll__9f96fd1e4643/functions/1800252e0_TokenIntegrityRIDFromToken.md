# _TokenIntegrityRIDFromToken

- ea: `0x1800252e0`
- end: `0x180025360`
- name: `_TokenIntegrityRIDFromToken`
- size: `128`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024d04`
- `0x180025250`
- `0x180081170`

## callees

- `0x1800252e0`
- `0x180025368`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002533a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002533a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025348`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025348`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180025322`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180025322`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180025330`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180025330`

## pseudocode

```c
__int64 __fastcall TokenIntegrityRIDFromToken(HANDLE TokenHandle, DWORD *a2)
{
  HANDLE ProcessHeap; // rax
  int TokenInformation_Heap; // edi
  PUCHAR SidSubAuthorityCount; // rax
  HANDLE v7; // rax

  ProcessHeap = GetProcessHeap();
  TokenInformation_Heap = GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(ProcessHeap, TokenHandle);
  if ( TokenInformation_Heap >= 0 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(MEMORY[0]);
    *a2 = *GetSidSubAuthority(MEMORY[0], (unsigned int)*SidSubAuthorityCount - 1);
    v7 = GetProcessHeap();
    HeapFree(v7, 0, 0);
  }
  return (unsigned int)TokenInformation_Heap;
}

```

## disassembly

```asm
0x1800252e0  mov     [rsp+arg_0], rbx
0x1800252e5  mov     [rsp+arg_8], rsi
0x1800252ea  push    rdi
0x1800252eb  sub     rsp, 20h
0x1800252ef  mov     rsi, rdx
0x1800252f2  mov     [rsp+28h+lpMem], 0
0x1800252fb  mov     rbx, rcx
0x1800252fe  call    cs:__imp_GetProcessHeap
0x180025304  lea     r9, [rsp+28h+lpMem]
0x180025309  mov     rdx, rbx; TokenHandle
0x18002530c  mov     rcx, rax; hHeap
0x18002530f  call    ??$GetTokenInformation_HeapFree@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)
0x180025314  mov     edi, eax
0x180025316  test    eax, eax
0x180025318  js      short loc_18002534E
0x18002531a  mov     rbx, [rsp+28h+lpMem]
0x18002531f  mov     rcx, [rbx]; pSid
0x180025322  call    cs:__imp_GetSidSubAuthorityCount
0x180025328  mov     rcx, [rbx]; pSid
0x18002532b  movzx   edx, byte ptr [rax]
0x18002532e  dec     edx; nSubAuthority
0x180025330  call    cs:__imp_GetSidSubAuthority
0x180025336  mov     ecx, [rax]
0x180025338  mov     [rsi], ecx
0x18002533a  call    cs:__imp_GetProcessHeap
0x180025340  mov     r8, rbx; lpMem
0x180025343  xor     edx, edx; dwFlags
0x180025345  mov     rcx, rax; hHeap
0x180025348  call    cs:__imp_HeapFree
0x18002534e  mov     rbx, [rsp+28h+arg_0]
0x180025353  mov     eax, edi
0x180025355  mov     rsi, [rsp+28h+arg_8]
0x18002535a  add     rsp, 20h
0x18002535e  pop     rdi
0x18002535f  retn
```
