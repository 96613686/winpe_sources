# IkeGetPeerTokenResponder

- ea: `0x18007efdc`
- end: `0x18007f117`
- name: `IkeGetPeerTokenResponder`
- size: `315`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082710`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x18007efdc`
- `0x180084874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f030`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007f0cb`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007f0cb`
- `SspiCli!QuerySecurityContextToken` at `0x18007f099`
- `SspiCli!QuerySecurityContextToken` at `0x18007f099`

## string_xrefs

- `0x18007f0a7`: `QuerySecurityContextToken`
- `0x18007efef`: `IkeGetPeerTokenResponder`
- `0x18007f076`: `IkeGetPeerTokenResponder`
- `0x18007f0f2`: `IkeGetPeerTokenResponder`
- `0x18007f0fe`: `IkeGetPeerTokenResponder`
- `0x18007f0db`: `DuplicateToken`

## pseudocode

```c
__int64 __fastcall IkeGetPeerTokenResponder(__int64 a1, __int64 a2)
{
  int v4; // esi
  int v5; // ebp
  HANDLE *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // r8
  const char *v10; // rdx
  DWORD SecurityContextToken; // eax

  v4 = 0;
  v5 = 0;
  TraceLogHelper("IkeGetPeerTokenResponder", 1);
  if ( (*(_DWORD *)(a2 + 72) & 0x100000) != 0 )
    v6 = (HANDLE *)(*(_QWORD *)(*(_QWORD *)(a1 + 1096) + 24LL) + 232LL);
  else
    v6 = (HANDLE *)(a1 + 984);
  if ( *v6 )
  {
    CloseHandle(*v6);
    *v6 = 0;
  }
  if ( *(_DWORD *)(a2 + 88) != 2 )
  {
    v7 = (unsigned int)(*(_DWORD *)(a2 + 88) - 3);
    if ( *(_DWORD *)(a2 + 88) == 3 )
    {
      v5 = 1;
      goto LABEL_13;
    }
    v7 = (unsigned int)(*(_DWORD *)(a2 + 88) - 4);
    if ( *(_DWORD *)(a2 + 88) == 4 )
    {
LABEL_17:
      v4 = IsAllowedAnonymousTokenForSsl(v7, a2);
      if ( (*(_DWORD *)(a2 + 40) & 2) == 0 )
        goto LABEL_13;
      goto LABEL_18;
    }
    if ( *(_DWORD *)(a2 + 88) != 5 )
    {
      v7 = (unsigned int)(*(_DWORD *)(a2 + 88) - 9);
      if ( *(_DWORD *)(a2 + 88) != 9 )
      {
        v7 = (unsigned int)(*(_DWORD *)(a2 + 88) - 10);
        if ( *(_DWORD *)(a2 + 88) != 10 )
        {
          if ( *(_DWORD *)(a2 + 88) != 12 )
            goto LABEL_13;
          goto LABEL_18;
        }
      }
      goto LABEL_17;
    }
  }
LABEL_18:
  SecurityContextToken = QuerySecurityContextToken((PCtxtHandle)(a2 + 24), v6);
  if ( !v4 && SecurityContextToken )
  {
    v10 = "QuerySecurityContextToken";
LABEL_24:
    v9 = SecurityContextToken;
    goto LABEL_25;
  }
LABEL_13:
  v8 = 0;
  if ( !*v6 )
  {
    if ( !v5 && !v4 )
    {
      v9 = 87;
      v10 = "IkeGetPeerTokenResponder";
LABEL_25:
      v8 = WfpReportSysErrorAsWinError(v7, v10, v9, 1);
      goto LABEL_26;
    }
    if ( !DuplicateToken(gIkeExtGlobals[86].OwningThread, SecurityImpersonation, v6) )
    {
      SecurityContextToken = GetLastError();
      v10 = "DuplicateToken";
      goto LABEL_24;
    }
  }
LABEL_26:
  TraceLogHelper("IkeGetPeerTokenResponder", 0);
  return IkeReturnError(v8, "IkeGetPeerTokenResponder");
}

```

## disassembly

