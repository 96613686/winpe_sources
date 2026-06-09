# IsFullTrustIntegrityToken

- ea: `0x18002f43c`
- end: `0x18002f606`
- name: `IsFullTrustIntegrityToken`
- size: `458`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e8e0`

## callees

- `0x18002f43c`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18002f508`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002f508`
- `ntdll!NtQueryInformationToken` at `0x18002f4ab`
- `ntdll!NtQueryInformationToken` at `0x18002f5da`
- `ntdll!NtQueryInformationToken` at `0x18002f4ab`
- `ntdll!NtQueryInformationToken` at `0x18002f5da`
- `ntdll!RtlSubAuthoritySid` at `0x18002f51e`
- `ntdll!RtlSubAuthoritySid` at `0x18002f51e`
- `ntdll!NtOpenProcessToken` at `0x18002f571`
- `ntdll!NtOpenProcessToken` at `0x18002f571`
- `ntdll!NtClose` at `0x18002f5f5`
- `ntdll!NtClose` at `0x18002f5f5`
- `ntdll!RtlFreeHeap` at `0x18002f553`
- `ntdll!RtlFreeHeap` at `0x18002f553`
- `ntdll!RtlAllocateHeap` at `0x18002f5a3`
- `ntdll!RtlAllocateHeap` at `0x18002f5a3`

## pseudocode

```c
__int64 __fastcall IsFullTrustIntegrityToken(HANDLE TokenHandle, _BYTE *a2)
{
  PSID *Heap; // rbx
  HANDLE v5; // rdi
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  PUCHAR v9; // rax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-31h] BYREF
  _BYTE TokenInformation[96]; // [rsp+40h] [rbp-29h] BYREF

  Heap = 0;
  TokenHandlea = TokenHandle;
  TokenInformationLength = 0;
  v5 = TokenHandle;
  memset_0(TokenInformation, 0, 0x58u);
  *a2 = 0;
  if ( !v5 )
  {
    v7 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandlea);
    if ( v7 < 0 )
      goto LABEL_4;
    v5 = TokenHandlea;
  }
  v6 = NtQueryInformationToken(v5, TokenIntegrityLevel, TokenInformation, 0x58u, &TokenInformationLength);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Heap = (PSID *)TokenInformation;
LABEL_9:
    v9 = RtlSubAuthorityCountSid(*Heap);
    if ( *RtlSubAuthoritySid(*Heap, (unsigned __int8)(*v9 - 1)) > 0x1000 )
      *a2 = 1;
    goto LABEL_4;
  }
  if ( v6 != -1073741789 )
    goto LABEL_4;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
  if ( !Heap )
  {
    v7 = -1073741670;
    goto LABEL_4;
  }
  v7 = NtQueryInformationToken(TokenHandlea, TokenIntegrityLevel, Heap, TokenInformationLength, &TokenInformationLength);
  if ( v7 >= 0 )
    goto LABEL_9;
LABEL_4:
  if ( TokenHandlea != TokenHandle )
    NtClose(TokenHandlea);
  if ( Heap && Heap != (PSID *)TokenInformation )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002f43c  mov     [rsp-8+arg_10], rbx
