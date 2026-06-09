# TLSRpcCanLSUpdateAD

- ea: `0x180058b00`
- end: `0x180058f16`
- name: `TLSRpcCanLSUpdateAD`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, _WORD *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000d060`
- `0x18000e8b4`
- `0x18000f8b8`
- `0x18001ae3c`
- `0x180058284`
- `0x180058408`
- `0x180058b00`
- `0x18006d4cc`
- `0x18006d850`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!free` at `0x180058e33`
- `msvcrt!free` at `0x180058e47`
- `msvcrt!free` at `0x180058e60`
- `msvcrt!free` at `0x180058e33`
- `msvcrt!free` at `0x180058e47`
- `msvcrt!free` at `0x180058e60`
- `ADVAPI32!CreateWellKnownSid` at `0x180058d75`
- `ADVAPI32!CreateWellKnownSid` at `0x180058d75`
- `ADVAPI32!CheckTokenMembership` at `0x180058da0`
- `ADVAPI32!CheckTokenMembership` at `0x180058da0`
- `NETAPI32!DsRoleFreeMemory` at `0x180058e74`
- `NETAPI32!DsRoleFreeMemory` at `0x180058e74`
- `KERNEL32!GetComputerNameW` at `0x180058c84`
- `KERNEL32!GetComputerNameW` at `0x180058c84`
- `KERNEL32!GetLastError` at `0x180058c96`
- `KERNEL32!GetLastError` at `0x180058d87`
- `KERNEL32!GetLastError` at `0x180058c96`
- `KERNEL32!GetLastError` at `0x180058d87`
- `KERNEL32!LocalAlloc` at `0x180058d4a`
- `KERNEL32!LocalAlloc` at `0x180058d4a`
- `KERNEL32!LocalFree` at `0x180058e0b`
- `KERNEL32!LocalFree` at `0x180058e0b`

## string_xrefs

