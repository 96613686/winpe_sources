# CSmbShareEngine::_GetShareAcl(ushort const *,CAceList * *)

- ea: `0x18005a814`
- end: `0x18005a92d`
- name: `?_GetShareAcl@CSmbShareEngine@@AEAAJPEBGPEAPEAVCAceList@@@Z`
- size: `281`
- prototype: `int(CSmbShareEngine *__hidden this, const unsigned __int16 *, struct CAceList **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005a664`

## callees

- `0x1800098dc`
- `0x18000b660`
- `0x180033fc0`
- `0x18005a814`
- `0x18005a934`
- `0x1800727d0`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a8b0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a8b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a8d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a8d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a8ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a8ed`

## pseudocode

```c
__int64 __fastcall CSmbShareEngine::_GetShareAcl(
        CSmbShareEngine *this,
        const unsigned __int16 *a2,
        struct CAceList **a3)
{
  int Instance; // ebx
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+28h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  struct IShareInfo *v9; // [rsp+38h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-10h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+78h] [rbp+28h] BYREF

  v9 = 0;
  if ( (int)CSmbShareEngine::_GetShareInfo(this, a2, &v9) < 0 )
  {
    return (unsigned int)CAceList::CreateInstance(a3);
  }
  else
  {
    pv = 0;
    Instance = (*(__int64 (__fastcall **)(struct IShareInfo *, LPVOID *))(*(_QWORD *)v9 + 64LL))(v9, &pv);
    if ( Instance >= 0 )
    {
      if ( pv )
      {
        pSecurityDescriptor = 0;
        if ( ConvertSDDLToSD((const unsigned __int16 *)pv, &pSecurityDescriptor) < 0 )
        {
          Instance = CAceList::CreateInstance(a3);
        }
        else
        {
          bDaclPresent = 0;
          bDaclDefaulted = 0;
          pDacl = 0;
          if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted)
            || (Instance = ResultFromKnownLastError(), Instance >= 0) )
          {
            Instance = CAceList::CreateInstance(pDacl, a3);
          }
          LocalFree(pSecurityDescriptor);
        }
        CoTaskMemFree(pv);
      }
      else
      {
        Instance = CAceList::CreateInstance(a3);
      }
    }
    (*(void (__fastcall **)(struct IShareInfo *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005a814  mov     [rsp-8+arg_0], rbx
0x18005a819  mov     [rsp-8+arg_8], rdi
0x18005a81e  push    rbp
0x18005a81f  mov     rbp, rsp
0x18005a822  sub     rsp, 50h
0x18005a826  mov     rdi, r8
0x18005a829  mov     [rbp+var_18], 0
0x18005a831  lea     r8, [rbp+var_18]; struct IShareInfo **
0x18005a835  call    ?_GetShareInfo@CSmbShareEngine@@AEAAJPEBGPEAPEAUIShareInfo@@@Z; CSmbShareEngine::_GetShareInfo(ushort const *,IShareInfo * *)
0x18005a83a  test    eax, eax
0x18005a83c  js      loc_18005A911
0x18005a842  mov     rcx, [rbp+var_18]
0x18005a846  lea     rdx, [rbp+pv]
0x18005a84a  mov     [rbp+pv], 0
0x18005a852  mov     rax, [rcx]
0x18005a855  mov     rax, [rax+40h]
0x18005a859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a85e  mov     ebx, eax
0x18005a860  test    eax, eax
0x18005a862  js      loc_18005A8FF
0x18005a868  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18005a86c  test    rcx, rcx
0x18005a86f  jz      loc_18005A8F5
0x18005a875  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x18005a879  mov     [rbp+pSecurityDescriptor], 0
0x18005a881  call    ?ConvertSDDLToSD@@YAJPEBGPEAPEAX@Z; ConvertSDDLToSD(ushort const *,void * *)
0x18005a886  test    eax, eax
0x18005a888  js      short loc_18005A8DF
0x18005a88a  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18005a88e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18005a892  lea     r8, [rbp+pDacl]; pDacl
0x18005a896  mov     [rbp+bDaclPresent], 0
0x18005a89d  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18005a8a1  mov     [rbp+bDaclDefaulted], 0
0x18005a8a8  mov     [rbp+pDacl], 0
0x18005a8b0  call    cs:__imp_GetSecurityDescriptorDacl
0x18005a8b6  test    eax, eax
0x18005a8b8  jnz     short loc_18005A8C5
0x18005a8ba  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005a8bf  mov     ebx, eax
0x18005a8c1  test    eax, eax
0x18005a8c3  js      short loc_18005A8D3
0x18005a8c5  mov     rcx, [rbp+pDacl]; struct _ACL *
0x18005a8c9  mov     rdx, rdi; struct CAceList **
0x18005a8cc  call    ?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAPEAV1@@Z; CAceList::CreateInstance(_ACL *,CAceList * *)
0x18005a8d1  mov     ebx, eax
0x18005a8d3  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x18005a8d7  call    cs:__imp_LocalFree
0x18005a8dd  jmp     short loc_18005A8E9
0x18005a8df  mov     rcx, rdi; struct CAceList **
0x18005a8e2  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x18005a8e7  mov     ebx, eax
0x18005a8e9  mov     rcx, [rbp+pv]; pv
0x18005a8ed  call    cs:__imp_CoTaskMemFree
0x18005a8f3  jmp     short loc_18005A8FF
0x18005a8f5  mov     rcx, rdi; struct CAceList **
0x18005a8f8  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x18005a8fd  mov     ebx, eax
0x18005a8ff  mov     rcx, [rbp+var_18]
0x18005a903  mov     rax, [rcx]
0x18005a906  mov     rax, [rax+10h]
0x18005a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a90f  jmp     short loc_18005A91B
0x18005a911  mov     rcx, rdi; struct CAceList **
0x18005a914  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x18005a919  mov     ebx, eax
0x18005a91b  mov     rdi, [rsp+50h+arg_8]
0x18005a920  mov     eax, ebx
0x18005a922  mov     rbx, [rsp+50h+arg_0]
0x18005a927  add     rsp, 50h
0x18005a92b  pop     rbp
0x18005a92c  retn
```
