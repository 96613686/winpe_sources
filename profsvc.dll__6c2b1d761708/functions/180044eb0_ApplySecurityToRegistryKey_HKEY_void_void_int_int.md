# ApplySecurityToRegistryKey_(HKEY__ *,void *,void *,int,int)

- ea: `0x180044eb0`
- end: `0x18004515a`
- name: `?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z`
- size: `682`
- prototype: `__int64 __fastcall(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005370`
- `0x180011c00`
- `0x1800250b0`
- `0x18003fff4`
- `0x180044eb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180044efc`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180044f52`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180044efc`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180044f52`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180045033`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180045033`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180044fbc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180044fbc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180044fff`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180044fff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180044f8d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180045092`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180044f8d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180045092`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045125`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180045063`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180045063`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180045109`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180045109`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800450cd`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800450cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplySecurityToRegistryKey_(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a3)
{
  int v5; // eax
  PSECURITY_DESCRIPTOR v6; // rdi
  signed int v7; // ebx
  LSTATUS KeySecurity; // eax
  LSTATUS v9; // eax
  BOOL SecurityDescriptorDacl; // eax
  DWORD v11; // esi
  DWORD v12; // edx
  struct _ACL *v13; // rsi
  BOOL v14; // eax
  BOOL v15; // eax
  signed int ExplicitEntriesFromAclW; // eax
  BOOL v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-2Ch] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+4Ch] [rbp-24h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptora; // [rsp+60h] [rbp-10h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-8h] BYREF

  cbSecurityDescriptor = 512;
  pSecurityDescriptora = 0;
  v5 = ResultFromHeapAlloc(0x200u, &pSecurityDescriptora);
  v6 = pSecurityDescriptora;
  v7 = v5;
  if ( v5 >= 0 )
  {
    KeySecurity = RegGetKeySecurity(handle, 4u, pSecurityDescriptora, &cbSecurityDescriptor);
    v7 = KeySecurity;
    if ( KeySecurity > 0 )
      v7 = (unsigned __int16)KeySecurity | 0x80070000;
    if ( v7 == -2147024774 )
    {
      pSecurityDescriptora = 0;
      v7 = ResultFromHeapReAlloc(v6, cbSecurityDescriptor, &pSecurityDescriptora);
      if ( v7 < 0 )
        goto LABEL_26;
      v6 = pSecurityDescriptora;
      v9 = RegGetKeySecurity(handle, 4u, pSecurityDescriptora, &cbSecurityDescriptor);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v7 >= 0 )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
      v7 = ResultFromWin32Bool(SecurityDescriptorDacl);
      if ( v7 >= 0 )
      {
        pAce = 0;
        GetAce(pDacl, pDacl->AceCount - 1, &pAce);
        pSecurityDescriptora = 0;
        v11 = (unsigned __int16)(*((_WORD *)pAce + 1) + 8);
        v7 = ResultFromHeapAlloc((unsigned __int16)(*((_WORD *)pAce + 1) + 8), &pSecurityDescriptora);
        if ( v7 >= 0 )
        {
          v12 = v11;
          v13 = (struct _ACL *)pSecurityDescriptora;
          v14 = InitializeAcl((PACL)pSecurityDescriptora, v12, 2u);
          v7 = ResultFromWin32Bool(v14);
          if ( v7 >= 0 )
          {
            v15 = AddAce(v13, 2u, 0, pAce, *((unsigned __int16 *)pAce + 1));
            v7 = ResultFromWin32Bool(v15);
            if ( v7 >= 0 )
            {
              pcCountOfExplicitEntries = 0;
              pListOfExplicitEntries = 0;
              ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(
                                          v13,
                                          &pcCountOfExplicitEntries,
                                          &pListOfExplicitEntries);
              v7 = ExplicitEntriesFromAclW;
              if ( ExplicitEntriesFromAclW > 0 )
                v7 = (unsigned __int16)ExplicitEntriesFromAclW | 0x80070000;
              if ( v7 >= 0 )
              {
                v17 = GetSecurityDescriptorDacl(v6, &bDaclPresent, &pDacl, &bDaclDefaulted);
                v7 = ResultFromWin32Bool(v17);
                if ( v7 >= 0 && bDaclPresent && pDacl )
                {
                  pSecurityDescriptora = 0;
                  v18 = SetEntriesInAclW(
                          pcCountOfExplicitEntries,
                          pListOfExplicitEntries,
                          pDacl,
                          (PACL *)&pSecurityDescriptora);
                  v7 = v18;
                  if ( v18 > 0 )
                    v7 = (unsigned __int16)v18 | 0x80070000;
                  if ( v7 >= 0 )
                  {
                    v19 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)pSecurityDescriptora, 0);
                    v7 = v19;
                    if ( v19 > 0 )
                      v7 = (unsigned __int16)v19 | 0x80070000;
                    LocalFree(pSecurityDescriptora);
                  }
                }
              }
            }
          }
          ResultFromHeapFree(v13);
        }
      }
    }
  }
