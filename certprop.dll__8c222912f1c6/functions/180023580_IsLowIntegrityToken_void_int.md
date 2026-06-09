# IsLowIntegrityToken(void *,int *)

- ea: `0x180023580`
- end: `0x180023720`
- name: `?IsLowIntegrityToken@@YAKPEAXPEAH@Z`
- size: `416`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800232c4`

## callees

- `0x180023580`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023603`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023689`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023603`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800235f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023678`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800235f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023678`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002363d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002363d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023663`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800235d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023633`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800235d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023633`
- `ntdll!RtlEqualSid` at `0x1800236c1`
- `ntdll!RtlEqualSid` at `0x1800236c1`
- `ADVAPI32!CreateWellKnownSid` at `0x180023659`
- `ADVAPI32!CreateWellKnownSid` at `0x1800236aa`
- `ADVAPI32!CreateWellKnownSid` at `0x180023659`
- `ADVAPI32!CreateWellKnownSid` at `0x1800236aa`

## pseudocode

```c
__int64 __fastcall IsLowIntegrityToken(HANDLE TokenHandle, int *a2)
{
  void **v4; // rdi
  void *v5; // rsi
  DWORD v6; // ebx
  DWORD LastError; // eax
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  void *v12; // rax
  void *v13; // rdx
  HANDLE v14; // rax
  HANDLE v15; // rax
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  cbSid = 0;
  if ( !TokenHandle || !a2 )
    return 87;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, (PDWORD)&dwBytes) )
    goto LABEL_27;
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
    goto LABEL_27;
  if ( LastError != 122 )
    return v6;
  v8 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v4 = (void **)HeapAlloc(ProcessHeap, 8u, v8);
  if ( !v4 )
    return 14;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, dwBytes, (PDWORD)&dwBytes) )
  {
LABEL_27:
    if ( !CreateWellKnownSid(WinLowLabelSid, 0, 0, &cbSid) )
      v6 = GetLastError();
    if ( v6 )
    {
      if ( v6 != 122 )
        goto LABEL_19;
      v10 = cbSid;
      v11 = GetProcessHeap();
      v12 = HeapAlloc(v11, 8u, v10);
      v5 = v12;
      if ( !v4 )
      {
        v6 = 14;
        goto LABEL_21;
      }
      v6 = 0;
      if ( !CreateWellKnownSid(WinLowLabelSid, 0, v12, &cbSid) )
        goto LABEL_9;
    }
    v13 = *v4;
    *a2 = 0;
    if ( RtlEqualSid(v5, v13) )
      *a2 = 1;
LABEL_19:
    if ( !v4 )
      goto LABEL_21;
    goto LABEL_20;
  }
LABEL_9:
  v6 = GetLastError();
LABEL_20:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v4);
LABEL_21:
  if ( v5 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v5);
  }
  return v6;
}

