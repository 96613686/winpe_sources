# FGetLogonSID(void *,void * *)

- ea: `0x180122b28`
- end: `0x180122c70`
- name: `?FGetLogonSID@@YA_NPEAXPEAPEAX@Z`
- size: `328`
- prototype: `bool __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180122ea8`

## callees

- `0x180122b28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180122b64`
- `KERNEL32!GetLastError` at `0x180122b64`
- `KERNEL32!HeapFree` at `0x180122c39`
- `KERNEL32!HeapFree` at `0x180122c52`
- `KERNEL32!HeapFree` at `0x180122c39`
- `KERNEL32!HeapFree` at `0x180122c52`
- `KERNEL32!HeapAlloc` at `0x180122b85`
- `KERNEL32!HeapAlloc` at `0x180122bfc`
- `KERNEL32!HeapAlloc` at `0x180122b85`
- `KERNEL32!HeapAlloc` at `0x180122bfc`
- `KERNEL32!GetProcessHeap` at `0x180122b77`
- `KERNEL32!GetProcessHeap` at `0x180122bee`
- `KERNEL32!GetProcessHeap` at `0x180122c2b`
- `KERNEL32!GetProcessHeap` at `0x180122c44`
- `KERNEL32!GetProcessHeap` at `0x180122b77`
- `KERNEL32!GetProcessHeap` at `0x180122bee`
- `KERNEL32!GetProcessHeap` at `0x180122c2b`
- `KERNEL32!GetProcessHeap` at `0x180122c44`
- `ADVAPI32!GetTokenInformation` at `0x180122b5a`
- `ADVAPI32!GetTokenInformation` at `0x180122bb1`
- `ADVAPI32!GetTokenInformation` at `0x180122b5a`
- `ADVAPI32!GetTokenInformation` at `0x180122bb1`
- `ADVAPI32!GetLengthSid` at `0x180122be2`
- `ADVAPI32!GetLengthSid` at `0x180122be2`
- `ADVAPI32!CopySid` at `0x180122c1a`
- `ADVAPI32!CopySid` at `0x180122c1a`

## pseudocode

