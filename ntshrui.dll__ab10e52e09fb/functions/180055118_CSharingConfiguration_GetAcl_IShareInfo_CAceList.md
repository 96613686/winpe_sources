# CSharingConfiguration::_GetAcl(IShareInfo *,CAceList * *)

- ea: `0x180055118`
- end: `0x1800551e2`
- name: `?_GetAcl@CSharingConfiguration@@AEAAJPEAUIShareInfo@@PEAPEAVCAceList@@@Z`
- size: `202`
- prototype: `int(CSharingConfiguration *__hidden this, struct IShareInfo *, struct CAceList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180054470`

## callees

- `0x1800098dc`
- `0x18000b660`
- `0x180033fc0`
- `0x180055118`
- `0x1800727d0`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180055195`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180055195`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551d2`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::_GetAcl(
        CSharingConfiguration *this,
        struct IShareInfo *a2,
        struct CAceList **a3)
{
  __int64 v3; // rax
  int Instance; // ebx
  LPVOID pv; // [rsp+20h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-8h] BYREF
  CSharingConfiguration *bDaclDefaulted; // [rsp+50h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp+38h] BYREF

  bDaclDefaulted = this;
  v3 = *(_QWORD *)a2;
  pv = 0;
  Instance = (*(__int64 (__fastcall **)(struct IShareInfo *, LPVOID *))(v3 + 64))(a2, &pv);
  if ( Instance >= 0 )
  {
    if ( pv )
    {
      pSecurityDescriptor = 0;
      Instance = ConvertSDDLToSD((const unsigned __int16 *)pv, &pSecurityDescriptor);
      if ( Instance >= 0 )
      {
        bDaclPresent = 0;
        LODWORD(bDaclDefaulted) = 0;
        pDacl = 0;
        if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)&bDaclDefaulted)
          || (Instance = ResultFromKnownLastError(), Instance >= 0) )
        {
          Instance = CAceList::CreateInstance(pDacl, a3);
        }
        CoTaskMemFree(pSecurityDescriptor);
      }
    }
    else
    {
      Instance = CAceList::CreateInstance(a3);
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180055118  mov     [rsp-18h+bDaclDefaulted], rcx
0x18005511d  push    rbp
0x18005511e  push    rbx
0x18005511f  push    rdi
0x180055120  mov     rbp, rsp
0x180055123  sub     rsp, 30h
0x180055127  mov     rax, [rdx]
0x18005512a  mov     rcx, rdx
0x18005512d  lea     rdx, [rbp+pv]
0x180055131  mov     [rbp+pv], 0
0x180055139  mov     rdi, r8
0x18005513c  mov     rax, [rax+40h]
0x180055140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055145  mov     ebx, eax
0x180055147  test    eax, eax
0x180055149  js      loc_1800551D8
0x18005514f  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180055153  test    rcx, rcx
0x180055156  jz      short loc_1800551C4
0x180055158  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x18005515c  mov     [rbp+pSecurityDescriptor], 0
0x180055164  call    ?ConvertSDDLToSD@@YAJPEBGPEAPEAX@Z; ConvertSDDLToSD(ushort const *,void * *)
0x180055169  mov     ebx, eax
0x18005516b  test    eax, eax
0x18005516d  js      short loc_1800551CE
0x18005516f  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180055173  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180055177  lea     r8, [rbp+pDacl]; pDacl
0x18005517b  mov     [rbp+bDaclPresent], 0
0x180055182  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180055186  mov     dword ptr [rbp+bDaclDefaulted], 0
0x18005518d  mov     [rbp+pDacl], 0
0x180055195  call    cs:__imp_GetSecurityDescriptorDacl
0x18005519b  test    eax, eax
0x18005519d  jnz     short loc_1800551AA
0x18005519f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800551a4  mov     ebx, eax
0x1800551a6  test    eax, eax
0x1800551a8  js      short loc_1800551B8
0x1800551aa  mov     rcx, [rbp+pDacl]; struct _ACL *
0x1800551ae  mov     rdx, rdi; struct CAceList **
0x1800551b1  call    ?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAPEAV1@@Z; CAceList::CreateInstance(_ACL *,CAceList * *)
0x1800551b6  mov     ebx, eax
0x1800551b8  mov     rcx, [rbp+pSecurityDescriptor]; pv
0x1800551bc  call    cs:__imp_CoTaskMemFree
0x1800551c2  jmp     short loc_1800551CE
0x1800551c4  mov     rcx, rdi; struct CAceList **
0x1800551c7  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x1800551cc  mov     ebx, eax
0x1800551ce  mov     rcx, [rbp+pv]; pv
0x1800551d2  call    cs:__imp_CoTaskMemFree
0x1800551d8  mov     eax, ebx
0x1800551da  add     rsp, 30h
0x1800551de  pop     rdi
0x1800551df  pop     rbx
0x1800551e0  pop     rbp
0x1800551e1  retn
```
