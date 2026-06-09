# GetCurrentOwnerSID(void)

- ea: `0x1800225c4`
- end: `0x18002276f`
- name: `?GetCurrentOwnerSID@@YAPEAXXZ`
- size: `427`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180004060`

## callees

- `0x1800225c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180022727`
- `KERNEL32!LocalFree` at `0x180022738`
- `KERNEL32!LocalFree` at `0x180022727`
- `KERNEL32!LocalFree` at `0x180022738`
- `KERNEL32!LocalAlloc` at `0x180022696`
- `KERNEL32!LocalAlloc` at `0x1800226e9`
- `KERNEL32!LocalAlloc` at `0x180022696`
- `KERNEL32!LocalAlloc` at `0x1800226e9`
- `KERNEL32!GetCurrentThread` at `0x1800225e3`
- `KERNEL32!GetCurrentThread` at `0x1800225e3`
- `KERNEL32!GetCurrentProcess` at `0x180022626`
- `KERNEL32!GetCurrentProcess` at `0x180022626`
- `KERNEL32!CloseHandle` at `0x18002274f`
- `KERNEL32!CloseHandle` at `0x18002274f`
- `KERNEL32!GetLastError` at `0x18002260f`
- `KERNEL32!GetLastError` at `0x18002267b`
- `KERNEL32!GetLastError` at `0x18002260f`
- `KERNEL32!GetLastError` at `0x18002267b`
- `ADVAPI32!CopySid` at `0x180022714`
- `ADVAPI32!CopySid` at `0x180022714`
- `ADVAPI32!OpenProcessToken` at `0x18002263c`
- `ADVAPI32!OpenProcessToken` at `0x18002263c`
- `ADVAPI32!GetLengthSid` at `0x1800226d9`
- `ADVAPI32!GetLengthSid` at `0x180022700`
- `ADVAPI32!GetLengthSid` at `0x1800226d9`
- `ADVAPI32!GetLengthSid` at `0x180022700`
- `ADVAPI32!OpenThreadToken` at `0x1800225ff`
- `ADVAPI32!OpenThreadToken` at `0x1800225ff`
- `ADVAPI32!GetTokenInformation` at `0x18002266b`
- `ADVAPI32!GetTokenInformation` at `0x1800226c3`
- `ADVAPI32!GetTokenInformation` at `0x18002266b`
- `ADVAPI32!GetTokenInformation` at `0x1800226c3`

## pseudocode

```c
HLOCAL GetCurrentOwnerSID(void)
{
  HLOCAL v0; // rbx
  PSID *v1; // rdi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  PSID v4; // rsi
  DWORD LengthSid; // eax
  DWORD v6; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  TokenHandle = (void *)-1LL;
  TokenInformationLength = 0;
  v1 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
    && (GetLastError() != 1008
     || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 8u, &TokenHandle)))
    || !GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &TokenInformationLength) && GetLastError() != 122
    || (v1 = (PSID *)LocalAlloc(0, TokenInformationLength)) == 0
    || !GetTokenInformation(TokenHandle, TokenOwner, v1, TokenInformationLength, &TokenInformationLength)
    || (v4 = *v1, LengthSid = GetLengthSid(*v1), (v0 = LocalAlloc(0, LengthSid)) == 0)
    || (v6 = GetLengthSid(v4), !CopySid(v6, v0, v4)) )
  {
    LocalFree(v0);
    v0 = 0;
  }
  LocalFree(v1);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800225c4  mov     rax, rsp