- `0x180058ba7`: `TLSRpcCanLSUpdateAD`
- `0x180058ea0`: `TLSRpcCanLSUpdateAD`
- `0x180058ece`: `TLSRpcCanLSUpdateAD`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TLSRpcCanLSUpdateAD(__int64 a1, _WORD *a2, _DWORD *a3, _DWORD *a4)
{
  _DWORD *v5; // rax
  void *v6; // rsi
  WCHAR *v7; // r13
  PVOID v8; // r14
  void *v9; // r12
  PVOID *v12; // rcx
  char IsEnabled; // al
  int v14; // ecx
  __int64 v15; // rbx
  bool v16; // zf
  unsigned int TSLSGroupNameAndDomainInfo; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // r9
  enum WELL_KNOWN_SID_TYPE v21; // r8d
  int v22; // ecx
  HLOCAL v23; // rax
  BOOL v24; // eax
  int v25; // eax
  int v27; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-C8h] BYREF
  WINBOOL IsMember; // [rsp+3Ch] [rbp-C4h] BYREF
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  PVOID v32; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v33; // [rsp+50h] [rbp-B0h]
  LPCWSTR localgroupname; // [rsp+58h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR servername; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[20]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t String1[512]; // [rsp+A0h] [rbp-60h] BYREF

  nSize = 16;
  v5 = a3;
  localgroupname = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  servername = 0;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  IsMember = 0;
  cbSid = 0;
  v33 = a3;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids,
      L"TLSRpcCanLSUpdateAD");
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v33;
  }
  if ( a1 && v5 && a4 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_1156395322>::GetImpl'::`2'::impl);
    v14 = *(_DWORD *)(a1 + 12) & 2;
    v15 = -1;
    if ( IsEnabled )
    {
      if ( !v14 )
      {
LABEL_11:
        TSLSGroupNameAndDomainInfo = 5;
LABEL_25:
        *v33 = 0;
        goto LABEL_51;
      }
      v16 = (unsigned int)IsCallFromAdmin() == 0;
    }
    else
    {
      v16 = v14 == 0;
    }
    if ( v16 )
      goto LABEL_11;
    *v33 = 0;
    if ( a2 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      if ( v18 )
        v6 = a2;
      Block = v6;
    }
    TSLSGroupNameAndDomainInfo = GetTSLSGroupNameAndDomainInfo(&servername, &Block, &localgroupname);
    v6 = Block;
    v7 = (WCHAR *)servername;
    if ( TSLSGroupNameAndDomainInfo )
      goto LABEL_25;
    TSLSGroupNameAndDomainInfo = IsLSonDC(&v27, &v32);
    if ( !TSLSGroupNameAndDomainInfo )
    {
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        v8 = v32;
        if ( !a2 )
          goto LABEL_31;
        v19 = -1;
        do
          ++v19;
        while ( a2[v19] );
        if ( v19 )
          v20 = (void *)*((_QWORD *)v32 + 1);
        else
LABEL_31:
          v20 = v6;
        StringCchPrintfW(String1, 0x200u, L"%s\\%s$", v20, Buffer);
        TSLSGroupNameAndDomainInfo = CheckGrpMembership(v7, localgroupname, String1, &v30);
        v22 = 0;
        if ( TSLSGroupNameAndDomainInfo )
          goto LABEL_25;
        if ( v27 != 1 )
          goto LABEL_44;
        TSLSGroupNameAndDomainInfo = CheckGrpMembership(v7, localgroupname, v21, &v31);
        if ( TSLSGroupNameAndDomainInfo )
          goto LABEL_25;
        cbSid = 68;
        v23 = LocalAlloc(0x40u, 0x44u);
        v9 = v23;
        if ( !v23 )
        {
          TSLSGroupNameAndDomainInfo = 8;
          goto LABEL_25;
        }
        if ( CreateWellKnownSid(WinBuiltinTerminalServerLicenseServersSid, 0, v23, &cbSid) )
        {
          v24 = CheckTokenMembership(0, v9, &IsMember);
          v22 = 0;
          if ( v24 )
          {
            if ( !IsMember )
              v22 = 1;
            goto LABEL_44;
          }
        }
        TSLSGroupNameAndDomainInfo = GetLastError();
LABEL_24:
        if ( TSLSGroupNameAndDomainInfo )
          goto LABEL_25;
        v22 = 0;
LABEL_44:
        *v33 = 1;
        v25 = 0;
        *a4 = 0;
        if ( !v30 )
        {
          v25 = 1;
          *a4 = 1;
        }
        if ( !v27 )
          goto LABEL_52;
        if ( !v31 )
        {
          v25 |= 2u;
          *a4 = v25;
        }
        if ( v22 != 1 )
          goto LABEL_52;
        TSLSGroupNameAndDomainInfo = v25 | 4;
LABEL_51:
        *a4 = TSLSGroupNameAndDomainInfo;
LABEL_52:
        if ( v9 )
          LocalFree(v9);
        if ( !a2 )
          goto LABEL_57;
        do
          ++v15;
        while ( a2[v15] );
        if ( !v15 )
        {
LABEL_57:
          if ( v6 )
            free(v6);
        }
        if ( v7 )
          free(v7);
        if ( localgroupname )
          free((void *)localgroupname);
        if ( v8 )
          DsRoleFreeMemory(v8);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids,
            L"TLSRpcCanLSUpdateAD");
        return 0;
      }
      TSLSGroupNameAndDomainInfo = GetLastError();
    }
    v8 = v32;
    goto LABEL_24;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x1000) != 0 )
    WPP_SF_S(v12[2], 37, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids, L"TLSRpcCanLSUpdateAD");
  return 87;
}

