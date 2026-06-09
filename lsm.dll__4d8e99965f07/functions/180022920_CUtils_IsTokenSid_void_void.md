# CUtils::IsTokenSid(void *,void *)

- ea: `0x180022920`
- end: `0x180022ae0`
- name: `?IsTokenSid@CUtils@@CAJPEAX0@Z`
- size: `448`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800163b4`

## callees

- `0x1800077a0`
- `0x180022920`
- `0x18004e850`
- `0x18004f318`
- `0x180099530`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180022a1d`
- `ntdll!RtlEqualSid` at `0x180022a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022976`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022a07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022976`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022a07`

## string_xrefs

- `0x180022a62`: `IsTokenSid: Error %x Getting TokenInformation`
- `0x180022aab`: `IsTokenSid: Error %x Getting TokenInformation on buffer\n`
- `0x180022ac4`: `IsTokenSid: Error allocating %d bytes memory\n`

## pseudocode

```c
__int64 __fastcall CUtils::IsTokenSid(HANDLE TokenHandle, void *a2)
{
  PSID v3; // rdi
  unsigned int v4; // r14d
  unsigned __int64 v5; // rax
  void *v6; // rsp
  signed int v8; // eax
  signed int LastError; // eax
  PSID TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  PSID *p_TokenInformation; // [rsp+38h] [rbp+8h]
  PSID v12; // [rsp+40h] [rbp+10h]

  v3 = CUtils::pSystemSid;
  v12 = CUtils::pSystemSid;
  if ( CUtils::pSystemSid )
  {
    v4 = 0;
    LODWORD(TokenInformation) = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformation);
    if ( (_DWORD)TokenInformation )
    {
      HIDWORD(TokenInformation) = (_DWORD)TokenInformation;
      v5 = (unsigned int)TokenInformation + 15LL;
      if ( v5 < (unsigned int)TokenInformation )
        v5 = 0xFFFFFFFFFFFFFF0LL;
      v6 = alloca(v5 & 0xFFFFFFFFFFFFFFF0uLL);
      p_TokenInformation = &TokenInformation;
      if ( &TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               &TokenInformation,
               (DWORD)TokenInformation,
               (PDWORD)&TokenInformation) )
        {
          LOBYTE(v4) = RtlEqualSid(TokenInformation, v3) == 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation on buffer\n", v4);
        }
      }
      else
      {
        _DbgPrintMessage(8, "IsTokenSid: Error allocating %d bytes memory\n", (_DWORD)TokenInformation);
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation", v4);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v4;
}

```

## disassembly