```c
char __fastcall FGetLogonSID(HANDLE TokenHandle, void **a2)
{
  char v3; // di
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v6; // rsi
  unsigned int i; // ecx
  __int64 v8; // rbp
  DWORD LengthSid; // ebx
  HANDLE v10; // rax
  void *v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  HANDLE v14; // rax
  DWORD dwBytes; // [rsp+48h] [rbp+10h] BYREF
  int dwBytes_4; // [rsp+4Ch] [rbp+14h]

  dwBytes_4 = HIDWORD(a2);
  v3 = 0;
  dwBytes = 0;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &dwBytes) || GetLastError() == 122 )
  {
    v4 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned int *)HeapAlloc(ProcessHeap, 0, v4);
    if ( v6 )
    {
      if ( GetTokenInformation(TokenHandle, TokenGroups, v6, dwBytes, &dwBytes) )
      {
        for ( i = 0; i < *v6; ++i )
        {
          v8 = 2LL * i;
          if ( (v6[4 * i + 4] & 0xC0000000) == 0xC0000000 )
          {
            LengthSid = GetLengthSid(*(PSID *)&v6[4 * i + 2]);
            dwBytes = LengthSid;
            v10 = GetProcessHeap();
            v11 = HeapAlloc(v10, 0, LengthSid);
            vpLogonIdSID = v11;
            if ( !v11 )
              goto LABEL_13;
            if ( !CopySid(dwBytes, v11, *(PSID *)&v6[2 * v8 + 2]) )
            {
              v12 = vpLogonIdSID;
              v13 = GetProcessHeap();
              HeapFree(v13, 0, v12);
              goto LABEL_13;
            }
            break;
          }
        }
        v3 = 1;
      }
LABEL_13:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180122b28  mov     rax, rsp
0x180122b2b  mov     [rax+8], rbx
0x180122b2f  mov     [rax+18h], rbp
0x180122b33  mov     [rax+20h], rsi
0x180122b37  mov     [rax+10h], rdx
0x180122b3b  push    rdi
0x180122b3c  sub     rsp, 30h
0x180122b40  mov     rbp, rcx
0x180122b43  xor     edi, edi
0x180122b45  mov     [rax+10h], edi
0x180122b48  lea     rax, [rax+10h]
0x180122b4c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180122b51  xor     r9d, r9d; TokenInformationLength
0x180122b54  xor     r8d, r8d; TokenInformation
0x180122b57  lea     edx, [rdi+2]; TokenInformationClass
0x180122b5a  call    cs:__imp_GetTokenInformation
0x180122b60  test    eax, eax
0x180122b62  jnz     short loc_180122B73
0x180122b64  call    cs:__imp_GetLastError
0x180122b6a  cmp     eax, 7Ah ; 'z'
0x180122b6d  jnz     loc_180122C58
0x180122b73  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x180122b77  call    cs:__imp_GetProcessHeap
0x180122b7d  mov     r8d, ebx; dwBytes
0x180122b80  xor     edx, edx; dwFlags
0x180122b82  mov     rcx, rax; hHeap
0x180122b85  call    cs:__imp_HeapAlloc
0x180122b8b  mov     rsi, rax
0x180122b8e  test    rax, rax
0x180122b91  jz      loc_180122C58
0x180122b97  lea     rax, [rsp+38h+dwBytes]
0x180122b9c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180122ba1  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x180122ba6  mov     r8, rsi; TokenInformation
0x180122ba9  mov     edx, 2; TokenInformationClass
0x180122bae  mov     rcx, rbp; TokenHandle
0x180122bb1  call    cs:__imp_GetTokenInformation
0x180122bb7  test    eax, eax
0x180122bb9  jz      loc_180122C44
0x180122bbf  mov     ecx, edi
0x180122bc1  mov     edx, 0C0000000h
0x180122bc6  cmp     ecx, [rsi]
0x180122bc8  jnb     short loc_180122C41
0x180122bca  mov     ebp, ecx
0x180122bcc  add     rbp, rbp
0x180122bcf  mov     eax, [rsi+rbp*8+10h]
0x180122bd3  and     eax, edx
0x180122bd5  cmp     eax, edx
0x180122bd7  jz      short loc_180122BDD
0x180122bd9  inc     ecx
0x180122bdb  jmp     short loc_180122BC6
0x180122bdd  mov     rcx, [rsi+rbp*8+8]; pSid
0x180122be2  call    cs:__imp_GetLengthSid
0x180122be8  mov     ebx, eax
0x180122bea  mov     dword ptr [rsp+38h+dwBytes], ebx
0x180122bee  call    cs:__imp_GetProcessHeap
0x180122bf4  mov     r8d, ebx; dwBytes
0x180122bf7  xor     edx, edx; dwFlags
0x180122bf9  mov     rcx, rax; hHeap
0x180122bfc  call    cs:__imp_HeapAlloc
0x180122c02  mov     cs:?vpLogonIdSID@@3PEAXEA, rax; void * vpLogonIdSID
0x180122c09  test    rax, rax
0x180122c0c  jz      short loc_180122C44
0x180122c0e  mov     r8, [rsi+rbp*8+8]; pSourceSid
0x180122c13  mov     rdx, rax; pDestinationSid
0x180122c16  mov     ecx, dword ptr [rsp+38h+dwBytes]; nDestinationSidLength
0x180122c1a  call    cs:__imp_CopySid
0x180122c20  test    eax, eax
0x180122c22  jnz     short loc_180122C41
0x180122c24  mov     rbx, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x180122c2b  call    cs:__imp_GetProcessHeap
0x180122c31  mov     r8, rbx; lpMem
0x180122c34  xor     edx, edx; dwFlags
0x180122c36  mov     rcx, rax; hHeap
0x180122c39  call    cs:__imp_HeapFree
0x180122c3f  jmp     short loc_180122C44
0x180122c41  mov     dil, 1
0x180122c44  call    cs:__imp_GetProcessHeap
0x180122c4a  mov     rcx, rax; hHeap
0x180122c4d  mov     r8, rsi; lpMem
0x180122c50  xor     edx, edx; dwFlags
0x180122c52  call    cs:__imp_HeapFree
0x180122c58  mov     al, dil
0x180122c5b  mov     rbx, [rsp+38h+arg_0]
0x180122c60  mov     rbp, [rsp+38h+arg_10]
0x180122c65  mov     rsi, [rsp+38h+arg_18]
0x180122c6a  add     rsp, 30h
0x180122c6e  pop     rdi
0x180122c6f  retn
```
