# CuiCheckElevationAutoApproval(_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,_AUTO_APPROVE_TYPE *)

- ea: `0x140003660`
- end: `0x14000380d`
- name: `?CuiCheckElevationAutoApproval@@YAKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@PEAW4_AUTO_APPROVE_TYPE@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct _CONSENTUI_PARAM_HEADER *, struct _CREDUI_CONTEXT *, enum _AUTO_APPROVE_TYPE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140003660`
- `0x140003820`
- `0x140013a2c`
- `0x140013b50`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003805`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003745`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400036db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400036db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000371d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000371d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400036fc`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400036fc`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400036ca`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400036ca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140003730`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140003730`

## pseudocode

```c
__int64 __fastcall CuiCheckElevationAutoApproval(
        struct _CONSENTUI_PARAM_HEADER *a1,
        struct _CREDUI_CONTEXT *a2,
        enum _AUTO_APPROVE_TYPE *a3)
{
  unsigned int v3; // edi
  __int64 v7; // rcx
  PSID *v8; // rax
  PSID *v9; // r14
  unsigned int LastError; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-48h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+44h] [rbp-44h] BYREF

  v3 = 0;
  TokenInformationLength = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)a3 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_ddDd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      14,
      a3,
      *((unsigned int *)a1 + 1),
      *((_DWORD *)a1 + 8),
      *((_DWORD *)a1 + 12),
      *(_DWORD *)a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a2 == 3 )
  {
    TokenInformationLength = GetSidLengthRequired(1u) + 16;
    v8 = (PSID *)LocalAlloc(0, TokenInformationLength);
    v9 = v8;
    if ( !v8 )
    {
      v3 = 8;
      goto LABEL_7;
    }
    *v8 = v8 + 2;
    InitializeSid(v8 + 2, &pIdentifierAuthority, 1u);
    if ( GetTokenInformation(
           *((HANDLE *)a1 + 3),
           TokenIntegrityLevel,
           v9,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      if ( *GetSidSubAuthority(*v9, 0) < 0x2000 || *((char *)a1 + 48) >= 0 )
        goto LABEL_6;
      LastError = CuiCheckElevationAutoApprovalMedium(a1, a2, a3);
    }
    else
    {
      LastError = GetLastError();
    }
    v3 = LastError;
LABEL_6:
    LocalFree(v9);
LABEL_7:
    v7 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
    WPP_SF_Ddd(*(_QWORD *)(v7 + 16), a2, a3, v3, *(_DWORD *)a3, *(_DWORD *)a2);
  return v3;
}

```

## disassembly

```asm
0x140003660  push    rbx
0x140003662  push    rsi
0x140003663  push    rdi
0x140003664  sub     rsp, 70h
0x140003668  mov     rax, cs:__security_cookie
0x14000366f  xor     rax, rsp
0x140003672  mov     [rsp+88h+var_38], rax
0x140003677  xor     eax, eax
0x140003679  mov     [rsp+88h+arg_18], rbp
0x140003681  mov     edi, eax
0x140003683  mov     [rsp+88h+TokenInformationLength], eax
0x140003687  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], eax
0x14000368b  mov     rsi, r8
0x14000368e  mov     [r8], eax
0x140003691  mov     rbx, rdx
0x140003694  mov     [rsp+88h+var_28], r15
0x140003699  mov     rbp, rcx
0x14000369c  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 1000h
0x1400036a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036aa  lea     r15, WPP_GLOBAL_Control
0x1400036b1  cmp     rcx, r15
0x1400036b4  jnz     loc_140003780
0x1400036ba  cmp     dword ptr [rbx], 3
0x1400036bd  jnz     loc_140003757
0x1400036c3  mov     cl, 1; nSubAuthorityCount
0x1400036c5  mov     [rsp+88h+var_20], r14
0x1400036ca  call    cs:__imp_GetSidLengthRequired
0x1400036d0  add     eax, 10h
0x1400036d3  xor     ecx, ecx; uFlags
0x1400036d5  mov     edx, eax; uBytes
0x1400036d7  mov     [rsp+88h+TokenInformationLength], eax
0x1400036db  call    cs:__imp_LocalAlloc
0x1400036e1  mov     r14, rax
0x1400036e4  test    rax, rax
0x1400036e7  jz      loc_1400037FB
0x1400036ed  lea     rcx, [rax+10h]; Sid
0x1400036f1  mov     r8b, 1; nSubAuthorityCount
0x1400036f4  lea     rdx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x1400036f9  mov     [rax], rcx
0x1400036fc  call    cs:__imp_InitializeSid
0x140003702  mov     r9d, [rsp+88h+TokenInformationLength]; TokenInformationLength
0x140003707  lea     rax, [rsp+88h+TokenInformationLength]
0x14000370c  mov     rcx, [rbp+18h]; TokenHandle
0x140003710  mov     r8, r14; TokenInformation
0x140003713  mov     edx, 19h; TokenInformationClass
0x140003718  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x14000371d  call    cs:__imp_GetTokenInformation
0x140003723  test    eax, eax
0x140003725  jz      loc_140003805
0x14000372b  mov     rcx, [r14]; pSid
0x14000372e  xor     edx, edx; nSubAuthority
0x140003730  call    cs:__imp_GetSidSubAuthority
0x140003736  cmp     dword ptr [rax], 2000h
0x14000373c  jnb     loc_1400037DC
0x140003742  mov     rcx, r14; hMem
0x140003745  call    cs:__imp_LocalFree
0x14000374b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003752  mov     r14, [rsp+88h+var_20]
0x140003757  mov     rbp, [rsp+88h+arg_18]
0x14000375f  cmp     rcx, r15
0x140003762  mov     r15, [rsp+88h+var_28]
0x140003767  jnz     short loc_1400037BC
0x140003769  mov     eax, edi
0x14000376b  mov     rcx, [rsp+88h+var_38]
0x140003770  xor     rcx, rsp; StackCookie
0x140003773  call    __security_check_cookie
0x140003778  add     rsp, 70h
0x14000377c  pop     rdi
0x14000377d  pop     rsi
0x14000377e  pop     rbx
0x14000377f  retn
0x140003780  test    byte ptr [rcx+1Ch], 2
0x140003784  jz      loc_1400036BA
0x14000378a  mov     eax, [rbx]
0x14000378c  mov     edx, 0Eh
0x140003791  mov     r9d, [rbp+4]
0x140003795  mov     rcx, [rcx+10h]
0x140003799  mov     [rsp+88h+var_58], eax
0x14000379d  mov     eax, [rbp+30h]
0x1400037a0  mov     [rsp+88h+var_60], eax
0x1400037a4  mov     eax, [rbp+20h]
0x1400037a7  mov     dword ptr [rsp+88h+ReturnLength], eax
0x1400037ab  call    WPP_SF_ddDd
0x1400037b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037b7  jmp     loc_1400036BA
0x1400037bc  test    byte ptr [rcx+1Ch], 2
0x1400037c0  jz      short loc_140003769
0x1400037c2  mov     eax, [rbx]
0x1400037c4  mov     r9d, edi
0x1400037c7  mov     rcx, [rcx+10h]
0x1400037cb  mov     [rsp+88h+var_60], eax
0x1400037cf  mov     eax, [rsi]
0x1400037d1  mov     dword ptr [rsp+88h+ReturnLength], eax
0x1400037d5  call    WPP_SF_Ddd
0x1400037da  jmp     short loc_140003769
0x1400037dc  test    byte ptr [rbp+30h], 80h
0x1400037e0  jz      loc_140003742
0x1400037e6  mov     r8, rsi; enum _AUTO_APPROVE_TYPE *
0x1400037e9  mov     rdx, rbx; struct _CREDUI_CONTEXT *
0x1400037ec  mov     rcx, rbp; struct _CONSENTUI_PARAM_HEADER *
0x1400037ef  call    ?CuiCheckElevationAutoApprovalMedium@@YAKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@PEAW4_AUTO_APPROVE_TYPE@@@Z; CuiCheckElevationAutoApprovalMedium(_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,_AUTO_APPROVE_TYPE *)
0x1400037f4  mov     edi, eax
0x1400037f6  jmp     loc_140003742
0x1400037fb  mov     edi, 8
0x140003800  jmp     loc_14000374B
0x140003805  call    cs:__imp_GetLastError
0x14000380b  jmp     short loc_1400037F4
```
