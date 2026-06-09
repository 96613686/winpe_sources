# IsFolderPrivateForUser

- ea: `0x180063ca0`
- end: `0x180063ede`
- name: `IsFolderPrivateForUser`
- size: `574`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSid)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x180013220`
- `0x180063af0`
- `0x180063ca0`
- `0x180072ae4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180063d74`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180063d74`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180063e37`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180063e37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063da4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063e80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063da4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063e80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063eb6`
- `KERNEL32!lstrlenW` at `0x180063e6c`
- `KERNEL32!lstrlenW` at `0x180063e6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063e04`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063e04`
- `ADVAPI32!GetInheritanceSourceW` at `0x180063deb`
- `ADVAPI32!GetInheritanceSourceW` at `0x180063deb`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180063d3b`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180063d3b`

## pseudocode

```c
__int64 __fastcall IsFolderPrivateForUser(LPWSTR pObjectName, LPCWSTR StringSid, _DWORD *a3, unsigned __int16 **a4)
{
  PSECURITY_DESCRIPTOR v9; // rcx
  struct _INHERITED_FROMW *pInheritArray; // rax
  LPCWSTR *v11; // r14
  PACL v12; // rcx
  unsigned int v13; // esi
  PACL v14; // rbx
  __int64 v15; // rbx
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  PACL pAcl; // [rsp+50h] [rbp-20h] BYREF
  PSID Sid; // [rsp+58h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-10h] BYREF
  WORD pControl; // [rsp+C0h] [rbp+50h] BYREF
  DWORD dwRevision; // [rsp+C8h] [rbp+58h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( !a3 )
    return 0;
  *a3 = 0;
  if ( !pObjectName || !StringSid )
    return 0;
  if ( (unsigned int)DoesVolumeSupportSecurity(pObjectName) )
  {
    pSecurityDescriptor = 0;
    pAcl = 0;
    if ( GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &pSecurityDescriptor) )
    {
      *a3 = 4;
    }
    else
    {
      if ( (unsigned int)_IsDaclPrivateForUser(pAcl, StringSid) )
      {
        v9 = pSecurityDescriptor;
        pControl = 0;
        dwRevision = 0;
        *a3 = 1;
        GetSecurityDescriptorControl(v9, &pControl, &dwRevision);
        if ( (pControl & 0x1000) == 0 )
        {
          *a3 |= 2u;
          if ( a4 )
          {
            pInheritArray = (struct _INHERITED_FROMW *)LocalAlloc(0x40u, 16LL * pAcl->AceCount);
            v11 = (LPCWSTR *)pInheritArray;
            if ( pInheritArray )
            {
              if ( !GetInheritanceSourceW(pObjectName, SE_FILE_OBJECT, 4u, 1, 0, 0, pAcl, 0, &ShareMap, pInheritArray) )
              {
                Sid = 0;
                if ( ConvertStringSidToSidW(StringSid, &Sid) )
                {
                  v12 = pAcl;
                  v13 = 0;
                  v14 = pAcl + 1;
                  while ( v13 < v12->AceCount )
                  {
                    if ( v14->AclRevision <= 3u )
                    {
                      if ( EqualSid(Sid, &v14[1]) && (*(_DWORD *)&v14->AceCount & 0x1F01FF) == 0x1F01FF )
                      {
                        v15 = 2LL * v13;
                        if ( SLODWORD(v11[2 * v13]) > 0 )
                        {
                          v16 = lstrlenW(v11[2 * v13 + 1]) + 1;
                          v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
                          *a4 = v17;
                          if ( v17 )
                            StringCchCopyW(v17, v16, v11[v15 + 1]);
                        }
                        break;
                      }
                      v12 = pAcl;
                    }
                    ++v13;
                    v14 = (PACL)((char *)v14 + v14->AclSize);
                  }
                  LocalFree(Sid);
                }
              }
              LocalFree(v11);
            }
          }
        }
      }
      LocalFree(pSecurityDescriptor);
    }
    return 1;
  }
  else
  {
    *a3 = 4;
    return 1;
  }
}

