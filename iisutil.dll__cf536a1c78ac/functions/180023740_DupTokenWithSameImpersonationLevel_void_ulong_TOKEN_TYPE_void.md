# DupTokenWithSameImpersonationLevel(void *,ulong,_TOKEN_TYPE,void * *)

- ea: `0x180023740`
- end: `0x18002380b`
- name: `?DupTokenWithSameImpersonationLevel@@YAHPEAXKW4_TOKEN_TYPE@@PEAPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, DWORD dwDesiredAccess, TOKEN_TYPE TokenType, PHANDLE phNewToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008000`
- `0x180023740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023796`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800237f5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800237f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002377d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002377d`

## string_xrefs

- `0x1800237bb`: `GetTokenInformation - failed to get TokenImpersonationLevel LastError=%d, using SecurityImpersonation\n`
- `0x1800237a9`: `DupTokenWithSameImpersonationLevel`
- `0x1800237b4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\tokenacl.cxx`

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
0x180023740  push    rbx
0x180023742  push    rbp
0x180023743  push    rsi
0x180023744  push    rdi
0x180023745  sub     rsp, 48h
0x180023749  mov     rdi, r9
0x18002374c  mov     [rsp+68h+TokenInformation], 0
0x180023754  mov     r9d, 4; TokenInformationLength
0x18002375a  mov     [rsp+68h+var_34], 0
0x180023762  mov     esi, r8d
0x180023765  lea     rax, [rsp+68h+var_34]
0x18002376a  mov     ebp, edx
0x18002376c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180023771  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180023776  mov     rbx, rcx
0x180023779  lea     edx, [r9+5]; TokenInformationClass
0x18002377d  call    cs:__imp_GetTokenInformation
0x180023784  nop     dword ptr [rax+rax+00h]
0x180023789  test    eax, eax
0x18002378b  jnz     short loc_1800237DF
0x18002378d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023794  jz      short loc_1800237D2
0x180023796  call    cs:__imp_GetLastError
0x18002379d  nop     dword ptr [rax+rax+00h]
0x1800237a2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800237a9  lea     r9, aDuptokenwithsa_0; "DupTokenWithSameImpersonationLevel"
0x1800237b0  mov     dword ptr [rsp+68h+phNewToken], eax; char
0x1800237b4  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800237bb  lea     rax, aGettokeninform; "GetTokenInformation - failed to get Tok"...
0x1800237c2  mov     r8d, 391h; unsigned int
0x1800237c8  mov     [rsp+68h+ReturnLength], rax; char *
0x1800237cd  call    PuDbgPrint
0x1800237d2  mov     r9d, 2
0x1800237d8  mov     [rsp+68h+TokenInformation], r9d
0x1800237dd  jmp     short loc_1800237E4
0x1800237df  mov     r9d, [rsp+68h+TokenInformation]; ImpersonationLevel
0x1800237e4  mov     [rsp+68h+phNewToken], rdi; phNewToken
0x1800237e9  xor     r8d, r8d; lpTokenAttributes
0x1800237ec  mov     edx, ebp; dwDesiredAccess
0x1800237ee  mov     dword ptr [rsp+68h+ReturnLength], esi; TokenType
0x1800237f2  mov     rcx, rbx; hExistingToken
0x1800237f5  call    cs:__imp_DuplicateTokenEx
0x1800237fc  nop     dword ptr [rax+rax+00h]
0x180023801  add     rsp, 48h
0x180023805  pop     rdi
0x180023806  pop     rsi
0x180023807  pop     rbp
0x180023808  pop     rbx
0x180023809  retn
```
