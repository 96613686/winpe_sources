# CSid::Initialize(void *,ushort const *)

- ea: `0x1800a9030`
- end: `0x1800a92a3`
- name: `?Initialize@CSid@@QEAA_NPEAXPEBG@Z`
- size: `627`
- prototype: `bool __fastcall(CSid *__hidden this, PSID pSourceSid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800a8418`

## callees

- `0x18000a504`
- `0x180072a08`
- `0x1800769f0`
- `0x18007d6f0`
- `0x18007dcbc`
- `0x1800a9030`
- `0x1800a9da8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a9096`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a90ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a9096`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a90ad`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800a907a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800a907a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a90bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a90bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a920a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a920a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a911a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a9193`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a911a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a9193`

## string_xrefs

- `0x1800a9054`: `CSid::Initialize - Entering...`
- `0x1800a9084`: `CSid::Initialize - IsValidSid returned false!`
- `0x1800a90c5`: `CSid::Initialize - Call to CopySid returned FALSE!`
- `0x1800a919d`: `CSid::Initialize - call to LookupAccountSid returned FALSE!`
- `0x1800a9214`: `CSid::Initialize - call to ConvertSidToStringSid returned false!`
- `0x1800a9274`: `CSid::Initialize - Leaving successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CSid::Initialize(CSid *this, PSID pSourceSid, const unsigned __int16 *a3)
{
  DWORD LengthSid; // eax
  void *v6; // rbx
  DWORD v7; // eax
  WCHAR *v8; // r14
  WCHAR *ReferencedDomainName; // r15
  char v10; // bl
  LPWSTR StringSid[4]; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *cchReferencedDomainName; // [rsp+A0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+48h] BYREF

  cchReferencedDomainName = a3;
  CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"CSid::Initialize - Entering...");
  CSid::Reset(this);
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v6 = operator new[](LengthSid);
    *((_QWORD *)this + 1) = v6;
    v7 = GetLengthSid(pSourceSid);
    if ( !CopySid(v7, v6, pSourceSid) )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 2u, L"CSid::Initialize - Call to CopySid returned FALSE!");
      CSid::Reset(this);
      return *(_BYTE *)this;
    }
    cchName = 0;
    LODWORD(cchReferencedDomainName) = 0;
    LookupAccountSidW(
      0,
      *((PSID *)this + 1),
      0,
      &cchName,
      0,
      (LPDWORD)&cchReferencedDomainName,
      (PSID_NAME_USE)this + 20);
    if ( cchName && (_DWORD)cchReferencedDomainName )
    {
      v8 = (WCHAR *)operator new[](saturated_mul(cchName, 2u));
      StringSid[1] = v8;
      ReferencedDomainName = (WCHAR *)operator new[](saturated_mul((unsigned int)cchReferencedDomainName, 2u));
      StringSid[2] = ReferencedDomainName;
      if ( !LookupAccountSidW(
              0,
              *((PSID *)this + 1),
              v8,
              &cchName,
              ReferencedDomainName,
              (LPDWORD)&cchReferencedDomainName,
              (PSID_NAME_USE)this + 20) )
      {
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"CSid::Initialize - call to LookupAccountSid returned FALSE!");
LABEL_9:
        CSid::Reset(this);
        v10 = *(_BYTE *)this;
LABEL_10:
        operator delete(ReferencedDomainName);
        operator delete(v8);
        return v10;
      }
      CWString::operator=((CSid *)((char *)this + 16));
      if ( !*((_BYTE *)this + 28) )
        goto LABEL_9;
      CWString::operator=((CSid *)((char *)this + 32));
      if ( !*((_BYTE *)this + 44) )
        goto LABEL_9;
      StringSid[0] = 0;
      if ( !ConvertSidToStringSidW(*((PSID *)this + 1), StringSid) )
      {
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgAccessCheck,
          2u,
          L"CSid::Initialize - call to ConvertSidToStringSid returned false!");
LABEL_15:
        CSid::Reset(this);
        v10 = *(_BYTE *)this;
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)StringSid);
        goto LABEL_10;
      }
      CWString::operator=((CSid *)((char *)this + 64));
      if ( !*((_BYTE *)this + 76) )
        goto LABEL_15;
      *(_BYTE *)this = 1;
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)StringSid);
      operator delete(ReferencedDomainName);
      operator delete(v8);
    }
    CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 4u, L"CSid::Initialize - Leaving successfully.");
    return *(_BYTE *)this;
  }
  CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 2u, L"CSid::Initialize - IsValidSid returned false!");
  return *(_BYTE *)this;
}

```

## disassembly