```asm
0x180022920  mov     [rsp-8+arg_0], rcx
0x180022925  push    rbp
0x180022926  push    rbx
0x180022927  push    rsi
0x180022928  push    rdi
0x180022929  push    r14
0x18002292b  push    r15
0x18002292d  sub     rsp, 58h
0x180022931  lea     rbp, [rsp+30h]
0x180022936  mov     rax, cs:__security_cookie
0x18002293d  xor     rax, rbp
0x180022940  mov     [rbp+50h+var_38], rax
0x180022944  mov     r15, rcx
0x180022947  mov     rdi, cs:?pSystemSid@CUtils@@0PEAXEA; void * CUtils::pSystemSid
0x18002294e  mov     [rbp+50h+var_40], rdi
0x180022952  test    rdi, rdi
0x180022955  jz      loc_180022A82
0x18002295b  xor     r14d, r14d
0x18002295e  mov     [rbp+50h+TokenInformation], r14d
0x180022962  lea     rax, [rbp+50h+TokenInformation]
0x180022966  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18002296b  xor     r9d, r9d; TokenInformationLength
0x18002296e  xor     r8d, r8d; TokenInformation
0x180022971  mov     edx, 1; TokenInformationClass
0x180022976  call    cs:__imp_GetTokenInformation
0x18002297d  nop     dword ptr [rax+rax+00h]
0x180022982  mov     esi, [rbp+50h+TokenInformation]
0x180022985  test    esi, esi
0x180022987  jz      loc_180022A4C
0x18002298d  mov     [rbp+50h+var_4C], esi
0x180022990  lea     rax, [rsi+0Fh]
0x180022994  cmp     rax, rsi
0x180022997  ja      short loc_1800229A3
0x180022999  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800229a3  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800229a7  call    _alloca_probe
0x1800229ac  sub     rsp, rax
0x1800229af  lea     rbx, [rsp+80h+TokenInformation]
0x1800229b4  mov     [rbp+50h+var_48], rbx
0x1800229b8  jmp     short loc_1800229E7
0x1800229ba  call    _o__resetstkoflw_0
0x1800229bf  xor     ebx, ebx
0x1800229c1  mov     [rbp+50h+var_48], rbx
0x1800229c5  mov     esi, [rbp+50h+var_4C]
0x1800229c8  mov     r8d, esi
0x1800229cb  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x1800229d2  mov     ecx, 8; int
0x1800229d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800229dc  xor     r14d, r14d
0x1800229df  mov     rdi, [rbp+50h+var_40]
0x1800229e3  mov     r15, [rbp+50h+arg_0]
0x1800229e7  test    rbx, rbx
0x1800229ea  jz      loc_180022AC1
0x1800229f0  lea     rax, [rbp+50h+TokenInformation]
0x1800229f4  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800229f9  mov     r9d, esi; TokenInformationLength
0x1800229fc  mov     r8, rbx; TokenInformation
0x1800229ff  mov     edx, 1; TokenInformationClass
0x180022a04  mov     rcx, r15; TokenHandle
0x180022a07  call    cs:__imp_GetTokenInformation
0x180022a0e  nop     dword ptr [rax+rax+00h]
0x180022a13  test    eax, eax
0x180022a15  jz      short loc_180022A8A
0x180022a17  mov     rdx, rdi; Sid2
0x180022a1a  mov     rcx, [rbx]; Sid1
0x180022a1d  call    cs:__imp_RtlEqualSid
0x180022a24  nop     dword ptr [rax+rax+00h]
0x180022a29  test    al, al
0x180022a2b  setz    r14b
0x180022a2f  mov     eax, r14d
0x180022a32  mov     rcx, [rbp+50h+var_38]
0x180022a36  xor     rcx, rbp; StackCookie
0x180022a39  call    __security_check_cookie
0x180022a3e  lea     rsp, [rbp+28h]
0x180022a42  pop     r15
0x180022a44  pop     r14
0x180022a46  pop     rdi
0x180022a47  pop     rsi
0x180022a48  pop     rbx
0x180022a49  pop     rbp
0x180022a4a  retn
0x180022a4c  call    cs:__imp_GetLastError
0x180022a53  nop     dword ptr [rax+rax+00h]
0x180022a58  mov     r14d, eax
0x180022a5b  test    eax, eax
0x180022a5d  jg      short loc_180022A75
0x180022a5f  mov     r8d, r14d
0x180022a62  lea     rdx, aIstokensidErro_1; "IsTokenSid: Error %x Getting TokenInfor"...
0x180022a69  mov     ecx, 8; int
0x180022a6e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022a73  jmp     short loc_180022A2F
0x180022a75  movzx   r14d, ax
0x180022a79  or      r14d, 80070000h
0x180022a80  jmp     short loc_180022A5F
0x180022a82  mov     r14d, 8000FFFFh
0x180022a88  jmp     short loc_180022A2F
0x180022a8a  call    cs:__imp_GetLastError
0x180022a91  nop     dword ptr [rax+rax+00h]
0x180022a96  mov     r14d, eax
0x180022a99  test    eax, eax
0x180022a9b  jle     short loc_180022AA8
0x180022a9d  movzx   r14d, ax
0x180022aa1  or      r14d, 80070000h
0x180022aa8  mov     r8d, r14d
0x180022aab  lea     rdx, aIstokensidErro_0; "IsTokenSid: Error %x Getting TokenInfor"...
0x180022ab2  mov     ecx, 8; int
0x180022ab7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022abc  jmp     loc_180022A2F
0x180022ac1  mov     r8d, esi
0x180022ac4  lea     rdx, aIstokensidErro; "IsTokenSid: Error allocating %d bytes m"...
0x180022acb  mov     ecx, 8; int
0x180022ad0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022ad5  mov     r14d, 8007000Eh
0x180022adb  jmp     loc_180022A2F
0x180099f00  push    rbp
0x180099f02  sub     rsp, 30h
0x180099f06  lea     rbp, [rdx+30h]
0x180099f0a  mov     rax, [rcx]
0x180099f0d  xor     ecx, ecx
0x180099f0f  cmp     dword ptr [rax], 0C00000FDh
0x180099f15  setz    cl
0x180099f18  mov     eax, ecx
0x180099f1a  add     rsp, 30h
0x180099f1e  pop     rbp
0x180099f1f  retn
```