```

## disassembly

```asm
0x180063ca0  mov     [rsp-38h+arg_0], rbx
0x180063ca5  push    rbp
0x180063ca6  push    rsi
0x180063ca7  push    rdi
0x180063ca8  push    r12
0x180063caa  push    r13
0x180063cac  push    r14
0x180063cae  push    r15
0x180063cb0  mov     rbp, rsp
0x180063cb3  sub     rsp, 70h
0x180063cb7  xor     r14d, r14d
0x180063cba  mov     r13, r9
0x180063cbd  mov     rbx, r8
0x180063cc0  mov     r12, rdx
0x180063cc3  mov     r15, rcx
0x180063cc6  test    r9, r9
0x180063cc9  jz      short loc_180063CCE
0x180063ccb  mov     [r9], r14
0x180063cce  test    rbx, rbx
0x180063cd1  jz      loc_180063EC4
0x180063cd7  mov     [r8], r14d
0x180063cda  test    r15, r15
0x180063cdd  jz      loc_180063EC4
0x180063ce3  test    r12, r12
0x180063ce6  jz      loc_180063EC4
0x180063cec  call    ?DoesVolumeSupportSecurity@@YAHPEBG@Z; DoesVolumeSupportSecurity(ushort const *)
0x180063cf1  test    eax, eax
0x180063cf3  jnz     short loc_180063D05
0x180063cf5  mov     dword ptr [rbx], 4
0x180063cfb  mov     eax, 1
0x180063d00  jmp     loc_180063EC6
0x180063d05  xor     r9d, r9d; ppsidOwner
0x180063d08  mov     [rbp+pSecurityDescriptor], r14
0x180063d0c  lea     rax, [rbp+pSecurityDescriptor]
0x180063d10  mov     [rbp+pAcl], r14
0x180063d14  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180063d19  mov     rcx, r15; pObjectName
0x180063d1c  lea     rax, [rbp+pAcl]
0x180063d20  mov     [rsp+70h+ppSacl], r14; ppSacl
0x180063d25  lea     esi, [r9+4]
0x180063d29  mov     [rsp+70h+ppDacl], rax; ppDacl
0x180063d2e  lea     edi, [rsi-3]
0x180063d31  mov     [rsp+70h+ppsidGroup], r14; ppsidGroup
0x180063d36  mov     edx, edi; ObjectType
0x180063d38  mov     r8d, esi; SecurityInfo
0x180063d3b  call    cs:__imp_GetNamedSecurityInfoW
0x180063d41  test    eax, eax
0x180063d43  jnz     loc_180063EBE
0x180063d49  mov     rcx, [rbp+pAcl]; pacl
0x180063d4d  mov     rdx, r12; StringSid
0x180063d50  call    ?_IsDaclPrivateForUser@@YAHPEAU_ACL@@PEBG@Z; _IsDaclPrivateForUser(_ACL *,ushort const *)
0x180063d55  test    eax, eax
0x180063d57  jz      loc_180063EB2
0x180063d5d  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180063d61  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180063d65  lea     rdx, [rbp+pControl]; pControl
0x180063d69  mov     [rbp+pControl], r14w
0x180063d6e  mov     [rbp+dwRevision], r14d
0x180063d72  mov     [rbx], edi
0x180063d74  call    cs:__imp_GetSecurityDescriptorControl
0x180063d7a  mov     eax, 1000h
0x180063d7f  test    [rbp+pControl], ax
0x180063d83  jnz     loc_180063EB2
0x180063d89  or      dword ptr [rbx], 2
0x180063d8c  test    r13, r13
0x180063d8f  jz      loc_180063EB2
0x180063d95  mov     rax, [rbp+pAcl]
0x180063d99  lea     ecx, [rsi+3Ch]; uFlags
0x180063d9c  movzx   edx, word ptr [rax+4]
0x180063da0  shl     rdx, 4; uBytes
0x180063da4  call    cs:__imp_LocalAlloc
0x180063daa  xor     ebx, ebx
0x180063dac  mov     r14, rax
0x180063daf  test    rax, rax
0x180063db2  jz      loc_180063EB2
0x180063db8  mov     rcx, [rbp+pAcl]
0x180063dbc  mov     r9d, edi; Container
0x180063dbf  mov     [rsp+70h+pInheritArray], rax; pInheritArray
0x180063dc4  mov     r8d, esi; SecurityInfo
0x180063dc7  lea     rax, ?ShareMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING ShareMap
0x180063dce  mov     edx, edi; ObjectType
0x180063dd0  mov     [rsp+70h+pGenericMapping], rax; pGenericMapping
0x180063dd5  mov     [rsp+70h+ppSecurityDescriptor], rbx; pfnArray
0x180063dda  mov     [rsp+70h+ppSacl], rcx; pAcl
0x180063ddf  mov     rcx, r15; pObjectName
0x180063de2  mov     dword ptr [rsp+70h+ppDacl], ebx; GuidCount
0x180063de6  mov     [rsp+70h+ppsidGroup], rbx; pObjectClassGuids
0x180063deb  call    cs:__imp_GetInheritanceSourceW
0x180063df1  test    eax, eax
0x180063df3  jnz     loc_180063EA9
0x180063df9  lea     rdx, [rbp+Sid]; Sid
0x180063dfd  mov     [rbp+Sid], rbx
0x180063e01  mov     rcx, r12; StringSid
0x180063e04  call    cs:__imp_ConvertStringSidToSidW
0x180063e0a  test    eax, eax
0x180063e0c  jz      loc_180063EA9
0x180063e12  mov     rcx, [rbp+pAcl]
0x180063e16  mov     esi, ebx
0x180063e18  mov     r15d, 1F01FFh
0x180063e1e  lea     rbx, [rcx+8]
0x180063e22  movzx   eax, word ptr [rcx+4]
0x180063e26  cmp     esi, eax
0x180063e28  jnb     short loc_180063E9F
0x180063e2a  cmp     byte ptr [rbx], 3
0x180063e2d  ja      short loc_180063E50
0x180063e2f  mov     rcx, [rbp+Sid]; pSid1
0x180063e33  lea     rdx, [rbx+8]; pSid2
0x180063e37  call    cs:__imp_EqualSid
0x180063e3d  test    eax, eax
0x180063e3f  jz      short loc_180063E4C
0x180063e41  mov     eax, [rbx+4]
0x180063e44  and     eax, r15d
0x180063e47  cmp     eax, r15d
0x180063e4a  jz      short loc_180063E5B
0x180063e4c  mov     rcx, [rbp+pAcl]
0x180063e50  movzx   eax, word ptr [rbx+2]
0x180063e54  add     esi, edi
0x180063e56  add     rbx, rax
0x180063e59  jmp     short loc_180063E22
0x180063e5b  mov     ebx, esi
0x180063e5d  add     rbx, rbx
0x180063e60  cmp     dword ptr [r14+rbx*8], 0
0x180063e65  jle     short loc_180063E9F
0x180063e67  mov     rcx, [r14+rbx*8+8]; lpString
0x180063e6c  call    cs:__imp_lstrlenW
0x180063e72  add     eax, edi
0x180063e74  mov     ecx, 40h ; '@'; uFlags
0x180063e79  movsxd  rsi, eax
0x180063e7c  lea     rdx, [rsi+rsi]; uBytes
0x180063e80  call    cs:__imp_LocalAlloc
0x180063e86  mov     [r13+0], rax
0x180063e8a  test    rax, rax
0x180063e8d  jz      short loc_180063E9F
0x180063e8f  mov     r8, [r14+rbx*8+8]; unsigned __int16 *
0x180063e94  mov     rdx, rsi; unsigned __int64
0x180063e97  mov     rcx, rax; unsigned __int16 *
0x180063e9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063e9f  mov     rcx, [rbp+Sid]; hMem
0x180063ea3  call    cs:__imp_LocalFree
0x180063ea9  mov     rcx, r14; hMem
0x180063eac  call    cs:__imp_LocalFree
0x180063eb2  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x180063eb6  call    cs:__imp_LocalFree
0x180063ebc  jmp     short loc_180063EC0
0x180063ebe  mov     [rbx], esi
0x180063ec0  mov     eax, edi
0x180063ec2  jmp     short loc_180063EC6
0x180063ec4  xor     eax, eax
0x180063ec6  mov     rbx, [rsp+70h+arg_0]
0x180063ece  add     rsp, 70h
0x180063ed2  pop     r15
0x180063ed4  pop     r14
0x180063ed6  pop     r13
0x180063ed8  pop     r12
0x180063eda  pop     rdi
0x180063edb  pop     rsi
0x180063edc  pop     rbp
0x180063edd  retn
```