```asm
0x1800a9030  mov     [rsp-28h+arg_0], rbx
0x1800a9035  mov     [rsp-28h+arg_8], rsi
0x1800a903a  mov     [rsp-28h+arg_10], r8
0x1800a903f  push    rbp
0x1800a9040  push    rdi
0x1800a9041  push    r13
0x1800a9043  push    r14
0x1800a9045  push    r15
0x1800a9047  mov     rbp, rsp
0x1800a904a  sub     rsp, 60h
0x1800a904e  mov     rsi, rdx
0x1800a9051  mov     rdi, rcx
0x1800a9054  lea     r8, aCsidInitialize; "CSid::Initialize - Entering..."
0x1800a905b  mov     edx, 4; unsigned int
0x1800a9060  lea     r13, ?dbgAccessCheck@@3VCDebugWrapper@@A; CDebugWrapper dbgAccessCheck
0x1800a9067  mov     rcx, r13; this
0x1800a906a  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a906f  mov     rcx, rdi; this
0x1800a9072  call    ?Reset@CSid@@QEAAXXZ; CSid::Reset(void)
0x1800a9077  mov     rcx, rsi; pSid
0x1800a907a  call    cs:__imp_IsValidSid
0x1800a9080  test    eax, eax
0x1800a9082  jnz     short loc_1800A9093
0x1800a9084  lea     r8, aCsidInitialize_4; "CSid::Initialize - IsValidSid returned "...
0x1800a908b  lea     edx, [rax+2]
0x1800a908e  jmp     loc_1800A9280
0x1800a9093  mov     rcx, rsi; pSid
0x1800a9096  call    cs:__imp_GetLengthSid
0x1800a909c  mov     ecx, eax; unsigned __int64
0x1800a909e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a90a3  mov     rbx, rax
0x1800a90a6  mov     [rdi+8], rax
0x1800a90aa  mov     rcx, rsi; pSid
0x1800a90ad  call    cs:__imp_GetLengthSid
0x1800a90b3  mov     r8, rsi; pSourceSid
0x1800a90b6  mov     rdx, rbx; pDestinationSid
0x1800a90b9  mov     ecx, eax; nDestinationSidLength
0x1800a90bb  call    cs:__imp_CopySid
0x1800a90c1  test    eax, eax
0x1800a90c3  jnz     short loc_1800A90E4
0x1800a90c5  lea     r8, aCsidInitialize_2; "CSid::Initialize - Call to CopySid retu"...
0x1800a90cc  lea     edx, [rax+2]; unsigned int
0x1800a90cf  mov     rcx, r13; this
0x1800a90d2  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a90d7  mov     rcx, rdi; this
0x1800a90da  call    ?Reset@CSid@@QEAAXXZ; CSid::Reset(void)
0x1800a90df  jmp     loc_1800A9288
0x1800a90e4  mov     [rbp+cchName], 0
0x1800a90eb  mov     dword ptr [rbp+arg_10], 0
0x1800a90f2  lea     rbx, [rdi+50h]
0x1800a90f6  mov     [rsp+60h+peUse], rbx; peUse
0x1800a90fb  lea     rax, [rbp+arg_10]
0x1800a90ff  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a9104  mov     [rsp+60h+ReferencedDomainName], 0; ReferencedDomainName
0x1800a910d  lea     r9, [rbp+cchName]; cchName
0x1800a9111  xor     r8d, r8d; Name
0x1800a9114  mov     rdx, [rdi+8]; Sid
0x1800a9118  xor     ecx, ecx; lpSystemName
0x1800a911a  call    cs:__imp_LookupAccountSidW
0x1800a9120  mov     eax, [rbp+cchName]
0x1800a9123  test    eax, eax
0x1800a9125  jz      loc_1800A9274
0x1800a912b  cmp     dword ptr [rbp+arg_10], 0
0x1800a912f  jz      loc_1800A9274
0x1800a9135  mov     ecx, eax
0x1800a9137  mov     esi, 2
0x1800a913c  mov     eax, esi
0x1800a913e  mul     rcx
0x1800a9141  lea     r15, [rsi-3]
0x1800a9145  cmovb   rax, r15
0x1800a9149  mov     rcx, rax; unsigned __int64
0x1800a914c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a9151  mov     r14, rax
0x1800a9154  mov     [rbp+var_18], rax
0x1800a9158  mov     ecx, dword ptr [rbp+arg_10]
0x1800a915b  mov     eax, esi
0x1800a915d  mul     rcx
0x1800a9160  cmovb   rax, r15
0x1800a9164  mov     rcx, rax; unsigned __int64
0x1800a9167  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a916c  mov     r15, rax
0x1800a916f  mov     [rbp+var_10], rax
0x1800a9173  mov     [rsp+60h+peUse], rbx; peUse
0x1800a9178  lea     rax, [rbp+arg_10]
0x1800a917c  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a9181  mov     [rsp+60h+ReferencedDomainName], r15; ReferencedDomainName
0x1800a9186  lea     r9, [rbp+cchName]; cchName
0x1800a918a  mov     r8, r14; Name
0x1800a918d  mov     rdx, [rdi+8]; Sid
0x1800a9191  xor     ecx, ecx; lpSystemName
0x1800a9193  call    cs:__imp_LookupAccountSidW
0x1800a9199  test    eax, eax
0x1800a919b  jnz     short loc_1800A91D6
0x1800a919d  lea     r8, aCsidInitialize_3; "CSid::Initialize - call to LookupAccoun"...
0x1800a91a4  mov     edx, esi; unsigned int
0x1800a91a6  mov     rcx, r13; this
0x1800a91a9  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a91ae  mov     rcx, rdi; this
0x1800a91b1  call    ?Reset@CSid@@QEAAXXZ; CSid::Reset(void)
0x1800a91b6  mov     bl, [rdi]
0x1800a91b8  mov     rdx, rsi
0x1800a91bb  mov     rcx, r15; Block
0x1800a91be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a91c3  nop
0x1800a91c4  mov     rdx, rsi
0x1800a91c7  mov     rcx, r14; Block
0x1800a91ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a91cf  mov     al, bl
0x1800a91d1  jmp     loc_1800A928A
0x1800a91d6  lea     rcx, [rdi+10h]; this
0x1800a91da  mov     rdx, r14
0x1800a91dd  call    ??4CWString@@QEAAAEAV0@PEBG@Z; CWString::operator=(ushort const *)
0x1800a91e2  cmp     byte ptr [rdi+1Ch], 0
0x1800a91e6  jz      short loc_1800A91AE
0x1800a91e8  lea     rcx, [rdi+20h]; this
0x1800a91ec  mov     rdx, r15
0x1800a91ef  call    ??4CWString@@QEAAAEAV0@PEBG@Z; CWString::operator=(ushort const *)
0x1800a91f4  cmp     byte ptr [rdi+2Ch], 0
0x1800a91f8  jz      short loc_1800A91AE
0x1800a91fa  mov     [rbp+StringSid], 0
0x1800a9202  lea     rdx, [rbp+StringSid]; StringSid
0x1800a9206  mov     rcx, [rdi+8]; Sid
0x1800a920a  call    cs:__imp_ConvertSidToStringSidW
0x1800a9210  test    eax, eax
0x1800a9212  jnz     short loc_1800A923D
0x1800a9214  lea     r8, aCsidInitialize_0; "CSid::Initialize - call to ConvertSidTo"...
0x1800a921b  mov     edx, esi; unsigned int
0x1800a921d  mov     rcx, r13; this
0x1800a9220  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9225  mov     rcx, rdi; this
0x1800a9228  call    ?Reset@CSid@@QEAAXXZ; CSid::Reset(void)
0x1800a922d  mov     bl, [rdi]
0x1800a922f  lea     rcx, [rbp+StringSid]
0x1800a9233  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800a9238  jmp     loc_1800A91B8
0x1800a923d  lea     rcx, [rdi+40h]; this
0x1800a9241  mov     rdx, [rbp+StringSid]
0x1800a9245  call    ??4CWString@@QEAAAEAV0@PEBG@Z; CWString::operator=(ushort const *)
0x1800a924a  cmp     byte ptr [rdi+4Ch], 0
0x1800a924e  jz      short loc_1800A9225
0x1800a9250  mov     byte ptr [rdi], 1
0x1800a9253  lea     rcx, [rbp+StringSid]
0x1800a9257  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800a925c  nop
0x1800a925d  mov     rdx, rsi
0x1800a9260  mov     rcx, r15; Block
0x1800a9263  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a9268  nop
0x1800a9269  mov     rdx, rsi
0x1800a926c  mov     rcx, r14; Block
0x1800a926f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a9274  lea     r8, aCsidInitialize_1; "CSid::Initialize - Leaving successfully"...
0x1800a927b  mov     edx, 4; unsigned int
0x1800a9280  mov     rcx, r13; this
0x1800a9283  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800a9288  mov     al, [rdi]
0x1800a928a  lea     r11, [rsp+60h+var_s0]
0x1800a928f  mov     rbx, [r11+30h]
0x1800a9293  mov     rsi, [r11+38h]
0x1800a9297  mov     rsp, r11
0x1800a929a  pop     r15
0x1800a929c  pop     r14
0x1800a929e  pop     r13
0x1800a92a0  pop     rdi
0x1800a92a1  pop     rbp
0x1800a92a2  retn
```
