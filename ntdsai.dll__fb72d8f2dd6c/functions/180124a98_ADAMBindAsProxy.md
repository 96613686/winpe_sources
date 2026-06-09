# ADAMBindAsProxy

- ea: `0x180124a98`
- end: `0x180124e15`
- name: `ADAMBindAsProxy`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1801241d0`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x180021aa3`
- `0x180124a98`
- `0x18040486c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124cf8`
- `ntdll!RtlNtStatusToDosError` at `0x180124b94`
- `ntdll!RtlNtStatusToDosError` at `0x180124b94`
- `ADVAPI32!LsaOpenPolicy` at `0x180124b75`
- `ADVAPI32!LsaOpenPolicy` at `0x180124b75`
- `ADVAPI32!LsaLookupSids` at `0x180124bca`
- `ADVAPI32!LsaLookupSids` at `0x180124bca`
- `ADVAPI32!LsaClose` at `0x180124dd8`
- `ADVAPI32!LsaClose` at `0x18045e83d`
- `ADVAPI32!LsaClose` at `0x180124dd8`
- `ADVAPI32!LsaClose` at `0x18045e83d`
- `ADVAPI32!LsaFreeMemory` at `0x180124db8`
- `ADVAPI32!LsaFreeMemory` at `0x180124dc8`
- `ADVAPI32!LsaFreeMemory` at `0x18045e81d`
- `ADVAPI32!LsaFreeMemory` at `0x18045e82d`
- `ADVAPI32!LsaFreeMemory` at `0x180124db8`
- `ADVAPI32!LsaFreeMemory` at `0x180124dc8`
- `ADVAPI32!LsaFreeMemory` at `0x18045e81d`
- `ADVAPI32!LsaFreeMemory` at `0x18045e82d`
- `ADVAPI32!LogonUserW` at `0x180124cea`
- `ADVAPI32!LogonUserW` at `0x180124cea`

## pseudocode

```c
__int64 __fastcall ADAMBindAsProxy(int a1, __int64 a2, const WCHAR *a3, void **a4, NTSTATUS *a5, DWORD *a6)
{
  int v9; // ebx
  void *v11; // rdi
  void *v12; // rsi
  int v13; // ebx
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  NTSTATUS v16; // ecx
  int v17; // r8d
  int v18; // r9d
  NTSTATUS v19; // eax
  DWORD LastError; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+48h] [rbp-88h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-80h] BYREF
  void *v28; // [rsp+58h] [rbp-78h]
  void *v29; // [rsp+60h] [rbp-70h]
  void *phToken; // [rsp+68h] [rbp-68h] BYREF
  PSID Sids; // [rsp+70h] [rbp-60h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-58h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+E0h] [rbp+10h] BYREF

  phToken = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ReferencedDomains = 0;
  Names = 0;
  Sids = (PSID)(a2 + 24);
  v9 = dword_180527FD0;
  if ( (gfADAMRequireSecureProxyBind || dword_180527FC8) && !(unsigned __int8)SampIsSecureLdapConnection() )
  {
    *a5 = -1073741715;
    *a6 = 8237;
    return 2148074252LL;
  }
  v11 = 0;
  v29 = 0;
  v12 = 0;
  v28 = 0;
  v13 = v9 != 0 ? 5 : 0;
  v14 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v14 >= 0 )
  {
    v19 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
    if ( v19 >= 0 )
    {
      v11 = (void *)THAlloc_(
                      a1,
                      1,
                      (unsigned int)ReferencedDomains->Domains[Names->DomainIndex].Name.Length + 2,
                      1,
                      0,
                      54004443);
      v29 = v11;
      v12 = (void *)THAlloc_(a1, 1, (unsigned int)Names->Name.Length + 2, 1, 0, 54004444);
      v28 = v12;
      memcpy_0(
        v11,
        ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
        ReferencedDomains->Domains[Names->DomainIndex].Name.Length);
      memcpy_0(v12, Names->Name.Buffer, Names->Name.Length);
      if ( LogonUserW((LPCWSTR)v12, (LPCWSTR)v11, a3, v13 + 3, 0, &phToken) )
      {
        *a4 = phToken;
        v15 = 0;
        *a6 = 0;
      }
      else
      {
        LastError = GetLastError();
        *a6 = LastError;
        v21 = LastError - 5;
        if ( v21 )
        {
          v22 = v21 - 1318;
          if ( v22 )
          {
            v23 = v22 - 7;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                v25 = v24 - 462;
                if ( v25 )
                {
                  if ( v25 == 116 )
                    *a5 = -1073741260;
                  else
                    *a5 = -1073741595;
                }
                else
                {
                  *a5 = -1073741421;
                }
              }
              else
              {
                *a5 = -1073741710;
              }
            }
            else
            {
              *a5 = -1073741711;
            }
          }
          else
          {
            *a5 = -1073741718;
          }
        }
        else
        {
          *a5 = -1073741790;
        }
        v15 = -2146893044;
      }
      goto LABEL_29;
    }
    if ( v19 == -1073741709 )
    {
      *a5 = -1073741724;
      v15 = -2146893044;
    }
    else
    {
      *a5 = v19;
      v15 = -2146893052;
    }
    v16 = v19;
  }
  else
  {
    *a5 = -1073741595;
    v15 = -2146893052;
    v16 = v14;
  }
  *a6 = RtlNtStatusToDosError(v16);
LABEL_29:
  if ( Names )
    LsaFreeMemory(Names);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v12 )
    THFreeAux(a1, (_DWORD)v12, v17, v18, 54004505);
  if ( v11 )
    THFreeAux(a1, (_DWORD)v11, v17, v18, 54004508);
  return v15;
}

```