0x1800225c7  mov     [rax+18h], rbx
0x1800225cb  mov     [rax+20h], rsi
0x1800225cf  push    rdi
0x1800225d0  sub     rsp, 30h
0x1800225d4  xor     ebx, ebx
0x1800225d6  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800225de  mov     [rax+8], ebx
0x1800225e1  xor     edi, edi
0x1800225e3  call    cs:__imp_GetCurrentThread
0x1800225ea  nop     dword ptr [rax+rax+00h]
0x1800225ef  lea     esi, [rbx+8]
0x1800225f2  xor     r8d, r8d; OpenAsSelf
0x1800225f5  mov     rcx, rax; ThreadHandle
0x1800225f8  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800225fd  mov     edx, esi; DesiredAccess
0x1800225ff  call    cs:__imp_OpenThreadToken
0x180022606  nop     dword ptr [rax+rax+00h]
0x18002260b  test    eax, eax
0x18002260d  jnz     short loc_180022650
0x18002260f  call    cs:__imp_GetLastError
0x180022616  nop     dword ptr [rax+rax+00h]
0x18002261b  cmp     eax, 3F0h
0x180022620  jnz     loc_180022724
0x180022626  call    cs:__imp_GetCurrentProcess
0x18002262d  nop     dword ptr [rax+rax+00h]
0x180022632  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180022637  mov     edx, esi; DesiredAccess
0x180022639  mov     rcx, rax; ProcessHandle
0x18002263c  call    cs:__imp_OpenProcessToken
0x180022643  nop     dword ptr [rax+rax+00h]
0x180022648  test    eax, eax
0x18002264a  jz      loc_180022724
0x180022650  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180022655  lea     rax, [rsp+38h+TokenInformationLength]
0x18002265a  xor     r9d, r9d; TokenInformationLength
0x18002265d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180022662  xor     r8d, r8d; TokenInformation
0x180022665  lea     esi, [r9+4]
0x180022669  mov     edx, esi; TokenInformationClass
0x18002266b  call    cs:__imp_GetTokenInformation
0x180022672  nop     dword ptr [rax+rax+00h]
0x180022677  test    eax, eax
0x180022679  jnz     short loc_180022690
0x18002267b  call    cs:__imp_GetLastError
0x180022682  nop     dword ptr [rax+rax+00h]
0x180022687  cmp     eax, 7Ah ; 'z'
0x18002268a  jnz     loc_180022724
0x180022690  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180022694  xor     ecx, ecx; uFlags
0x180022696  call    cs:__imp_LocalAlloc
0x18002269d  nop     dword ptr [rax+rax+00h]
0x1800226a2  mov     rdi, rax
0x1800226a5  test    rax, rax
0x1800226a8  jz      short loc_180022724
0x1800226aa  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800226af  lea     rax, [rsp+38h+TokenInformationLength]
0x1800226b4  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800226b9  mov     r8, rdi; TokenInformation
0x1800226bc  mov     edx, esi; TokenInformationClass
0x1800226be  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800226c3  call    cs:__imp_GetTokenInformation
0x1800226ca  nop     dword ptr [rax+rax+00h]
0x1800226cf  test    eax, eax
0x1800226d1  jz      short loc_180022724
0x1800226d3  mov     rsi, [rdi]
0x1800226d6  mov     rcx, rsi; pSid
0x1800226d9  call    cs:__imp_GetLengthSid
0x1800226e0  nop     dword ptr [rax+rax+00h]
0x1800226e5  mov     edx, eax; uBytes
0x1800226e7  xor     ecx, ecx; uFlags
0x1800226e9  call    cs:__imp_LocalAlloc
0x1800226f0  nop     dword ptr [rax+rax+00h]
0x1800226f5  mov     rbx, rax
0x1800226f8  test    rax, rax
0x1800226fb  jz      short loc_180022724
0x1800226fd  mov     rcx, rsi; pSid
0x180022700  call    cs:__imp_GetLengthSid
0x180022707  nop     dword ptr [rax+rax+00h]
0x18002270c  mov     r8, rsi; pSourceSid
0x18002270f  mov     rdx, rbx; pDestinationSid
0x180022712  mov     ecx, eax; nDestinationSidLength
0x180022714  call    cs:__imp_CopySid
0x18002271b  nop     dword ptr [rax+rax+00h]
0x180022720  test    eax, eax
0x180022722  jnz     short loc_180022735
0x180022724  mov     rcx, rbx; hMem
0x180022727  call    cs:__imp_LocalFree
0x18002272e  nop     dword ptr [rax+rax+00h]
0x180022733  xor     ebx, ebx
0x180022735  mov     rcx, rdi; hMem
0x180022738  call    cs:__imp_LocalFree
0x18002273f  nop     dword ptr [rax+rax+00h]
0x180022744  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180022749  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002274d  jz      short loc_18002275B
0x18002274f  call    cs:__imp_CloseHandle
0x180022756  nop     dword ptr [rax+rax+00h]
0x18002275b  mov     rsi, [rsp+38h+arg_18]
0x180022760  mov     rax, rbx
0x180022763  mov     rbx, [rsp+38h+arg_10]
0x180022768  add     rsp, 30h
0x18002276c  pop     rdi
0x18002276d  retn
```