```

## disassembly

```asm
0x180058b00  mov     [rsp-8+arg_0], rbx
0x180058b05  push    rbp
0x180058b06  push    rsi
0x180058b07  push    rdi
0x180058b08  push    r12
0x180058b0a  push    r13
0x180058b0c  push    r14
0x180058b0e  push    r15
0x180058b10  lea     rbp, [rsp-3B0h]
0x180058b18  sub     rsp, 4B0h
0x180058b1f  mov     rax, cs:__security_cookie
0x180058b26  xor     rax, rsp
0x180058b29  mov     [rbp+3E0h+var_40], rax
0x180058b30  mov     rdi, rdx
0x180058b33  mov     [rsp+4E0h+nSize], 10h
0x180058b3b  xor     edx, edx
0x180058b3d  mov     rax, r8
0x180058b40  mov     [rsp+4E0h+localgroupname], rdx
0x180058b45  mov     esi, edx
0x180058b47  mov     [rsp+4E0h+Block], rdx
0x180058b4c  mov     r13d, edx
0x180058b4f  mov     [rsp+4E0h+servername], rdx
0x180058b54  mov     r14d, edx
0x180058b57  mov     [rsp+4E0h+var_498], rdx
0x180058b5c  mov     r12d, edx
0x180058b5f  mov     [rsp+4E0h+var_4AC], edx
0x180058b63  mov     r15, r9
0x180058b66  mov     [rsp+4E0h+var_4A0], edx
0x180058b6a  mov     rbx, rcx
0x180058b6d  mov     [rsp+4E0h+var_49C], edx
0x180058b71  mov     [rsp+4E0h+var_4B0], edx
0x180058b75  mov     [rsp+4E0h+IsMember], edx
0x180058b79  mov     [rsp+4E0h+cbSid], edx
0x180058b7d  mov     [rsp+4E0h+var_490], rax
0x180058b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180058b89  lea     r8, WPP_GLOBAL_Control
0x180058b90  cmp     rcx, r8
0x180058b93  jz      short loc_180058BCD
0x180058b95  test    dword ptr [rcx+1Ch], 1000h
0x180058b9c  jz      short loc_180058BCD
0x180058b9e  mov     rcx, [rcx+10h]
0x180058ba2  lea     edx, [r12+24h]
0x180058ba7  lea     r9, aTlsrpccanlsupd; "TLSRpcCanLSUpdateAD"
0x180058bae  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x180058bb5  call    WPP_SF_S
0x180058bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180058bc1  lea     r8, WPP_GLOBAL_Control
0x180058bc8  mov     rax, [rsp+4E0h+var_490]
0x180058bcd  test    rbx, rbx
0x180058bd0  jz      loc_180058EBC
0x180058bd6  test    rax, rax
0x180058bd9  jz      loc_180058EBC
0x180058bdf  test    r15, r15
0x180058be2  jz      loc_180058EBC
0x180058be8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1156395322@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1156395322@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322> `wil::Feature<__WilFeatureTraits_Feature_1156395322>::GetImpl(void)'::`2'::impl
0x180058bef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1156395322@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1156395322>::__private_IsEnabled(void)
0x180058bf4  mov     ecx, [rbx+0Ch]
0x180058bf7  xor     edx, edx
0x180058bf9  and     ecx, 2
0x180058bfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180058c00  test    al, al
0x180058c02  jz      short loc_180058C1D
0x180058c04  test    ecx, ecx
0x180058c06  jz      short loc_180058C13
0x180058c08  call    IsCallFromAdmin
0x180058c0d  xor     edx, edx
0x180058c0f  test    eax, eax
0x180058c11  jnz     short loc_180058C21
0x180058c13  mov     eax, 5
0x180058c18  jmp     loc_180058CAF
0x180058c1d  test    ecx, ecx
0x180058c1f  jmp     short loc_180058C11
0x180058c21  mov     rax, [rsp+4E0h+var_490]
0x180058c26  mov     [rax], edx
0x180058c28  test    rdi, rdi
0x180058c2b  jz      short loc_180058C45
0x180058c2d  mov     rax, rbx
0x180058c30  inc     rax
0x180058c33  cmp     [rdi+rax*2], dx
0x180058c37  jnz     short loc_180058C30
0x180058c39  test    rax, rax
0x180058c3c  cmovnz  rsi, rdi
0x180058c40  mov     [rsp+4E0h+Block], rsi
0x180058c45  lea     r8, [rsp+4E0h+localgroupname]
0x180058c4a  lea     rdx, [rsp+4E0h+Block]
0x180058c4f  lea     rcx, [rsp+4E0h+servername]
0x180058c54  call    GetTSLSGroupNameAndDomainInfo
0x180058c59  mov     rsi, [rsp+4E0h+Block]
0x180058c5e  mov     r13, [rsp+4E0h+servername]
0x180058c63  test    eax, eax
0x180058c65  jnz     short loc_180058CAF
0x180058c67  lea     rdx, [rsp+4E0h+var_498]
0x180058c6c  lea     rcx, [rsp+4E0h+var_4AC]
0x180058c71  call    IsLSonDC
0x180058c76  test    eax, eax
0x180058c78  jnz     short loc_180058CA2
0x180058c7a  lea     rdx, [rsp+4E0h+nSize]; nSize
0x180058c7f  lea     rcx, [rsp+4E0h+Buffer]; lpBuffer
0x180058c84  call    cs:__imp_GetComputerNameW
0x180058c8b  nop     dword ptr [rax+rax+00h]
0x180058c90  xor     ecx, ecx
0x180058c92  test    eax, eax
0x180058c94  jnz     short loc_180058CBC
0x180058c96  call    cs:__imp_GetLastError
0x180058c9d  nop     dword ptr [rax+rax+00h]
0x180058ca2  mov     r14, [rsp+4E0h+var_498]
0x180058ca7  test    eax, eax
0x180058ca9  jz      loc_180058DC1
0x180058caf  mov     rcx, [rsp+4E0h+var_490]
0x180058cb4  and     dword ptr [rcx], 0
0x180058cb7  jmp     loc_180058DFD
0x180058cbc  mov     r14, [rsp+4E0h+var_498]
0x180058cc1  test    rdi, rdi
0x180058cc4  jz      short loc_180058CDD
0x180058cc6  mov     rax, rbx
0x180058cc9  inc     rax
0x180058ccc  cmp     [rdi+rax*2], cx
0x180058cd0  jnz     short loc_180058CC9
0x180058cd2  test    rax, rax
0x180058cd5  jz      short loc_180058CDD
0x180058cd7  mov     r9, [r14+8]
0x180058cdb  jmp     short loc_180058CE0
0x180058cdd  mov     r9, rsi
0x180058ce0  lea     rax, [rsp+4E0h+Buffer]
0x180058ce5  mov     edx, 200h; unsigned __int64
0x180058cea  lea     r8, aSS; "%s\\%s$"
0x180058cf1  mov     [rsp+4E0h+var_4C0], rax
0x180058cf6  lea     rcx, [rbp+3E0h+String1]; unsigned __int16 *
0x180058cfa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058cff  mov     rdx, [rsp+4E0h+localgroupname]; localgroupname
0x180058d04  lea     r9, [rsp+4E0h+var_4A0]; int *
0x180058d09  lea     r8, [rbp+3E0h+String1]; String1
0x180058d0d  mov     rcx, r13; servername
0x180058d10  call    ?CheckGrpMembership@@YAKPEBG00PEAH@Z; CheckGrpMembership(ushort const *,ushort const *,ushort const *,int *)
0x180058d15  xor     ecx, ecx
0x180058d17  test    eax, eax
0x180058d19  jnz     short loc_180058CAF
0x180058d1b  cmp     [rsp+4E0h+var_4AC], 1
0x180058d20  jnz     loc_180058DBF
0x180058d26  mov     rdx, [rsp+4E0h+localgroupname]; localgroupname
0x180058d2b  lea     r9, [rsp+4E0h+var_49C]; int *
0x180058d30  mov     rcx, r13; servername
0x180058d33  call    ?CheckGrpMembership@@YAKPEBG0W4WELL_KNOWN_SID_TYPE@@PEAH@Z; CheckGrpMembership(ushort const *,ushort const *,WELL_KNOWN_SID_TYPE,int *)
0x180058d38  test    eax, eax
0x180058d3a  jnz     loc_180058CAF
0x180058d40  lea     edx, [rax+44h]; uBytes
0x180058d43  lea     ecx, [rax+40h]; uFlags
0x180058d46  mov     [rsp+4E0h+cbSid], edx
0x180058d4a  call    cs:__imp_LocalAlloc
0x180058d51  nop     dword ptr [rax+rax+00h]
0x180058d56  mov     r12, rax
0x180058d59  test    rax, rax
0x180058d5c  jnz     short loc_180058D68
0x180058d5e  lea     eax, [r12+8]
0x180058d63  jmp     loc_180058CAF
0x180058d68  xor     edx, edx; DomainSid
0x180058d6a  lea     r9, [rsp+4E0h+cbSid]; cbSid
0x180058d6f  mov     r8, r12; pSid
0x180058d72  lea     ecx, [rdx+3Ch]; WellKnownSidType
0x180058d75  call    cs:__imp_CreateWellKnownSid
0x180058d7c  nop     dword ptr [rax+rax+00h]
0x180058d81  xor     ecx, ecx; TokenHandle
0x180058d83  test    eax, eax
0x180058d85  jnz     short loc_180058D98
0x180058d87  call    cs:__imp_GetLastError
0x180058d8e  nop     dword ptr [rax+rax+00h]
0x180058d93  jmp     loc_180058CA7
0x180058d98  lea     r8, [rsp+4E0h+IsMember]; IsMember
0x180058d9d  mov     rdx, r12; SidToCheck
0x180058da0  call    cs:__imp_CheckTokenMembership
0x180058da7  nop     dword ptr [rax+rax+00h]
0x180058dac  xor     ecx, ecx
0x180058dae  test    eax, eax
0x180058db0  jz      short loc_180058D87
0x180058db2  cmp     [rsp+4E0h+IsMember], ecx
0x180058db6  jnz     short loc_180058DBF
0x180058db8  mov     ecx, 1
0x180058dbd  jmp     short loc_180058DC5
0x180058dbf  jmp     short loc_180058DC5
0x180058dc1  mov     ecx, [rsp+4E0h+var_4B0]
0x180058dc5  mov     rax, [rsp+4E0h+var_490]
0x180058dca  xor     edx, edx
0x180058dcc  mov     dword ptr [rax], 1
0x180058dd2  xor     eax, eax
0x180058dd4  mov     [r15], eax
0x180058dd7  cmp     [rsp+4E0h+var_4A0], edx
0x180058ddb  jnz     short loc_180058DE3
0x180058ddd  lea     eax, [rdx+1]
0x180058de0  mov     [r15], eax
0x180058de3  cmp     [rsp+4E0h+var_4AC], edx
0x180058de7  jz      short loc_180058E00
0x180058de9  cmp     [rsp+4E0h+var_49C], edx
0x180058ded  jnz     short loc_180058DF5
0x180058def  or      eax, 2
0x180058df2  mov     [r15], eax
0x180058df5  cmp     ecx, 1
0x180058df8  jnz     short loc_180058E00
0x180058dfa  or      eax, 4
0x180058dfd  mov     [r15], eax
0x180058e00  xor     r15d, r15d
0x180058e03  test    r12, r12
0x180058e06  jz      short loc_180058E17
0x180058e08  mov     rcx, r12; hMem
0x180058e0b  call    cs:__imp_LocalFree
0x180058e12  nop     dword ptr [rax+rax+00h]
0x180058e17  test    rdi, rdi
0x180058e1a  jz      short loc_180058E2B
0x180058e1c  inc     rbx
0x180058e1f  cmp     [rdi+rbx*2], r15w
0x180058e24  jnz     short loc_180058E1C
0x180058e26  test    rbx, rbx
0x180058e29  jnz     short loc_180058E3F
0x180058e2b  test    rsi, rsi
0x180058e2e  jz      short loc_180058E3F
0x180058e30  mov     rcx, rsi; Block
0x180058e33  call    cs:__imp_free
0x180058e3a  nop     dword ptr [rax+rax+00h]
0x180058e3f  test    r13, r13
0x180058e42  jz      short loc_180058E53
0x180058e44  mov     rcx, r13; Block
0x180058e47  call    cs:__imp_free
0x180058e4e  nop     dword ptr [rax+rax+00h]
0x180058e53  mov     rax, [rsp+4E0h+localgroupname]
0x180058e58  test    rax, rax
0x180058e5b  jz      short loc_180058E6C
0x180058e5d  mov     rcx, rax; Block
0x180058e60  call    cs:__imp_free
0x180058e67  nop     dword ptr [rax+rax+00h]
0x180058e6c  test    r14, r14
0x180058e6f  jz      short loc_180058E80
0x180058e71  mov     rcx, r14; Buffer
0x180058e74  call    cs:__imp_DsRoleFreeMemory
0x180058e7b  nop     dword ptr [rax+rax+00h]
0x180058e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180058e87  lea     rax, WPP_GLOBAL_Control
0x180058e8e  cmp     rcx, rax
0x180058e91  jz      short loc_180058EB8
0x180058e93  test    dword ptr [rcx+1Ch], 1000h
0x180058e9a  jz      short loc_180058EB8
0x180058e9c  mov     rcx, [rcx+10h]
0x180058ea0  lea     r9, aTlsrpccanlsupd; "TLSRpcCanLSUpdateAD"
0x180058ea7  mov     edx, 26h ; '&'
0x180058eac  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x180058eb3  call    WPP_SF_S
0x180058eb8  xor     eax, eax
0x180058eba  jmp     short loc_180058EEB
0x180058ebc  cmp     rcx, r8
0x180058ebf  jz      short loc_180058EE6
0x180058ec1  test    dword ptr [rcx+1Ch], 1000h
0x180058ec8  jz      short loc_180058EE6
0x180058eca  mov     rcx, [rcx+10h]
0x180058ece  lea     r9, aTlsrpccanlsupd; "TLSRpcCanLSUpdateAD"
0x180058ed5  mov     edx, 25h ; '%'
0x180058eda  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x180058ee1  call    WPP_SF_S
0x180058ee6  mov     eax, 57h ; 'W'
0x180058eeb  mov     rcx, [rbp+3E0h+var_40]
0x180058ef2  xor     rcx, rsp; StackCookie
0x180058ef5  call    __security_check_cookie
0x180058efa  mov     rbx, [rsp+4E0h+arg_0]
0x180058f02  add     rsp, 4B0h
0x180058f09  pop     r15
0x180058f0b  pop     r14
0x180058f0d  pop     r13
0x180058f0f  pop     r12
0x180058f11  pop     rdi
0x180058f12  pop     rsi
0x180058f13  pop     rbp
0x180058f14  retn
```