```asm
0x18007efdc  push    rbx
0x18007efde  push    rbp
0x18007efdf  push    rsi
0x18007efe0  push    rdi
0x18007efe1  push    r14
0x18007efe3  sub     rsp, 20h
0x18007efe7  mov     rdi, rdx
0x18007efea  mov     rbx, rcx
0x18007efed  xor     esi, esi
0x18007efef  lea     rcx, aIkegetpeertoke_0; "IkeGetPeerTokenResponder"
0x18007eff6  xor     ebp, ebp
0x18007eff8  lea     r14d, [rsi+1]
0x18007effc  mov     edx, r14d
0x18007efff  call    TraceLogHelper
0x18007f004  test    dword ptr [rdi+48h], 100000h
0x18007f00b  jz      short loc_18007F021
0x18007f00d  mov     rax, [rbx+448h]
0x18007f014  mov     rbx, [rax+18h]
0x18007f018  add     rbx, 0E8h
0x18007f01f  jmp     short loc_18007F028
0x18007f021  add     rbx, 3D8h
0x18007f028  mov     rcx, [rbx]; hObject
0x18007f02b  test    rcx, rcx
0x18007f02e  jz      short loc_18007F039
0x18007f030  call    cs:__imp_CloseHandle
0x18007f036  mov     [rbx], rsi
0x18007f039  mov     ecx, [rdi+58h]
0x18007f03c  sub     ecx, 2
0x18007f03f  jz      short loc_18007F092
0x18007f041  sub     ecx, r14d
0x18007f044  jz      short loc_18007F0B0
0x18007f046  sub     ecx, r14d
0x18007f049  jz      short loc_18007F07F
0x18007f04b  sub     ecx, r14d
0x18007f04e  jz      short loc_18007F092
0x18007f050  sub     ecx, 4
0x18007f053  jz      short loc_18007F07F
0x18007f055  sub     ecx, r14d
0x18007f058  jz      short loc_18007F07F
0x18007f05a  cmp     ecx, 2
0x18007f05d  jz      short loc_18007F092
0x18007f05f  xor     edi, edi
0x18007f061  cmp     [rbx], rdi
0x18007f064  jnz     loc_18007F0F0
0x18007f06a  test    ebp, ebp
0x18007f06c  jnz     short loc_18007F0B5
0x18007f06e  test    esi, esi
0x18007f070  jnz     short loc_18007F0B5
0x18007f072  lea     r8d, [rdi+57h]
0x18007f076  lea     rdx, aIkegetpeertoke_0; "IkeGetPeerTokenResponder"
0x18007f07d  jmp     short loc_18007F0E5
0x18007f07f  mov     rdx, rdi
0x18007f082  call    IsAllowedAnonymousTokenForSsl
0x18007f087  test    dword ptr [rdi+28h], 2
0x18007f08e  mov     esi, eax
0x18007f090  jz      short loc_18007F05F
0x18007f092  lea     rcx, [rdi+18h]; phContext
0x18007f096  mov     rdx, rbx; Token
0x18007f099  call    cs:__imp_QuerySecurityContextToken
0x18007f09f  test    esi, esi
0x18007f0a1  jnz     short loc_18007F05F
0x18007f0a3  test    eax, eax
0x18007f0a5  jz      short loc_18007F05F
0x18007f0a7  lea     rdx, aQuerysecurityc_0; "QuerySecurityContextToken"
0x18007f0ae  jmp     short loc_18007F0E2
0x18007f0b0  mov     ebp, r14d
0x18007f0b3  jmp     short loc_18007F05F
0x18007f0b5  mov     rcx, cs:gIkeExtGlobals
0x18007f0bc  mov     r8, rbx; DuplicateTokenHandle
0x18007f0bf  mov     edx, 2; ImpersonationLevel
0x18007f0c4  mov     rcx, [rcx+0D80h]; ExistingTokenHandle
0x18007f0cb  call    cs:__imp_DuplicateToken
0x18007f0d1  test    eax, eax
0x18007f0d3  jnz     short loc_18007F0F0
0x18007f0d5  call    cs:__imp_GetLastError
0x18007f0db  lea     rdx, aDuplicatetoken; "DuplicateToken"
0x18007f0e2  mov     r8d, eax
0x18007f0e5  mov     r9d, r14d
0x18007f0e8  call    WfpReportSysErrorAsWinError
0x18007f0ed  mov     rdi, rax
0x18007f0f0  xor     edx, edx
0x18007f0f2  lea     rcx, aIkegetpeertoke_0; "IkeGetPeerTokenResponder"
0x18007f0f9  call    TraceLogHelper
0x18007f0fe  lea     rdx, aIkegetpeertoke_0; "IkeGetPeerTokenResponder"
0x18007f105  mov     rcx, rdi
0x18007f108  add     rsp, 20h
0x18007f10c  pop     r14
0x18007f10e  pop     rdi
0x18007f10f  pop     rsi
0x18007f110  pop     rbp
0x18007f111  pop     rbx
0x18007f112  jmp     IkeReturnError
```