LABEL_26:
  ResultFromHeapFree(v6);
  ResultFromHeapFree(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180044eb0  push    rbp
0x180044eb2  push    rbx
0x180044eb3  push    rsi
0x180044eb4  push    rdi
0x180044eb5  push    r12
0x180044eb7  push    r14
0x180044eb9  push    r15
0x180044ebb  mov     rbp, rsp
0x180044ebe  sub     rsp, 70h
0x180044ec2  mov     r14, rcx
0x180044ec5  mov     rsi, rdx
0x180044ec8  mov     ecx, 200h; dwBytes
0x180044ecd  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x180044ed1  xor     r15d, r15d
0x180044ed4  mov     [rbp+cbSecurityDescriptor], ecx
0x180044ed7  mov     [rbp+pSecurityDescriptor], r15
0x180044edb  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180044ee0  mov     rdi, [rbp+pSecurityDescriptor]
0x180044ee4  mov     ebx, eax
0x180044ee6  test    eax, eax
0x180044ee8  js      loc_180045139
0x180044eee  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180044ef2  mov     r8, rdi; pSecurityDescriptor
0x180044ef5  lea     edx, [r15+4]; SecurityInformation
0x180044ef9  mov     rcx, r14; hKey
0x180044efc  call    cs:__imp_RegGetKeySecurity
0x180044f03  nop     dword ptr [rax+rax+00h]
0x180044f08  mov     ebx, eax
0x180044f0a  mov     r12d, 80070000h
0x180044f10  test    eax, eax
0x180044f12  jle     short loc_180044F1A
0x180044f14  movzx   ebx, ax
0x180044f17  or      ebx, r12d
0x180044f1a  cmp     ebx, 8007007Ah
0x180044f20  jnz     short loc_180044F6A
0x180044f22  mov     edx, [rbp+cbSecurityDescriptor]; dwBytes
0x180044f25  lea     r8, [rbp+pSecurityDescriptor]; void **
0x180044f29  mov     rcx, rdi; lpMem
0x180044f2c  mov     [rbp+pSecurityDescriptor], r15
0x180044f30  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180044f35  mov     ebx, eax
0x180044f37  test    eax, eax
0x180044f39  js      loc_180045139
0x180044f3f  mov     rdi, [rbp+pSecurityDescriptor]
0x180044f43  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180044f47  mov     r8, rdi; pSecurityDescriptor
0x180044f4a  mov     edx, 4; SecurityInformation
0x180044f4f  mov     rcx, r14; hKey
0x180044f52  call    cs:__imp_RegGetKeySecurity
0x180044f59  nop     dword ptr [rax+rax+00h]
0x180044f5e  mov     ebx, eax
0x180044f60  test    eax, eax
0x180044f62  jle     short loc_180044F6A
0x180044f64  movzx   ebx, ax
0x180044f67  or      ebx, r12d
0x180044f6a  test    ebx, ebx
0x180044f6c  js      loc_180045139
0x180044f72  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180044f76  mov     [rbp+pDacl], r15
0x180044f7a  lea     r8, [rbp+pDacl]; pDacl
0x180044f7e  mov     [rbp+bDaclPresent], r15d
0x180044f82  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180044f86  mov     [rbp+bDaclDefaulted], r15d
0x180044f8a  mov     rcx, rsi; pSecurityDescriptor
0x180044f8d  call    cs:__imp_GetSecurityDescriptorDacl
0x180044f94  nop     dword ptr [rax+rax+00h]
0x180044f99  mov     ecx, eax; int
0x180044f9b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180044fa0  mov     ebx, eax
0x180044fa2  test    eax, eax
0x180044fa4  js      loc_180045139
0x180044faa  mov     rcx, [rbp+pDacl]; pAcl
0x180044fae  lea     r8, [rbp+pAce]; pAce
0x180044fb2  mov     [rbp+pAce], r15
0x180044fb6  movzx   edx, word ptr [rcx+4]
0x180044fba  dec     edx; dwAceIndex
0x180044fbc  call    cs:__imp_GetAce
0x180044fc3  nop     dword ptr [rax+rax+00h]
0x180044fc8  mov     rax, [rbp+pAce]
0x180044fcc  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x180044fd0  mov     [rbp+pSecurityDescriptor], r15
0x180044fd4  movzx   ecx, word ptr [rax+2]
0x180044fd8  add     cx, 8
0x180044fdc  movzx   esi, cx
0x180044fdf  mov     ecx, esi; dwBytes
0x180044fe1  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180044fe6  mov     ebx, eax
0x180044fe8  test    eax, eax
0x180044fea  js      loc_180045139
0x180044ff0  mov     edx, esi; nAclLength
0x180044ff2  mov     r8d, 2; dwAclRevision
0x180044ff8  mov     rsi, [rbp+pSecurityDescriptor]
0x180044ffc  mov     rcx, rsi; pAcl
0x180044fff  call    cs:__imp_InitializeAcl
0x180045006  nop     dword ptr [rax+rax+00h]
0x18004500b  mov     ecx, eax; int
0x18004500d  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180045012  mov     ebx, eax
0x180045014  test    eax, eax
0x180045016  js      loc_180045131
0x18004501c  mov     r9, [rbp+pAce]; pAceList
0x180045020  xor     r8d, r8d; dwStartingAceIndex
0x180045023  mov     rcx, rsi; pAcl
0x180045026  movzx   eax, word ptr [r9+2]
0x18004502b  lea     edx, [r8+2]; dwAceRevision
0x18004502f  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x180045033  call    cs:__imp_AddAce
0x18004503a  nop     dword ptr [rax+rax+00h]
0x18004503f  mov     ecx, eax; int
0x180045041  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180045046  mov     ebx, eax
0x180045048  test    eax, eax
0x18004504a  js      loc_180045131
0x180045050  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180045054  mov     [rbp+pcCountOfExplicitEntries], r15d
0x180045058  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18004505c  mov     [rbp+pListOfExplicitEntries], r15
0x180045060  mov     rcx, rsi; pacl
0x180045063  call    cs:__imp_GetExplicitEntriesFromAclW
0x18004506a  nop     dword ptr [rax+rax+00h]
0x18004506f  mov     ebx, eax
0x180045071  test    eax, eax
0x180045073  jle     short loc_18004507B
0x180045075  movzx   ebx, ax
0x180045078  or      ebx, r12d
0x18004507b  test    ebx, ebx
0x18004507d  js      loc_180045131
0x180045083  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180045087  mov     rcx, rdi; pSecurityDescriptor
0x18004508a  lea     r8, [rbp+pDacl]; pDacl
0x18004508e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180045092  call    cs:__imp_GetSecurityDescriptorDacl
0x180045099  nop     dword ptr [rax+rax+00h]
0x18004509e  mov     ecx, eax; int
0x1800450a0  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800450a5  mov     ebx, eax
0x1800450a7  test    eax, eax
0x1800450a9  js      loc_180045131
0x1800450af  cmp     [rbp+bDaclPresent], r15d
0x1800450b3  jz      short loc_180045131
0x1800450b5  mov     r8, [rbp+pDacl]; OldAcl
0x1800450b9  test    r8, r8
0x1800450bc  jz      short loc_180045131
0x1800450be  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800450c2  lea     r9, [rbp+pSecurityDescriptor]; NewAcl
0x1800450c6  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x1800450c9  mov     [rbp+pSecurityDescriptor], r15
0x1800450cd  call    cs:__imp_SetEntriesInAclW
0x1800450d4  nop     dword ptr [rax+rax+00h]
0x1800450d9  mov     ebx, eax
0x1800450db  test    eax, eax
0x1800450dd  jle     short loc_1800450E5
0x1800450df  movzx   ebx, ax
0x1800450e2  or      ebx, r12d
0x1800450e5  test    ebx, ebx
0x1800450e7  js      short loc_180045131
0x1800450e9  mov     rax, [rbp+pSecurityDescriptor]
0x1800450ed  xor     r9d, r9d; psidOwner
0x1800450f0  mov     [rsp+70h+pSacl], r15; pSacl
0x1800450f5  mov     rcx, r14; handle
0x1800450f8  mov     [rsp+70h+var_48], rax; pDacl
0x1800450fd  mov     qword ptr [rsp+70h+nAceListLength], r15; psidGroup
0x180045102  lea     edx, [r9+4]; ObjectType
0x180045106  mov     r8d, edx; SecurityInfo
0x180045109  call    cs:__imp_SetSecurityInfo
0x180045110  nop     dword ptr [rax+rax+00h]
0x180045115  mov     ebx, eax
0x180045117  test    eax, eax
0x180045119  jle     short loc_180045121
0x18004511b  movzx   ebx, ax
0x18004511e  or      ebx, r12d
0x180045121  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x180045125  call    cs:__imp_LocalFree
0x18004512c  nop     dword ptr [rax+rax+00h]
0x180045131  mov     rcx, rsi; lpMem
0x180045134  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180045139  mov     rcx, rdi; lpMem
0x18004513c  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180045141  xor     ecx, ecx; lpMem
0x180045143  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180045148  mov     eax, ebx
0x18004514a  add     rsp, 70h
0x18004514e  pop     r15
0x180045150  pop     r14
0x180045152  pop     r12
0x180045154  pop     rdi
0x180045155  pop     rsi
0x180045156  pop     rbx
0x180045157  pop     rbp
0x180045158  retn
```