```

## disassembly

```asm
0x180023580  mov     rax, rsp
0x180023583  mov     [rax+10h], rbx
0x180023587  mov     [rax+20h], rbp
0x18002358b  push    rsi
0x18002358c  push    rdi
0x18002358d  push    r14
0x18002358f  sub     rsp, 30h
0x180023593  mov     dword ptr [rax+8], 0
0x18002359a  mov     r14, rdx
0x18002359d  mov     dword ptr [rax+18h], 0
0x1800235a4  mov     rbp, rcx
0x1800235a7  test    rcx, rcx
0x1800235aa  jz      loc_180023706
0x1800235b0  test    rdx, rdx
0x1800235b3  jz      loc_180023706
0x1800235b9  lea     rax, [rax+8]
0x1800235bd  xor     edi, edi
0x1800235bf  xor     r9d, r9d; TokenInformationLength
0x1800235c2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800235c7  xor     r8d, r8d; TokenInformation
0x1800235ca  xor     esi, esi
0x1800235cc  xor     ebx, ebx
0x1800235ce  lea     edx, [rdi+19h]; TokenInformationClass
0x1800235d1  call    cs:__imp_GetTokenInformation
0x1800235d7  test    eax, eax
0x1800235d9  jnz     short loc_18002364A
0x1800235db  call    cs:__imp_GetLastError
0x1800235e1  mov     ebx, eax
0x1800235e3  test    eax, eax
0x1800235e5  jz      short loc_18002364A
0x1800235e7  cmp     eax, 7Ah ; 'z'
0x1800235ea  jnz     loc_18002370B
0x1800235f0  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x1800235f4  call    cs:__imp_GetProcessHeap
0x1800235fa  mov     r8d, ebx; dwBytes
0x1800235fd  lea     edx, [rdi+8]; dwFlags
0x180023600  mov     rcx, rax; hHeap
0x180023603  call    cs:__imp_HeapAlloc
0x180023609  mov     rdi, rax
0x18002360c  test    rax, rax
0x18002360f  jnz     short loc_180023619
0x180023611  lea     ebx, [rsi+0Eh]
0x180023614  jmp     loc_18002370B
0x180023619  mov     r9d, dword ptr [rsp+48h+dwBytes]; TokenInformationLength
0x18002361e  lea     rax, [rsp+48h+dwBytes]
0x180023623  xor     ebx, ebx
0x180023625  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002362a  mov     r8, rdi; TokenInformation
0x18002362d  mov     rcx, rbp; TokenHandle
0x180023630  lea     edx, [rbx+19h]; TokenInformationClass
0x180023633  call    cs:__imp_GetTokenInformation
0x180023639  test    eax, eax
0x18002363b  jnz     short loc_18002364A
0x18002363d  call    cs:__imp_GetLastError
0x180023643  mov     ebx, eax
0x180023645  jmp     loc_1800236D7
0x18002364a  xor     edx, edx; DomainSid
0x18002364c  lea     r9, [rsp+48h+cbSid]; cbSid
0x180023651  xor     r8d, r8d; pSid
0x180023654  lea     ebp, [rdx+42h]
0x180023657  mov     ecx, ebp; WellKnownSidType
0x180023659  call    cs:__imp_CreateWellKnownSid
0x18002365f  test    eax, eax
0x180023661  jnz     short loc_18002366B
0x180023663  call    cs:__imp_GetLastError
0x180023669  mov     ebx, eax
0x18002366b  test    ebx, ebx
0x18002366d  jz      short loc_1800236B4
0x18002366f  cmp     ebx, 7Ah ; 'z'
0x180023672  jnz     short loc_1800236D2
0x180023674  mov     ebx, [rsp+48h+cbSid]
0x180023678  call    cs:__imp_GetProcessHeap
0x18002367e  mov     r8d, ebx; dwBytes
0x180023681  mov     edx, 8; dwFlags
0x180023686  mov     rcx, rax; hHeap
0x180023689  call    cs:__imp_HeapAlloc
0x18002368f  mov     rsi, rax
0x180023692  test    rdi, rdi
0x180023695  jnz     short loc_18002369C
0x180023697  lea     ebx, [rdi+0Eh]
0x18002369a  jmp     short loc_1800236EB
0x18002369c  lea     r9, [rsp+48h+cbSid]; cbSid
0x1800236a1  mov     r8, rax; pSid
0x1800236a4  xor     edx, edx; DomainSid
0x1800236a6  mov     ecx, ebp; WellKnownSidType
0x1800236a8  xor     ebx, ebx
0x1800236aa  call    cs:__imp_CreateWellKnownSid
0x1800236b0  test    eax, eax
0x1800236b2  jz      short loc_18002363D
0x1800236b4  mov     rdx, [rdi]; Sid2
0x1800236b7  mov     rcx, rsi; Sid1
0x1800236ba  mov     dword ptr [r14], 0
0x1800236c1  call    cs:__imp_RtlEqualSid
0x1800236c7  test    al, al
0x1800236c9  jz      short loc_1800236D2
0x1800236cb  mov     dword ptr [r14], 1
0x1800236d2  test    rdi, rdi
0x1800236d5  jz      short loc_1800236EB
0x1800236d7  call    cs:__imp_GetProcessHeap
0x1800236dd  mov     r8, rdi; lpMem
0x1800236e0  xor     edx, edx; dwFlags
0x1800236e2  mov     rcx, rax; hHeap
0x1800236e5  call    cs:__imp_HeapFree
0x1800236eb  test    rsi, rsi
0x1800236ee  jz      short loc_18002370B
0x1800236f0  call    cs:__imp_GetProcessHeap
0x1800236f6  mov     r8, rsi; lpMem
0x1800236f9  xor     edx, edx; dwFlags
0x1800236fb  mov     rcx, rax; hHeap
0x1800236fe  call    cs:__imp_HeapFree
0x180023704  jmp     short loc_18002370B
0x180023706  mov     ebx, 57h ; 'W'
0x18002370b  mov     rbp, [rsp+48h+arg_18]
0x180023710  mov     eax, ebx
0x180023712  mov     rbx, [rsp+48h+arg_8]
0x180023717  add     rsp, 30h
0x18002371b  pop     r14
0x18002371d  pop     rdi
0x18002371e  pop     rsi
0x18002371f  retn
```
