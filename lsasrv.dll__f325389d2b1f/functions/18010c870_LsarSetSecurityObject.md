# LsarSetSecurityObject

- ea: `0x18010c870`
- end: `0x18010cbbb`
- name: `LsarSetSecurityObject`
- size: `843`
- prototype: `__int64 __fastcall(void *, SECURITY_INFORMATION SecurityInformation, struct _LSAPR_SR_SECURITY_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ddc0`
- `0x180010ba0`
- `0x18001f530`
- `0x180053dec`
- `0x18007cb90`
- `0x1800b34d4`
- `0x1800bd6e0`
- `0x18010c870`
- `0x18010cf70`
- `0x18011cb00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cb33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cb33`
- `api-ms-win-security-base-l1-1-0!SetSecurityAccessMask` at `0x18010c913`
- `api-ms-win-security-base-l1-1-0!SetSecurityAccessMask` at `0x18010c913`
- `ntdll!RtlFreeHeap` at `0x18010cb6c`
- `ntdll!RtlFreeHeap` at `0x18010cb6c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18010cacc`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18010cacc`
- `ntdll!RtlSetSecurityObject` at `0x18010cab6`
- `ntdll!RtlSetSecurityObject` at `0x18010cab6`
- `ntdll!RtlAllocateHeap` at `0x18010c9bd`
- `ntdll!RtlAllocateHeap` at `0x18010c9bd`
- `ntdll!NtClose` at `0x18010cb10`
- `ntdll!NtClose` at `0x18010cb10`
- `ntdll!NtOpenThreadToken` at `0x18010ca3d`
- `ntdll!NtOpenThreadToken` at `0x18010ca3d`
- `RPCRT4!RpcRevertToSelf` at `0x18010ca4b`
- `RPCRT4!RpcRevertToSelf` at `0x18010ca4b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010ca14`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010ca59`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010ca14`
- `RPCRT4!I_RpcMapWin32Status` at `0x18010ca59`
- `RPCRT4!RpcImpersonateClient` at `0x18010ca06`
- `RPCRT4!RpcImpersonateClient` at `0x18010ca06`

## pseudocode

```c
__int64 __fastcall LsarSetSecurityObject(
        _BYTE *a1,
        SECURITY_INFORMATION SecurityInformation,
        struct _LSAPR_SR_SECURITY_DESCRIPTOR *a3)
{
  char v3; // r12
  int Attribute; // ebx
  _BYTE *v8; // [rsp+A0h] [rbp+40h] BYREF
  DWORD DesiredAccess; // [rsp+B0h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+B8h] [rbp+58h]

