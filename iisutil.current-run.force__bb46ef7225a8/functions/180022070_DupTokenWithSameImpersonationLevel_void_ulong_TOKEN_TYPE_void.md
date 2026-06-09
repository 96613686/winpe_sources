# DupTokenWithSameImpersonationLevel(void *,ulong,_TOKEN_TYPE,void * *)

- ea: `0x180022070`
- end: `0x180022128`
- name: `?DupTokenWithSameImpersonationLevel@@YAHPEAXKW4_TOKEN_TYPE@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, DWORD dwDesiredAccess, TOKEN_TYPE TokenType, PHANDLE phNewToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007300`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220c0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022119`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022119`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800220ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800220ad`

## string_xrefs

- `0x1800220df`: `GetTokenInformation - failed to get TokenImpersonationLevel LastError=%d, using SecurityImpersonation\n`
- `0x1800220cd`: `DupTokenWithSameImpersonationLevel`
- `0x1800220d8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\tokenacl.cxx`

## pseudocode

```c
BOOL __fastcall DupTokenWithSameImpersonationLevel(
        HANDLE hExistingToken,
        DWORD dwDesiredAccess,
        TOKEN_TYPE TokenType,
        PHANDLE phNewToken)
{
  char LastError; // al
  SECURITY_IMPERSONATION_LEVEL v9; // r9d
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  DWORD ReturnLength[13]; // [rsp+34h] [rbp-34h] BYREF

  TokenInformation = 0;
  ReturnLength[0] = 0;
  if ( GetTokenInformation(hExistingToken, TokenImpersonationLevel, &TokenInformation, 4u, ReturnLength) )
  {
    v9 = TokenInformation;
  }
  else
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\tokenacl.cxx",
        0x391u,
        "DupTokenWithSameImpersonationLevel",
        "GetTokenInformation - failed to get TokenImpersonationLevel LastError=%d, using SecurityImpersonation\n",
        LastError);
    }
    v9 = SecurityImpersonation;
    TokenInformation = 2;
  }
  return DuplicateTokenEx(hExistingToken, dwDesiredAccess, 0, v9, TokenType, phNewToken);
}

```

## disassembly

```asm
0x180022070  push    rbx
0x180022072  push    rbp
0x180022073  push    rsi
0x180022074  push    rdi
0x180022075  sub     rsp, 48h
0x180022079  mov     rdi, r9
0x18002207c  mov     [rsp+68h+TokenInformation], 0
0x180022084  mov     r9d, 4; TokenInformationLength
0x18002208a  mov     [rsp+68h+var_34], 0
0x180022092  mov     esi, r8d
0x180022095  lea     rax, [rsp+68h+var_34]
0x18002209a  mov     ebp, edx
0x18002209c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800220a1  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x1800220a6  mov     rbx, rcx
0x1800220a9  lea     edx, [r9+5]; TokenInformationClass
0x1800220ad  call    cs:__imp_GetTokenInformation
0x1800220b3  test    eax, eax
0x1800220b5  jnz     short loc_180022103
0x1800220b7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800220be  jz      short loc_1800220F6
0x1800220c0  call    cs:__imp_GetLastError
0x1800220c6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800220cd  lea     r9, aDuptokenwithsa_0; "DupTokenWithSameImpersonationLevel"
0x1800220d4  mov     dword ptr [rsp+68h+phNewToken], eax; char
0x1800220d8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800220df  lea     rax, aGettokeninform; "GetTokenInformation - failed to get Tok"...
0x1800220e6  mov     r8d, 391h; unsigned int
0x1800220ec  mov     [rsp+68h+ReturnLength], rax; char *
0x1800220f1  call    PuDbgPrint
0x1800220f6  mov     r9d, 2
0x1800220fc  mov     [rsp+68h+TokenInformation], r9d
0x180022101  jmp     short loc_180022108
0x180022103  mov     r9d, [rsp+68h+TokenInformation]; ImpersonationLevel
0x180022108  mov     [rsp+68h+phNewToken], rdi; phNewToken
0x18002210d  xor     r8d, r8d; lpTokenAttributes
0x180022110  mov     edx, ebp; dwDesiredAccess
0x180022112  mov     dword ptr [rsp+68h+ReturnLength], esi; TokenType
0x180022116  mov     rcx, rbx; hExistingToken
0x180022119  call    cs:__imp_DuplicateTokenEx
0x18002211f  add     rsp, 48h
0x180022123  pop     rdi
0x180022124  pop     rsi
0x180022125  pop     rbp
0x180022126  pop     rbx
0x180022127  retn
```
