# KerbGetTokenPackage(void *,int *,_TOKEN_APPCONTAINER_INFORMATION * *)

- ea: `0x18006d3b4`
- end: `0x18006d476`
- name: `?KerbGetTokenPackage@@YAJPEAXPEAHPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *, struct _TOKEN_APPCONTAINER_INFORMATION **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180046100`

## callees

- `0x18006d3b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d41e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d41e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d461`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d461`
- `ntdll!NtQueryInformationToken` at `0x18006d3fa`
- `ntdll!NtQueryInformationToken` at `0x18006d44d`
- `ntdll!NtQueryInformationToken` at `0x18006d3fa`
- `ntdll!NtQueryInformationToken` at `0x18006d44d`

## pseudocode

```c
__int64 __fastcall KerbGetTokenPackage(HANDLE TokenHandle, int *a2, struct _TOKEN_APPCONTAINER_INFORMATION **a3)
{
  NTSTATUS v6; // edi
  struct _TOKEN_APPCONTAINER_INFORMATION *v7; // rbx
  ULONG TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  *a3 = 0;
  v10 = 0;
  TokenInformationLength = 4;
  v6 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v10, 4u, &TokenInformationLength);
  if ( v6 >= 0 && v10 )
  {
    *a2 = 1;
    TokenInformationLength = 76;
    v7 = (struct _TOKEN_APPCONTAINER_INFORMATION *)LocalAlloc(0, 0x4Cu);
    if ( v7 )
    {
      v6 = NtQueryInformationToken(
             TokenHandle,
             TokenAppContainerSid,
             v7,
             TokenInformationLength,
             &TokenInformationLength);
      if ( v6 < 0 )
        LocalFree(v7);
      else
        *a3 = v7;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006d3b4  mov     r11, rsp
0x18006d3b7  mov     [r11+8], rbx
0x18006d3bb  push    rbp
0x18006d3bc  push    rsi
0x18006d3bd  push    rdi
0x18006d3be  sub     rsp, 30h
0x18006d3c2  mov     r9d, 4; TokenInformationLength
0x18006d3c8  mov     dword ptr [rdx], 0
0x18006d3ce  mov     rsi, r8
0x18006d3d1  mov     qword ptr [r8], 0
0x18006d3d8  mov     rbx, rdx
0x18006d3db  mov     [rsp+48h+arg_10], 0
0x18006d3e3  lea     rax, [r11+10h]
0x18006d3e7  mov     [r11+10h], r9d
0x18006d3eb  lea     edx, [r9+19h]; TokenInformationClass
0x18006d3ef  mov     [r11-28h], rax
0x18006d3f3  lea     r8, [r11+18h]; TokenInformation
0x18006d3f7  mov     rbp, rcx
0x18006d3fa  call    cs:__imp_NtQueryInformationToken
0x18006d400  mov     edi, eax
0x18006d402  test    eax, eax
0x18006d404  js      short loc_18006D467
0x18006d406  cmp     [rsp+48h+arg_10], 0
0x18006d40b  jz      short loc_18006D467
0x18006d40d  mov     edx, 4Ch ; 'L'; uBytes
0x18006d412  mov     dword ptr [rbx], 1
0x18006d418  xor     ecx, ecx; uFlags
0x18006d41a  mov     [rsp+48h+TokenInformationLength], edx
0x18006d41e  call    cs:__imp_LocalAlloc
0x18006d424  mov     rbx, rax
0x18006d427  test    rax, rax
0x18006d42a  jnz     short loc_18006D433
0x18006d42c  mov     edi, 0C000009Ah
0x18006d431  jmp     short loc_18006D467
0x18006d433  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18006d438  lea     rax, [rsp+48h+TokenInformationLength]
0x18006d43d  mov     r8, rbx; TokenInformation
0x18006d440  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18006d445  mov     edx, 1Fh; TokenInformationClass
0x18006d44a  mov     rcx, rbp; TokenHandle
0x18006d44d  call    cs:__imp_NtQueryInformationToken
0x18006d453  mov     edi, eax
0x18006d455  test    eax, eax
0x18006d457  js      short loc_18006D45E
0x18006d459  mov     [rsi], rbx
0x18006d45c  jmp     short loc_18006D467
0x18006d45e  mov     rcx, rbx; hMem
0x18006d461  call    cs:__imp_LocalFree
0x18006d467  mov     rbx, [rsp+48h+arg_0]
0x18006d46c  mov     eax, edi
0x18006d46e  add     rsp, 30h
0x18006d472  pop     rdi
0x18006d473  pop     rsi
0x18006d474  pop     rbp
0x18006d475  retn
```