## disassembly

```asm
0x180124a98  mov     rax, rsp
0x180124a9b  mov     [rax+18h], rbx
0x180124a9f  mov     [rax+8], rcx
0x180124aa3  push    rsi
0x180124aa4  push    rdi
0x180124aa5  push    r12
0x180124aa7  push    r14
0x180124aa9  push    r15
0x180124aab  sub     rsp, 90h
0x180124ab2  mov     r15, r9
0x180124ab5  mov     r12, r8
0x180124ab8  mov     r14, rcx
0x180124abb  mov     qword ptr [rax-68h], 0
0x180124ac3  mov     qword ptr [rax-80h], 0
0x180124acb  xorps   xmm0, xmm0
0x180124ace  movups  xmmword ptr [rax-58h], xmm0
0x180124ad2  movups  xmmword ptr [rax-48h], xmm0
0x180124ad6  movups  xmmword ptr [rax-38h], xmm0
0x180124ada  mov     [rsp+0B8h+ReferencedDomains], 0
0x180124ae3  mov     qword ptr [rax+10h], 0
0x180124aeb  lea     rax, [rdx+18h]
0x180124aef  mov     [rsp+0B8h+Sids], rax
0x180124af4  mov     ebx, cs:dword_180527FD0
0x180124afa  cmp     cs:gfADAMRequireSecureProxyBind, 0
0x180124b01  jnz     short loc_180124B0C
0x180124b03  cmp     cs:dword_180527FC8, 0
0x180124b0a  jz      short loc_180124B4E
0x180124b0c  call    SampIsSecureLdapConnection
0x180124b11  test    al, al
0x180124b13  jnz     short loc_180124B4E
0x180124b15  mov     rax, [rsp+0B8h+arg_20]
0x180124b1d  mov     dword ptr [rax], 0C000006Dh
0x180124b23  mov     rax, [rsp+0B8h+arg_28]
0x180124b2b  mov     dword ptr [rax], 202Dh
0x180124b31  mov     eax, 8009030Ch
0x180124b36  mov     rbx, [rsp+0B8h+arg_10]
0x180124b3e  add     rsp, 90h
0x180124b45  pop     r15
0x180124b47  pop     r14
0x180124b49  pop     r12
0x180124b4b  pop     rdi
0x180124b4c  pop     rsi
0x180124b4d  retn
0x180124b4e  xor     edi, edi
0x180124b50  mov     [rsp+0B8h+var_70], rdi
0x180124b55  xor     esi, esi
0x180124b57  mov     [rsp+0B8h+var_78], rsi
0x180124b5c  neg     ebx
0x180124b5e  sbb     ebx, ebx
0x180124b60  and     ebx, 5
0x180124b63  lea     r9, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x180124b68  mov     r8d, 800h; DesiredAccess
0x180124b6e  lea     rdx, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180124b73  xor     ecx, ecx; SystemName
0x180124b75  call    cs:__imp_LsaOpenPolicy
0x180124b7b  test    eax, eax
0x180124b7d  jns     short loc_180124BA9
0x180124b7f  mov     rcx, [rsp+0B8h+arg_20]
0x180124b87  mov     dword ptr [rcx], 0C00000E5h
0x180124b8d  mov     ebx, 80090304h
0x180124b92  mov     ecx, eax; Status
0x180124b94  call    cs:__imp_RtlNtStatusToDosError
0x180124b9a  mov     rcx, [rsp+0B8h+arg_28]
0x180124ba2  mov     [rcx], eax
0x180124ba4  jmp     loc_180124DAB
0x180124ba9  lea     rax, [rsp+0B8h+arg_8]
0x180124bb1  mov     [rsp+0B8h+Names], rax; Names
0x180124bb6  lea     r9, [rsp+0B8h+ReferencedDomains]; ReferencedDomains
0x180124bbb  lea     r8, [rsp+0B8h+Sids]; Sids
0x180124bc0  mov     edx, 1; Count
0x180124bc5  mov     rcx, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x180124bca  call    cs:__imp_LsaLookupSids
0x180124bd0  mov     edx, eax
0x180124bd2  test    eax, eax
0x180124bd4  jns     short loc_180124C05
0x180124bd6  cmp     eax, 0C0000073h
0x180124bdb  jnz     short loc_180124BF2
0x180124bdd  mov     rcx, [rsp+0B8h+arg_20]
0x180124be5  mov     dword ptr [rcx], 0C0000064h
0x180124beb  mov     ebx, 8009030Ch
0x180124bf0  jmp     short loc_180124C01
0x180124bf2  mov     rax, [rsp+0B8h+arg_20]
0x180124bfa  mov     [rax], edx
0x180124bfc  mov     ebx, 80090304h
0x180124c01  mov     ecx, edx
0x180124c03  jmp     short loc_180124B94
0x180124c05  mov     rax, [rsp+0B8h+arg_8]
0x180124c0d  movsxd  rcx, dword ptr [rax+18h]
0x180124c11  lea     rdx, [rcx+rcx*2]
0x180124c15  mov     rax, [rsp+0B8h+ReferencedDomains]
0x180124c1a  mov     rcx, [rax+8]
0x180124c1e  movzx   r8d, word ptr [rcx+rdx*8]
0x180124c23  add     r8, 2
0x180124c27  mov     dword ptr [rsp+0B8h+phToken], 3380ADBh
0x180124c2f  mov     dword ptr [rsp+0B8h+Names], 0
0x180124c37  mov     esi, 1
0x180124c3c  mov     r9d, esi
0x180124c3f  mov     edx, esi
0x180124c41  mov     rcx, r14
0x180124c44  call    THAlloc_
0x180124c49  mov     rdi, rax
0x180124c4c  mov     [rsp+0B8h+var_70], rax
0x180124c51  mov     rcx, [rsp+0B8h+arg_8]
0x180124c59  movzx   r8d, word ptr [rcx+8]
0x180124c5e  add     r8, 2
0x180124c62  mov     dword ptr [rsp+0B8h+phToken], 3380ADCh
0x180124c6a  mov     dword ptr [rsp+0B8h+Names], 0
0x180124c72  mov     r9d, esi
0x180124c75  mov     edx, esi
0x180124c77  mov     rcx, r14
0x180124c7a  call    THAlloc_
0x180124c7f  mov     rsi, rax
0x180124c82  mov     [rsp+0B8h+var_78], rax
0x180124c87  mov     rcx, [rsp+0B8h+arg_8]
0x180124c8f  movsxd  rdx, dword ptr [rcx+18h]
0x180124c93  lea     r10, [rdx+rdx*2]
0x180124c97  mov     rcx, [rsp+0B8h+ReferencedDomains]
0x180124c9c  mov     rdx, [rcx+8]
0x180124ca0  movzx   r8d, word ptr [rdx+r10*8]; Size
0x180124ca5  mov     rdx, [rdx+r10*8+8]; Src
0x180124caa  mov     rcx, rdi; void *
0x180124cad  call    memcpy_0
0x180124cb2  mov     rdx, [rsp+0B8h+arg_8]
0x180124cba  movzx   r8d, word ptr [rdx+8]; Size
0x180124cbf  mov     rdx, [rdx+10h]; Src
0x180124cc3  mov     rcx, rsi; void *
0x180124cc6  call    memcpy_0
0x180124ccb  lea     rax, [rsp+0B8h+var_68]
0x180124cd0  mov     [rsp+0B8h+phToken], rax; phToken
0x180124cd5  mov     dword ptr [rsp+0B8h+Names], 0; dwLogonProvider
0x180124cdd  lea     r9d, [rbx+3]; dwLogonType
0x180124ce1  mov     r8, r12; lpszPassword
0x180124ce4  mov     rdx, rdi; lpszDomain
0x180124ce7  mov     rcx, rsi; lpszUsername
0x180124cea  call    cs:__imp_LogonUserW
0x180124cf0  test    eax, eax
0x180124cf2  jnz     loc_180124D97
0x180124cf8  call    cs:__imp_GetLastError
0x180124cfe  mov     rcx, [rsp+0B8h+arg_28]
0x180124d06  mov     [rcx], eax
0x180124d08  sub     eax, 5
0x180124d0b  jz      short loc_180124D82
0x180124d0d  sub     eax, 526h
0x180124d12  jz      short loc_180124D72
0x180124d14  sub     eax, 7
0x180124d17  jz      short loc_180124D62
0x180124d19  sub     eax, 1
0x180124d1c  jz      short loc_180124D52
0x180124d1e  sub     eax, 1CEh
0x180124d23  jz      short loc_180124D42
0x180124d25  cmp     eax, 74h ; 't'
0x180124d28  mov     rax, [rsp+0B8h+arg_20]
0x180124d30  jz      short loc_180124D3A
0x180124d32  mov     dword ptr [rax], 0C00000E5h
0x180124d38  jmp     short loc_180124D90
0x180124d3a  mov     dword ptr [rax], 0C0000234h
0x180124d40  jmp     short loc_180124D90
0x180124d42  mov     rax, [rsp+0B8h+arg_20]
0x180124d4a  mov     dword ptr [rax], 0C0000193h
0x180124d50  jmp     short loc_180124D90
0x180124d52  mov     rax, [rsp+0B8h+arg_20]
0x180124d5a  mov     dword ptr [rax], 0C0000072h
0x180124d60  jmp     short loc_180124D90
0x180124d62  mov     rax, [rsp+0B8h+arg_20]
0x180124d6a  mov     dword ptr [rax], 0C0000071h
0x180124d70  jmp     short loc_180124D90
0x180124d72  mov     rax, [rsp+0B8h+arg_20]
0x180124d7a  mov     dword ptr [rax], 0C000006Ah
0x180124d80  jmp     short loc_180124D90
0x180124d82  mov     rax, [rsp+0B8h+arg_20]
0x180124d8a  mov     dword ptr [rax], 0C0000022h
0x180124d90  mov     ebx, 8009030Ch
0x180124d95  jmp     short loc_180124DAB
0x180124d97  mov     rax, [rsp+0B8h+var_68]
0x180124d9c  mov     [r15], rax
0x180124d9f  xor     ebx, ebx
0x180124da1  mov     rax, [rsp+0B8h+arg_28]
0x180124da9  mov     [rax], ebx
0x180124dab  mov     rcx, [rsp+0B8h+arg_8]; Buffer
0x180124db3  test    rcx, rcx
0x180124db6  jz      short loc_180124DBE
0x180124db8  call    cs:__imp_LsaFreeMemory
0x180124dbe  mov     rcx, [rsp+0B8h+ReferencedDomains]; Buffer
0x180124dc3  test    rcx, rcx
0x180124dc6  jz      short loc_180124DCE
0x180124dc8  call    cs:__imp_LsaFreeMemory
0x180124dce  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x180124dd3  test    rcx, rcx
0x180124dd6  jz      short loc_180124DDE
0x180124dd8  call    cs:__imp_LsaClose
0x180124dde  test    rsi, rsi
0x180124de1  jz      short loc_180124DF6
0x180124de3  mov     dword ptr [rsp+0B8h+Names], 3380B19h
0x180124deb  mov     rdx, rsi
0x180124dee  mov     rcx, r14
0x180124df1  call    THFreeAux
0x180124df6  test    rdi, rdi
0x180124df9  jz      short loc_180124E0E
0x180124dfb  mov     dword ptr [rsp+0B8h+Names], 3380B1Ch
0x180124e03  mov     rdx, rdi
0x180124e06  mov     rcx, r14
0x180124e09  call    THFreeAux
0x180124e0e  mov     eax, ebx
0x180124e10  jmp     loc_180124B36
0x18045e808  push    rbp
0x18045e80a  sub     rsp, 30h
0x18045e80e  mov     rbp, rdx
0x18045e811  mov     rcx, [rbp+0C8h]; Buffer
0x18045e818  test    rcx, rcx
0x18045e81b  jz      short loc_18045E824
0x18045e81d  call    cs:__imp_LsaFreeMemory
0x18045e823  nop
0x18045e824  mov     rcx, [rbp+30h]; Buffer
0x18045e828  test    rcx, rcx
0x18045e82b  jz      short loc_18045E834
0x18045e82d  call    cs:__imp_LsaFreeMemory
0x18045e833  nop
0x18045e834  mov     rcx, [rbp+38h]; ObjectHandle
0x18045e838  test    rcx, rcx
0x18045e83b  jz      short loc_18045E844
0x18045e83d  call    cs:__imp_LsaClose
0x18045e843  nop
0x18045e844  mov     rdx, [rbp+40h]
0x18045e848  test    rdx, rdx
0x18045e84b  jz      short loc_18045E869
0x18045e84d  mov     [rsp+38h+var_18], 3380B19h
0x18045e855  mov     rcx, [rbp+0C0h]
0x18045e85c  call    THFreeAux
0x18045e861  mov     qword ptr [rbp+40h], 0
0x18045e869  mov     rdx, [rbp+48h]
0x18045e86d  test    rdx, rdx
0x18045e870  jz      short loc_18045E88E
0x18045e872  mov     [rsp+38h+var_18], 3380B1Ch
0x18045e87a  mov     rcx, [rbp+0C0h]
0x18045e881  call    THFreeAux
0x18045e886  mov     qword ptr [rbp+48h], 0
0x18045e88e  add     rsp, 30h
0x18045e892  pop     rbp
0x18045e893  retn
```