0x18002f441  mov     [rsp-8+arg_18], rsi
0x18002f446  push    rbp
0x18002f447  push    rdi
0x18002f448  push    r14
0x18002f44a  lea     rbp, [rsp-47h]
0x18002f44f  sub     rsp, 0B0h
0x18002f456  mov     rax, cs:__security_cookie
0x18002f45d  xor     rax, rsp
0x18002f460  mov     [rbp+57h+var_20], rax
0x18002f464  xor     ebx, ebx
0x18002f466  mov     [rbp+57h+TokenHandle], rcx
0x18002f46a  mov     r14, rdx
0x18002f46d  mov     [rbp+57h+TokenInformationLength], ebx
0x18002f470  mov     rsi, rcx
0x18002f473  mov     rdi, rcx
0x18002f476  xor     edx, edx; Val
0x18002f478  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18002f47c  lea     r8d, [rbx+58h]; Size
0x18002f480  call    memset_0
0x18002f485  mov     [r14], bl
0x18002f488  test    rdi, rdi
0x18002f48b  jz      loc_18002F564
0x18002f491  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002f497  lea     rax, [rbp+57h+TokenInformationLength]
0x18002f49b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002f49f  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002f4a4  mov     rcx, rdi; TokenHandle
0x18002f4a7  lea     edx, [r9-3Fh]; TokenInformationClass
0x18002f4ab  call    cs:__imp_NtQueryInformationToken
0x18002f4b2  nop     dword ptr [rax+rax+00h]
0x18002f4b7  mov     edi, eax
0x18002f4b9  test    eax, eax
0x18002f4bb  jns     short loc_18002F501
0x18002f4bd  cmp     eax, 0C0000023h
0x18002f4c2  jz      loc_18002F590
0x18002f4c8  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18002f4cc  cmp     rcx, rsi
0x18002f4cf  jnz     loc_18002F5F5
0x18002f4d5  test    rbx, rbx
0x18002f4d8  jnz     short loc_18002F538
0x18002f4da  mov     eax, edi
0x18002f4dc  mov     rcx, [rbp+57h+var_20]
0x18002f4e0  xor     rcx, rsp; StackCookie
0x18002f4e3  call    __security_check_cookie
0x18002f4e8  lea     r11, [rsp+0C0h+var_10]
0x18002f4f0  mov     rbx, [r11+30h]
0x18002f4f4  mov     rsi, [r11+38h]
0x18002f4f8  mov     rsp, r11
0x18002f4fb  pop     r14
0x18002f4fd  pop     rdi
0x18002f4fe  pop     rbp
0x18002f4ff  retn
0x18002f501  lea     rbx, [rbp+57h+TokenInformation]
0x18002f505  mov     rcx, [rbx]; Sid
0x18002f508  call    cs:__imp_RtlSubAuthorityCountSid
0x18002f50f  nop     dword ptr [rax+rax+00h]
0x18002f514  mov     cl, [rax]
0x18002f516  dec     cl
0x18002f518  movzx   edx, cl; SubAuthority
0x18002f51b  mov     rcx, [rbx]; Sid
0x18002f51e  call    cs:__imp_RtlSubAuthoritySid
0x18002f525  nop     dword ptr [rax+rax+00h]
0x18002f52a  cmp     dword ptr [rax], 1000h
0x18002f530  jbe     short loc_18002F4C8
0x18002f532  mov     byte ptr [r14], 1
0x18002f536  jmp     short loc_18002F4C8
0x18002f538  lea     rax, [rbp+57h+TokenInformation]
0x18002f53c  cmp     rbx, rax
0x18002f53f  jz      short loc_18002F4DA
0x18002f541  mov     rcx, gs:60h
0x18002f54a  mov     r8, rbx; P
0x18002f54d  xor     edx, edx; Flags
0x18002f54f  mov     rcx, [rcx+30h]; HeapHandle
0x18002f553  call    cs:__imp_RtlFreeHeap
0x18002f55a  nop     dword ptr [rax+rax+00h]
0x18002f55f  jmp     loc_18002F4DA
0x18002f564  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002f568  mov     edx, 8; DesiredAccess
0x18002f56d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002f571  call    cs:__imp_NtOpenProcessToken
0x18002f578  nop     dword ptr [rax+rax+00h]
0x18002f57d  mov     edi, eax
0x18002f57f  test    eax, eax
0x18002f581  js      loc_18002F4C8
0x18002f587  mov     rdi, [rbp+57h+TokenHandle]
0x18002f58b  jmp     loc_18002F491
0x18002f590  mov     rcx, gs:60h
0x18002f599  xor     edx, edx; Flags
0x18002f59b  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x18002f59f  mov     rcx, [rcx+30h]; HeapHandle
0x18002f5a3  call    cs:__imp_RtlAllocateHeap
0x18002f5aa  nop     dword ptr [rax+rax+00h]
0x18002f5af  mov     rbx, rax
0x18002f5b2  test    rax, rax
0x18002f5b5  jnz     short loc_18002F5C1
0x18002f5b7  mov     edi, 0C000009Ah
0x18002f5bc  jmp     loc_18002F4C8
0x18002f5c1  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002f5c5  lea     rax, [rbp+57h+TokenInformationLength]
0x18002f5c9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002f5cd  mov     r8, rbx; TokenInformation
0x18002f5d0  mov     edx, 19h; TokenInformationClass
0x18002f5d5  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002f5da  call    cs:__imp_NtQueryInformationToken
0x18002f5e1  nop     dword ptr [rax+rax+00h]
0x18002f5e6  mov     edi, eax
0x18002f5e8  test    eax, eax
0x18002f5ea  js      loc_18002F4C8
0x18002f5f0  jmp     loc_18002F505
0x18002f5f5  call    cs:__imp_NtClose
0x18002f5fc  nop     dword ptr [rax+rax+00h]
0x18002f601  jmp     loc_18002F4D5
```
