# SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x1800121fc`
- end: `0x180012328`
- name: `?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z`
- size: `300`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, HKEY, int, WCHAR *StringSecurityDescriptor)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000df14`
- `0x18000df6c`
- `0x18000e194`
- `0x1800121a8`

## callees

- `0x180003330`
- `0x1800063e0`
- `0x180007c60`
- `0x18000a6d0`
- `0x1800121fc`
- `0x180012388`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001230d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001230d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001226e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800122ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001226e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800122ba`

## pseudocode

```c
__int64 __fastcall SetHiveSecurity_(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        HKEY a5,
        int a6,
        WCHAR *StringSecurityDescriptor)
{
  int v11; // ebx
  const unsigned __int16 *v12; // r8
  WCHAR *v13; // rdi
  BOOL v14; // eax
  BOOL v15; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF

  StringSecurityDescriptor = 0;
  v11 = ResultFromHeapAllocArray<unsigned short>(a4, &StringSecurityDescriptor);
  if ( v11 >= 0 )
  {
    v12 = a2;
    v13 = StringSecurityDescriptor;
    v11 = StringCchPrintfW(StringSecurityDescriptor, a4, v12, a1);
    if ( v11 >= 0 )
    {
      SecurityDescriptor = 0;
      v14 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0);
      v11 = ResultFromWin32Bool(v14);
      if ( v11 >= 0 )
      {
        StringSecurityDescriptor = 0;
        v11 = StringCchPrintfW(v13, a4, a3, a1);
        if ( v11 >= 0 )
        {
          v15 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                  v13,
                  1u,
                  (PSECURITY_DESCRIPTOR *)&StringSecurityDescriptor,
                  0);
          v11 = ResultFromWin32Bool(v15);
          if ( v11 >= 0 )
          {
            v11 = _ApplySecurityToRegistryTree(a5, SecurityDescriptor, StringSecurityDescriptor, 1, a6);
            LocalFree(StringSecurityDescriptor);
          }
        }
        LocalFree(SecurityDescriptor);
      }
    }
    ResultFromHeapFree(v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800121fc  mov     rax, rsp
0x1800121ff  push    rbx
0x180012200  push    rbp
0x180012201  push    rsi
0x180012202  push    rdi
0x180012203  push    r14
0x180012205  sub     rsp, 40h
0x180012209  mov     rdi, rdx
0x18001220c  mov     qword ptr [rax+38h], 0
0x180012214  mov     rbp, rcx
0x180012217  lea     rdx, [rax+38h]
0x18001221b  mov     rcx, r9
0x18001221e  mov     rsi, r9
0x180012221  mov     r14, r8
0x180012224  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x180012229  mov     ebx, eax
0x18001222b  test    eax, eax
0x18001222d  js      loc_18001231B
0x180012233  mov     r8, rdi; unsigned __int16 *
0x180012236  mov     r9, rbp
0x180012239  mov     rdi, [rsp+68h+StringSecurityDescriptor]
0x180012241  mov     rdx, rsi; unsigned __int64
0x180012244  mov     rcx, rdi; unsigned __int16 *
0x180012247  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001224c  mov     ebx, eax
0x18001224e  test    eax, eax
0x180012250  js      loc_180012313
0x180012256  xor     r9d, r9d; SecurityDescriptorSize
0x180012259  mov     [rsp+68h+SecurityDescriptor], 0
0x180012262  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180012267  mov     rcx, rdi; StringSecurityDescriptor
0x18001226a  lea     edx, [r9+1]; StringSDRevision
0x18001226e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180012274  mov     ecx, eax; int
0x180012276  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001227b  mov     ebx, eax
0x18001227d  test    eax, eax
0x18001227f  js      loc_180012313
0x180012285  mov     r9, rbp
0x180012288  mov     [rsp+68h+StringSecurityDescriptor], 0
0x180012294  mov     r8, r14; unsigned __int16 *
0x180012297  mov     rdx, rsi; unsigned __int64
0x18001229a  mov     rcx, rdi; unsigned __int16 *
0x18001229d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800122a2  mov     ebx, eax
0x1800122a4  test    eax, eax
0x1800122a6  js      short loc_180012308
0x1800122a8  xor     r9d, r9d; SecurityDescriptorSize
0x1800122ab  lea     r8, [rsp+68h+StringSecurityDescriptor]; SecurityDescriptor
0x1800122b3  mov     rcx, rdi; StringSecurityDescriptor
0x1800122b6  lea     edx, [r9+1]; StringSDRevision
0x1800122ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800122c0  mov     ecx, eax; int
0x1800122c2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800122c7  mov     ebx, eax
0x1800122c9  test    eax, eax
0x1800122cb  js      short loc_180012308
0x1800122cd  mov     eax, [rsp+68h+arg_28]
0x1800122d4  mov     r9d, 1; int
0x1800122da  mov     r8, [rsp+68h+StringSecurityDescriptor]; void *
0x1800122e2  mov     rdx, [rsp+68h+SecurityDescriptor]; void *
0x1800122e7  mov     rcx, [rsp+68h+arg_20]; HKEY
0x1800122ef  mov     [rsp+68h+var_48], eax; int
0x1800122f3  call    ?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z; _ApplySecurityToRegistryTree(HKEY__ *,void *,void *,int,int)
0x1800122f8  mov     rcx, [rsp+68h+StringSecurityDescriptor]; hMem
0x180012300  mov     ebx, eax
0x180012302  call    cs:__imp_LocalFree
0x180012308  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x18001230d  call    cs:__imp_LocalFree
0x180012313  mov     rcx, rdi; lpMem
0x180012316  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001231b  mov     eax, ebx
0x18001231d  add     rsp, 40h
0x180012321  pop     r14
0x180012323  pop     rdi
0x180012324  pop     rsi
0x180012325  pop     rbp
0x180012326  pop     rbx
0x180012327  retn
```