  v8 = a1;
  DesiredAccess = 0;
  v3 = 0;
  TokenHandle = 0;
  if ( a3 && *((_QWORD *)a3 + 1) )
  {
    if ( LsapValidateLsaprSrSecurityDescriptorWithSecurityInformation(a3, SecurityInformation) )
    {
      Attribute = LsapDbVerifyHandle((__int64)a1, 0, 0, 0);
      if ( Attribute >= 0 )
      {
        if ( !a1[133] )
          SetSecurityAccessMask(SecurityInformation, &DesiredAccess);
        Attribute = LsapDbReferenceObject((struct _LSAP_DB_HANDLE *)a1, DesiredAccess, 9);
        if ( Attribute >= 0 )
        {
          v3 = 1;
          if ( LsaDbExtIsHandleDsHandle((struct _LSAP_DB_HANDLE *)a1) )
          {
            Attribute = -1073741637;
          }
          else
          {
            Attribute = LsapDbReadAttribute(a1);
            if ( Attribute >= 0 )
              Attribute = -1073741596;
          }
        }
      }
    }
    else
    {
      Attribute = -1073741703;
    }
  }
  else
  {
    Attribute = -1073741811;
  }
  while ( TokenHandle )
  {
    if ( TokenHandle != LsapGlobalProcessToken )
      NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( v3 )
    return (unsigned int)LsapDbDereferenceObject(
                           (unsigned int)&v8,
                           *((_DWORD *)a1 + 26),
                           *((_DWORD *)a1 + 26),
                           17,
                           7,
                           Attribute);
  return (unsigned int)Attribute;
}

```

## disassembly

```asm
0x18010c870  mov     [rsp-38h+arg_8], rbx
0x18010c875  mov     [rsp-38h+arg_0], rcx
0x18010c87a  push    rbp
0x18010c87b  push    rsi
0x18010c87c  push    rdi
0x18010c87d  push    r12
0x18010c87f  push    r13
0x18010c881  push    r14
0x18010c883  push    r15
0x18010c885  mov     rbp, rsp
0x18010c888  sub     rsp, 60h
0x18010c88c  xor     eax, eax
0x18010c88e  xor     r15d, r15d
0x18010c891  xorps   xmm0, xmm0
0x18010c894  mov     [rbp+DesiredAccess], r15d
0x18010c898  xor     esi, esi
0x18010c89a  mov     [rbp+var_8], rax
0x18010c89e  xor     r12b, r12b
0x18010c8a1  mov     [rbp+ObjectsSecurityDescriptor], rax
0x18010c8a5  mov     [rbp+TokenHandle], rax
0x18010c8a9  mov     rbx, r8
0x18010c8ac  mov     r14d, edx
0x18010c8af  mov     rdi, rcx
0x18010c8b2  movups  [rbp+var_28], xmm0
0x18010c8b6  movups  xmmword ptr [rbp+Size], xmm0
0x18010c8ba  test    r8, r8
0x18010c8bd  jnz     short loc_18010C8C9
0x18010c8bf  mov     ebx, 0C000000Dh
0x18010c8c4  jmp     loc_18010CAF4
0x18010c8c9  cmp     [r8+8], rax
0x18010c8cd  jz      short loc_18010C8BF
0x18010c8cf  mov     rcx, rbx; struct _LSAPR_SR_SECURITY_DESCRIPTOR *
0x18010c8d2  call    ?LsapValidateLsaprSrSecurityDescriptorWithSecurityInformation@@YAEPEAU_LSAPR_SR_SECURITY_DESCRIPTOR@@K@Z; LsapValidateLsaprSrSecurityDescriptorWithSecurityInformation(_LSAPR_SR_SECURITY_DESCRIPTOR *,ulong)
0x18010c8d7  test    al, al
0x18010c8d9  jnz     short loc_18010C8E5
0x18010c8db  mov     ebx, 0C0000079h
0x18010c8e0  jmp     loc_18010CAF4
0x18010c8e5  mov     r13, [rbx+8]
0x18010c8e9  xor     r9d, r9d
0x18010c8ec  xor     r8d, r8d
0x18010c8ef  xor     edx, edx
0x18010c8f1  mov     rcx, rdi
0x18010c8f4  call    LsapDbVerifyHandle
0x18010c8f9  mov     ebx, eax
0x18010c8fb  test    eax, eax
0x18010c8fd  js      loc_18010CAF4
0x18010c903  cmp     [rdi+85h], sil
0x18010c90a  jnz     short loc_18010C91F
0x18010c90c  lea     rdx, [rbp+DesiredAccess]; DesiredAccess
0x18010c910  mov     ecx, r14d; SecurityInformation
0x18010c913  call    cs:__imp_SetSecurityAccessMask
0x18010c91a  nop     dword ptr [rax+rax+00h]
0x18010c91f  mov     r8d, [rdi+68h]
0x18010c923  mov     rcx, rdi; struct _LSAP_DB_HANDLE *
0x18010c926  mov     edx, [rbp+DesiredAccess]; DesiredAccess
0x18010c929  mov     r9d, r8d
0x18010c92c  mov     dword ptr [rsp+60h+Token], 9; int
0x18010c934  call    LsapDbReferenceObject
0x18010c939  mov     ebx, eax
0x18010c93b  test    eax, eax
0x18010c93d  js      loc_18010CAF4
0x18010c943  mov     rcx, rdi; struct _LSAP_DB_HANDLE *
0x18010c946  mov     r12b, 1
0x18010c949  call    ?LsaDbExtIsHandleDsHandle@@YAEPEAU_LSAP_DB_HANDLE@@@Z; LsaDbExtIsHandleDsHandle(_LSAP_DB_HANDLE *)
0x18010c94e  test    al, al
0x18010c950  jz      short loc_18010C95C
0x18010c952  mov     ebx, 0C00000BBh
0x18010c957  jmp     loc_18010CAF4
0x18010c95c  lea     rax, ?LsapDbNames@@3PAU_UNICODE_STRING@@A; _UNICODE_STRING near * LsapDbNames
0x18010c963  mov     dword ptr [rbp+var_28], esi
0x18010c966  lea     rdx, [rbp+var_28]
0x18010c96a  mov     qword ptr [rbp+var_28+8], rax
0x18010c96e  mov     rcx, rdi; void *
0x18010c971  mov     [rbp+Size], rsi
0x18010c975  mov     dword ptr [rbp+Size+8], esi
0x18010c978  mov     word ptr [rbp+Size+0Ch], si
0x18010c97c  mov     byte ptr [rbp+Size+0Eh], sil
0x18010c980  call    LsapDbReadAttribute
0x18010c985  mov     ebx, eax
0x18010c987  test    eax, eax
0x18010c989  js      loc_18010CAF4
0x18010c98f  mov     rsi, [rbp+Size]
0x18010c993  test    rsi, rsi
0x18010c996  jnz     short loc_18010C9A2
0x18010c998  mov     ebx, 0C00000E4h
0x18010c99d  jmp     loc_18010CAF4
0x18010c9a2  mov     eax, dword ptr [rbp+Size+8]
0x18010c9a5  test    eax, eax
0x18010c9a7  jz      short loc_18010C998
0x18010c9a9  mov     rcx, gs:60h
0x18010c9b2  mov     r8d, eax; Size
0x18010c9b5  xor     edx, edx; Flags
0x18010c9b7  mov     ebx, eax
0x18010c9b9  mov     rcx, [rcx+30h]; HeapHandle
0x18010c9bd  call    cs:__imp_RtlAllocateHeap
0x18010c9c4  nop     dword ptr [rax+rax+00h]
0x18010c9c9  mov     [rbp+ObjectsSecurityDescriptor], rax
0x18010c9cd  test    rax, rax
0x18010c9d0  jnz     short loc_18010C9DC
0x18010c9d2  mov     ebx, 0C000009Ah
0x18010c9d7  jmp     loc_18010CAF4
0x18010c9dc  mov     r8, rbx; Size
0x18010c9df  mov     rdx, rsi; Src
0x18010c9e2  mov     rcx, rax; void *
0x18010c9e5  call    memcpy_0
0x18010c9ea  mov     [rbp+TokenHandle], r15
0x18010c9ee  test    r12b, r14b
0x18010c9f1  jz      loc_18010CA91
0x18010c9f7  cmp     [rdi+85h], r15b
0x18010c9fe  jnz     loc_18010CA86
0x18010ca04  xor     ecx, ecx; BindingHandle
0x18010ca06  call    cs:__imp_RpcImpersonateClient
0x18010ca0d  nop     dword ptr [rax+rax+00h]
0x18010ca12  mov     ecx, eax; Status
0x18010ca14  call    cs:__imp_I_RpcMapWin32Status
0x18010ca1b  nop     dword ptr [rax+rax+00h]
0x18010ca20  mov     ebx, eax
0x18010ca22  test    eax, eax
0x18010ca24  js      loc_18010CAF4
0x18010ca2a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010ca2e  mov     r8b, r12b; OpenAsSelf
0x18010ca31  mov     edx, 8; DesiredAccess
0x18010ca36  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18010ca3d  call    cs:__imp_NtOpenThreadToken
0x18010ca44  nop     dword ptr [rax+rax+00h]
0x18010ca49  mov     ebx, eax
0x18010ca4b  call    cs:__imp_RpcRevertToSelf
0x18010ca52  nop     dword ptr [rax+rax+00h]
0x18010ca57  mov     ecx, eax; Status
0x18010ca59  call    cs:__imp_I_RpcMapWin32Status
0x18010ca60  nop     dword ptr [rax+rax+00h]
0x18010ca65  mov     r15d, eax
0x18010ca68  test    eax, eax
0x18010ca6a  js      loc_18010CAF4
0x18010ca70  mov     eax, 80000000h
0x18010ca75  lea     ecx, [rbx+rax]
0x18010ca78  test    eax, ecx
0x18010ca7a  jnz     short loc_18010CA91
0x18010ca7c  cmp     ebx, 0C000007Ch
0x18010ca82  jnz     short loc_18010CAF4
0x18010ca84  jmp     short loc_18010CA91
0x18010ca86  mov     rax, cs:?LsapGlobalProcessToken@@3PEAXEA; void * LsapGlobalProcessToken
0x18010ca8d  mov     [rbp+TokenHandle], rax
0x18010ca91  movsxd  rax, dword ptr [rdi+68h]
0x18010ca95  lea     r8, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18010ca99  imul    r9, rax, 58h ; 'X'
0x18010ca9d  lea     rax, qword_18019F3B8
0x18010caa4  mov     rdx, r13; ModificationDescriptor
0x18010caa7  add     r9, rax; GenericMapping
0x18010caaa  mov     ecx, r14d; SecurityInformation
0x18010caad  mov     rax, [rbp+TokenHandle]
0x18010cab1  mov     [rsp+60h+Token], rax; Token
0x18010cab6  call    cs:__imp_RtlSetSecurityObject
0x18010cabd  nop     dword ptr [rax+rax+00h]
0x18010cac2  mov     ebx, eax
0x18010cac4  test    eax, eax
0x18010cac6  js      short loc_18010CAF4
0x18010cac8  mov     rcx, [rbp+ObjectsSecurityDescriptor]; SecurityDescriptor
0x18010cacc  call    cs:__imp_RtlLengthSecurityDescriptor
0x18010cad3  nop     dword ptr [rax+rax+00h]
0x18010cad8  mov     r8, [rbp+ObjectsSecurityDescriptor]; void *
0x18010cadc  lea     rdx, ?LsapDbNames@@3PAU_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x18010cae3  mov     r9d, eax; unsigned int
0x18010cae6  mov     rcx, rdi; void *
0x18010cae9  call    ?LsapDbWriteAttributeObject@@YAJPEAXPEAU_UNICODE_STRING@@0K@Z; LsapDbWriteAttributeObject(void *,_UNICODE_STRING *,void *,ulong)
0x18010caee  mov     ebx, eax
0x18010caf0  test    eax, eax
0x18010caf2  jns     short loc_18010CAFE
0x18010caf4  test    ebx, ebx
0x18010caf6  mov     eax, r15d
0x18010caf9  cmovs   eax, ebx
0x18010cafc  mov     ebx, eax
0x18010cafe  mov     rcx, [rbp+TokenHandle]; Handle
0x18010cb02  test    rcx, rcx
0x18010cb05  jz      short loc_18010CB2B
0x18010cb07  cmp     rcx, cs:?LsapGlobalProcessToken@@3PEAXEA; void * LsapGlobalProcessToken
0x18010cb0e  jz      short loc_18010CB1F
0x18010cb10  call    cs:__imp_NtClose
0x18010cb17  nop     dword ptr [rax+rax+00h]
0x18010cb1c  mov     r15d, eax
0x18010cb1f  mov     [rbp+TokenHandle], 0
0x18010cb27  test    ebx, ebx
0x18010cb29  js      short loc_18010CAF4
0x18010cb2b  test    rsi, rsi
0x18010cb2e  jz      short loc_18010CB3F
0x18010cb30  mov     rcx, rsi; hMem
0x18010cb33  call    cs:__imp_LocalFree
0x18010cb3a  nop     dword ptr [rax+rax+00h]
0x18010cb3f  mov     rcx, [rbp+ObjectsSecurityDescriptor]; void *
0x18010cb43  test    rcx, rcx
0x18010cb46  jz      short loc_18010CB78
0x18010cb48  test    ebx, ebx
0x18010cb4a  js      short loc_18010CB59
0x18010cb4c  cmp     dword ptr [rdi+68h], 1
0x18010cb50  jnz     short loc_18010CB59
0x18010cb52  call    ?LsapReplaceNewPolicyObjectSD@@YAXPEAX@Z; LsapReplaceNewPolicyObjectSD(void *)
0x18010cb57  jmp     short loc_18010CB78
0x18010cb59  mov     rcx, gs:60h
0x18010cb62  xor     edx, edx; Flags
0x18010cb64  mov     r8, [rbp+ObjectsSecurityDescriptor]; P
0x18010cb68  mov     rcx, [rcx+30h]; HeapHandle
0x18010cb6c  call    cs:__imp_RtlFreeHeap
0x18010cb73  nop     dword ptr [rax+rax+00h]
0x18010cb78  test    r12b, r12b
0x18010cb7b  jz      short loc_18010CBA0
0x18010cb7d  mov     edx, [rdi+68h]
0x18010cb80  lea     rcx, [rbp+arg_0]
0x18010cb84  mov     r8d, edx
0x18010cb87  mov     [rsp+60h+var_38], ebx
0x18010cb8b  mov     r9d, 11h
0x18010cb91  mov     dword ptr [rsp+60h+Token], 7
0x18010cb99  call    LsapDbDereferenceObject
0x18010cb9e  mov     ebx, eax
0x18010cba0  mov     eax, ebx
0x18010cba2  mov     rbx, [rsp+60h+arg_8]
0x18010cbaa  add     rsp, 60h
0x18010cbae  pop     r15
0x18010cbb0  pop     r14
0x18010cbb2  pop     r13
0x18010cbb4  pop     r12
0x18010cbb6  pop     rdi
0x18010cbb7  pop     rsi
0x18010cbb8  pop     rbp
0x18010cbb9  retn
```
