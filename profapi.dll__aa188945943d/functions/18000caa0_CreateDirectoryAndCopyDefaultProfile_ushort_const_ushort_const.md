# _CreateDirectoryAndCopyDefaultProfile(ushort const *,ushort const *)

- ea: `0x18000caa0`
- end: `0x18000cba2`
- name: `?_CreateDirectoryAndCopyDefaultProfile@@YAJPEBG0@Z`
- size: `258`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d23c`

## callees

- `0x180001ab8`
- `0x180005b60`
- `0x18000caa0`
- `0x18000cba8`
- `0x180016834`
- `0x180016bec`
- `0x180016cf4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000caee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000caee`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000cb41`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000cb41`

## pseudocode

```c
__int64 __fastcall _CreateDirectoryAndCopyDefaultProfile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HLOCAL v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  hMem = 0;
  v3 = CreateSecurityDescriptorForUser(a1, (int)a2, &hMem);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    v6 = hMem;
    SecurityAttributes.lpSecurityDescriptor = hMem;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v7 = CreateNestedDirectory(a2, &SecurityAttributes);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( !SetFileSecurityW(a2, 4u, v6) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x171, v10, v11);
      v7 = _CopyFromDefaultProfile(a2, v6);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v8 = 0;
        goto LABEL_13;
      }
      v9 = 371;
    }
    else
    {
      v9 = 365;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)v7,
      SecurityAttributes.nLength);
LABEL_13:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
    return v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16A,
    (unsigned int)"minio\\profapi\\load.cpp",
    (const char *)(unsigned int)v3,
    SecurityAttributes.nLength);
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x18000caa0  mov     rax, rsp
0x18000caa3  mov     [rax+8], rbx
0x18000caa7  mov     [rax+10h], rsi
0x18000caab  push    rdi
0x18000caac  sub     rsp, 40h
0x18000cab0  mov     rsi, rdx
0x18000cab3  mov     qword ptr [rax+18h], 0
0x18000cabb  lea     r8, [rax+18h]; void **
0x18000cabf  call    ?CreateSecurityDescriptorForUser@@YAJPEBGHPEAPEAX@Z; CreateSecurityDescriptorForUser(ushort const *,int,void * *)
0x18000cac4  mov     ebx, eax
0x18000cac6  test    eax, eax
0x18000cac8  jns     short loc_18000CAFB
0x18000caca  mov     rcx, [rsp+48h]; this
0x18000cacf  mov     r9d, eax; char *
0x18000cad2  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000cad9  mov     edx, 16Ah; void *
0x18000cade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cae3  nop
0x18000cae4  mov     rcx, [rsp+48h+hMem]; hMem
0x18000cae9  test    rcx, rcx
0x18000caec  jz      short loc_18000CAF4
0x18000caee  call    cs:__imp_LocalFree
0x18000caf4  mov     eax, ebx
0x18000caf6  jmp     loc_18000CB92
0x18000cafb  mov     qword ptr [rsp+48h+SecurityAttributes.nLength], 18h; int
0x18000cb04  mov     rbx, [rsp+48h+hMem]
0x18000cb09  mov     [rsp+48h+SecurityAttributes.lpSecurityDescriptor], rbx
0x18000cb0e  mov     qword ptr [rsp+48h+SecurityAttributes.bInheritHandle], 0
0x18000cb17  lea     rdx, [rsp+48h+SecurityAttributes]; lpSecurityAttributes
0x18000cb1c  mov     rcx, rsi; unsigned __int16 *
0x18000cb1f  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000cb24  mov     edi, eax
0x18000cb26  test    eax, eax
0x18000cb28  jns     short loc_18000CB31
0x18000cb2a  mov     edx, 16Dh
0x18000cb2f  jmp     short loc_18000CB6E
0x18000cb31  mov     rdi, [rsp+48h]
0x18000cb36  mov     r8, rbx; pSecurityDescriptor
0x18000cb39  mov     edx, 4; SecurityInformation
0x18000cb3e  mov     rcx, rsi; lpFileName
0x18000cb41  call    cs:__imp_SetFileSecurityW
0x18000cb47  test    eax, eax
0x18000cb49  jnz     short loc_18000CB58
0x18000cb4b  mov     edx, 171h; void *
0x18000cb50  mov     rcx, rdi; this
0x18000cb53  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000cb58  mov     rdx, rbx; pSecurityDescriptor
0x18000cb5b  mov     rcx, rsi; unsigned __int16 *
0x18000cb5e  call    ?_CopyFromDefaultProfile@@YAJPEBGPEAX@Z; _CopyFromDefaultProfile(ushort const *,void *)
0x18000cb63  mov     edi, eax
0x18000cb65  test    eax, eax
0x18000cb67  jns     short loc_18000CB84
0x18000cb69  mov     edx, 173h; void *
0x18000cb6e  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000cb75  mov     r9d, eax; char *
0x18000cb78  mov     rcx, [rsp+48h]; this
0x18000cb7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb82  jmp     short loc_18000CB86
0x18000cb84  xor     edi, edi
0x18000cb86  lea     rcx, [rsp+48h+hMem]
0x18000cb8b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18000cb90  mov     eax, edi
0x18000cb92  mov     rbx, [rsp+48h+arg_0]
0x18000cb97  mov     rsi, [rsp+48h+arg_8]
0x18000cb9c  add     rsp, 40h
0x18000cba0  pop     rdi
0x18000cba1  retn
```
