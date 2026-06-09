# SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x180035b60`
- end: `0x180035c85`
- name: `?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z`
- size: `293`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, HKEY, int, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027910`
- `0x180037f78`
- `0x18003fe18`
- `0x18003fe74`
- `0x1800486bc`

## callees

- `0x180004170`
- `0x180006580`
- `0x180012290`
- `0x180024898`
- `0x180035b60`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035c6a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035bcf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035c15`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035bcf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035c15`

## pseudocode

```c
__int64 __fastcall SetHiveSecurity_(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        HKEY a5,
        int a6,
        int (*a7)(HKEY, void *, void *, int, int))
{
  int v11; // ebx
  const unsigned __int16 *v12; // r8
  WCHAR *v13; // rdi
  BOOL v14; // eax
  BOOL v15; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR StringSecurityDescriptor[6]; // [rsp+38h] [rbp-30h] BYREF

  StringSecurityDescriptor[0] = 0;
  v11 = ResultFromHeapAllocArray<unsigned short>(a4, StringSecurityDescriptor);
  if ( v11 >= 0 )
  {
    v12 = a2;
    v13 = (WCHAR *)StringSecurityDescriptor[0];
    v11 = StringCchPrintfW((unsigned __int16 *)StringSecurityDescriptor[0], a4, v12, a1);
    if ( v11 >= 0 )
    {
      StringSecurityDescriptor[0] = 0;
      v14 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              v13,
              1u,
              (PSECURITY_DESCRIPTOR *)StringSecurityDescriptor,
              0);
      v11 = ResultFromWin32Bool(v14);
      if ( v11 >= 0 )
      {
        SecurityDescriptor = 0;
        v11 = StringCchPrintfW(v13, a4, a3, a1);
        if ( v11 >= 0 )
        {
          v15 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0);
          v11 = ResultFromWin32Bool(v15);
          if ( v11 >= 0 )
          {
            v11 = ((__int64 (__fastcall *)(HKEY, LPCWSTR, PSECURITY_DESCRIPTOR, __int64, int))a7)(
                    a5,
                    StringSecurityDescriptor[0],
                    SecurityDescriptor,
                    1,
                    a6);
            LocalFree(SecurityDescriptor);
          }
        }
        LocalFree((HLOCAL)StringSecurityDescriptor[0]);
      }
    }
    ResultFromHeapFree(v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180035b60  push    rbx
0x180035b62  push    rbp
0x180035b63  push    rsi
0x180035b64  push    rdi
0x180035b65  push    r14
0x180035b67  sub     rsp, 40h
0x180035b6b  mov     rdi, rdx
0x180035b6e  mov     [rsp+68h+StringSecurityDescriptor], 0
0x180035b77  mov     rbp, rcx
0x180035b7a  lea     rdx, [rsp+68h+StringSecurityDescriptor]
0x180035b7f  mov     rcx, r9
0x180035b82  mov     rsi, r9
0x180035b85  mov     r14, r8
0x180035b88  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x180035b8d  mov     ebx, eax
0x180035b8f  test    eax, eax
0x180035b91  js      loc_180035C78
0x180035b97  mov     r8, rdi; unsigned __int16 *
0x180035b9a  mov     r9, rbp
0x180035b9d  mov     rdi, [rsp+68h+StringSecurityDescriptor]
0x180035ba2  mov     rdx, rsi; unsigned __int64
0x180035ba5  mov     rcx, rdi; unsigned __int16 *
0x180035ba8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035bad  mov     ebx, eax
0x180035baf  test    eax, eax
0x180035bb1  js      loc_180035C70
0x180035bb7  xor     r9d, r9d; SecurityDescriptorSize
0x180035bba  mov     [rsp+68h+StringSecurityDescriptor], 0
0x180035bc3  lea     r8, [rsp+68h+StringSecurityDescriptor]; SecurityDescriptor
0x180035bc8  mov     rcx, rdi; StringSecurityDescriptor
0x180035bcb  lea     edx, [r9+1]; StringSDRevision
0x180035bcf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035bd5  mov     ecx, eax; int
0x180035bd7  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180035bdc  mov     ebx, eax
0x180035bde  test    eax, eax
0x180035be0  js      loc_180035C70
0x180035be6  mov     r9, rbp
0x180035be9  mov     [rsp+68h+SecurityDescriptor], 0
0x180035bf2  mov     r8, r14; unsigned __int16 *
0x180035bf5  mov     rdx, rsi; unsigned __int64
0x180035bf8  mov     rcx, rdi; unsigned __int16 *
0x180035bfb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035c00  mov     ebx, eax
0x180035c02  test    eax, eax
0x180035c04  js      short loc_180035C65
0x180035c06  xor     r9d, r9d; SecurityDescriptorSize
0x180035c09  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180035c0e  mov     rcx, rdi; StringSecurityDescriptor
0x180035c11  lea     edx, [r9+1]; StringSDRevision
0x180035c15  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035c1b  mov     ecx, eax; int
0x180035c1d  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180035c22  mov     ebx, eax
0x180035c24  test    eax, eax
0x180035c26  js      short loc_180035C65
0x180035c28  mov     ecx, [rsp+68h+arg_28]
0x180035c2f  mov     r9d, 1
0x180035c35  mov     r8, [rsp+68h+SecurityDescriptor]
0x180035c3a  mov     rdx, [rsp+68h+StringSecurityDescriptor]
0x180035c3f  mov     rax, [rsp+68h+arg_30]
0x180035c47  mov     [rsp+68h+var_48], ecx
0x180035c4b  mov     rcx, [rsp+68h+arg_20]
0x180035c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c58  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180035c5d  mov     ebx, eax
0x180035c5f  call    cs:__imp_LocalFree
0x180035c65  mov     rcx, [rsp+68h+StringSecurityDescriptor]; hMem
0x180035c6a  call    cs:__imp_LocalFree
0x180035c70  mov     rcx, rdi; lpMem
0x180035c73  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180035c78  mov     eax, ebx
0x180035c7a  add     rsp, 40h
0x180035c7e  pop     r14
0x180035c80  pop     rdi
0x180035c81  pop     rsi
0x180035c82  pop     rbp
0x180035c83  pop     rbx
0x180035c84  retn
```
