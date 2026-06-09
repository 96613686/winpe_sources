# CuipGetClientLUID(void *,_LUID *)

- ea: `0x1400148f8`
- end: `0x140014a10`
- name: `?CuipGetClientLUID@@YAKPEAXPEAU_LUID@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _LUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000cfdc`

## callees

- `0x1400148f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400149fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400149fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014952`
- `ntdll!RtlNtStatusToDosError` at `0x14001493c`
- `ntdll!RtlNtStatusToDosError` at `0x14001493c`
- `ntdll!NtQueryInformationToken` at `0x140014925`
- `ntdll!NtQueryInformationToken` at `0x140014982`
- `ntdll!NtQueryInformationToken` at `0x140014925`
- `ntdll!NtQueryInformationToken` at `0x140014982`
- `ntdll!RtlSubAuthoritySid` at `0x1400149d6`
- `ntdll!RtlSubAuthoritySid` at `0x1400149e9`
- `ntdll!RtlSubAuthoritySid` at `0x1400149d6`
- `ntdll!RtlSubAuthoritySid` at `0x1400149e9`

## pseudocode

```c
__int64 __fastcall CuipGetClientLUID(HANDLE TokenHandle, struct _LUID *a2)
{
  unsigned int *v3; // rdi
  int v5; // eax
  ULONG v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  void *v9; // rsi
  ULONG TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  v5 = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  if ( v5 >= 0 )
  {
LABEL_13:
    v6 = 1338;
    goto LABEL_14;
  }
  if ( v5 == -1073741789 )
  {
    v3 = (unsigned int *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v3 )
    {
      v6 = 8;
      goto LABEL_14;
    }
    v5 = NtQueryInformationToken(TokenHandle, TokenGroups, v3, TokenInformationLength, &TokenInformationLength);
    if ( v5 >= 0 )
    {
      v7 = 0;
      TokenInformationLength = 0;
      v8 = 0;
      while ( v7 < *v3 )
      {
        if ( (v3[4 * v7 + 4] & 0xC0000000) == 0xC0000000 )
        {
          v9 = *(void **)&v3[4 * v8 + 2];
          if ( !v9 )
            goto LABEL_13;
          v6 = 0;
          a2->HighPart = *RtlSubAuthoritySid(*(PSID *)&v3[4 * v8 + 2], 1u);
          a2->LowPart = *RtlSubAuthoritySid(v9, 2u);
          goto LABEL_14;
        }
        TokenInformationLength = ++v7;
        v8 = v7;
      }
      goto LABEL_13;
    }
  }
  v6 = RtlNtStatusToDosError(v5);
LABEL_14:
  LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x1400148f8  push    rbx
0x1400148fa  push    rsi
0x1400148fb  push    rdi
0x1400148fc  push    r14
0x1400148fe  sub     rsp, 38h
0x140014902  mov     r14, rdx
0x140014905  mov     [rsp+58h+TokenInformationLength], 0
0x14001490d  lea     rax, [rsp+58h+TokenInformationLength]
0x140014912  xor     edi, edi
0x140014914  xor     r9d, r9d; TokenInformationLength
0x140014917  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14001491c  xor     r8d, r8d; TokenInformation
0x14001491f  mov     rbx, rcx
0x140014922  lea     edx, [rdi+2]; TokenInformationClass
0x140014925  call    cs:__imp_NtQueryInformationToken
0x14001492b  test    eax, eax
0x14001492d  jns     loc_1400149F6
0x140014933  cmp     eax, 0C0000023h
0x140014938  jz      short loc_140014949
0x14001493a  mov     ecx, eax; Status
0x14001493c  call    cs:__imp_RtlNtStatusToDosError
0x140014942  mov     ebx, eax
0x140014944  jmp     loc_1400149FB
0x140014949  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x14001494d  mov     ecx, 40h ; '@'; uFlags
0x140014952  call    cs:__imp_LocalAlloc
0x140014958  mov     rdi, rax
0x14001495b  test    rax, rax
0x14001495e  jnz     short loc_140014968
0x140014960  lea     ebx, [rax+8]
0x140014963  jmp     loc_1400149FB
0x140014968  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x14001496d  lea     rax, [rsp+58h+TokenInformationLength]
0x140014972  mov     r8, rdi; TokenInformation
0x140014975  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14001497a  mov     edx, 2; TokenInformationClass
0x14001497f  mov     rcx, rbx; TokenHandle
0x140014982  call    cs:__imp_NtQueryInformationToken
0x140014988  test    eax, eax
0x14001498a  js      short loc_14001493A
0x14001498c  xor     ecx, ecx
0x14001498e  mov     [rsp+58h+TokenInformationLength], 0
0x140014996  xor     eax, eax
0x140014998  mov     r8d, 0C0000000h
0x14001499e  cmp     ecx, [rdi]
0x1400149a0  jnb     short loc_1400149F6
0x1400149a2  mov     edx, eax
0x1400149a4  mov     eax, ecx
0x1400149a6  inc     rax
0x1400149a9  add     rax, rax
0x1400149ac  mov     eax, [rdi+rax*8]
0x1400149af  and     eax, r8d
0x1400149b2  cmp     eax, r8d
0x1400149b5  jz      short loc_1400149C1
0x1400149b7  inc     ecx
0x1400149b9  mov     [rsp+58h+TokenInformationLength], ecx
0x1400149bd  mov     eax, ecx
0x1400149bf  jmp     short loc_14001499E
0x1400149c1  add     rdx, rdx
0x1400149c4  mov     rsi, [rdi+rdx*8+8]
0x1400149c9  test    rsi, rsi
0x1400149cc  jz      short loc_1400149F6
0x1400149ce  xor     ebx, ebx
0x1400149d0  mov     rcx, rsi; Sid
0x1400149d3  lea     edx, [rbx+1]; SubAuthority
0x1400149d6  call    cs:__imp_RtlSubAuthoritySid
0x1400149dc  lea     edx, [rbx+2]; SubAuthority
0x1400149df  mov     rcx, rsi; Sid
0x1400149e2  mov     r8d, [rax]
0x1400149e5  mov     [r14+4], r8d
0x1400149e9  call    cs:__imp_RtlSubAuthoritySid
0x1400149ef  mov     ecx, [rax]
0x1400149f1  mov     [r14], ecx
0x1400149f4  jmp     short loc_1400149FB
0x1400149f6  mov     ebx, 53Ah
0x1400149fb  mov     rcx, rdi; hMem
0x1400149fe  call    cs:__imp_LocalFree
0x140014a04  mov     eax, ebx
0x140014a06  add     rsp, 38h
0x140014a0a  pop     r14
0x140014a0c  pop     rdi
0x140014a0d  pop     rsi
0x140014a0e  pop     rbx
0x140014a0f  retn
```
