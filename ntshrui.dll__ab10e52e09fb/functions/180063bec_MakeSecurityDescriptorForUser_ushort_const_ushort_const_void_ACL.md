# _MakeSecurityDescriptorForUser(ushort const *,ushort const *,void * *,_ACL * *)

- ea: `0x180063bec`
- end: `0x180063c8e`
- name: `?_MakeSecurityDescriptorForUser@@YAHPEBG0PEAPEAXPEAPEAU_ACL@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(LPCVOID lpSource, const unsigned __int16 *, void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063ef0`

## callees

- `0x180063bec`
- `0x180072e60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180063c6b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180063c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180063c3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180063c3a`

## pseudocode

```c
__int64 __fastcall _MakeSecurityDescriptorForUser(
        LPCVOID lpSource,
        const unsigned __int16 *a2,
        void **a3,
        struct _ACL **a4)
{
  unsigned int v4; // ebx
  PSECURITY_DESCRIPTOR v7; // rcx
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+28h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  *a4 = 0;
  StringSecurityDescriptor = 0;
  if ( FormatString((LPWSTR)&StringSecurityDescriptor, g_hInstance, lpSource, a2) )
  {
    SecurityDescriptor = 0;
    v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0);
    if ( v4 )
    {
      v7 = SecurityDescriptor;
      *a3 = SecurityDescriptor;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      GetSecurityDescriptorDacl(v7, &bDaclPresent, a4, &bDaclDefaulted);
    }
    LocalFree((HLOCAL)StringSecurityDescriptor);
  }
  return v4;
}

```

## disassembly

```asm
0x180063bec  mov     rax, rsp
0x180063bef  mov     [rax+8], rbx
0x180063bf3  mov     [rax+10h], rsi
0x180063bf7  push    rdi
0x180063bf8  sub     rsp, 40h
0x180063bfc  xor     ebx, ebx
0x180063bfe  mov     rdi, r9
0x180063c01  mov     [r9], rbx
0x180063c04  mov     rsi, r8
0x180063c07  mov     r9, rdx
0x180063c0a  mov     [rax-20h], rbx
0x180063c0e  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180063c15  mov     r8, rcx; lpSource
0x180063c18  lea     rcx, [rax-20h]; lpBuffer
0x180063c1c  call    ?FormatString@@YAKPEAPEAGPEAUHINSTANCE__@@PEBGZZ; FormatString(ushort * *,HINSTANCE__ *,ushort const *,...)
0x180063c21  test    eax, eax
0x180063c23  jz      short loc_180063C7C
0x180063c25  mov     rcx, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180063c2a  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180063c2f  xor     r9d, r9d; SecurityDescriptorSize
0x180063c32  mov     [rsp+48h+SecurityDescriptor], rbx
0x180063c37  lea     edx, [rbx+1]; StringSDRevision
0x180063c3a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180063c40  mov     ebx, eax
0x180063c42  test    eax, eax
0x180063c44  jz      short loc_180063C71
0x180063c46  mov     rcx, [rsp+48h+SecurityDescriptor]; pSecurityDescriptor
0x180063c4b  lea     r9, [rsp+48h+bDaclDefaulted]; lpbDaclDefaulted
0x180063c50  mov     r8, rdi; pDacl
0x180063c53  mov     [rsi], rcx
0x180063c56  lea     rdx, [rsp+48h+bDaclPresent]; lpbDaclPresent
0x180063c5b  mov     [rsp+48h+bDaclPresent], 0
0x180063c63  mov     [rsp+48h+bDaclDefaulted], 0
0x180063c6b  call    cs:__imp_GetSecurityDescriptorDacl
0x180063c71  mov     rcx, [rsp+48h+StringSecurityDescriptor]; hMem
0x180063c76  call    cs:__imp_LocalFree
0x180063c7c  mov     rsi, [rsp+48h+arg_8]
0x180063c81  mov     eax, ebx
0x180063c83  mov     rbx, [rsp+48h+arg_0]
0x180063c88  add     rsp, 40h
0x180063c8c  pop     rdi
0x180063c8d  retn
```
