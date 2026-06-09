# WhoAmI(ushort * *)

- ea: `0x140003384`
- end: `0x14000354a`
- name: `?WhoAmI@@YAJPEAPEAG@Z`
- size: `454`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f7c`

## callees

- `0x140003384`
- `0x140005482`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003407`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003407`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400033d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400033d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400033c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400033c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003510`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140003497`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140003497`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140003450`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140003450`

## pseudocode

```c
__int64 __fastcall WhoAmI(unsigned __int16 **a1)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  unsigned int v7; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[512]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Name[512]; // [rsp+660h] [rbp+560h] BYREF

  peUse = SidTypeUser;
  cchName = 0;
  cchReferencedDomainName = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &ReturnLength)
      && (cchName = 512,
          cchReferencedDomainName = 512,
          LookupAccountSidW(
            0,
            TokenInformation[0],
            Name,
            &cchName,
            ReferencedDomainName,
            &cchReferencedDomainName,
            &peUse)) )
    {
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( Name[v4] );
      cchName = v4;
      do
        ++v3;
      while ( ReferencedDomainName[v3] );
      cchReferencedDomainName = v3;
      v5 = (unsigned __int16 *)LocalAlloc(0, 2LL * (unsigned int)(v3 + v4 + 2));
      v6 = v5;
      if ( v5 )
      {
        memcpy_0(v5, ReferencedDomainName, 2LL * cchReferencedDomainName);
        v6[cchReferencedDomainName] = 92;
        memcpy_0(&v6[cchReferencedDomainName + 1], Name, 2LL * (cchName + 1));
        *a1 = v6;
        v7 = 0;
      }
      else
      {
        v7 = -2147024888;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x140003384  push    rbp
0x140003386  push    rbx
0x140003387  push    rsi
0x140003388  push    rdi
0x140003389  lea     rbp, [rsp-978h]
0x140003391  sub     rsp, 0A78h
0x140003398  mov     rax, cs:__security_cookie
0x14000339f  xor     rax, rsp
0x1400033a2  mov     [rbp+990h+var_30], rax
0x1400033a9  xor     esi, esi
0x1400033ab  mov     [rsp+0A90h+var_A44], 1
0x1400033b3  mov     [rsp+0A90h+cchName], esi
0x1400033b7  mov     rdi, rcx
0x1400033ba  mov     [rsp+0A90h+var_A50], esi
0x1400033be  mov     [rsp+0A90h+TokenHandle], rsi
0x1400033c3  call    cs:__imp_GetCurrentProcess
0x1400033c9  lea     r8, [rsp+0A90h+TokenHandle]; TokenHandle
0x1400033ce  mov     edx, 20008h; DesiredAccess
0x1400033d3  mov     rcx, rax; ProcessHandle
0x1400033d6  call    cs:__imp_OpenProcessToken
0x1400033dc  test    eax, eax
0x1400033de  jz      loc_140003518
0x1400033e4  mov     rcx, [rsp+0A90h+TokenHandle]; TokenHandle
0x1400033e9  lea     rax, [rsp+0A90h+var_A48]
0x1400033ee  mov     ebx, 200h
0x1400033f3  mov     [rsp+0A90h+var_A48], esi
0x1400033f7  mov     r9d, ebx; TokenInformationLength
0x1400033fa  mov     [rsp+0A90h+ReturnLength], rax; ReturnLength
0x1400033ff  lea     r8, [rsp+0A90h+TokenInformation]; TokenInformation
0x140003404  lea     edx, [rsi+1]; TokenInformationClass
0x140003407  call    cs:__imp_GetTokenInformation
0x14000340d  test    eax, eax
0x14000340f  jz      loc_1400034F6
0x140003415  mov     rdx, [rsp+0A90h+TokenInformation]; Sid
0x14000341a  lea     rax, [rsp+0A90h+var_A44]
0x14000341f  mov     [rsp+0A90h+peUse], rax; peUse
0x140003424  lea     r9, [rsp+0A90h+cchName]; cchName
0x140003429  lea     rax, [rsp+0A90h+var_A50]
0x14000342e  mov     [rsp+0A90h+cchName], ebx
0x140003432  mov     [rsp+0A90h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140003437  lea     r8, [rbp+990h+Name]; Name
0x14000343e  lea     rax, [rbp+990h+ReferencedDomainName]
0x140003445  mov     [rsp+0A90h+var_A50], ebx
0x140003449  xor     ecx, ecx; lpSystemName
0x14000344b  mov     [rsp+0A90h+ReturnLength], rax; ReferencedDomainName
0x140003450  call    cs:__imp_LookupAccountSidW
0x140003456  test    eax, eax
0x140003458  jz      loc_1400034F6
0x14000345e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003462  lea     rdx, [rbp+990h+Name]
0x140003469  mov     rcx, rax
0x14000346c  inc     rcx
0x14000346f  cmp     [rdx+rcx*2], si
0x140003473  jnz     short loc_14000346C
0x140003475  mov     [rsp+0A90h+cchName], ecx
0x140003479  lea     rdx, [rbp+990h+ReferencedDomainName]
0x140003480  inc     rax
0x140003483  cmp     [rdx+rax*2], si
0x140003487  jnz     short loc_140003480
0x140003489  lea     edx, [rcx+2]
0x14000348c  mov     [rsp+0A90h+var_A50], eax
0x140003490  add     edx, eax
0x140003492  xor     ecx, ecx; uFlags
0x140003494  add     rdx, rdx; uBytes
0x140003497  call    cs:__imp_LocalAlloc
0x14000349d  mov     rbx, rax
0x1400034a0  test    rax, rax
0x1400034a3  jz      short loc_1400034EF
0x1400034a5  mov     r8d, [rsp+0A90h+var_A50]
0x1400034aa  lea     rdx, [rbp+990h+ReferencedDomainName]; Src
0x1400034b1  add     r8, r8; Size
0x1400034b4  mov     rcx, rax; void *
0x1400034b7  call    memcpy_0
0x1400034bc  mov     ecx, [rsp+0A90h+var_A50]
0x1400034c0  lea     rdx, [rbp+990h+Name]; Src
0x1400034c7  mov     word ptr [rbx+rcx*2], 5Ch ; '\'
0x1400034cd  mov     r8d, [rsp+0A90h+cchName]
0x1400034d2  mov     eax, [rsp+0A90h+var_A50]
0x1400034d6  inc     r8d
0x1400034d9  inc     rax
0x1400034dc  add     r8, r8; Size
0x1400034df  lea     rcx, [rbx+rax*2]; void *
0x1400034e3  call    memcpy_0
0x1400034e8  mov     [rdi], rbx
0x1400034eb  mov     ebx, esi
0x1400034ed  jmp     short loc_14000350B
0x1400034ef  mov     ebx, 80070008h
0x1400034f4  jmp     short loc_14000350B
0x1400034f6  call    cs:__imp_GetLastError
0x1400034fc  mov     ebx, eax
0x1400034fe  test    eax, eax
0x140003500  jle     short loc_14000350B
0x140003502  movzx   ebx, ax
0x140003505  or      ebx, 80070000h
0x14000350b  mov     rcx, [rsp+0A90h+TokenHandle]; hObject
0x140003510  call    cs:__imp_CloseHandle
0x140003516  jmp     short loc_14000352D
0x140003518  call    cs:__imp_GetLastError
0x14000351e  mov     ebx, eax
0x140003520  test    eax, eax
0x140003522  jle     short loc_14000352D
0x140003524  movzx   ebx, ax
0x140003527  or      ebx, 80070000h
0x14000352d  mov     eax, ebx
0x14000352f  mov     rcx, [rbp+990h+var_30]
0x140003536  xor     rcx, rsp; StackCookie
0x140003539  call    __security_check_cookie
0x14000353e  add     rsp, 0A78h
0x140003545  pop     rdi
0x140003546  pop     rsi
0x140003547  pop     rbx
0x140003548  pop     rbp
0x140003549  retn
```
