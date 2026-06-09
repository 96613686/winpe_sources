# CuipGetClientLogonSessionLUID(_CONSENTUI_PARAM_HEADER *,_LUID *)

- ea: `0x140014a18`
- end: `0x140014aaf`
- name: `?CuipGetClientLogonSessionLUID@@YAKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_LUID@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct _CONSENTUI_PARAM_HEADER *, struct _LUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cfdc`

## callees

- `0x140014a18`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014a8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140014a74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140014a74`

## pseudocode

```c
__int64 __fastcall CuipGetClientLogonSessionLUID(struct _CONSENTUI_PARAM_HEADER *a1, struct _LUID *a2)
{
  void *v2; // rcx
  unsigned int v4; // ecx
  DWORD ReturnLength; // [rsp+30h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-50h] BYREF
  __int128 v8; // [rsp+3Ch] [rbp-4Ch]
  __int128 v9; // [rsp+4Ch] [rbp-3Ch]
  __int128 v10; // [rsp+5Ch] [rbp-2Ch]
  int v11; // [rsp+6Ch] [rbp-1Ch]

  v2 = (void *)*((_QWORD *)a1 + 3);
  TokenInformation = 0;
  v11 = 0;
  ReturnLength = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( GetTokenInformation(v2, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
  {
    v4 = 0;
    *a2 = *(struct _LUID *)((char *)&v8 + 4);
  }
  else
  {
    return GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x140014a18  push    rbx
0x140014a1a  sub     rsp, 80h
0x140014a21  mov     rax, cs:__security_cookie
0x140014a28  xor     rax, rsp
0x140014a2b  mov     [rsp+88h+var_18], rax
0x140014a30  mov     rcx, [rcx+18h]; TokenHandle
0x140014a34  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x140014a39  xor     eax, eax
0x140014a3b  mov     [rsp+88h+TokenInformation], 0
0x140014a43  xorps   xmm0, xmm0
0x140014a46  mov     [rsp+88h+var_1C], eax
0x140014a4a  mov     r9d, 38h ; '8'; TokenInformationLength
0x140014a50  mov     [rsp+88h+var_58], eax
0x140014a54  mov     rbx, rdx
0x140014a57  lea     rax, [rsp+88h+var_58]
0x140014a5c  movups  [rsp+88h+var_4C], xmm0
0x140014a61  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x140014a66  lea     edx, [r9-2Eh]; TokenInformationClass
0x140014a6a  movups  [rsp+88h+var_3C], xmm0
0x140014a6f  movups  [rsp+88h+var_2C], xmm0
0x140014a74  call    cs:__imp_GetTokenInformation
0x140014a7a  test    eax, eax
0x140014a7c  jz      short loc_140014A8F
0x140014a7e  mov     eax, dword ptr [rsp+88h+var_4C+8]
0x140014a82  xor     ecx, ecx
0x140014a84  mov     [rbx+4], eax
0x140014a87  mov     eax, dword ptr [rsp+88h+var_4C+4]
0x140014a8b  mov     [rbx], eax
0x140014a8d  jmp     short loc_140014A97
0x140014a8f  call    cs:__imp_GetLastError
0x140014a95  mov     ecx, eax
0x140014a97  mov     eax, ecx
0x140014a99  mov     rcx, [rsp+88h+var_18]
0x140014a9e  xor     rcx, rsp; StackCookie
0x140014aa1  call    __security_check_cookie
0x140014aa6  add     rsp, 80h
0x140014aad  pop     rbx
0x140014aae  retn
```
